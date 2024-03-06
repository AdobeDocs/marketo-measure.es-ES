---
description: '[!DNL Marketo Measure] Integraciones con Adobe Launch: [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Integraciones con Adobe Launch'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 2%

---

# Integraciones de [!DNL Marketo Measure] con Adobe Launch {#marketo-measure-integrations-with-adobe-launch}

La extensión de Adobe Launch está diseñada para [!DNL Marketo Measure] usuarios que ya utilizan Adobe Launch en su sitio web. La extensión sirve como solución de administración de etiquetas que puede utilizar para configurar y cargar dinámicamente scripts en sus páginas en función de determinados eventos y condiciones.

Cuando se instala y configura en Adobe Launch, la variable [!DNL Marketo Measure] La extensión de carga el script bizible.js en las páginas donde el script de Launch de Adobe esté presente. Esto permite a los especialistas en marketing añadir bizible.js a través de la configuración de Launch del Adobe, en lugar de modificar explícitamente la página web para añadir la etiqueta de script bizible.js.

## Configuración de la extensión de Launch de Adobe {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>Consulte los siguientes vínculos para obtener más información sobre Adobe Launch y sus extensiones:
>
>* [[!DNL Marketo Measure] Extensión](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html#catalog){target="_blank"}
>* [Información general sobre Adobe Launch](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html){target="_blank"}
>* [Información general sobre la extensión Adobe Launch](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html){target="_blank"}

1. Cree una propiedad siguiendo los pasos [en este artículo](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html#go-to-the-data-collection-interface){target="_blank"}.

1. Haga clic en la propiedad que ha creado.

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. Clic **[!UICONTROL Extensiones]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. Haga clic en **[!UICONTROL Catálogo]** y busque &quot;.[!UICONTROL Bizible].&quot;

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. En el [!UICONTROL Bizible Analytics] mosaico, haga clic en **[!UICONTROL Instalar]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. En el campo Bizible AccountId, escriba la dirección URL del sitio web (por ejemplo, `adobe.com`).

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

   >[!NOTE]
   >
   >Este campo no es el &quot;ID de cuenta&quot; en la tabla Business_Prod.Business. Todas las actividades web desde la URL determinada (por ejemplo, `adobe.com`) se asignan al [!DNL Marketo Measure] inquilino.

1. Haga clic en **[!UICONTROL Guardar]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. Clic **[!UICONTROL Reglas]**, luego seleccione **[!UICONTROL Crear nueva regla]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. Haga clic en **[!UICONTROL Añadir]** botón debajo de [!UICONTROL Eventos].

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. En la lista desplegable Extensión, seleccione **[!UICONTROL Núcleo]**. A continuación, en la lista desplegable Tipo de evento, seleccione **[!UICONTROL Library Loaded (Page Top)]**. Si no le asigna un nombre al evento, se aplica uno predeterminado. Clic **[!UICONTROL Conservar cambios]** cuando termine.

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. Haga clic en **[!UICONTROL Añadir]** en Acciones.

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. En la lista desplegable Extensión, seleccione **[!UICONTROL Bizible Analytics]**. A continuación, en la lista desplegable Tipo de acción, seleccione **[!UICONTROL Inicializar]**. Si no asigna un nombre a la acción, se aplica uno predeterminado. Clic **[!UICONTROL Conservar cambios]** cuando termine.

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. Haga clic en **[!UICONTROL Guardar]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)
