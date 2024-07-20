---
description: '[!DNL Marketo Measure] integraciones con el lanzamiento de Adobe - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] integraciones con Adobe Launch'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: 6aaf6fd26f19e9382cc559e54558e1c5d84cfd6d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 2%

---

# Integraciones de [!DNL Marketo Measure] con Adobe Launch {#marketo-measure-integrations-with-adobe-launch}

La extensión de Adobe Launch está diseñada para los usuarios de [!DNL Marketo Measure] existentes que ya usan Adobe Launch en su sitio web. La extensión sirve como solución de administración de etiquetas que puede utilizar para configurar y cargar dinámicamente scripts en sus páginas en función de determinados eventos y condiciones.

Cuando se instala y configura en Adobe Launch, la extensión [!DNL Marketo Measure] carga el script bizible.js en las páginas donde el script de Adobe Launch esté presente. Esto permite a los especialistas en marketing añadir bizible.js a través de la configuración de Launch del Adobe, en lugar de modificar explícitamente la página web para añadir la etiqueta de script bizible.js.

## Configuración de la extensión de Launch de Adobe {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>Consulte los siguientes vínculos para obtener más información sobre Adobe Launch y sus extensiones:
>
>* [[!DNL Marketo Measure] Extensión](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html#catalog){target="_blank"}
>* [Información general sobre el lanzamiento en Adobe](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html){target="_blank"}
>* [Información general sobre la extensión de Adobe Launch](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html){target="_blank"}

1. Cree una propiedad siguiendo los pasos [de este artículo](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html#go-to-the-data-collection-interface){target="_blank"}.

1. Haga clic en la propiedad que ha creado.

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. Haga clic en **[!UICONTROL Extensiones]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. Haz clic en la pestaña **[!UICONTROL Catálogo]** y busca &quot;[!UICONTROL Bizible]&quot;.

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. En el mosaico de [!UICONTROL Bizible Analytics], haga clic en **[!UICONTROL Instalar]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. En el campo Bizible AccountId, escriba la dirección URL del sitio web (por ejemplo, `adobe.com`).

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

1. Haga clic en **[!UICONTROL Guardar]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. Haga clic en **[!UICONTROL Reglas]** y luego seleccione **[!UICONTROL Crear nueva regla]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. Haga clic en el botón **[!UICONTROL Agregar]** en [!UICONTROL Eventos].

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. En la lista desplegable Extensión, seleccione **[!UICONTROL Principal]**. A continuación, en la lista desplegable Tipo de evento, seleccione **[!UICONTROL Biblioteca cargada (Principio de página)]**. Si no le asigna un nombre al evento, se aplica uno predeterminado. Haga clic en **[!UICONTROL Conservar cambios]** cuando haya terminado.

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. Haga clic en el botón **[!UICONTROL Agregar]** en Acciones.

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. En el menú desplegable Extensión, seleccione **[!UICONTROL Bizible Analytics]**. A continuación, en la lista desplegable Tipo de acción, seleccione **[!UICONTROL Inicializar]**. Si no asigna un nombre a la acción, se aplica uno predeterminado. Haga clic en **[!UICONTROL Conservar cambios]** cuando haya terminado.

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. Haga clic en **[!UICONTROL Guardar]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)

