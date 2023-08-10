---
unique-page-id: 18874564
description: Definición de [!DNL Marketo Measure] Sesiones web - [!DNL Marketo Measure] - Documentación del producto
title: Definición de sesiones web de  [!DNL Marketo Measure]
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 1%

---

# Definición de sesiones web de [!DNL Marketo Measure] {#definition-of-marketo-measure-web-sessions}

Descubra cómo [!DNL Marketo Measure] define las sesiones web.

A **sesión web** hace referencia a las interacciones de una persona con su sitio web durante un período de tiempo determinado. La sesión comienza cuando un usuario aterriza en el sitio web.

Por ejemplo, Haley visita adobe.com. Su visita al sitio inicia una sesión. Cuando Haley abandona el sitio, cerrando la pestaña o el navegador web o saliendo del sitio, la sesión finaliza.

Un usuario no puede abrir varias sesiones al mismo tiempo. Si Haley abre [!DNL adobe.com] en 10 pestañas independientes, solo se ha creado una sesión en relación con su visita al sitio web.

## ¿Cómo? [!DNL Marketo Measure] ¿desea definir una nueva sesión? {#how-does-marketo-measure-define-a-new-session}

Hay algunas cosas que determinan cuándo termina una sesión y cuándo comienza una nueva. Las dos vías principales [!DNL Marketo Measure] las sesiones que pueden finalizar son:

* **Caducidad basada en el tiempo**
* **Caducidad basada en el canal**

## Caducidad basada en el tiempo {#time-based-expiration}

**¿Cuánto dura una sesión?**

[!DNL Marketo Measure] las sesiones finalizarán tras 30 minutos de inactividad en el sitio web. Por ejemplo:

Cuando Haley visita adobe.com, comienza una sesión. Explora el sitio web durante unos minutos y luego se aleja de su ordenador, pero deja el sitio web abierto. Tras 30 minutos de inactividad, la sesión finaliza.

Actualmente, [!DNL Marketo Measure] solo considera la navegación por páginas y los envíos de formularios como actividad. El desplazamiento por la página web o el desplazamiento por encima de un elemento de la página no se consideran actividades. Así que si Haley visita adobe.com para leer una publicación de blog, y le toma una hora leerla, su sesión web terminará después de 30 minutos incluso si se está desplazando por el contenido de la página.

## Caducidad basada en el canal {#channel-based-expiration}

[!DNL Marketo Measure] iniciará una nueva sesión cada vez que un usuario visite su sitio web desde un canal de marketing digital diferente o desde un sitio web externo. Esto incluye:

* Un sitio web de referencia
* Canales sociales ([!DNL Facebook], [!DNL LinkedIn], etc.)
* Canales de búsqueda de pago u orgánicos ([!DNL Google/Bing])

**Sitios web de referencia y canales sociales**

Cada vez que un visitante llega a su sitio web desde un sitio web de referencia o un canal social, comienza una nueva sesión.

Di que Haley está en LinkedIn, hace clic en un [!DNL Marketo Measure] publique y se redirija al sitio web del Adobe. A continuación, mientras se desplaza [!DNL Facebook], Haley ve otro [!DNL Marketo Measure] publicación. Cuando hace clic en esta publicación y se le redirige al sitio del Adobe, esto provoca la primera sesión web relacionada con [!DNL LinkedIn] hasta el final y una nueva sesión relacionada con [!DNL Facebook] comienza.

**Canales de búsqueda de pago u orgánicos**

Las nuevas sesiones comenzarán cada vez que un usuario entre en el sitio a través de canales de búsqueda orgánicos o de pago. Si Haley llega al sitio web del Adobe a través de una búsqueda orgánica, y luego visita inmediatamente su sitio web a través de un anuncio de pago en Google, se crearán dos sesiones separadas.

**Tráfico web directo**

Si un visitante llega a su sitio web escribiendo la URL de su sitio web en la barra de direcciones, no siempre hace que comience una nueva sesión.

Si la primera sesión web de Haley comienza como resultado de una visita desde un sitio de referencia, un canal social o un canal de búsqueda orgánica/paga y luego visita el sitio a través de un canal directo en la web, esto no causaría el inicio de una nueva sesión.

_Sin embargo_, si la primera sesión web de Haley se originó en Web Direct y luego visita el sitio web a través de _un sitio externo/de referencia_, la primera sesión finalizará y se abrirá una nueva sesión relacionada con el sitio externo/de referencia.

## Sesiones de Google Analytics {#google-analytics-sessions}

Hay algunas similitudes con cómo [!DNL Marketo Measure] y Google Analytics define las sesiones. Para obtener más información sobre cómo definen las sesiones los Google Analytics, visite: [https://support.google.com/analytics/answer/2731565?hl=en](http://support.google.com/analytics/answer/2731565?hl=en){target="_blank"}
