---
unique-page-id: 18874720
description: Cómo afectan las herramientas de Administración de ofertas [!DNL Marketo Measure] - [!DNL Marketo Measure] - Documentación del producto
title: Cómo afectan a  [!DNL Marketo Measure] las herramientas de administración de ofertas
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
feature: APIs, Integration, UTM Parameters
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 3%

---

# Cómo afectan a [!DNL Marketo Measure] las herramientas de administración de ofertas  {#how-bid-management-tools-affect-marketo-measure}

Descubra cómo las plataformas de administración de ofertas afectan a [!DNL Marketo Measure] La capacidad de rastrear AdWords y BingAds, junto con la forma de configurar plantillas de seguimiento con nuestros parámetros para garantizar que todo se rastree correctamente.

Kenshoo y Marin son buenas herramientas que permiten a los especialistas en marketing rastrear, administrar y optimizar sus campañas publicitarias con diferentes motores de búsqueda. Para que [!DNL Marketo Measure] parámetros que se añadirán a estas direcciones URL de publicidad, deberá configurar una plantilla de seguimiento con nuestra [!DNL Marketo Measure] parámetros. No es posible conectar sus plataformas de publicidad a su [!DNL Marketo Measure] y habilite el etiquetado automático, ya que provoca la [!DNL Marketo Measure] sistema de etiquetado para competir con el sistema de etiquetado de Kenshoo/Marin. Esto provoca que nuestros parámetros se modifiquen y se adjunten incorrectamente. Para evitar esto, las plantillas de seguimiento con [!DNL Marketo Measure] Los parámetros deben configurarse dentro de Kenshoo y Marin.

## Para [!DNL Adwords] Cuentas {#for-adwords-accounts}

Configure una plantilla de seguimiento como se indica a continuación:

* Haga clic en **[!UICONTROL Campañas]** pestaña.
* Haga clic en **[!UICONTROL Biblioteca compartida]** en la barra de navegación lateral.
* Clic **Opciones de URL**.
* Junto a Plantilla de seguimiento, haga clic en **Editar**.
* Rellene la dirección URL:

   * Si TODAS las direcciones URL de su anuncio tienen un signo &quot;?&quot; en ellos, utilice esta dirección URL:
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * Si NINGUNA de las URL de anuncio tiene un &quot;?&quot; en ellos, utilice esta dirección URL:
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## Para [!DNL Bing Ads] Cuentas {#for-bing-ads-accounts}

Configure una plantilla de seguimiento como se indica a continuación:

* Haga clic en **[!UICONTROL Campañas]** pestaña.
* Haga clic en **[!UICONTROL Biblioteca compartida]** en la barra de navegación lateral.
* Clic **Opciones de URL**.
* Junto a Plantilla de seguimiento, haga clic en **Editar**.
* Rellene la dirección URL:

   * Si TODAS las direcciones URL de su anuncio tienen un signo &quot;?&quot; en ellos, utilice esta dirección URL:
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * Si NINGUNA de las URL de anuncio tiene un &quot;?&quot; en ellos, utilice esta dirección URL:
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
