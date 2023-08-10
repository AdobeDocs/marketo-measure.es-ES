---
unique-page-id: 35586080
description: 'Integración de linkedIn: [!DNL Marketo Measure] - Documentación del producto'
title: Integración de linkedIn
exl-id: 705209ef-1ece-496c-ac2f-6a31055bd993
feature: APIs, Integration
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '2603'
ht-degree: 1%

---

# Integración de linkedIn {#linkedin-integration}

## Información general {#overview}

El [!DNL Marketo Measure] la integración con LinkedIn se divide en dos partes:

Contenido patrocinado: la integración de contenido patrocinado permite [!DNL Marketo Measure] para etiquetar direcciones URL de destino en [!DNL LinkedIn] anuncios, que en última instancia permite [!DNL Marketo Measure] para seguir a un usuario a través de todo el recorrido de puntos de contacto y asignar la actividad de nuevo a la actividad específica [!DNL LinkedIn] Campaign y Creative. Esto proporciona perspectivas a los clientes sobre el ROI de su [!DNL LinkedIn] actividad.

Forms de generación de clientes potenciales: a través de la integración con Forms de generación de clientes potenciales de LinkedIn, Marketo Measure obtiene un conocimiento detallado de los formularios que se han enviado a través de la plataforma LinkedIn. Estos formularios se comparan con los posibles clientes de su CRM o [!DNL Marketo Engage] para que sean aptos para la atribución. Con una perspectiva de la campaña, el creativo y el formulario que ayudó a generar los formularios, los equipos ahora pueden optimizar aún más su gasto en marketing y publicidad de LinkedIn.

## Disponibilidad {#availability}

Disponible para todos los clientes.

## Requisitos {#requirements}

**Funciones del administrador de campañas**

Para [!DNL Marketo Measure] para poder descargar los datos de anuncios y los datos de coste de anuncios, debe tener una de las siguientes funciones en el administrador de campañas:

* Administrador de facturación
* Administrador de cuentas
* Administrador de campañas

Más información: [Funciones y roles de usuario en el administrador de Campaign](https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager).

**Roles de administrador de medios pagados**

Para [!DNL Marketo Measure] para poder crear/actualizar elementos creativos patrocinados, debe tener una de las siguientes funciones de administrador de medios de pago:

* Afiche de contenido patrocinado
* Gerente principal de Forms

Más información: [Roles de administrador de página de linkedIn](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

Hay otros [!DNL LinkedIn] funciones que desempeñamos **no** para nuestra integración. Estas funciones a menudo se confunden con las funciones requeridas, por lo que tenga en cuenta que hay una diferencia.

**Roles de administrador de página**

Para [!DNL Marketo Measure] para poder descargar/integrar posibles clientes de los formularios de generación de posibles clientes, debe tener la siguiente función de administrador de página:

* Super Admin

Más información: [Roles de administrador de página de linkedIn](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

## Tipos de anuncios de linkedIn {#linkedin-ad-types}

[!DNL Marketo Measure] admitirá lo siguiente:

**Contenido patrocinado:** El contenido patrocinado le permite enviar contenido a [!DNL LinkedIn] fuente de miembros más allá de los que siguen a su compañía. El contenido patrocinado puede dirigirse a una audiencia específica y ayudar a los anunciantes a llegar a [!DNL LinkedIn] miembros siempre y cuando participen en el [!DNL LinkedIn] en equipos de escritorio, dispositivos móviles y tabletas. Se admite el contenido patrocinado con Forms de generación de posibles clientes.

Los tipos de contenido patrocinado y los formatos admitidos por [!DNL Marketo Measure] son anuncios de imagen única y anuncios de vídeo (a través de Forms de generación de clientes potenciales). Debido a la complejidad del esquema, no se admiten anuncios de carrusel.

[!DNL Marketo Measure] no admite mensajes patrocinados, anuncios de texto ni anuncios dinámicos.

![](assets/one.png)

>[!TIP]
>
>Para cualquiera de sus campañas/gastos que se originen a partir de una fuente de contenido no patrocinada (como el tipo de campaña &quot;Anuncio de texto&quot; o &quot;Correo electrónico patrocinado&quot;), [!DNL Marketo Measure] hace _no_ admiten de forma inherente el seguimiento de estos tipos de campaña. Si desea rastrear el gasto en campañas como esta junto con su gasto en &quot;contenido patrocinado&quot;, asegúrese de usar nuestro CSV de gasto en marketing para registrar manualmente dicho gasto.

## Cómo funciona: Contenido patrocinado {#how-it-works-sponsored-content}

>[!NOTE]
>
>Antes del primer uso, esta configuración de función debe habilitarse navegando a [!DNL Marketo Measure] [!UICONTROL Configuración] > [!UICONTROL Integraciones] > [!UICONTROL Anuncios] > [!UICONTROL Habilitar Forms de generación de clientes potenciales de LinkedIn].

**[!DNL LinkedIn's]Requisitos exclusivos de etiquetado automático**

[!DNL Marketo Measure] puede ayudarle a realizar el seguimiento de [!DNL LinkedIn] rendimiento de la campaña mediante el etiquetado automático de sus páginas de aterrizaje.

[!DNL Marketo Measure] buscará elementos creativos con un recurso compartido de LinkedIn único y agregará un `?_bl={creativeId}` al final del mismo.

**Copiar recursos compartidos**

Con esto [!DNL Marketo Measure/LinkedIn] Para la integración, pedimos a los clientes que no copien, clonen ni dupliquen elementos creativos existentes. Si se encuentran recursos compartidos y se detectan para que solo se utilicen en un creativo, [!DNL Marketo Measure] Puede etiquetar el recurso compartido tal cual sin tener que recrear ningún elemento creativo o compartido, y el historial de todos los anuncios (impresiones, clics, recursos compartidos) permanecerá.

Tan pronto como se encuentre un recurso compartido para compartirlo entre varios creativos, [!DNL Marketo Measure] tendrá que pasar por un proceso de pausa, copia y reetiquetado para crear un conjunto único. [!DNL Marketo Measure] hará una pausa y archivará los creativos en directo y, por lo tanto, borrará el Historial de anuncios, incluidas las impresiones, los clics y los recursos compartidos en medios sociales, para etiquetar todo automáticamente de forma adecuada.

En adelante, [!DNL Marketo Measure] recomienda que no duplique ningún [!DNL LinkedIn] Comparte y mantiene todos los creativos y recursos compartidos tan únicos como sea posible para que simplemente podamos añadir nuestro seguimiento sin tener que borrar el Historial de anuncios.

**URL abreviadas**

El motivo del paso adicional es que LinkedIn permite que las URL de destino sean una URL abreviada (bit.ly, goog.le, etc.,), lo que significa que [!DNL Marketo Measure] no ve la dirección URL larga y resuelta y [!DNL Marketo Measure] debe añadir parámetros de seguimiento a una dirección URL resuelta. Con el fin de evitar ese problema, [!DNL Marketo Measure] busca direcciones URL abreviadas antes de volver a crear un anuncio, expande la dirección URL y, a continuación, crea el nuevo anuncio con la dirección URL resuelta y todos sus parámetros, lo que permite [!DNL Marketo Measure] para añadir etiquetas. La creación de un nuevo anuncio borrará el historial de anuncios (impresiones, clics, usos compartidos), por lo que se necesita permiso para etiquetar direcciones URL abreviadas.

Si utiliza abundantemente direcciones URL abreviadas, esto podría afectar gravemente a sus elementos creativos. Le recomendamos que ya no utilice direcciones URL abreviadas para que [!DNL Marketo Measure] Puede etiquetar las páginas de aterrizaje sin tener que crear nuevos anuncios y borrar el Historial de anuncios.

**El proceso**

Empecemos con algunos ejemplos. Digamos que lo hemos hecho....

Creative A: Compartir 123\
Creative B: Compartir 234\
Creative C : Compartir 234\
Creative ID : Compartir 234

![](assets/two.png)

`1)` [!DNL Marketo Measure] buscará primero en todas las campañas, elementos creativos y recursos compartidos con el estado Activo. [!DNL Marketo Measure] no etiquetará anuncios en pausa, archivados o cancelados. Si un anuncio se pausó, se establece en [!UICONTROL activo], lo etiquetaremos una vez que esté activo de nuevo. Si podemos encontrar un recurso compartido único, lo que significa que no se utiliza en varios elementos creativos o campañas (por ejemplo, Creative A : recurso compartido 123), [!DNL Marketo Measure] agregará nuestro parámetro personalizado `>> ?_bl={creativeId}` a la URL compartida.

`2)` Ahora, si la acción se ha compartido y ha perdido su exclusividad (por ejemplo, Creative B : Compartir 234 y Creative C : Compartir 234 y Creative D : Compartir 234), [!DNL Marketo Measure] hará una pausa y archivará todos los creativos similares (que serían Creative B, Creative C y Creative D).

`3)` [!DNL Marketo Measure] Creará 3 nuevos creativos, Creative E, Creative F y Creative G, que copiarán el contenido de Creative B, que se archivará.

`4)` [!DNL Marketo Measure] también creará 3 nuevos recursos compartidos, Compartir 345, Compartir 456 y Compartir 567, que copian el contenido de Compartir 234, excepto que tendrá su propio contenido único `?_bl` etiquetado.

`5)` [!DNL Marketo Measure] Tendrá que comprobar regularmente que las acciones no se comparten y, si lo hacen, reiniciaremos el proceso en el paso 2 anterior.

>[!NOTE]
>
>La implementación de esto significará que nuestros clientes perderán el historial de anuncios de Creative B : Share 234, Creative C : Share 234 y Creative D : Share 234 porque ahora se vuelve a crear con Creative E : Share 345, Share F : Share 456 y Creative G : Share 567 respectivamente.

![](assets/three.png)

## Cómo funciona: Forms de generación de clientes potenciales {#how-it-works-lead-gen-forms}

**El proceso**

Pasante [!DNL LinkedIn's] La API de formularios de publicidad y la API de respuesta de formularios de publicidad permiten recopilar datos de envío de formularios para una cuenta de publicidad y asociar la dirección de correo electrónico a un posible cliente de CRM o Marketo.

Los formularios linkedIn pueden contener varias direcciones de correo electrónico. Cuando descarguemos respuestas de formulario, buscaremos direcciones de correo electrónico con la siguiente prioridad: Correo electrónico de trabajo, Dirección de correo electrónico (campo de formulario principal) o campos personalizados con un valor de correo electrónico válido.

Independientemente del estado de Campaña o Creativo, todas las respuestas del formulario resultarán en un punto de contacto. [!DNL Marketo Measure] tiene una restricción retrospectiva de 90 días, por lo que [!DNL Marketo Measure] no puede acceder a las respuestas del formulario anteriores a 90 días, pero durante más tiempo [!DNL Marketo Measure] y [!DNL LinkedIn] Cuando la integración de con esté habilitada, los puntos de contacto del formulario de generación de clientes potenciales serán visibles a través de [!DNL Marketo Measure].

>[!NOTE]
>
>Los costes de linkedIn se siguen descargando como parte de las campañas de contenido patrocinado.

**Seguimiento de Lead Gen Forms en CRM o Marketo**

Antes de [!DNL Marketo Measure] y existía la integración de Forms de LinkedIn Lead Gen, la práctica común era que los clientes insertaran sus envíos de formularios a un programa de Marketo o a una campaña de CRM para realizar un seguimiento de los formularios y recibir la atribución en esas actividades. Una vez habilitada la configuración de Forms de generación de posibles clientes, queremos asegurarnos de que los envíos de formularios no se cuenten dos veces. Compruebe lo siguiente:

* El campo &quot;Habilitar puntos de contacto del comprador&quot; en el objeto CRM está establecido en &quot;Ninguno&quot; o &quot;Excluir todos los miembros de la campaña&quot;
* Actualizar cualquier programa de Marketo relacionado o reglas de actividad de Marketo
* Actualizar cualquier regla de CRM Campaign relacionada

>[!NOTE]
>
>La API de LinkedIn tiene una limitación retrospectiva de 90 días, por lo que si utiliza reglas de Marketo o CRM, se recomienda establecer la fecha de finalización de la regla en 90 días antes de la fecha en la que habilitó la integración en [!DNL Marketo Measure].

## Detalles del Touchpoint {#touchpoint-details}

Una [!DNL Marketo Measure] ha etiquetado correctamente su página de aterrizaje en LinkedIn creative, podrá ver los datos de anuncios resueltos en el punto de contacto. Esta es la asignación de valores de datos que debería ver:

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>Campo Touchpoint</th> 
   <th>Valor de muestra</th> 
  </tr> 
  <tr> 
   <td><p>ID de anuncio </p></td> 
   <td><p>84186224 </p></td> 
  </tr> 
  <tr> 
   <td><p>Contenido de anuncios </p></td> 
   <td><p>copy-1-image-2-man El 95 % de los especialistas en marketing #B2B consideran que la estrategia de creación de demanda es exitosa. Más información: [!DNL https]://lnkd.in/jgdi50vKrgv</p></td> 
  </tr> 
  <tr> 
   <td><p>ID de grupo de publicidad </p></td> 
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
   <td><p>Nombre de campaña de anuncios </p></td> 
   <td><p>SU - Cuentas COM - Capacidades de demanda </p></td> 
  </tr> 
  <tr> 
   <td><p>URL de destino del anuncio </p></td> 
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
   <td><p>ID de palabra clave </p></td> 
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
   <td><p>Social de pago.LinkedIn </p></td> 
  </tr> 
  <tr> 
   <td><p>Medio </p></td> 
   <td><p>"cpc" o "Formulario de generación de clientes potenciales"</p></td> 
  </tr> 
  <tr> 
   <td><p>Página del referenciador </p></td> 
   <td><p>www.linkedin.com/ </p></td> 
  </tr> 
  <tr> 
   <td><p>Página de referente: sin procesar </p></td> 
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
   <td><p>Origen del punto de contacto </p></td> 
   <td><p>LinkedIn </p></td> 
  </tr> 
 </tbody> 
</table>

## Costos {#costs}

Porque [!DNL Marketo Measure] tiene una integración directa con [!DNL LinkedIn], descargamos el gasto registrado para cada campaña y creativo cada día. No es necesario que un cliente informe de [!DNL LinkedIn] gastar en el [!DNL Marketo Measure] ya no es necesario.

Al igual que con otras integraciones de publicidad, [!DNL Marketo Measure] ha definido una regla de canal de marketing para colocar todo [!DNL LinkedIn] campañas, elementos creativos y costes. Para utilizar la regla, el cliente querrá insertar una nueva fila para su [!DNL LinkedIn] esfuerzos. Puede ser un canal nuevo o existente. En la columna Referente, utilice la definición &quot;[[!DNL LinkedIn] Pagado]&quot; que [!DNL Marketo Measure] se ha definido como cualquier punto de contacto con un [!DNL Marketo Measure] etiqueta.

![](assets/four.png)

## [!DNL Marketo Measure] Discover {#marketo-measure-discover}

Se han realizado algunas mejoras en [!DNL Marketo Measure] Descubra para admitir informes de Forms de generación de clientes potenciales.

**Tablero de medios de pago**

Mosaico Forms de generación de posibles clientes: nuevo mosaico que incluye el recuento de los rellenos de formulario de LinkedIn. La obtención de detalles de este recuento mostrará el ID de actividad, la fecha del formulario, el nombre del formulario y la dirección de correo electrónico.

**Tablero de ruta de participación**

Recorrido de eventos: incluye el tipo de evento &quot;Actividad&quot; y el medio &quot;Formulario de generación de posibles clientes&quot; para los formularios que se incluyen en la integración. La vista de obtención de detalles incluye Detalles de Campaign, Creative y Form.

## Preguntas frecuentes sobre contenido patrocinado {#sponsored-content-faq}

**¿Qué es un recurso compartido oscuro?**

Un recurso compartido oscuro es una publicación en la que nunca se publica en la página de la compañía y se crea inmediatamente y se añade directamente como creativo. Para que [!DNL Marketo Measure]Los creativos creados por él no aparecen en la parte superior de la página de una empresa y vuelven a ser promocionados, se utilizan acciones oscuras para que puedan lanzarse entre bastidores.

**Qué hace Statuses [!DNL Marketo Measure] ¿realmente etiqueta?**

Hay cuatro estados diferentes en una [!DNL LinkedIn] Campaign y Creative: Activo, pausado, archivado y cancelado. Solo etiquetamos las campañas y los elementos creativos que están activos. Al etiquetar otros estados, se vuelven a establecer como Activos. [!DNL Marketo Measure] no etiquetará campañas o creativos en pausa, archivados o cancelados, pero reanudará el etiquetado si el estado cambia a Activo.

**¿Cuál es el valor de [!DNL Marketo Measure] ¿está usando para etiquetar?**

Al final de la dirección URL de destino, [!DNL Marketo Measure] está agregando el parámetro `&_bl={creativeId}`, donde la variable `{creativeId}` es el ID creativo de LinkedIn. Con el ID de creativo, [!DNL Marketo Measure] también puede determinar el ID de campaña porque [!DNL LinkedIn] tiene una estructura de anuncios bastante básica, ya que cada creativo solo puede pertenecer a una campaña.

**¿Qué pasa con mi antiguo creativo? [!DNL Marketo Measure] ¿crea una nueva versión de él?**

Cuándo [!DNL Marketo Measure] vuelve a crear un recurso compartido y lo coloca en un nuevo creativo, el antiguo creativo se archiva. Por eso también [!DNL Marketo Measure] no etiquetará campañas archivadas o creativos; de lo contrario, se enlazaría con [!DNL Marketo Measure] intentando etiquetarlo indefinidamente.

**¿Por qué la dirección URL de destino del anuncio creado no coincide con mi anuncio original?**

[!DNL Marketo Measure] debe añadir los parámetros de seguimiento a una dirección URL resuelta, pero la URL presentada en la API puede ser potencialmente una URL abreviada sin todos los parámetros presentes. Con el fin de evitar ese problema, [!DNL Marketo Measure] busca direcciones URL abreviadas antes de volver a crear una adición, la resuelve y, a continuación, crea la nueva publicidad con la dirección URL resuelta y todos sus parámetros, lo que permite [!DNL Marketo Measure] para añadir etiquetas.

**¿Estás etiquetando todos mis anuncios? ¿No veo el parámetro bl en todas las páginas de aterrizaje?**

Hemos observado que algunos especialistas en marketing colocan un vínculo de imagen en la dirección URL de destino, que [!DNL Marketo Measure] no se puede etiquetar, por lo que se busca la URL dentro del contenido del anuncio. If [!DNL Marketo Measure] tiene permisos para etiquetar direcciones URL abreviadas, ampliaremos la dirección URL y la etiquetaremos, pero debido a la estructura de copia de LinkedIn, se acorta automáticamente dentro del texto. La etiqueta se encuentra dentro de la URL abreviada de LinkedIn, que aparece en el campo Contenido de publicidad del punto de contacto en lugar de en el campo Página de aterrizaje: sin procesar.

**Oh no, alguien de mi equipo accidentalmente clonó una parte. ¿Puedo pausarlo?**

No te preocupes. [!DNL Marketo Measure] comprobará mediante programación si hay recursos compartidos que ya no son únicos, lo que significa que se han copiado en un Creative diferente. Una vez detectada esa copia, [!DNL Marketo Measure] seguirá el flujo habitual para etiquetar y crear anuncios nuevos.

**Mi anuncio estaba pendiente de revisión anteriormente. ¿Por qué está pendiente de revisión nuevamente después de [!DNL Marketo Measure] ¿Lo etiquetaste?**

LinkedIn requiere que todos los anuncios que se crean o modifican sigan el proceso de seguridad normal antes de publicarse. [!DNL Marketo Measure] intenta interceptar el anuncio lo más rápido posible, ya que busca nuevos anuncios cada 6 horas, pero con [!DNL LinkedIn's] Este paso adicional puede retrasar el inicio unas horas.

**Hay 2 URL en mi anuncio. ¿A cuál le etiquetan?**

Ambos. El [!DNL Marketo Measure] La integración de permite etiquetar la dirección URL de destino desde la imagen de pulsación en el anuncio, pero también actualiza automáticamente la dirección URL abreviada en la descripción del anuncio.

![](assets/five.png)

**He conectado mi [!DNL LinkedIn ads] cuenta. ¿Por qué no [!DNL Marketo Measure] ¿está etiquetando mis vínculos?**

Los conectados [!DNL LinkedIn] El usuario debe tener el acceso de edición adecuado, lo que significa que debe ser un administrador de cuentas, un administrador de campañas o un administrador creativo.

**¿Cómo sé si mi creativo se copiará? ¿Puedo ver si mis creativos están usando el mismo recurso compartido?**

No se ha proporcionado el ID compartido en un [!DNL LinkedIn] , por lo que no hay una manera clara y obvia de comprobar las asignaciones de elementos creativos para compartir. Si sospecha que un elemento creativo puede ser una copia, puede comprobarlo manualmente abriendo el anuncio desde su [!DNL LinkedIn] Administrador de campañas: se abre el anuncio en una nueva pestaña y se encuentra el ID compartido en la dirección URL.

![](assets/six.png)

## Preguntas frecuentes sobre Lead Gen Forms {#lead-gen-forms-faq}

**¿Cuál es el coste de esta mejora?**

Esta oferta se incluye con cualquier pago [!DNL Marketo Measure] suscripción.

**¿La integración es retroactiva?**

Sí, descargaremos respuestas de formularios y anuncios históricos de LinkedIn, aunque nos limitaremos a la ventana retrospectiva de 90 días. Cuanto más largo sea el [!DNL Marketo Measure] Cuando la integración de LinkedIn esté habilitada, los puntos de contacto del formulario de generación de clientes potenciales serán visibles a través de [!DNL Marketo Measure].

No hay ninguna opción para establecer una fecha específica para la descarga, pero puede establecer de forma opcional las reglas de eliminación de puntos de contacto si hay puntos de contacto que necesite suprimir.

**¿Se activará automáticamente si ya estoy utilizando el [!DNL Marketo Measure] ¿Integración de anuncios de linkedIn?**

No, no empezaremos a descargarla automáticamente para todos los clientes, pero es muy sencillo activar esta función en los ajustes.

**¿Están disponibles los datos del formulario?**

Los datos de formulario están disponibles mediante [!DNL Marketo Measure] Descubra cómo se incluyen el ID y el nombre del formulario. Los detalles del formulario aún no están disponibles en los objetos de punto de contacto en CRM.

**¿Qué le pasa a cualquiera? [!DNL LinkedIn] ¿Los posibles clientes que se han sincronizado anteriormente con programas de Marketo o campañas CRM?**

Se recomienda ajustar cualquier [!DNL Marketo Measure] reglas para generar puntos de contacto a partir de esos programas o campañas específicos para evitar duplicaciones. La API de LinkedIn tiene una limitación retrospectiva de 90 días, por lo que si utiliza reglas de Marketo o CRM, se recomienda establecer la fecha de finalización de la regla en 90 días antes de la fecha en la que habilitó la integración en [!DNL Marketo Measure]. A partir de este momento, [!DNL Marketo Measure] Puede descargar estos posibles clientes para usted con buenos conocimientos y detalles.

**¿Hay algún etiquetado automático o seguimiento relacionado?**

No, esto es diferente de otros [!DNL Marketo Measure] integraciones. En lugar de modificar la página de aterrizaje (ya que no hay ningún clic en esta página), solo descargamos la información relevante de LinkedIn y la tratamos como actividades dentro de [!DNL Marketo Measure].
