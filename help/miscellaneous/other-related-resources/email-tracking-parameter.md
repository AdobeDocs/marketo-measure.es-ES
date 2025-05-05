---
unique-page-id: 37356030
description: Parámetro de seguimiento de correo electrónico - [!DNL Marketo Measure]
title: Parámetro de seguimiento de correo electrónico
exl-id: e2cfd59e-ce4a-4cbb-b64a-828d1db7410f
feature: Tracking
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 4%

---

# Parámetro de seguimiento de correo electrónico {#email-tracking-parameter}

El parámetro de seguimiento de correo electrónico [!DNL Marketo Measure] permite a los especialistas en marketing tratar los clics en correos electrónicos como envíos de formularios, de modo que se generen puntos de contacto para esas acciones. Sin utilizar un parámetro de seguimiento de correo electrónico, las pulsaciones de un correo electrónico solo se tratan como &quot;visitas web&quot; hasta que el usuario interactúa con el sitio a través de un envío de formulario o un chat web.

## Casos de uso  {#use-cases}

**Registro de seminario web**: el equipo de marketing envía una invitación por correo electrónico con un solo botón para registrarse en un seminario web. Dado que el correo electrónico ya contiene la información de la persona, con un solo clic se registra automáticamente. La página de aterrizaje contiene el parámetro de seguimiento de correo electrónico, por lo que cuando pulsan y aterrizan en la página de confirmación, [!DNL Marketo Measure] puede capturar la dirección de correo electrónico y tratar el clic como un relleno de formulario, lo que genera un punto de contacto.

**Descarga de contenido**: El equipo de marketing de contenido desea promocionar un libro electrónico reciente que haya publicado con un vínculo de descarga directa de un correo electrónico. Cuando se crea la plantilla de correo electrónico, la página de confirmación de descarga contiene el parámetro de seguimiento de correo electrónico para que, al hacer clic, [!DNL Marketo Measure] pueda capturar la dirección de correo electrónico. Sin tener que rellenar un formulario en el sitio, [!DNL Marketo Measure] puede generar un punto de contacto para la descarga de contenido. Esto se debe a que el correo electrónico los envió a la página de confirmación con el parámetro de seguimiento de correo electrónico.

## Cómo funciona {#how-it-works}

Cuando un visitante llega a su sitio, [!DNL Marketo Measure] espera encontrar una página de aterrizaje con una dirección de correo electrónico o un identificador de [!DNL Salesforce] para que podamos asociar esa visita con un &quot;envío de formulario&quot; y generar un punto de contacto para esa actividad.

Como cliente, puede crear una plantilla de correo electrónico como lo haría normalmente. Una vez que sea el momento de agregar en la página de aterrizaje la acción que desea rastrear, debe determinar el token, la etiqueta de variable o la macro que acepta la plataforma de automatización de marketing para mostrar dinámicamente el valor de cada individuo.

Marketo Measure acepta los siguientes valores: Dirección de correo electrónico, ID de posible cliente de Salesforce o ID de contacto de Salesforce.

## Ejemplos de etiquetas {#tag-examples}

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p>Automatización de marketing</p></th> 
   <th><p>Token/etiqueta/macro </p></th> 
   <th><p>Ejemplo</p></th> 
   <th><p>Material de apoyo</p></th> 
  </tr> 
  <tr> 
   <td><p>Marketo</p></td> 
   <td><p>{{lead.Email Address}} </p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId={{lead.EmailAddress}}</p></td> 
   <td><p>https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/personalizing-landing-pages/tokens-overview.html?lang=es</p></td> 
  </tr> 
  <tr> 
   <td><p>Pardot</p></td> 
   <td><p>%%email%% </p><p>o</p><p>%%user_crm_id%%</p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId=%%email%%</p></td> 
   <td><p>https://help.salesforce.com/s/articleView?language=en_US&amp;id=pardot_variable_tags_reference.htm&amp;type=5</p></td> 
  </tr> 
  <tr> 
   <td><p>Hubspot</p></td> 
   <td><p>(insertado mediante el editor)</p></td> 
   <td><p>n/a</p></td> 
   <td><p>https://knowledge.hubspot.com/website-pages/personalize-your-content</p></td> 
  </tr> 
  <tr> 
   <td><p>Act-On</p></td> 
   <td><p>(insertado a través del Compositor de mensajes)</p></td> 
   <td><p>n/a</p></td> 
   <td><p>https://connect.act-on.com/hc/en-us/articles/360033436074-How-to-Personalize-Email-Content-with-CRM-Data</p></td> 
  </tr> 
 </tbody> 
</table>

Y, por último, en [!DNL Marketo Measure], debe especificar el parámetro de seguimiento para que [!DNL Marketo Measure] pueda encontrar el valor del correo electrónico o el identificador. El valor predeterminado es &quot;mailId&quot;, como se muestra en los ejemplos anteriores y en la captura de pantalla siguiente. Escriba el valor en Configuración en [!DNL Marketo Measure] y luego haga clic en **[!UICONTROL Guardar]**.

![](assets/one.png)
