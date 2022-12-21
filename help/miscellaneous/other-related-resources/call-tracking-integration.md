---
unique-page-id: 18874592
description: Integración del seguimiento de llamadas - [!DNL Marketo Measure] - Documentación del producto
title: Integración de seguimiento de la llamada
exl-id: bc35a789-e056-4456-9038-306ed34c2a8e
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 0%

---

# Integración de seguimiento de la llamada {#call-tracking-integration}

Nuestra integración con [!DNL CallTrackingMetrics] está diseñado para combinar una sesión web con una llamada telefónica. Una llamada telefónica se trata como un envío de formulario a [!DNL Marketo Measure]. Otorga crédito a una sesión web que de otra manera solo se habría considerado una visita web porque no había ningún envío de formulario real.

## Rastreo de llamadas explicado {#call-tracking-explained}

El &quot;seguimiento de llamadas&quot; en sentido general es un producto de empresas como [!DNL CallTrackingMetrics], [!DNL DiaglogTech], [!DNL Invoca]o [!DNL CallRail], por nombrar algunos. Se muestran números de teléfono únicos a los usuarios en función de los diferentes canales de marketing o campañas de las que proceden. Esto permite a los especialistas en marketing ver el rendimiento de esos canales o campañas.

![](assets/1.png)

## Antes y después {#before-and-after}

Eche un vistazo al diagrama de flujo a continuación para ver cómo [!DNL Marketo Measure] se utiliza para gestionar llamadas telefónicas sin una integración con CallTrackingMetrics. La llamada telefónica que se realizó no se rastreó, por lo que se vio como una sesión web y no se creó ningún punto de contacto para ella. No fue hasta la siguiente visita en la que el usuario completó un formulario en el que finalmente se rellenó un punto de contacto.

Con la integración, puede ver que la sesión web estaba realmente vinculada a una llamada telefónica. El siguiente relleno del formulario termina siendo un toque PostLC y se sigue realizando como parte del recorrido.

![](assets/2.png)

## Cómo funciona {#how-it-works}

CallTrackingMetrics tiene que hacer un poco de trabajo de desarrollo en su extremo para que esto funcione. Con el javascript que colocan en su sitio, CallTrackingMetrics puede obtener el _biz_uid del [!DNL Marketo Measure] cookie. Este[!DNL BizibleId]&quot; se almacena a continuación mediante CallTrackingMetrics.

Cuando un visitante llega a su sitio y realiza una llamada telefónica, es tarea de CallTrackingMetrics impulsar esos datos en [!DNL Salesforce]  Normalmente, un [!DNL Salesforce Task] se crea para rellenar datos como número de teléfono, asunto, tipo y ahora, la variable [!DNL BizibleId]

La variable [!DNL BizibleId] es un campo que se instala con la versión 6.7 o posterior de la variable [!DNL Marketo Measure] Paquete de atribución de marketing.

A continuación se muestra un ejemplo de un registro de tarea con la variable [!DNL BizibleId] rellenado.

![](assets/3.png)

When [!DNL Marketo Measure] encuentra un registro Task con un [!DNL BizibleId] valor rellenado, [!DNL Marketo Measure] puede asignar ese usuario a una sesión web con el mismo [!DNL BizibleId] y atribuir esa sesión a una llamada telefónica en lugar de a una visita web.

## Touchpoint {#the-touchpoint}

When [!DNL Marketo Measure] puede importar/descargar la tarea, procesamos ese detalle junto con la sesión web. En la mayoría de los casos, se puede combinar con un referente o un anuncio. En el siguiente ejemplo, un visitante encontró el negocio a través de un anuncio de Google de pago y realizó una llamada telefónica.

La variable [!UICONTROL Touchpoint] El tipo &quot;Llamada&quot; se extrae de la tarea, de la captura de pantalla anterior, que también se rellena con CallTrackingMetrics cuando se crea la tarea.

![](assets/4.png)

## Informes {#reporting}

Valores de Tipo de punto de contacto que [!DNL Marketo Measure] normalmente, las pulsaciones son Visita web, Formulario web o Chat web, pero en el caso de los puntos de contacto CallTrackingMetrics, el tipo de punto de contacto es Llamada telefónica. Esto ayuda a los especialistas en marketing a ver qué canales atraen la mayoría de las llamadas telefónicas y a generar ingresos para su organización.

![](assets/5.png)

## Preguntas frecuentes {#faq}

**¿Por qué mi visita web de tipo punto de contacto es?**

El tipo de punto de contacto se rellena desde el campo Task.Type . Si el campo Task.Type está en blanco, [!DNL Marketo Measure] establecerá automáticamente el tipo de punto de contacto como visita web. Una vez rellenado el campo Task.Type [!DNL Marketo Measure] leerá ese valor y rellenará el tipo de punto de contacto en consecuencia.

**¿Qué otros campos rellena el punto de contacto desde la llamada telefónica?**

Tanto el Tipo de punto de contacto como el Medio contendrán los datos extraídos de Task.Type. Todos los demás puntos de datos se extraen de los datos de seguimiento web y javascript.

**¿Por qué esta llamada no está vinculada a una sesión web?**

En primer lugar, compruebe la tarea para asegurarse de que hay una [!DNL BizibleId] rellenado. Si no hay ningún valor, no crearemos ni podremos crear un punto de contacto para él. Esto tendrá que escalarse con CallTrackingMetrics.

Si hay un valor, tenga en cuenta que solo se consideran 30 minutos todas las sesiones web. Si se hizo clic en un anuncio de Google a las 12:17pm (inicio de la sesión en el sitio web), pero la llamada telefónica no se produjo hasta la 1:05pm, no combinaremos la sesión web y la llamada telefónica. En su lugar, [!DNL Marketo Measure] creará un [!DNL Salesforce Task] touchpoint para realizar el seguimiento de la llamada telefónica, pero no tendrá datos de sesión web.

![](assets/6.png)

## Asociaciones {#partnerships}

[!DNL Marketo Measure] actualmente tiene un socio oficial de seguimiento de llamadas que ha pasado por el proceso de integración &quot;oficial&quot; con nosotros, que incluye capacitación de productos y mercadotecnia conjunta. Este socio es CallTrackingMetrics.
