---
description: Integración de LinkedIn - [!DNL Marketo Measure]
title: Integración de LinkedIn
exl-id: 705209ef-1ece-496c-ac2f-6a31055bd993
feature: APIs, Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '2736'
ht-degree: 1%

---


# Integración de LinkedIn {#linkedin-integration}

## Información general {#overview}

La integración de [!DNL Marketo Measure] con LinkedIn consta de dos partes:

Contenido patrocinado: la integración de contenido patrocinado permite que [!DNL Marketo Measure] etiquete las direcciones URL de destino en los anuncios de [!DNL LinkedIn], lo que en última instancia permite que [!DNL Marketo Measure] siga a un usuario a través de todo el recorrido de puntos de contacto y asigne la actividad de nuevo a la campaña y a Creative de [!DNL LinkedIn] específicas. Esto proporciona información a los clientes sobre el ROI de su actividad [!DNL LinkedIn].

Forms de generación de clientes potenciales: a través de la integración con Forms de generación de clientes potenciales de LinkedIn, Marketo Measure obtiene insight en formularios que se han enviado a través de la plataforma LinkedIn. Estos rellenos de formulario se comparan con los posibles clientes de su instancia de CRM o [!DNL Marketo Engage] para que puedan ser atribuidos. Con insight en la campaña, Creative y Form que ayudó a generar los formularios, los equipos ahora pueden optimizar aún más su gasto en marketing y publicidad de LinkedIn.

## Disponibilidad {#availability}

Disponible para todos los usuarios.

## Requisitos {#requirements}

**Roles de administrador de campaña**

Para que [!DNL Marketo Measure] pueda descargar los datos de anuncios y los datos de costo de anuncios, debe tener uno de los siguientes roles en el Administrador de campañas:

* Administrador de facturación
* Administrador de cuentas
* Administrador de campañas

Más información: [Roles y funciones de usuario en el administrador de Campaign](https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager).

**Roles de administrador de medios de pago**

Para que [!DNL Marketo Measure] pueda crear/actualizar elementos creativos patrocinados, debe tener uno de los siguientes roles de administrador de medios de pago:

* Afiche de contenido patrocinado
* Gerente principal de Forms

Más información: [Roles de administrador de página de LinkedIn](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

Hay otros roles de [!DNL LinkedIn] que **no** necesitamos para nuestra integración. Estas funciones a menudo se confunden con las funciones requeridas, por lo que tenga en cuenta que hay una diferencia.

**Roles de administrador de página**

Para que [!DNL Marketo Measure] pueda descargar o integrar posibles clientes desde formularios de posible cliente, debe tener la siguiente función de administrador de página:

* Super Admin

Más información: [Roles de administrador de página de LinkedIn](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

## Tipos de anuncios de LinkedIn {#linkedin-ad-types}

[!DNL Marketo Measure] admitirá:

**Contenido patrocinado:** El contenido patrocinado le permite enviar contenido a la fuente [!DNL LinkedIn] de miembros además de a los que siguen a su compañía. El contenido patrocinado se puede dirigir a una audiencia específica y puede ayudar a los anunciantes a llegar a los miembros de [!DNL LinkedIn] dondequiera y cuando participen en la plataforma [!DNL LinkedIn] en equipos de escritorio, dispositivos móviles y tabletas. Se admite el contenido patrocinado con Forms de generación de posibles clientes.

Los tipos de formatos de anuncios de contenido patrocinado admitidos por [!DNL Marketo Measure] son anuncios de imagen única y anuncios de vídeo (a través de Forms de generación de clientes potenciales). Debido a la complejidad del esquema, no se admiten anuncios de carrusel.

[!DNL Marketo Measure] no admite mensajes patrocinados, anuncios de texto o anuncios dinámicos.

![Tipos de formato de anuncio de LinkedIn que muestran opciones de anuncios de imagen única, anuncios de vídeo y carrusel con compatibilidad con Forms de generación de clientes potenciales](assets/one.png)

>[!TIP]
>Para cualquiera de sus campañas/gastos que se originen a partir de una fuente de contenido no patrocinada (como el tipo de campaña &quot;Anuncio de texto&quot; o &quot;Correo electrónico patrocinado&quot;), [!DNL Marketo Measure] no _no_ admite de forma inherente el seguimiento de estos tipos de campañas. Si desea rastrear el gasto en campañas como esta junto con su gasto en &quot;contenido patrocinado&quot;, asegúrese de usar nuestro CSV de gasto en marketing para registrar manualmente dicho gasto.

## Cómo funciona: Contenido patrocinado {#how-it-works-sponsored-content}

>[!NOTE]
>Antes de usar por primera vez, esta configuración de característica debe habilitarse navegando a [!DNL Marketo Measure] [!UICONTROL Configuración] > [!UICONTROL Integraciones] > [!UICONTROL Anuncios] > [!UICONTROL Habilitar Forms de generación de clientes potenciales de LinkedIn].

**[!DNL LinkedIn's]requisitos exclusivos de etiquetado automático**

[!DNL Marketo Measure] puede ayudar a rastrear el rendimiento de tu campaña [!DNL LinkedIn] al etiquetar automáticamente tus páginas de aterrizaje.

[!DNL Marketo Measure] buscará elementos creativos con un recurso compartido de LinkedIn único y agregará un parámetro `?_bl={creativeId}` al final.

**Copiando recursos compartidos**

Con esta integración de [!DNL Marketo Measure/LinkedIn], pedimos a los clientes que no copien, clonen ni dupliquen elementos creativos existentes. Si se encuentran Recursos compartidos y se detectan para que solo se usen en un Creative, [!DNL Marketo Measure] puede etiquetar el Recurso compartido tal cual sin tener que recrear ningún Creativo o Recurso compartido y todo el historial de anuncios (impresiones, clics, recursos compartidos) permanecerá.

Tan pronto como se encuentre que un recurso compartido se comparte entre varios elementos creativos, [!DNL Marketo Measure] tendrá que pasar por un proceso de pausar, copiar y volver a etiquetar para crear un conjunto único. [!DNL Marketo Measure] pausará y archivará los elementos creativos activos y, por lo tanto, borrará el Historial de anuncios, incluidas las impresiones, los clics y los recursos compartidos en medios sociales, para etiquetar automáticamente todo correctamente.

Más adelante, [!DNL Marketo Measure] recomienda que no duplique ningún recurso compartido de [!DNL LinkedIn] y que mantenga todos los elementos creativos y recursos compartidos tan únicos como sea posible para que simplemente podamos agregar nuestro seguimiento sin tener que borrar el historial de anuncios.

**URL abreviadas**

El motivo del paso adicional es que LinkedIn permite que las direcciones URL de destino sean una dirección URL abreviada (bit.ly, goog.le, etc.,), lo que significa que [!DNL Marketo Measure] no ve la dirección URL larga y resuelta y [!DNL Marketo Measure] necesita agregar parámetros de seguimiento a una dirección URL resuelta. Para evitar ese problema, [!DNL Marketo Measure] busca direcciones URL abreviadas antes de volver a crear un anuncio, expande la dirección URL y, a continuación, crea el nuevo anuncio con la dirección URL resuelta y todos sus parámetros, lo que permite que [!DNL Marketo Measure] agregue etiquetas. La creación de un nuevo anuncio borrará el historial de anuncios (impresiones, clics, usos compartidos), por lo que se necesita permiso para etiquetar direcciones URL abreviadas.

Si utiliza abundantemente direcciones URL abreviadas, esto podría afectar gravemente a sus elementos creativos. Le recomendamos que ya no utilice direcciones URL abreviadas para que [!DNL Marketo Measure] pueda etiquetar las páginas de aterrizaje sin tener que crear anuncios nuevos y borrar el Historial de anuncios.

**El proceso**

Empecemos con algunos ejemplos. Digamos que lo hemos hecho....

Creative A : Compartir 123\
Creative B : uso compartido 234\
Creative C : uso compartido 234\
Creative D : Compartir 234

![Diagrama que muestra cuatro creativos con sus recursos compartidos asociados antes del proceso de etiquetado automático](assets/two.png)

`1)` [!DNL Marketo Measure] buscará primero en todas las campañas, elementos creativos y recursos compartidos con el estado &quot;Activo&quot;. [!DNL Marketo Measure] no etiquetará anuncios en pausa, archivados o cancelados. Si un anuncio se pausó y luego se estableció en [!UICONTROL activo], lo etiquetaremos una vez que esté activo de nuevo. Si podemos encontrar un recurso compartido único, lo que significa que no se utiliza en varios elementos creativos o campañas (por ejemplo, Creative A : recurso compartido 123), [!DNL Marketo Measure] agregará nuestro parámetro personalizado `>> ?_bl={creativeId}` a la dirección URL del recurso compartido.

`2)` Ahora, si el recurso compartido se ha compartido y ha perdido su exclusividad (por ejemplo, Creative B : Recurso compartido 234 y Creative C : Recurso compartido 234 y Creative D : Recurso compartido 234), [!DNL Marketo Measure] hará una pausa y archivará todos los elementos creativos similares (que serían Creative B, Creative C y Creative D).

`3)` [!DNL Marketo Measure] creará tres nuevos elementos creativos, Creative E, Creative F y Creative G, que copiarán el contenido de Creative B, que se archivará.

`4)` [!DNL Marketo Measure] también creará 3 recursos compartidos nuevos, Compartir 345, Compartir 456 y Compartir 567, que copian el contenido de Compartir 234, excepto que tendrá su propio etiquetado único de `?_bl`.

`5)` [!DNL Marketo Measure] tendrá que comprobar con regularidad que los recursos compartidos no se comparten y, si lo hacen, reiniciaremos el proceso en el paso 2 anterior.

>[!NOTE]
>La implementación de esto significará que nuestros clientes perderán el historial de anuncios de Creative B : Compartir 234, Creative C : Compartir 234 y Creative D : Compartir 234 porque ahora se vuelve a crear con Creative E : Compartir 345, Compartir F : Compartir 456 y Creative G : Compartir 567 respectivamente.

![Diagrama que muestra los nuevos creativos con recursos compartidos únicos creados después del proceso de etiquetado y archivado automático](assets/three.png)

## Cómo funciona: Forms de generación de clientes potenciales {#how-it-works-lead-gen-forms}

**[!DNL LinkedIn's]requisitos exclusivos de etiquetado automático**

[!DNL Marketo Measure] puede ayudar a rastrear el rendimiento de tu campaña [!DNL LinkedIn] al etiquetar automáticamente tus páginas de aterrizaje.

[!DNL Marketo Measure] buscará elementos creativos con un recurso compartido de LinkedIn único y agregará un parámetro `?_bl={creativeId}` al final.

**El proceso**

A través de la API de formularios de publicidad [!DNL LinkedIn's] y la API de respuesta de formularios de publicidad, podemos recopilar datos de envío de formularios para una cuenta de publicidad y asociar la dirección de correo electrónico a un posible cliente desde CRM o Marketo.

Los formularios de LinkedIn pueden contener varias direcciones de correo electrónico. Cuando descarguemos respuestas de formulario, buscaremos direcciones de correo electrónico con la siguiente prioridad: Correo electrónico de trabajo, Dirección de correo electrónico (campo de formulario principal) o campos personalizados con un valor de correo electrónico válido.

Independientemente del estado de Campaign o Creative, todas las respuestas de formulario resultarán en un punto de contacto. [!DNL Marketo Measure] tiene una restricción retrospectiva de 90 días, por lo que [!DNL Marketo Measure] no puede acceder a las respuestas del formulario con más de 90 días, pero cuanto más tiempo esté habilitada la integración de [!DNL Marketo Measure] y [!DNL LinkedIn], más puntos de contacto del formulario de generación de clientes potenciales serán visibles a través de [!DNL Marketo Measure].

>[!NOTE]
>Los costes de LinkedIn se siguen descargando como parte de las campañas de contenido patrocinadas.

**Seguimiento de Forms de generación de clientes potenciales en CRM o Marketo**

Antes de que existiera la integración de Forms de generación de clientes potenciales de [!DNL Marketo Measure] y LinkedIn, era práctica común que los clientes insertaran sus envíos de formularios a un programa de Marketo o a una campaña de CRM para rastrear los formularios y recibir atribución en esas actividades. Una vez habilitada la configuración de Forms de generación de posibles clientes, queremos asegurarnos de que los envíos de formularios no se cuenten dos veces. Compruebe lo siguiente:

* El campo &quot;Habilitar puntos de contacto del comprador&quot; en el objeto CRM está establecido en &quot;Ninguno&quot; o &quot;Excluir todos los miembros de la campaña&quot;
* Actualizar cualquier programa de Marketo relacionado o reglas de actividad de Marketo
* Actualizar cualquier regla de CRM Campaign relacionada

>[!NOTE]
>La API de LinkedIn tiene una limitación retrospectiva de 90 días, por lo que si utiliza reglas de Marketo o CRM, se recomienda establecer la fecha de finalización de la regla en 90 días antes de la fecha en la que habilitó la integración en [!DNL Marketo Measure].

## Detalles del Touchpoint {#touchpoint-details}

Después de que [!DNL Marketo Measure] haya etiquetado correctamente su página de aterrizaje en el elemento creativo de LinkedIn, podrá ver los datos de anuncios resueltos en el punto de contacto. Esta es la asignación de valores de datos que debería ver:

<table>
 <colgroup>
  <col>
  <col>
 </colgroup>
 <tbody>
  <tr>
   <th style="width:30%">Campo Touchpoint</th>
   <th>Valor de muestra</th>
  </tr>
  <tr>
   <td>ID de anuncio</td>
   <td>84186224</td>
  </tr>
  <tr>
   <td>Contenido de anuncios</td>
   <td>copy-1-image-2-man El 95 % de los especialistas en marketing #B2B consideran que la estrategia de creación de demanda es exitosa. Más información: [!DNL https]://lnkd.in/jgdi50vKrgv</td>
  </tr>
  <tr>
   <td>ID de grupo de publicidad</td>
   <td>(En blanco)</td>
  </tr>
  <tr>
   <td>Nombre del grupo de anuncios</td>
   <td>(En blanco)</td>
  </tr>
  <tr>
   <td>ID de campaña de publicidad</td>
   <td>138949954</td>
  </tr>
  <tr>
   <td>Nombre de campaña de anuncios</td>
   <td>SU - Cuentas COM - Capacidades de demanda</td>
  </tr>
  <tr>
   <td>URL de destino de anuncio <b>*</b></td>
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217</td>
  </tr>
  <tr>
   <td>Formulario/URL</td>
   <td>info.bizible.com/demo</td>
  </tr>
  <tr>
   <td>URL del formulario: sin procesar</td>
   <td>info.bizible.com/demo</td>
  </tr>
  <tr>
   <td>ID de palabra clave</td>
   <td>(En blanco)</td>
  </tr>
  <tr>
   <td>Tipo de coincidencia de palabra clave</td>
   <td>(En blanco)</td>
  </tr>
  <tr>
   <td>Página de destino</td>
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders</td>
  </tr>
  <tr>
   <td>Página de aterrizaje: sin procesar</td>
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217</td>
  </tr>
  <tr>
   <td>Canal de marketing</td>
   <td>Social de pago</td>
  </tr>
  <tr>
   <td>Canal de marketing: ruta</td>
   <td>Social de pago.LinkedIn</td>
  </tr>
  <tr>
   <td>Medio</td>
   <td>"cpc" o "Formulario de generación de clientes potenciales"</td>
  </tr>
  <tr>
   <td>Página del referenciador</td>
   <td>www.linkedin.com/</td>
  </tr>
  <tr>
   <td>Página de referente: sin procesar</td>
   <td>www.linkedin.com/</td>
  </tr>
  <tr>
   <td>Frase de búsqueda</td>
   <td>(En blanco)</td>
  </tr>
  <tr>
   <td>Tipo de Touchpoint</td>
   <td>Formulario web</td>
  </tr>
  <tr>
   <td>Origen del Touchpoint</td>
   <td>LinkedIn</td>
  </tr>
 </tbody>
</table>

**&#42;** _El campo &quot;URL de destino de anuncio&quot; solo se rellena para el contenido patrocinado. No se ha rellenado para Forms de generación de posibles clientes._

<br>

## Costos {#costs}

Dado que [!DNL Marketo Measure] tiene una integración directa con [!DNL LinkedIn], descargamos diariamente el gasto registrado para cada campaña y Creative. Ya no es necesario que un cliente informe sobre el gasto de [!DNL LinkedIn] en la aplicación [!DNL Marketo Measure].

Al igual que con otras integraciones de anuncios, [!DNL Marketo Measure] ha definido una regla de canal de marketing para colocar todas las [!DNL LinkedIn] campañas, elementos creativos y costos. Para usar la regla, el cliente querrá insertar una nueva fila para los esfuerzos de [!DNL LinkedIn] pagados. Puede ser un canal nuevo o existente. En la columna Referente, use la definición &quot;[[!DNL LinkedIn] de pago]&quot; que [!DNL Marketo Measure] ha definido como cualquier punto de contacto con la etiqueta [!DNL Marketo Measure].

![Configuración de regla de canal de marketing que muestra la definición de canal de pago de LinkedIn con la columna de referente](assets/four.png)

## [!DNL Marketo Measure] Discover {#marketo-measure-discover}

Se han realizado algunas mejoras en [!DNL Marketo Measure] Discover para admitir informes de Forms de generación de clientes potenciales.

**Tablero de medios de pago**

Mosaico Forms de generación de posibles clientes: nuevo mosaico que incluye un recuento de los rellenos de formulario de LinkedIn. La obtención de detalles de este recuento mostrará el ID de actividad, la fecha del formulario, el nombre del formulario y la dirección de correo electrónico.

**Tablero de rutas de participación**

Recorrido de eventos: incluye el tipo de evento &quot;Actividad&quot; y el medio &quot;Formulario de generación de posibles clientes&quot; para los formularios que se incluyen en la integración. La vista de obtención de detalles incluye detalles de Campaign, Creative y Form.

## Preguntas frecuentes sobre contenido patrocinado {#sponsored-content-faq}

**¿Qué es un recurso compartido oscuro?**

Un recurso compartido oscuro es una publicación en la que nunca se publica en la página de la compañía y se crea inmediatamente y se agrega directamente como Creative. Para que los creativos creados por [!DNL Marketo Measure] no aparezcan en la parte superior de la página de una compañía y sean promocionados de nuevo, se utilizan recursos compartidos oscuros para que puedan lanzarse entre bastidores.

**¿Qué estados etiqueta [!DNL Marketo Measure] en realidad?**

Hay cuatro estados diferentes en una campaña de [!DNL LinkedIn] y en Creative: Activo, En pausa, Archivado y Cancelado. Solo etiquetamos las campañas y los elementos creativos que están activos. Al etiquetar otros estados, se vuelven a establecer como Activos. [!DNL Marketo Measure] no etiquetará campañas o creativos en pausa, archivados o cancelados, pero reanudará el etiquetado si el estado cambia a Activo.

**¿Cuál es el valor que [!DNL Marketo Measure] está usando para etiquetar?**

Al final de la dirección URL de destino, [!DNL Marketo Measure] agrega el parámetro `&_bl={creativeId}`, donde `{creativeId}` es el Creative Id de LinkedIn. Con el ID de Creative, [!DNL Marketo Measure] también puede determinar el ID de campaña, ya que [!DNL LinkedIn] tiene una estructura de anuncios bastante básica, ya que cada Creative solo puede pertenecer a una campaña.

**¿Qué sucede con mi antiguo creativo una vez que [!DNL Marketo Measure] crea una nueva versión?**

Cuando [!DNL Marketo Measure] vuelve a crear un recurso compartido y lo coloca en un nuevo Creative, se archiva el Creative antiguo. Esta es también la razón por la que [!DNL Marketo Measure] no etiquetará campañas archivadas o creativos; de lo contrario, se reproduciría con [!DNL Marketo Measure] intentando etiquetarlo indefinidamente.

**¿Por qué la dirección URL de destino del anuncio creado no coincide con mi anuncio original?**

[!DNL Marketo Measure] necesita agregar los parámetros de seguimiento a una dirección URL resuelta, pero la dirección URL que se presenta en la API puede ser potencialmente una dirección URL abreviada sin todos los parámetros presentes. Para evitar ese problema, [!DNL Marketo Measure] busca direcciones URL abreviadas antes de volver a crear una adición, la resuelve y, a continuación, crea la nueva publicidad con la dirección URL resuelta y todos sus parámetros, lo que permite que [!DNL Marketo Measure] agregue etiquetas.

**¿Estás etiquetando todos mis anuncios? ¿No veo el parámetro bl en todas mis páginas de aterrizaje?**

Hemos observado que algunos especialistas en marketing colocarán un vínculo de imagen en la dirección URL de destino, que [!DNL Marketo Measure] no puede etiquetar, por lo que buscamos la dirección URL dentro del contenido del anuncio. Si [!DNL Marketo Measure] tiene permisos para etiquetar direcciones URL abreviadas, expandiremos la dirección URL y la etiquetaremos, pero debido a la estructura de copia de LinkedIn, se acorta automáticamente dentro del texto. La etiqueta se muestra en la URL abreviada de LinkedIn, que aparece en el campo Contenido de publicidad del punto de contacto en lugar de en el campo Página de aterrizaje: sin procesar.

**No, alguien de mi equipo clonó accidentalmente un recurso compartido. ¿Puedo pausarlo?**

No te preocupes. [!DNL Marketo Measure] comprobará mediante programación si hay recursos compartidos que ya no son únicos, lo que significa que se han copiado en otro Creative. Una vez detectada esa copia, [!DNL Marketo Measure] seguirá el flujo habitual para etiquetar y crear anuncios nuevos.

**Mi anuncio estaba pendiente de revisión anteriormente. ¿Por qué está pendiente de revisión nuevamente después de que [!DNL Marketo Measure] la etiquetara?**

LinkedIn requiere que todos los anuncios que se crean o modifican sigan el proceso de seguridad normal antes de publicarse. [!DNL Marketo Measure] intenta interceptar el anuncio lo más rápido posible, ya que busca nuevos anuncios cada 6 horas, pero con [!DNL LinkedIn's] paso adicional, puede retrasar el lanzamiento unas horas.

**Hay dos direcciones URL en mi anuncio. ¿Cuál se etiqueta?**

Ambos. La integración de [!DNL Marketo Measure] nos permite etiquetar la dirección URL de destino de la imagen de pulsación en el anuncio, pero también actualiza automáticamente la dirección URL abreviada en la descripción del anuncio.

![Anuncio de LinkedIn que muestra tanto la URL de destino como la URL abreviada en la descripción que se etiquetan](assets/five.png)

**He conectado mi cuenta de [!DNL LinkedIn ads]. ¿Por qué [!DNL Marketo Measure] no está etiquetando mis vínculos?**

El usuario de [!DNL LinkedIn] conectado necesita tener acceso de edición adecuado, lo que significa que el usuario debe ser un administrador de cuentas, un administrador de campaña o un administrador de Creative.

**¿Cómo sé si se copiará mi elemento creativo? ¿Puedo ver si mis creativos están usando el mismo recurso compartido?**

El identificador compartido no se ha proporcionado en un informe [!DNL LinkedIn], por lo que no existe una forma clara y obvia de comprobar las asignaciones de creatividad a uso compartido. Si cree que un elemento creativo puede ser una copia, puede comprobarlo manualmente abriendo el anuncio desde el administrador de campañas de [!DNL LinkedIn]; esto abre el anuncio en una nueva pestaña y puede encontrar el ID compartido en la dirección URL.

![Administrador de LinkedIn Campaign que muestra el anuncio abierto en una nueva pestaña con el identificador compartido visible en la dirección URL](assets/six.png)

## Preguntas frecuentes sobre Lead Gen Forms {#lead-gen-forms-faq}

**¿Cuál es el costo de esta mejora?**

Esta oferta se incluye con cualquier suscripción de [!DNL Marketo Measure] de pago.

**¿La integración es retroactiva?**

Sí, descargaremos respuestas de formularios y anuncios históricos de LinkedIn, aunque nos limitaremos a la ventana retrospectiva de 90 días. Cuanto más tiempo esté habilitada la integración de [!DNL Marketo Measure] y LinkedIn, más puntos de contacto del formulario de generación de clientes potenciales serán visibles a través de [!DNL Marketo Measure].

No hay ninguna opción para establecer una fecha específica para la descarga, pero puede establecer de forma opcional las reglas de eliminación de puntos de contacto si hay puntos de contacto que necesite suprimir.

**¿Se activará automáticamente si ya estoy usando la integración de anuncios de LinkedIn de [!DNL Marketo Measure]?**

No, no empezaremos a descargarla automáticamente para todos los clientes, pero es muy sencillo activar esta función en los ajustes.

**¿Están disponibles los datos del formulario?**

Los datos del formulario están disponibles a través de [!DNL Marketo Measure] Discover, incluidos el identificador y el nombre del formulario. Los detalles del formulario aún no están disponibles en los objetos de punto de contacto en CRM.

**¿Qué les sucede a [!DNL LinkedIn] posibles clientes que se hayan sincronizado previamente con Programas de Marketo o Campañas CRM?**

Se recomienda ajustar cualquier regla [!DNL Marketo Measure] para generar puntos de contacto desde esos programas o campañas específicos a fin de evitar duplicaciones. La API de LinkedIn tiene una limitación retrospectiva de 90 días, por lo que si utiliza reglas de Marketo o CRM, se recomienda establecer la fecha de finalización de la regla en 90 días antes de la fecha en la que habilitó la integración en [!DNL Marketo Measure]. A partir de este momento, [!DNL Marketo Measure] puede descargar estos posibles clientes con mayor insight y detalles.

**¿Hay algún etiquetado automático o seguimiento involucrado?**

No, esto es diferente de otras integraciones de [!DNL Marketo Measure]. En lugar de modificar la página de aterrizaje (ya que no hay ningún clic en esta página), solo descargamos la información relevante de LinkedIn y la tratamos como actividades dentro de [!DNL Marketo Measure].
