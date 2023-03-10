---
description: '''[!DNL Marketo Measure] Integraciones con Adobe Launch: [!DNL Marketo Measure] - Documentación del producto'
title: '[!DNL Marketo Measure] Integraciones con Adobe Launch'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
source-git-commit: 19f670505358b04fb26620574b71c2af8d0d9847
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---

# [!DNL Marketo Measure] Integraciones con Adobe Launch {#marketo-measure-integrations-with-adobe-launch}

La extensión de Launch de Adobe está diseñada para [!DNL Marketo Measure] usuarios que ya aprovechan Adobe Launch en su sitio web. La extensión sirve como solución de administración de etiquetas que puede utilizar para configurar y cargar dinámicamente scripts en las páginas en función de ciertos eventos y condiciones.

Cuando se instala y configura en Adobe Launch, la variable [!DNL Marketo Measure] la extensión cargará el script bizible.js en las páginas donde esté presente el script de Adobe Launch. Esto permite a los especialistas en marketing añadir bizible.js a través de la configuración de Launch de Adobe, en lugar de modificar explícitamente la página web para añadir la etiqueta de script bizible.js.

## Configuración de la extensión de Launch de Adobe {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>Consulte los siguientes vínculos para obtener más información sobre Adobe Launch y sus extensiones:
>
>* [[!DNL Marketo Measure] Extensión](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html?lang=en#catalog){target="_blank"}
>* [Información general sobre Launch de Adobe](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/index.html?lang=en#prerequisites){target="_blank"}
>* [Información general sobre la extensión de Launch de Adobe](https://experienceleague.adobe.com/docs/launch/using/extension-dev/overview.html?lang=en#extension-configuration){target="_blank"}


1. Cree una propiedad siguiendo los pasos [en este artículo](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html?lang=en#go-to-the-data-collection-interface){target="_blank"}.

1. Haga clic en la propiedad que acaba de crear.

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. Haga clic en **[!UICONTROL Extensiones]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. Haga clic en el **[!UICONTROL Catálogo]** y busque &quot;[!UICONTROL Bizible].&quot;

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. En el [!UICONTROL Bizible Analytics] mosaico, haga clic en **[!UICONTROL Instalar]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. En el campo AccountId de Bizible, escriba la dirección URL de su sitio web.

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

   >[!NOTE]
   >
   >Este campo no es el &quot;ID de cuenta&quot; en la tabla Business_Prod.Business. Todas las actividades web de la URL dada se asignarán al [!DNL Marketo Measure] inquilino.

1. Haga clic en **[!UICONTROL Guardar]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. Haga clic en **[!UICONTROL Reglas]** y, a continuación, seleccione **[!UICONTROL Crear nueva regla]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. Haga clic en el **[!UICONTROL Agregar]** botón debajo de [!UICONTROL Eventos].

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. En la lista desplegable Extensión , seleccione **[!UICONTROL Principal]**. A continuación, en la lista desplegable Tipo de evento , seleccione **[!UICONTROL Biblioteca cargada (Principio de página)]**. Si no asigna un nombre al evento, se aplicará uno predeterminado. Haga clic en **[!UICONTROL Conservar cambios]** cuando haya terminado.

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. Haga clic en el **[!UICONTROL Agregar]** en Acciones.

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. En la lista desplegable Extensión , seleccione **[!UICONTROL Bizible Analytics]**. A continuación, en la lista desplegable Tipo de acción , seleccione **[!UICONTROL Inicializar]**. Si no asigna un nombre a la acción, se aplicará uno predeterminado. Haga clic en **[!UICONTROL Conservar cambios]** cuando haya terminado.

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. Haga clic en **[!UICONTROL Guardar]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)
