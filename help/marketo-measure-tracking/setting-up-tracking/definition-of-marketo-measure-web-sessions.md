---
unique-page-id: 18874564
description: Definición de [!DNL Marketo Measure] Sesiones web - [!DNL Marketo Measure] - Documentación del producto
title: Definición de [!DNL Marketo Measure] Sesiones web
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# Definición de [!DNL Marketo Measure] Sesiones web {#definition-of-marketo-measure-web-sessions}

Descubra cómo [!DNL Marketo Measure] define sesiones web.

A **sesión web** hace referencia a las interacciones de un individuo con su sitio web durante un tiempo determinado. La sesión comienza cuando un usuario aterriza en el sitio web.

Por ejemplo, Haley visita adobe.com. Su visita al sitio comienza una sesión. Cuando Haley abandona el sitio, cerrando la pestaña o el navegador web o navegando fuera del sitio, la sesión finaliza.

Un usuario no puede abrir varias sesiones al mismo tiempo. Si se abre Haley [!DNL adobe.com] en 10 pestañas separadas, solo se ha creado una sesión en relación con su visita al sitio web.

## ¿Cómo [!DNL Marketo Measure] definir una nueva sesión? {#how-does-marketo-measure-define-a-new-session}

Hay algunas cosas que determinan cuándo finaliza una sesión y cuándo comienza una nueva. Las dos vías principales [!DNL Marketo Measure] las sesiones pueden finalizar:

* **Caducidad basada en el tiempo**
* **Caducidad basada en canales**

## Caducidad basada en el tiempo {#time-based-expiration}

**¿Durante cuánto tiempo dura una sesión?**

[!DNL Marketo Measure] las sesiones finalizarán tras 30 minutos de inactividad en el sitio web. Por ejemplo:

Cuando Haley visita adobe.com, comienza una sesión. Ella explora el sitio web por unos minutos y luego se aleja de su computadora, pero deja el sitio web abierto. Tras 30 minutos de inactividad, la sesión finalizará.

Actualmente, [!DNL Marketo Measure] solo considera la navegación de página y los envíos de formularios como actividad. Desplazarse por la página web o pasar el ratón por encima de un elemento de la página no se considera actividad. Así que si Haley visita adobe.com para leer un post de su blog, y le toma una hora leer, su sesión web terminará después de 30 minutos aunque se desplace por el contenido de la página.

## Caducidad basada en canales {#channel-based-expiration}

[!DNL Marketo Measure] iniciará una nueva sesión cada vez que un usuario visite su sitio web desde un canal de marketing digital diferente o desde un sitio web externo. Esto incluye:

* Un sitio web de referencia
* Canales sociales ([!DNL Facebook], [!DNL LinkedIn], etc.)
* Canales de búsqueda orgánicos o de pago ([!DNL Google/Bing])

**Sitios web de referencia y canales sociales**

Cada vez que un visitante llega a su sitio web desde un sitio web de referencia o un canal social, se iniciará una nueva sesión.

Digamos que Haley está en LinkedIn, hace clic en un [!DNL Marketo Measure] y se redirige al sitio web de Adobe. A continuación, mientras se desplaza [!DNL Facebook], Haley ve otro [!DNL Marketo Measure] publicación. Cuando hace clic en este anuncio y se redirige al sitio de Adobe, esto provoca la primera sesión web relacionada con [!DNL LinkedIn] al final y una nueva sesión relacionada con [!DNL Facebook] comienza.

**Canales de búsqueda orgánica o de pago**

Las nuevas sesiones se iniciarán cada vez que un usuario visite su sitio web a través de canales de búsqueda orgánicos o de pago. Si Haley llega al sitio web de Adobe a través de una búsqueda orgánica y luego visita inmediatamente su sitio web a través de un anuncio pagado en Google, se crearán dos sesiones separadas.

**Tráfico directo web**

Si un visitante llega a su sitio web escribiendo la dirección URL de su sitio web en la barra de direcciones, no siempre provoca que comience una nueva sesión.

Si la primera sesión web de Haley comienza como resultado de una visita desde un sitio de referencia, un canal social o un canal de búsqueda orgánica o paga y luego visita el sitio a través de una página web directa, esto no causaría que se inicie una nueva sesión.

_Sin embargo_, si la primera sesión web de Haley se originó en Web Direct, y luego visita el sitio web a través de _un sitio externo/referente_, la primera sesión finalizará y se abrirá una nueva sesión relacionada con el sitio externo/de referencia.

## Sesiones de Google Analytics {#google-analytics-sessions}

Hay algunas similitudes con cómo [!DNL Marketo Measure] y los Google Analytics definen las sesiones. Para obtener más información sobre cómo definen las sesiones los Google Analytics, visite: [https://support.google.com/analytics/answer/2731565?hl=en](http://support.google.com/analytics/answer/2731565?hl=en){target=&quot;_blank&quot;}
