---
description: "[!DNL Marketo Measure] Plantilla de informe - Tableau - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Plantilla de informe - Tableau"
exl-id: 18963be9-5c6e-4454-8244-b50460e2bed5
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '2323'
ht-degree: 0%

---

# Plantilla de informe de [!DNL Marketo Measure]: Cuadro {#marketo-measure-report-template-tableau}

## Introducción {#getting-started}

Puede acceder a las [!DNL Tableau] plantilla de informe [aquí](https://github.com/adobe/Marketo-Measure-BI-Templates){target="_blank"}.

Abra el [!DNL Adobe Marketo Measure] Archivo de libro Tableau de plantilla de informes.

Deberá actualizar los datos de conexión existentes con la información de conexión específica del Snowflake. Haga clic en [!UICONTROL Editar conexión] y siga los pasos descritos en la sección [[!UICONTROL Conexión de datos]](#data-connection) de esta documentación.

![](assets/marketo-measure-report-template-tableau-1.png)

## Conexión de datos {#data-connection}

Debe configurar una conexión de datos con la instancia de Snowflake. Para ello necesitará el nombre del servidor junto con su nombre de usuario y contraseña. Los detalles sobre dónde encontrar esta información y restablecer su contraseña, si es necesario, están documentados [aquí](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}.

![](assets/marketo-measure-report-template-tableau-2.png)

También deberá introducir un comando SQL inicial. Esto admite el uso de consultas personalizadas en este modelo de datos. El comando a introducir es &quot;Usar esquema&quot; `<your schema name>`&quot;. Puede localizar el nombre del esquema en la [!UICONTROL conexiones de data warehouse] , consulte la documentación a la que se hace referencia arriba.

![](assets/marketo-measure-report-template-tableau-3.png)

### Consultas SQL personalizadas {#custom-sql-queries}

Porque [!DNL Tableau] aplica filtros de fuente de datos a la consulta general y no a la tabla individual en la que está establecido el filtro. Hemos seleccionado utilizar SQL personalizado para cada tabla del modelo. Esto permite al modelo filtrar las filas eliminadas y duplicadas en el nivel de tabla. Por ejemplo, cuando se aplica como filtro de fuente de datos, sesión._deleted_date es null se agregará a la cláusula where de la consulta, lo que da como resultado la siguiente consulta.

**Filtros agregados a la fuente de datos**

```
--A deleted session removes this row completely and the touchpoint data is lost. Select *
   From Touchpoint    tp
      join Session sn
      on tp.session_id = sn.session_id 
 Where tp._deleted_date is null
    and sn._deleted_date is null
```

Sin embargo, esto no es correcto, ya que si se eliminó una sesión, pero no el punto de contacto correspondiente, los datos del punto de contacto se eliminan del conjunto de datos. Queremos que los datos del punto de contacto estén presentes en el conjunto de datos, ya que el punto de contacto no se ha eliminado. Añadir SQL personalizado garantiza que los criterios de filtro se apliquen en el nivel de tabla, lo que da como resultado la siguiente consulta.

**Filtros aplicados mediante SQL personalizado**

```
--A deleted session only removes the session related data, and the touchpoint data is preserved. Select *
   From Touchpoint       tp
      join Session sn
      on tp.session_id          = sn.session_id 
      and sn._deleted_date      is null
  Where tp._deleted_date is null
```

## Transformaciones de datos {#data-transformations}

Se han aplicado algunas transformaciones a los datos de [!DNL Tableau] a partir de su estado original en Snowflake. La mayoría de estas transformaciones se aplican en las consultas SQL personalizadas que generan las tablas en la variable [!DNL Tableau] modelo. Para ver el SQL personalizado utilizado para generar una tabla, haga clic con el botón derecho en el nombre de la tabla y seleccione &quot;Editar consulta SQL personalizada&quot;. A continuación se describen algunas de las transformaciones específicas.

![](assets/marketo-measure-report-template-tableau-4.png)

![](assets/marketo-measure-report-template-tableau-5.png)

### Columnas eliminadas {#removed-columns}

Para simplificar el modelo de datos y eliminar datos redundantes e innecesarios, hemos reducido el número de columnas importadas en Tableau desde la tabla del Snowflake original. Las columnas eliminadas incluyen claves externas innecesarias, datos dimensionales desnormalizados que se aprovechan mejor mediante relaciones con otras tablas del modelo, columnas de auditoría y campos utilizados para tareas internas [!DNL Marketo Measure] procesando. Puede agregar o quitar columnas según sea necesario para sus necesidades comerciales editando la lista de columnas importadas en la sección Seleccionar del SQL personalizado.

>[!NOTE]
>
>La mayoría de las tablas del almacén de datos contienen datos dimensionales desnormalizados. Hemos trabajado para normalizar y limpiar el modelo en [!DNL Tableau] lo más posible para mejorar el rendimiento y la precisión de los datos. Tenga cuidado al incluir campos desnormalizados adicionales en tablas de hechos, ya que esto podría romper el filtrado dimensional en todas las tablas y también podría generar informes inexactos.

### Columnas con nombre cambiado {#renamed-columns}

Se ha cambiado el nombre de las tablas y columnas para facilitar su uso y estandarizar las convenciones de nomenclatura. Para ver los cambios de nombre de columna, haga referencia a las instrucciones SQL personalizadas que crean las tablas.

### Filas añadidas {#rows-added}

Para agregar capacidades de conversión de moneda a los cálculos del modelo, hemos agregado una columna de tasa de conversión corporativa y una columna de tasa de conversión objetivo a las tablas Oportunidad y Costo. El valor de estas columnas se agrega al nivel de fila y se evalúa uniendo a la tabla Tasa de conversión tanto en la fecha como en el identificador de moneda. Dado que Tableau no permite que las tablas de hechos compartan más de una tabla de dimensiones, las tasas de conversión se añadieron directamente a las tablas que la utilizan. Para obtener más información sobre cómo funciona la conversión de moneda en este modelo, consulte la [Conversión de moneda](#currency-conversion) de esta documentación.

![](assets/marketo-measure-report-template-tableau-6.png)

Hay algunos lugares donde dos mesas de [!DNL Snowflake] se han combinado con una unión para crear una tabla en el [!DNL Tableau] modelo de datos de. En estos casos, se ha añadido una columna &quot;Tipo&quot; para indicar qué [!DNL Snowflake] de la que procede y designe qué entidad representa la fila. Para obtener más información sobre las tablas que se han combinado, consulte la sección Relación y flujo de datos en esta documentación.

![](assets/marketo-measure-report-template-tableau-7.png)

### Nombres de los segmentos {#segment-names}

Dado que los nombres de segmentos se pueden personalizar, tienen nombres de columna genéricos en el almacén de datos del Snowflake. [!DNL BIZ_SEGMENT_NAMES] es una tabla de asignación que enumera el nombre del segmento genérico con el nombre de segmento personalizado al que está asignado, tal como se define en la sección de segmentos en la [!DNL Marketo Measure] IU. Si utiliza nombres de segmento personalizados y desea actualizar su [!DNL Tableau] para incorporarlas, utilice esta tabla y cambie manualmente el nombre de las columnas dentro del modelo Tableau. Las columnas del segmento se encuentran en la tabla de puntos de contacto de cliente potencial y atribución, y solo será necesario cambiar el nombre una vez.

El [!UICONTROL CATEGORÍA] La columna muestra el número de categoría y la columna SEGMENT_NAME tiene el nombre de segmento personalizado al que se asigna.

![](assets/marketo-measure-report-template-tableau-8.png)

Los nombres se pueden actualizar de dos formas. La primera opción es actualizar el SQL personalizado. En este ejemplo, se ha cambiado el nombre de las categorías 1 a 6 en función de la asignación de la tabla Nombres de segmentos.

![](assets/marketo-measure-report-template-tableau-9.png)

La otra opción es cambiar el nombre de las columnas directamente en la [!DNL Tableau] tabla.

![](assets/marketo-measure-report-template-tableau-10.png)

## Modelo de datos {#data-model}

Haga clic en la imagen siguiente para ver su versión a tamaño completo.

[![](assets/marketo-measure-report-template-tableau-11.png)](/help/bi-report-templates/assets/tableau-data-model.png){target="_blank"}

### Relaciones y flujo de datos {#relationships-and-data-flow}

Los datos de evento, utilizados para crear puntos de contacto, se almacenan en [!UICONTROL Session], [!UICONTROL Tarea], [!UICONTROL Evento], [!UICONTROL Actividad], y [!UICONTROL Miembro de campaña] tablas. Estas tablas de eventos se unen a la tabla de puntos de contacto a través de sus respectivos ID. Si el evento resultó en un punto de contacto, los detalles se almacenan en la tabla de puntos de contacto.

Los puntos de contacto del posible cliente y los puntos de contacto de atribución se combinan en una tabla de este modelo, con un vínculo a la tabla de puntos de contacto. Se ha añadido la columna &quot;Tipo de punto de contacto&quot; para designar si una fila es un posible cliente o un punto de contacto de atribución. La mayoría de los datos dimensionales de los puntos de contacto de cliente potencial y atribución proceden de su vínculo al punto de contacto correspondiente.

Las transiciones de etapa de oportunidad y las transiciones de etapa de posible cliente se combinan en una tabla de este modelo, con un vínculo a la variable [!UICONTROL Posible cliente y atribución] Tabla de Touchpoint. Se ha añadido la columna Tipo de transición para designar si una fila es una transición de etapa de oportunidad o de posible cliente.

Tanto los datos de coste como los de punto de contacto comparten las dimensiones de canal y campaña. Sin embargo, Tableau tiene una capacidad limitada para modelar dimensiones compartidas entre tablas de hechos. Dado que estamos limitados a una sola tabla de dimensiones compartida, los datos de canal y campaña se han combinado en una tabla. Se combinan utilizando una combinación cruzada de las dos dimensiones en una tabla de Tableau: Channel y Campaign. El ID único se crea concatenando los ID de canal y de campaña. Este mismo valor de ID se agrega a las tablas Punto de contacto y Coste para crear una relación con esta tabla de dimensiones combinada.

![](assets/marketo-measure-report-template-tableau-12.png)

En este modelo, las dimensiones Campaña y Canal están vinculadas al punto de contacto, por lo que todos los informes sobre estas dimensiones se realizan a través de este vínculo, lo que significa que los informes dimensionales sobre los datos de evento pueden estar incompletos. Esto se debe a que muchos eventos no tienen vínculos a estas dimensiones hasta que se procesan en puntos de contacto.

>[!NOTE]
>
>Algunos eventos, como las Sesiones, tienen vínculos directos a las dimensiones Campaña y Canal. Si se desea realizar informes sobre estas dimensiones en el nivel de sesión, se recomienda crear un modelo de datos independiente para este fin.

Los datos de coste se almacenan en diferentes niveles de agregación dentro de la tabla de coste de Snowflake Data Warehouse. Para todos los proveedores de publicidad, los datos de nivel de campaña se pueden resumir en el nivel de canal. Por este motivo, este modelo extrae los datos de coste en función del indicador &quot;campaign_is_aggregatable_cost&quot;. Los costes autoinformados se pueden enviar solo a nivel de canal y no es necesario que tengan datos de Campaign. Para ofrecer la creación de informes de costes más precisa posible, los costes autoinformados se extraen en función del indicador &quot;channel_is_aggregatable_cost&quot;. La consulta que importa los datos de coste se escribe con la siguiente lógica: Si ad_provider = &quot;SelfReported&quot;, channel_is_aggregatable_cost = true; de lo contrario, campaign_is_aggregatable_cost = true.

En el contexto de este modelo, el posible cliente, [!UICONTROL Contacto], [!UICONTROL Cuenta], y [!UICONTROL Oportunidad] Los datos de se consideran datos dimensionales y se unen directamente a la tabla de puntos de contacto de cliente potencial y atribución.

### Conversión de moneda {#currency-conversion}

Las tasas de la tabla Tasa de conversión representan el valor necesario para convertir una cantidad de la moneda corporativa. Las conversiones a cualquier divisa requieren una conversión doble, primero de la divisa original a la divisa corporativa y, a continuación, de la divisa corporativa a la divisa seleccionada. El primer paso en esta cadena del modelo es añadir dos columnas con estas tasas de conversión a las tablas con importes, Oportunidad y Coste. Estos pasos se detallan en la sección Filas añadidas de este documento. Como no es necesario que las tasas de conversión sean estáticas y pueden cambiar según intervalos de fechas especificados, todos los cálculos de conversión de moneda deben realizarse en el nivel de fila. La conversión de la moneda original a la moneda corporativa consiste en dividir el valor por la tasa de conversión corporativa y, a continuación, multiplicar por la tasa de conversión objetivo. La tasa de conversión de destino está determinada por el valor de parámetro de moneda seleccionado.

* Convertir el valor original al valor en moneda corporativa / tasa de conversión corporativa = valor en moneda corporativa
* Convertir el valor de moneda corporativa al valor de moneda seleccionado en moneda corporativa `*` tasa de conversión de la moneda seleccionada = valor en la moneda seleccionada

![](assets/marketo-measure-report-template-tableau-13.png)

Las medidas de conversión de moneda de este modelo sustituyen la tasa por un valor de 1,0 si no se puede identificar ninguna tasa de conversión. Se han creado medidas independientes para mostrar el valor de moneda de la medida y avisar si un cálculo incluye más de un valor de moneda (es decir, no se pudo convertir un valor a la moneda seleccionada). Estas medidas, Moneda de coste y Moneda de ingresos, se incluyen como información sobre herramientas en cualquier imagen que muestre datos de Costes o Ingresos.

![](assets/marketo-measure-report-template-tableau-14.png)

## Definiciones de datos {#data-definitions}

Se han añadido definiciones a [!DNL Tableau model] para parámetros, columnas personalizadas y medidas.

![](assets/marketo-measure-report-template-tableau-15.png)

Para ver las definiciones de columnas procedentes directamente de [!DNL Snowflake], consulte la [documentación de data warehouse](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target="_blank"}.

## Discrepancias entre plantillas y Discover {#discrepancies-between-templates-and-discover}

### Ingresos atribuidos {#attributed-revenue}

Los puntos de contacto principales y los puntos de contacto de atribución heredan los datos dimensionales del punto de contacto original. El modelo de plantilla de informes obtiene todos los datos dimensionales heredados de la relación con Touchpoint, mientras que en el modelo Discover, los datos dimensionales se desnormalizan en los registros de punto de contacto de cliente potencial y atribución. Los valores generales de ingresos atribuidos o de ingresos atribuidos a la canalización deben alinearse entre los dos informes. Sin embargo, pueden observarse discrepancias cuando los ingresos se desglosan o filtran por datos dimensionales (canal, subcanal o campaña). Si las cantidades de ingresos dimensionales no coinciden entre la plantilla y Discover, es probable que falten registros de punto de contacto en el conjunto de datos del informe de plantilla. Esto sucede cuando hay un registro de punto de contacto de posible cliente o de atribución, pero no hay ningún registro correspondiente en la tabla de puntos de contacto dentro del conjunto de datos importado al informe. Dado que estas tablas se filtran por fecha de modificación, es posible que el registro de punto de contacto de cliente potencial/atribución se haya modificado más recientemente que el registro de punto de contacto y, por lo tanto, el punto de contacto de cliente potencial/atribución se haya importado al conjunto de datos mientras que el registro de punto de contacto original no lo estaba. Para solucionar este problema, amplíe el intervalo de fechas filtrado para la tabla de puntos de contacto o considere la posibilidad de eliminar la restricción de fecha en su totalidad.

>[!NOTE]
>
>Touchpoint es una tabla grande, así que considere las compensaciones de un conjunto de datos más completo en comparación con la cantidad de datos que deben importarse.

### Costo {#cost}

Los informes de costes en las plantillas solo están disponibles a nivel de campaña y canal. Sin embargo, Discover ofrece informes con niveles de granularidad más bajos para algunos proveedores de publicidad (es decir, creativo, de palabras clave, de grupos de publicidad, etc.). Para obtener más información sobre cómo se modelan los datos de costes en las plantillas, consulte la [!UICONTROL Modelo de datos] de esta documentación. Si el filtro de dimensión en [!UICONTROL Discover] se establece en canal o campaña, los costes en los niveles de canal, subcanal y campaña deben alinearse entre Discover y las plantillas de informe.

### Retorno de la inversión {#roi}

Dado que el ROI se calcula a partir de los ingresos atribuidos y el coste, las mismas discrepancias que pueden surgir en cualquiera de estos cálculos pueden surgir en el ROI y por los mismos motivos, como se indica en esas secciones.

### Puntos de contacto {#touchpoints}

Estas métricas, como se muestra en las plantillas de informes, no se reflejan en Discover. Actualmente no hay ninguna comparación directa posible entre ambos.

### Tráfico web {#web-traffic}

El modelo de datos de plantilla de creación de informes normaliza los datos dimensionales de canal, subcanal y campaña a través de la relación entre Session y Touchpoint. Esto es diferente al modelo de datos Discover, que desnormaliza estas dimensiones en Sesión. Debido a esta distinción, los recuentos generales de visitas y visitantes deben coincidir entre Discover y la plantilla de informes. Sin embargo, una vez mostrados o filtrados por dimensión, no se espera que estos números se alineen. Esto se debe a que los datos dimensionales de la plantilla solo están disponibles para eventos web que dieron como resultado un punto de contacto (es decir, eventos no anónimos). Para obtener más información, consulte la [Modelo de datos](#data-model) de esta documentación.

Puede haber pequeñas discrepancias en los recuentos totales de formularios del sitio entre [!DNL Discover] y la plantilla. Esto se debe a que el modelo de datos de la plantilla de informes obtiene datos dimensionales para el formulario del sitio mediante una relación con la sesión y, a continuación, con el punto de contacto; hay algunas instancias en las que los datos del formulario del sitio no tienen una sesión correlacionada.

### Posibles clientes y cuentas {#leads-and-accounts}

Los informes dimensionales para las cuentas tocadas pueden diferir ligeramente entre [!DNL Discover] y la plantilla, esto se debe de nuevo al modelado dimensional proveniente de la relación entre Touchpoint y Lead Touchpoint o Attribution Touchpoint. Consulte los detalles descritos en la sección Ingresos atribuidos para obtener más información.

Todos los recuentos de posibles clientes en [!UICONTROL Discover] se atribuyen a los recuentos de posibles clientes y, en la plantilla de informes, la métrica es [!UICONTROL posibles clientes] tocado. Por lo tanto, no existe una comparación directa posible entre los dos informes para esta medida.

### Ruta de participación {#engagement-path}

No hay comparación directa entre las variables [!UICONTROL Ruta de participación] informar en [!DNL Discover] y la plantilla. El informe en [!DNL Discover] se modela a partir del punto de contacto, mientras que el informe de la plantilla se modela a partir del punto de contacto de atribución. La plantilla se centra únicamente en las oportunidades y sus puntos de contacto relacionados, en lugar de mostrar todos los datos de puntos de contacto.

### Velocidad del acuerdo {#deal-velocity}

No debe haber discrepancias entre este informe en la plantilla y el mosaico Velocidad de la oferta en el panel Velocidad de la oferta en Discover.
