---
description: Cómo afectan las herramientas de administración de ofertas a la guía de [!DNL Marketo Measure] para los usuarios de Marketo Measure
title: Cómo afectan las herramientas de administración de ofertas a [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
feature: APIs, Integration, UTM Parameters
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: fb43f4c1-87d9-4081-8df1-6fe7e6e5cdc8
    internal-label: APIs
  - id: 7da342c5-06ee-5869-b3e8-b73d5bf75a9d
    internal-label: Integration
  - id: 3968a9c0-3e19-5a76-a1f0-f5a9a986c53a
    internal-label: UTM Parameters
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%
---
# Cómo afectan las herramientas de administración de ofertas a [!DNL Marketo Measure] {#how-bid-management-tools-affect-marketo-measure}

Descubra cómo las plataformas de administración de ofertas afectan la capacidad de [!DNL Marketo Measure] para rastrear AdWords y BingAds, junto con cómo configurar plantillas de seguimiento con nuestros parámetros para garantizar que todo se rastree correctamente.

Kenshoo y Marin son excelentes herramientas que permiten a los especialistas en marketing rastrear, administrar y optimizar sus campañas publicitarias con diferentes motores de búsqueda. Para que [!DNL Marketo Measure] parámetros se adjunten a estas direcciones URL de anuncios, debe configurar una plantilla de seguimiento con nuestros [!DNL Marketo Measure] parámetros. No es posible conectar las plataformas de anuncios a la cuenta de [!DNL Marketo Measure] y habilitar el etiquetado automático, ya que hace que el sistema de etiquetado de [!DNL Marketo Measure] compita con el sistema de etiquetado de Kenshoo/Marin. Esto provoca que nuestros parámetros se modifiquen y se adjunten incorrectamente. Para evitar esto, es necesario configurar las plantillas de seguimiento con [!DNL Marketo Measure] parámetros dentro de Kenshoo y Marin.

## Para [!DNL Adwords] cuentas {#for-adwords-accounts}

Configure una plantilla de seguimiento como se indica a continuación:

* Haga clic en la ficha **[!UICONTROL Campañas]**.
* Haga clic en el vínculo **[!UICONTROL Biblioteca compartida]** en la barra de navegación lateral.
* Haga clic en **Opciones de URL**.
* Junto a &quot;Plantilla de seguimiento&quot;, haz clic en **Editar**.
* Rellene la dirección URL:

  * Si TODAS las direcciones URL de su anuncio tienen un signo &quot;?&quot; en ellos, utilice esta dirección URL:
    * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
  * Si NINGUNA de las URL de anuncio tiene un &quot;?&quot; en ellos, utilice esta dirección URL:
    * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## Para [!DNL Bing Ads] cuentas {#for-bing-ads-accounts}

Configure una plantilla de seguimiento como se indica a continuación:

* Haga clic en la ficha **[!UICONTROL Campañas]**.
* Haga clic en el vínculo **[!UICONTROL Biblioteca compartida]** en la barra de navegación lateral.
* Haga clic en **Opciones de URL**.
* Junto a &quot;Plantilla de seguimiento&quot;, haz clic en **Editar**.
* Rellene la dirección URL:

  * Si TODAS las direcciones URL de su anuncio tienen un signo &quot;?&quot; en ellos, utilice esta dirección URL:
    * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
  * Si NINGUNA de las URL de anuncio tiene un &quot;?&quot; en ellos, utilice esta dirección URL:
    * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
