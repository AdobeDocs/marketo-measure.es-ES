---
description: Guía de integración de seguimiento de llamadas para usuarios de Marketo Measure
title: Integración de seguimiento de llamadas
exl-id: bc35a789-e056-4456-9038-306ed34c2a8e
feature: Tracking, Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 1%

---

# Integración de seguimiento de llamadas {#call-tracking-integration}

Nuestra integración con [!DNL CallTrackingMetrics] está pensada para combinar una sesión web con una llamada telefónica. Una llamada telefónica se trata como un envío de formulario a [!DNL Marketo Measure]. Atribuye crédito a una sesión web que, de lo contrario, solo se habría considerado una visita web porque no hubo envío real del formulario.

## Seguimiento de llamadas explicado {#call-tracking-explained}

En general, el &quot;seguimiento de llamadas&quot; es un producto de compañías como [!DNL CallTrackingMetrics], [!DNL DiaglogTech], [!DNL Invoca] o [!DNL CallRail], por nombrar algunas. Los usuarios ven números de teléfono únicos en función de los diferentes canales de marketing o campañas de las que proceden. Esto permite a los especialistas en marketing ver el rendimiento de esos canales o campañas.

![&#x200B; &quot;Seguimiento de llamadas&quot; en el sentido general es un producto de compañías como &#x200B;](assets/other-resources-6.png)

## Antes y después de {#before-and-after}

Observe el diagrama de flujo siguiente para ver cómo [!DNL Marketo Measure] utilizaba para gestionar llamadas telefónicas sin una integración con CallTrackingMetrics. La llamada telefónica que se realizó no se rastreó, por lo que se vio como una sesión web y no se creó ningún punto de contacto para ella. No fue hasta la siguiente visita en la que el usuario completó un formulario que finalmente se rellenó un punto de contacto.

Con la integración, puede ver que la sesión web estaba realmente vinculada a una llamada telefónica. El siguiente relleno de formulario termina siendo un contacto PostLC y se sigue rastreando como parte del recorrido.

![Con la integración, puede ver que la sesión web fue](assets/other-resources-4.png)

## Cómo funciona {#how-it-works}

CallTrackingMetrics tiene que hacer algún trabajo de desarrollo en su extremo para que esto funcione. Con el JavaScript que colocan en el sitio, CallTrackingMetrics puede obtener `_biz_uid` de la cookie [!DNL Marketo Measure]. A continuación, CallTrackingMetrics almacena este &quot;BizibleId&quot;.

Cuando un visitante llega a su sitio y realiza una llamada telefónica, es tarea de CallTrackingMetrics insertar esos datos en [!DNL Salesforce].  Normalmente, se crea un [!DNL Salesforce Task] que rellena datos como el número de teléfono, el asunto, el tipo y, ahora, el [!DNL BizibleId]

[!DNL BizibleId] es un campo que se instala con la versión 6.7 o posterior del paquete de atribución de marketing [!DNL Marketo Measure].

A continuación se muestra un ejemplo de un registro de tarea con [!DNL BizibleId] rellenado.

![A continuación se muestra un ejemplo de un registro de tarea con BizibleId](assets/other-resources-5.png)

Cuando [!DNL Marketo Measure] encuentra un registro de tarea con un valor [!DNL BizibleId] conocido rellenado, [!DNL Marketo Measure] puede asignar ese usuario a una sesión web con el mismo [!DNL BizibleId] y atribuir esa sesión a una llamada telefónica en lugar de a una visita web.

## El Touchpoint {#the-touchpoint}

Cuando [!DNL Marketo Measure] puede importar o descargar la tarea, procesamos ese detalle junto con la sesión web. Normalmente, se puede combinar con un referente o anuncio. En el siguiente ejemplo, un visitante encontró el negocio a través de un anuncio de Google de pago e hizo una llamada telefónica.

El tipo de [!UICONTROL Touchpoint] &quot;Llamada&quot; se extrae de la tarea, de la captura de pantalla anterior, que también se rellena con CallTrackingMetrics cuando se crea la tarea.

![Se ha extraído el tipo de punto de contacto &quot;Llamada&quot; de la tarea, desde el](assets/marketo-engage-activities-01.png)

## Sistema de informes {#reporting}

Los valores del tipo de punto de contacto que [!DNL Marketo Measure] suele insertar son Visita web, Formulario web o Chat web, pero en el caso de los puntos de contacto de CallTrackingMetrics, el tipo de punto de contacto es Llamada telefónica. Esto ayuda a los especialistas en marketing a ver qué canales atraen la mayor cantidad de llamadas telefónicas y generan ingresos para su organización.

![Los valores de Tipo de punto de contacto que Marketo Measure suele insertar son Visita web,](assets/other-resources-1.png)

## Preguntas frecuentes {#faq}

**¿Por qué es mi visita web de tipo de punto de contacto?**

El tipo de punto de contacto se rellena desde el campo Task.Type. Si el campo Task.Type está en blanco, [!DNL Marketo Measure] establecerá automáticamente el tipo de punto de contacto como visita web. Una vez que se rellene el campo Task.Type [!DNL Marketo Measure], leerá ese valor y rellenará el Touchpoint Type en consecuencia.

**¿Qué otros campos rellena Touchpoint desde la llamada telefónica?**

Tanto Touchpoint Type como Medium contienen los datos extraídos de Task.Type. El resto de los puntos de datos se extraen de los datos de seguimiento web y JavaScript.

**¿Por qué esta llamada no está vinculada a una sesión web?**

En primer lugar, compruebe la tarea para asegurarse de que haya un [!DNL BizibleId] rellenado. Si no hay ningún valor, no podemos crear un punto de contacto para él. Esto debe escalarse con CallTrackingMetrics.

Si hay un valor, tenga en cuenta que solo consideramos que todas las sesiones web son de 30 minutos. Si se hizo clic en un anuncio de Google a las 12:17pm (inicio de la sesión en el sitio web), pero la llamada no se realizó hasta las 1:05pm, no combinaremos la sesión web y la llamada telefónica. En su lugar, [!DNL Marketo Measure] crea un punto de contacto [!DNL Salesforce Task] independiente para realizar el seguimiento de la llamada telefónica, pero no tendrá datos de sesión web.

![Si hay un valor, tenga en cuenta que solo consideramos todas las páginas web](assets/other-resources-2.png)

## Asociaciones {#partnerships}

[!DNL Marketo Measure] tiene actualmente un socio oficial de seguimiento de llamadas que ha pasado por el proceso de integración &quot;oficial&quot; con nosotros, que incluye marketing conjunto y formación sobre el producto. Este socio es CallTrackingMetrics.
