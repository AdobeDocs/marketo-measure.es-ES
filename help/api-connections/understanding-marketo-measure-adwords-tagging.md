---
description: Entender las instrucciones de etiquetado de  [!DNL Marketo Measure] AdWords para usuarios de Marketo Measure
title: 'Información sobre el etiquetado de AdWords de  [!DNL Marketo Measure] '
exl-id: c6658766-d3a8-46ed-b2d2-826eb61ce269
feature: APIs, Integration, UTM Parameters
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 6%

---

# Explicación del etiquetado de AdWords [!DNL Marketo Measure] {#understanding-marketo-measure-adwords-tagging}

Para realizar un seguimiento de los anuncios a un nivel muy granular, las URL de destino de anuncio deben ser únicas. Para ello, el etiquetado automático de [!DNL Marketo Measure] agrega automáticamente parámetros de seguimiento a las direcciones URL de destino de anuncio de sus anuncios de [!DNL AdWords]. Echemos un vistazo al ejemplo siguiente.

La siguiente URL no proporcionará datos granulares:

* `http://example.com/landing-page?myParam=foo`

Sin embargo, la misma dirección URL proporcionará datos granulares debido a los [!DNL Marketo Measure] parámetros:

* `http://example.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Funcionamiento del etiquetado automático de [!DNL Marketo Measure] {#how-marketo-measure-auto-tagging-works}

**Si [!DNL Marketo Measure] encuentra una plantilla de seguimiento:**

* [!DNL Marketo Measure] agregará sus parámetros a la plantilla de seguimiento.
* Si se encuentra una redirección de terceros en una plantilla de seguimiento como Kenshoo o Marin, [!DNL Marketo Measure] no realizará ninguna acción. En su lugar, debe [agregar [!DNL Marketo Measure] parámetros a la herramienta de terceros en su cuenta](/help/api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

Sin embargo, si no se encuentra ninguna plantilla de seguimiento, [!DNL Marketo Measure]:

* Analizar todas las direcciones URL de destino de anuncios para nuestros [!DNL Marketo Measure] parámetros.
* Si te encuentran, estás listo para irte.
* Si no se encuentra, [!DNL Marketo Measure] adjuntará sus parámetros al final de las direcciones URL de destino de la publicidad. Para los anuncios nuevos, [!DNL Marketo Measure] adjuntará sus parámetros a la dirección URL de destino de la publicidad en un plazo de dos horas a partir de la creación.
* Es importante disponer de una plantilla de seguimiento antes de habilitar el etiquetado automático para que [!DNL Marketo Measure] pueda adjuntarse a ella y evitar que se restablezca el historial de anuncios.

[!DNL Marketo Measure] recomienda utilizar una Plantilla de seguimiento del nivel de la cuenta, nivel de campaña o nivel de grupo de anuncios, ya que esta permite añadir o eliminar parámetros para todos los anuncios sin el riesgo de provocar interrupciones o eliminación en el Historial de anuncios.

## Plantillas de seguimiento {#tracking-templates}

Como explica [!DNL Google AdWords], una plantilla de seguimiento es la dirección URL que se usa para llegar a una página de aterrizaje. La información de seguimiento recopilada se utiliza para comprender el tráfico publicitario. [Haga clic aquí](https://support.google.com/adwords/answer/7197008?hl=en){target="_blank"} para obtener más información de Google.

[!DNL Marketo Measure] recomienda usar una plantilla de seguimiento de nivel de cuenta, nivel de campaña o nivel de grupo de anuncios, ya que permite agregar y restar parámetros para todos los anuncios sin el riesgo de interrupciones o eliminación del historial de anuncios.

Hay dos plantillas de seguimiento que [!DNL Marketo Measure] recomienda usar. Utilice lo siguiente para determinar qué versión es apropiada para usted:

* Si todas las direcciones URL del anuncio tienen un signo &quot;?&quot; en ellos, utilice esta dirección URL:

`{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

* Si ninguna de las direcciones URL del anuncio tiene &quot;?&quot; en ellos, utilice esta dirección URL:

`{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Configuración de una plantilla de seguimiento en el nivel de cuenta {#setting-up-a-tracking-template-at-the-account-level}

1. Inicie sesión en su cuenta de [!DNL Google AdWords].

1. Haga clic en **[!UICONTROL Todas las campañas]** y, a continuación, en **[!UICONTROL Configuración]** en la ventana de ampliación.

   ![](assets/utilizing-connections-13.png)

1. Haga clic en **[!UICONTROL Configuración de la cuenta]** en la parte superior y luego en **[!UICONTROL Plantilla de seguimiento]**. Escriba la plantilla de seguimiento [!DNL Marketo Measure].

   ![](assets/bizible-guide-1.png)

1. Haga clic en **[!UICONTROL Guardar]**.

## Configuración de una plantilla de seguimiento en el nivel de campaña {#setting-up-a-tracking-template-at-the-campaign-level}

1. Haga clic en **[!UICONTROL Todas las campañas]** y luego en **[!UICONTROL Campañas]** en la ventana de expansión.

   ![](assets/utilizing-connections-12.png)

1. Seleccione todas las campañas aplicables o **[!UICONTROL Seleccionar todo]**, haga clic en **[!UICONTROL Editar]** y luego haga clic en **[!UICONTROL Cambiar plantillas de seguimiento]**.

   ![](assets/five-five-1.png)

1. Escriba la plantilla de seguimiento [!DNL Marketo Measure] y haga clic en **[!UICONTROL Aplicar]**.

## Configuración de una plantilla de seguimiento en el nivel de grupo de anuncios: {#setting-up-a-tracking-template-at-the-ad-group-level}

1. Haga clic en **[!UICONTROL Todas las campañas]** y, a continuación, en **[!UICONTROL Grupos de publicidad]** en la ventana de ampliación.

   ![](assets/four-four-1.png)

1. Seleccione todos los grupos de anuncios aplicables o Seleccionar todo, haga clic en **[!UICONTROL Editar]** y, a continuación, haga clic en **[!UICONTROL Plantillas de seguimiento de cambios]**.

1. Escriba la plantilla de seguimiento [!DNL Marketo Measure] y haga clic en **[!UICONTROL Aplicar]**.

   ![](assets/one-one-1.png)

## Preguntas frecuentes {#faq}

**Q: ¿Qué permisos necesita el usuario conectado?**

A: userinfo.email

**Q: ¿Cuánto tiempo puede tomar importar los datos gastados?**

A: 6 horas

**Q: ¿Cuánto tiempo puede tomar importar datos de publicidad?**

A: 4 horas

**Q: para los anuncios dinámicos de búsqueda, ¿podemos rastrear la combinación de titular, descripción, etc., en el elemento creativo que se proporcionó?**

R: No podemos recuperar detalles creativos individuales para anuncios dinámicos de búsqueda, pero si el etiquetado automático está habilitado, aún podemos obtener el ID creativo y los ingresos de atributos.

>[!NOTE]
>
>Una vez realizados los cambios, habrá terminado. Póngase en contacto con el [Soporte técnico de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} si tiene alguna pregunta durante la instalación.

[Haga clic aquí](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"} para recibir instrucciones de Google sobre cómo crear plantillas de seguimiento a nivel de cuenta.
