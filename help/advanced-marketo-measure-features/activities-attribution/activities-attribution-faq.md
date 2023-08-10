---
unique-page-id: 18874704
description: Preguntas frecuentes sobre atribución de actividades - [!DNL Marketo Measure] - Documentación del producto
title: Preguntas frecuentes sobre la atribución de actividades
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
feature: Attribution
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 3%

---

# Preguntas frecuentes sobre la atribución de actividades {#activities-attribution-faq}

El [!DNL Marketo Measure] La funcionalidad Actividades nos permite importar todos sus registros de actividad y generar puntos de contacto para ellos, lo que permite que estas actividades reciban crédito de atribución. El caso de uso más común es rastrear Actividades del equipo de ventas, ya que normalmente crearán un registro de llamadas telefónicas o correos electrónicos enviados a los posibles clientes. Otras cosas únicas de las que se puede realizar un seguimiento son las interacciones de contenido, como las descargas de recursos o las vistas de vídeos.

**¿En qué se diferencia esto de las campañas sin conexión?**

La mayor diferencia es que las campañas solo pueden proporcionar un punto de contacto, ya que solo permiten un miembro de campaña por cada posible cliente o contacto. Esto significa que no puede realizar el seguimiento de eventos recurrentes como llamadas o demostraciones salientes o asistentes a seminarios web, a menos que cree campañas individuales para cada agrupación. Las actividades te permitirán medir todos y cada uno de los eventos.

**¿Hay alguna diferencia entre las tareas, los eventos y las actividades?**

El objeto Activities actúa como paraguas o elemento principal sobre los objetos Task y Event. Las actividades abarcan esencialmente tareas y eventos. Las tareas suelen utilizarse para registrar elementos puntuales rápidos, como una llamada telefónica o un correo electrónico. Los eventos suelen utilizarse para elementos que pueden tener una fecha de inicio o de finalización, como reuniones o conferencias.

**Si tengo un posible cliente o un contacto con la misma tarea recurrente, como un correo electrónico o una llamada, ¿veré los puntos de contacto del comprador para todos?**

Sí. Habrá una relación 1:1 entre las actividades sincronizadas y los puntos de contacto creados.

**¿Cómo sé qué registros resultarán en la creación de puntos de contacto?**

Una buena sugerencia es configurar primero los filtros usando el objeto Activity en su CRM. En función de las reglas de filtro, esto le dará una buena idea de cuántos registros se encuentran dentro de ese criterio, a continuación, puede refinarlos según sea necesario. Esto no es obligatorio, pero es una forma útil para que los usuarios entiendan cuántos puntos de contacto de actividades se crearán una vez configuradas las reglas de actividades.

**¿Qué es el [!DNL Marketo Measure] ¿Nombre de campaña?**

Dado que estas actividades generarán un punto de contacto, [!DNL Marketo Measure] necesita saber a qué canal y subcanal pertenecen. Para cada regla, se le solicitará que proporcione un [!DNL Marketo Measure] Nombre de campaña. Una vez creado, puede utilizar el CSV de canales en línea para asignarlo [!DNL Marketo Measure] Nombre de la campaña a su canal correspondiente. El [!DNL Marketo Measure] El nombre de la campaña también aparecerá en el propio punto de contacto dentro de la variable [!UICONTROL Nombre de campaña de publicidad] field.

**¿Qué otros campos de Touchpoint se rellenan?**

| **Campo Touchpoint** | **Valor** |
|---|---|
| Cliente potencial o Contacto | Todas las actividades están relacionadas con un posible cliente o contacto |
| Campaña | Channel.Subchannel [[!DNL Marketo Measure]] |
| Origen del punto de contacto | Actividad de CRM |
| Medio | Activity.Type |
| Tipo de Touchpoint | Activity.Type |
| Nombre de campaña de anuncios | [!DNL Marketo Measure] Nombre de la campaña |
| Contenido de anuncios | Asunto de actividad |
| ID de anuncio | ID externo de actividad |
| Fecha de Touchpoint | [personalizado: configurado en las aplicaciones] |

**¿Qué sucede si necesito crear una regla diferente para cada representante de ventas? ¿Necesito crear diferentes [!DNL Marketo Measure] ¿Campañas para cada uno?**

No, tú no. Presentamos el concepto &quot;Nombres dinámicos de campaña&quot;. Esto le permite rellenar parte (o todo) del [!DNL Marketo Measure] Nombre de campaña con un &quot;parámetro de reemplazo&quot; que hace referencia a un campo del objeto Activity. Por ejemplo, si tiene un [!DNL Marketo Measure] Nombre de la campaña titulada &quot;Llamada saliente&quot;, pero si desea que el representante de ventas esté al final, tome el nombre del campo CRM y llame al [!DNL Marketo Measure] Nombre de campaña &quot;Llamada saliente&quot; {AssignedTo}&quot; o &quot;Llamada saliente {CreatedBy}.&quot;

**¿Cómo configuro las actividades de en? [!DNL Marketo Measure] aplicación?**

Instrucciones sobre cómo configurar actividades dentro de [!UICONTROL Marketo] La aplicación Measure se encuentra en [!DNL Marketo Measure] Artículo de soporte de Actividades.

**¿Qué significan los distintos operadores?**

* is equal to: coincidencia exacta con el valor (también conocido como social)
* contains: el texto está en el medio (también conocido como: &#42;social&#42;)
* comienza con: el valor comienza con el texto (también conocido como: social)&#42;)
* termina con: el valor termina con el texto (también conocido como: &#42;social)
* coincide con cualquiera: se pueden agregar varios valores separados por comas. If [!UICONTROL empieza por], [!UICONTROL termina por], o si es necesario aplicar los operadores de contiene, use el comodín (&#42;)
* bueno que: se utiliza para campos numéricos o campos de fecha y hora
* menor que: se utiliza para campos numéricos o campos de fecha y hora

**¿En qué canal se transferirán estas actividades?**

Una vez la regla de actividad y sus correspondientes [!DNL Marketo Measure] Cuando se creen, los nombres de campaña, utilizarán las definiciones de Canales en línea para colocar esas campañas en el canal de marketing correcto. [!DNL Marketo Measure] tiene la capacidad de definir canales no solo usando el medio y la fuente, sino también la campaña.

En el ejemplo anterior, para asignar la campaña &quot;Llamada saliente {Asignada a}&quot; al canal BDR, deseará insertar una fila en el CSV de canales en línea para el canal BDR con una definición de campaña de &quot;Llamada saliente&quot;&#42;&quot;: el asterisco indica un valor comodín, por lo que todas las campañas que comiencen con &quot;Llamada saliente&quot; caerán dentro del canal BDR, en lugar de tener que crear una fila independiente para cada nombre de campaña.
