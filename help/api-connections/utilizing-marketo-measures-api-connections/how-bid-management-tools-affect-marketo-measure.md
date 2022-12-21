---
unique-page-id: 18874720
description: Cómo afectan las herramientas de administración de ofertas [!DNL Marketo Measure] - [!DNL Marketo Measure] - Documentación del producto
title: Cómo afectan las herramientas de administración de ofertas [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---

# Cómo afectan las herramientas de administración de ofertas [!DNL Marketo Measure] {#how-bid-management-tools-affect-marketo-measure}

Descubra cómo las plataformas de administración de ofertas afectan a la variable [!DNL Marketo Measure] la capacidad de rastrear AdWords y BingAds, junto con la configuración de plantillas de seguimiento con nuestros parámetros para garantizar que todo se rastree correctamente.

Kenshoo y Marin son herramientas buenas que permiten a los especialistas en marketing rastrear, administrar y optimizar sus campañas publicitarias con diferentes motores de búsqueda. Para [!DNL Marketo Measure] parámetros que se adjuntarán a estas URL de anuncio, deberá configurar una plantilla de seguimiento con nuestra [!DNL Marketo Measure] parámetros. No es posible conectar las plataformas de publicidad a su [!DNL Marketo Measure] y habilite el etiquetado automático, ya que provoca la [!DNL Marketo Measure] sistema de etiquetado para competir con el sistema de etiquetado de Kenshoo/Marin. Esto hace que nuestros parámetros se modifiquen y se adjunten incorrectamente. Para evitar esto, haga un seguimiento de las plantillas con [!DNL Marketo Measure] es necesario configurar los parámetros de dentro de Kenshoo y Marin.

## Para [!DNL Adwords] Cuentas {#for-adwords-accounts}

Configure una plantilla de seguimiento de la siguiente manera:

* Haga clic en el **[!UICONTROL Campañas]** pestaña .
* Haga clic en el **[!UICONTROL Biblioteca compartida]** en la barra de navegación lateral.
* Haga clic en **Opciones de URL**.
* Junto a &quot;Plantilla de seguimiento&quot;, haga clic en **Editar**.
* Complete la URL:

   * Si TODAS las direcciones URL de la publicidad tienen un &quot;?&quot; en ellos, utilice esta dirección URL:
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * Si NINGUNA de las URL de su publicidad tiene un &quot;?&quot; en ellos, utilice esta dirección URL:
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## Para [!DNL Bing Ads] Cuentas {#for-bing-ads-accounts}

Configure una plantilla de seguimiento de la siguiente manera:

* Haga clic en el **[!UICONTROL Campañas]** pestaña .
* Haga clic en el **[!UICONTROL Biblioteca compartida]** en la barra de navegación lateral.
* Haga clic en **Opciones de URL**.
* Junto a &quot;Plantilla de seguimiento&quot;, haga clic en **Editar**.
* Complete la URL:

   * Si TODAS las direcciones URL de la publicidad tienen un &quot;?&quot; en ellos, utilice esta dirección URL:
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * Si NINGUNA de las URL de su publicidad tiene un &quot;?&quot; en ellos, utilice esta dirección URL:
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
