---
unique-page-id: 37356030
description: Parámetro de seguimiento de correo electrónico - [!DNL Marketo Measure] - Documentación del producto
title: Parámetro de seguimiento de correo electrónico
exl-id: e2cfd59e-ce4a-4cbb-b64a-828d1db7410f
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 3%

---

# Parámetro de seguimiento de correo electrónico {#email-tracking-parameter}

La variable [!DNL Marketo Measure] El parámetro de seguimiento de correo electrónico permite a los especialistas en marketing tratar los clics de correo electrónico como envíos de formularios para que se generen puntos de contacto para esas acciones. Sin utilizar un parámetro de seguimiento de correo electrónico, las pulsaciones de un correo electrónico solo se tratan como &quot;visitas web&quot; hasta que el usuario realmente interactúa con el sitio mediante un envío de formulario o una conversación en la web.

## Casos de uso  {#use-cases}

**Registro de seminario web**: El equipo de marketing envía una invitación por correo electrónico con un solo botón para registrarse en un seminario web. Como el correo electrónico ya tiene la información de la persona, el clic único los registrará automáticamente. La página de aterrizaje contiene el parámetro de seguimiento de correo electrónico, de modo que cuando pulsan y aterrizan en la página de confirmación, [!DNL Marketo Measure] puede capturar la dirección de correo electrónico y tratar la pulsación como un relleno de formulario, que generará un punto de contacto.

**Descarga de contenido**: El equipo de marketing de contenido quiere promocionar un eBook reciente que han publicado con un vínculo de descarga directa desde un correo electrónico. Cuando se crea la plantilla de correo electrónico, la página de confirmación de descarga contiene el parámetro de seguimiento de correo electrónico para que cuando pulsen, [!DNL Marketo Measure] puede capturar la dirección de correo electrónico. Sin tener que rellenar un formulario en el sitio, [!DNL Marketo Measure] puede generar un touchpoint para la descarga de contenido que se produjo mediante el correo electrónico porque los puso en la página de confirmación con el parámetro de seguimiento de correo electrónico.

## Cómo funciona {#how-it-works}

Cuando un visitante llega a su sitio, [!DNL Marketo Measure] espera encontrar una página de aterrizaje con una dirección de correo electrónico o [!DNL Salesforce] Id para que podamos asociar esa visita con un &quot;envío de formulario&quot; y generar un punto de contacto para esa actividad.

Como cliente, creará una plantilla de correo electrónico como lo haría normalmente. Una vez que haya llegado el momento de agregar en la página de aterrizaje la acción que desee rastrear, deberá determinar el token, la etiqueta de variable o la macro que la plataforma de automatización de marketing acepte para mostrar dinámicamente el valor de cada individuo.

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
   <th><p>Token/Etiqueta/Macro </p></th> 
   <th><p>Ejemplo</p></th> 
   <th><p>Material de apoyo</p></th> 
  </tr> 
  <tr> 
   <td><p>Marketo</p></td> 
   <td><p>{{Dirección de correo electrónico del posible cliente}} </p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId={{lead.EmailAddress}}</p></td> 
   <td><p>https://docs.marketo.com/display/public/DOCS/Tokens+Overview#TokensOverview-PersonTokens</p></td> 
  </tr> 
  <tr> 
   <td><p>Pardot</p></td> 
   <td><p>%%email%% </p><p>o</p><p>%%user_crm_id%%</p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId=%%email%%</p></td> 
   <td><p>https://help.salesforce.com/articleView?id=pardot_variable_tags_reference.htm&amp;type=5</p></td> 
  </tr> 
  <tr> 
   <td><p>Hubspot</p></td> 
   <td><p>(insertado mediante Editor)</p></td> 
   <td><p>n/a</p></td> 
   <td><p>https://knowledge.hubspot.com/cos-general/how-to-use-personalization-with-your-content</p></td> 
  </tr> 
  <tr> 
   <td><p>Act-On</p></td> 
   <td><p>(insertado mediante el Compositor de mensajes)</p></td> 
   <td><p>n/a</p></td> 
   <td><p>https://connect.act-on.com/hc/en-us/articles/360033436074-How-to-Personalize-Email-Content-with-CRM-Data</p></td> 
  </tr> 
 </tbody> 
</table>

Y finalmente, en [!DNL Marketo Measure], deberá especificar el parámetro de seguimiento para que [!DNL Marketo Measure] Puede localizar el valor del correo electrónico o del ID. El valor predeterminado es &quot;mailId&quot;, como se muestra en los ejemplos anteriores y en la captura de pantalla siguiente. Introduzca el valor en la Configuración en [!DNL Marketo Measure]y haga clic en **[!UICONTROL Guardar]**.

![](assets/one.png)
