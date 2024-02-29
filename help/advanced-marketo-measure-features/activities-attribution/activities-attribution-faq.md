---
unique-page-id: 18874704
description: Preguntas frecuentes sobre atribución de actividades - [!DNL Marketo Measure]
title: Preguntas frecuentes sobre la atribución de actividades
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
feature: Attribution
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 2%

---

# Preguntas frecuentes sobre la atribución de actividades {#activities-attribution-faq}

[!DNL Marketo Measure] Las actividades importan todos los registros de actividad y generan puntos de contacto para ellas, lo que permite que estas actividades reciban crédito de atribución. El caso de uso más común es rastrear Actividades del equipo de ventas, ya que comúnmente crean un registro de llamadas telefónicas o correos electrónicos que se envían a los posibles clientes. Otras cosas únicas de las que se puede realizar un seguimiento son las interacciones de contenido, como las descargas de recursos o las vistas de vídeos.

**¿En qué se diferencia esto de las campañas sin conexión?**

La mayor diferencia es que las campañas solo pueden proporcionar un punto de contacto, ya que solo permiten un miembro de campaña por cada posible cliente o contacto. Esto significa que no puede realizar el seguimiento de eventos recurrentes como llamadas o demostraciones salientes o asistentes a seminarios web, a menos que cree campañas individuales para cada agrupación. Las actividades permiten medir cada evento.

**¿Hay alguna diferencia entre las tareas, los eventos y las actividades?**

El objeto Activities actúa como paraguas o elemento principal sobre los objetos Task y Event. Las actividades abarcan esencialmente tareas y eventos. Las tareas suelen utilizarse para registrar elementos puntuales rápidos, como una llamada telefónica o un correo electrónico. Los eventos suelen utilizarse para elementos que pueden tener una fecha de inicio o de finalización, como reuniones o conferencias.

**Si tengo un posible cliente o contacto con la misma tarea recurrente, ¿veré los puntos de contacto del comprador para todos?**

Sí. Existe una relación 1:1 entre las actividades sincronizadas y los puntos de contacto creados.

**¿Cómo sé qué registros resultan en la creación de puntos de contacto?**

Una buena sugerencia es configurar primero los filtros usando el objeto Activity en su CRM. En función de las reglas de filtro, esto le da una buena idea de cuántos registros se encuentran dentro de ese criterio, y luego puede refinarlos según sea necesario. Esto no es obligatorio, pero es una forma útil para que los usuarios entiendan cuántos puntos de contacto de actividades se crearán una vez configuradas las reglas de actividades.

**¿Qué es el [!DNL Marketo Measure] ¿Nombre de campaña?**

Dado que estas actividades generan un punto de contacto, [!DNL Marketo Measure] debe saber a qué canal y subcanal pertenecen. Para cada regla, debe proporcionar un [!DNL Marketo Measure] Nombre de campaña. Una vez creado, utilice el CSV de canales en línea para asignarlo [!DNL Marketo Measure] Nombre de la campaña a su canal correspondiente. El [!DNL Marketo Measure] Nombre de campaña también aparece en el propio punto de contacto dentro de la variable [!UICONTROL Nombre de campaña de publicidad] field.

**¿Qué otros campos de Touchpoint se rellenan?**

| **Campo Touchpoint** | **Valor** |
|---|---|
| Posible cliente/Contacto | Todas las actividades están relacionadas con un posible cliente o contacto |
| Campaña | Channel.Subchannel [[!DNL Marketo Measure]] |
| Origen del Touchpoint | Actividad de CRM |
| Medio | Activity.Type |
| Tipo de Touchpoint | Activity.Type |
| Nombre de campaña de anuncios | [!DNL Marketo Measure] Nombre de campaña |
| Contenido de anuncios | Asunto de actividad |
| ID de anuncio | ID externo de actividad |
| Fecha de Touchpoint | [personalizado: configurado en las aplicaciones] |

**¿Qué sucede si necesito crear una regla diferente para cada representante de ventas? ¿Necesito crear diferentes [!DNL Marketo Measure] ¿Campaña para cada uno?**

No, tú no. &quot;Nombres dinámicos de campaña&quot; le permite rellenar parte (o todo) el [!DNL Marketo Measure] Nombre de campaña con un &quot;parámetro de reemplazo&quot; que hace referencia a un campo del objeto Activity. Por ejemplo, si tiene un [!DNL Marketo Measure] Nombre de la campaña titulada &quot;Llamada saliente&quot;, pero si desea que el representante de ventas esté al final, tome el nombre del campo CRM y llame al [!DNL Marketo Measure] Nombre de campaña &quot;Llamada saliente&quot; {AssignedTo}&quot; o &quot;Llamada saliente {CreatedBy}.&quot;

**¿Cómo configuro las actividades de en? [!DNL Marketo Measure] aplicación?**

Instrucciones sobre cómo configurar actividades en [!UICONTROL Marketo] La aplicación Measure se encuentra en [!DNL Marketo Measure] Artículo de soporte de Actividades.

**¿Qué significan los distintos operadores?**

* is equal to: coincidencia exacta con el valor (también conocido como social)
* contains: el texto está en el medio (también conocido como: &#42;social&#42;)
* comienza con: el valor comienza con el texto (también conocido como: social)&#42;)
* termina con: el valor termina con el texto (también conocido como: &#42;social)
* coincide con cualquiera: se pueden agregar varios valores separados por comas. If [!UICONTROL empieza por], [!UICONTROL termina por], o si se deben aplicar operadores contains, utilice el comodín (&#42;)
* mayor que: se utiliza para campos numéricos o campos de fecha y hora
* menor que: se utiliza para campos numéricos o campos de fecha y hora

**¿En qué canal se incluyen estas actividades?**

Cuando la regla de actividad y sus correspondientes [!DNL Marketo Measure] Cuando se creen los nombres de las campañas, use las definiciones de Canales en línea para colocar esas campañas en el Canal de marketing correcto. [!DNL Marketo Measure] Puede definir canales utilizando no solo el medio y la fuente, sino también la campaña.

En el ejemplo anterior, para asignar la campaña &quot;Llamada saliente {Assigned To}&quot; al canal BDR, inserte una fila en el CSV de los canales en línea para el canal BDR con una definición de campaña de &quot;Llamada saliente&quot;&#42;&quot;: el asterisco indica un valor comodín, por lo que todas las campañas que comiencen con &quot;Llamada saliente&quot; caerán dentro del canal BDR, en lugar de tener que crear una fila independiente para cada nombre de campaña.
