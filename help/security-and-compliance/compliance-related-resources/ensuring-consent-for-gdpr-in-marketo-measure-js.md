---
unique-page-id: 35586069
description: Garantizar el consentimiento para el RGPD en Marketo Measure Js - Marketo Measure - Product Documentation
title: Garantizar el consentimiento para el RGPD en la Medida Js de Marketo
exl-id: 9afc5e4d-cf97-4c49-b9ee-ee1cc99c1f90
source-git-commit: c7d3bbce1f0c6a99409822c06c43961c93cd9458
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Garantizar el consentimiento para el RGPD en la Medida Js de Marketo {#ensuring-consent-for-gdpr-in-marketo-measure-js}

El Reglamento General de Protección de Datos (RGPD) es una legislación de la Unión Europea que entró en vigor el 25 de mayo de 2018.

## Resumen {#overview}

El objetivo del RGPD es reforzar los derechos de los interesados dentro de la Unión Europea (UE) y del Espacio Económico Europeo (EEE) con respecto a la forma en que se utilizan y protegen sus datos personales. Por &quot;datos personales&quot; se entiende toda información relacionada con una persona física identificada o identificable. El RGPD se aplica a cualquier organización dentro o fuera de la UE que comercialice bienes o servicios con sujetos de datos de la UE y del EEE o que realice un seguimiento de sus comportamientos. Si usted hace negocios con sujetos de datos en Europa que involucren el procesamiento de sus datos personales, esta legislación se aplica a usted. Las sanciones por incumplimiento son importantes, con grandes multas para quienes incumplan el reglamento; la multa máxima por una sola infracción es de €20 millones o el 4% del volumen de negocios anual a nivel mundial, lo que sea bueno.

De forma predeterminada, [!DNL bizible.js] recopila datos de análisis de los usuarios a menos que esté configurado específicamente para esperar el consentimiento. When [!DNL bizible.js] está configurado para esperar al consentimiento del usuario, no creará cookies ni enviará datos de análisis hasta que se alcance el consentimiento.

## Espera del consentimiento {#how-to-wait-for-consent}

Existen dos formas de configurar [!DNL bizible.js] para esperar el consentimiento.

Opción 1: Reemplazar el valor predeterminado [!DNL bizible.js] etiqueta de script con:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

**Si usa [!DNL Google Tag Manager] para instalar script**, tenga en cuenta que GTM elimina los atributos de datos, por lo que debe utilizar el siguiente script en su lugar:

`<span id="bizible-settings" data-consent-button-id="ConsentButtonId"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>En este caso, [!DNL bizible.js] adjuntará un evento en el que se hace clic al elemento HTML con el id &quot;ConsentButtonId&quot;.

Cuando se hace clic en este elemento de HTML, [!DNL bizible.js] creará una cookie para recordar que se ha recibido el consentimiento del usuario y empezar a recopilar los datos de análisis de la forma habitual.

**-o-**

Opción 2: Reemplazar el valor predeterminado [!DNL bizible.js] etiqueta de script con:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-requires-user-consent="true"></script>`

Esto indica que [!DNL bizible.js] para no rastrear hasta que se alcance el consentimiento, lo que se puede hacer con la siguiente API de JS:

*window[&#39;Bizible&#39;] = window[&#39;Bizible&#39;] || { _queue: [], push: función (o, p) { this._queue.push({ tipo: o, datos: p }); } };*

*Bizible.Push(&#39;Consent&#39;, true);*

**Si usa [!DNL Google Tag Manager] para instalar script**, tenga en cuenta que GTM elimina los atributos de datos, por lo que debe utilizar el siguiente script en su lugar:

`<span id="bizible-settings" data-requires-user-consent="true"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>bizible.js creará una cookie para recordar que se ha recibido el consentimiento del usuario y empezará a recopilar datos de análisis como de costumbre solo después de llamar a la API de JS.

Por el contrario, los clientes también pueden utilizar esta API para retirar el consentimiento del usuario:

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };`

`Bizible.Push('Consent', false);`

Cuando se ejecute este código, se eliminarán todas las cookies que [!DNL bizible.js] creado anteriormente y reanudará la recopilación de datos de analytics solo si el usuario vuelve a consentir.
