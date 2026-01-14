---
description: Guía de canales de marketing y subcanales para usuarios de Marketo Measure
title: Canales y subcanales de marketing
exl-id: fbe2a994-cf6d-439c-af96-a562216434cc
feature: Channels
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 95%

---

# Canales y subcanales de marketing {#marketing-channels-and-subchannels}

## Finalidad {#purpose}

Para definir qué son un canal y un subcanal en [!DNL Marketo Measure], su relación con su contenido, la diferencia entre las dos clasificaciones y su uso dentro de la aplicación de [!DNL Marketo Measure].

## Información general {#overview}

Los canales de marketing se utilizan para ayudar a categorizar (o “agrupar”) las actividades de marketing con el fin de facilitar los informes, tanto en el ROI Dash de [!DNL Marketo Measure], como en su CRM. [!DNL Marketo Measure] incluye 12 canales listos para usar (que puede personalizar o cambiar de nombre para adaptarlos a las convenciones de su organización), así como la capacidad de crear canales personalizados para un filtrado aún más granular.

Cada vez que reciba un visitante a una de las páginas de Contenido de su sitio (tanto si ese Contenido es una Página web, una Descarga de documentos técnicos, una Dirección URL de página, etc.), ese Cliente potencial se “agrupa” en un canal o subcanal en función de varios parámetros de UTM encontrados en la dirección URL:

* Medio
* Origen
* Campaña
* Página de destino
* Sitio web de referencia

Para personalizar el “bloque” en el que se ubicarán sus Clientes potenciales en función de sus parámetros de UTM, puede utilizar Reglas de canal. Para obtener más información sobre la configuración y el mantenimiento de sus Reglas del canal, [haga clic aquí](/help/channel-tracking-and-setup/online-custom-channel-setup.md).

Obtenga información sobre cómo configurar sus [Canales en línea](/help/channel-tracking-and-setup/online-custom-channel-setup.md) y [Canales sin conexión](/help/channel-tracking-and-setup/offline-custom-channel-setup.md), así como la diferencia entre ellos.

**Canal de marketing**

El Canal de marketing es el nivel de clasificación más amplio y puede cubrir una amplia variedad de subcanales. Puede considerarlos el “tipo” de Subcanal del que provienen sus clientes potenciales. Algunos ejemplos de Canales de marketing son **Búsqueda de pago, Búsqueda orgánica, Visualización** y **Social de pago**. El Canal de marketing suele corresponder al valor del parámetro utm_medium encontrado en su dirección URL.

**Subcanal**

Los subcanales son la segunda pieza del rompecabezas al agrupar los Clientes potenciales entrantes. Los subcanales cuentan la historia de exactamente _qué_ iteración de su Canal de marketing se utilizó. Por ejemplo, dentro del Canal de marketing social de pago, puede tener Subcanales para **AdWord**, **BingAds**, **Facebook**, etc. El Subcanal suele corresponder al valor del parámetro utm_source encontrado en su dirección URL.

## Ejemplo de caso de uso {#use-case-example}

El diagrama siguiente ilustra un ejemplo de un Canal de marketing, Subcanal y Contenido basado en una página web con la siguiente URL:

* [http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&utm_medium=paidsocial](http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&utm_medium=paidsocial)*

En este caso, el Contenido al que el usuario intenta acceder es la Guía de introducción a la atribución de marketing B2B. [!DNL Marketo Measure] analizará la URL que lleva a este Contenido mediante las Reglas de canal configuradas en esta organización y las utilizará para “agrupar” este cliente potencial en el Canal de marketing “Social de pago” y el Subcanal “LinkedIn”.

![En este caso, el contenido al que el usuario intenta acceder es](assets/online-channels-1.png)

Más ejemplos…

**Canal de marketing (Medio)**

* PPC
* Social de pago
* Social orgánico
* Correo electrónico
* Eventos y conferencias
* Búsqueda orgánica/SEO
* PR
* Programas de referencia

**Subcanal (origen del punto de contacto)**

* Google AdWords
* Bing Ads
* Anuncios publicitarios de Facebook
* Rollo de anuncios
* Doble clic
* Capterra
* Campañas de goteo
* LinkedIn Ads

**Contenido (documentos técnicos, direcciones URL de la página, publicaciones del blog)**

* www.adobe.com/blog1
* www.adobe.com/whitepaper
* www.adobe.com/sign-up-now
