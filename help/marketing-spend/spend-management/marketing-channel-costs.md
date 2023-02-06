---
unique-page-id: 18874602
description: Costes de canal de marketing - [!DNL Marketo Measure] - Documentación del producto
title: Costes de canal de marketing
exl-id: 36ccaff3-db55-47bd-a24e-4aa1894f13e0
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 1%

---

# Costes de canal de marketing {#marketing-channel-costs}

Uno de los beneficios más fundamentales de utilizar [!DNL Marketo Measure] es la capacidad de conectar los esfuerzos de marketing directamente con el impacto en los ingresos, con la granularidad deseada. Es posible ver el retorno de la inversión en el nivel de punto de contacto. Para aprovechar este beneficio, los costes de canal simplemente deben cargarse en la variable [!DNL Marketo Measure] aplicación. Los informes de ROI se crean automáticamente y están disponibles en la **Tablero de ROI de marketing** en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

[Haga clic aquí para ir directamente a las instrucciones.](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs)

La variable [!DNL Marketo Measure] La función Gasto en marketing permite a los clientes cargar su gasto en todos los canales, subcanales y campañas. Cuantos más datos añadan los clientes, más informes de ROI podemos mostrar en el Tablero de atribución de ingresos.

Los costes notificados e importados desde conexiones de publicidad directa se recuperan automáticamente en el nivel más granular y no es necesario cargarlos. Esto incluye nuestras integraciones actuales con Google AdWords, Bing Ads, Doubleclick y Facebook.

[Haga clic aquí para ir directamente a las preguntas frecuentes.](/help/marketing-spend/spend-management/marketing-channel-costs.md#faq)

## Definiciones {#definitions}

**Gastos por campaña**

En el nivel más granular, los clientes pueden especificar el gasto por campañas individuales, agrupadas dentro de su canal respectivo. Para campañas CRM, [!DNL Marketo Measure] ha incluido el ID de campaña en una columna independiente que le ayudará a asignar el gasto en campañas sin conexión de su CRM a esta tabla. Añadir gasto a este nivel permitirá a los clientes ver el ROI de la campaña y optimizar el rendimiento por Campaign.

El total de todas las campañas no necesita sumar ningún valor introducido en el subcanal o canal, pero no puede ser superior a ningún valor introducido en el subcanal o canal. Si la suma es menor que el valor introducido en el subcanal o canal, [!DNL Marketo Measure] agregará automáticamente una fila para &quot;Otro&quot; para cubrir la diferencia y rellenar los huecos.

**Gastos por subcanal**

En un nivel superior, los clientes pueden introducir los gastos por subcanal, agrupados debajo de su canal. Añadir gasto a este nivel permitirá a los clientes ver el ROI de los subcanales y optimizar el rendimiento por subcanal.

El total de todos los subcanales no necesita sumar ningún valor introducido en el canal, pero no puede ser mayor que ningún valor introducido en el canal. Si la suma es menor que el valor introducido en el canal, [!DNL Marketo Measure] agregará automáticamente una fila para &quot;Otro&quot; para cubrir la diferencia y rellenar los huecos.

**Gastos por canal**

En el nivel más alto, los clientes pueden introducir los gastos por canal. Añadir gasto a este nivel permitirá a los clientes ver el ROI del canal y optimizar el rendimiento por canal.

**Selector de fechas**

El intervalo de fechas predeterminado comenzará a partir de la fecha de inicio con [!DNL Marketo Measure] hasta el mes actual. Para garantizar que los costes sigan siendo correctos, no puede introducir costes para meses futuros, pero puede introducir costes durante meses antes de la asociación con [!DNL Marketo Measure].

**Filtro**

Para reducir los resultados en la tabla Gastos de marketing, seleccione un Canal en la parte superior para filtrar otros canales. Esto resulta útil cuando tiene un equipo centrado en un canal único.

**Buscar**

Utilice el cuadro Buscar para buscar texto coincidente de Canales, Subcanales o Campañas.

**Descargar los costos actuales**

El CSV descargado extraerá los resultados de la pantalla actual, lo que significa que cualquier fecha, filtro o búsqueda que se haya aplicado se descargará tal cual.

**Cargar CSV**

Independientemente de qué vista esté en el explorador, si es una vista filtrada o la vista predeterminada con todas las fechas y canales, puede cargar cualquier CSV.

El error más común al que nos enfrentamos es el formato de las columnas de fecha, que ocurre si se cambia el formato de fecha y podría suceder intencionadamente si se cambia entre Excel y/o hojas de Google. Tenga en cuenta que la fecha debe ser MM-AA, así que el 12 de septiembre y no el 12 de septiembre, o el 12 de mayo y no el 05-12.

## Antes de empezar {#before-you-begin}

[!DNL Marketo Measure] viene con 13 canales predeterminados que se pueden usar o ampliar. Además, se pueden crear hasta 40 canales en línea y sin conexión para adaptarse a su estructura de marketing única. Sobre esta base, se pueden crear un total de 200 subcanales para admitir también estos canales en línea y sin conexión.

[!DNL Marketo Measure] descargará automáticamente los costes de canal de marketing de las plataformas con las que tenga una integración de API, como Bing Ads y Google AdWords. Costes para plataformas que no están integradas con [!DNL Marketo Measure] deberá cargarse manualmente. Los canales de marketing deben configurarse antes de cargar los datos de coste.

## Carga de costes de marketing {#uploading-marketing-costs}

Una vez configurados o actualizados los canales y las reglas de marketing, se pueden cargar los costes asociados. Para ello, siga los pasos a continuación:

**Paso 1: Vaya a la página Gastos de marketing en la página [!DNL Marketo Measure] Aplicación.**

Vaya a la **[!UICONTROL Mi cuenta]** , haga clic en **[!UICONTROL Configuración]** y, a continuación, vaya a la **[!UICONTROL Gasto en marketing]** en la barra lateral izquierda debajo de la **[!UICONTROL Informes]** para obtener más información.

![](assets/1.png)

**Paso 2: Descargar el CSV de Costes actuales**

Vaya a la derecha de la pantalla y haga clic en **[!UICONTROL Descargar los costes actuales].** Esta opción le permite descargar una hoja de cálculo en formato CSV.

![](assets/2.png)

**Paso 3: Abra el archivo CSV y realice cambios**

Puede importar el archivo y abrirlo utilizando Google Sheets, Apple Numbers, Microsoft Excel o su software de elección. [!DNL Marketo Measure] recomienda utilizar hojas de Google.

Después de importar la hoja, realice los cambios que desee, como agregar costos a canales y subcanales o actualizar la información existente.

Compruebe las reglas lógicas de la hoja. Cada fila debe contener un canal y uno de sus subcanales separados por un (.) punto al final. Es importante utilizar este formato de forma coherente.

Por ejemplo, para indicar Facebook como subcanal y social como canal, la regla debe escribirse de la siguiente manera: &quot;Social.Facebook.&quot; Del mismo modo, para rastrear un evento sin conexión, la sintaxis del canal debe ser: &quot;Events.Big Conference&quot;. Se muestran ejemplos en la siguiente imagen:

![](assets/3.png)

_Notas adicionales_:

No modifique las fechas en la hoja de cálculo porque esto puede causar problemas cuando se carga el documento.

No deje ningún campo en blanco. Incluso si no hay un valor de dólar que agregar, introduzca 0 $ como la cantidad de dólar.

No es necesario introducir ni actualizar los costes de Bing Ads y Google AdWords porque [!DNL Marketo Measure] extrae automáticamente estos datos de su conexión API con estas plataformas.

**Paso 4: Guardar archivo en formato CSV**

Si está trabajando en hojas de Google, asegúrese de descargar el archivo primero. No excluir ni eliminar datos mensuales, ya que esto provocará dificultades al intentar cargar el archivo CSV en [!DNL Marketo Measure] más tarde.

**Paso 5: Cargar el archivo CSV**

Vaya a la **[!UICONTROL Costo]** de la sección [!DNL Marketo Measure] aplicación y haga clic en **[!UICONTROL Upload.CSV]**. El sistema se actualizará y reflejará la nueva información.

## Preguntas frecuentes {#faq}

**¿Por qué aparecen números en el CSV?**

Si no se introduce ningún valor en un nivel superior como Canal o Subcanal, [!DNL Marketo Measure] sumará automáticamente los niveles secundarios, que se presentarán una vez cargado el archivo. Además, si la suma de los elementos secundarios es menor que un valor introducido para el elemento principal, [!DNL Marketo Measure] agregará una fila &quot;Otro&quot; para mostrar la diferencia en el total.

**¿Cómo se determinan las Campañas en la lista que estoy viendo?**

En este momento, nuestros resultados enumeran las Campañas que hemos visto que reciben un Touchpoint. Si hubo actividad de una campaña, se mostrará esa campaña en función de la fecha de punto de contacto en la que se produjo.

**Hay demasiadas filas y columnas para pasar por alto. ¿Puedo consolidar la vista?**

Con la capacidad de cambiar el intervalo de fechas, filtrar el canal o buscar valores, puede consolidar los resultados de la tabla para que se ajusten mejor a sus necesidades.

**¿Por qué no puedo cargar un archivo?**

Tenemos diferentes conjuntos de permisos dentro de la variable [!DNL Marketo Measure] Aplicación. Para cargar un archivo, debe ser un &quot;AccountAdmin&quot;. Para evitarlo, solicite acceso a su AccountAdmin o pida a su AccountAdmin que cargue el archivo en su nombre. Puede encontrar una lista de usuarios y sus funciones en **[!UICONTROL Mi cuenta]** > **[!UICONTROL Configuración]** > **[!UICONTROL Ver/Agregar usuarios de cuenta]**.
