---
unique-page-id: 18874684
description: Fechas de sincronización de campañas - [!DNL Marketo Measure] - Documentación del producto
title: Fechas de sincronización de campañas
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 0%

---

# Fechas de sincronización de campañas {#campaign-sync-dates}

Conozca lo que hace la función Fechas de sincronización de campañas, y ofrezca algunos casos de uso para esta función.

**[!DNL Marketo Measure]Paquete necesario: 6.9 o superior**

Esta función consiste en dos campos de fecha simples en la variable [!DNL Salesforce] Objeto de campaña:

* Fecha inicial de Touchpoint
* Fecha de finalización de Touchpoint

Una vez que los puntos de contacto del comprador están activados en una campaña determinada, las fechas de sincronización de la campaña le permiten establecer parámetros de fecha de punto de contacto en la campaña individual. Por lo tanto, si agregara una Fecha de finalización de Touchpoint del 1 de marzo de 2017, entonces [!DNL Marketo Measure] solo creará Touchpoints en los miembros de Campaign que se añadieron a la campaña antes de esa fecha. [!DNL Marketo Measure] no creará Touchpoints para los miembros de la campaña que se añadieron después del 1 de marzo de 2017.

![](assets/1.gif)

Del mismo modo, si agregara una Fecha de inicio de punto de contacto en una campaña (digamos, 1 de enero de 2017), entonces [!DNL Marketo Measure] no creará Touchpoints en los miembros de Campaign que se añadieron a la campaña antes del 1 de enero de 2017. No es necesario agregar una fecha de inicio de Touchpoint si agrega una fecha de finalización de Touchpoint y viceversa.

## Casos de uso {#use-cases}

**Rellenar puntos de contacto**

Puede haber ocasiones en las que un equipo de marketing puede perder la adición de parámetros utm a un esfuerzo de marketing determinado. Las fechas de sincronización de campañas le permitirán (si utiliza campañas SFDC para los esfuerzos en línea) rellenar algunos datos que faltan. Digamos que está ejecutando una campaña de correo electrónico que comenzó el 1 de mayo, pero su equipo no añadió parámetros utm en esa campaña de correo electrónico hasta el 15 de mayo. Si está realizando el seguimiento de las conversiones de correo electrónico a través de una campaña SFDC, podrá establecer una fecha de finalización de Touchpoint del 15 de mayo en dicha campaña y habilitar Touchpoints para los miembros &quot;Respondidos&quot; de la campaña. Esta acción indicará [!DNL Marketo Measure] para crear Touchpoints para todas esas respuestas hasta el 15 de mayo.

**Puntos de contacto de pertenencia a una campaña retroactiva**

Si eres un nuevo [!DNL Marketo Measure] cliente, es posible que esté interesado en traer algunos de los datos de marketing que ha estado rastreando a través de campañas SFDC. Sin embargo, si tuviera que habilitar Touchpoints en las campañas de SFDC en línea, podría tener el problema de la atribución de recuento doble ya que [!DNL Marketo Measure] crea automáticamente Touchpoints para sus campañas de marketing en línea. Para evitar los datos de recuento doble, puede utilizar Fechas de finalización de puntos de contacto de Campaign para establecer un límite en las fechas de punto de contacto creadas por [!DNL Marketo Measure] en la campaña SFDC. Por ejemplo, si desea agregar conversiones retroactivas para una campaña de Social que ha estado rastreando en SFDC, pero comprende que ha agregado la variable [!DNL Marketo Measure] JavaScript (que crea Touchpoints en línea) el 1 de julio, permite editar la campaña de Social SFDC para que contenga una fecha de finalización de Touchpoint igual al 1 de julio y habilitar Touchpoints para esa campaña.

Puede haber muchos otros casos de uso para las fechas de finalización de Touchpoint. Si necesita ayuda para averiguar una situación específica, no dude en ponerse en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Universidad: Campos de miembros de campaña y campaña](https://learn.bizible.com/2-bizible-customization/137720https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
