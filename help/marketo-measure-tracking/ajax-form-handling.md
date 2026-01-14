---
description: Guía de administración de formularios de AJAX para usuarios de Marketo Measure
title: Gestión de formularios AJAX
exl-id: 042e42ff-d8d9-4380-b878-aba4934bc4a0
feature: Tracking
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 1%

---

# Gestión de formularios AJAX {#ajax-form-handling}

Para informar manualmente sobre las conversiones de clientes a [!DNL Marketo Measure], existe una API sencilla que puede usar. Ambas API de JavaScript están disponibles automáticamente en el sitio, si tiene código de seguimiento. No es necesario hacer nada especial para acceder a ellos.

## Escenario 1: un formulario de HTML con un envío de AJAX {#scenario-html-form-with-an-ajax-submit}

Cuando se usan formularios que contienen AJAX (u otro mecanismo) para enviar las fechas de conversión del cliente a nuestros servidores, es posible que [!DNL Marketo Measure] no tenga conocimiento de la conversión del cliente a través de ninguna de las rutas estándar que monitorizamos. En este escenario, podemos utilizar una API simple (proporcionada a continuación).

Si administra sus propios envíos de formularios, puede llamar explícitamente a [!DNL Marketo Measure] desde JavaScript. [!DNL Marketo Measure] recopila toda la información relevante del formulario y la publica asincrónicamente en nuestros servidores.

**A continuación se muestra un ejemplo de código que utiliza JQuery (suponiendo que el ID del formulario es &quot;formId&quot;):**

```javascript
///////////////////////////////////////////////////////////////////////
// Preamble for all API usage.
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };

// Give Marketo Measure the JQuery Selector for the form and we'll collect the data automatically.
Bizible.Push('Form',$('#*formId*'));
```

**A continuación se muestra un ejemplo de código que no utiliza JQuery (suponiendo que el ID del formulario es &quot;formId&quot;):**

```javascript
///////////////////////////////////////////////////////////////////////
// Preamble for all API usage.
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };

// Give Marketo Measure the Form ID and we'll collect the data automatically.
Bizible.Push('Form','MyFormID');
```

## Escenario 2: información de posibles clientes recopilada en un formulario que no es de HTML {#scenario-lead-information-collected-in-a-non-html-form}

Si la información de un posible cliente convertido se recopila mediante JavaScript o campos de texto simples sin formulario HTML, esta solución funciona por usted. A continuación se comparte la API que se debe utilizar en este caso:

```javascript
///////////////////////////////////////////////////////////////////////
// Preamble for all API usage.
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };

// If your site is using Ajax, or you are running a secure site, it is best to send us the data directly.
Bizible.Push('User', {
eMail: 'user@gmail.com' // required
});
```

En este código, el campo [!UICONTROL correo electrónico] es obligatorio. [!DNL Marketo Measure] publica estos datos de manera asincrónica en nuestros servidores.

## Escenario 3: informar sobre el usuario desde la página de agradecimiento {#scenario-report-user-information-from-the-thank-you-page}

A veces, es más conveniente informar la información de posibles clientes a [!DNL Marketo Measure] desde la página de agradecimiento, una vez enviado el formulario. La forma más sencilla de informar sobre esta información es agregar un elemento oculto a la página que contiene información del envío del formulario, y [!DNL Bizible.js] leerá esta información cuando se haya cargado la página &quot;Gracias&quot;.

**Por ejemplo:**

```html
<div id="bizible.reportUser" style="display:none"
data-email="user@gmail.com">
```

No importa si el elemento oculto es un tipo de etiqueta div, script o cualquier otro. [!DNL Marketo Measure] busca id=&quot;bizible.reportUser&quot; para leer la información.
