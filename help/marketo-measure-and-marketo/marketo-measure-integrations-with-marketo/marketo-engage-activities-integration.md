---
unique-page-id: 42762749
description: Integración de actividades de [!DNL Marketo Engage] - [!DNL Marketo Measure]
title: Integración de actividades de [!DNL Marketo Engage]
exl-id: 463ad9b2-e1bd-49dd-8bf5-0da7b7132f05
feature: Integration
source-git-commit: de366de2d1df3d4dc9fc33e5fd0dab225b6af081
workflow-type: tm+mt
source-wordcount: '1660'
ht-degree: 1%

---

# Integración de actividades de [!DNL Marketo Engage] {#marketo-engage-activities-integration}

Como parte de la integración general de [!DNL Marketo Measure] y [!DNL Marketo Engage], este esfuerzo por extraer las actividades de Marketo desempeña un papel fundamental. A través de las actividades de Marketo, el sistema rastrea eventos como `Click Email`, `Change Score` o `Change Status in Progression`; estos tipos de actividades se pueden reducir y definir para seleccionar un subconjunto apto para los puntos de contacto. Una vez creados los puntos de contacto de estas actividades, se rastrean en el recorrido de participación y se miden junto con otros canales de marketing, como la búsqueda de pago o el marketing de socio.

## Requisitos {#requirements}

* Instancia de Production Marketo
* Instancia de producción [!DNL Salesforce] o [!DNL Microsoft Dynamics]
* Cualquier suscripción pagada de [!DNL Marketo Measure]
* Sincronización de personas de Marketo habilitada (configuración de [!DNL Marketo Measure])
* Programas de Marketo habilitados (configuración de [!DNL Marketo Measure])
* Actividades de Marketo habilitadas (configuración de [!DNL Marketo Measure])

## Instalación {#setup}

1. Para comenzar a configurar actividades de Marketo, vaya a **Mi cuenta** > **Configuración** > **Actividades**.

   ![](assets/one-1.png)

   ![](assets/two-1.png)

   Lo primero que debe hacer es seleccionar la lista de tipos de actividades en los que planea crear reglas. No se requiere un número elevado de tipos de actividades, pero se recomienda que no sobrecargue los puntos de contacto y diluya la importancia de los hitos significativos. Dicho esto, es posible que no necesite más de cinco tipos de actividades para rastrear las participaciones relevantes.

1. Haga clic en el menú desplegable debajo de [!UICONTROL Seleccionar tipos de actividades] para comenzar a elegir los distintos tipos.

   ![](assets/three-1.png)

1. Cuando haya seleccionado todas las actividades que necesita, podrá verlas rellenadas en su [!UICONTROL Lista de actividades seleccionadas] y en [!UICONTROL Definir reglas].

   ![](assets/four-1.png)

1. Para cada tipo de actividad, debe definir una o más reglas que determinen qué registros cumplen los requisitos para los puntos de contacto. En este ejemplo, agregamos una regla para el tipo de actividad &quot;Cambiar puntuación&quot; para que el sistema cree un punto de contacto cuando una persona de Marketo alcance una puntuación de 90 o superior.

1. En primer lugar, según el tipo de actividad, es posible que tenga que configurar un [!DNL Marketo Measure] Nombre de campaña que se pueda usar más adelante para la asignación de canales. Los nombres de campaña [!DNL Marketo Measure] se pueden reutilizar en varias reglas. Esto ayuda a tener nombres más amplios que se pueden utilizar en una sola regla de canal. No todos los tipos de actividades contienen un programa de Marketo, por lo que es necesario especificar un nombre como primer paso.

   A continuación se muestra un ejemplo del aspecto que tendría ese paso adicional:

   ![](assets/five-1.png)

1. En el ejemplo &quot;Cambiar puntuación&quot;, es necesario introducir un Nombre de campaña, ya que esa información se extrae del Programa de Marketo. Ahora cree la expresión de regla. Siguiendo este ejemplo, seleccione el campo &quot;[!UICONTROL Nuevo valor]&quot; con un operador de &quot;[!UICONTROL es mayor que]&quot; con un valor de 90.

   Puede ampliar las reglas y agregar filtros o criterios adicionales agregando instrucciones &quot;and&quot; u &quot;or&quot; para reducir los resultados.

   ![](assets/six-1.png)

   ![](assets/seven-1.png)

1. Por último, elija qué utilizar como fecha de punto de contacto. Todos los campos de fecha y hora disponibles aparecen aquí desde Marketo. A menos que tenga campos de fecha personalizados, verá &quot;[!UICONTROL Fecha de actividad]&quot;.

   ![](assets/eight-1.png)

1. Asegúrese de hacer clic en **[!UICONTROL Guardar como borrador]** durante el recorrido para no perder los cambios.

   ![](assets/nine-1.png)

1. Vaya a la pestaña **[!UICONTROL Asignación de atributos]**.

   ![](assets/ten-1.png)

1. Para cada tipo de actividad que seleccionó, tiene la opción de asignar atributos de Marketo adicionales a los campos de Touchpoint para poder ver y crear informes de esos valores en [!DNL Marketo Measure Discover] o en CRM.

   Muchos de los campos se han asignado automáticamente y no se pueden cambiar para que sean coherentes con el resto de las integraciones. Consulte la sección Asignaciones de campos a continuación para encontrar esos valores. Para algunos tipos de actividad, Marketo incluye atributos para una página de aterrizaje, una página de referencia o un explorador que se puede asignar de forma opcional a un campo de Touchpoint. En el ejemplo siguiente, hemos hecho algunas sugerencias adicionales que se pueden eliminar.

1. Seleccione el campo Buyer Touchpoint de la columna izquierda al que desee asignar. A continuación, elija el atributo de Marketo que desea rellenar en el campo Buyer Touchpoint. Recuerde que estas son asignaciones adicionales opcionales además de las que [!DNL Marketo Measure] ya ha establecido.

   Campos asignables:

   * Ciudad
   * País
   * Región
   * Página de aterrizaje
   * Página del referenciador
   * Página de formulario
   * Fecha de formulario
   * Plataforma
   * Explorador

   >[!NOTE]
   >
   >Los campos de publicidad como Contenido de publicidad o Palabra clave no están disponibles en esta lista, ya que se reservan para las integraciones de nuestra plataforma de publicidad.

## Tipos de actividad {#activity-types}

Algunos tipos de actividades nos proporcionan el ID y el nombre del programa, por lo que es fácil asignarlos al ID y al nombre de la campaña en Buyer Touchpoint. Para otros, no hay ninguna asociación de programa, por lo que parte de la definición de reglas requiere que cree un Nombre de campaña de [!DNL Marketo Measure]. A continuación se muestran listas de cada categoría:

**Tipos de actividades con Id. de programa**

Enviar correo electrónico (6)\
Correo electrónico enviado (7)\
Correo electrónico rechazado (8)\
Correo electrónico de cancelación de suscripción (9)\
Abrir correo electrónico (10)\
Haga clic en Correo electrónico (11)\
Cambiar valor de datos (13)\
Puntuación de cambio (22)\
Añadir a la lista (24)\
Cambiar estado en progresión (104)\
Añadir a Nutrir (113)\
Cambio de la cadencia de la nutrición (115)

>[!NOTE]
>
>De los tipos de actividades para los que se espera un id. de programa, si se detecta una actividad sin un programa, [!DNL Marketo Measure] no la aceptará como punto de contacto elegible, ya que no podemos tener valores de campaña nulos.

**Tipos de actividades sin Id. de programa**

Haga clic en Vínculo (3)\
Nuevo posible cliente (12)\
Cable de sincronización a SFDC (19)\
Convertir posible cliente (21)\
Cambiar propietario (23)\
Eliminar de la lista (25)\
Actividad de SFDC (26)\
Correo electrónico rechazado (27)\
Eliminar posible cliente de SFDC (29)\
Combinar posibles clientes (32)\
Agregar a oportunidad (34)\
Quitar de oportunidad (35)\
Oportunidad de actualización (36)\
Eliminar posible cliente (37)\
Enviar alerta (38)\
Enviar correo electrónico de ventas (39)\
Abrir correo electrónico de ventas (40)\
Haga clic en Correo electrónico de ventas (41)\
Añadir a SFDC Campaign (42)\
Eliminar de SFDC Campaign (43)\
Cambiar estado en SFDC Campaign (44)\
Correo electrónico de recepción de ventas (45)\
Campaña de solicitud (47)\
Correo electrónico de ventas devuelto (48)\
Cambiar etapa de ingresos (101)\
Cambiar etapa de ingresos manualmente (102)\
Cambiar segmento (108)\
Llamar a Webhook (110)\
Enviar Reenviar a un amigo Correo electrónico (111)\
Correo electrónico enviado a un amigo (112)\
Cambio de la pista de nutrición (114)\
Insertar posible cliente en Marketo (145)\
Sincronizar posible cliente con Microsoft (300)\
Compartir contenido (400)
Interacción con el diálogo (158)
Documento interactuado con (159)
Cita de diálogo programada (160)
Objetivo del diálogo alcanzado (161)
Actividad personalizada (xxx)

## Asignación de canales {#channel-mapping}

Para cualquiera de las reglas de un tipo de actividad con un ID de programa, el canal de programa de Marketo se determina a partir del programa. Utilizamos el canal de programa para asignarlo a sus canales sin conexión personalizados, por lo que debe asegurarse de que sus canales estén configurados correctamente [según se indica aquí](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping){target="_blank"}.

Y para cualquiera de las reglas de un tipo de actividad sin un ID de programa, el primer paso fue crear un nombre de campaña. Use este nombre de campaña para configurar sus canales en línea personalizados [aquí](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md){target="_blank"}.

Si los canales de sus actividades de Marketo no están correctamente configurados, es probable que sus nuevos puntos de contacto entren en el canal &quot;Otro&quot;.

## Costos de programa {#program-costs}

Mediante la importación de datos de los programas de Marketo, los costes se descargan automáticamente de los costes del periodo y los costes notificados en Marketo se distribuyen a lo largo del mes asignado. Por ejemplo, si se informa de 1000 $ para enero de 2021, los 1000 $ se dividen en 31 días. Los costos se pueden encontrar en [!DNL Marketo Measure Discover].

## Asignación de cookies {#cookie-mapping}

Como resultado de la integración de [!DNL Marketo Measure] con Marketo, el identificador de cookie [!DNL Marketo Measure] ahora también se asigna y sincroniza con [!DNL Marketo Munchkin Id]. Esto ayuda a cerrar la brecha para atribuir el primer contacto anónimo a una sesión web en lugar de atribuir los toques FTP y LC a una actividad de Marketo. Imagine este escenario:

Mark hace clic en un anuncio de Facebook y llega a wayneenterprises.com donde obtiene una cookie con [!DNL Marketo Measure] id. 123 y [!DNL Marketo Munchkin Id] 456. No se rellena ningún formulario.

El equipo de marketing de empresas de Wayne envía una notificación por correo electrónico a posibles clientes específicos, uno de los cuales es `mark@email.com`.

`mark@email.com` recibe el correo electrónico, hace clic y aterriza en `wayneenterprises.com`. Esto se convierte en `mark@email.com's` segunda visita a `wayneenterprise.com` con los mismos ID de cookie, pero no se rellenó el formulario, por lo que para [!DNL Marketo Measure], sigue siendo un visitante anónimo.

El equipo de marketing de empresas Wayne crea una regla de actividad de Marketo para generar puntos de contacto para un tipo de actividad de &quot;clic en correo electrónico&quot;.

La implementación de hoy crearía un único punto de contacto FT y LC para `mark@email.com` desde la actividad de Marketo a partir del tipo de actividad &quot;Hacer clic en el correo electrónico&quot;.

Con esta mejora de la asignación de cookies, el FTP regresaría y se acreditaría al anuncio de Facebook y la LC se acreditaría al correo electrónico.

>[!NOTE]
>
>Con el comportamiento de asignación de cookies, puede encontrar algunos puntos de contacto LC que provienen de una visita web. Es posible que un posible cliente apareciera en Marketo sin ninguna actividad asociada, que luego [!DNL Marketo Measure] descargara ese posible cliente, que coincidiera con las cookies asociadas y que luego lo rastreara hasta la sesión web más reciente, incluso si no había ninguna actividad de formulario que creara el posible cliente.

## Preguntas frecuentes {#faq}

**¿Cómo sé si crear una regla de programas de Marketo o una regla de actividades de Marketo?**

La integración de programas de [!DNL Marketo Engage] es una forma sencilla de generar puntos de contacto en función de si una persona es miembro de un programa. Si está interesado en definir una regla basada en el momento en que una persona cambia a un estado de programa determinado, la integración de actividades de [!DNL Marketo Engage] será la configuración que desee, específicamente el tipo de actividad &quot;Cambiar estado en progresión&quot; para que la fecha de punto de contacto se pueda asignar a la fecha de actividad generada por el sistema.

**¿Por qué se trunca el nombre de mi tipo de punto de contacto?**

El campo Tipo de punto de contacto se creó en el paquete [!DNL Marketo Measure] con 16 caracteres. Lamentablemente, cambiar el límite de caracteres del campo requeriría dejar obsoleto el campo existente y crear uno. El valor del Tipo de punto de contacto es el Tipo de actividad, que también se establece en el campo Medium.

**¿Por qué mi tipo de actividad personalizada no aparece en la lista de actividades disponibles?**

Solo se muestran los tipos de actividad personalizados &quot;Aprobado&quot; y no Borrador ni Aprobado con Borrador.

**¿Cómo puedo determinar para qué tipos de actividad deseo generar un punto de contacto?**

Aunque no hay límite en el número de tipos de actividades que puede crear, generalmente recomendamos no más de cinco tipos de actividades. Se tarda tiempo en determinar qué actividades de marketing son lo suficientemente relevantes como para formar parte del recorrido de puntos de contacto. Por ejemplo, puede que &quot;Cancelar la suscripción al correo electrónico&quot; no sea un punto de contacto significativo para rastrear, pero &quot;Hacer clic en el correo electrónico&quot; con filtros adicionales podría ser uno bueno. Esto varía según cada organización y cada equipo, por lo que le sugerimos que trabaje con su equipo para generar ideas sobre el mejor enfoque aquí.

**¿Por qué se ha cortado mi nombre de explorador?**

El nombre de explorador [!DNL Marketo Measure] tiene un límite estricto de 20 caracteres, aunque el valor de agente de usuario que obtenemos de Marketo tiende a ser una cadena más larga.

BrowserInfo.Name\
BrowserInfo.Version\
PlatformInfo.Name\
PlatformInfo.Version
