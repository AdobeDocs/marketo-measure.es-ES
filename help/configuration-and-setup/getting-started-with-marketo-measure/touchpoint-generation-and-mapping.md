---
unique-page-id: 18874554
description: 'Generación y asignación de puntos de contacto: [!DNL Marketo Measure] - Documentación del producto'
title: Generación y asignación de puntos de contacto
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# Generación y asignación de puntos de contacto {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure] los artículos de atribución dependen de dos procesos:

* Generación de touchpoint, que crea puntos de contacto que representan las interacciones de una persona con sus esfuerzos de marketing y ventas
* Asignación de puntos de contacto, que acredita los puntos de contacto con el canal y subcanal adecuados

Para que usted pueda sacar el máximo partido de [!DNL Marketo Measure], debe trabajar con su [!DNL Marketo Measure] rep para personalizar ambos procesos según las necesidades de su organización.

Métodos de generación de touchpoint

El proceso de generación de puntos de contacto responde a la pregunta: &quot;¿Cómo es [!DNL Marketo Measure] ¿va a saber que esto ocurrió?&quot; Según el conjunto de funciones y los tipos de interacciones que puedan tener los clientes potenciales, hay hasta tres formas: [!DNL Marketo Measure] puede elegir una interacción y crear un punto de contacto para representarla.

| **Tipo de interacción** | **Ejemplo** | **Método de generación de touchpoint** |
|---|---|---|
| En línea, en sus sitios | Relleno de formulario | [!DNL Marketo Measure] JavaScript |
| Sin conexión; En línea, no en sus sitios | ferias comerciales; El socio de distribución de contenido ofrece una lista de posibles clientes que interactuaron con el contenido | Membresía de CRM Campaign sincronizada con [!DNL Marketo Measure], ya sea estableciendo el tipo de sincronización de campaña directamente en la campaña o estableciendo reglas en la página Campañas en [!DNL Marketo Measure] |
| Actividad de ventas | Llamada de salida de SDR. | Registro de actividad de CRM (tarea o evento) sincronizado con [!DNL Marketo Measure], a través de la lógica en la variable [!UICONTROL Actividades] en [!DNL Marketo Measure] |

Métodos de asignación de Touchpoint

El proceso de asignación de puntos de contacto responde a la pregunta: &quot;Una vez creado este punto de contacto, ¿cómo es [!DNL Marketo Measure] ¿va a saber a qué canal y subcanal pertenece?&quot; Cada método de generación de puntos de contacto tiene su propio método de asignación de puntos de contacto.

| **Tipo de interacción** | **Método de generación** | **Método de asignación** |
|---|---|---|
| En línea, en sus sitios | [!DNL Marketo Measure] JavaScript | A través de [!DNL Online Channels] en [!DNL Marketo Measure], haciendo referencia a valores de UTM, página de aterrizaje e información de página de referencia |
| Sin conexión; En línea, no en sus sitios | Sincronización de miembros de CRM Campaign | A través de [!UICONTROL Canales sin conexión] en [!DNL Marketo Measure], haciendo referencia al tipo de campaña |
| Actividad de ventas | Sincronización de actividades de CRM | A través de [!UICONTROL Canales en línea] en [!DNL Marketo Measure], haciendo referencia al nombre de campaña asignado en la variable [!UICONTROL Actividades] página |

>[!MORELIKETHIS]
>
>* [Asignación de puntos de contacto en línea a [!DNL Marketo Measure] Canales/subcanales](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [Sincronización de campañas CRM desde SFDC](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)
>* [Sincronización de campañas CRM desde [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [Asignación de campañas CRM a [!DNL Marketo Measure] Canales/subcanales](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [Creación de touchpoints a partir de actividades de ventas](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [Preguntas más frecuentes sobre actividades y asignación de puntos de contacto de actividades a canales/subcanales](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)


