---
unique-page-id: 42762729
description: "[!DNL Marketo Engage] Integración de programas - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Engage] Integración de programas"
exl-id: c26087e3-d821-4fe7-bacd-eeaa1530a4b0
feature: Integration
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1259'
ht-degree: 2%

---

# [!DNL Marketo Engage] Integración de programas {#marketo-engage-programs-integration}

A través de [!DNL Marketo Measure] integración con [!DNL Marketo Engage] Nuestros clientes pueden empezar a crear puntos de contacto para el seguimiento de atribución desde las suscripciones al programa de Marketo. Esta capacidad permite a los especialistas en marketing iniciar el seguimiento de las suscripciones a programas desde programas de correo electrónico o participación que, de lo contrario, no serían vistos por el [!DNL Marketo Measure] javascript y deben medirse dentro del recorrido de atribución.

## Disponibilidad {#availability}

Todos los niveles.

## Requisitos {#requirements}

* Instancia de Production Marketo
* Instancia de Production Salesforce o Microsoft Dynamics
* Cualquier pago [!DNL Marketo Measure] suscripción
* Sincronización de personas de Marketo habilitada ([!DNL Marketo Measure] Configuración)
* Programas Marketo habilitados ([!DNL Marketo Measure] Configuración)

## Instalación {#setup}

**Reglas**

1. Para empezar a configurar reglas en Programas de Marketo, vaya a **[!UICONTROL Mi cuenta]** > **[!UICONTROL Configuración]** > **[!UICONTROL Programas]**. Haga clic en **+** para empezar a crear la primera regla.

   ![](assets/one.png)

   ![](assets/two.png)

1. Si lo desea, puede definir un nombre para la regla si resulta útil realizar un seguimiento de la misma. Primero debe seleccionar el campo para definir la regla en la lista de campos Programa y Suscripción al programa. Continúe creando la regla seleccionando el operador y el valor esperado que desea comprobar.

   ![](assets/three.png)

1. Añada otra instrucción dentro del mismo cuadro para configurar un criterio &quot;y&quot; en la regla o haga clic en el icono + fuera del cuadro para configurar una instrucción &quot;o&quot;.

   ![](assets/four.png)

1. Elija qué fecha o campo de fecha/hora debe utilizarse para asignar a la fecha del punto de contacto. Para ver la lista de valores disponibles en Marketo, introduzca una llave `{` y se muestran los campos disponibles.

   ![](assets/five.png)

   >[!NOTE]
   >
   >Si la regla desea registrar la fecha de la actividad o la fecha en la que un miembro del programa alcanzó un estado determinado, deberá utilizar la variable [!DNL Marketo Engage] Actividades Integración y configuración de una regla para el tipo de actividad &quot;Cambiar estado en progresión&quot;.

   ![](assets/six.png)

La regla completada debería tener un aspecto similar al siguiente:

## Prueba {#test}

Después de crear algunas reglas, es posible que desee probarlas para comprobar que la instrucción coincide con los programas.

1. Para ejecutar una prueba, haga clic en **[!UICONTROL PRUEBA]** como se muestra a continuación.

   ![](assets/seven.png)

1. Aparecerá un modal donde puede introducir el ID de programa desde Marketo.

   ![](assets/eight.png)

   Una vez introducido el ID de y hecho clic en [!UICONTROL Prueba] , nuestro motor de reglas pasará por cada regla y determinará si el Programa se ajusta o no a alguna de las reglas. En el ejemplo siguiente, puede ver que el Programa 1002, llamado [!DNL Marketo Measure] Libro electrónico, tiene 5 miembros del programa y es elegible debido a la regla que se muestra.

   Las reglas se ejecutan en un tamaño de muestra de 5000 miembros. Si su programa contiene más de 5000 miembros, es posible que no verifiquemos la compatibilidad de todos los miembros. Esta herramienta simplemente sirve como una forma de comprobar si las reglas se construyen correctamente.

   ![](assets/nine.png)

   Puede hacer clic en el recuento de miembros para ver una lista de los ID de personas de Marketo que cumplen los requisitos dentro del programa.

   ![](assets/ten.png)

## Asignación de canales {#channel-mapping}

En la lista de canales de programa de Marketo, debe asignar los valores al [!DNL Marketo Measure] canales de marketing personalizados que haya creado en Configuración. Cualquier punto de contacto generado por estos programas heredará los nombres de canal y subcanal que seleccione aquí.

1. Comience por navegar hasta **[!UICONTROL Mi cuenta]** > **[!UICONTROL Configuración]** > **[!UICONTROL Canales sin conexión]**.

1. En la parte superior, tendrá la opción de asignar a sus tipos de campaña de CRM y, a continuación, abajo, verá las opciones para sus canales de programa de Marketo.

1. Seleccione primero el canal que debe asignarse al valor y, a continuación, seleccione opcionalmente el subcanal. Una vez finalizado, haga clic en **[!UICONTROL Guardar]** en la parte inferior.

   ![](assets/eleven.png)

## Costos de programa {#program-costs}

Mediante la importación de datos de los programas de Marketo, los costes se descargan automáticamente de los costes del periodo y el coste notificado en Marketo se distribuye a lo largo del mes asignado. Por ejemplo, si se informa de 1000 $ para enero de 2021, los 1000 $ se dividen en 31 días. Los costes se encuentran en [!DNL Marketo Measure Discover].

## Cómo funciona {#how-it-works}

**Asignaciones de campos**

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>biz_ad_campaigns</th> 
   <th>Marketo</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>Identificación</td> 
  </tr> 
  <tr> 
   <td>IS_DELETED</td> 
   <td>(compruebe si el programa sigue existiendo a través de la API)</td> 
  </tr> 
  <tr> 
   <td><p>NAME</p></td> 
   <td>name</td> 
  </tr> 
 </tbody> 
</table>

| biz_campaign_members | Marketo |
|---|---|
| ID | &quot;MarketoProgramMembership&quot;_ProgramId_Lead Id |
| MODIFIED_DATE | updatedAt |
| CREATED_DATE | memberDate |
| LEAD_ID | ID (inscripción a la lista) |
| LEAD_EMAIL | Correo electrónico (miembros de lista) |
| STATUS | progressionStatus |
| HAS_RESPONDED | reachedStatus |
| CAMPAIGN_NAME | programName |
| CAMPAIGN_ID | programId |
| CAMPAIGN_TYPE | canal |

## Asignación de cookies {#cookie-mapping}

Como resultado de la [!DNL Marketo Measure] integración con Marketo, la [!DNL Marketo Measure] El ID de cookie ahora también está asignado y sincronizado con el [!DNL Marketo Munchkin Id]. Esto ayuda a cerrar la brecha para atribuir el primer contacto anónimo a una sesión web en lugar de atribuir los toques FTP y LC a una actividad de Marketo. Imagine este escenario:

Marcar clics en una [!DNL Facebook] anuncio y aterriza en wayneenterprises.com donde lo cocinan con [!DNL Marketo Measure] Id 123 y [!DNL Marketo Munchkin Id] 456. No se rellena ningún formulario.

El equipo de marketing de empresas de Wayne envía una notificación por correo electrónico a posibles clientes específicos, uno de los cuales es `mark@email.com`.

`mark@email.com` recibe el correo electrónico, hace clic y aterriza en wayneenterprises.com. Esto se convierte en `mark@email.com's` segunda visita a `wayneenterprise.com` con los mismos ID de cookie, pero no se rellenó el formulario, por lo que [!DNL Marketo Measure]Sin embargo, siguen siendo un visitante anónimo.

El equipo de marketing de empresas Wayne crea una regla de actividad de Marketo para generar puntos de contacto para un tipo de actividad de &quot;clic en correo electrónico&quot;.

La implementación de hoy crearía un único punto de contacto FT y LC para `mark@email.com` de la actividad de Marketo desde el tipo de actividad &quot;Haga clic en correo electrónico&quot;.

Con esta mejora de la asignación de cookies, la FT volvería y se acreditaría a la [!DNL Facebook] El anuncio y la LC se acreditarían al correo electrónico.

>[!NOTE]
>
>Con el comportamiento de asignación de cookies, puede encontrar algunos puntos de contacto LC que provienen de una visita web. Es posible que un posible cliente apareciera en Marketo sin ninguna actividad asociada, y [!DNL Marketo Measure] descargó ese posible cliente, comparó las cookies asociadas y, a continuación, lo rastreó hasta la sesión web más reciente, incluso si no había ninguna actividad de formulario que creara el posible cliente.

## Preguntas frecuentes {#faq}

**¿Cómo configuro la fecha de punto de contacto para que sea la fecha de progresión o la fecha en la que se produjo el cambio de estado para el miembro de mi programa?**

Si la regla desea registrar la fecha de la actividad o la fecha en la que un miembro del programa alcanzó un estado determinado, deberá utilizar la variable [!DNL Marketo Engage] Actividades Integración y configuración de una regla para el tipo de actividad &quot;Cambiar estado en progresión&quot;. De lo contrario, la variable [!DNL Marketo Engage] La integración de programas solo hace que la fecha de pertenencia esté disponible, que es la primera fecha que trajo a la persona de Marketo al programa, aunque haya varios estados.

**¿Puedo obtener una lista de selección de opciones de fecha para la fecha de Touchpoint?**

Para almacenar en déclencheur el autocompletado, comience introduciendo un corchete `{` en el campo de texto, aparecen los campos disponibles.

**Si creo reglas del programa Marketo y también tengo reglas de campaña CRM, ¿se contarán dos veces?**

Depende de la definición de la regla, pero posiblemente, sí. Deberá evaluar el conjunto de reglas para no tener reglas que abarquen un programa y una campaña, ya que no se anulará la duplicación ni se detectarán suscripciones similares. Una posible solución es copiar las reglas de Campaign en Programas si desea que Marketo sea la única fuente fiable y luego eliminar las reglas de Campaign. Otra opción es agregar un criterio &quot;CreatedOn&quot; o &quot;CreatedDate&quot; en las reglas para que las reglas anteriores a una fecha determinada utilicen reglas de Campaign y las reglas posteriores a una fecha determinada utilicen reglas de Programa. Hay muchas soluciones, pero se necesitará algo de planificación y coordinación.

**¿Están disponibles para definir los campos personalizados de pertenencia a programas de Marketo?**

Debido a limitaciones técnicas, por ahora no se pueden admitir campos personalizados de pertenencia a programas. Una vez que esos campos estén disponibles a través de API de Marketo adicionales, se expondrán a nosotros y serán visibles para que los utilice.

**¿Cómo sé si debo usar Programas o Actividades?**

El [!DNL Marketo Engage] La integración de programas es una forma sencilla de generar puntos de contacto en función de si una persona es o no miembro de un programa. Si está interesado en definir una regla basada en el momento en que una persona cambia a un estado de programa determinado, la variable [!DNL Marketo Engage] La integración de actividades será la configuración que desee, específicamente el tipo de actividad &quot;Cambiar estado en progresión&quot;.
