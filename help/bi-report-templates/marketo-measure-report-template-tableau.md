---
description: "[!DNL Marketo Measure] Plantilla de informe - Tableau - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Plantilla de informe - Tableau"
exl-id: 18963be9-5c6e-4454-8244-b50460e2bed5
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '2324'
ht-degree: 0%

---

# [!DNL Marketo Measure] Plantilla de informe: cuadro {#marketo-measure-report-template-tableau}

## Introducción {#getting-started}

Puede acceder al [!DNL Tableau] plantilla de informe [here](https://github.com/adobe/Marketo-Measure-BI-Templates){target="_blank"}.

Abra el [!DNL Adobe Marketo] Medir el archivo del libro Tableau de la plantilla de informes.

Deberá actualizar los datos de conexión existentes a la información de conexión específica del Snowflake. Haga clic en el [!UICONTROL Editar conexión] y siga los pasos descritos en la sección [[!UICONTROL Conexión de datos]](#data-connection) de esta documentación.

![](assets/marketo-measure-report-template-tableau-1.png)

## Conexión de datos {#data-connection}

Deberá configurar una conexión de datos en la instancia de Snowflake. Para ello, necesitará el nombre del servidor junto con su nombre de usuario y contraseña. Los detalles sobre dónde encontrar esta información y restablecer su contraseña, si es necesario, están documentados [here](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}.

![](assets/marketo-measure-report-template-tableau-2.png)

También deberá introducir un comando SQL inicial. Esto admite el uso de consultas personalizadas en este modelo de datos. El comando que se va a introducir es &quot;Usar esquema `<your schema name>`&quot;. Puede localizar el nombre del esquema en la variable [!UICONTROL conexiones del almacén de datos] consulte la documentación a la que se hace referencia más arriba.

![](assets/marketo-measure-report-template-tableau-3.png)

### Consultas SQL personalizadas {#custom-sql-queries}

Porque [!DNL Tableau] aplica filtros de fuente de datos a la consulta general y no a la tabla individual en la que está establecido el filtro. hemos elegido utilizar SQL personalizado para cada tabla del modelo. Esto permite que el modelo filtre las filas eliminadas y duplicadas en el nivel de tabla. Por ejemplo, cuando se aplica como filtro de fuente de datos, sesión._delete_date es nulo se agregará a la cláusula where de la consulta, lo que dará como resultado la siguiente consulta.

**Filtros agregados a la fuente de datos**

```
--A deleted session removes this row completely and the touchpoint data is lost. Select *
   From Touchpoint    tp
      join Session sn
      on tp.session_id = sn.session_id 
 Where tp._deleted_date is null
    and sn._deleted_date is null
```

Sin embargo, esto no es correcto, ya que si se elimina una sesión, pero el punto de contacto correspondiente no se elimina, los datos del punto de contacto se eliminan del conjunto de datos. Queremos que los datos de punto de contacto estén presentes en el conjunto de datos, ya que el punto de contacto no se ha eliminado. Añadir SQL personalizado garantiza que los criterios de filtro se apliquen en el nivel de tabla, lo que resulta en la siguiente consulta.

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

Se han aplicado algunas transformaciones a los datos de [!DNL Tableau] desde su estado original en Snowflake. La mayoría de estas transformaciones se aplican en consultas SQL personalizadas que generan las tablas en la variable [!DNL Tableau] modelo. Para ver el SQL personalizado utilizado para generar una tabla, haga clic con el botón derecho en el nombre de la tabla y seleccione Editar consulta SQL personalizada. A continuación se describen algunas de las transformaciones específicas.

![](assets/marketo-measure-report-template-tableau-4.png)

![](assets/marketo-measure-report-template-tableau-5.png)

### Columnas eliminadas {#removed-columns}

Para simplificar el modelo de datos y eliminar datos redundantes e innecesarios, hemos reducido el número de columnas importadas en Tableau desde la tabla del Snowflake original. Las columnas eliminadas incluyen claves externas innecesarias, datos dimensionales no normalizados que se aprovechan mejor mediante relaciones con otras tablas del modelo, columnas de auditoría y campos utilizados para [!DNL Marketo Measure] procesamiento. Puede agregar o quitar columnas según sus necesidades comerciales editando la lista de columnas importadas en la sección Select del SQL personalizado.

>[!NOTE]
>
>La mayoría de las tablas del almacén de datos contienen datos dimensionales no normalizados. Hemos trabajado para normalizar y limpiar el modelo en [!DNL Tableau] lo máximo posible para mejorar el rendimiento y la precisión de los datos. Tenga cuidado al incluir campos desnormalizados adicionales en tablas de hechos, esto puede romper el filtrado dimensional entre tablas y también podría resultar en informes inexactos.

### Columnas renombradas {#renamed-columns}

Se ha cambiado el nombre de las tablas y las columnas para que sean más fáciles de usar y para estandarizar las convenciones de nomenclatura. Para ver los cambios en el nombre de la columna, haga referencia a las instrucciones SQL personalizadas que crean las tablas.

### Filas agregadas {#rows-added}

Para agregar capacidades de conversión de moneda a los cálculos del modelo, hemos agregado una tasa de conversión corporativa y una columna de tasa de conversión objetivo a las tablas Oportunidad y Costo. El valor de estas columnas se agrega en el nivel de fila y se evalúa uniéndose a la tabla Tasa de conversión tanto en la fecha como en el identificador de moneda. Dado que Tableau no permite que las tablas de hechos compartan más de una tabla de dimensiones, las tasas de conversión se agregaron directamente a las tablas que la utilizan. Para obtener más información sobre cómo funciona la conversión de moneda en este modelo, consulte la [Conversión de moneda](#currency-conversion) en esta documentación.

![](assets/marketo-measure-report-template-tableau-6.png)

Hay algunos lugares en los que hay dos mesas [!DNL Snowflake] se han combinado con una unión para crear una tabla en la [!DNL Tableau] modelo de datos. En estos casos, se ha añadido una columna &quot;Tipo&quot; para indicar qué [!DNL Snowflake] tabla de la que proviene y designe la entidad que representa la fila. Para obtener más información sobre las tablas que se han combinado, consulte la sección Relación y flujo de datos en esta documentación.

![](assets/marketo-measure-report-template-tableau-7.png)

### Nombres de los segmentos {#segment-names}

Dado que los nombres de segmentos se pueden personalizar, tienen nombres de columna genéricos en el almacén de datos del Snowflake. [!DNL BIZ_SEGMENT_NAMES] es una tabla de asignación que muestra el nombre genérico del segmento con el nombre personalizado al que está asignado, tal como se define en la sección del segmento en la [!DNL Marketo Measure] IU. Si utiliza nombres de segmento personalizados y desea actualizar su [!DNL Tableau] para incorporarlos, utilice esta tabla y cambie manualmente el nombre de las columnas dentro del modelo Tableau. Las columnas de segmento se encuentran en la tabla de puntos de contacto de posible cliente y atribución y solo será necesario cambiar el nombre una vez.

La variable [!UICONTROL CATEGORÍA] enumera el número de categoría y la columna SEGMENT_NAME tiene el nombre de segmento personalizado al que se asigna.

![](assets/marketo-measure-report-template-tableau-8.png)

Los nombres se pueden actualizar de dos formas. La primera opción es actualizar el SQL personalizado. En este ejemplo, se ha cambiado el nombre de las Categorías 1 a 6 en función de la asignación de la tabla Nombres de segmentos.

![](assets/marketo-measure-report-template-tableau-9.png)

La otra opción es cambiar el nombre de las columnas directamente en la [!DNL Tableau] tabla.

![](assets/marketo-measure-report-template-tableau-10.png)

## Modelo de datos {#data-model}

Haga clic en la imagen siguiente para su versión de tamaño completo.

[![](assets/marketo-measure-report-template-tableau-11.png)](/help/bi-report-templates/assets/tableau-data-model.png){target="_blank"}

### Relaciones y flujo de datos {#relationships-and-data-flow}

Los datos de evento, que se utilizan para crear puntos de contacto, se almacenan en la variable [!UICONTROL Sesión], [!UICONTROL Tarea], [!UICONTROL Evento], [!UICONTROL Actividad]y [!UICONTROL Miembro de la campaña] tablas. Estas tablas de eventos se unen a la tabla de Touchpoint mediante sus respectivos ID y, si el evento tuvo como resultado un touchpoint, los detalles se almacenan en la tabla de Touchpoint.

Los puntos de contacto de posibles clientes y los puntos de contacto de atribución se combinan en una tabla de este modelo, con un vínculo a la tabla de puntos de contacto. Se ha añadido la columna &quot;Tipo de punto de contacto&quot; para designar si una fila es un punto de contacto de posible cliente o de atribución. La mayoría de los datos dimensionales de los puntos de contacto de posible cliente y atribución provienen de su vínculo al punto de contacto correspondiente.

Las transiciones de fase de oportunidad y las transiciones de fase de posible cliente se combinan en una tabla de este modelo, con un vínculo a la [!UICONTROL Posible cliente y atribución] Tabla de punto de contacto. Se ha añadido la columna &quot;Tipo de transición&quot; para designar si una fila es una transición de oportunidad o de etapa de posible cliente.

Tanto los datos de Coste como los de Touchpoint comparten las dimensiones Canal y Campaña. Sin embargo, Tableau está limitado en su capacidad de modelar dimensiones compartidas entre tablas de hechos. Dado que estamos limitados a una sola tabla de dimensión compartida, los datos de canal y campaña se han combinado en una tabla. Se combinan utilizando un vínculo cruzado de las dos dimensiones en una tabla de Tableau: Canal y campaña. El id único se crea concatenando los id de canal y de campaña. Este mismo valor de id se agrega a las tablas Touchpoint y Cost para crear una relación con esta tabla de dimensiones combinada.

![](assets/marketo-measure-report-template-tableau-12.png)

En este modelo, las dimensiones Campaña y Canal están vinculadas al punto de contacto, por lo que todos los informes sobre estas dimensiones se realizan a través de este vínculo, lo que significa que los informes dimensionales sobre los datos de evento pueden estar incompletos. Esto se debe a que muchos eventos no tienen vínculos a estas dimensiones hasta que se procesan en Touchpoints.

>[!NOTE]
>
>Algunos eventos, como Sesiones, tienen vínculos directos a las dimensiones Campaña y Canal . Si desea crear informes a nivel de sesión sobre estas dimensiones, se recomienda crear un modelo de datos independiente para este fin.

Los datos de costes se almacenan en diferentes niveles de agregación dentro de la tabla de costes del almacén de datos del Snowflake. Para todos los proveedores de publicidad, los datos de nivel de campaña se pueden resumir hasta el nivel de canal. Por este motivo, este modelo extrae datos de coste basados en el indicador &quot;campaign_is_gregatable_cost&quot;. Los costes informados por separado se pueden enviar solo a nivel de canal y no son necesarios para tener datos de Campaign. Para proporcionar la información de costes más precisa posible, los costes informados por sí mismos se extraen en función del indicador &quot;channel_is_gregatable_cost&quot;. La consulta que importa los datos de coste se escribe con la siguiente lógica: Si ad_provider = &quot;SelfReported&quot; entonces channel_is_gregatable_cost = true, de lo contrario campaign_is_gregatable_cost = true.

Dentro del contexto de este modelo, Lead, [!UICONTROL Contacto], [!UICONTROL Cuenta]y [!UICONTROL Oportunidad] Los datos de se consideran datos dimensionales y se unen directamente a la tabla de puntos de contacto de posible cliente y atribución.

### Conversión de moneda {#currency-conversion}

Las tasas de la tabla Tasa de conversión representan el valor necesario para convertir una cantidad de la moneda corporativa. Las conversiones a cualquier moneda requieren una doble conversión, primero de la moneda original a la moneda corporativa y después de la moneda corporativa a la moneda seleccionada. El primer paso en esta cadena del modelo es agregar dos columnas con estas tasas de conversión a las tablas con importes, oportunidad y coste. Estos pasos se detallan en la sección Filas agregadas de este documento. Como no es necesario que las tasas de conversión sean estáticas y pueden cambiar según intervalos de fechas especificados, todos los cálculos de conversión de moneda deben realizarse en el nivel de fila. La conversión de la moneda original a la moneda corporativa consiste en dividir el valor por la tasa de conversión corporativa y luego multiplicarlo por la tasa de conversión objetivo. La tasa de conversión de destino está determinada por el valor del parámetro de moneda seleccionado.

* Convertir el valor original al valor de moneda corporativa / tasa de conversión corporativa = valor en moneda corporativa
* Convertir el valor de la divisa corporativa a la divisa seleccionada en la divisa corporativa `*` tasa de conversión de la moneda seleccionada = valor en la moneda seleccionada

![](assets/marketo-measure-report-template-tableau-13.png)

Las medidas de conversión de moneda de este modelo sustituyen un valor de 1,0 para la tasa si no se puede identificar ninguna tasa de conversión. Se han creado medidas independientes para mostrar el valor de moneda de la medida y avisar si un cálculo incluye más de un valor de moneda (es decir, si un valor no se ha podido convertir a la moneda seleccionada). Estas medidas, Moneda de coste y Moneda de ingresos, se incluyen como información sobre herramientas en cualquier elemento visual que muestre los datos de Coste o Ingresos.

![](assets/marketo-measure-report-template-tableau-14.png)

## Definiciones de datos {#data-definitions}

Se han añadido definiciones al [!DNL Tableau model] para parámetros, columnas personalizadas y medidas.

![](assets/marketo-measure-report-template-tableau-15.png)

Para ver las definiciones de las columnas que provienen directamente de [!DNL Snowflake], consulte la [documentación del almacén de datos](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target="_blank"}.

## Discrepancias entre las plantillas y Discover {#discrepancies-between-templates-and-discover}

### Ingresos atribuidos {#attributed-revenue}

Los puntos de contacto de posibles clientes y los puntos de contacto de atribución heredan datos dimensionales del punto de contacto original. El modelo de plantilla de informes obtiene todos los datos dimensionales heredados de la relación con Touchpoint, mientras que en el modelo de Discover, los datos dimensionales se desnormalizan a los registros de Touchpoint de posible cliente y atribución. Los ingresos atribuidos totales o los valores de ingresos atribuidos a la canalización deberían alinearse entre los dos informes. Sin embargo, pueden observarse discrepancias cuando los ingresos se desglosan o filtran por datos dimensionales (canal, subcanal o campaña). Si las cantidades de ingresos dimensionales no coinciden entre la plantilla y Discover, es probable que falten registros de puntos de contacto en el conjunto de datos del informe de plantilla. Esto sucede cuando hay un registro de Punto de contacto de posible cliente o atribución, pero no hay ningún registro correspondiente en la tabla de Punto de contacto dentro del conjunto de datos importado en el informe. Dado que estas tablas se filtran por fecha de modificación, es posible que el registro de puntos de contacto de posible cliente/atribución se haya modificado más recientemente que el registro de punto de contacto y, por lo tanto, el punto de contacto de posible cliente/atribución se haya importado en el conjunto de datos mientras que el registro de punto de contacto original no lo fue. Para solucionar este problema, amplíe el intervalo de fechas filtrado para la tabla de Touchpoint o considere la posibilidad de quitar la restricción de fechas al mismo tiempo.

>[!NOTE]
>
>Touchpoint es una tabla grande, por lo que debe tener en cuenta las compensaciones de un conjunto de datos más completo frente a la cantidad de datos que debe importarse.

### Costo {#cost}

Los informes de costes en las plantillas solo están disponibles en los niveles de campaña y canal; sin embargo, Discover ofrece informes con niveles de granularidad más bajos para algunos proveedores de publicidad (es decir, creativos, de palabra clave, de grupos de anuncios, etc.). Para obtener más información sobre cómo se modelan los datos de costes en las plantillas, consulte la [!UICONTROL Modelo de datos] de esta documentación. Si la dimensión filtra en [!UICONTROL Discover] está configurada como canal o campaña, los costos en los niveles de canal, subcanal y campaña deben alinearse entre Discover y las plantillas de informe.

### Retorno de la inversión {#roi}

Dado que el ROI se calcula a partir de Ingresos y Coste atribuidos, las mismas discrepancias que podrían surgir en cualquiera de estos cálculos pueden surgir en el ROI y por las mismas razones, como se indica en esas secciones.

### Puntos de contacto {#touchpoints}

Estas métricas, tal como se muestra en las plantillas de informes, no se ven reflejadas en Discover. Actualmente no hay ninguna comparación directa posible entre ambos.

### Tráfico web {#web-traffic}

El modelo de datos de plantilla de informes normaliza los datos dimensionales de canal, subcanal y campaña a través de la relación entre Sesión y Touchpoint. Es distinto al modelo de datos de Discover , que desnormaliza estas dimensiones en Sesión . Debido a esta distinción, los recuentos generales de visitas y visitantes deben coincidir entre Discover y la plantilla de informes. Sin embargo, una vez mostrada o filtrada por dimensión, no se espera que estos números se alineen. Esto se debe a que los datos dimensionales de la plantilla solo están disponibles para eventos web que hayan provocado un punto de contacto (es decir, eventos no anónimos). Para obtener más información, consulte la [Modelo de datos](#data-model) de esta documentación.

Puede haber pequeñas discrepancias en el recuento total de formularios del sitio entre [!DNL Discover] y la plantilla. Esto se debe a que el modelo de datos de la plantilla de informes obtiene datos dimensionales para el formulario del sitio a través de una relación con Session y, a continuación, Touchpoint; hay algunos casos en los que los datos de formulario del sitio no tienen una sesión correlacionada.

### Posibles clientes y cuentas {#leads-and-accounts}

Los informes dimensionales de las cuentas afectadas pueden diferir ligeramente entre [!DNL Discover] y la plantilla, esto también se debe al modelado dimensional que proviene de la relación entre Touchpoint y el Punto de contacto de posible cliente o el Punto de contacto de atribución. Consulte los detalles descritos en la sección Ingresos atribuidos para obtener más información.

Todos los recuentos de posibles clientes en [!UICONTROL Discover] se les atribuyen recuentos de posibles clientes y en la plantilla de informes la métrica es [!UICONTROL posibles clientes] tocado. Por lo tanto, no hay ninguna comparación directa posible entre los dos informes para esta medida.

### Ruta de participación {#engagement-path}

No hay comparación directa entre las variables [!UICONTROL Ruta de participación] informe en [!DNL Discover] y la plantilla. El informe de [!DNL Discover] está modelado desde el punto de contacto mientras que el informe de la plantilla está modelado desde el punto de contacto de atribución. La plantilla se centra únicamente en las oportunidades y sus puntos de contacto relacionados, en lugar de mostrar todos los datos de puntos de contacto.

### Velocidad del acuerdo {#deal-velocity}

No debe haber discrepancias entre este informe en la plantilla y el mosaico Velocidad de oferta en el panel Velocity de Discover.
