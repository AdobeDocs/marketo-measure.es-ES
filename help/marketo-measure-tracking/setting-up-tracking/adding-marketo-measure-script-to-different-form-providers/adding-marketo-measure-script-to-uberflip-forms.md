---
unique-page-id: 18874749
description: Agregando [!DNL Marketo Measure] Script a [!DNL Uberflip] FORMS - [!DNL Marketo Measure] - Documentación del producto
title: Adición del script de  [!DNL Marketo Measure]  a formularios de  [!DNL Uberflip]
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 3%

---

# Adición del script de [!DNL Marketo Measure] a formularios de [!DNL Uberflip] {#adding-marketo-measure-script-to-uberflip-forms}

Si está utilizando [!DNL Uberflip] para administrar el contenido, es importante que siga estos pasos necesarios para asegurarse de que [!DNL Marketo Measure] está realizando un seguimiento de esos envíos de formularios. Su gestor de éxito en [!DNL Uberflip] También debería poder ayudarle con esto.

1. Agregar este script a [!DNL Uberflip]de [!UICONTROL Custom Code>HTML] sección.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Asegúrese de esto [!DNL Marketo Measure] AJAX el código de preámbulo se activa tanto al cargar la página como al cambiar de página de la. Haga esto dentro de la [!UICONTROL Custom Code>JS] sección

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   Se agregará este preámbulo a ambos [!DNL Hubs.onLoad] y el [!DNL Hubs.onPageChange] AJAX Los enlaces de eventos de Javascript se encuentran a continuación. (Nota: Es posible que también tenga otros códigos en estos vínculos de eventos. Solo asegúrese de incluir el preámbulo también).

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. Cree y defina una función que inserte datos en Bizible tras el envío de un formulario CTA. Esto va en el [!UICONTROL Custom Code>Javascript] sección. (Nota: Esta función solo requiere el parámetro ctaData que proporciona Uberflip, pero puede incluir los demás parámetros ctaId y ctaName en caso de que el usuario desee personalizar su código para pasar estos datos también).

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. Cuando se envíe un formulario de CTA, asegúrese de que [!DNL Marketo Measure] se ejecuta según se indica a continuación. Esto se hace dentro de la variable [!UICONTROL Custom Code>JS] sección. (Nota: es posible que tenga otro código dentro del vínculo de evento javascript Hubs.onCtaFormSubmitSuccess; asegúrese de incluir también esta llamada de función).

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
