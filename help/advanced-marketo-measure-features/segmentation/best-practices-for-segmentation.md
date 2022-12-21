---
description: 'Prácticas recomendadas para la segmentación: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para la segmentación
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Prácticas recomendadas para la segmentación {#best-practices-for-segmentation}

## Resumen {#overview}

[!DNL Marketo Measure] La segmentación le permite definir reglas, que son esencialmente filtros, basadas en los campos CRM para agruparlas en segmentos individuales. Estos segmentos estarán disponibles para su uso en los paneles de Discover, así como en los [!DNL Salesforce] informes.

La segmentación es crucial para la utilización de su [!DNL Marketo Measure] , especialmente en los tableros de Discover. Porque la variable [!DNL Marketo Measure] Los tableros de Discover están limitados a un conjunto predeterminado de filtros, la segmentación le permite diseccionar los datos en Discover de la misma manera que lo haría en su [!DNL Salesforce] informes.

Cuando se inserta en [!DNL Salesforce], los valores de segmento se escriben en el campo &quot;Segmento&quot; y se encuentran dentro de cualquier tipo de informe de punto de contacto del comprador. Esto permite generar informes uniformes en ambas plataformas. El segmento también se puede encontrar en el &quot;Detalle de punto de contacto&quot; de cualquier punto de contacto.

Cuando se inserte en Discover, los segmentos aparecerán como un filtro disponible en el menú desplegable de filtros ubicado en todos los tableros.

## Práctica recomendada {#best-practice}

Tanto si define la segmentación por primera vez como si solo revisa la segmentación que se ha establecido anteriormente, tenga en cuenta las siguientes prácticas recomendadas.

* ¡Manténlo simple!
* Alinee el nombre del segmento con la nomenclatura de su organización, es decir, la categoría = nombre del filtro, segmento = valor del filtro
* No utilice campos de fórmula en las reglas
* Siempre que sea posible, genere la segmentación tanto en el posible cliente/contacto como en la oportunidad para que pueda utilizarla en todo el canal
   * No todas las categorías de segmentos se alinearán en todo el canal
      * Una categoría de segmento de &quot;Tipo de oportunidad&quot; no se relaciona con los posibles clientes, por ejemplo, sin embargo, un segmento relacionado con &quot;Región&quot; es probablemente una categoría que se pueda definir en todo el canal
* Piense en las formas en las que actualmente desea dividir los datos, ya sea en CRM o en una herramienta BI, considere la posibilidad de crearlos como un segmento en [!DNL Marketo Measure] para que pueda tener los mismos informes en Discover

## Práctica recomendada para mantenimiento {#best-practice-for-maintenance}

Al revisar la segmentación al menos dos veces al año, se asegurará de que la segmentación esté actualizada. Como práctica recomendada, recomendamos revisar las reglas dentro de la función[!UICONTROL Segmentos]la pestaña &#39; del [!DNL Marketo Measure] Configuración de la cuenta, así como la extracción de informes dentro de [!DNL Salesforce] para revisar los segmentos en acción. Estos pasos le ayudarán a usted y a su equipo a sentirse seguros de su segmentación y, posteriormente, de su [!DNL Marketo Measure] informes.

Otras razones para que esto pueda déclencheur una revisión de la Segmentación incluyen:

* Volumen de negocio en su equipo de marketing
* Cambios en los campos que se utilizan para definir los segmentos
* Adiciones o cambios en los segmentos que ya se han establecido

>[!MORELIKETHIS]
>
>[Configurar la segmentación personalizada](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
