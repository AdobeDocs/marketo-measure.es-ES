---
unique-page-id: 18874795
description: Adición [!DNL Marketo Measure] Script - [!DNL Marketo Measure] - Documentación del producto
title: Adición [!DNL Marketo Measure] Secuencia de comandos
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 0%

---

# Adición [!DNL Marketo Measure] Secuencia de comandos {#adding-marketo-measure-script}

[!DNL Marketo Measure] JavaScript que le gustaría rastrear [!DNL Marketo Measure] debe agregarse a todas las propiedades web lo antes posible. Una vez implementado el JavaScript, [!DNL Marketo Measure] empezará a recopilar sus datos digitales. Este artículo describe los métodos para implementar [!DNL Marketo Measure] JavaScript y consideraciones adicionales que se deben tener en cuenta.

>[!NOTE]
>
>Asegúrese de que [reclamaron todos los dominios adecuados en la variable [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md){target=&quot;_blank&quot;} además de implementar la variable [!DNL Marketo Measure] JavaScript.

Introducción a [!DNL Marketo Measure], existen dos maneras de agregar la variable [!DNL Marketo Measure] JavaScript para su sitio web:

* Codificación rígida
* Sistemas Tag Management

## Codificación rígida {#hard-coding}

Como práctica recomendada, recomendamos encarecidamente la codificación [!DNL Marketo Measure] JavaScript a las propiedades web. Para codificar el script de forma rígida, deberá colocar la secuencia de comandos antes del cierre `</head>` en todas las páginas del sitio.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Codificación del JavaScript en la variable `<head>` de sus páginas garantiza que [!DNL Marketo Measure] la secuencia de comandos se cargará primero y no se falta información de referente. La variable [!DNL Marketo Measure] JavaScript se carga asincrónicamente. Si se codifica de forma rígida, JavaScript debe agregarse manualmente a la automatización de marketing.

>[!TIP]
>
>Aprenda a asegurarse de que el script es [Compatible con el RGPD](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target=&quot;_blank&quot;}.

## Sistemas Tag Management {#tag-management-systems}

Si agrega [!DNL Marketo Measure] JavaScript mediante la codificación no es posible, otra opción es agregar la variable [!DNL Marketo Measure] secuencia de comandos con un sistema de Tag Management como [!DNL Google Tag Manager] (GTM) o Tealium.

Tenga en cuenta que usar sistemas de administración de etiquetas para implementar [!DNL Marketo Measure] JS puede causar una pérdida potencial de datos del 5 al 10% debido a la latencia del tiempo de carga del script. Esencialmente, si la herramienta de administración de etiquetas no se carga lo suficientemente rápido, [!DNL Marketo Measure] JS tampoco se puede cargar lo suficientemente rápido y podría perder la información del primer referente.

Una práctica habitual es implementar [!DNL Marketo Measure] JS a través de una herramienta de administración de etiquetas hasta que el tiempo/los recursos sean mejores para pasar a la codificación.

Para agregar [!DNL Marketo Measure] a través de una solución de administración de etiquetas, deberá crear una etiqueta nueva y agregar nuestro JavaScript dentro de ella. Aplique esta etiqueta a todas las páginas del sitio web de las que desee realizar un seguimiento.

[!DNL Marketo Measure] recomienda que cualquier vista de página haga que la etiqueta se active. Además, es mejor dar [!DNL Marketo Measure] la prioridad más alta en el orden de activación y asegúrese de que no haya scripts sincrónicos delante del [!DNL Marketo Measure] para garantizar la máxima calidad de los datos.

Se puede obtener más información [se encuentra aquí](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target=&quot;_blank&quot;}.

## Consideraciones adicionales {#additional-considerations}

[!DNL Marketo Measure] JavaScript se basa en dominios, por lo que se puede administrar automáticamente cualquier subdominio siempre que el JavaScript esté en las páginas y el dominio raíz sea el mismo que el dominio utilizado para crear la cuenta de medida de Marketo.

Sin embargo, si utiliza dominios separados o internacionales, asegúrese de dejar que su [!DNL Marketo Measure] El consultor sabe. Los dominios deben agregarse manualmente a su cuenta en la variable [!DNL Marketo Measure] finalizar para que [!DNL Marketo Measure] conoce para vincular los datos de dominios adicionales a su cuenta. Por lo tanto, envíe cualquier dominio separado/internacional a su [!DNL Marketo Measure] Consultor.

Si usa páginas de terceros, hable sobre su caso de uso con su [!DNL Marketo Measure] Consultor. En general, le interesa saber si puede agregar una versión personalizada de [!DNL Marketo Measure] JavaScript para rastrear esas páginas si corresponde. Si esto no es posible, el seguimiento a través de puntos de contacto de CRM Campaign se explorará con su [!DNL Marketo Measure] Consultor.

¿Tiene formularios que NO deberían rastrearse con [!DNL Marketo Measure] ya que no tienen necesariamente sentido para la atribución (por ejemplo, cancelar la suscripción de formularios, inicios de sesión de clientes, etc.)? Si es así, deseará añadir el código de exclusión [en este artículo](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md){target=&quot;_blank&quot;} para cada formulario

¿Tiene páginas no seguras? Si es así, debe protegerlos, ya que la navegación entre una página segura y no segura interrumpirá la sesión de seguimiento.

Asegúrese de mantener una conversación con su equipo web para que sepa [!DNL Marketo Measure] JavaScript siempre debe estar en las propiedades web adecuadas. Si se introducen nuevas páginas, formularios o sitios, asegúrese de implementar [!DNL Marketo Measure] JavaScript forma parte del protocolo .

Si [!DNL Web Application Firewall (WAF)] durante la configuración de JavaScript, los usuarios pueden deshabilitar esa regla WAF o incluir las cookies en la lista de permitidos, como se muestra a continuación:

![](assets/adding-marketo-measure-script-1.png)

## Forms prestará especial atención a {#forms-to-pay-extra-attention-to}

**Envío de varios formularios**

* Problema: Si tiene varios formularios vinculados como parte de un único envío de formulario, es posible que el primer formulario genere un punto de contacto aunque no se envíe el formulario completo.
* Solución: Deberá forzar que uno de los formularios informe al usuario a [!DNL Marketo Measure] en función de los datos en caché y discuta las prácticas de abandono. En general, [código de usuario del informe](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target=&quot;_blank&quot;} puede resolver esto.

**Inicio de sesión en la cuenta (no creación)**

* Problema: [!DNL Marketo Measure] recomienda no crear touchpoints para los inicios de sesión de cuenta posteriores, ya que estos tienden a diluir el historial de atribución.
* Solución: Agregue Excluir código al formulario de inicio de sesión de cuenta, cliente o socio.

>[!NOTE]
>
>Se recomienda crear un punto de contacto para la creación de una cuenta o prueba.

**Descarga de recursos**

* Problema: Si los recursos están conectados, [!DNL Marketo Measure] rastreará las descargas como rellenos de formulario. Si los recursos no están conectados, existen limitaciones a lo que podemos informar sin personalización.
* Solución: Portal del recurso si desea que el seguimiento lo realice [!DNL Marketo Measure] JavaScript. Si esta no es una opción y le gustaría tener un punto de contacto para ella, considere sincronizar una campaña de CRM en su lugar.

**iFrames**

* Problema: Los iFrames funcionan esencialmente como páginas dentro de las páginas.
* Solución: La variable [!DNL Marketo Measure] JS debe implementarse directamente en el encabezado iFrame para que podamos adjuntar correctamente al formulario.

**Lightboxes**

* Los Lightboxes suelen ser ventanas emergentes que contienen iFrames
* Solución: el [!DNL Marketo Measure] JS debe implementarse dentro del encabezado de ese iFrame alojado.

**Varios formularios en una página**

* Problema: Si hay varios formularios alojados en una página, es posible que no pueda saber qué formulario específico se rellenó con la variable [!DNL Marketo Measure] Campo URL del formulario.
* Solución: Si necesita saber qué formulario se rellenó, busque configurar el hash de URL dinámico con su equipo web.

**Forms organizado en `<div>` format**

* Problema: [!DNL Marketo Measure] JS tiene dificultades para reconocer formularios organizados en `<div>` para que se pueda necesitar código personalizado.
* Solución: Estos [plantillas de usuario del informe](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md)El equipo de desarrollo web puede usar {target=&quot;_blank&quot;} para agregar el código necesario.

**Chat**

* Problema: Si utiliza un proveedor de chat, puede que sea necesario un manejo especial.
* Solución: [!DNL Marketo Measure] se integra con Drift, Olark, Livechat, LivePerson y SnapEngage. Es necesario realizar el seguimiento de todas las demás plataformas mediante la pertenencia a campañas CRM.

**Segundo dominio**

* Problema: [!DNL Marketo Measure] JavaScript es específico del dominio, por lo que es necesario realizar pasos adicionales para cualquier dominio separado o internacional. Tenga en cuenta que [!DNL Marketo Measure] JS puede gestionar subdominios en el mismo dominio raíz.
* Solución: Si es propietario de varios dominios raíz, le gustaría que le realizara un seguimiento [!DNL Marketo Measure] asegúrese de agregar JS a los dominios Y dejar que su [!DNL Marketo Measure] El consultor sabe qué dominios deben asociarse manualmente a su [!DNL Marketo Measure] cuenta.

## Pruebas [!DNL Marketo Measure] JavaScript {#testing-marketo-measure-javascript}

Su [!DNL Marketo Measure] El consultor le ayudará a identificar las pruebas del sitio web para asegurarse de que [!DNL Marketo Measure] JavaScript está presente en todas las páginas. Parte de esta prueba consistirá en enviar algunos rellenos de formulario con detalles de prueba claramente indicados para garantizar que el seguimiento se devuelva correctamente.

Sin embargo, su [!DNL Marketo Measure] Es probable que un consultor no esté tan familiarizado con su sitio web como lo está su equipo web. Por esta razón, es muy importante que su equipo web u otro equipo apropiado, compruebe minuciosamente el sitio web, especialmente si hay formularios complejos en uso como los mencionados anteriormente. En última instancia, su equipo será responsable de garantizar que todas las propiedades web necesarias se rastreen correctamente, pero si está al tanto de formularios o situaciones complejos, puede preguntar a su [!DNL Marketo Measure] Consultor para obtener asistencia en pruebas.

Para probar un formulario, siga estos pasos:

1. Utilice siempre un explorador de incógnito o borre la caché entre cada prueba de envío de formulario Y utilice una dirección de correo electrónico diferente cada vez.

   a. Una práctica recomendada es utilizar un correo electrónico falso que contenga algo que indique que es una prueba y la hora del día. Por ejemplo: testing830am@test.com.

1. Registre la dirección URL de la página que envía el formulario y el correo electrónico utilizado.

1. Busque el registro creado en su CRM (posible cliente o contacto) para ese envío de formulario y verifique que se haya creado correctamente un punto de contacto.

   a. Puede usar un [!DNL Marketo Measure] informe de existencias, como Posibles clientes con puntos de contacto del comprador, o observe el diseño de la página posible cliente/contacto si elige actualizar los diseños de página con [!DNL Marketo Measure] detalles.

   b. Tenga en cuenta que esto podría tardar algún tiempo en procesarse.
