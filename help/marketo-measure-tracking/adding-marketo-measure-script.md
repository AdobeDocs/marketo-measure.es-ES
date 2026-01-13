---
description: Agregando  [!DNL Marketo Measure] script - [!DNL Marketo Measure]
title: 'Adición del script de  [!DNL Marketo Measure] '
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1291'
ht-degree: 57%

---


# Adición del script de [!DNL Marketo Measure] {#adding-marketo-measure-script}

El JavaScript de [!DNL Marketo Measure] que le gustaría rastrear mediante [!DNL Marketo Measure] debe añadirse a todas las propiedades web lo antes posible. Una vez implementado JavaScript, [!DNL Marketo Measure] comienza a recopilar los datos digitales. Este artículo describe los métodos para implementar [!DNL Marketo Measure] JavaScript y otros aspectos.

>[!NOTE]
>Asegúrese de que haber reclamado todos los dominios adecuados de [&#x200B; en  [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md){target="_blank"} además de implementar el JavaScript de [!DNL Marketo Measure].

Al comenzar con [!DNL Marketo Measure], hay dos maneras de añadir el JavaScript de [!DNL Marketo Measure] a su sitio web:

* Codificación rígida
* Sistemas de administración de etiquetas

## Codificación rígida {#hard-coding}

Como práctica recomendada, se recomienda codificar el JavaScript de [!DNL Marketo Measure] en las propiedades web. Para codificar el script, debe colocarlo antes del `</head>` de cierre en todas las páginas del sitio.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Codificar el JavaScript en `<head>` de sus páginas garantiza que el script [!DNL Marketo Measure] se cargue primero y que no se pierda la información de referencia. El JavaScript de [!DNL Marketo Measure] se carga asincrónicamente. Si está codificando, JavaScript debe añadirse manualmente a la automatización de marketing.

>[!TIP]
>Aprenda a asegurarse de que el script [cumpla con el RGPD](/help/security/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target="_blank"}.

## Sistemas de administración de etiquetas {#tag-management-systems}

Si no es posible agregar [!DNL Marketo Measure] JavaScript mediante la codificación, otra opción es agregar el script [!DNL Marketo Measure] mediante un sistema Tag Management como [!DNL Google Tag Manager] (GTM) o Tealium.

El uso de sistemas de administración de etiquetas para implementar [!DNL Marketo Measure] JS puede causar una posible pérdida de datos del 5 al 10% debido a la latencia del tiempo de carga del script. Básicamente, si la herramienta de administración de etiquetas no se carga con la rapidez suficiente, el JS de [!DNL Marketo Measure] tampoco se puede cargar con la rapidez suficiente y podría perder la información del primer referente.

Una práctica común es implementar el JS de [!DNL Marketo Measure] a través de una herramienta de administración de etiquetas hasta que el tiempo/recurso sea mejor para pasar a la codificación.

Para agregar el script [!DNL Marketo Measure] a través de una solución de administración de etiquetas, debe crear una etiqueta y agregar su JavaScript dentro de ella. Aplique esta etiqueta a todas las páginas del sitio web de las que desee realizar un seguimiento.

[!DNL Marketo Measure] recomienda que cualquier vista de página haga que la etiqueta se active. Además, se recomienda dar a [!DNL Marketo Measure] la prioridad más alta en el orden de activación y asegurarse de que no haya scripts sincrónicos delante de la etiqueta [!DNL Marketo Measure] para garantizar la máxima calidad de los datos.

Puede obtener más información [aquí](/help/marketo-measure-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target="_blank"}.

## Consideraciones adicionales {#additional-considerations}

El JavaScript de [!DNL Marketo Measure] se basa en el dominio, por lo que puede gestionar automáticamente cualquier subdominio siempre que JavaScript esté en las páginas y el dominio raíz sea el mismo que el dominio utilizado para crear la cuenta de Marketo Measure.

Sin embargo, si utiliza dominios independientes o internacionales, asegúrese de que lo sepa su consultor de [!DNL Marketo Measure]. Los dominios deben agregarse manualmente a su cuenta en el extremo [!DNL Marketo Measure] para que [!DNL Marketo Measure] sepa que debe vincular los datos de los dominios adicionales a su cuenta. Por lo tanto, envíe cualquier dominio independiente o internacional a su consultor de [!DNL Marketo Measure].

Si usa páginas de terceros, hable sobre su caso de uso con el consultor de [!DNL Marketo Measure]. En general, le interesará saber si puede agregar una versión personalizada de [!DNL Marketo Measure] JavaScript para rastrear esas páginas, si corresponde. Si no es posible, se explorará el seguimiento a través de los puntos de contacto de CRM Campaign con su consultor [!DNL Marketo Measure].

¿Tiene formularios a los que [!DNL Marketo Measure] NO debería realizar un seguimiento, ya que no necesariamente tienen sentido para la atribución (por ejemplo, cancelar la suscripción de formularios, inicios de sesión de clientes, etc.)? Si es así, deseará agregar el código de exclusión [en este artículo](/help/marketo-measure-tracking/excluding-marketo-measure-from-specific-forms.md){target="_blank"} a cada formulario

¿Tiene páginas que no son seguras? Debe protegerlas, ya que la navegación entre una página segura/no segura interrumpe la sesión de seguimiento.

Asegúrese de tener una conversación con su equipo web para que sepan que el JavaScript de [!DNL Marketo Measure]debe estar siempre en las propiedades web adecuadas. Si se introducen nuevas páginas, formularios o sitios, asegúrese de que la implementación de JavaScript de [!DNL Marketo Measure] forme parte del protocolo.

Si se activa una advertencia [!DNL Web Application Firewall (WAF)] durante la configuración de JavaScript, los usuarios pueden deshabilitar esa regla de WAF o lista de permitidos las cookies, como se muestra en el siguiente ejemplo:

![Ejemplo de mensaje de advertencia de WAF para el script de Marketo Measure](assets/adding-marketo-measure-script-1.png)

## Formularios a los que debe prestarse especial atención {#forms-to-pay-extra-attention-to}

**Envío de varios formularios**

* Problema: Si tiene varios formularios vinculados como parte de un solo envío de formulario, es posible que el primer formulario genere un punto de contacto aunque el formulario completo no se envíe.
* Solución: debe forzar uno de los formularios para que informe al usuario a [!DNL Marketo Measure] en función de los datos almacenados en caché y discutir las prácticas de abandono. Generalmente, [código de usuario del informe](/help/marketo-measure-tracking/ajax-form-handling.md){target="_blank"} puede resolverlo.

**Inicio de sesión de la cuenta (sin creación)**

* Problema: [!DNL Marketo Measure] recomienda no crear puntos de contacto para los inicios de sesión posteriores de la cuenta, ya que tienden a diluir la historia de atribución.
* Solución: añada el código de exclusión al formulario de inicio de sesión de cuenta/cliente/socio.

>[!NOTE]
>Se recomienda crear un punto de contacto para la creación de una cuenta o una prueba.

**Descarga de recursos**

* Problema: Si los recursos están bloqueados, [!DNL Marketo Measure] rastrea las descargas como rellenos de formulario. Si sus recursos no están protegidos, existen limitaciones sobre lo que podemos informar sin personalización.
* Solución: proteja el recurso si desea que lo rastree el JavaScript de [!DNL Marketo Measure]. Si esta no es una opción y aún desea un punto de contacto para él, considere la posibilidad de sincronizar una campaña CRM en su lugar.

**iFrames**

* Problema: los iFrames funcionan esencialmente como páginas dentro de las páginas.
* Solución: el JS [!DNL Marketo Measure] debe implementarse directamente en el encabezado del iFrame para que nos adjuntemos correctamente al formulario.

**Lightboxes**

* Los Lightboxes suelen ser ventanas emergentes que contienen iFrames
* Solución: el JS de [!DNL Marketo Measure] debe implementarse dentro del encabezado de ese iFrame alojado.

**Varios formularios en una página**

* Problema: si hay varios formularios alojados en una página, es posible que no pueda saber qué formulario específico se rellenó con el campo URL de formulario de [!DNL Marketo Measure].
* Solución: si necesita saber qué formulario se ha rellenado, explore la configuración del hashing de URL dinámico con su equipo web.

**Formularios organizados en `<div>` formato**

* Problema: el JS de [!DNL Marketo Measure] tiene dificultades para reconocer los formularios organizados en formato `<div>`, por lo que puede ser necesario código personalizado.
* Solución: su equipo de desarrollo web puede utilizar estas [plantillas de usuario de informe](/help/marketo-measure-tracking/ajax-form-handling.md){target="_blank"} para añadir el código necesario.

**Chat**

* Problema: si utiliza un proveedor de chat, puede ser necesario un manejo especial.
* Solución: [!DNL Marketo Measure] se integra con Drift, Olark, Livechat, LivePerson y SnapEngage. Todas las demás plataformas deben rastrearse mediante el abono a la campaña de CRM.

**Segundo dominio**

* Problema: [!DNL Marketo Measure] JavaScript es un dominio específico, por lo que se deben realizar pasos adicionales para cualquier dominio independiente o internacional. [!DNL Marketo Measure] JS puede administrar subdominios en el mismo dominio raíz.
* Solución: si es propietario de varios dominios raíz, que le gustaría que [!DNL Marketo Measure] rastreara, asegúrese de añadir JS a los dominios y permita que su consultor de [!DNL Marketo Measure] sepa qué dominios deben asociarse manualmente a su cuenta de [!DNL Marketo Measure].

## Pruebas de el JavaScript de [!DNL Marketo Measure] {#testing-marketo-measure-javascript}

Su consultor de [!DNL Marketo Measure] le ayudará a probar el sitio web para asegurarse de que el JavaScript de [!DNL Marketo Measure] esté presente en todas las páginas. Parte de esta prueba consiste en enviar algunos formularios rellenados con detalles de prueba claramente indicados para garantizar que el seguimiento se devuelva correctamente.

Sin embargo, es probable que su consultor de [!DNL Marketo Measure] no esté tan familiarizado con el sitio web como el equipo web. Por este motivo, es muy importante que su equipo web u otro equipo adecuado compruebe exhaustivamente el sitio web, especialmente si hay formularios complejos en uso como los mencionados anteriormente. En última instancia, su equipo será responsable de garantizar que todas las propiedades web necesarias estén rastreadas correctamente, pero si conoce algún formulario o situación compleja, puede preguntar a su consultor de [!DNL Marketo Measure] en las pruebas.

Para probar un formulario usted mismo, siga estos pasos:

1. Utilice siempre un explorador de incógnito o borre la caché entre cada prueba de envío de formulario y utilice una dirección de correo electrónico diferente cada vez.

   a. Una práctica recomendada es utilizar un correo electrónico falso que contenga la hora del día y algo que indique que es una prueba. Por ejemplo: testing830am@test.com.

1. Registre la dirección URL de la página que está enviando el formulario y el correo electrónico utilizado.

1. Busque el registro creado en su CRM (posible cliente o contacto) para dicho envío de formulario y compruebe que se creó correctamente un punto de contacto.

   a. Puede utilizar un informe de existencias de [!DNL Marketo Measure] como posibles clientes con Buyer Touchpoints u observe el diseño de la página de posible cliente/contacto si decide actualizar los diseños de página con detalles de [!DNL Marketo Measure].

   b. Los datos podrían tardar un poco en procesarse.
