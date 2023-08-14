---
description: Documentación del producto  [!DNL Marketo Measure] . Prácticas recomendadas para la segmentación.
title: Prácticas recomendadas para la segmentación
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
feature: Segmentation
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: ht
source-wordcount: '419'
ht-degree: 100%

---

# Prácticas recomendadas para la segmentación {#best-practices-for-segmentation}

## Información general {#overview}

La segmentación de [!DNL Marketo Measure] le permite definir reglas, que son esencialmente filtros, basados en los campos CRM para agruparlos en segmentos individuales. Estos segmentos estarán disponibles para su uso en los paneles de Discover, así como en la creación de informes de [!DNL Salesforce].

La segmentación es crucial para la utilización de su cuenta de [!DNL Marketo Measure], especialmente dentro de sus tableros de Discover. Debido a que los tableros de Discover de [!DNL Marketo Measure] se limitan a un conjunto predeterminado de filtros; la segmentación le permite dividir los datos en Discover de forma muy similar a como lo haría en la creación de informes de [!DNL Salesforce].

Cuando se insertan en [!DNL Salesforce], los valores del segmento se escriben en el campo “Segmento” y se incluyen en cualquier tipo de informe Buyer Touchpoint. Esto permite crear informes homogéneos en ambas plataformas. El segmento también se puede encontrar en “Touchpoint Detail” de cualquier punto de contacto.

Cuando se inserten en Discover, los segmentos aparecerán como un filtro disponible en el menú desplegable de filtros ubicado en todos los tableros.

## Práctica recomendada {#best-practice}

Tanto si define la segmentación por primera vez como si simplemente revisa la segmentación previamente establecida, tenga en cuenta las siguientes prácticas recomendadas.

* No se complique.
* Alinee el nombre del segmento con la nomenclatura de la organización, es decir, la categoría = nombre del filtro, segmento = valor del filtro
* No utilice campos de fórmula en las reglas
* Siempre que sea posible, genere la segmentación tanto en el posible cliente/contacto como en la oportunidad para que se pueda utilizarla en todo el canal
   * No todas las categorías de segmentos se alinearán en todo el canal
      * Una categoría de segmento de “Tipo de oportunidad” no se relacionará con posibles clientes, por ejemplo; sin embargo, un segmento relacionado con “Región” es probablemente una categoría que se puede definir a lo largo del canal
* Piense en las formas en que le gusta dividir los datos actualmente, ya sea en la herramienta CRM o en una de BI, y considere la posibilidad de crear esto como un segmento en [!DNL Marketo Measure] para que pueda tener los mismos informes en Discover

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Revisar la segmentación al menos dos veces al año garantizará que la segmentación esté actualizada. Como práctica recomendada, le recomendamos que revise sus reglas dentro de la pestaña “[!UICONTROL Segmentos]” de su Configuración de la cuenta de [!DNL Marketo Measure], así como extraer informes en [!DNL Salesforce] para revisar los segmentos en acción. Estos pasos le ayudarán a usted y a su equipo a confiar en su segmentación y, posteriormente, en la creación de informes de [!DNL Marketo Measure].

Otras razones que pueden desencadenar una revisión de la Segmentación incluyen las siguientes:

* Rotación en su equipo de marketing
* Cambios en los campos utilizados para definir los segmentos
* Adiciones o cambios en los segmentos que ya se han establecido

>[!MORELIKETHIS]
>
>[Cómo configurar la segmentación personalizada](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
