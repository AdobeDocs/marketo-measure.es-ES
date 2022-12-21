---
unique-page-id: 42762310
description: 'Sincronización de datos históricos: [!DNL Marketo Measure] - Documentación del producto'
title: Sincronización de datos históricos
exl-id: 5a3c1a71-463a-4d75-98b9-fc225839512a
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '1496'
ht-degree: 1%

---

# Sincronización de datos históricos {#syncing-historical-data}

[!DNL Marketo Measure] es una solución que proporciona los datos más granulares y procesables. Sin embargo, entendemos que es posible que tenga datos existentes para los que desee atribuir. Es posible generar touchpoints para los datos históricos, pero es importante tener en cuenta algunos factores antes de avanzar en este proceso.

## Factores que hay que tener en cuenta {#factors-to-consider}

**¿Los datos ya están organizados en campañas?**

a. Los datos deben organizarse en Campañas para sincronizarse con [!DNL Marketo Measure] para que se generen Touchpoints. Si actualmente no está organizado en Campañas, debe evaluar si vale la pena el tiempo y los recursos necesarios para segmentar los datos en las campañas correspondientes.

b. La fecha en la que el miembro fue agregado a la campaña o marcado como respondido se utilizará para la fecha de Touchpoint, por lo que también debe ser precisa. [!DNL Marketo Measure] ofrece soluciones alternativas tanto en SFDC como en MSD para actualizar las fechas, pero esto podría llevar mucho tiempo en función del volumen.

**¿Tiene una cantidad de datos equitativa organizada en campañas para todos los canales (búsqueda de pago, eventos, orgánicos, etc.)?**

Es importante tener una imagen equilibrada de la atribución para tener informes precisos y &quot;justos&quot;. Por ejemplo, si solo tiene datos para esfuerzos históricos de canales sin conexión como Eventos, los datos se sesgarán inherentemente sin datos históricos en línea para complementarlos.

**¿Qué nivel de granularidad espera?**

Esencialmente, solo conocerá el nombre del canal, el subcanal y la campaña.

**¿Cuáles son sus objetivos de creación de informes en el futuro?**

Estos datos van a ser limitados, por lo que es importante tener en cuenta cómo planea usarlos. Es posible que no tenga sentido comparar los datos históricos con los datos futuros.

**¿Hasta dónde quieres ir?**

[!DNL Marketo Measure] recomienda encarecidamente no pasar del año anterior.

Este es un tema que recomendamos encarecidamente que debatamos con su [!DNL Marketo Measure] póngase en contacto primero. Si ha considerado lo anterior y desea continuar, instrucciones generales (separadas para [!DNL Salesforce] y [!DNL Microsoft Dynamics]).

## Sincronización de campañas históricas en [!DNL Salesforce] {#syncing-historic-campaigns-in-salesforce}

**En línea:**

Para sincronizar datos en línea históricos, los datos deben estar organizados en campañas de Salesforce a las que desee sincronizar [!DNL Marketo Measure] via [!DNL Salesforce] Reglas de sincronización de campañas en [!DNL Marketo Measure] aplicación. Es importante asegurarse de que los puntos de contacto no se generen a partir de ninguna de estas campañas después de la fecha en que se activó el JavaScript. El motivo de esto es evitar puntos de contacto duplicados. Una vez que JavaScript está activo, los esfuerzos en línea se rastrean automáticamente, por lo que no queremos rastrearlos también a través de una campaña SFDC. Para evitar este problema, asegúrese de agregar una sensación de tiempo a la regla. Tal vez algo como &quot;Fecha de creación de miembro de campaña&quot; sea menor que [Fecha de lanzamiento de JavaScript]&quot;.

![](assets/syncing-historical-data-1.png)

El componente de asignación de canales para datos en línea históricos puede ser un poco complicado. Queremos que coincida con sus reglas de canal en línea actuales (desde la hoja de reglas en línea) lo más cerca posible para informes limpios. A continuación se muestra un ejemplo de asignación de canales ideal.

>[!NOTE]
>
>Esta asignación de canales se realiza en la variable [!UICONTROL Canales sin conexión] de la sección [!DNL Marketo Measure] ya que estamos usando campañas SFDC.

| Tipo de campaña de Salesforce | Canal | Subcanal |
|---|---|---|
| Búsqueda de pago - AdWords | Búsqueda paga | AdWords |
| Búsqueda de pago - Bing | Búsqueda paga | Bing |
| Búsqueda de pago: Yahoo | Búsqueda paga | Yahoo |

Los datos en línea agregados de esta manera serán inherentemente menos granulares que los datos en línea [!DNL Marketo Measure] rastrea a través de JavaScript. Por ejemplo, los campos como Dirección URL del formulario, Página de aterrizaje, Página de referente, etc. no se rellenarán. Por lo tanto, se recomienda dividir las campañas en cada fuente si es posible. Como se observa en el ejemplo anterior, es necesario tener varios tipos de campaña para cada fuente a fin de tener granularidad en los informes.

Puede que no sea posible o razonable tener el número de tipos de campaña de SFDC para admitir la asignación de canales granular, por lo que puede recurrir a la asignación únicamente al nivel de canal e ignorar los subcanales. Si el nivel de canal tampoco se conoce, puede configurar un canal proxy como &quot;Digital histórico&quot; para que al menos sepa que fue un contacto en línea.

Si necesita editar en masa la fecha del punto de contacto que se insertará para estos esfuerzos históricos en línea, utilice el [!DNL Marketo Measure] personalizado &quot;[!UICONTROL Fecha de punto de contacto de actualización masiva]&quot; (está disponible como campo personalizado en el objeto de campaña en SFDC). Si la campaña tiene un lapso de tiempo corto, quizá valga la pena editar en masa la fecha del punto de contacto de un día a otro, mientras que podría tener sentido realizar actualizaciones en masa semanalmente si la campaña tiene un lapso de tiempo más largo. Si utiliza la funcionalidad de Fecha de punto de contacto de actualización masiva, asegúrese de actualizar la regla de sincronización de campaña para usar la Fecha de punto de contacto del comprador en el campo de fecha. Tenga en cuenta que esto podría requerir ser creativo con las reglas de sincronización de campañas si esto solo se aplica a una o dos campañas y no a todas.

**Sin conexión:**

Los datos históricos de los esfuerzos de marketing sin conexión (aquellos que no se pueden rastrear mediante JavaScript) también deberán organizarse en campañas SFDC. Las campañas de SFDC son la forma [!DNL Marketo Measure] rastrea los esfuerzos sin conexión independientemente de si la actividad es &quot;histórica&quot; o &quot;actual/posterior[!DNL Marketo Measure] implementación&quot;, por lo que debe seguir la misma asignación de canales decidida en la formación original de Configuración de canales sin conexión.

Si es necesario, utilice el botón &quot;Actualización masiva de fecha de punto de contacto&quot; para editar en masa la fecha de punto de contacto para los miembros de la campaña. Por ejemplo, si está creando campañas de SFDC después de que se produzca el evento, querrá editar en masa la fecha correcta. Si utiliza la funcionalidad de Fecha de punto de contacto de actualización masiva, asegúrese de actualizar la regla de sincronización de campaña para usar la Fecha de punto de contacto del comprador en el campo de fecha. Tenga en cuenta que esto podría requerir ser creativo con las reglas de sincronización de campañas si esto solo se aplica a una o dos campañas y no a todas.

## Sincronización de campañas históricas en [!DNL Dynamics] {#syncing-historic-campaigns-in-dynamics}

[!DNL Marketo Measure] puede generar de forma retroactiva puntos de contacto para interacciones que se hayan producido en el pasado, siempre que estén organizadas en Campañas dentro de [!DNL Dynamics].

Esto suele implicar trabajo en CRM para contabilizar fechas históricas. El control también será diferente para los esfuerzos en línea (rastreados por JS) y los esfuerzos sin conexión (no se pueden rastrear con JS).

Siga las instrucciones que se indican a continuación para organizar los datos históricos en [!DNL Dynamics] en un formato que se pueda sincronizar con [!DNL Marketo Measure].

**En línea:**

Los datos digitales históricos deben organizarse en [!DNL Dynamics] campañas para que se rellenen. Idealmente, esta estructura ya está en su lugar.

Si los datos se alojan en otro sitio (como sigue viviendo en la automatización de marketing), será necesario insertarlos en [!DNL Dynamics] y se organizan en las campañas correspondientes. A continuación, tendrá que tener en cuenta la fecha del punto de contacto, ya que desea que refleje la fecha del pasado, no la fecha en la que la insertó [!DNL Dynamics]. Para anular esta fecha, puede utilizar el campo personalizado &quot;Fecha de punto de contacto del comprador&quot; para cambiar la fecha. Deberá agregarlo al formulario de lista de marketing.

![](assets/syncing-historical-data-2.png)

Como resultado, puede establecer de forma masiva la fecha para todos los miembros de esa lista de marketing que se utilizará para la fecha de punto de contacto. Para tener fechas históricas más precisas, cree varias listas de marketing para la misma campaña, cada una con su propia fecha de punto de contacto. Si la campaña tiene un lapso de tiempo corto, quizá valga la pena crear una lista de marketing para cada día. Si la campaña tiene un lapso de tiempo más largo, puede que sea recomendable crear una lista de marketing semanalmente.

Puede encontrar más información sobre la sincronización de listas de marketing aquí: [[!DNL Dynamics] Campañas y listas de marketing](/help/marketo-measure-and-dynamics/dynamics-reporting/dynamics-campaigns-and-marketing-lists.md)

>[!NOTE]
>
>Si, por cualquier motivo, tiene una actividad de seguimiento en línea de campaña activa después de la fecha de lanzamiento de JavaScript, asegúrese de establecer la variable[!UICONTROL Fecha de finalización de Touchpoint]&quot; hasta la fecha en que se activó el JS. Esto sirve para evitar tener puntos de contacto duplicados para la misma interacción.

Consideraciones: Los datos en línea agregados de esta manera serán inherentemente menos granulares que los datos en línea [!DNL Marketo Measure] rastrea a través de JavaScript. Por ejemplo, campos como: La dirección URL del formulario, la página de aterrizaje, la página de referente, etc., no se rellenarán. Por lo tanto, se recomienda dividir las campañas en cada fuente si es posible. A continuación se muestra un ejemplo de asignación ideal.

| Tipo de campaña de Dynamics | Canal | Subcanal |
|---|---|---|
| Búsqueda de pago - AdWords | Búsqueda paga | AdWords |
| Búsqueda de pago - Bing | Búsqueda paga | Bing |
| Búsqueda de pago: Yahoo | Búsqueda paga | Yahoo |

Si no dispone de una forma de identificar una fuente o no vale la pena dedicar tiempo y esfuerzo, puede utilizar un tipo de campaña asignado a un canal denominado, por ejemplo, &quot;Digital heredado&quot; o &quot;Sitio web histórico&quot;.

**Sin conexión:**

Para tener puntos de contacto para esfuerzos de marketing sin conexión del pasado, los datos deben organizarse en [!DNL Dynamics] campañas y sincronizadas con [!DNL Marketo Measure]. El proceso es el mismo que para los canales sin conexión actuales (sincronice la campaña mediante Listas de marketing o Respuestas de campaña). A continuación se muestra un ejemplo de asignación de canales.

| Tipo de campaña de Dynamics | Canal | Subcanal |
|---|---|---|
| Eventos: conferencias patrocinadas | Eventos | Conferencias patrocinadas |
| Eventos: eventos de socio | Eventos | Eventos de socios |
| Eventos: eventos alojados | Eventos | Eventos alojados |
| Seminario web: seminario web para socios | Seminario web | Seminario web para socios |

Si estos datos no están ya organizados en Campañas con las fechas correctas establecidas, puede utilizar el campo &quot;Fecha de punto de contacto del comprador&quot; para reflejar la fecha exacta de la actividad sin conexión del pasado.

