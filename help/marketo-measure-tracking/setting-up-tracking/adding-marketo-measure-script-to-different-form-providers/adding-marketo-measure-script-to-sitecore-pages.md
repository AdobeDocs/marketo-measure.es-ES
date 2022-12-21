---
unique-page-id: 18874747
description: Adición [!DNL Marketo Measure] Secuencia de comandos para páginas de SiteCatalyst - [!DNL Marketo Measure] - Documentación del producto
title: Adición [!DNL Marketo Measure] Secuencia de comandos para páginas de SiteCatalyst
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 0%

---

# Adición [!DNL Marketo Measure] Secuencia de comandos para páginas de SiteCatalyst {#adding-marketo-measure-script-to-sitecore-pages}

Los sistemas de administración de contenido pueden requerir pasos adicionales más allá de la implementación de scripts estándar para [!DNL Marketo Measure] para reconocer los envíos de formularios. El proceso siguiente describe cómo agregar la variable [!DNL Marketo Measure] javascript a su [!DNL Sitecore] páginas.

Para sitios con páginas de SiteCatalyst :

1. Inicie sesión en SiteCatalyst y navegue hasta su sitio web. Busque la variable [!UICONTROL Configuración] carpeta que reside en el mismo nivel que su [!UICONTROL Página principal] elemento y [!UICONTROL Metadatos] carpeta.
1. Haga clic en el **[!UICONTROL +]** junto a la variable [!UICONTROL Configuración] carpeta.
1. Haga clic en el **[!UICONTROL +]** junto a la variable [!UICONTROL Herramientas] carpeta.
1. Seleccione el [!UICONTROL Javascript] elemento.
1. En el [!UICONTROL Contenido] , haga clic en la pestaña **[!UICONTROL Bloquear y editar]** para desbloquear el elemento y editarlo.
1. Busque la [!UICONTROL &quot;JavaScript&quot;] para obtener más información. Si aún no está expandido, haga clic en el botón **[!UICONTROL +]**.
1. Introduzca nuestro script: `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. Haga clic en **[!UICONTROL Guardar]** en la esquina superior izquierda.
