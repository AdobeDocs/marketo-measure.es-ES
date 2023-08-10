---
unique-page-id: 18874608
description: "[!DNL Marketo Measure] Parámetros - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Parámetros"
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
feature: APIs, Integration, UTM Parameters
source-git-commit: 3bad77a72c0dea6caf0daadbb594f10f791af715
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---

# Parámetros de [!DNL Marketo Measure] {#marketo-measure-parameters}

## [!DNL Marketo Measure] Parámetros explicados {#marketo-measure-parameters-explained}

Para obtener más información del uso de UTM, [!DNL Marketo Measure] añade parámetros personalizados a sus anuncios en [!DNL Google] AdWords, Bing Ads y [!DNL Facebook] Anuncios. [!DNL Marketo Measure] se integra con estas plataformas para automatizar la mayor parte del proceso de configuración. Si decide utilizar el etiquetado automático, [!DNL Marketo Measure] adjuntará automáticamente sus parámetros a las direcciones URL de sus anuncios. [!DNL Marketo Measure] también descargará automáticamente los costes de marketing de las plataformas y los cargará en [!DNL Marketo Measure] aplicación.

Ejemplo de una dirección URL sin parámetros:

`http://adobe.com/landing-page?myParam=foo`

Ejemplo de una dirección URL con [!DNL Marketo Measure] parámetros:

`http://adobe.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Parámetros de AdWords {#adwords-parameters}

* `_bk={keyword}`
   * Representa la palabra clave que la persona utilizó en el motor de búsqueda.
   * Es similar al parámetro de término de UTM.

* `_bt={creative}`
   * Representa el nombre o el ID de creatividad.
   * Es similar al parámetro de contenido de UTM.

* `_bm={matchtype}`
   * Representa la coincidencia de la palabra clave.
   * Los tipos de coincidencia de palabras clave ayudan a controlar qué búsquedas almacenan en déclencheur su anuncio. Por ejemplo, puede utilizar la coincidencia amplia para mostrar su anuncio a una audiencia amplia o puede utilizar la coincidencia exacta para centrarse en grupos específicos de clientes.
   * Los tres tipos de coincidencia son: amplia, difusa y exacta.

>[!TIP]
>
>Para obtener más información sobre los tipos de coincidencia, consulte [Este es un artículo relevante de AdWords](https://support.google.com/adwords/answer/2497836?hl=en){target="_blank"}.

* `_bn={network}`
   * Representa el tipo de red de publicidad - [visualización o búsqueda](https://support.google.com/adwords/answer/1752334?hl=en){target="_blank"}.
   * Esto es similar al parámetro de origen de UTM.

* `_bg={adgroupID}`
   * Representa el ID del grupo de publicidad al que pertenece el anuncio

>[!NOTE]
>
>No se admiten parámetros de URL de redireccionamiento.

## Parámetros de Bing Ads {#bing-ads-parameters}

* `_bt={adid}`
* `utm_medium=cpc`
* `utm_source=bing`
* `utm_term={keyword}`

## Parámetros de facebook {#facebook-parameters}

* `_bf ={creative}`
   * Representa el nombre o el ID de creatividad
