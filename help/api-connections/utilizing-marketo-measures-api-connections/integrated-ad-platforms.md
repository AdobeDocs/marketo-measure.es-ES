---
unique-page-id: 18874594
description: 'Plataformas de publicidad integradas: [!DNL Marketo Measure]'
title: Plataformas de anuncios integradas
exl-id: df30ee8a-8b07-4f14-94e8-cc482fca8b18
feature: APIs, Integration
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '1661'
ht-degree: 0%

---

# Plataformas de anuncios integradas {#integrated-ad-platforms}

[!DNL Marketo Measure] tiene conexiones de API con Google AdWords, Microsoft BingAds, [!DNL Facebook] Ads y haga doble clic en Campaign Manager. A través de estas conexiones API, [!DNL Marketo Measure] es capaz de extraer datos fácilmente y enviarlos a su CRM junto con la aplicación de comprador externa. No es necesario cargar manualmente los costes ni los datos. En su lugar, las cuentas simplemente deben estar conectadas y autorizadas al [!DNL Marketo Measure] aplicación. [!DNL Marketo Measure] descargará automáticamente los costes de marketing de las plataformas y los cargará en el [!DNL Marketo Measure] aplicación. Si selecciona habilitar el etiquetado automático para AdWords, BingAds o [!DNL Facebook] Anuncios, [!DNL Marketo Measure] adjuntará automáticamente sus parámetros a las direcciones URL de sus anuncios.

## Cómo conectar plataformas de publicidad {#how-to-connect-ad-platforms}

Antes de entrar en detalles específicos de cada plataforma, veremos cómo conectar cualquiera de estas cuentas a [!DNL Marketo Measure]. Primero inicie sesión en [!DNL Marketo Measure] y vaya a la **[!UICONTROL Configuración]** en la opción **[!UICONTROL Mi cuenta]** en la parte superior izquierda de la pantalla. A continuación, seleccione **[!UICONTROL Conexiones]** en el **[!UICONTROL Integraciones]** de la izquierda.

Como se muestra en la siguiente imagen, verá un botón para configurar nuevas conexiones de anuncios.

![](assets/2.png)

Después de hacer clic en [!UICONTROL Configuración de la conexión de nuevos anuncios] botón, aparecerá una ventana (que se muestra a continuación) con cuatro anuncios [!UICONTROL conectar]tipos de iones. Haga clic en conectar y aparecerá otra ventana en la que se solicitarán credenciales. Introduzca las credenciales de y haga clic en [!UICONTROL autorizar] para conectar la cuenta a [!DNL Marketo Measure].

![](assets/select-account-type.png)

## Google AdWords {#google-adwords}

Cuando crea sus anuncios en [!DNL Google AdWords]Además, se le recomienda que etiquete sus campañas de una de las tres maneras siguientes: etiquetado manual, etiquetado automático o creación de una plantilla de seguimiento. El etiquetado manual de la URL de AdWords depende de que defina y añada los parámetros al final de las URL de los anuncios. El etiquetado manual permite que cualquier plataforma que no sea de Google lea fácilmente los datos recopilados por los parámetros.

La plantilla de seguimiento es una herramienta que proporciona Google para agregar lo que denomina parámetros ValueTrack. Funcionan de la misma manera que las UTM y otros parámetros de etiquetado.

## Qué sucede cuando el etiquetado automático está habilitado {#what-happens-when-auto-tagging-is-enabled}

[!DNL Marketo Measure] Busca plantillas de seguimiento en su [!DNL AdWords] cuenta:

* *Opción A*: se encuentra la plantilla de seguimiento. [!DNL Marketo Measure] añade sus parámetros a la plantilla.
* *Opción B*: se encuentra el redireccionamiento de terceros. Si se encuentra una redirección de terceros en la plantilla de seguimiento, [!DNL Marketo Measure] no puede realizar ninguna acción. Deberá añadir manualmente la variable [!DNL Marketo Measure] al sistema de terceros. Un ejemplo de redireccionamiento de terceros sería una herramienta de gestión de ofertas como Kenshoo o Marin. Obtenga más información sobre cómo [las herramientas de gestión de ofertas afectan a [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

* *Opción C*: no se encuentra ninguna plantilla de seguimiento. [!DNL Marketo Measure] analizará todas las URL de destino de publicidad para la [!DNL Marketo Measure] parámetros. En función del análisis, si:
   * Se han encontrado parámetros: la configuración ha finalizado.
   * No se han encontrado parámetros: [!DNL Marketo Measure] adjuntará sus parámetros al final de las URL de destino de la publicidad. [!DNL Marketo Measure] añade nuevos anuncios en un plazo de dos horas tras su creación. Tenga en cuenta que los parámetros no se añaden a una plantilla.

Obtenga más información sobre nuestras [[!DNL AdWords] funcionalidad de etiquetado automático](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md){target="_blank"}.

## Cómo activar [!DNL Marketo Measure] Etiquetado automático de AdWords {#how-to-enable-marketo-measure-auto-tagging-for-adwords}

Antes de habilitar [!DNL Marketo Measure] etiquetado automático, **Asegúrese de tener una plantilla de seguimiento habilitada en el nivel de cuenta, campaña o grupo de publicidad de su cuenta de AdWords. Esto es necesario para cualquier cuenta de AdWords que tenga [!DNL Marketo Measure] etiquetado automático habilitado.** Al habilitar una plantilla de seguimiento, se evitan pérdidas en los datos del historial de rendimiento de las publicidades. Tenga en cuenta que habilitar las plantillas de seguimiento en los niveles de palabra clave, vínculo de sitio o anuncio hará que el anuncio pase por el proceso de revisión y aprobación y puede reiniciar potencialmente el historial de rendimiento de los anuncios. Si no hay ninguna plantilla de seguimiento habilitada, [!DNL Marketo Measure] adjuntará el [!DNL Marketo Measure] el seguimiento de parámetros directamente a la &quot;URL final&quot; del anuncio, lo que también puede causar la pérdida de datos del historial de anuncios.

Una vez que tenga una plantilla de seguimiento, siga las instrucciones a continuación para habilitar [!DNL Marketo Measure] Etiquetado automático. Nota: [!DNL Marketo Measure] también etiquetará automáticamente cualquier anuncio pausado en su cuenta.

1. Inicie sesión en su [!DNL Marketo Measure] cuenta en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

1. Ir a [!UICONTROL Mi cuenta] > [!UICONTROL Configuración] > [!UICONTROL Integraciones] > [!UICONTROL Conexiones].

   ![](assets/4.png)

1. Haga clic en el icono de lápiz junto a la cuenta de AdWords que tendrá. [!DNL Marketo Measure] etiquetado automático habilitado.

   ![](assets/5.png)

1. En la esquina superior derecha, active la opción **[!UICONTROL Etiquetado automático]** cambiar a **[!UICONTROL Sí]**. En la parte inferior de la página, haga clic en **[!UICONTROL Más información]** para expandir el cuadro de texto, haga clic en **[!UICONTROL Guardar]**. Se ha completado la configuración del etiquetado automático.

   ![](assets/6.png)

## Cómo configurar una plantilla de seguimiento en AdWords con [!DNL Marketo Measure] Parámetros {#how-to-set-up-a-tracking-template-in-adwords-with-marketo-measure-parameters}

Tenga en cuenta que debe agregar plantillas de seguimiento en las [!UICONTROL Cuenta], [!UICONTROL Campaign] o el nivel de grupo de publicidad en AdWords. Si agrega Plantillas de seguimiento a los niveles de Palabra clave, Vínculo de sitio o Anuncio, su anuncio deberá pasar por el proceso de revisión y aprobación y se arriesga a reiniciar el historial de rendimiento de sus anuncios. Más información sobre [creación de plantillas de seguimiento](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"}.

1. Inicie sesión en su [!DNL Google AdWords] Cuenta.
1. Vaya a su [!UICONTROL Campañas] vista desde la barra de navegación izquierda
1. Vaya a &quot;[!UICONTROL Configuración]&quot;, también en la barra de navegación izquierda
1. Cambie a &quot;[!UICONTROL Configuración de cuenta]&quot; vista en la parte superior
1. Expanda el &quot;[!UICONTROL Seguimiento]&quot; sección
1. Pegue una de las siguientes cadenas de texto en la plantilla de seguimiento para establecer el valor de la plantilla:

   * Si tiene signos de interrogación en TODAS las direcciones URL, utilice el siguiente texto:

   `{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

   * Si no tiene signos de interrogación en ninguna de las direcciones URL, agregue el siguiente texto:

   `{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}*`

   Para evitar que se produzcan errores al etiquetar manualmente las direcciones URL, normalmente se recomienda generar los parámetros de UTM automáticamente. Esto no tiene que significar el etiquetado automático con AdWords o [!DNL Marketo Measure] parámetros, existen varias herramientas que simplifican el proceso al generar automáticamente los parámetros de la URL en función de la información proporcionada.

   >[!TIP]
   >
   >Si se produce un error que indica que la plantilla de seguimiento no es válida, intente borrar la caché del explorador y volver a intentarlo, lo que a menudo soluciona el problema.

## Cómo generar automáticamente etiquetas UTM para [!DNL Google AdWords] {#how-to-automatically-generate-utm-tags-for-google-adwords}

Al principio, puede parecer difícil crear etiquetas de UTM, pero hay muchas herramientas disponibles para crear fácilmente direcciones URL con parámetros de UTM. Puede utilizar cualquiera de los siguientes recursos o buscar más herramientas en la web. Tenga en cuenta que [!DNL Marketo Measure] no respalda ni garantiza nada con estas plataformas y herramientas.

**[!DNL Google URL]Generador**

El Generador de URL de Google es una herramienta estándar para crear direcciones URL con formato correcto mediante etiquetas UTM. Introduzca la URL y el valor deseado de cada parámetro y haga clic en &quot;[!UICONTROL Generar URL]&quot;. Es una herramienta ideal si solo tiene que etiquetar un puñado de direcciones URL. Acceso a la herramienta [aquí](https://support.google.com/analytics/answer/1033867?hl=es){target="_blank"}.

**Hoja de cálculo de Google generada por EpikOne**

Esta hoja de cálculo tiene una fórmula que genera automáticamente las direcciones URL de destino etiquetadas. Es una buena herramienta si necesita etiquetar un gran número de vínculos. Acceso a la hoja de cálculo [aquí](https://spreadsheets.google.com/ccc?key=p7c_HKcmspSUfEYSO0gskKw&amp;hl=en){target="_blank"}.

**Herramienta de etiquetado de enlaces de Rafflecopter**

La hoja de cálculo creada por Rafflecopter es una versión modificada de [!DNL EpikOne's] hoja de cálculo. También contiene una fórmula que generará automáticamente vínculos de destino etiquetados para que los utilice.

Cada una de estas herramientas tiene instrucciones detalladas sobre cómo utilizarla y modificarla para adaptarla a sus necesidades. La herramienta está disponible [aquí](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"}.

**Effin Amazing UTM Builder**

Esta herramienta es una extensión de Chrome que le permite generar rápidamente etiquetas UTM. Encontrarlo. [aquí](https://chrome.google.com/webstore/detail/effin-amazing-utm-builder/eoaapiimcaimddnfhfnifgkinmpcbccp?hl=en){target="_blank"}.

## Anuncios de Bing {#bing-ads}

Bing Ads es una plataforma integrada que le permite habilitar el etiquetado automático para direcciones URL o utilizar una herramienta de terceros, como [!DNL Marketo Measure], para etiquetar anuncios. [!DNL Bing Ads] también se basa en parámetros de UTM.

La función de etiquetado automático de Bing Ads agrega los siguientes parámetros de UTM:

* Utm_source
* Utm_medium
* Utm_term

El etiquetado automático de Bing Ads también agrega el siguiente parámetro personalizado:

`_bt={adid}`

La cadena tendría este aspecto:

`{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`

Es importante tener en cuenta que [!DNL Bing Ads] le permite añadir aún más parámetros utilizando sus etiquetas personalizadas en las direcciones URL finales para obtener más granularidad, si lo desea.

Si lo desea, puede utilizar una plantilla de seguimiento, pero no es necesaria para lo siguiente [!DNL Bing Ads] y [!DNL Marketo Measure] para integrar. Esto se debe a [!DNL Bing] permite editar los anuncios sin cambiar el historial, por lo que [!DNL Marketo Measure] puede actualizar la dirección URL de destino.

El etiquetado automático debe habilitarse mediante [!DNL Marketo Measure] para que el [!DNL Marketo Measure] Los parámetros de se pueden añadir automáticamente. No hay riesgo de perder el historial de rendimiento de anuncios anteriores con Bing Ads.

Visite la [[!DNL Bing Ads]](https://advertise.bingads.microsoft.com/en-us/blog/post/august-2016/upgraded-urls-now-available-in-bing-ads-an-easier-way-to-manage-your-tracking-urls){target="_blank"} para obtener más información sobre cómo añadir etiquetas en su plataforma.

## Anuncios publicitarios de Facebook {#facebook-ads}

El [!DNL Marketo Measure] integración con [!DNL Facebook] le permite descargar automáticamente información de publicidad y etiquetar la dirección URL con sus parámetros. [!DNL Marketo Measure] extraerá la información de la campaña y del conjunto de anuncios a través del etiquetado automático. El conjunto de anuncios rellenará el campo Nombre del grupo de anuncios. Para obtener más información sobre la configuración de etiquetas de URL en la [!DNL Facebook] plataforma, visite la [!DNL Facebook] [negocio](https://www.facebook.com/business/help/1016122818401732/?ref=u2u){target="_blank"} página.

Antes de habilitar el etiquetado automático con [!DNL Facebook Ads]Sin embargo, es importante exportar el historial de rendimiento anterior como CSV. En este punto, cuando [!DNL Marketo Measure] etiquetas [!DNL Facebook Ads] con su parámetro _bf, [!DNL Facebook] lee los anuncios como nuevos y borra el historial de rendimiento. Por lo tanto, es importante exportar un registro del rendimiento anterior si eso es algo de valor para usted y su organización.

Tenga en cuenta que puede conectar su [!DNL Facebook] cuenta en cualquier momento a [!DNL Marketo Measure] aplicación y no se perderán datos: solo cuando el etiquetado automático esté habilitado se borrará el historial de rendimiento.

Consulte [este artículo](https://www.facebook.com/business/help/393890194130036){target="_blank"} de Facebook para obtener más información sobre la exportación [!DNL Facebook] Informes de publicidad.

## Contenido patrocinado por linkedIn {#linkedin-sponsored-content}

La integración de LinkedIn permite [!DNL Marketo Measure] para etiquetar direcciones URL de destino en [!DNL LinkedIn] Contenido patrocinado, que en última instancia permite [!DNL Marketo Measure] para seguir a un usuario a través de todo el recorrido de puntos de contacto y asignar la actividad de nuevo a la actividad específica [!DNL LinkedIn] Campaign y Creative. Esto proporciona perspectivas a los clientes sobre el ROI de su [!DNL LinkedIn] actividad. [!DNL Marketo Measure] buscará creativos con un único [!DNL LinkedIn] Compartir y agregar un `?_bl={creativeId}` al final del mismo.

Porque [!DNL LinkedIn] Las acciones pueden utilizarse en varias campañas y elementos creativos. Pedimos a los clientes que no copien, clonen o dupliquen elementos creativos existentes para que puedan mantener su exclusividad. Si se encuentran recursos compartidos y se detectan para que solo se utilicen en un creativo, [!DNL Marketo Measure] Puede etiquetar el recurso compartido tal cual sin tener que recrear ningún elemento creativo o compartido, y el historial de todos los anuncios (impresiones, clics, recursos compartidos) permanecerá.

Tan pronto como se encuentre un recurso compartido para compartirlo entre varios creativos, [!DNL Marketo Measure] tendrá que pasar por un proceso de pausa, copia y reetiquetado para crear un conjunto único. [!DNL Marketo Measure] pausará y archivará los creativos en directo, lo que significa que el creativo que contiene las impresiones, los clics y los recursos compartidos en medios sociales también se archivará.

## Plataformas no integradas {#non-integrated-platforms}

Para plataformas que no están integradas con [!DNL Marketo Measure], el [!DNL Marketo Measure] no se puede utilizar la funcionalidad de etiquetado automático. Los parámetros deberán añadirse manualmente.
