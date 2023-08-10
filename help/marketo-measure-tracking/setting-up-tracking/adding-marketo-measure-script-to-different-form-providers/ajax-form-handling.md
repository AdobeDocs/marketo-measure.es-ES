---
unique-page-id: 18874745
description: AJAX Administración de formularios - [!DNL Marketo Measure] - Documentación del producto
title: Gestión de formularios AJAX
exl-id: 042e42ff-d8d9-4380-b878-aba4934bc4a0
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# Gestión de formularios AJAX {#ajax-form-handling}

Para informar manualmente de las conversiones de clientes a [!DNL Marketo Measure], hemos proporcionado una API muy sencilla que puede utilizar. Ambas API de Javascript están disponibles automáticamente en su sitio, si tiene nuestro código de seguimiento en él. No es necesario hacer nada especial para acceder a ellos.

## Escenario 1: formulario de HTML AJAX con envío de {#scenario-html-form-with-an-ajax-submit}

AJAX Cuando se utilizan formularios que contienen (u otro mecanismo) para enviar fechas de conversión del cliente a nuestros servidores, [!DNL Marketo Measure] puede que no esté al tanto de la conversión del cliente a través de ninguna de las rutas estándar que monitorizamos. En este escenario, podemos aprovechar una API simple (proporcionada a continuación).

Si administra sus propios envíos de formularios, puede llamar explícitamente a [!DNL Marketo Measure] desde JavaScript. [!DNL Marketo Measure] recopilará toda la información relevante del formulario y la publicará asincrónicamente en nuestros servidores.

**A continuación se muestra un ejemplo de código con JQuery (suponiendo que el ID del formulario es &quot;formId&quot;):**

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

## Escenario 2: información de posibles clientes recopilada en un formulario que no sea de HTML {#scenario-lead-information-collected-in-a-non-html-form}

Si se recopila información de un posible cliente convertido mediante JavaScript o campos de texto simples sin formulario HTML, esta solución es la adecuada para usted. A continuación se comparte la API que se debe utilizar en este caso:

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// If your site is using Ajax, or you are running a secure site, it is best to send us the data directly.  
Bizible.Push('User', {
eMail: 'user@gmail.com' // required  
});  
```

En este código, la variable [!UICONTROL email] Este campo es obligatorio. [!DNL Marketo Measure] publicará estos datos de forma asíncrona en nuestros servidores.

## Escenario 3: informar sobre el usuario desde la página de agradecimiento {#scenario-report-user-information-from-the-thank-you-page}

En algunos casos, es más conveniente informar de la información sobre posibles clientes a [!DNL Marketo Measure] en la página de agradecimiento, después de enviar el formulario. La forma más sencilla de informar sobre esta información es añadir un elemento oculto a la página que contiene información del envío del formulario, y [!DNL Bizible.js] leerá esta información cuando se haya cargado la página de agradecimiento.

**Por ejemplo:**

```html
<div id="bizible.reportUser" style="display:none"  
data-email="user@gmail.com">  
```

No importa si el elemento oculto es un tipo de etiqueta div, script o cualquier otro. [!DNL Marketo Measure] busca id=&quot;bizible.reportUser&quot; para leer la información.
