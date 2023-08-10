---
unique-page-id: 18874684
description: Fechas de sincronización de Campaign - [!DNL Marketo Measure] - Documentación del producto
title: Fechas de sincronización de campañas
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
feature: Channels
source-git-commit: 31ffb58f5318b71d478056f9b914eb1d42c7719a
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 2%

---

# Fechas de sincronización de campañas {#campaign-sync-dates}

Descubra lo que hace la función Fechas de sincronización de Campaign, así como algunos casos de uso para esta función.

**[!DNL Marketo Measure]Paquete requerido: 6.9 o superior**

Esta función consta de dos campos de fecha simples en la variable [!DNL Salesforce] Objeto de campaña:

* Fecha de inicio de Touchpoint
* Fecha de finalización de Touchpoint

Una vez que los puntos de contacto del comprador están activados en una campaña en particular, las fechas de sincronización de campaña le permiten establecer los parámetros de fecha de punto de contacto en la campaña individual. Por lo tanto, si tuviera que añadir una fecha de finalización de Touchpoint del 1 de marzo de 2017, [!DNL Marketo Measure] solo creará puntos de contacto en los miembros de la campaña que se añadieron a la campaña antes de esa fecha. [!DNL Marketo Measure] no creará puntos de contacto para los miembros de la campaña que se añadieron después del 1 de marzo de 2017.

![](assets/1.gif)

Del mismo modo, si tuviera que añadir una fecha de inicio de Touchpoint en una campaña (por ejemplo, el 1 de enero de 2017), [!DNL Marketo Measure] no creará puntos de contacto en los miembros de la campaña que se añadieron a la campaña antes del 1 de enero de 2017. No es necesario añadir una Fecha de inicio de punto de contacto si se añade una Fecha de finalización de punto de contacto y viceversa.

## Casos de uso {#use-cases}

**Puntos de contacto de relleno**

Puede haber ocasiones en que a un equipo de marketing le falte añadir parámetros utm a un esfuerzo de marketing concreto. Las fechas de sincronización de campañas le permitirán (si utiliza campañas SFDC para esfuerzos en línea) rellenar algunos datos que se han perdido. Supongamos que está ejecutando una campaña de correo electrónico que comenzó el 1 de mayo, pero su equipo no agregó parámetros utm en esa campaña de correo electrónico hasta el 15 de mayo. Si está realizando un seguimiento de las conversiones por correo electrónico a través de una campaña de SFDC, podrá establecer una fecha de finalización de Touchpoint del 15 de mayo en esa campaña y habilitar los puntos de contacto para los miembros &quot;respondidos&quot; de la campaña. Esta acción indicará [!DNL Marketo Measure] crear puntos de contacto para todas esas respuestas hasta el 15 de mayo.

**Puntos de contacto de pertenencia a campaña retroactiva**

Si eres un nuevo [!DNL Marketo Measure] cliente de, podría estar interesado en obtener algunos de los datos de marketing que ha estado rastreando mediante campañas de SFDC. Sin embargo, si habilitara los puntos de contacto en sus campañas SFDC en línea, podría tener el problema de la atribución de recuento doble desde [!DNL Marketo Measure] está creando automáticamente puntos de contacto para sus esfuerzos de marketing en línea. Para evitar el recuento doble de datos, puede utilizar Fechas de finalización de punto de contacto de Campaign para establecer un límite en las fechas de punto de contacto creadas por [!DNL Marketo Measure] en la campaña de SFDC. Por ejemplo, si desea añadir conversiones retroactivas para una campaña social que ha estado rastreando en SFDC, pero tiene entendido que ha añadido la variable [!DNL Marketo Measure] JavaScript (que crea puntos de contacto en línea) el 1 de julio. A continuación, puede editar la campaña de Social SFDC para que contenga una fecha de finalización de punto de contacto igual al 1 de julio y activar los puntos de contacto del comprador para esa campaña.

Puede haber muchos otros casos de uso para las fechas de finalización de Touchpoint. Si necesita ayuda para resolver una situación específica, no dude en ponerse en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Universidad: Campos de campaña y de miembros de campaña](https://learn.bizible.com/2-bizible-customization/137720https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
