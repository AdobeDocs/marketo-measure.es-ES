---
unique-page-id: 18874747
description: Agregando [!DNL Marketo Measure] Script para páginas de Sitecore - [!DNL Marketo Measure]
title: Adición del script de  [!DNL Marketo Measure]  a páginas de Sitecore
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 3%

---

# Agregando [!DNL Marketo Measure] Script a páginas de Sitecore {#adding-marketo-measure-script-to-sitecore-pages}

Los sistemas de administración de contenido pueden requerir pasos adicionales más allá de la implementación de scripts estándar para [!DNL Marketo Measure] para reconocer los envíos de formularios. El siguiente proceso describe cómo añadir los [!DNL Marketo Measure] javascript a su [!DNL Sitecore] páginas.

Para sitios con páginas de Sitecore:

1. Inicie sesión en Sitecore y navegue hasta su sitio web. Busque el [!UICONTROL Configuración] que reside en el mismo nivel que su [!UICONTROL Inicio] elemento y [!UICONTROL Metadatos] carpeta.
1. Haga clic en **[!UICONTROL +]** junto al [!UICONTROL Configuración] carpeta.
1. Haga clic en **[!UICONTROL +]** junto al [!UICONTROL Herramientas] carpeta.
1. Seleccione el [!UICONTROL Javascript] elemento.
1. En el [!UICONTROL Contenido] , haga clic en **[!UICONTROL Bloquear y editar]** para desbloquear el elemento y editarlo.
1. Busque el [!UICONTROL &#39;JavaScript&#39;] sección. Si aún no está expandido, haga clic en el icono **[!UICONTROL +]**.
1. Introduzca el script: `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. Clic **[!UICONTROL Guardar]** en la esquina superior izquierda.
