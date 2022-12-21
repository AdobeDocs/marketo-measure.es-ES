---
unique-page-id: 18874743
description: Conexión [!DNL Marketo Measure] a Administrador de scripts de cancelación de devoluciones - [!DNL Marketo Measure] - Documentación del producto
title: Conexión [!DNL Marketo Measure] al Administrador de scripts de cancelación de devoluciones
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---

# Conexión [!DNL Marketo Measure] al Administrador de scripts de cancelación de devoluciones {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] se integra directamente con Unbounce, lo que le permite rastrear la fuente de marketing digital de las conversiones de su página de aterrizaje directamente en [!DNL Salesforce]. Para establecer la conexión, simplemente agregue la variable [!DNL Marketo Measure] a su Administrador de scripts de rechazo. Así es como.

1. Inicie sesión en su [!DNL Unbounce] cuenta.
1. Haga clic en **[!UICONTROL Configuración]** > **[!UICONTROL Administrador de secuencias de comandos]** > **[!UICONTROL Agregar secuencia de comandos]**.
1. En la ventana emergente, seleccione [!UICONTROL Script personalizado] y asígnele el nombre &quot;[!DNL Marketo Measure Marketing Analytics].&quot; Haga clic en **[!UICONTROL Agregar detalles de secuencia de comandos]**.
1. Seleccione la colocación en el encabezado. Incluya la secuencia de comandos en la página de aterrizaje principal y en el cuadro de diálogo de confirmación de formulario. Pegue el [!DNL Marketo Measure] en el cuadro.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Haga clic en **[!UICONTROL Guardar]**.

La variable [!DNL Marketo Measure] la integración funciona en las páginas de aterrizaje de Unbounce siempre que estén alojadas en su dominio (por ejemplo, landing.mysite.com) no en las que utilizan el dominio unbounce.com .
