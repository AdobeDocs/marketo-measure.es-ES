---
description: Guía de segmentación personalizada para usuarios de Marketo Measure
title: Segmentación personalizada
exl-id: c20a2add-250e-45ff-97a6-1b1c03351b6a
feature: Segmentation
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 0%

---

# Segmentación personalizada {#custom-segmentation}

Los segmentos proporcionan la capacidad de filtrar datos en el panel de ROI de [!DNL Marketo Measure] para explorar en profundidad un conjunto de datos específico. Por ejemplo, un segmento podría definirse por territorio geográfico o por sistema de clasificación.

**¿Por qué la segmentación personalizada?**

La segmentación personalizada permite filtrar los puntos de contacto por categorías (nombre del filtro) y reglas (valores del filtro). Los clientes de nivel 1 obtienen un segmento, mientras que los de nivel 2 y superiores obtienen diez. Según el objeto al que apunte el guión de ROI (cliente potencial o contacto), puede crear segmentos basados en los campos que se encuentran en el objeto de cliente potencial/contacto. Además, podrá crear segmentos basados en cualquier campo que se encuentre en el objeto de oportunidad.

**¿Cuándo es útil la característica Segmentación personalizada?**

La segmentación personalizada se puede utilizar para ver los datos de un tipo de registro concreto. Una vez asignada la lógica del filtro, debería poder ver en la vista de cascada de demanda del panel [!DNL Marketo Measure] los mismos datos que vería en su CRM.

**¿Cómo lo configuro?**

>[!NOTE]
>
>Al actualizar las reglas de segmentos, se volverán a procesar los datos históricos.

Paso 1: Determine qué información desea ver.

Antes de usar esta función, averigüe por qué información de punto de contacto desea filtrar. Recuerde utilizar los valores exactos en su CRM para los tipos de registro. La configuración filtrará los puntos de contacto de la parte superior a la parte inferior de la funnel de marketing.

Paso 2: Inicie sesión y busque la función [!UICONTROL Segmentos].

* Vaya a [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} e inicie sesión
* En la ficha [!UICONTROL Mi cuenta], seleccione [!UICONTROL Configuración]
* Seleccione [!UICONTROL Segmentos] de las opciones de la barra lateral izquierda, en la sección [!UICONTROL Informes]

Paso 3: Comprender los componentes.

* Utilice esta leyenda para comprender los distintos iconos de esta página

![Use esta leyenda para comprender los distintos iconos que se encuentran en esta página](assets/custom-segmentation-1.png)

Paso 4: Adición De Reglas De Filtro.

* En primer lugar, introduzca el nombre de la categoría. [!UICONTROL Tipo de negocio] es un ejemplo. Haga clic en la marca de verificación cuando haya terminado. Debe introducir un nombre de categoría para poder añadir segmentos
* Haga clic en el signo más para agregar un segmento
* Introduzca un nombre de segmento. Por ejemplo: puede tener un segmento para Nuevos negocios, Socios, Renovación o Ampliación de venta

![Escriba un nombre de segmento. Por ejemplo, podría tener un segmento para ](assets/custom-segmentation-2.png)

* Haga clic en el icono &quot;+&quot; para mostrar los campos de entrada de la regla. Las opciones de la lista desplegable Campo extrae campos directamente de su CRM

![Haga clic en el icono de signo más para mostrar los campos de entrada de la regla. Las opciones ](assets/custom-segmentation-3.png)

>[!NOTE]
>
>Los campos de fórmula no se pueden utilizar dentro de las reglas y no aparecerán en la lista de selección. Dado que las fórmulas calculan en segundo plano y no modifican un registro, [!DNL Marketo Measure] no puede detectar si un registro se ajusta o no a una regla.

* La opción [!UICONTROL Value] no es una lista desplegable y su valor debe introducirse manualmente. Asegúrese de comprobar los valores en su organización de Salesforce
* Repita este proceso para las reglas del segmento Oportunidades
* La categoría &quot;Otros&quot; es un segmento predeterminado que capturará cualquier punto de contacto indefinido. Puede cambiar el nombre del segmento predeterminado
* Haga clic en el icono de la papelera para eliminar una categoría completa o una regla individual dentro de una categoría. También puede hacer clic en el icono de lápiz para editar la categoría o la regla
* Observe que tiene un botón &quot;[!UICONTROL Guardar]&quot; y un botón &quot;Guardar y procesar&quot;. Utilice el botón Guardar para guardar el trabajo y los cambios con el tiempo. Utilice el botón Guardar y procesar SOLO una vez que se haya asegurado de que:

   * La asignación es precisa
   * Ha añadido todos los segmentos que desea rastrear dentro de una categoría
   * El botón Guardar y procesar déclencheur [!DNL Marketo Measure] para sincronizar todos los puntos de contacto y aplicar la nueva información que agregó. Este proceso tarda 7 días y las reglas no se pueden cambiar durante este periodo

**_Notas adicionales:_**

Si las reglas no están configuradas tanto para posibles clientes/contactos como para oportunidades, solo verá una parte de los datos. Para obtener más información, si no configura las reglas de Oportunidades, solo verá datos de cliente potencial/contacto sin las oportunidades asociadas a ellos. Lo mismo ocurre si no configura reglas para posibles clientes o contactos, solo verá oportunidades sin los posibles clientes o contactos asociados.

Cuando haya terminado, haga clic en [!UICONTROL Guardar] primero, vuelva a comprobar todo y, a continuación, haga clic en [!UICONTROL Guardar y procesar]. Recuerde que no puede editar la configuración durante los siete días posteriores al guardar y procesar, ya que [!DNL Marketo Measure] está volviendo a dar formato a los datos durante este tiempo.

Si es cliente de Marketo Measure Ultimate y ha establecido su objeto de panel predeterminado como contacto, no utilice los dos campos siguientes específicos para posible cliente ([obtener más información](/help/data-integrity-requirement.md){target="_blank"}).

* b2b.personStatus
* b2b.isConverted

**¿Cómo se guardan los informes generados?**

Los informes generados no se pueden guardar directamente en la interfaz de usuario. Sin embargo, [!DNL Marketo Measure] guarda los nombres de los segmentos en la dirección URL para que pueda mantener un registro de cada informe marcando la página.
