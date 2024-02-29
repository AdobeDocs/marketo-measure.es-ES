---
unique-page-id: 18874690
description: 'Reautorización de cuentas conectadas: [!DNL Marketo Measure]'
title: Volver a autorizar cuentas conectadas
exl-id: 7abd1d67-5bed-45bb-844f-0ffd23c3d7f8
feature: APIs, Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 3%

---

# Volver a autorizar cuentas conectadas {#reauthorizing-connected-accounts}

Cuando una cuenta se desconecte de su [!DNL Marketo Measure] , el estado de la plataforma cambiará a &quot;Se requiere autorización&quot; y mostrará un icono de llave roja.

Si la plataforma de publicidad se desconecta, [!DNL Marketo Measure] no podrá descargar los datos de costes o, si tiene habilitado el etiquetado automático, adjunte el [!DNL Marketo Measure] Parámetros de UTM para cualquier anuncio recién creado. [!DNL Marketo Measure] no podrá anexar de forma retroactiva los parámetros de UTM a ningún punto de contacto creado desde la plataforma de publicidad mientras la cuenta estaba desconectada.

Si la plataforma CRM se desconecta, [!DNL Marketo Measure] no será capaz de actualizar [!DNL Marketo Measure] o inserte nuevos puntos de contacto en su organización. Una vez restablecida la conexión CRM, [!DNL Marketo Measure] insertará los datos que se hayan omitido mientras se desconectaba la cuenta.

![](assets/1-1.png)

## Volver a autorizar cuentas desconectadas {#re-authorizing-disconnected-accounts}

1. Ir a [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} e inicie sesión.
1. Seleccionar **[!UICONTROL Configuración]** en el [!UICONTROL Mi cuenta] en la esquina superior izquierda.
1. Busque la sección Integraciones a la izquierda y haga clic en **[!UICONTROL Conexiones]**.
1. Seleccione el símbolo de llave roja junto a la cuenta que debe volver a conectarse.
1. Aparecerá una ventana emergente, que le pedirá que proporcione los detalles de inicio de sesión de la cuenta.
