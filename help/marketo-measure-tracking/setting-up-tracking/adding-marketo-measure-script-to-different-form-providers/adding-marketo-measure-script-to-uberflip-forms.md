---
unique-page-id: 18874749
description: Adición [!DNL Marketo Measure] Secuencia de comandos para [!DNL Uberflip] Forms - [!DNL Marketo Measure] - Documentación del producto
title: Adición [!DNL Marketo Measure] Secuencia de comandos para [!DNL Uberflip] Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Adición [!DNL Marketo Measure] Secuencia de comandos para [!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

Si está utilizando [!DNL Uberflip] para administrar el contenido, es importante que siga estos pasos necesarios para asegurarse de que [!DNL Marketo Measure] realiza el seguimiento de esos envíos de formularios. El Administrador de éxito en [!DNL Uberflip] también debería poder ayudarle con esto.

1. Agregar esta secuencia de comandos a [!DNL Uberflip]&#39;s [!UICONTROL Código personalizado>HTML] para obtener más información.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Asegúrese de que [!DNL Marketo Measure] el código de preámbulo se activa tanto en la carga de página como en AJAX cambio de página. Haga esto dentro de [!UICONTROL Custom Code>JS] sección

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   Añadirá este preámbulo a ambos [!DNL Hubs.onLoad] y [!DNL Hubs.onPageChange] AJAX evento de Javascript se vincula por debajo. (Nota: También puede tener otros códigos en estos enlaces de eventos. Asegúrese de incluir también el preámbulo).

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. Cree y defina una función que inserte los datos en Bizible al enviar el Llamada a acción del formulario. Esto entra en el [!UICONTROL Código personalizado>Javascript] para obtener más información. (Nota: esta función solo requiere el parámetro ctaData que proporciona Uberflip, pero puede incluir los demás parámetros ctaId y ctaName en caso de que el usuario desee personalizar su código para pasar también estos datos).

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. Cuando se envíe una llamada a acción de formulario, asegúrese de que su [!DNL Marketo Measure] se ejecuta de la siguiente manera. Esto se hace dentro de la variable [!UICONTROL Custom Code>JS] para obtener más información. (Nota: Puede tener otro código dentro del vínculo de evento de javascript Hubs.onCtaFormSubmitSuccess, asegúrese de incluir también esta llamada de función).

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
