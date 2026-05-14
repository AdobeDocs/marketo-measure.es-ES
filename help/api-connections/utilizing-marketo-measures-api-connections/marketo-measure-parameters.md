---
unique-page-id: 18874608
description: '[!DNL Marketo Measure] parámetros - [!DNL Marketo Measure]'
title: Parámetros de [!DNL Marketo Measure]
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
feature: APIs, Integration, UTM Parameters
TQID: https://experienceleague.adobe.com/IurdaUgr2R1vxfOP4bcXp8TSUj4ymkA-R9kZ9put4Ug
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
feature_v2:
  - id: fb43f4c1-87d9-4081-8df1-6fe7e6e5cdc8
subfeature_v2:
  - id: fabdc8ff-b627-44fc-b09d-973166bc2b14
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 243
ht-degree: 91%

---

# Parámetros de [!DNL Marketo Measure] {#marketo-measure-parameters}

## Parámetros de [!DNL Marketo Measure] explicados {#marketo-measure-parameters-explained}

Para obtener más información del uso de UTM, [!DNL Marketo Measure] añade parámetros personalizados a sus anuncios en AdWords, de [!DNL Google] Bing Ads y Anuncios de [!DNL Facebook]. [!DNL Marketo Measure] se integra con estas plataformas para automatizar la mayor parte del proceso de configuración. Si decide utilizar el etiquetado automático, [!DNL Marketo Measure] adjuntará automáticamente sus parámetros a las direcciones URL de sus anuncios. [!DNL Marketo Measure] también descargará automáticamente los costes de marketing de las plataformas y los cargará en la aplicación de [!DNL Marketo Measure].

Ejemplo de una dirección URL sin parámetros:

`http://adobe.com/landing-page?myParam=foo`

Ejemplo de una dirección URL con parámetros de [!DNL Marketo Measure]:

`http://adobe.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Parámetros de AdWords {#adwords-parameters}

* `_bk={keyword}`
   * Representa la palabra clave que la persona utilizó en el motor de búsqueda.
   * Es similar al parámetro de término de UTM.

* `_bt={creative}`
   * Representa el nombre o el ID de creativo.
   * Es similar al parámetro de contenido de UTM.

* `_bm={matchtype}`
   * Representa la coincidencia de la palabra clave.
   * Los tipos de concordancia de palabras clave ayudan a controlar qué búsquedas activan su anuncio. Por ejemplo, puede utilizar la coincidencia amplia para mostrar su anuncio a un público amplio o puede utilizar la coincidencia exacta para centrarse en grupos específicos de clientes.
   * Los tres tipos de coincidencia son: amplia, difusa y exacta.

>[!TIP]
>
>Para obtener más información sobre los tipos de coincidencia, [aquí tiene un artículo de AdWords relevante](https://support.google.com/adwords/answer/2497836?hl=es){target="_blank"}.

* `_bn={network}`
   * Representa el tipo de red de anuncios: [visualización o búsqueda](https://support.google.com/adwords/answer/1752334?hl=es){target="_blank"}.
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

## Parámetros de Facebook {#facebook-parameters}

* `_bf ={creative}`
   * Esto representa el nombre o el ID de creativo
