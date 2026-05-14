---
unique-page-id: 18874747
description: Agregando  [!DNL Marketo Measure] script a las páginas de Sitecore - [!DNL Marketo Measure]
title: Adición del script de  [!DNL Marketo Measure]  a páginas de Sitecore
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
feature: Tracking
TQID: https://experienceleague.adobe.com/sXO-rCY3NbxX0AztYt-o3f-tpJFlrncLIb7-NvEjZO0
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 126
ht-degree: 3%

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
