---
unique-page-id: 18874704
description: Preguntas frecuentes sobre atribución de actividades - [!DNL Marketo Measure] - Documentación del producto
title: Preguntas frecuentes sobre atribución de actividades
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 2%

---

# Preguntas frecuentes sobre atribución de actividades {#activities-attribution-faq}

La variable [!DNL Marketo Measure] La funcionalidad Actividades nos permite importar todos sus registros de actividad y generar puntos de contacto para ellos, lo que permite que estas actividades reciban crédito de atribución. El caso de uso más común es rastrear las actividades del equipo de ventas, ya que normalmente crean un registro de llamadas telefónicas o correos electrónicos que se envían a los posibles clientes. Otras cosas únicas de las que se puede realizar un seguimiento son las interacciones de contenido, como las descargas de recursos o las vistas de vídeo.

**¿En qué se diferencia esto de las campañas sin conexión?**

La mayor diferencia es que las campañas solo pueden proporcionar un punto de contacto, ya que las campañas solo permiten un miembro de campaña por cada posible cliente o contacto. Esto significa que no se pueden rastrear eventos recurrentes como llamadas salientes, demostraciones o asistentes a seminarios web, a menos que se creen campañas individuales para cada grupo. Las actividades le permiten medir cada evento.

**¿Hay alguna diferencia entre Tarea, Eventos y Actividades?**

El objeto Actividades actúa como paraguas (o principal) sobre los objetos Tarea y Evento. Las actividades abarcan esencialmente tareas y eventos. Las tareas suelen utilizarse para registrar elementos únicos rápidos, como una llamada telefónica o un correo electrónico. Los eventos suelen utilizarse para cosas que pueden tener una fecha de inicio o de finalización, como reuniones o conferencias.

**Si tengo un posible cliente o contacto con la misma tarea recurrente como un correo electrónico o una llamada, ¿veré los puntos de contacto del comprador para todos esos elementos?**

Sí. Habrá una relación 1:1 entre las actividades sincronizadas y los touchpoints creados.

**¿Cómo sé qué registros resultarán en la creación de Touchpoints?**

Una buena sugerencia es configurar los filtros utilizando primero el objeto Activity en su CRM. En función de las reglas de filtro, esto le dará una buena idea de cuántos registros se encuentran bajo ese criterio y, a continuación, podrá refinarlos según sea necesario. Esto no es necesario, pero es una forma útil para que los usuarios entiendan cuántos puntos de contacto de actividades se crearán una vez que se hayan configurado las reglas de actividades.

**¿Qué es el [!DNL Marketo Measure] ¿Nombre de la campaña?**

Como estas actividades resultarán en un punto de contacto, [!DNL Marketo Measure] necesita saber a qué canal y subcanal pertenecen. Para cada regla, debe proporcionar un [!DNL Marketo Measure] Nombre de campaña. Una vez creado, puede usar el CSV de Canales en línea para asignarlo [!DNL Marketo Measure] Nombre de campaña al canal correspondiente. La variable [!DNL Marketo Measure] El nombre de campaña también aparecerá en el propio touchpoint dentro del [!UICONTROL Nombre de campaña de publicidad] campo .

**¿Qué otros campos de Touchpoint se rellenan?**

| **Campo de punto de contacto** | **Valor** |
|---|---|
| Cliente potencial o Contacto | Todas las actividades están relacionadas con un posible cliente o contacto |
| Campaña | Channel.Subchannel [[!DNL Marketo Measure]] |
| Fuente del Touchpoint | Actividad de CRM |
| Media | Activity.Type |
| Tipo de Touchpoint | Activity.Type |
| Nombre de campaña de publicidad | [!DNL Marketo Measure] Nombre de la campaña |
| Contenido de la publicidad | Asunto de la actividad |
| ID de anuncio | Id Externo De Actividad |
| Fecha de Touchpoint | [personalizado: se establece en aplicaciones] |

**¿Qué sucede si necesito crear una regla diferente para cada representante de ventas? ¿Debo crear diferentes [!DNL Marketo Measure] ¿Campañas para cada una?**

No, no. Hemos introducido un concepto de &quot;Nombres de campaña dinámicos&quot;. Esto le permite completar la parte (o todo) del [!DNL Marketo Measure] Nombre de campaña utilizando un &quot;parámetro de sustitución&quot; que hace referencia a un campo del objeto Actividad. Por ejemplo, si tiene un [!DNL Marketo Measure] Nombre de la campaña titulada &quot;Llamada saliente&quot; pero desea que el representante de ventas esté al final, toma el nombre del campo CRM y llama a la función [!DNL Marketo Measure] Nombre de campaña &quot;Llamada saliente {AssignedTo}&quot; o &quot;Llamada saliente {CreatedBy}&quot;.

**¿Cómo configuro actividades en la [!DNL Marketo Measure] app?**

Instrucciones sobre cómo configurar actividades dentro de la variable [!UICONTROL Marketo] La aplicación de medida se puede encontrar en la [!DNL Marketo Measure] Artículo de soporte técnico de las actividades.

**¿Qué significan los diferentes operadores?**

* es igual a: coincidencia exacta con el valor (también es decir: social)
* contiene: el texto está en el medio (también conocido como: &#42;social&#42;)
* comienza con: el valor empieza por el texto (también es decir: social&#42;)
* termina con: el valor termina con el texto (es decir: &#42;social)
* coincide con cualquiera: se pueden agregar varios valores separados por coma. If [!UICONTROL comienza con], [!UICONTROL termina con], o contiene operadores que deben aplicarse, se usa el comodín (&#42;)
* bueno que: se utiliza para campos numéricos o campos de fecha y hora
* menor que: se utiliza para campos numéricos o campos de fecha y hora

**¿En qué canal se incluirán estas actividades?**

Una vez que la regla de actividad y su correspondiente [!DNL Marketo Measure] Nombre de campaña, cuando se creen, usará las definiciones de Canales en línea para colocar esas Campañas en el Canal de marketing correcto. [!DNL Marketo Measure] tiene la capacidad de definir canales no solo mediante el medio y la fuente, sino también mediante campañas.

En el ejemplo anterior, para asignar la campaña &quot;Llamada saliente {Asignada a}&quot; al canal BDR, debe insertar una fila en el CSV de Canales en línea para el canal BDR con una definición de campaña de &quot;Llamada saliente&quot;&#42;&quot; - el asterisco indica un valor comodín, por lo que todas las campañas que empiecen con &quot;Llamada saliente&quot; caerán en el canal BDR, en lugar de tener que crear una fila separada para cada nombre de campaña.
