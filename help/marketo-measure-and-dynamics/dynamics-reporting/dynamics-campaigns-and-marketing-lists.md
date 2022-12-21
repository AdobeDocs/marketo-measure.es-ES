---
unique-page-id: 18874610
description: 'Campañas de Dynamics y listas de marketing: [!DNL Marketo Measure] - Documentación del producto'
title: Listas de marketing y campañas de Dynamics
exl-id: 7b3d4032-5edf-489d-b86b-1e2a5755b258
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 0%

---

# Listas de marketing y campañas de Dynamics {#dynamics-campaigns-and-marketing-lists}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero aún así ver &quot;Bizible&quot; en su CRM. Estamos trabajando para que esto se actualice y el cambio de marca se reflejará pronto en su CRM.

## Campañas {#campaigns}

Las campañas de Dynamics son adecuadas para realizar el seguimiento de la actividad de marketing sin conexión e incluirlas en el recorrido omnicanal. Las campañas deben estar relacionadas con posibles clientes o contactos y pueden resumirse en la campaña a través de las respuestas de campaña o las listas de marketing.

## Respuestas de campaña {#campaign-responses}

Cuando los posibles clientes o los contactos se añaden directamente a una campaña, se introducen como registro de respuesta a la campaña.

![](assets/1.png)

## Habilitar puntos de contacto {#enable-touchpoints}

Para incluir estos registros en el recorrido de touchpoint, existen algunas opciones para sincronizar los tipos de respuestas de campaña. En el registro de campaña, debe haber un campo personalizado de la solución instalada con la etiqueta &quot;[!UICONTROL Habilitar puntos de contacto del comprador].&quot; Si no lo ve, el campo deberá agregarse mediante el Editor de formularios.

![](assets/2.png)

Puede seleccionar incluir todos los registros que tengan una respuesta de campaña en la campaña, o solo los que tengan una respuesta de &quot;Interesado&quot; o, de forma predeterminada, no puede incluir ninguna respuesta de campaña. Puede dejar el campo en blanco o explícitamente elegir excluirlo.

[!DNL Marketo Measure] no admite valores de respuesta personalizados.

![](assets/3.png)

Estos son los valores de respuesta de stock para la respuesta de campaña:

![](assets/4.png)

Según su selección, estos registros ahora son aptos para puntos de contacto en el recorrido de posibles clientes, contactos u oportunidades. Si cumplen los requisitos, aparecerá un punto de contacto de &quot;Dynamics Campaign&quot; en el recorrido.

Una de las razones por las que una respuesta de campaña podría no aparecer es porque ya se había registrado una actividad de primer toque o contacto de creación de posibles clientes para el posible cliente o contacto y la función &quot;PostLC&quot; está desactivada o ha alcanzado su número máximo de puntos de contacto.

## Fecha de Touchpoint {#touchpoint-date}

La fecha de punto de contacto de una campaña suele ser la fecha en la que se agregó la respuesta de la campaña a la campaña. Se puede sobrescribir si se rellena el campo personalizado de la solución instalada con la etiqueta &quot;Fecha del punto de contacto del comprador&quot;. Si no lo ve, el campo deberá agregarse mediante el Editor de formularios.

Un ejemplo habitual de este campo es el de los eventos en los que se agrega una lista de análisis de distintivos de un evento a CRM días después de ocurrir el evento, de modo que el usuario pueda cambiar de nuevo la Fecha de punto de contacto del comprador al momento en que se produjo el evento.

![](assets/5.png)

## Listas de marketing {#marketing-lists}

Las listas de marketing son otra forma de incluir posibles clientes o contactos en un recorrido de marketing. Las listas de marketing son únicas para un grupo de posibles clientes o contactos, lo que significa que el usuario debe seleccionar si su lista es un conjunto de posibles clientes o un conjunto de contactos.

[!DNL Marketo Measure] solo admite listas de marketing estáticas. No se admiten las listas de marketing dinámico porque nuestro procesamiento requiere que verifiquemos la fecha de modificación de un registro, pero como una lista dinámica está cambiando con frecuencia, no hay ninguna fecha de modificación para [!DNL Marketo Measure] para comprobar con. Esto requeriría una descarga constante del conjunto de datos completo a lo largo del día.

![](assets/6.png)

La captura de pantalla anterior es una Lista de marketing para posibles clientes. Las listas de marketing están asociadas a campañas y se pueden asociar a varias campañas. A menos que solo cree una lista de marketing para una campaña, [!DNL Marketo Measure] no recomienda que los clientes usen listas de marketing para rastrear sus campañas. Es poco probable que la misma lista exacta de posibles clientes o contactos sea elegible para puntos de contacto en varias campañas.

## Habilitar puntos de contacto {#enable-touchpoints-1}

Para habilitar una lista de marketing para puntos de contacto, hay una configuración independiente en el registro de campaña etiquetada como &quot;[!UICONTROL Sincronizar listas de marketing],&quot; que es un simple interruptor de sí/no. Si no lo ve, el campo deberá agregarse mediante el Editor de formularios. En el registro de campaña, puede ver qué listas de marketing están relacionadas con la campaña para saber cuántas listas está habilitando.

![](assets/7.png)

## Fecha de Touchpoint {#touchpoint-date-1}

La fecha de Touchpoint de una lista de marketing suele ser la fecha creada por ListMember, por lo que la fecha en la que el posible cliente o contacto se agregó a la lista de marketing. Se puede sobrescribir si se rellena el campo personalizado de la solución instalada con la etiqueta &quot;Fecha del punto de contacto del comprador&quot;. Si no lo ve, el campo deberá agregarse mediante el Editor de formularios.

![](assets/8.png)

## Asignación de canales {#channel-mapping}

Las campañas de Dynamics se agrupan en los canales de marketing personalizados mediante el campo Tipo de campaña . Pueden cambiarse en el menú Personalizaciones de Dynamics.

Los valores del menú Tipo de campaña se extraen del [!DNL Marketo Measure] Aplicación. **[!UICONTROL Mi cuenta]** > **[!UICONTROL Configuración]** > **[!UICONTROL Canales sin conexión]**.

Para cada tipo de campaña, se puede asignar a una combinación de canal y subcanal para que cada punto de contacto que se derive de la campaña tenga el canal y subcanal asignados correctamente.

![](assets/9.png)

![](assets/10.png)

## Fecha de sincronización de campaña {#campaign-sync-date}

Esto no está disponible para los clientes de Dynamics

## Preguntas frecuentes {#faq}

**¿Podemos habilitar puntos de contacto en listas de marketing o solo en campañas en Dynamics?**

Puede habilitar una lista de marketing, pero debe estar relacionada con una campaña, ya que la opción para sincronizar una lista de marketing permanece en la campaña.

**¿Podemos usar Respuestas de campaña Y Listas de marketing en una campaña?**

Sí.
