---
unique-page-id: 18874745
description: AJAX de formulario - [!DNL Marketo Measure] - Documentación del producto
title: Gestión AJAX formulario
exl-id: 042e42ff-d8d9-4380-b878-aba4934bc4a0
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---

# Gestión AJAX formulario {#ajax-form-handling}

Para informar manualmente de las conversiones de los clientes a [!DNL Marketo Measure], hemos proporcionado una API muy sencilla que puede utilizar. Ambas API de Javascript están disponibles automáticamente en su sitio, si tiene nuestro código de seguimiento. No hay necesidad de hacer nada especial para acceder a ellos.

## Escenario 1: formulario de HTML con AJAX enviado {#scenario-html-form-with-an-ajax-submit}

Cuando se utilizan formularios que contienen AJAX (u otro mecanismo) para enviar fechas de conversión del cliente a nuestros servidores, [!DNL Marketo Measure] es posible que no esté al tanto de la conversión del cliente a través de cualquiera de las rutas estándar que monitoreamos. En este escenario, podemos aprovechar una API simple (proporcionada a continuación).

Si gestiona sus propios envíos de formularios, puede llamar explícitamente a [!DNL Marketo Measure] de Javascript. [!DNL Marketo Measure] recopilará toda la información relevante del formulario y la enviará asincrónicamente a nuestros servidores.

**A continuación se muestra un ejemplo de código que utiliza JQuery (suponiendo que el ID del formulario es &quot;formId&quot;):**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the JQuery Selector for the form and we'll collect the data automatically.  
Bizible.Push('Form',$('#*formId*'));
```

**A continuación se muestra un ejemplo de código que no utiliza JQuery (suponiendo que el ID del formulario es &quot;formId&quot;):**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the Form ID and we'll collect the data automatically.
Bizible.Push('Form','MyFormID');
```

## Escenario 2: Información de posible cliente recopilada en un formulario que no es de HTML {#scenario-lead-information-collected-in-a-non-html-form}

Si la información de un posible cliente convertido se recopila mediante JavaScript o campos de texto simples sin formulario html, esta solución le ayudará. Compartido a continuación, se muestra la API que se utilizará en este escenario:

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// If your site is using Ajax, or you are running a secure site, it is best to send us the data directly.  
Bizible.Push('User', {
eMail: 'user@gmail.com' // required  
});  
```

En este código, la variable [!UICONTROL email] es obligatorio. [!DNL Marketo Measure] publicará estos datos asincrónicamente en nuestros servidores.

## Escenario 3: informar de la información del usuario desde la página de agradecimiento {#scenario-report-user-information-from-the-thank-you-page}

En algunos casos, es más conveniente informar de la información de posible cliente a [!DNL Marketo Measure] en la página de agradecimiento, después de enviar el formulario. La manera más sencilla de informar de esta información es agregar un elemento oculto a la página que contiene información del envío del formulario, y [!DNL Bizible.js] leerá esta información cuando se haya cargado la página de agradecimiento.

**Por ejemplo:**

```html
<div id="bizible.reportUser" style="display:none"  
data-email="user@gmail.com">  
```

No importa si el elemento oculto es un div, un script o cualquier otro tipo de etiqueta. [!DNL Marketo Measure] busca id=&quot;bizible.reportUser&quot; para leer la información.
