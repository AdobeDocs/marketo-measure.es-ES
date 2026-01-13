---
description: Eliminar parámetros de seguimiento de  [!DNL Marketo Measure]  de la dirección URL de la página de destino en Google Analytics
title: Eliminar parámetros de seguimiento de  [!DNL Marketo Measure]  de la dirección URL de la página de destino en Google Analytics
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 19%

---


# Eliminar [!DNL Marketo Measure] parámetros de seguimiento de la dirección URL de la página de aterrizaje en Google Analytics {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

A veces, cuando visualice páginas de aterrizaje en [!DNL Google Analytics], querrá quitar los parámetros de seguimiento de las direcciones URL. De lo contrario, se dividirán en filas individuales.

Afortunadamente, esta es una solución fácil.

1. En [!DNL Google Analytics], vaya a [!UICONTROL Administración] >[!UICONTROL Ver configuración] >[!UICONTROL Excluir parámetros de consulta de URL].
1. Escriba &quot;_bt,_bk,_bm,_bn,_bg&quot; en el cuadro (menos las comillas).
1. Desplácese hacia abajo y haga clic en **[!UICONTROL Guardar]**.

   Tenga en cuenta que [!DNL Google Analytics] no vuelve a procesar los datos. Por lo tanto, este cambio solo se reflejará en adelante y los datos anteriores se seguirán mostrando con los parámetros bt, bk y bm.
