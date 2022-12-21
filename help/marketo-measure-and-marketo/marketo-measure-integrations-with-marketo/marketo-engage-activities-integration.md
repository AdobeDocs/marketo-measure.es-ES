---
unique-page-id: 42762749
description: "[!DNL Marketo Engage] Integración de actividades - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Engage] Integración de actividades"
exl-id: 463ad9b2-e1bd-49dd-8bf5-0da7b7132f05
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '1628'
ht-degree: 0%

---

# [!DNL Marketo Engage] Integración de actividades {#marketo-engage-activities-integration}

Como parte del [!DNL Marketo Measure] y [!DNL Marketo Engage] Integración, este esfuerzo para incorporar las actividades de Marketo juega un papel importante. A través de las actividades de Marketo, el sistema rastrea eventos como Click Email, Change Score o Change Status in Progression (Correo electrónico de clic, puntuación de cambio o estado de cambio en progresión). Estos tipos de actividades se pueden reducir y definir para seleccionar un subconjunto que sea apto para puntos de contacto. Una vez creados los puntos de contacto en estas actividades, se los rastrea en el recorrido de participación y se miden junto con otros canales de marketing, como Búsqueda paga o Marketing de socios.

## Requisitos {#requirements}

* Instancia de Marketo de producción
* Producción [!DNL Salesforce] o [!DNL Microsoft Dynamics] instancia
* Cualquier pago [!DNL Marketo Measure] suscripción
* Sincronización de personas de Marketo habilitada ([!DNL Marketo Measure] Configuración)
* Programas de Marketo habilitados ([!DNL Marketo Measure] Configuración)
* Actividades de Marketo habilitadas ([!DNL Marketo Measure] Configuración)

## Instalación {#setup}

1. Para empezar a configurar actividades de Marketo, vaya a **Mi cuenta** > **Configuración** > **Actividades**.

   ![](assets/one-1.png)

   ![](assets/two-1.png)

   Lo primero que se necesita es seleccionar la lista de tipos de actividades en la que planea crear reglas. No se requiere un número estricto de tipos de actividades, pero también recomendamos que no sobrecargue sus puntos de contacto y diluya la importancia de hitos significativos. Dicho esto, es posible que no necesite más de 5 tipos de actividades para realizar el seguimiento de las participaciones relevantes.

1. Haga clic en el menú desplegable en [!UICONTROL Seleccionar tipos de actividades] para empezar a elegir los distintos tipos.

   ![](assets/three-1.png)

1. Una vez seleccionadas todas las actividades que necesita, también las verá rellenadas en su [!UICONTROL Lista de actividades seleccionadas] y en [!UICONTROL Definir reglas].

   ![](assets/four-1.png)

1. Para cada tipo de actividad, debe definir una o más reglas que determinen qué registros son aptos para puntos de contacto. Para nuestro ejemplo, agregaremos una regla para el tipo de actividad &quot;Cambiar puntuación&quot; para que el sistema cree un punto de contacto cuando una persona de Marketo alcance una puntuación de 90 o buenos.

1. En primer lugar, según el tipo de actividad, es posible que tenga que configurar un [!DNL Marketo Measure] Nombre de campaña que se puede usar más adelante para la asignación de canales. [!DNL Marketo Measure] Los nombres de campaña se pueden reutilizar en varias reglas. Esto ayuda a tener nombres más amplios que se pueden usar en una regla de canal único. No todos los tipos de actividades contienen un programa de Marketo, por lo que es necesario un nombre como primer paso.

   Este es un ejemplo de cómo sería ese paso adicional:

   ![](assets/five-1.png)

1. En nuestro ejemplo &quot;Change Score&quot; (puntuación de cambio), no necesitamos introducir un Campaign Name (Nombre de campaña), ya que podemos extraer esa información del programa Marketo. Ahora puede crear la expresión de regla. Siguiendo nuestro ejemplo, queremos seleccionar el campo &quot;[!UICONTROL Nuevo valor]&quot; con un operador de &quot;[!UICONTROL es bueno que]&quot; con un valor de 90.

   Puede ampliar las reglas y agregar filtros o criterios adicionales agregando instrucciones &quot;y&quot; o &quot;o&quot; para reducir los resultados.

   ![](assets/six-1.png)

   ![](assets/seven-1.png)

1. Por último, elija lo que deberíamos usar como Fecha de punto de contacto. Todos los campos de fecha y hora disponibles aparecerán aquí desde Marketo. A menos que tenga campos de fecha personalizados, verá &quot;[!UICONTROL Fecha de actividad].&quot;

   ![](assets/eight-1.png)

1. Asegúrese de hacer clic en **[!UICONTROL Guardar como borrador]** en el camino para que no pierdas tus cambios.

   ![](assets/nine-1.png)

1. Vaya a la **[!UICONTROL Asignación de atributos]** pestaña .

   ![](assets/ten-1.png)

1. Para cada tipo de actividad que haya seleccionado, tiene la opción de asignar atributos de Marketo adicionales a los campos de Touchpoint para que pueda ver e informar de esos valores en [!DNL Marketo Measure Discover] o en CRM.

   Muchos de los campos se han asignado automáticamente y no se pueden cambiar para ser coherentes con las otras integraciones. Consulte la sección Asignaciones de campos que aparece a continuación para encontrar esos valores. Para algunos tipos de actividades, Marketo incluye atributos para una página de aterrizaje, una página de referente o un explorador que se pueden asignar opcionalmente a un campo de Touchpoint. En el siguiente ejemplo, se han realizado algunas sugerencias adicionales que se pueden eliminar.

1. Seleccione el campo Punto de contacto del comprador en la columna izquierda a la que desee asignar. A continuación, elija el atributo de Marketo que desea rellenar en el campo Punto de contacto del comprador . Recuerde que se trata de una asignación opcional adicional sobre las que [!DNL Marketo Measure] ya se ha establecido.

   Campos Asignables:

   * Ciudad
   * País
   * Región
   * Página de aterrizaje
   * Página del referenciador
   * Página de formulario
   * Fecha de formulario
   * Plataforma
   * Navegador

   >[!NOTE]
   >
   >Los campos de publicidad, como Contenido del anuncio o Palabra clave, no están disponibles en esta lista, ya que están reservados para las integraciones de nuestra plataforma de publicidad.

## Tipos de actividades {#activity-types}

Algunos tipos de actividades nos proporcionan el ID de programa y el Nombre del programa, por lo que es fácil asignarlos al ID de campaña y al Nombre de campaña en el punto de contacto del comprador. Para otros, no hay ninguna asociación de programas, por lo que parte de la definición de reglas requiere que cree un [!DNL Marketo Measure] Nombre de campaña. A continuación se muestran las listas de cada categoría:

**Tipos de actividades con ID de programa**

Enviar correo electrónico (6)\
Correo electrónico enviado (7)\
Correo electrónico rechazado (8)\
Cancelar suscripción de correo electrónico (9)\
Abrir correo electrónico (10)\
Haga clic en Correo electrónico (11)\
Cambiar valor de datos (13)\
Puntuación de cambio (22)\
Agregar a la lista (24)\
Estado de cambio en progresión (104)\
Agregar a la fuente (113)\
Cambiar la cadencia de la imagen (115)

>[!NOTE]
>
>De los tipos de actividad en los que se espera un ID de programa, si se detecta una actividad sin un programa, [!DNL Marketo Measure] no lo aceptará como punto de contacto apto, ya que no podemos tener valores de Campaign nulos.

**Tipos de actividades sin ID de programa**

Haga clic en Vínculo (3)\
Nuevo posible cliente (12)\
Sincronización de posibles clientes con SFDC (19)\
Convertir posible cliente (21)\
Cambiar propietario (23)\
Quitar de la lista (25)\
Actividad de SFDC (26)\
Correo electrónico rechazado blando (27)\
Eliminar posible cliente de SFDC (29)\
Fusión de posibles clientes (32)\
Agregar a oportunidad (34)\
Eliminar de oportunidad (35)\
Actualizar oportunidad (36)\
Eliminar posible cliente (37)\
Enviar alerta (38)\
Enviar correo electrónico de ventas (39)\
Abrir correo electrónico de ventas (40)\
Haga clic en Correo electrónico de ventas (41)\
Añadir a la campaña SFDC (42)\
Eliminar de la campaña SFDC (43)\
Cambio de estado en la campaña SFDC (44)\
Recibir correo electrónico de ventas (45)\
Campaña de solicitud (47)\
Correo electrónico de ventas rechazado (48)\
Etapa de cambio de ingresos (101)\
Cambio manual del escenario de ingresos (102)\
Cambiar segmento (108)\
Llamar a Weblock (110)\
Enviar correo electrónico de reenvío a amigo (111)\
Correo electrónico de reenvío a amigo recibido (112)\
Pista de cambio de imagen (114)\
Insertar posible cliente en Marketo (145)\
Sincronización de posibles clientes con Microsoft (300)\
Diálogo Compartir Contenido (400) Comprometido (158) Documento Interactuado Con (159) Nombramiento De Diálogo Programado (160) Objetivo De Diálogo Alcanzado (161) Actividad Personalizada (xxx)

## Asignación de canales {#channel-mapping}

Para cualquiera de las reglas de un tipo de actividad con un ID de programa, el canal de programa de Marketo se determina a partir del programa. Utilizamos el canal de programa para asignarlo a sus canales sin conexión personalizados, por lo que tendrá que asegurarse de que los canales estén correctamente configurados [tal como se indica aquí](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping).

Y para cualquiera de las reglas de un tipo de actividad sin ID de programa, el primer paso era crear un nombre de campaña. Utilice este nombre de campaña para configurar los canales en línea personalizados [aquí](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

Si los canales de las actividades de Marketo no están correctamente configurados, es probable que los nuevos puntos de contacto estén en el canal &quot;Otros&quot;.

## Costes del programa {#program-costs}

A través de la importación de datos de Marketo Programs, los costes se descargan automáticamente de Period Costs y el coste registrado en Marketo se distribuye a lo largo del mes asignado. Por ejemplo, si se informa de 1000 dólares para enero de 2021, los 1000 dólares se dividen en 31 días. Los costes se encuentran en [!DNL Marketo Measure Discover].

## Asignación de cookies {#cookie-mapping}

Como resultado de [!DNL Marketo Measure] integración con Marketo, la variable [!DNL Marketo Measure] El ID de cookie ahora también se asigna y sincroniza con la variable [!DNL Marketo Munchkin Id]. Esto ayuda a cerrar el espacio para atribuir el primer contacto anónimo a una sesión web en lugar de atribuir los toques de FT y LC a una actividad de Marketo. Imagine este escenario:

Mark hace clic en un anuncio de Facebook y aterriza en wayneenterprise.com donde se le olvida [!DNL Marketo Measure] Id. 123 y [!DNL Marketo Munchkin Id] 456. No se rellena el formulario.

El equipo de Marketing de Wayne Enterprise envía una descarga de correo electrónico a posibles clientes específicos, uno de los cuales es `mark@email.com`.

`mark@email.com` recibe el correo electrónico y hace clic en y aterriza en `wayneenterprises.com`. Esto se convierte en `mark@email.com's` segunda visita a `wayneenterprise.com` con los mismos ID de cookie, pero no había ningún rellenado de formulario, por lo que se debe [!DNL Marketo Measure], siguen siendo visitantes anónimos.

El equipo de marketing de Wayne Enterprise crea una regla de actividad de Marketo para generar puntos de contacto para un tipo de actividad &quot;Haga clic en Correo electrónico&quot;.

La implementación actual crearía un único punto de contacto de FT y LC para `mark@email.com` desde la actividad de Marketo desde el tipo de actividad &quot;Haga clic en Correo electrónico&quot;.

Con esta mejora de la asignación de cookies, FT regresaría y se acreditaría a la publicidad de Facebook y la LC se acreditaría al correo electrónico.

>[!NOTE]
>
>Con el comportamiento de asignación de cookies, puede encontrar algunos puntos de contacto LC que provienen de una visita web. Es posible que un posible cliente apareciera en Marketo sin ninguna actividad asociada, entonces [!DNL Marketo Measure] descargó ese posible cliente, coincidió con las cookies asociadas y luego lo rastreó en la sesión web más reciente, incluso si no había ninguna actividad de formulario que creara el posible cliente.

## Preguntas frecuentes {#faq}

**¿Cómo sé si se crea una regla de Programas de Marketo o una regla de Actividades de Marketo?**

La variable [!DNL Marketo Engage] La integración de programas es una forma sencilla de generar puntos de contacto en función de si una persona es o no miembro de un programa. Si le interesa definir una regla en función del momento en el que una persona cambia a un estado de programa determinado, la variable [!DNL Marketo Engage] La integración de actividades es la configuración que desea, específicamente el tipo de actividad &quot;Cambiar estado en progresión&quot; para que la fecha de punto de contacto se pueda asignar a la fecha de actividad generada por el sistema.

**¿Por qué se trunca el nombre de mi tipo de punto de contacto?**

El campo Tipo de punto de contacto se creó en la variable [!DNL Marketo Measure] paquete con 16 caracteres. Lamentablemente, para cambiar el límite de caracteres del campo es necesario desaprobar el campo existente y crear uno nuevo. El valor del tipo de punto de contacto es el tipo de actividad, que también se establece en el campo Medio .

**¿Por qué mi tipo de actividad personalizado no aparece en la lista de actividades disponibles?**

Solo se muestran los tipos de actividades personalizadas &quot;Aprobado&quot; y no Borrador o Aprobado con Borrador.

**¿Cómo determino para qué tipos de actividades quiero generar un punto de contacto?**

Aunque no hay límite en el número de tipos de actividades que puede crear, generalmente se recomienda no más de 5 tipos de actividades. Se tarda tiempo en determinar qué actividades de marketing son lo suficientemente relevantes para formar parte del recorrido de touchpoint. Por ejemplo, &quot;Cancelar suscripción a correo electrónico&quot; puede no ser un punto de contacto significativo para rastrear, pero &quot;Hacer clic en correo electrónico&quot; con filtros adicionales puede ser bueno. Esto varía según cada organización y cada equipo, por lo que le sugerimos que trabaje con sus equipos para analizar el mejor enfoque aquí.

**¿Por qué mi nombre de navegador está cortado?**

La variable [!DNL Marketo Measure] El nombre del explorador tiene un límite estricto de 20 caracteres, aunque el valor del agente de usuario que obtenemos de Marketo tiende a ser una cadena más larga.

BrowserInfo.Name\
BrowserInfo.Version\
PlatformInfo.Name\
PlatformInfo.Version
