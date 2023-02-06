---
unique-page-id: 18874797
description: Adición [!DNL Marketo Measure] Secuencia de comandos mediante [!DNL Google Tag Manager] - [!DNL Marketo Measure] - Documentación del producto
title: Adición [!DNL Marketo Measure] Secuencia de comandos mediante [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Adición [!DNL Marketo Measure] Secuencia de comandos mediante [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

Al instalar el [!DNL Marketo Measure] javascript, recomendamos encarecidamente [codificar el script de forma rígida](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"} directamente en el sitio. Sin embargo, si esto no es posible, también puede usar [!DNL Google Tag Manager] (GTM) para cargar el [!DNL Marketo Measure] JS. Tenga en cuenta que [!DNL Marketo Measure] El JS cargado a través de GTM es susceptible a latencia. La latencia provoca un retraso en los tiempos de carga de las secuencias de comandos, lo que puede provocar que falte entre el 3% y el 5% de todos los envíos de formularios.

Si decide añadir nuestro script a través de GTM, establezca la variable [!DNL Marketo Measure] a la prioridad más alta en el orden de activación y asegúrese de que no hay scripts sincrónicos delante del [!DNL Marketo Measure] para reducir cualquier efecto de la latencia de GTM.

>[!NOTE]
>
>Utilice esta [artículo de asistencia técnica de Google](https://support.google.com/tagmanager/answer/2772421?hl=en){target="_blank"} para obtener más información.

## Cómo añadir [!DNL Marketo Measure] JS a través de [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. Abra GTM y añada la variable [!DNL Marketo Measure] en el contenedor de su sitio web. Asegúrese de seleccionar **[!UICONTROL Etiqueta HTML personalizada]**.

1. Utilice la variable [!DNL Marketo Measure] a continuación e inclúyalo en su contenedor.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Haga clic en **[!UICONTROL Agregar una regla de activación]** para que pueda indicar a Google que cargue nuestro fragmento en *Todas las páginas*.

1. Vaya a la sección Información general del borrador del contenedor a la izquierda. Haga clic en el botón para crear una nueva versión del contenedor y publicar los cambios.
