---
unique-page-id: 18874732
description: 'Prácticas recomendadas para configurar parámetros de UTM: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para configurar parámetros UTM
exl-id: 56019f41-b6ba-48c1-9bef-2a5f56d2d5f4
source-git-commit: 51397a02872035fef41d308c1f855bcaecc29c4e
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 3%

---

# Prácticas recomendadas para configurar parámetros UTM {#best-practices-for-setting-up-utm-parameters}

Los parámetros de UTM son la buena forma de cortar y fragmentar los datos de marketing. [!DNL Marketo Measure] utiliza y captura todos los parámetros de la UTM para rellenar campos en Salesforce y en la variable [!DNL Marketo Measure] aplicación. Con esta información, podrá comprender de dónde provienen sus posibles clientes, oportunidades y ofertas cerradas/ganadas.

Puede utilizar el [Google URL Builder](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"} to set up your UTM parameters and add them to your links within your marketing efforts. Use this [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"} si desea una forma más sencilla de realizar un seguimiento de todos los vínculos de la UTM.

## Valores de alto nivel para cada parámetro {#high-level-values-for-each-parameter}

**utm_medium**: Este campo se asigna al campo Medio . Utilice utm_medium para denotar el canal de alto nivel.

p. ej., [!UICONTROL Social], CPC, correo electrónico, web, orgánico

No utilice este campo para llamar al subcanal.

**utm_source**: Este campo se asigna al campo Origen del punto de contacto . Utilice utm_source para definir el subcanal desde el que se origina el posible cliente.

Por ejemplo, Facebook, Twitter, Linkedin, Drip_email, Email_blast, newsletter.

Manténgalo simple. No utilice este parámetro para denotar el tipo de anuncio, como la reorientación, el patrocinado, etc. No añada un utm_source = página principal, webdirect, sitio web. [!DNL Marketo Measure] rellenará automáticamente esta información.

**utm_campaign**: Este campo se asigna a Nombre de campaña de publicidad. Utilice utm_campaign para indicar el título de la campaña tal como existe en la plataforma de publicidad o como se hace referencia a ella internamente.

También es un buen parámetro para denotar geolocalización, tipo de red de publicidad (visualización v. search), etc.

Se recomienda utilizar guiones bajos en lugar de espacios y evitar la puntuación. Esto reduce las posibilidades de que los navegadores cometan errores de codificación al leer los parámetros.

Por ejemplo, AU_Idea_for_an_App_50k

**utm_content**: Esto se asigna a Contenido de anuncio. Utilice el Título de anuncio en el parámetro utm_content . Si se trata de una publicidad de imagen, utilice el título de la publicidad e incluya las dimensiones de la publicidad.

p. ej., [título de la publicidad] 200x400px

**utm_term**: Esto se asigna a Texto de palabra clave. Utilice este parámetro para indicar la palabra clave relacionada con la activación de la publicidad.

Si no hay ninguna palabra clave relacionada con la publicidad, deje este parámetro en blanco.

Por ejemplo, iPhone App Ideas

**Manténgalo simple y sucinto. No duplique esfuerzos, términos y canales.**

Imaginamos la jerarquía de UTM de la siguiente manera:

Medio > [!UICONTROL Fuente] > [!UICONTROL Campaign] > [!UICONTROL Contenido/Término]

Por ejemplo, si [!UICONTROL visualización] se ubica en Facebook, se recomienda lo siguiente:

fakewebsite.com/

?utm_medium=social

&amp;utm_source=facebook

&amp;utm_campaign=Display_campaign_ID

&amp;utm_content=content_of_campaign

Observe que los términos/canal no están duplicados y utm_term no se utiliza en este caso.

Si tiene alguna pregunta, póngase en contacto con el equipo de cuentas de Adobe (su administrador de cuentas) o [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
