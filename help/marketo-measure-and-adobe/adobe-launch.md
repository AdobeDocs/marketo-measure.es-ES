---
description: 'Integraciones de [!DNL Marketo Measure] con Adobe Launch:  [!DNL Marketo Measure]'
title: Integraciones de [!DNL Marketo Measure] con Adobe Launch
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 3%

---


# Integraciones de [!DNL Marketo Measure] con Adobe Launch {#marketo-measure-integrations}

La extensión de Adobe Launch está diseñada para los usuarios de [!DNL Marketo Measure] que ya usan Adobe Launch en su sitio web. La extensión sirve como solución de administración de etiquetas que puede utilizar para configurar y cargar dinámicamente scripts en sus páginas en función de determinados eventos y condiciones.

Cuando se instala y configura en Adobe Launch, la extensión [!DNL Marketo Measure] carga el script de bizible.js en las páginas donde el script de Adobe Launch esté presente. Esto permite a los especialistas en marketing añadir bizible.js a través de la configuración de Adobe Launch, en lugar de modificar explícitamente la página web para añadir la etiqueta de script bizible.js.

## Configuración de la extensión de Adobe Launch {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>Consulte los siguientes vínculos para obtener más información sobre Adobe Launch y sus extensiones:
> [[!DNL Marketo Measure] Extensión](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html#catalog){target="_blank"}
> [Información general de Adobe Launch](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html){target="_blank"}
> [Información general sobre la extensión Adobe Launch](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html){target="_blank"}

1. Cree una propiedad siguiendo los pasos [de este artículo](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html#go-to-the-data-collection-interface){target="_blank"}.

1. Haga clic en la propiedad que ha creado.

   ![Pantalla de selección de propiedades de Adobe Launch que muestra las propiedades disponibles](assets/marketo-measure-integrations-1.png)

1. Haga clic en **[!UICONTROL Extensiones]**.

   ![Pestaña Extensiones en la configuración de la propiedad de Adobe Launch](assets/marketo-measure-integrations-2.png)

1. Haz clic en la pestaña **[!UICONTROL Catálogo]** y busca &quot;[!UICONTROL Bizible]&quot;.

   ![Búsqueda en el catálogo de extensiones que muestra la extensión Bizible](assets/marketo-measure-integrations-3.png)

1. En el mosaico de [!UICONTROL Bizible Analytics], haga clic en **[!UICONTROL Instalar]**.

   ![Mosaico de extensión de Bizible Analytics con botón Instalar](assets/marketo-measure-integrations-4.png)

1. En el campo Bizible AccountId, escriba la dirección URL del sitio web (por ejemplo, `adobe.com`).

   ![Configuración de extensión Bizible con campo AccountId](assets/marketo-measure-integrations-5.png)

1. Haga clic en **[!UICONTROL Guardar]**.

   ![Botón Guardar para la configuración de la extensión de Bizible](assets/marketo-measure-integrations-6.png)

1. Haga clic en **[!UICONTROL Reglas]** y luego seleccione **[!UICONTROL Crear nueva regla]**.

   ![Ficha Reglas con el botón Crear nueva regla](assets/marketo-measure-integrations-7.png)

1. Haga clic en el botón **[!UICONTROL Agregar]** en [!UICONTROL Eventos].

   ![Botón Agregar en la sección Eventos de la configuración de regla](assets/marketo-measure-integrations-8.png)

1. En la lista desplegable Extensión, seleccione **[!UICONTROL Principal]**. A continuación, en la lista desplegable Tipo de evento, seleccione **[!UICONTROL Biblioteca cargada (Principio de página)]**. Si no le asigna un nombre al evento, se aplica uno predeterminado. Haga clic en **[!UICONTROL Conservar cambios]** cuando haya terminado.

   ![Cuadro de diálogo de configuración de evento con extensión principal y tipo de evento Library Loaded](assets/marketo-measure-integrations-9.png)

1. Haga clic en el botón **[!UICONTROL Agregar]** en Acciones.

   ![Botón Agregar en la sección Acciones de la configuración de regla](assets/marketo-measure-integrations-10.png)

1. En el menú desplegable Extensión, seleccione **[!UICONTROL Bizible Analytics]**. A continuación, en la lista desplegable Tipo de acción, seleccione **[!UICONTROL Inicializar]**. Si no asigna un nombre a la acción, se aplica uno predeterminado. Haga clic en **[!UICONTROL Conservar cambios]** cuando haya terminado.

   ![Cuadro de diálogo Configuración de acción con extensión de Bizible Analytics e Inicializar tipo de acción](assets/marketo-measure-integrations-11.png)

1. Haga clic en **[!UICONTROL Guardar]**.

   ![Botón Guardar para la configuración de regla](assets/marketo-measure-integrations-12.png)

