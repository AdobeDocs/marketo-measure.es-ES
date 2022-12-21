---
unique-page-id: 35586080
description: 'Integración de linkedIn: [!DNL Marketo Measure] - Documentación del producto'
title: Integración de linkedIn
exl-id: 705209ef-1ece-496c-ac2f-6a31055bd993
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '2603'
ht-degree: 1%

---

# Integración de linkedIn {#linkedin-integration}

## Resumen {#overview}

La variable [!DNL Marketo Measure] la integración con LinkedIn consta de dos partes:

Contenido patrocinado: La integración de contenido patrocinado permite [!DNL Marketo Measure] para etiquetar direcciones URL de destino en [!DNL LinkedIn] anuncios, que finalmente permite [!DNL Marketo Measure] para seguir a un usuario a través de su recorrido de punto de contacto completo y volver a asignar la actividad al [!DNL LinkedIn] Campaña y creativo. Esto proporciona a los clientes información sobre el ROI de sus [!DNL LinkedIn] actividad.

Generador de posibles clientes Forms: Gracias a la integración con LinkedIn Lead Gen Forms, Marketo Measure obtiene información sobre los formularios enviados a través de la plataforma LinkedIn. Estos rellenos de formulario se comparan con posibles clientes de su CRM o [!DNL Marketo Engage] para que sean aptos para la atribución. Con una perspectiva de la campaña, el creativo y el formulario que ayudó a generar los formularios, los equipos ahora pueden optimizar aún más su gasto en publicidad y marketing de LinkedIn.

## Disponibilidad {#availability}

Disponible para todos los clientes.

## Requisitos {#requirements}

**Funciones del administrador de campañas**

Para [!DNL Marketo Measure] para poder descargar los datos de costes de anuncios y anuncios, debe tener una de las siguientes funciones en el administrador de campañas:

* Administrador de facturación
* Administrador de cuentas
* Administrador de campañas

Más información: [Funciones y roles de usuario en el Administrador de campañas](https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager).

**Funciones de administrador de medios pagados**

Para [!DNL Marketo Measure] para poder crear/actualizar elementos creativos patrocinados, debe tener una de las siguientes funciones de administrador de medios pagados:

* Afiche de contenido patrocinado
* Forms Manager de Generación de posibles clientes

Más información: [Funciones de administración de páginas de linkedIn](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

Hay otros [!DNL LinkedIn] roles que hacemos **not** para nuestra integración. Estas funciones a menudo se confunden con las funciones requeridas, por lo que tenga en cuenta que hay una diferencia.

**Funciones de administración de la página**

Para [!DNL Marketo Measure] para poder descargar/integrar posibles clientes desde los formularios de posibles clientes, debe tener la siguiente función de administrador de página:

* Superadministrador

Más información: [Funciones de administración de páginas de linkedIn](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

## Tipos de anuncios de linkedIn {#linkedin-ad-types}

[!DNL Marketo Measure] admitirá:

**Contenido patrocinado:** El contenido patrocinado le permite enviar contenido al [!DNL LinkedIn] fuente de miembros más allá de los que siguen a su empresa. El contenido patrocinado se puede dirigir a una audiencia específica y puede ayudar a los anunciantes a alcanzar [!DNL LinkedIn] miembros, dondequiera y cuando estén participando en el [!DNL LinkedIn] plataforma en equipos de escritorio, móviles y tabletas. Se admite el contenido patrocinado con Forms de Generación de posibles clientes.

Los tipos de formatos de anuncios de contenido patrocinado admitidos por [!DNL Marketo Measure] son anuncios de imagen única y anuncios de vídeo (a través de la generación de posibles clientes Forms). Debido a la complejidad del esquema, no se admiten anuncios de Carrusel.

[!DNL Marketo Measure] no es compatible con la mensajería patrocinada, los anuncios de texto o los anuncios dinámicos.

![](assets/one.png)

>[!TIP]
>
>Para cualquiera de las campañas/gastos que se originen en una fuente de contenido no patrocinada (como el tipo de campaña de &quot;anuncio de texto&quot; o &quot;InMail patrocinado&quot;), [!DNL Marketo Measure] does _not_ admiten de forma inherente el seguimiento de estos tipos de campaña. Si desea rastrear los gastos de campañas como esta junto con los gastos de &quot;Contenido patrocinado&quot;, asegúrese de utilizar nuestro CSV de gastos de marketing para registrar manualmente dichos gastos.

## Cómo funciona: Contenido patrocinado {#how-it-works-sponsored-content}

>[!NOTE]
>
>Antes de la primera utilización, esta configuración de función debe habilitarse navegando a [!DNL Marketo Measure] [!UICONTROL Configuración] > [!UICONTROL Integraciones] > [!UICONTROL Publicidades] > [!UICONTROL Habilitar LinkedIn Lead Gen Forms].

**[!DNL LinkedIn's]Requisitos únicos de etiquetado automático**

[!DNL Marketo Measure] puede ayudarle a realizar el seguimiento de [!DNL LinkedIn] rendimiento de la campaña mediante el etiquetado automático de las páginas de aterrizaje.

[!DNL Marketo Measure] buscará creativos con un uso compartido único de LinkedIn y agregará un `?_bl={creativeId}` al final del parámetro.

**Copia de elementos compartidos**

Con esto [!DNL Marketo Measure/LinkedIn] Integración, pedimos que los clientes no copien, clonen o dupliquen los elementos creativos existentes. Si se encuentran elementos compartidos y se detecta que solo se utilizan en un elemento creativo, [!DNL Marketo Measure] Puede etiquetar el Compartir como está sin tener que volver a crear ningún elemento creativo o compartido y se conservará todo el historial de anuncios (impresiones, clics, compartidos).

Tan pronto como se encuentra una acción compartida que se comparte entre varios elementos creativos, [!DNL Marketo Measure] tendrá que ejecutar un proceso de pausar, copiar y volver a etiquetar para crear un conjunto único. [!DNL Marketo Measure] pondrán en pausa y archivarán los elementos creativos activos y, por lo tanto, borrarán el historial de anuncios, incluidas las impresiones, los clics y los recursos compartidos sociales, para etiquetar automáticamente todo correctamente.

Avanzando, [!DNL Marketo Measure] recomienda que no duplique ninguna [!DNL LinkedIn] Comparte y mantiene todos los elementos creativos y compartidos lo más únicos posible para que podamos simplemente agregar nuestro seguimiento sin tener que borrar el historial de anuncios.

**URL abreviadas**

El motivo del paso adicional es que LinkedIn permite que las direcciones URL de destino sean una URL abreviada (bit.ly, goog.le, etc.), lo que significa [!DNL Marketo Measure] no ve la URL larga resuelta y [!DNL Marketo Measure] debe agregar parámetros de seguimiento a una URL resuelta. Para evitar este problema, [!DNL Marketo Measure] busca direcciones URL abreviadas antes de volver a crear una publicidad, expande la dirección URL y luego crea la nueva publicidad con la dirección URL resuelta y todos sus parámetros, lo que permite [!DNL Marketo Measure] para agregar etiquetas. Al crear una publicidad nueva se borrará el historial de publicidades (impresiones, clics, compartidos), por lo que es necesario tener permiso para etiquetar direcciones URL abreviadas.

Si utiliza direcciones URL abreviadas en gran medida, esto podría afectar gravemente a los elementos creativos. Le recomendamos que ya no utilice direcciones URL abreviadas para que [!DNL Marketo Measure] pueden etiquetar las páginas de aterrizaje sin tener que crear anuncios nuevos y borrar el historial de anuncios.

**El proceso**

Empecemos con algunos ejemplos. Digamos que tenemos....

Creativo A : Compartir 123\
Creativo B : Compartir 234\
Creative C : Compartir 234\
Creative D : Compartir 234

![](assets/two.png)

`1)` [!DNL Marketo Measure] buscará primero todas las campañas, elementos creativos y compartidos con estado &quot;Activo&quot;. [!DNL Marketo Measure] no etiquetará anuncios en pausa, archivados o cancelados. Si se detuvo una publicidad, establezca como [!UICONTROL active], lo etiquetaremos una vez que vuelva a estar activo. Si podemos encontrar un recurso compartido único, lo que significa que no se utiliza en varios elementos creativos o campañas (por ejemplo, creativo A : Compartir 123), [!DNL Marketo Measure] agregará nuestro parámetro personalizado `>> ?_bl={creativeId}` a la URL del recurso compartido.

`2)` Ahora, si el recurso compartido se ha compartido y ha perdido su exclusividad (por ejemplo, Creative B : Compartir 234 y Creative C : Compartir 234 y Creative D : Compartir 234), [!DNL Marketo Measure] pondrán en pausa y archivarán todos los creativos similares (que serían Creative B, Creative C y Creative D).

`3)` [!DNL Marketo Measure] creará 3 nuevos creativos, Creative E, Creative F y Creative G, que copiarán el contenido de Creative B, que está archivado.

`4)` [!DNL Marketo Measure] también creará 3 nuevos elementos compartidos, Share 345, Share 456 y Share 567, que copian el contenido de Share 234, excepto que tendrá su propio `?_bl` etiquetado.

`5)` [!DNL Marketo Measure] Tendrá que comprobar regularmente que las acciones no se comparten y, si lo hacen, reiniciaremos el proceso en el paso 2 anterior.

>[!NOTE]
>
>Implementar esto significa que nuestros clientes perderán el historial de anuncios del Creative B : Compartir 234, Creative C : Compartir 234 y Creative D : Compartir 234 porque ahora se vuelve a crear con Creative E : Compartir 345, Compartir F : Compartir 456 y Creative G : Compartir 567 respectivamente.

![](assets/three.png)

## Cómo funciona: Forms de generación de posibles clientes {#how-it-works-lead-gen-forms}

**El proceso**

Hasta [!DNL LinkedIn's] API de formulario de anuncio y API de respuesta de formulario de anuncio, podemos recopilar datos de envío de formulario para una cuenta de anuncio y asociar la dirección de correo electrónico a un posible cliente desde CRM o Marketo.

Los formularios de linkedIn pueden contener varias direcciones de correo electrónico. Cuando descarguemos respuestas de formulario, buscaremos direcciones de correo electrónico con la siguiente prioridad: Trabajo por correo electrónico, dirección de correo electrónico (campo de formulario principal) o campos personalizados con un valor de correo electrónico válido.

Independientemente del estado de campaña o creativo, todas las respuestas de formulario resultarán en un punto de contacto. [!DNL Marketo Measure] tiene una restricción retrospectiva de 90 días, por lo que [!DNL Marketo Measure] no puede acceder a las respuestas del formulario que tengan más de 90 días, pero cuanto más tiempo tenga la variable [!DNL Marketo Measure] y [!DNL LinkedIn] la integración está habilitada, cuantos más puntos de contacto de formulario de posible cliente se puedan ver a través de [!DNL Marketo Measure].

>[!NOTE]
>
>Los costes de linkedIn se siguen descargando como parte de las campañas de contenido patrocinado.

**Seguimiento de la generación de posibles clientes Forms en CRM o Marketo**

Antes de que [!DNL Marketo Measure] y la integración de LinkedIn Lead Gen Forms existía, era una práctica habitual que los clientes insertaran sus envíos de formularios en un programa de Marketo o en una campaña CRM para rastrear los formularios y recibir atribución sobre esas actividades. Una vez que la configuración de Forms de Generación de posibles clientes está activada, queremos asegurarnos de que esos envíos de formularios no se contabilicen dos veces. Compruebe lo siguiente:

* El campo &quot;Habilitar puntos de contacto del comprador&quot; del objeto CRM está configurado en &quot;Ninguno&quot; o &quot;Excluir todos los miembros de la campaña&quot;
* Actualizar cualquier programa de Marketo o regla de actividad de Marketo relacionado
* Actualizar cualquier regla de CRM Campaign relacionada

>[!NOTE]
>
>La API de LinkedIn tiene una limitación retrospectiva de 90 días, por lo que si utiliza reglas de Marketo o CRM, se recomienda establecer la fecha de finalización de la regla en 90 días antes de la fecha en la que habilitó la integración en [!DNL Marketo Measure].

## Detalles del Touchpoint {#touchpoint-details}

Una vez [!DNL Marketo Measure] ha etiquetado correctamente su página de aterrizaje en el creativo de LinkedIn, podrá ver los datos de anuncios resueltos en el punto de contacto. Esta es la asignación de valores de datos que debería esperar ver:

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>Campo de punto de contacto</th> 
   <th>Valor de muestra</th> 
  </tr> 
  <tr> 
   <td><p>ID de anuncio </p></td> 
   <td><p>84186224 </p></td> 
  </tr> 
  <tr> 
   <td><p>Contenido de la publicidad </p></td> 
   <td><p>copy-1-image-2-man El 95% de los especialistas en marketing #B2B consideran que la estrategia de creación de demanda es exitosa. Más información: [!DNL https]://lnkd.in/jgdi50vKrgv</p></td> 
  </tr> 
  <tr> 
   <td><p>ID del grupo de publicidad </p></td> 
   <td><p>(en blanco) </p></td> 
  </tr> 
  <tr> 
   <td><p>Nombre del grupo de anuncios </p></td> 
   <td><p>(en blanco) </p></td> 
  </tr> 
  <tr> 
   <td><p>ID de campaña de publicidad </p></td> 
   <td><p>138949954 </p></td> 
  </tr> 
  <tr> 
   <td><p>Nombre de campaña de publicidad </p></td> 
   <td><p>EE. UU. - Cuentas COM - Capacidades de demanda </p></td> 
  </tr> 
  <tr> 
   <td><p>Dirección URL del destino de la publicidad </p></td> 
   <td><p>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217 </p></td> 
  </tr> 
  <tr> 
   <td><p>Formulario/URL </p></td> 
   <td><p>info.bizible.com/demo </p></td> 
  </tr> 
  <tr> 
   <td><p>URL del formulario: sin procesar </p></td> 
   <td><p>info.bizible.com/demo </p></td> 
  </tr> 
  <tr> 
   <td><p>Id De Palabra Clave </p></td> 
   <td><p>(en blanco) </p></td> 
  </tr> 
  <tr> 
   <td><p>Tipo de coincidencia de palabra clave </p></td> 
   <td><p>(en blanco) </p></td> 
  </tr> 
  <tr> 
   <td><p>Página de aterrizaje </p></td> 
   <td><p>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders </p></td> 
  </tr> 
  <tr> 
   <td><p>Página de aterrizaje: sin procesar </p></td> 
   <td><p>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217 </p></td> 
  </tr> 
  <tr> 
   <td><p>Canal de marketing </p></td> 
   <td><p>Social de pago </p></td> 
  </tr> 
  <tr> 
   <td><p>Canal de marketing: ruta </p></td> 
   <td><p>Social.LinkedIn de pago </p></td> 
  </tr> 
  <tr> 
   <td><p>Media </p></td> 
   <td><p>"cpc" o "Formulario de generación de posibles clientes"</p></td> 
  </tr> 
  <tr> 
   <td><p>Página del referenciador </p></td> 
   <td><p>www.linkedin.com/ </p></td> 
  </tr> 
  <tr> 
   <td><p>Página Referente - Sin procesar </p></td> 
   <td><p>www.linkedin.com/ </p></td> 
  </tr> 
  <tr> 
   <td><p>Frase de búsqueda </p></td> 
   <td><p>(en blanco) </p></td> 
  </tr> 
  <tr> 
   <td><p>Tipo de Touchpoint </p></td> 
   <td><p>Formulario web </p></td> 
  </tr> 
  <tr> 
   <td><p>Fuente del Touchpoint </p></td> 
   <td><p>LinkedIn </p></td> 
  </tr> 
 </tbody> 
</table>

## Costos {#costs}

Porque [!DNL Marketo Measure] tiene una integración directa con [!DNL LinkedIn], descargamos todos los días el gasto registrado para cada campaña y creativo. No es necesario que un cliente informe de [!DNL LinkedIn] gastar dentro de [!DNL Marketo Measure] ya no es así.

Al igual que con otras integraciones de publicidad, [!DNL Marketo Measure] ha definido una regla de canal de marketing para colocar todo [!DNL LinkedIn] campañas, elementos creativos y costes. Para utilizar la regla, el cliente desea insertar una nueva fila para su valor de Pago [!DNL LinkedIn] esfuerzos. Puede ser un canal nuevo o existente. En la columna Referente , utilice la definición &quot;[[!DNL LinkedIn] Pagado]&quot; que [!DNL Marketo Measure] se ha definido como cualquier punto de contacto con un [!DNL Marketo Measure] etiqueta.

![](assets/four.png)

## [!DNL Marketo Measure] Discover {#marketo-measure-discover}

Se han realizado algunas mejoras en [!DNL Marketo Measure] Discover admitirá los informes de Forms de Generación de posibles clientes.

**Media Board de pago**

Título de la generación de posibles clientes en Forms: Nuevo mosaico que incluye el recuento de rellenos de formulario de LinkedIn. Para obtener más información sobre este recuento, se mostrarán el ID de actividad, la fecha del formulario, el nombre del formulario y la dirección de correo electrónico.

**Tablero de rutas de participación**

Recorrido de eventos: Incluye el tipo de evento &quot;Actividad&quot; y el medio &quot;Formulario de generación de posibles clientes&quot; para los formularios que pasan por la integración. La vista de detalles incluye detalles de Campaña, Creativo y Formulario.

## Preguntas frecuentes sobre el contenido patrocinado {#sponsored-content-faq}

**¿Qué es una cuota oscura?**

Un recurso compartido oscuro es una publicación en la que nunca se publica en la página de la empresa y se crea inmediatamente y se añade directamente como un elemento creativo. De modo que [!DNL Marketo Measure]Los elementos creativos creados por la empresa no aparecen en la parte superior de la página de la empresa y se vuelven a promocionar, se utilizan elementos compartidos oscuros para que se puedan iniciar entre bastidores.

**Qué estados hace [!DNL Marketo Measure] en realidad etiqueta?**

Hay cuatro estados diferentes en un [!DNL LinkedIn] Campaña y creativo: Activo, En pausa, Archivado y Cancelado. Solo se etiquetan campañas y elementos creativos que sean activos. Etiquetar otros estados los establece de nuevo en Activo. [!DNL Marketo Measure] no etiquetará Campañas o Creativos en pausa, archivados o cancelados, pero reanudará el etiquetado si el estado cambia a Activo.

**¿Cuál es el valor que [!DNL Marketo Measure] ¿utiliza para etiquetar?**

Al final de la dirección URL de destino, [!DNL Marketo Measure] está agregando el parámetro `&_bl={creativeId}`, donde la variable `{creativeId}` es el Creative Id de LinkedIn. Con el ID de creativo, [!DNL Marketo Measure] también puede determinar el ID de campaña ya que [!DNL LinkedIn] tiene una estructura de anuncios bastante básica, ya que cada creativo solo puede pertenecer a una campaña.

**¿Qué pasa con mi antiguo creativo una vez? [!DNL Marketo Measure] crea una nueva versión de él?**

When [!DNL Marketo Measure] recrea un recurso compartido y lo coloca en un nuevo elemento creativo; el elemento creativo antiguo se archiva. Por eso también [!DNL Marketo Measure] no etiquetará campañas o elementos creativos archivados; de lo contrario, se reproduciría en bucle con [!DNL Marketo Measure] tratando de etiquetarlo indefinidamente.

**¿Por qué la dirección URL de destino de la publicidad creada no coincide con mi anuncio original?**

[!DNL Marketo Measure] necesita añadir los parámetros de seguimiento a una URL resuelta, pero la URL que se presenta en la API puede ser potencialmente una URL acortada sin todos los parámetros presentes. Para evitar este problema, [!DNL Marketo Measure] busca direcciones URL abreviadas antes de volver a crear un anuncio, lo resuelve y, a continuación, crea el nuevo anuncio con la dirección URL resuelta y todos sus parámetros, lo que permite [!DNL Marketo Measure] para agregar etiquetas.

**¿Estás etiquetando todos mis anuncios? ¿No veo el parámetro bl en todas mis páginas de aterrizaje?**

Se ha observado que algunos especialistas en marketing pondrán un vínculo de imagen en la dirección URL de destino, que [!DNL Marketo Measure] no se puede etiquetar, por lo que buscamos la dirección URL dentro del contenido de la publicidad. If [!DNL Marketo Measure] tiene permisos para etiquetar direcciones URL abreviadas, expandiremos la dirección URL y la etiqueta que, pero debido a la estructura de copia de LinkedIn, se acorta automáticamente dentro del texto. La etiqueta se activará dentro de la URL acortada de LinkedIn, que aparecerá en el campo Contenido de anuncio del punto de contacto en lugar de en el campo Página de aterrizaje: Sin procesar .

**Oh no, alguien de mi equipo accidentalmente clonó una parte. ¿Puedo pausarlo?**

No hay preocupaciones. [!DNL Marketo Measure] comprobará mediante programación si hay elementos compartidos que ya no son únicos, lo que significa que desde entonces se han copiado en un elemento creativo diferente. Una vez detectada la copia, [!DNL Marketo Measure] seguirá el flujo habitual para etiquetar y crear nuevas publicidades.

**Mi anuncio estaba pendiente de revisión anteriormente. ¿Por qué está pendiente de revisión de nuevo después de [!DNL Marketo Measure] ¿lo etiquetó?**

linkedIn requiere que todas las publicidades creadas o modificadas atraviesen el proceso de seguridad normal antes de anunciarse. [!DNL Marketo Measure] intenta interceptar el anuncio lo más rápido posible, ya que busca nuevos anuncios cada 6 horas pero con [!DNL LinkedIn's] paso adicional, puede retrasar el lanzamiento unas horas.

**Hay 2 direcciones URL en mi anuncio. ¿Cuál se etiqueta?**

Ambas. La variable [!DNL Marketo Measure] la integración nos permite etiquetar la dirección URL de destino desde la imagen de pulsación en la publicidad, pero también actualiza automáticamente la dirección URL acortada en la descripción de la publicidad.

![](assets/five.png)

**He conectado mi [!DNL LinkedIn ads] cuenta. Why is not [!DNL Marketo Measure] ¿etiquetar mis vínculos?**

El [!DNL LinkedIn] El usuario debe tener acceso de edición adecuado, lo que significa que debe ser administrador de cuentas, administrador de campañas o administrador creativo.

**¿Cómo sé si mi elemento creativo se copiará? ¿Puedo ver si mis creativos están usando el mismo recurso compartido?**

El ID de uso compartido no se proporciona en un [!DNL LinkedIn] , por lo que no hay una manera clara y obvia de comprobar las asignaciones de Creative a Share. Si cree que un creativo puede ser una copia, puede comprobarla manualmente abriendo la publicidad desde su [!DNL LinkedIn] Administrador de campañas: se abrirá la publicidad en una pestaña nueva y en la URL encontrará el ID de uso compartido.

![](assets/six.png)

## Preguntas frecuentes sobre la Generación de posibles clientes en Forms {#lead-gen-forms-faq}

**¿Cuál es el coste de esta mejora?**

Esta oferta está incluida con cualquier pago [!DNL Marketo Measure] suscripción.

**¿La integración es retroactiva?**

Sí, descargaremos respuestas históricas de anuncios de LinkedIn, aunque estamos limitados a la ventana retrospectiva de 90 días. Cuanto más tiempo tenga la función [!DNL Marketo Measure] y la integración de LinkedIn está habilitada, cuantos más puntos de contacto de la generación de posibles clientes se puedan ver a través de [!DNL Marketo Measure].

No hay opción de establecer una fecha específica para la descarga, pero si hay puntos de contacto que debe suprimir, puede establecer reglas de eliminación de puntos de contacto.

**¿Se habilitará automáticamente si ya estoy utilizando la variable [!DNL Marketo Measure] ¿Integración de anuncios de linkedIn?**

No, no empezaremos a descargarlo automáticamente para todos los clientes, pero es un conmutador muy sencillo para habilitar esta función en la configuración.

**¿Están disponibles los datos de formulario?**

Los datos de formulario están disponibles mediante [!DNL Marketo Measure] Discover incluye el ID de formulario y el nombre del formulario. Los detalles del formulario aún no están disponibles en los objetos touchpoint de CRM.

**Qué pasa con cualquier [!DNL LinkedIn] posibles clientes que se hayan sincronizado anteriormente con programas de Marketo o campañas de CRM?**

Se recomienda ajustar cualquier [!DNL Marketo Measure] reglas para generar puntos de contacto a partir de programas o campañas específicos para evitar duplicaciones. La API de LinkedIn tiene una limitación retrospectiva de 90 días, por lo que si utiliza reglas de Marketo o CRM, se recomienda establecer la fecha de finalización de la regla en 90 días antes de la fecha en la que habilitó la integración en [!DNL Marketo Measure]. A partir de este punto, [!DNL Marketo Measure] puede descargar esos posibles clientes con buenos detalles y datos.

**¿Se incluye etiquetado o seguimiento automático?**

No, esto es diferente a otro [!DNL Marketo Measure] integraciones. En lugar de modificar la página de aterrizaje (ya que no hay ningún clic en la página de aterrizaje), solo descargamos la información relevante de LinkedIn y la tratamos como actividades dentro de [!DNL Marketo Measure].
