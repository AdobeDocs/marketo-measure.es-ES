---
unique-page-id: 18874608
description: "[!DNL Marketo Measure] Parámetros - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Parámetros"
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 0%

---

# [!DNL Marketo Measure] Parámetros {#marketo-measure-parameters}

## [!DNL Marketo Measure] Parámetros explicados {#marketo-measure-parameters-explained}

Para obtener más información sobre el uso de UTM, [!DNL Marketo Measure] añade parámetros personalizados a sus publicidades en [!DNL Google] AdWords, Bing Ads y [!DNL Facebook] Anuncios. [!DNL Marketo Measure] se integra con estas plataformas para automatizar la mayor parte del proceso de configuración. Si selecciona utilizar el etiquetado automático, [!DNL Marketo Measure] adjuntará automáticamente sus parámetros a las direcciones URL de sus publicidades. [!DNL Marketo Measure] también descargará automáticamente sus costes de marketing desde las plataformas y los cargará en la variable [!DNL Marketo Measure] aplicación.

Ejemplo de una dirección URL sin parámetros:

`http://adobe.com/landing-page?myParam=foo`

Ejemplo de una dirección URL con [!DNL Marketo Measure] parámetros:

`http://adobe.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Parámetros de AdWords {#adwords-parameters}

* `_bk={keyword}`
   * Representa la palabra clave que la persona utilizó en el motor de búsqueda.
   * Es similar al parámetro de término UTM.

* `_bt={creative}`
   * Representa el ID o nombre creativo.
   * Es similar al parámetro de contenido UTM.

* `_bm={matchtype}`
   * Representa la proximidad con la que se encontró la palabra clave.
   * Los tipos de coincidencia de palabra clave ayudan a controlar las búsquedas en déclencheur de la publicidad. Por ejemplo, podría usar una coincidencia amplia para mostrar su publicidad a una audiencia amplia o podría usar la coincidencia exacta para ponerse en contacto con grupos específicos de clientes.
   * Los tres tipos de coincidencias son: amplio, borroso y exacto.

>[!NOTE]
>
>Para obtener más información sobre los tipos de coincidencia, [este es un artículo relevante de AdWords](https://support.google.com/adwords/answer/2497836?hl=en){target=&quot;_blank&quot;}.

* `_bn={network}`
   * Representa el tipo de red de publicidad - [visualización o búsqueda](https://support.google.com/adwords/answer/1752334?hl=en){target=&quot;_blank&quot;}.
   * Esto es similar al parámetro de origen de la UTM.

* `_bg={adgroupID}`
   * Representa el ID del grupo de publicidad al que pertenece el anuncio

## Parámetros de Bing Ads {#bing-ads-parameters}

* `_bt={adid}`
* `utm_medium=cpc`
* `utm_source=bing`
* `utm_term={keyword}`

## Parámetros de facebook {#facebook-parameters}

* `_bf ={creative}`
   * Representa el ID o nombre creativo
