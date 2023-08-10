---
description: "[!DNL Marketo Measure] Plantilla de informe - Power BI - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Plantilla de informe - Power BI"
exl-id: c296b8f9-4033-4723-9a71-63a458640d27
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '2571'
ht-degree: 1%

---

# Plantilla de informe de [!DNL Marketo Measure]: Power BI {#marketo-measure-report-template-power-bi}

## Introducción {#getting-started}

Puede acceder a la plantilla del informe de Power BI [aquí](https://github.com/adobe/Marketo-Measure-BI-Templates){target="_blank"}.

Abra el Adobe [!DNL Marketo Measure] Archivo de Power BI de plantilla de informes.

![](assets/marketo-measure-report-template-power-bi-1.png)

Puede encontrar la información específica de Servidor, Almacén y Esquema en la [!DNL Marketo Measure] Interfaz de usuario en [!DNL Data Warehouse] página de información. Se detallan las instrucciones para localizar esta página [aquí](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}.

Los parámetros QueryFilterStartDate y QueryFilterEndDate se utilizan para limitar la cantidad de datos importados. Estos parámetros deben tener el formato SQL como se utilizan en las consultas enviadas a [!DNL Snowflake]. Por ejemplo, si desea limitar los datos a los dos últimos años, QueryFilterStartDate sería dateadd (año,-2,current_date()). Estos parámetros se comparan con los tipos de datos datetime, por lo que se recomienda utilizar dateadd (day,1,current_date()) para que QueryFilterEndDate devuelva todos los datos a la hora actual.

## Conexión de datos {#data-connection}

Los parámetros introducidos al abrir el archivo se utilizan para estructurar consultas nativas que importan tablas del almacén de datos. Aún tendrá que configurar una conexión de datos con su [!DNL Snowflake] ejemplo. Para ello, necesitará los mismos nombres de servidor y almacén junto con su nombre de usuario y contraseña. Los detalles sobre dónde encontrar su nombre de usuario y restablecer su contraseña, si es necesario, están documentados [aquí](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}.

## Importación de datos {#data-import}

Para mejorar el rendimiento del informe y aprovechar las capacidades de transformación de Power Query, hemos elegido configurar esta plantilla mediante el método de almacenamiento de importación.

### Parámetros de consulta {#query-parameters}

Para limitar los datos importados en el modelo, cada tabla se configura con una consulta nativa como origen. Las consultas nativas requieren aprobación para ejecutarse, pero debe hacer clic en ejecutar para cada consulta. Este paso solo es necesario la primera vez que se ejecutan las consultas o si cambian los parámetros.

![](assets/marketo-measure-report-template-power-bi-2.png)

Todas las consultas filtran las filas eliminadas y la variable [!UICONTROL hechos] Las tablas se definen para filtrar a filas con una fecha de modificación entre las fechas de inicio y finalización introducidas como parámetros.

>[!NOTE]
>
>Debido a que los filtros de fecha se aplican a la fecha de modificación de una fila, tenga cuidado al crear informes sobre fechas que se encuentran fuera del intervalo de fechas restringido. Por ejemplo, el intervalo de fechas modificado está limitado a los últimos dos años. Esto puede incluir un evento con una fecha de evento de hace tres años, pero que se ha modificado recientemente. Sin embargo, los informes sobre los eventos de hace tres años devolverán resultados incompletos, ya que no todas las filas se habrán modificado en el lapso de tiempo de dos años.

![](assets/marketo-measure-report-template-power-bi-3.png)

Las siguientes tablas se tratan como tablas de hechos; los límites de fecha en la fecha de modificación se han agregado a estas consultas.

* Actividad
* Touchpoint.
* Punto de contacto principal
* Attribution Touchpoint
* Costo
* Formulario del sitio
* Sesión
* Membresía de la campaña
* Tarea
* Evento
* Transición de fase de cliente potencial/contacto
* Transición de fase de oportunidad

Las siguientes tablas se tratan como tablas de dimensiones; no se establecen límites de fecha para estas consultas.

* Cuenta
* Campaña
* Contacto
* Tasa de conversión
* Oportunidad
* Cliente potencial
* Fase
* Canal

## Transformaciones de datos {#data-transformations}

Se han aplicado algunas transformaciones a los datos de Power Query. Para ver las transformaciones específicas de cualquier tabla, abra Power Query, vaya a una tabla y observe los Pasos aplicados en la parte izquierda de la ventana. A continuación se describen algunas de las transformaciones específicas.

![](assets/marketo-measure-report-template-power-bi-4.png)

### Columnas eliminadas {#removed-columns}

Para simplificar el modelo de datos y eliminar datos redundantes e innecesarios, hemos reducido el número de columnas importadas en Power BI desde el original [!DNL Snowflake] tabla. Las columnas eliminadas incluyen claves externas innecesarias, datos dimensionales desnormalizados que se aprovechan mejor mediante relaciones con otras tablas del modelo, columnas de auditoría y campos utilizados para tareas internas [!DNL Marketo Measure] procesando. Puede agregar o quitar columnas según sea necesario para sus necesidades comerciales. Vaya al paso &quot;Otras columnas eliminadas&quot; después del paso &quot;Origen&quot; en cualquier tabla, haga clic en el icono de engranaje y actualice las columnas seleccionadas en la lista proporcionada.

>[!NOTE]
>
>* Tenga cuidado al agregar valores de clave externa adicionales. A menudo, Power BI se configura para detectar automáticamente las relaciones en el modelo y añadir valores de clave externa puede provocar vínculos no deseados entre tablas o deshabilitar las relaciones existentes.
>
>* La mayoría de las tablas de la [!DNL Marketo Measure] data warehouse contiene datos dimensionales desnormalizados. Power BI Hemos trabajado para normalizar y limpiar el modelo en la medida de lo posible para mejorar el rendimiento y la precisión de los datos. Tenga cuidado al incluir campos desnormalizados adicionales en tablas de hechos, ya que esto podría romper el filtrado dimensional en todas las tablas y también podría generar informes inexactos.


![](assets/marketo-measure-report-template-power-bi-5.png)

### Columnas con nombre cambiado {#renamed-columns}

Se ha cambiado el nombre de las tablas y columnas para facilitar su uso y estandarizar las convenciones de nomenclatura. Para ver los cambios de nombre de columna, vaya al paso &quot;Columnas renombradas&quot; después del paso &quot;Otras columnas eliminadas&quot; en cualquier tabla.

![](assets/marketo-measure-report-template-power-bi-6.png)

### Segmentos renombrados {#renamed-segments}

Dado que los nombres de segmentos se pueden personalizar, tienen nombres de columna genéricos en el almacén de datos del Snowflake. [!DNL BIZ_SEGMENT_NAMES] es una tabla de asignación que enumera el nombre del segmento genérico y su nombre de segmento personalizado asignado, definido en la sección de segmentos en la [!DNL Marketo Measure] IU. La tabla Nombre del segmento se utiliza para cambiar el nombre de las columnas del segmento en las tablas Punto de contacto de posible cliente y Punto de contacto de atribución. Si no existe ningún segmento personalizado, el nombre del segmento genérico permanece.

![](assets/marketo-measure-report-template-power-bi-7.png)

### Conversión de ID con distinción de mayúsculas y minúsculas {#case-sensitive-id-conversion}

[!DNL Marketo Measure] Los datos de tienen un par de tablas en las que los valores de clave principal (ID) distinguen entre mayúsculas y minúsculas, concretamente Touchpoint y Campaign. El motor de datos que impulsa la capa de modelado de Power BI no distingue entre mayúsculas y minúsculas, lo que da como resultado valores de ID &quot;duplicados&quot;. Para preservar la distinción entre mayúsculas y minúsculas en estos valores clave, hemos implementado pasos de transformación que adjuntan caracteres invisibles a caracteres en minúsculas, preservando la exclusividad del ID cuando se evalúa en la capa del motor de datos. Encontrará más detalles sobre el problema y los pasos detallados del método que hemos empleado [aquí] (https://blog.crossjoin.co.uk/2019 /10/06/power-bi-and-case-sense/){target="_blank"}. Estos valores de ID que distinguen entre mayúsculas y minúsculas están etiquetados como &quot;ID de unión&quot; y se utilizan como claves de unión en la capa de relación. Hemos ocultado los ID de unión de la capa de creación de informes, manteniendo los valores de ID originales visibles para su uso en la creación de informes, ya que los caracteres invisibles pueden interferir con las funciones de cortar/pegar y el filtrado.

![](assets/marketo-measure-report-template-power-bi-8.png)

![](assets/marketo-measure-report-template-power-bi-9.png)

### Filas añadidas {#rows-added}

Para agregar capacidades de conversión de moneda a los cálculos del modelo, se ha agregado una columna de tasa de conversión corporativa a las tablas Oportunidad y Costo. El valor de esta columna se agrega al nivel de fila y se evalúa uniendo a la tabla Tasa de conversión tanto en la fecha como en el identificador de moneda. Para obtener más información sobre cómo funciona la conversión de moneda en este modelo, consulte la [Conversión de moneda](#currency-conversion) de esta documentación.

![](assets/marketo-measure-report-template-power-bi-10.png)

La tabla Tasa de conversión almacenada en [!DNL Snowflake] contiene un intervalo de fechas para cada conversión. Power BI no permite unir criterios en un cálculo (es decir, entre un intervalo de fechas). Para unir en fecha, agregamos pasos a la tabla Tasa de conversión para expandir las filas de modo que haya una fila para cada fecha en el intervalo de fechas de conversión.

![](assets/marketo-measure-report-template-power-bi-11.png)

## Modelo de datos {#data-model}

Haga clic en la imagen siguiente para ver su versión a tamaño completo.

[![](assets/marketo-measure-report-template-power-bi-12.png)](/help/bi-report-templates/assets/power-bi-data-model.png){target="_blank"}

### Relaciones y flujo de datos {#relationships-and-data-flow}

Los datos de evento, utilizados para crear puntos de contacto, se almacenan en [!UICONTROL Session], [!UICONTROL Tarea], [!UICONTROL Evento], [!UICONTROL Actividad], y tablas de miembros de campaña. Estas tablas de eventos se unen a la tabla de puntos de contacto a través de sus respectivos ID. Si el evento resultó en un punto de contacto, los detalles se almacenan en la tabla de puntos de contacto.

Los puntos de contacto principales y los puntos de contacto de atribución se almacenan en sus propias tablas, con un vínculo a la tabla de puntos de contacto. La mayoría de los datos dimensionales de los puntos de contacto de cliente potencial y atribución proceden de su vínculo al punto de contacto correspondiente.

En este modelo, las dimensiones Campaña y Canal están vinculadas al punto de contacto, por lo que todos los informes sobre estas dimensiones se realizan a través de este vínculo, lo que significa que los informes dimensionales sobre los datos de evento pueden estar incompletos. Esto se debe a que muchos eventos no tienen vínculos a estas dimensiones hasta que se procesan en puntos de contacto. Nota: Algunos eventos, como las Sesiones, tienen vínculos directos a las dimensiones Campaña y Canal. Si se desea realizar informes sobre estas dimensiones en el nivel de sesión, se recomienda crear un modelo de datos independiente para este fin.

Los datos de costes se almacenan en diferentes niveles de agregación dentro de la variable [!DNL Snowflake] Tabla de costes de Data Warehouse. Para todos los proveedores de publicidad, los datos de nivel de campaña se pueden resumir en el nivel de canal. Por este motivo, este modelo extrae los datos de coste en función del indicador &quot;campaign_is_aggregatable_cost&quot;. Los costes autoinformados se pueden enviar solo a nivel de canal y no es necesario que tengan datos de Campaign. Para ofrecer la creación de informes de costes más precisa posible, los costes autoinformados se extraen en función del indicador &quot;channel_is_aggregatable_cost&quot;. La consulta que importa los datos de coste se escribe con la siguiente lógica: Si ad_provider = &quot;SelfReported&quot;, channel_is_aggregatable_cost = true; de lo contrario, campaign_is_aggregatable_cost = true.

Los datos de coste y los datos de punto de contacto tienen algunas dimensiones comunes, por lo que ambas tablas de hechos tienen relaciones con las tablas de dimensiones de campaña y canal.

En el contexto de este modelo, [!UICONTROL Posible cliente], [!UICONTROL Contacto], [!UICONTROL Cuenta], y [!UICONTROL Oportunidad] Los datos de se consideran datos dimensionales y se unen directamente al [!UICONTROL Posible cliente] Touchpoint y [!UICONTROL Atribución] Tablas de Touchpoint.

### Tablas agregadas {#added-tables}

**Fecha**

Dado que la Power BI sólo permite las relaciones entre las tablas de una columna, se ha agregado una tabla de dimensión Fecha para facilitar la unión necesaria entre las tablas que contienen importes (oportunidad y costo) y la tabla Tasa de conversión. Consulte la sección Conversión de moneda para obtener más información sobre cómo se calculan las conversiones de moneda en este modelo.

**Medidas**

Todas las medidas se han añadido a una tabla Medidas específica. No está conectado al modelo, pero sirve como una sola ubicación para almacenar todas las medidas, para facilitar su uso.

**Modelo de atribución**

Se ha agregado una tabla independiente para almacenar los nombres de los modelos de atribución. Esta tabla se utiliza para crear filtros que permiten al usuario cambiar entre modelos de atribución para cálculos de ingresos atribuidos.

### Conversión de moneda {#currency-conversion}

Las tasas de la tabla Tasa de conversión representan el valor necesario para convertir una cantidad de la moneda corporativa. Las conversiones a cualquier divisa requieren una conversión doble, primero de la divisa original a la divisa corporativa y, a continuación, de la divisa corporativa a la divisa seleccionada. El primer paso de esta cadena en el modelo es añadir una columna con la tasa de conversión a corporativa a las tablas con importes, oportunidad y coste. Estos pasos se detallan en la cabecera Filas añadidas de la sección Transformaciones de datos de este documento. La conversión de la moneda original a la moneda corporativa consiste en dividir el valor por esta columna agregada. El siguiente paso es multiplicar el valor de la moneda corporativa por la tasa de la tabla Tasa de conversión que corresponde a la moneda seleccionada.

* Convertir el valor original al valor en moneda corporativa / tasa de conversión corporativa = valor en moneda corporativa
* Convertir el valor de moneda corporativa al valor de moneda seleccionado en moneda corporativa `*` tasa de conversión de la moneda seleccionada = valor en la moneda seleccionada

Como no es necesario que las tasas de conversión sean estáticas y pueden cambiar según intervalos de fechas especificados, todos los cálculos de conversión de moneda deben realizarse en el nivel de fila. De nuevo, como las tasas de conversión pertenecen a un intervalo de fechas específico, el cálculo de búsqueda debe realizarse dentro del DAX de la medida, por lo que la relación puede definirse tanto en el código de moneda como en la fecha.

Las medidas de conversión de moneda de este modelo sustituyen la tasa por un valor de 1,0 si no se puede identificar ninguna tasa de conversión. Se han creado medidas independientes para mostrar el valor de moneda de la medida y avisar si un cálculo incluye más de un valor de moneda (es decir, no se pudo convertir un valor a la moneda seleccionada).

![](assets/marketo-measure-report-template-power-bi-13.png)

## Definiciones de datos {#data-definitions}

Se han agregado definiciones al modelo de Power BI para tablas, columnas personalizadas y medidas.

![](assets/marketo-measure-report-template-power-bi-14.png)

![](assets/marketo-measure-report-template-power-bi-15.png)

![](assets/marketo-measure-report-template-power-bi-16.png)

Para ver las definiciones de columnas procedentes directamente de [!DNL Snowflake], consulte la [documentación de data warehouse](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target="_blank"}

## Discrepancias entre plantillas y Discover {#discrepancies-between-templates-and-discover}

### Ingresos atribuidos {#attributed-revenue}

Los puntos de contacto principales y los puntos de contacto de atribución heredan los datos dimensionales del punto de contacto original. El modelo de plantilla de informes obtiene todos los datos dimensionales heredados de la relación con Touchpoint, mientras que en el modelo Discover, los datos dimensionales se desnormalizan en los registros de punto de contacto de cliente potencial y atribución. Los valores generales de ingresos atribuidos o de ingresos atribuidos a la canalización deben alinearse entre los dos informes. Sin embargo, pueden observarse discrepancias cuando los ingresos se desglosan o filtran por datos dimensionales (canal, subcanal o campaña). Si las cantidades de ingresos dimensionales no coinciden entre la plantilla y Discover, es probable que falten registros de punto de contacto en el conjunto de datos del informe de plantilla. Esto sucede cuando hay un registro de punto de contacto de posible cliente o de atribución, pero no hay ningún registro correspondiente en la tabla de puntos de contacto dentro del conjunto de datos importado al informe. Dado que estas tablas se filtran por fecha de modificación, es posible que el registro de punto de contacto de cliente potencial/atribución se haya modificado más recientemente que el registro de punto de contacto y, por lo tanto, el punto de contacto de cliente potencial/atribución se haya importado al conjunto de datos mientras que el registro de punto de contacto original no lo estaba. Para solucionar este problema, amplíe el intervalo de fechas filtrado para la tabla de puntos de contacto o considere la posibilidad de eliminar la restricción de fecha en su totalidad. Nota: Touchpoint es una tabla grande, así que considere las compensaciones de un conjunto de datos más completo frente a la cantidad de datos que deben importarse.

### Costo {#cost}

Los informes de costes en las plantillas solo están disponibles a nivel de campaña y canal. Sin embargo, Discover ofrece informes con niveles de granularidad más bajos para algunos proveedores de publicidad (es decir, creativo, de palabras clave, de grupos de publicidad, etc.). Para obtener más información sobre cómo se modelan los datos de coste en las plantillas, consulte la sección Modelo de datos de esta documentación. Si el filtro de dimensión en [!UICONTROL Discover] se establece en canal o campaña, los costes en los niveles de canal, subcanal y campaña deben alinearse entre Discover y las plantillas de informe.

### Retorno de la inversión {#roi}

Dado que el ROI se calcula a partir de los ingresos atribuidos y el coste, las mismas discrepancias que pueden surgir en cualquiera de estos cálculos pueden surgir en el ROI y por los mismos motivos, como se indica en esas secciones.

### Puntos de contacto {#touchpoints}

Estas métricas, como se muestra en las plantillas de informes, no se reflejan en Discover. Actualmente no hay ninguna comparación directa posible entre ambos.

### Tráfico web {#web-traffic}

El modelo de datos de plantilla de creación de informes normaliza los datos dimensionales de canal, subcanal y campaña a través de la relación entre Session y Touchpoint. Esto es diferente al modelo de datos Discover, que desnormaliza estas dimensiones en Sesión. Debido a esta distinción, los recuentos generales de visitas y visitantes deben coincidir entre Discover y la plantilla de informes. Sin embargo, una vez mostrados o filtrados por dimensión, no se espera que estos números se alineen. Esto se debe a que los datos dimensionales de la plantilla solo están disponibles para eventos web que dieron como resultado un punto de contacto (es decir, eventos no anónimos). Para obtener más información, consulte la [Modelo de datos](#data-model) de esta documentación.

Puede haber pequeñas discrepancias en los recuentos totales de formularios del sitio entre [!DNL Discover] y la plantilla. Esto se debe a que el modelo de datos de la plantilla de informes obtiene datos dimensionales para el formulario del sitio mediante una relación con la sesión y, a continuación, con el punto de contacto; hay algunas instancias en las que los datos del formulario del sitio no tienen una sesión correlacionada.

### Posibles clientes y cuentas {#leads-and-accounts}

Los informes dimensionales para las cuentas tocadas pueden diferir ligeramente entre Discover y la plantilla, esto se debe de nuevo al modelado dimensional proveniente de la relación entre Touchpoint y Lead Touchpoint o Attribution Touchpoint. Consulte los detalles descritos en la sección Ingresos atribuidos para obtener más información.

Todos los recuentos de posibles clientes en Discover se atribuyen a los recuentos de posibles clientes y, en la plantilla de informes, la métrica es posibles clientes tocados. Por lo tanto, no existe una comparación directa posible entre los dos informes para esta medida.

### Ruta de participación {#engagement-path}

No hay comparación directa entre las variables [!UICONTROL Ruta de participación] informe en Discover y la plantilla. El informe en [!DNL Discover] se modela a partir del punto de contacto, mientras que el informe de la plantilla se modela a partir del punto de contacto de atribución. La plantilla se centra únicamente en las oportunidades y sus puntos de contacto relacionados, en lugar de mostrar todos los datos de puntos de contacto.

### Velocidad del acuerdo {#deal-velocity}

No debe haber discrepancias entre este informe en la plantilla y el mosaico Velocidad de la oferta en el panel Velocidad de la oferta en Discover.
