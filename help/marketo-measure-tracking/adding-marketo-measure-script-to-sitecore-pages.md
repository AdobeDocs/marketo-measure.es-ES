---
description: Agregando script [!DNL Marketo Measure] a la guía de páginas de Sitecore para usuarios de Marketo Measure
title: Agregando script [!DNL Marketo Measure] a las páginas de SiteCore
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
feature: Tracking
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: dcbeff6e-0253-5a4b-9ac2-1b67cc4a6286
    internal-label: Tracking
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 0%
---
# Agregando script [!DNL Marketo Measure] a las páginas de SiteCore {#adding-marketo-measure-script-to-sitecore-pages}

Los sistemas de administración de contenido pueden requerir pasos adicionales más allá de la implementación de scripts estándar para [!DNL Marketo Measure] para reconocer los envíos de formularios. El proceso siguiente describe cómo agregar el javascript [!DNL Marketo Measure] a las páginas de [!DNL Sitecore].

Para sitios con páginas de Sitecore:

1. Inicie sesión en Sitecore y navegue hasta su sitio web. Busque la carpeta [!UICONTROL Configuration] que reside en el mismo nivel que su elemento [!UICONTROL Home] y la carpeta [!UICONTROL Metadata].
1. Haga clic en **[!UICONTROL +]** junto a la carpeta [!UICONTROL Configuración].
1. Haga clic en **[!UICONTROL +]** junto a la carpeta [!UICONTROL Herramientas].
1. Seleccione el elemento [!UICONTROL Javascript].
1. En la ficha [!UICONTROL Contenido], haga clic en el vínculo **[!UICONTROL Bloquear y editar]** para desbloquear el elemento y editarlo.
1. Busque la sección [!UICONTROL &#39;JavaScript&#39;]. Si aún no está expandido, haga clic en **[!UICONTROL +]**.
1. Escriba el script: `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. Haz clic en **[!UICONTROL Guardar]** en la esquina superior izquierda.
