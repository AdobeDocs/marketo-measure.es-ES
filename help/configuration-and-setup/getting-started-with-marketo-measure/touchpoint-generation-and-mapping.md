---
unique-page-id: 18874554
description: 'Generación y asignación de puntos de contacto: [!DNL Marketo Measure] - Documentación del producto'
title: Generación y asignación de puntos de contacto
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
feature: Touchpoints
source-git-commit: 3df1bd288ebd65f75a2ed52d7c8a6faf50c7ff1f
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 2%

---

# Generación y asignación de puntos de contacto {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure] las historias de atribución dependen de dos procesos:

* Generación de puntos de contacto, que crea puntos de contacto que representan las interacciones de una persona con sus esfuerzos de marketing y ventas
* Asignación de puntos de contacto, que acredita puntos de contacto al canal y subcanal adecuados

Para que usted pueda sacar el máximo partido a [!DNL Marketo Measure], debería trabajar con su [!DNL Marketo Measure] representante para personalizar ambos procesos y adaptarlos a las necesidades de su organización.

Métodos de generación de Touchpoint

El proceso de generación de puntos de contacto responde a la pregunta: &quot;¿Cómo es? [!DNL Marketo Measure] ¿Va a saber que esto ocurrió?&quot; Según el conjunto de funciones y los tipos de interacciones que puedan tener sus clientes potenciales, hay hasta tres formas [!DNL Marketo Measure] puede recoger una interacción y crear un punto de contacto para representarla.

>[!IMPORTANT]
>
>[!DNL Marketo Measure] solo genera un punto de contacto por sesión. Si se ha rellenado más de un formulario, solo se capturará el primer relleno de formulario.

| **Tipo de interacción** | **Ejemplo** | **Método de generación de Touchpoint** |
|---|---|---|
| En línea, en sus sitios | Relleno de formulario | [!DNL Marketo Measure] JavaScript |
| Sin conexión; En línea, no en sus sitios | Ferias comerciales; El socio de distribución de contenido ofrece una lista de posibles clientes que interactúan con el contenido | Suscripción a CRM Campaign sincronizada con [!DNL Marketo Measure], estableciendo el Tipo de sincronización de campaña directamente en la campaña o estableciendo reglas en la página Campañas en [!DNL Marketo Measure] |
| Actividad de ventas | Llamada saliente por SDR | Registro de actividad de CRM (tarea o evento) sincronizado con [!DNL Marketo Measure], mediante la lógica en [!UICONTROL Actividades] página en [!DNL Marketo Measure] |

Métodos de asignación de Touchpoint

El proceso de asignación de puntos de contacto responde a la pregunta: &quot;Una vez creado este punto de contacto, ¿cómo [!DNL Marketo Measure] ¿va a saber a qué canal y subcanal pertenece?&quot; Cada método de generación de puntos de contacto tiene su propio método de asignación de puntos de contacto.

| **Tipo de interacción** | **Método de generación** | **Método de asignación** |
|---|---|---|
| En línea, en sus sitios | [!DNL Marketo Measure] JavaScript | A través de [!DNL Online Channels] página en [!DNL Marketo Measure], haciendo referencia a valores de UTM, página de aterrizaje e información de página de referencia |
| Sin conexión; En línea, no en sus sitios | Sincronización de suscripción a CRM Campaign | A través de [!UICONTROL Canales sin conexión] página en [!DNL Marketo Measure], haciendo referencia al tipo de campaña |
| Actividad de ventas | Sincronización de actividad de CRM | A través de [!UICONTROL Canales en línea] página en [!DNL Marketo Measure], haciendo referencia al Nombre de campaña asignado en la [!UICONTROL Actividades] página |

>[!MORELIKETHIS]
>
>* [Asignación de puntos de contacto en línea a [!DNL Marketo Measure] Canales/Subcanales](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [Sincronización de campañas CRM desde SFDC](/help/channel-tracking-and-setup/offline-channels/deprecated-processes/syncing-offline-campaigns.md)
>* [Sincronización de campañas CRM desde [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [Asignación de campañas CRM a [!DNL Marketo Measure] Canales/Subcanales](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [Creación de puntos de contacto a partir de actividades de ventas](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [Preguntas frecuentes sobre actividades y asignación de puntos de contacto de actividades a canales o subcanales](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

