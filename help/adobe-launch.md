---
description: '''[!DNL Marketo Measure] integraciones con Adobe Launch - [!DNL Marketo Measure]'''
title: Integraciones de [!DNL Marketo Measure] con Adobe Launch
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 6%

---

# Integraciones de [!DNL Marketo Measure] con Adobe Launch {#marketo-measure-integrations-with-adobe-launch}

La extensión de Adobe Launch está diseñada para los usuarios de [!DNL Marketo Measure] que ya usan Adobe Launch en su sitio web. La extensión sirve como solución de administración de etiquetas que puede utilizar para configurar y cargar dinámicamente scripts en sus páginas en función de determinados eventos y condiciones.

Cuando se instala y configura en Adobe Launch, la extensión [!DNL Marketo Measure] carga el script de bizible.js en las páginas donde el script de Adobe Launch esté presente. Esto permite a los especialistas en marketing añadir bizible.js a través de la configuración de Adobe Launch, en lugar de modificar explícitamente la página web para añadir la etiqueta de script bizible.js.

## Configuración de la extensión de Adobe Launch {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>Consulte los siguientes vínculos para obtener más información sobre Adobe Launch y sus extensiones:
>
>* [[!DNL Marketo Measure] Extensión](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html#catalog){target="_blank"}
>* [Información general sobre Adobe Launch](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html){target="_blank"}
>* [Información general sobre la extensión Adobe Launch](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html){target="_blank"}

1. Cree una propiedad siguiendo los pasos [de este artículo](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html#go-to-the-data-collection-interface){target="_blank"}.

1. Haga clic en la propiedad que ha creado.

   ![1. Haga clic en la propiedad que ha creado.](assets/marketo-launch-12.png)

1. Haga clic en **[!UICONTROL Extensiones]**.

   ![1. Haga clic en Extensiones.](assets/marketo-launch-11.png)

1. Haz clic en la pestaña **[!UICONTROL Catálogo]** y busca &quot;[!UICONTROL Bizible]&quot;.

   ![1. Haga clic en la ficha Catálogo y busque &quot;Bizible&quot;.](assets/marketo-launch-10.png)

1. En el mosaico de [!UICONTROL Bizible Analytics], haga clic en **[!UICONTROL Instalar]**.

   ![1. En el mosaico de Bizible Analytics, haga clic en Instalar.](assets/marketo-launch-7.png)

1. En el campo Bizible AccountId, escriba la dirección URL del sitio web (por ejemplo, `adobe.com`).

   ![1. En el campo Bizible AccountId, escriba la dirección URL de su](assets/marketo-launch-6.png)

1. Haga clic en **[!UICONTROL Guardar]**.

   ![1. Haga clic en Guardar.](assets/marketo-launch-8.png)

1. Haga clic en **[!UICONTROL Reglas]** y luego seleccione **[!UICONTROL Crear nueva regla]**.

   ![1. Haga clic en Reglas y seleccione Crear nueva regla.](assets/marketo-launch-9.png)

1. Haga clic en el botón **[!UICONTROL Agregar]** en [!UICONTROL Eventos].

   ![1. Haga clic en el botón Agregar en Eventos.](assets/marketo-launch-2.png)

1. En la lista desplegable Extensión, seleccione **[!UICONTROL Principal]**. A continuación, en la lista desplegable Tipo de evento, seleccione **[!UICONTROL Biblioteca cargada (Principio de página)]**. Si no le asigna un nombre al evento, se aplica uno predeterminado. Haga clic en **[!UICONTROL Conservar cambios]** cuando haya terminado.

   ![1. En la lista desplegable Extensión, seleccione Principal. Luego, en el evento &#x200B;](assets/marketo-launch-1.png)

1. Haga clic en el botón **[!UICONTROL Agregar]** en Acciones.

   ![1. Haga clic en el botón Agregar en Acciones.](assets/marketo-launch-3.png)

1. En el menú desplegable Extensión, seleccione **[!UICONTROL Bizible Analytics]**. A continuación, en la lista desplegable Tipo de acción, seleccione **[!UICONTROL Inicializar]**. Si no asigna un nombre a la acción, se aplica uno predeterminado. Haga clic en **[!UICONTROL Conservar cambios]** cuando haya terminado.

   ![1. En el menú desplegable Extensión, seleccione Bizible Analytics. Luego, en la acción &#x200B;](assets/marketo-launch-4.png)

1. Haga clic en **[!UICONTROL Guardar]**.

   ![1. Haga clic en Guardar.](assets/marketo-launch-5.png)

