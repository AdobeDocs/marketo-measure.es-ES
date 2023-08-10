---
unique-page-id: 18874797
description: Agregando [!DNL Marketo Measure] Script mediante [!DNL Google Tag Manager] - [!DNL Marketo Measure] - Documentación del producto
title: Agregando [!DNL Marketo Measure] Script mediante [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Agregando [!DNL Marketo Measure] Script mediante [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

Al instalar el [!DNL Marketo Measure] javascript, recomendamos encarecidamente [codificación del script](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"} directamente en el sitio. Sin embargo, si no es posible, también puede utilizar [!DNL Google Tag Manager] (GTM) para cargar [!DNL Marketo Measure] JS. Tenga en cuenta que [!DNL Marketo Measure] El JS cargado a través de GTM es susceptible a la latencia. La latencia causa un retraso en los tiempos de carga de las secuencias de comandos que puede resultar en la pérdida de alrededor del 3-5 % de todos los envíos de formularios.

Si decide añadir nuestra secuencia de comandos a través de GTM, configure el [!DNL Marketo Measure] a la prioridad más alta de su orden de activación y asegúrese de que no haya scripts sincrónicos delante del [!DNL Marketo Measure] para reducir los efectos de la latencia de la GTM.

>[!NOTE]
>
>Utilice esto [artículo de asistencia de Google](https://support.google.com/tagmanager/answer/2772421?hl=en){target="_blank"} para obtener más información.

## Cómo agregar [!DNL Marketo Measure] JS mediante [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. Abra GTM y añada [!DNL Marketo Measure] en el contenedor del sitio web. Asegúrese de seleccionar **[!UICONTROL Etiqueta de HTML personalizada]**.

1. Utilice el [!DNL Marketo Measure] escriba la siguiente secuencia de comandos e inclúyala en su contenedor.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Clic **[!UICONTROL Añadir una regla de activación]** para que pueda indicarle a Google que cargue el fragmento en *Todas las páginas*.

1. Vaya a la sección Información general sobre el borrador del contenedor de la izquierda. Haga clic en el botón para crear una nueva versión del contenedor y publicar los cambios.
