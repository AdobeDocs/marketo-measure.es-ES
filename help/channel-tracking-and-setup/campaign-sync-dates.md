---
description: Guía de fechas de sincronización de Campaign para usuarios de Marketo Measure
title: Fechas de sincronización de campañas
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
feature: Channels
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 4%

---

# Fechas de sincronización de campañas {#campaign-sync-dates}

Descubra lo que hace la función Fechas de sincronización de Campaign, así como algunos casos de uso para esta función.

>[!NOTE]
>
>Este artículo trata sobre un proceso obsoleto. Recomendamos a los usuarios que utilicen el [proceso en la aplicación nuevo y mejorado](/help/channel-tracking-and-setup/custom-campaign-sync.md){target="_blank"}.

Se requiere el paquete **[!DNL Marketo Measure]: 6.9 o superior**

Esta característica consta de dos campos de fecha simples en el objeto de campaña [!DNL Salesforce]:

* Fecha de inicio de Touchpoint
* Fecha de finalización de Touchpoint

Una vez que los puntos de contacto del comprador están activados en una campaña en particular, las fechas de sincronización de campaña le permiten establecer los parámetros de fecha de punto de contacto en la campaña individual. Por lo tanto, si agregara una fecha de finalización de punto de contacto del 1 de marzo de 2017, [!DNL Marketo Measure] solo creará puntos de contacto en los miembros de la campaña que se agregaron a la campaña antes de esa fecha. [!DNL Marketo Measure] no creará puntos de contacto para los miembros de la campaña que se agregaron después del 1 de marzo de 2017.

![Una vez que los puntos de contacto del comprador estén habilitados en una campaña en particular, las fechas de sincronización de campañas](assets/legacy-processes-3.gif)

Del mismo modo, si agregara una fecha de inicio del punto de contacto en una campaña (por ejemplo, el 1 de enero de 2017), [!DNL Marketo Measure] no creará puntos de contacto en los miembros de la campaña que se agregaron a la campaña antes del 1 de enero de 2017. No es necesario añadir una Fecha de inicio de punto de contacto si se añade una Fecha de finalización de punto de contacto y viceversa.

## Casos de uso {#use-cases}

**Puntos de contacto de relleno**

Puede haber ocasiones en que a un equipo de marketing le falte añadir parámetros utm a un esfuerzo de marketing concreto. Las fechas de sincronización de campañas le permiten (si usa campañas de SFDC para esfuerzos en línea) rellenar algunos datos que se han perdido. Supongamos que está ejecutando una campaña de correo electrónico que comenzó el 1 de mayo, pero su equipo no agregó parámetros utm en esa campaña de correo electrónico hasta el 15 de mayo. Si está realizando un seguimiento de las conversiones por correo electrónico a través de una campaña de SFDC, podrá establecer una Fecha de finalización del punto de contacto del 15 de mayo en esa campaña y habilitar los puntos de contacto para los miembros &quot;respondidos&quot; de la campaña. Esta acción le indicará a [!DNL Marketo Measure] que cree puntos de contacto para todas esas respuestas hasta el 15 de mayo.

**Puntos de contacto de pertenencia a campañas retroactivas**

Si es un cliente nuevo de [!DNL Marketo Measure], es posible que le interese traer algunos de los datos de marketing que ha estado rastreando a través de SFDC Campaigns. Sin embargo, si habilitara los puntos de contacto en sus campañas de SFDC en línea, podría tener el problema de la atribución de recuento doble, ya que [!DNL Marketo Measure] crea automáticamente puntos de contacto para sus esfuerzos de marketing en línea. Para evitar el recuento doble de datos, puede usar las fechas de finalización de punto de contacto de Campaign para establecer un límite en las fechas de punto de contacto creadas por [!DNL Marketo Measure] en la campaña de SFDC. Por ejemplo, si desea agregar conversiones retroactivas para una campaña de Social que ha estado rastreando en SFDC, pero tiene entendido que agregó la JavaScript [!DNL Marketo Measure] (que crea puntos de contacto en línea) el 1 de julio, puede editar la campaña de SFDC de Social para que contenga una fecha de finalización de punto de contacto igual al 1 de julio y habilitar los puntos de contacto del comprador para esa campaña.

Puede haber muchos otros casos de uso para las fechas de finalización de Touchpoint. Si necesita ayuda para resolver una situación específica, no dude en ponerse en contacto con el [Soporte técnico de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
