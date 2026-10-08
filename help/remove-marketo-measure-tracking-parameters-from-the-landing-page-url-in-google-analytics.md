---
description: Elimine [!DNL Marketo Measure] parámetros de seguimiento de la dirección URL de la página de aterrizaje en las directrices de Google Analytics para usuarios de Marketo Measure
title: Eliminar [!DNL Marketo Measure] parámetros de seguimiento de la dirección URL de la página de aterrizaje en Google Analytics
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
feature: Tracking
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: dcbeff6e-0253-5a4b-9ac2-1b67cc4a6286
    internal-label: Tracking
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%
---
# Eliminar [!DNL Marketo Measure] parámetros de seguimiento de la dirección URL de la página de aterrizaje en Google Analytics {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

A veces, cuando visualice páginas de aterrizaje en [!DNL Google Analytics], querrá quitar los parámetros de seguimiento de las direcciones URL. De lo contrario, se dividirán en filas individuales.

Afortunadamente, esta es una solución fácil.

1. En [!DNL Google Analytics], vaya a [!UICONTROL Administración] >[!UICONTROL Ver configuración] >[!UICONTROL Excluir parámetros de consulta de URL].
1. Escriba &quot;_bt,_bk,_bm,_bn,_bg&quot; en el cuadro (menos las comillas).
1. Desplácese hacia abajo y haga clic en **[!UICONTROL Guardar]**.

   Tenga en cuenta que [!DNL Google Analytics] no vuelve a procesar los datos. Por lo tanto, este cambio solo se reflejará en adelante y los datos anteriores se seguirán mostrando con los parámetros bt, bk y bm.
