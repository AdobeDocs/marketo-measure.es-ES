---
unique-page-id: 18874749
description: Agregando [!DNL Marketo Measure] Script a [!DNL Uberflip] FORMS - [!DNL Marketo Measure]
title: Agregando [!DNL Marketo Measure] Script a [!DNL Uberflip] Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---

# Agregando [!DNL Marketo Measure] Script a [!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

Si está utilizando [!DNL Uberflip] para administrar el contenido, es importante que siga estos pasos necesarios para asegurarse de que [!DNL Marketo Measure] está realizando un seguimiento de esos envíos de formularios. Su gestor de éxito en [!DNL Uberflip] También debería poder ayudarle con esto.

1. Agregar este script a [!DNL Uberflip]de [!UICONTROL Custom Code>HTML] sección.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Asegúrese de esto [!DNL Marketo Measure] AJAX el código de preámbulo se activa tanto al cargar la página como al cambiar de página de la. Haga esto dentro de la [!UICONTROL Custom Code>JS] sección

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   Añada este preámbulo tanto a la variable [!DNL Hubs.onLoad] y el [!DNL Hubs.onPageChange] AJAX A continuación, se muestran los enlaces de eventos JavaScript para la. (Nota: Es posible que también tenga otro código en estos vínculos de eventos. Asegúrese de incluir también el preámbulo).

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. Cree y defina una función que dirija los datos a Bizible tras un envío de CTA de formulario. Esto va en el [!UICONTROL Custom Code>JavaScript] sección. (Nota: Esta función solo requiere el parámetro ctaData que proporciona Uberflip, pero puede incluir los demás parámetros ctaId y ctaName en caso de que el usuario desee personalizar su código para pasar estos datos también).

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. Cuando se envíe un formulario de CTA, asegúrese de que [!DNL Marketo Measure] se ejecuta según se indica a continuación. Esto se hace dentro de la variable [!UICONTROL Custom Code>JS] sección. (Nota: Es posible que tenga otro código dentro del vínculo de evento JavaScript Hubs.onCtaFormSubmitSuccess; asegúrese de incluir también esta llamada de función).

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
