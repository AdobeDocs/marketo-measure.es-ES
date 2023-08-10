---
description: 'Prácticas recomendadas para la segmentación: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para la segmentación
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
feature: Segmentation
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 2%

---

# Prácticas recomendadas para la segmentación {#best-practices-for-segmentation}

## Información general {#overview}

[!DNL Marketo Measure] La segmentación le permite definir reglas, que son esencialmente filtros, basados en los campos CRM para agruparlos en segmentos individuales. Estos segmentos estarán disponibles para su uso en sus paneles de Discover, así como en su [!DNL Salesforce] informes.

La segmentación es crucial para la utilización de su [!DNL Marketo Measure] cuenta, especialmente dentro de sus paneles de Discover. Debido a que el [!DNL Marketo Measure] Los tableros de Discover se limitan a un conjunto predeterminado de filtros; la segmentación le permite dividir los datos en Discover de forma muy similar a como lo haría en su [!DNL Salesforce] informes.

Cuando se inserta en [!DNL Salesforce], los valores de los segmentos se escriben en el campo &quot;Segmento&quot; y se incluyen en cualquier tipo de informe de punto de contacto del comprador. Esto permite generar informes uniformes en ambas plataformas. El segmento también se puede encontrar en el &quot;Detalle del punto de contacto&quot; de cualquier punto de contacto.

Cuando se inserten en Discover, los segmentos aparecerán como un filtro disponible en el menú desplegable de filtros ubicado en todos los tableros.

## Práctica recomendada {#best-practice}

Tanto si define la segmentación por primera vez como si simplemente revisa la segmentación previamente establecida, tenga en cuenta las siguientes prácticas recomendadas.

* ¡Manténgalo simple!
* Alinee el nombre del segmento con la nomenclatura de la organización, es decir, la categoría = nombre del filtro, el segmento = valor del filtro
* No utilice campos de fórmula en las reglas
* Siempre que sea posible, genere la segmentación tanto en el posible cliente/contacto como en la oportunidad para que pueda utilizarla en todo el canal
   * No todas las categorías de segmentos se alinearán en todo el canal
      * Una categoría de segmento de &quot;Tipo de oportunidad&quot; no se relacionará con posibles clientes, por ejemplo; sin embargo, un segmento relacionado con &quot;Región&quot; es probablemente una categoría que se puede definir a lo largo del canal
* Piense en las formas en que le gusta cortar los datos actualmente, ya sea en la herramienta CRM o en una de BI, y considere la posibilidad de crear esto como un segmento en [!DNL Marketo Measure] para que pueda tener los mismos informes en Discover

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Revisar la segmentación al menos dos veces al año garantizará que la segmentación esté actualizada. Como práctica recomendada, le recomendamos que revise sus reglas dentro de &#39;[!UICONTROL Segmentos]&#39; de su [!DNL Marketo Measure] Configuración de la cuenta, así como extraer informes en [!DNL Salesforce] para revisar los segmentos en acción. Estos pasos le ayudarán a usted y a su equipo a confiar en su segmentación y, posteriormente, en sus [!DNL Marketo Measure] informes.

Otras razones que pueden déclencheur revisar su Segmentación son...

* Facturación en su equipo de marketing
* Cambios en los campos utilizados para definir los segmentos
* Adiciones o cambios en los segmentos que ya se han establecido

>[!MORELIKETHIS]
>
>[Configuración de la segmentación personalizada](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
