---
description: "[!DNL Marketo Measure] Plantilla de informe - Power BI - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Plantilla de informe: Power BI"
exl-id: c296b8f9-4033-4723-9a71-63a458640d27
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '2583'
ht-degree: 1%

---

# [!DNL Marketo Measure] Plantilla de informe: Power BI {#marketo-measure-report-template-power-bi}

## Introducción {#getting-started}

Puede acceder a la plantilla de informe de Power BI [here](https://github.com/adobe/Marketo-Measure-BI-Templates){target=&quot;_blank&quot;}.

Abra el Adobe [!DNL Marketo Measure] Archivo de Power BI de plantilla de informes.

![](assets/marketo-measure-report-template-power-bi-1.png)

Puede encontrar la información específica de servidor, almacén y esquema en la [!DNL Marketo Measure] La interfaz de usuario de [!DNL Data Warehouse] página de información. Las instrucciones para localizar esta página se detallan [here](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target=&quot;_blank&quot;}.

Los parámetros QueryFilterStartDate y QueryFilterEndDate se utilizan para limitar la cantidad de datos importados. Estos parámetros deben tener el formato SQL tal como se utilizan en las consultas enviadas a [!DNL Snowflake]. Por ejemplo, si desea limitar los datos a los dos últimos años, QueryFilterStartDate se agregaría a la fecha (año, -2,fecha_actual()). Estos parámetros se comparan con los tipos de datos datetime, por lo que se recomienda utilizar dateadd (day,1,current_date()) para que QueryFilterEndDate devuelva todos los datos a la hora actual.

## Conexión de datos {#data-connection}

Los parámetros introducidos al abrir el archivo se utilizan para estructurar consultas nativas que importan tablas desde el almacén de datos. Aún tendrá que configurar una conexión de datos en su [!DNL Snowflake] instancia. Para ello, necesitará los mismos nombres de Servidor y Almacén junto con su nombre de usuario y contraseña. Los detalles sobre dónde encontrar el nombre de usuario y restablecer la contraseña, si es necesario, están documentados [here](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target=&quot;_blank&quot;}.

## Importación de datos {#data-import}

Para mejorar el rendimiento de los informes y aprovechar las capacidades de transformación de Power Query, hemos elegido configurar esta plantilla mediante el método de almacenamiento de importación.

### Parámetros de consulta {#query-parameters}

Para limitar los datos importados en el modelo, cada tabla se configura con una consulta nativa como fuente. Las consultas nativas requieren aprobación para ejecutarse. Deberá hacer clic en ejecutar para cada consulta. Este paso solo es necesario la primera vez que se ejecutan las consultas o si cambian los parámetros.

![](assets/marketo-measure-report-template-power-bi-2.png)

Todas las consultas filtran las filas eliminadas y la variable [!UICONTROL data] las tablas se establecen para filtrar a filas con una fecha modificada entre las fechas de inicio y finalización introducidas como parámetros.

>[!NOTE]
>
>Debido a que los filtros de fecha se aplican a la fecha de modificación de una fila, tenga cuidado al generar informes sobre fechas que se encuentran fuera del intervalo de fechas restringido. Por ejemplo, el intervalo de fechas modificado está limitado a los dos últimos años. Esto puede incluir un evento con una fecha de evento de hace tres años, pero que se ha modificado recientemente. Sin embargo, los informes sobre eventos de hace tres años devolverán resultados incompletos, ya que no todas las filas se habrán modificado dentro del lapso de dos años.

![](assets/marketo-measure-report-template-power-bi-3.png)

Los cuadros siguientes se tratan como cuadros de hechos; se han añadido a estas consultas los límites de fecha en la fecha de modificación.

* Actividad
* Touchpoint.
* Punto de contacto del posible cliente
* Punto de contacto de atribución
* Costo
* Formulario del sitio
* Sesión
* Membresía de la campaña
* Tarea
* Evento
* Transición de fase de posible cliente/contacto
* Transición de fase de oportunidad

Las tablas siguientes se tratan como tablas de dimensión: no se establecen límites de fecha para estas consultas.

* Cuenta
* Campaña
* Contacto
* Tasa de conversión
* Oportunidad
* Cliente potencial
* Etapa
* Canal

## Transformaciones de datos {#data-transformations}

Se han aplicado algunas transformaciones a los datos de Power Query. Para ver las transformaciones específicas de cualquier tabla, abra Power Query, vaya a una tabla y observe los Pasos aplicados en la parte izquierda de la ventana. A continuación se describen algunas de las transformaciones específicas.

![](assets/marketo-measure-report-template-power-bi-4.png)

### Columnas eliminadas {#removed-columns}

Para simplificar el modelo de datos y eliminar datos redundantes e innecesarios, hemos reducido el número de columnas importadas a Power BI desde el modelo original [!DNL Snowflake] tabla. Las columnas eliminadas incluyen claves externas innecesarias, datos dimensionales no normalizados que se aprovechan mejor mediante relaciones con otras tablas del modelo, columnas de auditoría y campos utilizados para [!DNL Marketo Measure] procesamiento. Puede agregar o eliminar columnas según sus necesidades comerciales. Vaya al paso &quot;Eliminadas otras columnas&quot; después del paso &quot;Origen&quot; de cualquier tabla, haga clic en el icono de engranaje y actualice las columnas seleccionadas en la lista proporcionada.

>[!NOTE]
>
>* Tenga cuidado al agregar valores de claves externas adicionales. A menudo, la Power BI se configura para detectar automáticamente las relaciones en el modelo y agregar valores de claves externas puede resultar en vínculos no deseados entre tablas o en deshabilitar las relaciones existentes.
>
>* La mayoría de las tablas de [!DNL Marketo Measure] el almacén de datos contiene datos dimensionales no normalizados. Hemos trabajado para normalizar y limpiar el modelo en la mayor medida posible para mejorar el rendimiento y la precisión de los datos. Tenga cuidado al incluir campos desnormalizados adicionales en tablas de hechos, esto puede romper el filtrado dimensional entre tablas y también podría resultar en informes inexactos.



![](assets/marketo-measure-report-template-power-bi-5.png)

### Columnas renombradas {#renamed-columns}

Se ha cambiado el nombre de las tablas y las columnas para que sean más fáciles de usar y para estandarizar las convenciones de nomenclatura. Para ver los cambios en el nombre de la columna, vaya al paso &quot;Columnas renombradas&quot; después del paso &quot;Otras columnas eliminadas&quot; de cualquier tabla.

![](assets/marketo-measure-report-template-power-bi-6.png)

### Segmentos con nombre cambiado {#renamed-segments}

Dado que los nombres de segmentos se pueden personalizar, tienen nombres de columna genéricos en el almacén de datos del Snowflake. [!DNL BIZ_SEGMENT_NAMES] es una tabla de asignación que muestra el nombre genérico del segmento y su nombre de segmento personalizado asignado, definido en la sección del segmento en la variable [!DNL Marketo Measure] IU. La tabla Nombre del segmento se utiliza para cambiar el nombre de las columnas del segmento en las tablas Punto de contacto de posible cliente y Punto de contacto de atribución. Si no existe ningún segmento personalizado, el nombre del segmento genérico permanece.

![](assets/marketo-measure-report-template-power-bi-7.png)

### Conversión de ID con distinción de mayúsculas y minúsculas {#case-sensitive-id-conversion}

[!DNL Marketo Measure] Los datos de tienen un par de tablas en las que los valores de clave principal (ID) distinguen entre mayúsculas y minúsculas, concretamente Touchpoint y Campaign. El motor de datos que impulsa la capa de modelado de Power BI no distingue entre mayúsculas y minúsculas, lo que resulta en valores de identificación &quot;duplicados&quot;. Para preservar la distinción entre mayúsculas y minúsculas de estos valores clave, hemos implementado pasos de transformación que adjuntan caracteres invisibles a caracteres en minúsculas, preservando la exclusividad del ID cuando se evalúa en la capa del motor de datos. Encontrará más detalles sobre el tema y los pasos detallados sobre el método que hemos empleado [here] (https://blog.crossjoin.co.uk/2019 /10/06/power-bi-and-case-distinct/){target=&quot;_blank&quot;}. Estos valores de ID que distinguen entre mayúsculas y minúsculas se etiquetan como &quot;ID de unión&quot; y se utilizan como claves de unión en la capa de relación. Hemos ocultado los ID de combinación de la capa de informes, manteniendo los valores de ID originales visibles para usarlos en los informes, ya que los caracteres invisibles pueden interferir con las funciones cortar/pegar y el filtrado.

![](assets/marketo-measure-report-template-power-bi-8.png)

![](assets/marketo-measure-report-template-power-bi-9.png)

### Filas agregadas {#rows-added}

Para agregar capacidades de conversión de moneda a los cálculos del modelo, hemos agregado una columna de tasa de conversión corporativa a las tablas Oportunidad y Coste. El valor de esta columna se agrega en el nivel de fila y se evalúa uniéndose a la tabla Tasa de conversión tanto en la fecha como en el identificador de moneda. Para obtener más información sobre cómo funciona la conversión de moneda en este modelo, consulte la [Conversión de moneda](#currency-conversion) en esta documentación.

![](assets/marketo-measure-report-template-power-bi-10.png)

La tabla de tasa de conversión almacenada en [!DNL Snowflake] contiene un intervalo de fechas para cada conversión. Power BI no permite combinar criterios en un cálculo (es decir, entre un intervalo de fechas). Para unirse a la fecha, hemos agregado pasos a la tabla Tasa de conversión para expandir las filas y así hay una fila para cada fecha en el intervalo de fechas de conversión.

![](assets/marketo-measure-report-template-power-bi-11.png)

## Modelo de datos {#data-model}

Haga clic en la imagen siguiente para su versión de tamaño completo.

[![](assets/marketo-measure-report-template-power-bi-12.png)](/help/bi-report-templates/assets/power-bi-data-model.png){target=&quot;_blank&quot;}

### Relaciones y flujo de datos {#relationships-and-data-flow}

Los datos de evento, que se utilizan para crear puntos de contacto, se almacenan en la variable [!UICONTROL Sesión], [!UICONTROL Tarea], [!UICONTROL Evento], [!UICONTROL Actividad]y las tablas de miembros de Campaign. Estas tablas de eventos se unen a la tabla de Touchpoint mediante sus respectivos ID y, si el evento tuvo como resultado un touchpoint, los detalles se almacenan en la tabla de Touchpoint.

Los puntos de contacto de posibles clientes y los puntos de contacto de atribución se almacenan en sus propias tablas, con un vínculo a la tabla de puntos de contacto. La mayoría de los datos dimensionales de los puntos de contacto de posible cliente y atribución provienen de su vínculo al punto de contacto correspondiente.

En este modelo, las dimensiones Campaña y Canal están vinculadas al punto de contacto, por lo que todos los informes sobre estas dimensiones se realizan a través de este vínculo, lo que significa que los informes dimensionales sobre los datos de evento pueden estar incompletos. Esto se debe a que muchos eventos no tienen vínculos a estas dimensiones hasta que se procesan en Touchpoints. Nota: algunos eventos, como Sesiones, tienen vínculos directos a las dimensiones Campaña y Canal . Si desea crear informes a nivel de sesión sobre estas dimensiones, se recomienda crear un modelo de datos independiente para este fin.

Los datos de costes se almacenan en diferentes niveles de agregación dentro del [!DNL Snowflake] tabla de coste del almacén de datos. Para todos los proveedores de publicidad, los datos de nivel de campaña se pueden resumir hasta el nivel de canal. Por este motivo, este modelo extrae datos de coste basados en el indicador &quot;campaign_is_gregatable_cost&quot;. Los costes informados por separado se pueden enviar solo a nivel de canal y no son necesarios para tener datos de Campaign. Para proporcionar la información de costes más precisa posible, los costes informados por sí mismos se extraen en función del indicador &quot;channel_is_gregatable_cost&quot;. La consulta que importa los datos de coste se escribe con la siguiente lógica: Si ad_provider = &quot;SelfReported&quot; entonces channel_is_gregatable_cost = true, de lo contrario campaign_is_gregatable_cost = true.

Los datos de costes y los datos de Touchpoint tienen algunas dimensiones comunes, por lo que ambas tablas de hechos están relacionadas con las tablas de dimensiones Campaña y Canal.

Dentro del contexto de este modelo, [!UICONTROL Posible cliente], [!UICONTROL Contacto], [!UICONTROL Cuenta]y [!UICONTROL Oportunidad] Los datos se consideran datos dimensionales y se unen directamente al [!UICONTROL Posible cliente] Touchpoint y [!UICONTROL Atribución] Tablas Touchpoint.

### Tablas agregadas {#added-tables}

**Fecha**

Como la Power BI solo permite relaciones entre tablas en una columna, se ha añadido una tabla de dimensión Fecha para facilitar la unión necesaria entre las tablas que contienen importes (Oportunidad y Coste) y la tabla Tasa de conversión. Consulte la sección Conversión de moneda para obtener más información sobre cómo se calculan las conversiones de moneda en este modelo.

**Medidas**

Todas las medidas se han añadido a una tabla de medidas específica. No está conectado al modelo, pero sirve como ubicación única para almacenar todas las medidas, para facilitar su uso.

**Modelo de atribución**

Se ha añadido una tabla independiente para almacenar los nombres de los modelos de atribución. Esta tabla se utiliza para crear filtros que permiten al usuario cambiar entre modelos de atribución para cálculos de ingresos atribuidos.

### Conversión de moneda {#currency-conversion}

Las tasas de la tabla Tasa de conversión representan el valor necesario para convertir una cantidad de la moneda corporativa. Las conversiones a cualquier moneda requieren una doble conversión, primero de la moneda original a la moneda corporativa y después de la moneda corporativa a la moneda seleccionada. El primer paso en esta cadena del modelo es agregar una columna con la tasa de conversión a la empresa a las tablas con importes, oportunidad y coste. Estos pasos se detallan en el encabezado Filas agregadas de la sección Transformaciones de datos de este documento. La conversión de la moneda original a la moneda corporativa consiste en dividir el valor por esta columna añadida. El siguiente paso es multiplicar el valor de la moneda corporativa por la tasa de la tabla Tasa de conversión que corresponde a la moneda seleccionada.

* Convertir el valor original al valor de moneda corporativa / tasa de conversión corporativa = valor en moneda corporativa
* Convertir el valor de la divisa corporativa a la divisa seleccionada en la divisa corporativa `*` tasa de conversión de la moneda seleccionada = valor en la moneda seleccionada

Como no es necesario que las tasas de conversión sean estáticas y pueden cambiar según intervalos de fechas especificados, todos los cálculos de conversión de moneda deben realizarse en el nivel de fila. De nuevo, como las tasas de conversión pertenecen a un intervalo de fechas específico, el cálculo de búsqueda debe realizarse dentro del DAX de la medida, de modo que la relación se pueda definir tanto en el código de moneda como en la fecha.

Las medidas de conversión de moneda de este modelo sustituyen un valor de 1,0 para la tasa si no se puede identificar ninguna tasa de conversión. Se han creado medidas independientes para mostrar el valor de moneda de la medida y avisar si un cálculo incluye más de un valor de moneda (es decir, si un valor no se ha podido convertir a la moneda seleccionada).

![](assets/marketo-measure-report-template-power-bi-13.png)

## Definiciones de datos {#data-definitions}

Se han añadido definiciones al modelo de Power BI para tablas, columnas personalizadas y medidas.

![](assets/marketo-measure-report-template-power-bi-14.png)

![](assets/marketo-measure-report-template-power-bi-15.png)

![](assets/marketo-measure-report-template-power-bi-16.png)

Para ver las definiciones de las columnas que provienen directamente de [!DNL Snowflake], consulte la [documentación del almacén de datos](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target=&quot;_blank&quot;}

## Discrepancias entre las plantillas y Discover {#discrepancies-between-templates-and-discover}

### Ingresos atribuidos {#attributed-revenue}

Los puntos de contacto de posibles clientes y los puntos de contacto de atribución heredan datos dimensionales del punto de contacto original. El modelo de plantilla de informes obtiene todos los datos dimensionales heredados de la relación con Touchpoint, mientras que en el modelo de Discover, los datos dimensionales se desnormalizan a los registros de Touchpoint de posible cliente y atribución. Los ingresos atribuidos totales o los valores de ingresos atribuidos a la canalización deberían alinearse entre los dos informes. Sin embargo, pueden observarse discrepancias cuando los ingresos se desglosan o filtran por datos dimensionales (canal, subcanal o campaña). Si las cantidades de ingresos dimensionales no coinciden entre la plantilla y Discover, es probable que falten registros de puntos de contacto en el conjunto de datos del informe de plantilla. Esto sucede cuando hay un registro de Punto de contacto de posible cliente o atribución, pero no hay ningún registro correspondiente en la tabla de Punto de contacto dentro del conjunto de datos importado en el informe. Dado que estas tablas se filtran por fecha de modificación, es posible que el registro de puntos de contacto de posible cliente/atribución se haya modificado más recientemente que el registro de punto de contacto y, por lo tanto, el punto de contacto de posible cliente/atribución se haya importado en el conjunto de datos mientras que el registro de punto de contacto original no lo fue. Para solucionar este problema, amplíe el intervalo de fechas filtrado para la tabla de Touchpoint o considere la posibilidad de quitar la restricción de fechas al mismo tiempo. Nota: Touchpoint es una tabla grande, por lo que debe tener en cuenta las compensaciones de un conjunto de datos más completo frente a la cantidad de datos que debe importarse.

### Costo {#cost}

Los informes de costes en las plantillas solo están disponibles en los niveles de campaña y canal; sin embargo, Discover ofrece informes con niveles de granularidad más bajos para algunos proveedores de publicidad (es decir, creativos, de palabra clave, de grupos de anuncios, etc.). Para obtener más información sobre cómo se modelan los datos de costes en las plantillas, consulte la sección Modelo de datos de esta documentación. Si la dimensión filtra en [!UICONTROL Discover] está configurada como canal o campaña, los costos en los niveles de canal, subcanal y campaña deben alinearse entre Discover y las plantillas de informe.

### Retorno de la inversión {#roi}

Dado que el ROI se calcula a partir de Ingresos y Coste atribuidos, las mismas discrepancias que podrían surgir en cualquiera de estos cálculos pueden surgir en el ROI y por las mismas razones, como se indica en esas secciones.

### Puntos de contacto {#touchpoints}

Estas métricas, tal como se muestra en las plantillas de informes, no se ven reflejadas en Discover. Actualmente no hay ninguna comparación directa posible entre ambos.

### Tráfico web {#web-traffic}

El modelo de datos de plantilla de informes normaliza los datos dimensionales de canal, subcanal y campaña a través de la relación entre Sesión y Touchpoint. Es distinto al modelo de datos de Discover , que desnormaliza estas dimensiones en Sesión . Debido a esta distinción, los recuentos generales de visitas y visitantes deben coincidir entre Discover y la plantilla de informes. Sin embargo, una vez mostrada o filtrada por dimensión, no se espera que estos números se alineen. Esto se debe a que los datos dimensionales de la plantilla solo están disponibles para eventos web que hayan provocado un punto de contacto (es decir, eventos no anónimos). Para obtener más información, consulte la [Modelo de datos](#data-model) de esta documentación.

Puede haber pequeñas discrepancias en el recuento total de formularios del sitio entre [!DNL Discover] y la plantilla. Esto se debe a que el modelo de datos de la plantilla de informes obtiene datos dimensionales para el formulario del sitio a través de una relación con Session y, a continuación, Touchpoint; hay algunos casos en los que los datos de formulario del sitio no tienen una sesión correlacionada.

### Posibles clientes y cuentas {#leads-and-accounts}

Los informes dimensionales de las cuentas que se tocaron pueden diferir ligeramente entre Discover y la plantilla. Esto se debe, de nuevo, al modelado dimensional que proviene de la relación entre Touchpoint y el Touchpoint de posible cliente o el Touchpoint de atribución. Consulte los detalles descritos en la sección Ingresos atribuidos para obtener más información.

Todos los recuentos de posibles clientes en Discover se atribuyen a recuentos de posibles clientes y en la plantilla de informes se tocan los posibles clientes. Por lo tanto, no hay ninguna comparación directa posible entre los dos informes para esta medida.

### Ruta de participación {#engagement-path}

No hay comparación directa entre las variables [!UICONTROL Ruta de participación] en Discover y la plantilla. El informe de [!DNL Discover] está modelado desde el punto de contacto mientras que el informe de la plantilla está modelado desde el punto de contacto de atribución. La plantilla se centra únicamente en las oportunidades y sus puntos de contacto relacionados, en lugar de mostrar todos los datos de puntos de contacto.

### Velocidad del acuerdo {#deal-velocity}

No debe haber discrepancias entre este informe en la plantilla y el mosaico Velocidad de oferta en el panel Velocity de Discover.
