---
description: Prácticas recomendadas para configurar la guía de parámetros de UTM para usuarios de Marketo Measure
title: Prácticas recomendadas para configurar parámetros UTM
exl-id: 56019f41-b6ba-48c1-9bef-2a5f56d2d5f4
feature: UTM Parameters
hidefromtoc: true
source-git-commit: 7a4661c8d42214d32e5360dc45d6d880b08ef37c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 71%

---

# Prácticas recomendadas para configurar parámetros UTM {#best-practices-for-setting-up-utm-parameters}

Los parámetros de UTM son una buena manera de cortar y fragmentar los datos de marketing. [!DNL Marketo Measure] utiliza y captura todos los parámetros de UTM para rellenar campos en Salesforce y en la aplicación [!DNL Marketo Measure]. Con esta información, podrá obtener una comprensión granular de dónde provienen sus posibles clientes, oportunidades y operaciones cerradas/ganadas.

Puede usar el [Generador de URL de Google](https://support.google.com/analytics/answer/1033867?hl=es){target="_blank"} para configurar los parámetros de UTM y agregarlos a los vínculos dentro de los esfuerzos de marketing. Use esta [hoja de cálculo de Google](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"} si desea una forma más sencilla de realizar el seguimiento de todos los vínculos de UTM.

## Valores de alto nivel para cada parámetro {#high-level-values-for-each-parameter}

**utm_medium**: este campo se asigna al campo Medium. Use utm_medium para denotar el canal de alto nivel.

Por ejemplo, [!UICONTROL Social], CPC, correo electrónico, web, orgánico

No utilice este campo para llamar al subcanal.

**utm_source**: este campo se asigna al campo Origen de Touchpoint. Utilice utm_source para definir el subcanal desde el que se origina el posible cliente.

Por ejemplo, Facebook, Twitter, LinkedIn, Drip_email, Email_blast, Newsletter.

No se complique. No utilice este parámetro para indicar un tipo de anuncio, como reorientación o patrocinado. No agregue utm_source = homepage, webdirect, website. [!DNL Marketo Measure] rellena automáticamente esta información por usted.

**utm_campaign**: este campo se asigna al nombre de la campaña de publicidad. Utilice utm_campaign para indicar el título de la campaña tal como existe en la plataforma de publicidad o como se denomina internamente.

Este también es un buen parámetro para denotar geolocalización, tipo de red de publicidad (mostrar v. búsqueda), etc.

Se recomienda utilizar guiones bajos en lugar de espacios y evitar el uso de signos de puntuación. Esto reduce las posibilidades de que se cometan errores de codificación al leer los parámetros en los exploradores.

Por ejemplo, AU_Idea_for_an_App_50k

**utm_content**: esto se asigna al contenido del anuncio. Utilice el Título del anuncio en el parámetro utm_content. Si es un anuncio de imagen, utilice el título del anuncio e incluya las dimensiones del anuncio.

Por ejemplo, [título del anuncio] 200 x 400 px

**utm_term**: esto se asigna al Texto de palabra clave. Utilice este parámetro para indicar la palabra clave relacionada con la activación de la publicidad.

Si no hay ninguna palabra clave relacionada con la publicidad, deje este parámetro en blanco.

P. ej., ideas de aplicaciones de iPhone

**Sea sencillo y breve. No duplique esfuerzos, términos y canales.**

Imaginamos la jerarquía de UTM de la siguiente manera:

Medium > [!UICONTROL Origen] > [!UICONTROL Campaña] > [!UICONTROL Contenido/Término]

P. ej., si se inserta un anuncio [!UICONTROL en pantalla] en Facebook, recomendamos lo siguiente:

`fakewebsite.com/?utm_medium=social&utm_source=facebook&utm_campaign=Display_campaign_ID&utm_content=content_of_campaign`

Observe que los términos/canal no están duplicados y que utm_term no se utiliza en este caso.

Si tiene alguna pregunta, comuníquese con el equipo de cuenta de Adobe (su administrador de cuentas) o con [Soporte técnico de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
