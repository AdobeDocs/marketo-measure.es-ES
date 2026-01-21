---
unique-page-id: 27656441
description: Preguntas frecuentes sobre la integración de Drift - [!DNL Marketo Measure]
title: Preguntas frecuentes sobre la integración de Drift
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
feature: Integration
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 2%

---

# Preguntas frecuentes sobre la integración de Drift {#drift-integration-faq}

Como parte de la integración de [!DNL Marketo Measure] con Drift, estas son algunas de las preguntas más frecuentes. Si tiene alguna pregunta que no se describe a continuación, póngase en contacto con el equipo de cuenta de Adobe (su administrador de cuentas) o con el [Soporte técnico de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

**¿Cómo se habilita la integración?**

El seguimiento de chats a la deriva para [!DNL Marketo Measure] está habilitado de manera predeterminada. Si desea deshabilitarlo (y no crear puntos de contacto desde chats a la deriva de forma predeterminada), agregue un atributo adicional agregado a su implementación de Javascript [!DNL Marketo Measure], que aparece en negrita a continuación:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

Para aquellos que usan [!DNL Google Tag Manager] para cargar el script [!DNL Marketo Measure], si desea excluir los chats de deriva de la aptitud para Touchpoint, agregue los siguientes `<span>` justo después del script [!DNL Marketo Measure]:

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**¿Qué hace la integración?**

La integración ahora permite que [!DNL Marketo Measure] rastree cuándo un usuario final proporciona su dirección de correo electrónico en un chat de Drift. A partir de ahí creamos puntos de contacto a partir de estas interacciones con un Touchpoint Type de &quot;Chat web&quot;. Esta integración permite a los especialistas en marketing comprender el rendimiento de sus interacciones de chat, junto con los canales, subcanales o campañas que llevan a las personas a interactuar con estos chats.

**¿Qué sucede si realizo un seguimiento del desplazamiento a través de reglas de sincronización de campaña?**

Si existen reglas de sincronización de campañas para crear puntos de contacto para las interacciones de chat de Drift, asegúrese de dejar de agregar esos usuarios finales en particular a la campaña de CRM correspondiente. De lo contrario, una vez que el bit de función esté habilitado, cree un punto de contacto de CRM Campaign y un punto de contacto digital para una interacción de chat de Drift.

**¿Qué sucede si realizo un seguimiento de la deriva a través de campañas CRM?**

Si hay campañas CRM en marcha para crear puntos de contacto para interacciones de chat de deriva, se debe establecer una fecha de finalización de punto de contacto en esas campañas específicas (la fecha de finalización de punto de contacto debe ser la fecha en la que se habilita el bit de la función de integración de chat web).

**¿Qué sucede si realizo un seguimiento de la deriva a través de actividades?**

Si existen reglas de actividad para crear puntos de contacto para las interacciones de chat de Drift, se debe añadir una parte adicional de lógica a las reglas. Agregue lógica utilizando el campo Fecha de creación de la tarea para evitar la duplicación de puntos de contacto (IE CrmTask.CreatedDate es menor que la fecha en la que se habilitó el bit de característica). Vea la captura de pantalla siguiente para ver un ejemplo.

![](assets/activity-rule-drift.png)
