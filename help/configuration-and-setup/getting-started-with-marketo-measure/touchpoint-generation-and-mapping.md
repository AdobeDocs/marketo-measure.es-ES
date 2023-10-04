---
unique-page-id: 18874554
description: 'Generación y asignación de puntos de contacto: documentación del producto  [!DNL Marketo Measure] '
title: Generación y asignación de puntos de contacto
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
feature: Touchpoints
source-git-commit: 3df1bd288ebd65f75a2ed52d7c8a6faf50c7ff1f
workflow-type: ht
source-wordcount: '374'
ht-degree: 100%

---

# Generación y asignación de puntos de contacto {#touchpoint-generation-and-mapping}

Las historias de atribución de [!DNL Marketo Measure] dependen de dos procesos:

* La generación de puntos de contacto, que crea puntos de contacto que representan las interacciones de una persona con sus esfuerzos de marketing y ventas
* La asignación de puntos de contacto, que acredita puntos de contacto al canal y subcanal adecuados

Para que pueda sacar el máximo partido a [!DNL Marketo Measure], debería trabajar con su representante de [!DNL Marketo Measure] para personalizar ambos procesos y adaptarlos a las necesidades de su organización.

Métodos de generación de puntos de contacto

El proceso de generación de puntos de contacto responde a la pregunta: “¿Cómo va a saber [!DNL Marketo Measure] que esto ocurrió?” Según el conjunto de funciones y los tipos de interacciones que puedan tener sus clientes potenciales, hay hasta tres formas que [!DNL Marketo Measure] puede recoger una interacción y crear un punto de contacto para representarla.

>[!IMPORTANT]
>
>[!DNL Marketo Measure] solo genera un punto de contacto por sesión. Si se ha rellenado más de un formulario, solo se capturará el primer relleno de formulario.

| **Tipo de interacción** | **Ejemplo** | **Método de generación de punto de contacto** |
|---|---|---|
| En línea, en sus sitios | Relleno de formulario | JavaScript de [!DNL Marketo Measure] |
| Sin conexión; en línea, no en sus sitios | Ferias comerciales; el socio de distribución de contenido ofrece una lista de clientes potenciales que interactúan con su contenido | Abono a CRM Campaign sincronizado con [!DNL Marketo Measure], estableciendo el Tipo de sincronización de campaña directamente en la campaña o estableciendo reglas en la página Campañas en [!DNL Marketo Measure] |
| Actividad de ventas | Llamada saliente por SDR | Registro de actividad de CRM (tarea o evento) sincronizado con [!DNL Marketo Measure], mediante la lógica en la página [!UICONTROL Actividades] en [!DNL Marketo Measure] |

Métodos de asignación de punto de contacto

El proceso de asignación de puntos de contacto responde a la pregunta: “Una vez creado este punto de contacto, ¿cómo va a saber [!DNL Marketo Measure] a qué canal y subcanal pertenece?” Cada método de generación de puntos de contacto tiene su propio método de asignación de puntos de contacto.

| **Tipo de interacción** | **Método de generación** | **Método de asignación** |
|---|---|---|
| En línea, en sus sitios | JavaScript de [!DNL Marketo Measure] | A través de la página [!DNL Online Channels] en [!DNL Marketo Measure], haciendo referencia a valores de UTM, página de aterrizaje e información de página de referencia |
| Sin conexión; en línea, no en sus sitios | Sincronización de suscripción a CRM Campaign | A través de la página [!UICONTROL Canales sin conexión] en [!DNL Marketo Measure], haciendo referencia al tipo de campaña |
| Actividad de ventas | Sincronización de actividad de CRM | A través de la página [!UICONTROL Canales en línea] en [!DNL Marketo Measure], haciendo referencia al Nombre de campaña asignado en la página [!UICONTROL Actividades] |

>[!MORELIKETHIS]
>
>* [Asignación de puntos de contacto en línea a [!DNL Marketo Measure] Canales/Subcanales](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [Sincronización de Campañas de CRM desde SFDC](/help/channel-tracking-and-setup/offline-channels/deprecated-processes/syncing-offline-campaigns.md)
>* [Sincronización de Campañas CRM desde [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [Asignación de Campañas CRM a [!DNL Marketo Measure] Canales/Subcanales](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [Creación de puntos de contacto a partir de actividades de ventas](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [Preguntas frecuentes sobre actividades y asignación de puntos de contacto de actividades a canales o subcanales](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

