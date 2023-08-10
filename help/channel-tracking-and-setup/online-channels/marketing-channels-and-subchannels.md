---
unique-page-id: 18874682
description: 'Canales y subcanales de marketing: [!DNL Marketo Measure] - Documentación del producto'
title: Canales y subcanales de marketing
exl-id: fbe2a994-cf6d-439c-af96-a562216434cc
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 5%

---

# Canales y subcanales de marketing {#marketing-channels-and-subchannels}

## Finalidad {#purpose}

Para definir en qué se encuentran un canal y un subcanal [!DNL Marketo Measure], su relación con el contenido, la diferencia entre las dos clasificaciones y su uso en el [!DNL Marketo Measure] aplicación.

## Información general {#overview}

Los canales de marketing se utilizan para categorizar (o &quot;agrupar&quot;) las actividades de marketing con el fin de facilitar los informes, tanto en el [!DNL Marketo Measure] ROI Dash, así como en su CRM. [!DNL Marketo Measure] incluye 12 canales predeterminados (que puede personalizar o cambiar de nombre para adaptarlos a las convenciones de su organización), así como la capacidad de crear canales personalizados para un filtrado aún más granular.

Cada vez que reciba un visitante a una de las páginas de contenido de su sitio (ya sea una página web, una descarga de documentos técnicos, una dirección URL de página, etc.), ese posible cliente se &quot;agrupa&quot; en un canal o subcanal en función de varios parámetros de UTM encontrados en la dirección URL:

* Medio
* Origen
* Campaña
* Página de aterrizaje
* Sitio web de referencia

Para personalizar el &quot;bloque&quot; en el que se ubicarán los posibles clientes en función de sus parámetros de UTM, puede utilizar Reglas de canal. Para obtener más información sobre la configuración y el mantenimiento de las reglas del canal, [haga clic aquí](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

Obtenga información sobre cómo configurar su [Canales en línea](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) y [Canales sin conexión](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md), así como la diferencia entre ellos.

**Canal de marketing**

El canal de marketing es el nivel de clasificación más amplio y puede cubrir una amplia variedad de subcanales. Puede considerarlos el &quot;tipo&quot; de subcanal del que provienen sus posibles clientes. Algunos ejemplos de canales de marketing son **Búsqueda de pago, Búsqueda orgánica, Visualización,** y **Social de pago**. El canal de marketing suele corresponder al valor del parámetro utm_medium encontrado en la dirección URL.

**Subcanal**

Los subcanales son la segunda pieza del rompecabezas al agrupar los posibles clientes entrantes. Los subcanales cuentan la historia de exactamente _que_ Se ha utilizado la iteración del canal de marketing. Por ejemplo, dentro del Canal de marketing social de pago, puede tener Subcanales para **AdWord**, **BingAds**, **Facebook**, etc. El subcanal suele corresponder al valor del parámetro utm_source encontrado en la dirección URL.

## Ejemplo de caso de uso {#use-case-example}

El diagrama siguiente ilustra un ejemplo de canal de marketing, subcanal y contenido basado en una página web con la siguiente URL:

* [http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial](http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial)*

En este caso, el contenido al que el usuario intenta acceder es la Guía de introducción a la atribución de marketing B2B. [!DNL Marketo Measure] Analizará la URL que lleva a este contenido mediante las reglas de canal configuradas en esta organización y las utilizará para &quot;agrupar&quot; este posible cliente en el canal de marketing &quot;Social de pago&quot; y el subcanal &quot;LinkedIn&quot;.

![](assets/1.jpg)

Más ejemplos...

**Canal de marketing (medio)**

* PPC
* Social de pago
* Social orgánico
* Correo electrónico
* Eventos y conferencias
* Búsqueda orgánica/SEO
* PR
* Programas de referencia

**Subcanal (origen de punto de contacto)**

* Google AdWords
* Bing Ads
* Anuncios publicitarios de Facebook
* Adroll
* Doble clic
* Capterra
* Campañas de goteo
* LinkedIn Ads

**Contenido (documentos técnicos, direcciones URL de la página, publicaciones del blog)**

* www.adobe.com/blog1
* www.adobe.com/whitepaper
* www.adobe.com/sign-up-now
