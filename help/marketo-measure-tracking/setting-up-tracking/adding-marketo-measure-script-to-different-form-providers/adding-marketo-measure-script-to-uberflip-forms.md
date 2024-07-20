---
unique-page-id: 18874749
description: Agregando  [!DNL Marketo Measure] script a [!DNL Uberflip] Forms - [!DNL Marketo Measure]
title: Agregando  [!DNL Marketo Measure] script a [!DNL Uberflip] Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---

# Agregando script [!DNL Marketo Measure] a Forms [!DNL Uberflip] {#adding-marketo-measure-script-to-uberflip-forms}

Si actualmente usa [!DNL Uberflip] para administrar el contenido, es importante que realice los pasos necesarios para asegurarse de que [!DNL Marketo Measure] realiza un seguimiento de los envíos de formularios. El administrador de éxito de [!DNL Uberflip] también debe poder ayudarle con esto.

1. Agregue este script a la sección [!UICONTROL Código personalizado>HTML] de [!DNL Uberflip].

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. AJAX Asegúrese de que este código de preámbulo [!DNL Marketo Measure] se active tanto al cargar la página como al cambiar de página de la misma. Haga esto dentro de la sección [!UICONTROL Custom Code>JS]

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   Agregue este preámbulo a los vínculos de evento [!DNL Hubs.onLoad] y [!DNL Hubs.onPageChange] de JavaScript a continuación, en los enlaces de evento de AJAX de la. (Nota: Es posible que también tenga otro código en estos vínculos de eventos. Asegúrese de incluir también el preámbulo).

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. Cree y defina una función que dirija los datos a Bizible tras un envío de CTA de formulario. Esto va a la sección [!UICONTROL Código personalizado>JavaScript]. (Nota: Esta función solo requiere el parámetro ctaData que proporciona Uberflip, pero puede incluir los demás parámetros ctaId y ctaName en caso de que el usuario desee personalizar su código para pasar estos datos también).

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. Cuando se envíe un CTA de formulario, asegúrese de que la función [!DNL Marketo Measure] se ejecute de la siguiente manera. Esto se hace dentro de la sección [!UICONTROL Custom Code>JS]. (Nota: Es posible que tenga otro código dentro del vínculo de evento Hubs.onCtaFormSubmitSuccess de JavaScript; asegúrese de incluir también esta llamada de función).

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
