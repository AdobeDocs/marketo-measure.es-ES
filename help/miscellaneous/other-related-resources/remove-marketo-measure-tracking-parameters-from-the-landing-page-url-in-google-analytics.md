---
unique-page-id: 18874736
description: 'Eliminar [!DNL Marketo Measure] Parámetros de seguimiento de la dirección URL de la página de aterrizaje en Google Analytics: [!DNL Marketo Measure] - Documentación del producto'
title: Eliminar [!DNL Marketo Measure] Seguimiento de parámetros desde la dirección URL de la página de aterrizaje en Google Analytics
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 0%

---

# Eliminar [!DNL Marketo Measure] Seguimiento de parámetros desde la dirección URL de la página de aterrizaje en Google Analytics {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

A veces al ver páginas de aterrizaje en [!DNL Google Analytics], deberá eliminar los parámetros de seguimiento de las direcciones URL. De lo contrario, se dividirán en filas individuales.

Afortunadamente, esta es una solución fácil.

1. En [!DNL Google Analytics], vaya a [!UICONTROL Administrador] >[!UICONTROL Configuración de vista] >[!UICONTROL Excluir parámetros de consulta de URL].
1. Escriba &quot;_bt,_bk,_bm,_bn,_bg&quot; en el cuadro (menos las comillas).
1. Desplácese hacia abajo y haga clic en **[!UICONTROL Guardar]**.

   Tenga en cuenta que [!DNL Google Analytics] no vuelve a procesar los datos. Por lo tanto, este cambio solo se reflejará a partir de ahora y los datos anteriores seguirán mostrándose con los parámetros bt, bk y bm.
