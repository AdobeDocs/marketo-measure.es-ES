---
description: Muestra cómo configurar bizible.js para que espere al consentimiento del usuario para el RGPD antes de configurar cookies o enviar datos
title: Garantizar el consentimiento para el RGPD en JS de Marketo Measure Js
exl-id: 9afc5e4d-cf97-4c49-b9ee-ee1cc99c1f90
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 95%

---

# Garantizar el consentimiento para el RGPD en JS de Marketo Measure Js {#ensuring-consent-for-gdpr-in-marketo-measure-js}

El Reglamento General de Protección de Datos (RGPD) es una legislación de la Unión Europea que entró en vigor el 25 de mayo de 2018.

## Información general {#overview}

El objetivo del RGPD es reforzar los derechos de las personas interesadas en la Unión Europea (UE) y el Espacio Económico Europeo (EEE) en relación con el uso y la protección de sus datos personales. Por &quot;datos personales&quot; se entiende toda información relacionada con una persona física identificada o identificable. El RGPD se aplica a cualquier organización dentro o fuera de la UE que comercialice bienes o servicios a interesados dentro de la UE y el EEA, o que realice un seguimiento de sus comportamientos. Si hace negocios con personas interesadas en Europa que supongan el procesamiento de sus datos personales, esta legislación se aplica a usted. Las sanciones por incumplimiento son significativas, con cuantiosas multas para los infractores de la normativa; la multa máxima por una sola infracción es de 20 millones de euros o el 4% de la facturación anual mundial, la cantidad que sea mayor.

De forma predeterminada, [!DNL bizible.js] recopila datos de análisis de los usuarios a menos que esté configurado para esperar el consentimiento. Cuándo [!DNL bizible.js] está configurado para esperar el consentimiento del usuario, no creará ninguna cookie ni enviará ningún dato analítico hasta que se alcance el consentimiento.

## Cómo esperar el consentimiento {#how-to-wait-for-consent}

Hay dos formas de configurar [!DNL bizible.js] para esperar el consentimiento.

Opción 1: reemplazar la etiqueta de script [!DNL bizible.js] predeterminada con:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

**Si utiliza [!DNL Google Tag Manager] para instalar el script**, tenga en cuenta que GTM elimina los atributos data-, por lo que debe utilizar la siguiente secuencia de comandos:

`<span id="bizible-settings" data-consent-button-id="ConsentButtonId"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>En este caso, [!DNL bizible.js] adjunta un evento en el que se hace clic al elemento HTML con el ID &quot;ConsentButtonId&quot;.

Cuando se hace clic en este elemento HTML, [!DNL bizible.js] crea una cookie para recordar que se ha recibido el consentimiento del usuario y empieza a recopilar datos de análisis de la forma habitual.

**-o-**

Opción 2: reemplace la etiqueta de script [!DNL bizible.js] predeterminada:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-requires-user-consent="true"></script>`

Esto indica a [!DNL bizible.js] que no rastree hasta que se alcance el consentimiento, lo que se puede hacer con la siguiente API de JS:

*window[&#39;Bizible&#39;] = window[&#39;Bizible&#39;] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };*

*Bizible.  Push(&#39;Consent&#39;, true);*

**Si utiliza [!DNL Google Tag Manager] para instalar el script**, tenga en cuenta que GTM elimina los atributos data-, por lo que debe utilizar la siguiente secuencia de comandos:

`<span id="bizible-settings" data-requires-user-consent="true"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>bizible.js crea una cookie para recordar que se ha recibido el consentimiento del usuario y empieza a recopilar datos de análisis de la forma habitual solo después de llamar a la API de JS.

Por el contrario, los clientes también pueden utilizar esta API para retirar el consentimiento del usuario:

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };`

`Bizible.Push('Consent', false);`

Cuando se ejecuta este código, elimina todas las cookies que [!DNL bizible.js] ha creado anteriormente y reanuda la recopilación de datos de análisis solo si el usuario vuelve a dar su consentimiento.
