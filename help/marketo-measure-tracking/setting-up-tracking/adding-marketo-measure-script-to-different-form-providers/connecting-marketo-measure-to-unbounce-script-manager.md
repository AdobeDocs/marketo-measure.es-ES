---
unique-page-id: 18874743
description: Conectando [!DNL Marketo Measure] para anular la devolución del Administrador de scripts - [!DNL Marketo Measure] - Documentación del producto
title: Conexión de  [!DNL Marketo Measure]  al administrador de scripts de cancelación de devoluciones
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 8%

---

# Conexión de [!DNL Marketo Measure] al administrador de scripts de cancelación de devoluciones {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] se integra directamente con Unbounce, lo que le permite rastrear la fuente de marketing digital de las conversiones de su página de aterrizaje directamente en [!DNL Salesforce]. Para establecer la conexión, simplemente agregue [!DNL Marketo Measure] a su Administrador de scripts de devolución. Así es como.

1. Inicie sesión en su [!DNL Unbounce] cuenta.
1. Clic **[!UICONTROL Configuración]** > **[!UICONTROL Administrador de scripts]** > **[!UICONTROL Agregar script]**.
1. En la ventana emergente, seleccione [!UICONTROL Script personalizado] y asígnele el nombre &quot;[!DNL Marketo Measure Marketing Analytics].&quot; Clic **[!UICONTROL Añadir detalles del script]**.
1. Seleccione la ubicación en el encabezado. Incluya el script en la página de aterrizaje principal y el cuadro de diálogo de confirmación de formulario. Pegue el [!DNL Marketo Measure] escriba el script siguiente en el cuadro.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Clic **[!UICONTROL Guardar]**.

El [!DNL Marketo Measure] La integración de funciona en páginas de aterrizaje de Unbounce siempre y cuando estén alojadas en su dominio (por ejemplo, landing.mysite.com) y no en los que utilizan el dominio unbounce.com.
