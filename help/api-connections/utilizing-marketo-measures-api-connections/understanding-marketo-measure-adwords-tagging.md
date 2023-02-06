---
unique-page-id: 18874678
description: Explicación [!DNL Marketo Measure] Etiquetado de AdWords - [!DNL Marketo Measure] - Documentación del producto
title: Explicación [!DNL Marketo Measure] Etiquetado de AdWords
exl-id: c6658766-d3a8-46ed-b2d2-826eb61ce269
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 0%

---

# Explicación [!DNL Marketo Measure] Etiquetado de AdWords {#understanding-marketo-measure-adwords-tagging}

Para poder realizar un seguimiento de las publicidades a nivel muy granular, las direcciones URL de destino de las publicidades deben ser únicas. Para lograrlo, [!DNL Marketo Measure] el etiquetado automático agrega automáticamente parámetros de seguimiento a las direcciones URL de destino de anuncio de su [!DNL AdWords] anuncios. Veamos un ejemplo a continuación.

La siguiente URL no proporciona datos granulares:

* `http://example.com/landing-page?myParam=foo`

Sin embargo, la misma dirección URL proporcionará datos granulares debido al [!DNL Marketo Measure] parámetros:

* `http://example.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Cómo [!DNL Marketo Measure] El etiquetado automático funciona {#how-marketo-measure-auto-tagging-works}

**If [!DNL Marketo Measure] encuentra una plantilla de seguimiento:**

* [!DNL Marketo Measure] agregará sus parámetros a la plantilla de seguimiento.
* Si se encuentra un redireccionamiento de terceros en una plantilla de seguimiento como Kenshoo o Marin, [!DNL Marketo Measure] no tomará ninguna acción. En su lugar, debe [add [!DNL Marketo Measure] parámetros de la herramienta de terceros de su cuenta](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

Sin embargo, si no se encuentra ninguna plantilla de seguimiento, [!DNL Marketo Measure] será:

* Analizar todas las direcciones URL de destino de publicidad para [!DNL Marketo Measure] Parámetros.
* Si te encuentran, estás listo para irte.
* Si no se encuentra, [!DNL Marketo Measure] adjuntará sus parámetros al final de las direcciones URL de destino de anuncio. Para anuncios nuevos, [!DNL Marketo Measure] adjuntará sus parámetros a la dirección URL del destino del anuncio en un plazo de dos horas a partir de la creación.
* Es importante tener una plantilla de seguimiento en su lugar antes de habilitar el etiquetado automático para que [!DNL Marketo Measure] puede adjuntarse a él e impedir que se restablezca el historial de anuncios.

[!DNL Marketo Measure] recomienda utilizar una plantilla de seguimiento de nivel de cuenta, de nivel de campaña o de grupo de anuncios, ya que permite añadir y restar parámetros para todos los anuncios sin riesgo de interrupciones o eliminación del historial de anuncios.

## Plantillas de seguimiento {#tracking-templates}

Como se explica en [!DNL Google AdWords], una plantilla de seguimiento es la dirección URL que se utiliza para llegar a una página de aterrizaje. La información de seguimiento recopilada se utiliza para comprender el tráfico de la publicidad. [Haga clic aquí](https://support.google.com/adwords/answer/7197008?hl=en){target="_blank"} para obtener más información de Google.

[!DNL Marketo Measure] recomienda utilizar una plantilla de seguimiento de nivel de cuenta, nivel de campaña o nivel de grupo de anuncios , ya que permite añadir y restar parámetros para todos los anuncios sin riesgo de interrupciones o eliminación del historial de anuncios.

Hay dos plantillas de seguimiento [!DNL Marketo Measure] recomienda utilizar . Utilice lo siguiente para determinar qué versión es apropiada para usted:

* Si todas las direcciones URL de la publicidad tienen un &quot;?&quot; en ellos, utilice esta dirección URL:

`{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

* Si ninguna de las direcciones URL de la publicidad tiene un &quot;?&quot; en ellos, utilice esta dirección URL:

`{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Configuración de una plantilla de seguimiento en el nivel de cuenta {#setting-up-a-tracking-template-at-the-account-level}

1. Inicie sesión en su [!DNL Google AdWords] Cuenta.

1. Haga clic en **[!UICONTROL Todas las campañas]** y luego **[!UICONTROL Configuración]** en la ventana de expansión.

   ![](assets/1.png)

1. Haga clic en **[!UICONTROL Configuración de la cuenta]** en la parte superior y luego **[!UICONTROL Plantilla de seguimiento]**. Introduzca la variable [!DNL Marketo Measure] Plantilla de seguimiento.

   ![](assets/2-1.png)

1. Haga clic en **[!UICONTROL Guardar]**.

## Configuración de una plantilla de seguimiento en el nivel de campaña {#setting-up-a-tracking-template-at-the-campaign-level}

1. Haga clic en **[!UICONTROL Todas las campañas]** y luego **[!UICONTROL Campañas]** en la ventana de expansión.

   ![](assets/3.png)

1. Seleccione todas las campañas aplicables o **[!UICONTROL Seleccionar todo]**, haga clic en **[!UICONTROL Editar]** y, a continuación, haga clic en **[!UICONTROL Cambiar plantillas de seguimiento]**.

   ![](assets/4-1.png)

1. Introduzca la variable [!DNL Marketo Measure] Plantilla de seguimiento y clic **[!UICONTROL Aplicar]**.

## Configuración de una plantilla de seguimiento en el nivel de grupo de publicidad: {#setting-up-a-tracking-template-at-the-ad-group-level}

1. Haga clic en **[!UICONTROL Todas las campañas]** y luego **[!UICONTROL Grupos de publicidad]** en la ventana de expansión.

   ![](assets/5-1.png)

1. Seleccione todos los grupos de anuncios aplicables o Seleccionar todo, haga clic en **[!UICONTROL Editar]** y haga clic en **[!UICONTROL Cambiar plantillas de seguimiento]**.

1. Introduzca la variable [!DNL Marketo Measure] Plantilla de seguimiento y clic **[!UICONTROL Aplicar]**.

   ![](assets/6-1.png)

## Preguntas frecuentes {#faq}

**P: ¿Qué permisos necesita el usuario conectado?**

A: userinfo.email

**P: ¿Cuánto tiempo se puede tardar en importar los datos de gasto?**

A: 6 horas

**P: ¿Cuánto tiempo se puede tardar en importar datos de publicidad?**

A: 4 horas

>[!NOTE]
>
>Una vez realizados los cambios, ya ha finalizado. No dude en ponerse en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} si hay alguna pregunta durante la configuración.

[Haga clic aquí](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"} para obtener instrucciones de Google sobre la creación de plantillas de seguimiento de nivel de cuenta.
