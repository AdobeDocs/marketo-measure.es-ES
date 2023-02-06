---
unique-page-id: 27656441
description: 'Preguntas frecuentes sobre la integración de Drift: [!DNL Marketo Measure] - Documentación del producto'
title: Preguntas frecuentes sobre la integración de Drift
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Preguntas frecuentes sobre la integración de Drift {#drift-integration-faq}

Como parte del [!DNL Marketo Measure] integración con Drift, hemos esbozado algunas de las preguntas más frecuentes. Si tiene alguna pregunta que no se describe a continuación, póngase en contacto con el administrador de éxito del cliente o [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

**¿Cómo se habilita la integración?**

Seguimiento del chat de deriva para [!DNL Marketo Measure] está activada de forma predeterminada. Si, por cualquier motivo, desea deshabilitarlo (y no crear Touchpoints a partir de Chats de deriva de forma predeterminada), necesitamos agregar un atributo adicional a su [!DNL Marketo Measure] Implementación de Javascript, que se muestra a continuación:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

Para aquellos que usan [!DNL Google Tag Manager] para cargar el [!DNL Marketo Measure] Script, si desea excluir los chats de deriva de ser elegibles para Touchpoint, deberá agregar a lo siguiente `<span>` justo después de su [!DNL Marketo Measure] Script:

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**¿Qué hace la integración?**

La integración ahora permite [!DNL Marketo Measure] para realizar un seguimiento de cuándo un usuario final proporciona su dirección de correo electrónico en una conversación de derivación. Desde allí creamos puntos de contacto a partir de estas interacciones con un tipo de punto de contacto de &quot;Chat web&quot;. Esta integración permite a los especialistas en marketing comprender el rendimiento de sus interacciones de chat, junto con los canales, subcanales o campañas que llevan a las personas a interactuar con estos chats.

**¿Qué sucede si realizo un seguimiento de la desviación mediante reglas de sincronización de campañas?**

Si hay reglas de sincronización de campañas para crear puntos de contacto para las interacciones de chat de Drift, debe asegurarse de dejar de agregar esos usuarios finales en particular a la campaña de CRM correspondiente. De lo contrario, una vez que el bit de característica esté habilitado, crearemos un punto de contacto de CRM Campaign y un punto de contacto digital para una interacción de chat de Drift.

**¿Qué sucede si realizo un seguimiento de la desviación a través de campañas CRM?**

Si existen campañas CRM para crear puntos de contacto para interacciones de chat de Drift, se deberá establecer una fecha de finalización de punto de contacto en esas campañas específicas (la fecha de finalización del punto de contacto debe ser la fecha en la que se habilitó el bit de la función de integración de chat web).

**¿Qué sucede si realizo un seguimiento de la desviación mediante actividades?**

Si existen reglas de actividad para crear puntos de contacto para las interacciones de chat de Drift, será necesario agregar un elemento de lógica adicional a las reglas. Deberá agregar lógica mediante el campo Fecha de creación de la tarea para evitar que se cree la duplicación de puntos de contacto (IE CrmTask.CreatedDate es menor que la fecha en la que se habilitó el bit de la función). Consulte la captura de pantalla siguiente, por ejemplo.

![](assets/activity-rule-drift.png)
