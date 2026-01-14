---
description: Conectando [!DNL Marketo Measure] a las instrucciones de Unbounce Script Manager para usuarios de Marketo Measure
title: Conexión de  [!DNL Marketo Measure]  al administrador de scripts de cancelación de devoluciones
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 7%

---


# Conectando [!DNL Marketo Measure] al Administrador de scripts de devolución {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] se integra directamente con Unbounce, lo que le permite rastrear la fuente de marketing digital de las conversiones de su página de aterrizaje directamente en [!DNL Salesforce]. Para establecer la conexión, simplemente agregue el script [!DNL Marketo Measure] a su Administrador de scripts de devolución. Así es cómo se hace.

1. Inicie sesión en su cuenta de [!DNL Unbounce].
1. Haga clic en **[!UICONTROL Configuración]** > **[!UICONTROL Administrador de scripts]** > **[!UICONTROL Agregar script]**.
1. En la ventana emergente, seleccione [!UICONTROL Script personalizado] y asígnele el nombre &quot;[!DNL Marketo Measure Marketing Analytics]&quot;. Haga clic en **[!UICONTROL Agregar detalles del script]**.
1. Seleccione la ubicación en el encabezado. Incluya el script en la página de aterrizaje principal y el cuadro de diálogo de confirmación de formulario. Pegue el script [!DNL Marketo Measure] siguiente en el cuadro.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Haga clic en **[!UICONTROL Guardar]**.

La integración de [!DNL Marketo Measure] funciona en páginas de aterrizaje de devolución siempre y cuando estén alojadas en su dominio (por ejemplo, landing.mysite.com) y no en el dominio unbounce.com.
