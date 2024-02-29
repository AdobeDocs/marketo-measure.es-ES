---
unique-page-id: 18874797
description: Agregando [!DNL Marketo Measure] Script mediante [!DNL Google Tag Manager] - [!DNL Marketo Measure]
title: Adición de script de  [!DNL Marketo Measure]  mediante  [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 59%

---

# Adición de script de [!DNL Marketo Measure]mediante [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

Al instalar el JavaScript de [!DNL Marketo Measure], recomendamos encarecidamente [codificar el script](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"} directamente en el sitio. Sin embargo, si esto no es posible, también puede utilizar [!DNL Google Tag Manager] (GTM) para cargar [!DNL Marketo Measure] JS. Tenga en cuenta que [!DNL Marketo Measure] El JS cargado a través de GTM es susceptible a la latencia. La latencia provoca un retraso en los tiempos de carga de las secuencias de comandos, lo que puede hacer que se pierda alrededor del 3-5 % de todos los envíos de formularios.

Si decide añadir la secuencia de comandos mediante GTM, configure el [!DNL Marketo Measure] a la prioridad más alta de su orden de activación y asegúrese de que no haya scripts sincrónicos delante del [!DNL Marketo Measure] para reducir los efectos de la latencia de la GTM.

>[!NOTE]
>
>Use esto [artículo de asistencia de Google](https://support.google.com/tagmanager/answer/2772421?hl=es){target="_blank"} para obtener más información.

## Cómo añadir el JS de [!DNL Marketo Measure] mediante [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. Abra GTM y añada [!DNL Marketo Measure] en el contenedor del sitio web. Asegúrese de seleccionar la **[!UICONTROL etiqueta HTML personalizada]**.

1. Utilice el script de [!DNL Marketo Measure] siguiente e inclúyalo en su contenedor.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Haga clic en **[!UICONTROL Añadir una regla de activación]** para que pueda indicarle a Google que cargue el fragmento en *Todas las páginas*.

1. Vaya a la sección Información general sobre el borrador del contenedor situada a la izquierda. Haga clic en el botón para crear una nueva versión del contenedor y publicar los cambios.
