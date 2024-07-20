---
unique-page-id: 18874690
description: 'Volver a autorizar cuentas conectadas:  [!DNL Marketo Measure]'
title: Volver a autorizar cuentas conectadas
exl-id: 7abd1d67-5bed-45bb-844f-0ffd23c3d7f8
feature: APIs, Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 3%

---

# Volver a autorizar cuentas conectadas {#reauthorizing-connected-accounts}

Cuando una cuenta se desconecta de su cuenta de [!DNL Marketo Measure], el estado de la plataforma cambiará a &quot;Se requiere autorización&quot; y mostrará un icono de llave roja.

Si la plataforma de publicidad se desconecta, [!DNL Marketo Measure] no podrá descargar los datos de costos o, si tiene habilitado el etiquetado automático, anexará los parámetros de UTM [!DNL Marketo Measure] a los anuncios recién creados. [!DNL Marketo Measure] no podrá anexar de forma retroactiva los parámetros de UTM a ningún punto de contacto creado desde la plataforma de publicidad mientras se desconectó la cuenta.

Si la plataforma CRM se desconecta, [!DNL Marketo Measure] no podrá actualizar los datos de [!DNL Marketo Measure] ni insertar nuevos puntos de contacto en la organización. Una vez restablecida la conexión de CRM, [!DNL Marketo Measure] insertará los datos que se hayan perdido mientras se desconectaba la cuenta.

![](assets/1-1.png)

## Volver a autorizar cuentas desconectadas {#re-authorizing-disconnected-accounts}

1. Vaya a [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} e inicie sesión.
1. Seleccione **[!UICONTROL Configuración]** en la ficha [!UICONTROL Mi cuenta] de la esquina superior izquierda.
1. Busque la sección Integraciones a la izquierda y haga clic en **[!UICONTROL Conexiones]**.
1. Seleccione el símbolo de llave roja junto a la cuenta que debe volver a conectarse.
1. Aparecerá una ventana emergente, que le pedirá que proporcione los detalles de inicio de sesión de la cuenta.
