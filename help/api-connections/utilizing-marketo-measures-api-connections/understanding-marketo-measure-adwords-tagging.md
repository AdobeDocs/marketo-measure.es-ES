---
unique-page-id: 18874678
description: Comprensión [!DNL Marketo Measure] Etiquetado de AdWords - [!DNL Marketo Measure] - Documentación del producto
title: Información sobre el etiquetado de AdWords de  [!DNL Marketo Measure]
exl-id: c6658766-d3a8-46ed-b2d2-826eb61ce269
feature: APIs, Integration, UTM Parameters
source-git-commit: 3bad77a72c0dea6caf0daadbb594f10f791af715
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 1%

---

# Información sobre el etiquetado de AdWords de [!DNL Marketo Measure] {#understanding-marketo-measure-adwords-tagging}

Para realizar un seguimiento de los anuncios a un nivel muy granular, las URL de destino de anuncio deben ser únicas. Para lograr esto, [!DNL Marketo Measure] El etiquetado automático agrega automáticamente parámetros de seguimiento a las direcciones URL de destino de publicidad de su [!DNL AdWords] anuncios. Echemos un vistazo al ejemplo siguiente.

La siguiente URL no proporcionará datos granulares:

* `http://example.com/landing-page?myParam=foo`

Sin embargo, la misma URL proporcionará datos granulares debido a la variable [!DNL Marketo Measure] parámetros:

* `http://example.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Cómo [!DNL Marketo Measure] Funciona el etiquetado automático {#how-marketo-measure-auto-tagging-works}

**If [!DNL Marketo Measure] encuentra una plantilla de seguimiento:**

* [!DNL Marketo Measure] agregará sus parámetros a la plantilla de seguimiento.
* Si se encuentra una redirección de terceros en una plantilla de seguimiento como Kenshoo o Marin, [!DNL Marketo Measure] no realizará ninguna acción. En su lugar, debe [añadir [!DNL Marketo Measure] parámetros a la herramienta de terceros de su cuenta](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

Sin embargo, si no se encuentra ninguna plantilla de seguimiento, [!DNL Marketo Measure] hará:

* Analizar todas las direcciones URL de destino de publicidad para su [!DNL Marketo Measure] Parámetros.
* Si te encuentran, estás listo para irte.
* Si no se encuentra, [!DNL Marketo Measure] adjuntará sus parámetros al final de las URL de destino de la publicidad. Para anuncios nuevos, [!DNL Marketo Measure] adjuntará sus parámetros a la URL de destino de la publicidad en un plazo de dos horas desde su creación.
* Es importante disponer de una plantilla de seguimiento antes de activar el etiquetado automático, de modo que [!DNL Marketo Measure] puede adjuntarse a él y evitar que se restablezca el historial de anuncios.

[!DNL Marketo Measure] recomienda utilizar una plantilla de seguimiento de nivel de cuenta, de nivel de campaña o de nivel de grupo de publicidad, ya que permite añadir y restar parámetros para todos los anuncios sin el riesgo de interrupciones o eliminación del historial de anuncios.

## Plantillas de seguimiento {#tracking-templates}

Como lo explica [!DNL Google AdWords], una plantilla de seguimiento es la dirección URL que se utiliza para llegar a una página de aterrizaje. La información de seguimiento recopilada se utiliza para comprender el tráfico publicitario. [Haga clic aquí](https://support.google.com/adwords/answer/7197008?hl=en){target="_blank"} para obtener más información de Google.

[!DNL Marketo Measure] recomienda utilizar una plantilla de seguimiento de nivel de cuenta, nivel de campaña o nivel de grupo de anuncios, ya que permite añadir y restar parámetros para todos los anuncios sin el riesgo de interrupciones o eliminación del historial de anuncios.

Hay dos plantillas de seguimiento [!DNL Marketo Measure] recomienda utilizar. Utilice lo siguiente para determinar qué versión es apropiada para usted:

* Si todas las direcciones URL del anuncio tienen un signo &quot;?&quot; en ellos, utilice esta dirección URL:

`{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

* Si ninguna de las direcciones URL del anuncio tiene &quot;?&quot; en ellos, utilice esta dirección URL:

`{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Configuración de una plantilla de seguimiento en el nivel de cuenta {#setting-up-a-tracking-template-at-the-account-level}

1. Inicie sesión en su [!DNL Google AdWords] Cuenta.

1. Clic **[!UICONTROL Todas las campañas]** y luego **[!UICONTROL Configuración]** en la ventana de ampliación.

   ![](assets/1.png)

1. Clic **[!UICONTROL Configuración de cuenta]** en la parte superior y luego **[!UICONTROL Plantilla de seguimiento]**. Introduzca el [!DNL Marketo Measure] Plantilla de seguimiento.

   ![](assets/2-1.png)

1. Clic **[!UICONTROL Guardar]**.

## Configuración de una plantilla de seguimiento en el nivel de campaña {#setting-up-a-tracking-template-at-the-campaign-level}

1. Clic **[!UICONTROL Todas las campañas]** y luego **[!UICONTROL Campañas]** en la ventana de ampliación.

   ![](assets/3.png)

1. Seleccione todas las campañas aplicables o **[!UICONTROL Seleccionar todo]**, haga clic en **[!UICONTROL Editar]** y haga clic en **[!UICONTROL Cambiar plantillas de seguimiento]**.

   ![](assets/4-1.png)

1. Introduzca el [!DNL Marketo Measure] Plantilla de seguimiento y clic **[!UICONTROL Aplicar]**.

## Configuración de una plantilla de seguimiento en el nivel de grupo de anuncios: {#setting-up-a-tracking-template-at-the-ad-group-level}

1. Clic **[!UICONTROL Todas las campañas]** y luego **[!UICONTROL Grupos de publicidad]** en la ventana de ampliación.

   ![](assets/5-1.png)

1. Seleccione todos los grupos de publicidad aplicables o seleccione todos y haga clic en **[!UICONTROL Editar]** y luego haga clic en **[!UICONTROL Cambiar plantillas de seguimiento]**.

1. Introduzca el [!DNL Marketo Measure] Plantilla de seguimiento y clic **[!UICONTROL Aplicar]**.

   ![](assets/6-1.png)

## Preguntas frecuentes {#faq}

**P: ¿Qué permisos necesita el usuario conectado?**

A: userinfo.email

**P: ¿Cuánto tiempo puede tardar la importación de datos de gasto?**

A: 6 horas

**P: ¿Cuánto tiempo puede tardar la importación de datos de publicidad?**

A: 4 horas

**P: En el caso de los anuncios dinámicos de búsqueda, ¿podemos rastrear la combinación de titular, descripción, etc., en el elemento creativo servido?**

R: No podemos recuperar detalles creativos individuales para anuncios dinámicos de búsqueda, pero si el etiquetado automático está habilitado, aún podemos obtener el ID creativo y los ingresos de atributos.

>[!NOTE]
>
>Una vez realizados los cambios, habrá terminado. No dude en ponerse en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} si hay alguna pregunta durante la configuración.

[Haga clic aquí](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"} para obtener instrucciones de Google sobre la creación de plantillas de seguimiento de nivel de cuenta.
