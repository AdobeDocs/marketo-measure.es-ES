---
unique-page-id: 35586069
description: 'Garantizar el consentimiento del RGPD en Marketo Measure Js: Marketo Measure, documentación del producto'
title: Garantizar el consentimiento del RGPD en Marketo Measure JS
exl-id: 9afc5e4d-cf97-4c49-b9ee-ee1cc99c1f90
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Garantizar el consentimiento del RGPD en Marketo Measure JS {#ensuring-consent-for-gdpr-in-marketo-measure-js}

El Reglamento General de Protección de Datos (RGPD) es una legislación de la Unión Europea que entró en vigor el 25 de mayo de 2018.

## Información general {#overview}

El objetivo del RGPD es reforzar los derechos de los interesados en la Unión Europea (UE) y el Espacio Económico Europeo (EEE) en lo que respecta a la forma en que se utilizan y protegen sus datos personales. Por &quot;datos personales&quot; se entiende toda información relacionada con una persona física identificada o identificable. El RGPD se aplica a cualquier organización dentro o fuera de la UE que comercialice bienes o servicios a interesados dentro de la UE y el EEE, o que realice un seguimiento de sus comportamientos. Si realiza negocios con interesados en Europa que impliquen el procesamiento de sus datos personales, esta legislación se aplica a usted. Las sanciones por incumplimiento son significativas, con grandes multas para aquellos que incumplan la normativa; la multa máxima por una sola infracción es de 20 millones de euros o el 4% de la facturación anual mundial, lo que sea bueno.

De forma predeterminada, [!DNL bizible.js] recopila datos de análisis de los usuarios a menos que esté configurado específicamente para esperar el consentimiento. Cuándo [!DNL bizible.js] está configurado para esperar el consentimiento del usuario, no creará cookies ni enviará datos de análisis hasta que se alcance el consentimiento.

## Cómo esperar el consentimiento {#how-to-wait-for-consent}

Hay dos formas de configurar [!DNL bizible.js] para esperar el consentimiento.

Opción 1: reemplazar el valor predeterminado [!DNL bizible.js] etiqueta de script con:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

**Si utiliza [!DNL Google Tag Manager] para instalar el script** Sin embargo, tenga en cuenta que GTM elimina los atributos data-, por lo que debe utilizar la siguiente secuencia de comandos:

`<span id="bizible-settings" data-consent-button-id="ConsentButtonId"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>En este caso, [!DNL bizible.js] adjuntará un evento en el que se hace clic al elemento HTML con el ID &quot;ConsentButtonId&quot;.

Cuando se hace clic en este elemento HTML, [!DNL bizible.js] creará una cookie para recordar que se ha recibido el consentimiento del usuario y empezará a recopilar los datos de analytics como de costumbre.

**-o-**

Opción 2: reemplazar la predeterminada [!DNL bizible.js] etiqueta de script con:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-requires-user-consent="true"></script>`

Esto indica [!DNL bizible.js] para no rastrear hasta que se alcance el consentimiento, lo cual se puede hacer con la siguiente API de JS:

*ventana[&#39;Bizible&#39;] = window[&#39;Bizible&#39;] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };*

*Bizible.Push(&#39;Consent&#39;, true);*

**Si utiliza [!DNL Google Tag Manager] para instalar el script** Sin embargo, tenga en cuenta que GTM elimina los atributos data-, por lo que debe utilizar la siguiente secuencia de comandos:

`<span id="bizible-settings" data-requires-user-consent="true"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>bizible.js creará una cookie para recordar que se ha recibido el consentimiento del usuario y comenzará a recopilar datos de análisis de la forma habitual solo después de llamar a la API de JS.

Por el contrario, los clientes también pueden utilizar esta API para retirar el consentimiento del usuario:

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };`

`Bizible.Push('Consent', false);`

Cuando se ejecute este código, eliminará todas las cookies que [!DNL bizible.js] creado anteriormente y que reanudará la recopilación de datos de analytics solo si el usuario vuelve a dar su consentimiento.
