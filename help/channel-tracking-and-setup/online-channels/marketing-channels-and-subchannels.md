---
unique-page-id: 18874682
description: 'Canales y subcanales de marketing: [!DNL Marketo Measure] - Documentación del producto'
title: Canales y subcanales de marketing
exl-id: fbe2a994-cf6d-439c-af96-a562216434cc
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 3%

---

# Canales y subcanales de marketing {#marketing-channels-and-subchannels}

## Objetivo {#purpose}

Para definir en qué se encuentran un canal y un subcanal [!DNL Marketo Measure], cómo se relacionan con su contenido, la diferencia entre las dos clasificaciones y cómo se utilizan dentro de la variable [!DNL Marketo Measure] aplicación.

## Resumen {#overview}

Los canales de marketing se utilizan para categorizar (o &quot;agrupar&quot;) sus actividades de marketing y facilitar la creación de informes, ambos en la variable [!DNL Marketo Measure] ROI Dash así como en su CRM. [!DNL Marketo Measure] incluye 12 canales predeterminados (que puede personalizar o cambiar de nombre para adaptarlos a las convenciones de su organización), así como la capacidad de crear canales personalizados para un filtrado aún más granular.

Siempre que reciba un visitante de una de las páginas de contenido de su sitio (ya sea que ese contenido sea una página web, una descarga de documentos técnicos, una URL de página, etc.), ese posible cliente se &quot;agrupará&quot; en un canal o subcanal basado en varios parámetros de la UTM que se encuentren en la dirección URL:

* Media
* Origen
* Campaña
* Página de aterrizaje
* Sitio web de referencia

Para personalizar en qué &quot;bloque&quot; se encuentran los posibles clientes en función de sus parámetros de UTM, puede utilizar las reglas de canal. Para obtener más información sobre la configuración y el mantenimiento de las reglas de canal, [haga clic aquí](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

Obtenga información sobre cómo configurar su [Canales en línea](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) y [Canales sin conexión](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md), así como la diferencia entre ellos.

**Canal de marketing**

El canal de marketing es el nivel más amplio de clasificación y puede abarcar una amplia variedad de subcanales. Puede considerar estos como el &quot;tipo&quot; de Subcanal del que provienen sus posibles clientes. Algunos ejemplos de canales de marketing son **Búsqueda de pago, Búsqueda orgánica, Visualización,** y **Social de pago**. El canal de marketing normalmente corresponde al valor del parámetro utm_medium que se encuentra en la dirección URL.

**Subcanal**

Los subcanales son la segunda pieza del rompecabezas al agrupar los posibles clientes entrantes. Los subcanales cuentan exactamente la historia de _which_ se ha utilizado la iteración del canal de marketing. Por ejemplo, en el Canal de marketing social de pago, puede tener subcanales para **AdWords**, **BingAds**, **Facebook**, etc. El subcanal normalmente corresponde al valor del parámetro utm_source que se encuentra en la dirección URL.

## Ejemplo de caso de uso {#use-case-example}

El diagrama siguiente ilustra un ejemplo de canal de marketing, subcanal y contenido basado en una página web con la siguiente dirección URL:

* [http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial](http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial)*

En este caso, el Contenido al que el usuario intenta acceder es la Guía de introducción a la atribución de marketing B2B. [!DNL Marketo Measure] analizará la dirección URL que lleva a este contenido mediante las reglas de canal configuradas en esta organización y las usará para &quot;agrupar&quot; este posible cliente en el canal de marketing &quot;Social pagado&quot; y el subcanal &quot;LinkedIn&quot;.

![](assets/1.jpg)

Más ejemplos...

**Canal de marketing (medio)**

* PPC
* Social de pago
* Social orgánico
* Email
* Eventos y conferencias
* Búsqueda orgánica/SEO
* PR
* Programas de referencia

**Subcanal (origen de punto de contacto)**

* Google AdWords
* BingAds
* Anuncios publicitarios de Facebook
* Analizar
* Doble clic
* Capterra
* Profundizar campañas
* LinkedIn Ads

**Contenido (Documentos técnicos, URL de la página, Publicaciones de blog)**

* www.adobe.com/blog1
* www.adobe.com/whitepaper
* www.adobe.com/sign-up-now
