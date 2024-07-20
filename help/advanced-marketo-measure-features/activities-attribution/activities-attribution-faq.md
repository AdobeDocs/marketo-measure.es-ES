---
unique-page-id: 18874704
description: Preguntas frecuentes sobre la atribución de actividades - [!DNL Marketo Measure]
title: Preguntas frecuentes sobre la atribución de actividades
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
feature: Attribution
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 2%

---

# Preguntas frecuentes sobre la atribución de actividades {#activities-attribution-faq}

[!DNL Marketo Measure] actividades importa todos sus registros de actividad y genera puntos de contacto para ellos, lo que permite que estas actividades reciban crédito de atribución. El caso de uso más común es rastrear Actividades del equipo de ventas, ya que comúnmente crean un registro de llamadas telefónicas o correos electrónicos que se envían a los posibles clientes. Otras cosas únicas de las que se puede realizar un seguimiento son las interacciones de contenido, como las descargas de recursos o las vistas de vídeos.

**¿En qué se diferencia esto de las campañas sin conexión?**

La mayor diferencia es que las campañas solo pueden proporcionar un punto de contacto, ya que solo permiten un miembro de campaña por cada posible cliente o contacto. Esto significa que no puede realizar el seguimiento de eventos recurrentes como llamadas o demostraciones salientes o asistentes a seminarios web, a menos que cree campañas individuales para cada agrupación. Las actividades permiten medir cada evento.

**¿Hay alguna diferencia entre las tareas, los eventos y las actividades?**

El objeto Activities actúa como paraguas o elemento principal sobre los objetos Task y Event. Las actividades abarcan esencialmente tareas y eventos. Las tareas suelen utilizarse para registrar elementos puntuales rápidos, como una llamada telefónica o un correo electrónico. Los eventos suelen utilizarse para elementos que pueden tener una fecha de inicio o de finalización, como reuniones o conferencias.

**Si tengo un posible cliente o contacto con la misma tarea recurrente, ¿veré los puntos de contacto del comprador para todos?**

Sí. Existe una relación 1:1 entre las actividades sincronizadas y los puntos de contacto creados.

**¿Cómo sé qué registros resultan en la creación de puntos de contacto?**

Una buena sugerencia es configurar primero los filtros usando el objeto Activity en su CRM. En función de las reglas de filtro, esto le da una buena idea de cuántos registros se encuentran dentro de ese criterio, y luego puede refinarlos según sea necesario. Esto no es obligatorio, pero es una forma útil para que los usuarios entiendan cuántos puntos de contacto de actividades se crearán una vez configuradas las reglas de actividades.

**¿Cuál es el nombre de campaña de [!DNL Marketo Measure]?**

Dado que estas actividades generan un punto de contacto, [!DNL Marketo Measure] debe saber a qué canal y subcanal pertenecen. Para cada regla, debe proporcionar un nombre de campaña [!DNL Marketo Measure]. Una vez creado, utilice el CSV de canales en línea para asignar el nombre de la campaña [!DNL Marketo Measure] a su canal correspondiente. El nombre de campaña [!DNL Marketo Measure] también aparece en el propio punto de contacto dentro del campo [!UICONTROL Nombre de campaña de publicidad].

**¿Qué otros campos de Touchpoint se han rellenado?**

| **Campo de punto de contacto** | **Valor** |
|---|---|
| Posible cliente/Contacto | Todas las actividades están relacionadas con un posible cliente o contacto |
| Campaña | Channel.Subchannel [[!DNL Marketo Measure]] |
| Origen del Touchpoint | Actividad de CRM |
| Medio | Activity.Type |
| Tipo de Touchpoint | Activity.Type |
| Nombre de campaña de anuncios | [!DNL Marketo Measure] nombre de campaña |
| Contenido de anuncios | Asunto de actividad |
| ID de anuncio | ID externo de actividad |
| Fecha de Touchpoint | [personalizado: establecido en aplicaciones] |

**¿Qué sucede si necesito crear una regla diferente para cada representante de ventas? ¿Necesito crear una campaña [!DNL Marketo Measure] diferente para cada una?**

No, tú no. &quot;Nombres dinámicos de campaña&quot; le permite rellenar parte (o todo) el nombre de campaña [!DNL Marketo Measure] mediante un &quot;parámetro de reemplazo&quot; que hace referencia a un campo del objeto Activity. Por ejemplo, si tiene un nombre de campaña de [!DNL Marketo Measure] llamado &quot;Llamada saliente&quot; pero desea que el representante de ventas esté al final, use el nombre de campo CRM y llame al nombre de campaña de [!DNL Marketo Measure]: &quot;Llamada saliente {AssignedTo}&quot; o &quot;Llamada saliente {CreatedBy}&quot;.

**¿Cómo configuro las actividades en la aplicación [!DNL Marketo Measure]?**

Encontrará instrucciones sobre cómo configurar actividades en la aplicación de medidas [!UICONTROL Marketo] en el artículo de compatibilidad con actividades [!DNL Marketo Measure].

**¿Qué significan los distintos operadores?**

* is equal to: coincidencia exacta con el valor (también conocido como social)
* contains: el texto está en el medio (también conocido como: &#42;social&#42;)
* empieza por: el valor comienza con el texto (también conocido como: social&#42;)
* termina en: el valor termina con el texto (también conocido como: &#42;social)
* coincide con cualquiera: se pueden agregar varios valores separados por comas. Si [!UICONTROL comienza con], [!UICONTROL termina con] o contiene operadores que deben aplicarse, use el comodín (&#42;)
* mayor que: se utiliza para campos numéricos o campos de fecha y hora
* menor que: se utiliza para campos numéricos o campos de fecha y hora

**¿En qué canal se incluyen estas actividades?**

Cuando se creen la regla de actividad y su correspondiente nombre de campaña [!DNL Marketo Measure], use las definiciones de canales en línea para colocar esas campañas en el canal de marketing correcto. [!DNL Marketo Measure] puede definir canales no solo mediante el medio y el origen, sino también mediante la campaña.

En el ejemplo anterior, para asignar la campaña &quot;Llamada saliente {Assigned To}&quot; al canal BDR, inserte una fila en el CSV de canales en línea para el canal BDR con una definición de campaña de &quot;Llamada saliente&#42;&quot;: el asterisco denota un valor comodín, por lo que todas las campañas que comiencen con &quot;Llamada saliente&quot; caerán bajo el canal BDR, en lugar de tener que crear una fila independiente para cada nombre de campaña.
