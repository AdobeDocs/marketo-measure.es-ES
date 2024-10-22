---
unique-page-id: 18874564
description: Definición de sesiones web de  [!DNL Marketo Measure]  - [!DNL Marketo Measure]
title: Definición de sesiones web de  [!DNL Marketo Measure]
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
feature: Tracking
source-git-commit: 9a5e267b4b268d067fbbe89a00a4da96752a44db
workflow-type: ht
source-wordcount: '811'
ht-degree: 100%

---

# Definición de sesiones web de [!DNL Marketo Measure] {#definition-of-marketo-measure-web-sessions}

Descubra cómo [!DNL Marketo Measure] define las sesiones web.

Una **sesión web** hace referencia a las interacciones de una persona con su sitio web durante un período de tiempo determinado. La sesión comienza cuando un usuario aterriza en el sitio web.

Por ejemplo, Haley visita adobe.com. En su visita al sitio, inicia sesión. Cuando Haley abandona el sitio, cierra la pestaña o el explorador web o sale del sitio, por lo tanto, la sesión finaliza.

El usuario no puede abrir varias sesiones al mismo tiempo. Si Haley abre [!DNL adobe.com] en 10 pestañas independientes, solo se ha creado una sesión en relación con su visita al sitio web.

## ¿Cómo define [!DNL Marketo Measure] una nueva sesión? {#how-does-marketo-measure-define-a-new-session}

Hay algunas cosas que determinan cuándo termina una sesión y cuándo comienza una nueva. Las dos maneras principales en que las sesiones de [!DNL Marketo Measure] pueden finalizar son las siguientes:

* **Caducidad basada en el tiempo**
* **Caducidad basada en el canal**

## Caducidad basada en el tiempo {#time-based-expiration}

### Comportamiento heredado {#legacy-behavior}

**¿Cuánto dura una sesión?**

Las sesiones de [!UICONTROL Marketo Measure] finalizarán transcurridos 30 minutos de inactividad en el sitio web. Por ejemplo:

Cuando Haley visita adobe.com, comienza una sesión. Explora el sitio web durante unos minutos y luego se aleja de su ordenador, pero deja el sitio web abierto. Tras 30 minutos de inactividad, la sesión finaliza.

Actualmente, [!UICONTROL Marketo Measure] solo considera la navegación por páginas y los envíos de formularios como actividad. El desplazamiento por la página web o sobre un elemento de la página no se consideran actividades. Por lo tanto, si Haley visita adobe.com para leer una publicación del blog, y tarda una hora leerla, su sesión web terminará transcurridos 30 minutos, incluso si se está desplazando por el contenido de la página.

### Nuevo comportamiento {#new-behavior}

Para los nuevos usuarios, este será el comportamiento predeterminado.

Los usuarios existentes pueden adoptar el nuevo comportamiento activando la opción en **Configuración** > **Atribución por contacto** > **Transferencia de canal de sesión**. Una vez activado, este ajuste no se puede revertir.

Cuando se crea una nueva sesión después de 30 minutos de inactividad, el canal de la sesión anterior se transfiere si la nueva sesión se inicia en un plazo de siete días. Esta prórroga solo se aplica a las visitas directas (sin referente ni referentes internos). Si la inactividad supera los siete días, el canal de la nueva sesión será Directo/Otro de forma predeterminada. Por ejemplo, si Haley visita landingpage.com desde Google, está inactivo durante más de 30 minutos y regresa en un plazo de siete días, la nueva sesión conservará el canal de Google. Sin embargo, si el mismo usuario vuelve a visitar la página a través de un canal diferente, el canal que no sea Directo no se anulará con el canal de Google anterior.

Solo se transmitirá el canal, excepto los detalles de la campaña o del remitente del reenvío. Esto se debe a que la clasificación de canales la gestiona Marketo Measure, mientras que otros puntos de datos se recopilan por separado.

**Inicio de sesión social**

Cuando un visitante utiliza el inicio de sesión social mediante Google, Microsoft o Apple, la sesión se combina en una sesión continua. Por ejemplo, si un visitante llega a una página desde LinkedIn, completa un inicio de sesión social de Google y llega a una página de agradecimiento, todo se contará como una sola sesión. Sin la opción de transferencia de canal de sesión activada, el inicio de sesión social crearía sesiones independientes debido al referente externo.

## Caducidad basada en el canal {#channel-based-expiration}

[!DNL Marketo Measure] iniciará una nueva sesión cada vez que un usuario visite su sitio web desde un canal de marketing digital diferente o desde un sitio web externo. Esto incluye lo siguiente:

* Un sitio web de referencia
* Canales sociales ([!DNL Facebook], [!DNL LinkedIn], etc.)
* Canales de búsqueda orgánica o de pago ([!DNL Google/Bing])

**Sitios web de referencia y canales sociales**

Cada vez que un visitante accede a su sitio web desde un sitio web de referencia o un canal social, comienza una nueva sesión.

Supongamos que Haley está en LinkedIn, hace clic en una publicación de [!DNL Marketo Measure] y se le redirige al sitio web de Adobe. A continuación, mientras se desplaza por [!DNL Facebook], Haley ve otra publicación de [!DNL Marketo Measure]. Cuando hace clic en esta publicación y se le redirige al sitio de Adobe, la primera sesión web relacionada con [!DNL LinkedIn] finaliza y comienza una nueva sesión relacionada con [!DNL Facebook].

**Canales de búsqueda orgánica o de pago**

Las nuevas sesiones comenzarán cada vez que el usuario acceda al sitio a través de canales de búsqueda orgánica o de pago. Si Haley accede al sitio web de Adobe a través de una búsqueda orgánica e inmediatamente visita el sitio web a través de un anuncio de pago en Google, se crean dos sesiones separadas.

**Tráfico directo web**

Si un visitante llega a su sitio web escribiendo la URL del sitio web en la barra de direcciones, no siempre se inicia una nueva sesión.

Si la primera sesión web de Haley comienza como resultado de una visita desde un sitio de referencia, un canal social o un canal de búsqueda orgánica/de pago y luego visita el sitio a través de Web Direct, esto no provoca el inicio de una nueva sesión.

_Sin embargo_, si la primera sesión web de Haley se originó en Web Direct y luego visita el sitio web a través de _un sitio externo/de referencia_, la primera sesión finalizará y se abrirá una nueva sesión relacionada con el sitio externo/de referencia.

## Sesiones de Google Analytics {#google-analytics-sessions}

Hay algunas similitudes sobre cómo [!DNL Marketo Measure] y Google Analytics definen las sesiones. Para obtener más información sobre cómo Google Analytics define las sesiones, visite: [https://support.google.com/analytics/answer/2731565?hl=en](https://support.google.com/analytics/answer/2731565?hl=en){target="_blank"}
