---
description: Guía de campañas de Dynamics y listas de marketing para usuarios de Marketo Measure
title: Listas de marketing y campañas de Dynamics
exl-id: 7b3d4032-5edf-489d-b86b-1e2a5755b258
feature: Microsoft Dynamics
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 3%

---

# Listas de marketing y campañas de Dynamics {#dynamics-campaigns-and-marketing-lists}

>[!NOTE]
>
>Este artículo trata sobre un proceso obsoleto. Recomendamos a los usuarios que utilicen el [proceso en la aplicación nuevo y mejorado](/help/channel-tracking-and-setup/custom-campaign-sync.md){target="_blank"}.

## Campañas {#campaigns}

Las campañas de Dynamics son buenas para rastrear actividades de marketing sin conexión e incluirlas en el recorrido omnicanal. Las campañas deben estar relacionadas con posibles clientes o contactos y pueden acumularse en la campaña a través de respuestas de campaña o listas de marketing.

## Respuestas de campaña {#campaign-responses}

Cuando se agregan posibles clientes o contactos directamente a una campaña, se introducen como un registro de respuesta de campaña.

![Cuando se agregan contactos o posibles clientes directamente a una campaña, se ingresan](assets/dynamics-lists-1.png)

## Habilitar puntos de contacto {#enable-touchpoints}

Para incluir estos registros en el recorrido de punto de contacto, existen algunas opciones para los tipos de respuestas de campaña que se deben sincronizar. En el registro de campaña, debe haber un campo personalizado de la solución instalada con la etiqueta &quot;[!UICONTROL Habilitar puntos de contacto del comprador]&quot;. Si no lo ve, el campo debe añadirse mediante el Editor de formularios.

![Para incluir estos registros en el recorrido de punto de contacto, hay algunos](assets/dynamics-lists-10.png)

Puede seleccionar incluir todos los registros que tengan una respuesta de campaña en la campaña, o solo aquellos con una respuesta de &quot;Interesado&quot; o, de forma predeterminada, no puede incluir las respuestas de campaña. Puede dejar el campo en blanco o elegir excluirlo explícitamente.

[!DNL Marketo Measure] no admite valores de respuesta personalizados.

![Marketo Measure no admite valores de respuesta personalizados.](assets/dynamics-lists-2.png)

Estos son los valores de respuesta de stock para la respuesta de campaña:

![Estos son los valores de respuesta de stock para la respuesta de campaña:](assets/dynamics-lists-3.png)

En función de su selección, estos registros ahora pueden optar a puntos de contacto en el recorrido de posible cliente, contacto u oportunidad. Si cumple los requisitos, aparecerá un punto de contacto de &quot;Dynamics Campaign&quot; en el recorrido.

Una razón por la que una respuesta de campaña podría no mostrarse es porque ya se ha registrado una actividad de primer contacto o contacto de creación de posible cliente para el posible cliente/contacto y la función &quot;PostLC&quot; está deshabilitada o ha alcanzado su número máximo de puntos de contacto.

## Fecha de Touchpoint {#touchpoint-date}

La fecha de punto de contacto de una campaña suele ser la fecha en la que se añadió la respuesta de campaña a la campaña. Se puede anular si se rellena el campo personalizado de la solución instalada con la etiqueta &quot;Fecha de Buyer Touchpoint&quot;. Si no lo ve, el campo debe añadirse mediante el Editor de formularios.

Un ejemplo común de uso de este campo es para eventos en los que se agrega una lista de análisis de distintivos de un evento al CRM días después de que se produzca el evento, de modo que el usuario pueda volver a cambiar la Fecha de Buyer Touchpoint a cuando se produjo el evento.

![Un ejemplo común de uso de este campo es para eventos donde hay una lista](assets/dynamics-lists-4.png)

## Listas de marketing {#marketing-lists}

Las listas de marketing son otra forma de incluir posibles clientes o contactos en un recorrido de marketing. Las listas de marketing son únicas para un grupo de posibles clientes o contactos, lo que significa que el usuario debe seleccionar si su lista es un conjunto de posibles clientes o un conjunto de contactos.

[!DNL Marketo Measure] solo admite listas de marketing estáticas. No se admiten listas de marketing dinámicas porque nuestro procesamiento requiere que comprobemos la fecha de modificación de un registro, pero como una lista dinámica cambia con frecuencia, no hay ninguna fecha de modificación para [!DNL Marketo Measure] con la que comprobar. Esto requeriría una descarga constante del conjunto de datos completo a lo largo del día.

![Marketo Measure solo admite listas de marketing estáticas. No se admite ](assets/dynamics-lists-5.png)

La captura de pantalla anterior es una lista de marketing para posibles clientes. Las listas de marketing están asociadas a campañas y pueden asociarse a varias campañas. A menos que en algún momento cree solamente una lista de mercadotecnia para una campaña, [!DNL Marketo Measure] no recomienda que los clientes usen listas de mercadotecnia para hacer un seguimiento de sus campañas. Es poco probable que la misma lista exacta de posibles clientes/contactos sea apta para puntos de contacto en varias campañas.

## Habilitar puntos de contacto {#enable-touchpoints-1}

Para habilitar una lista de marketing para puntos de contacto, hay una configuración independiente en el registro de campaña con la etiqueta &quot;[!UICONTROL Sincronizar listas de marketing]&quot;, que es un modificador simple de sí/no. Si no lo ve, el campo debe añadirse mediante el Editor de formularios. En el registro de campaña puede ver qué listas de marketing están relacionadas con la campaña para saber cuántas listas está habilitando.

![Para habilitar una lista de marketing para puntos de contacto, hay una configuración independiente](assets/legacy-processes-10.png)

## Fecha de Touchpoint {#touchpoint-date-1}

La fecha de punto de contacto de una lista de marketing suele ser la fecha de creación del ListMember, por lo que la fecha en la que se agregó el posible cliente o contacto a la lista de marketing. Se puede anular si se rellena el campo personalizado de la solución instalada con la etiqueta &quot;Fecha de Buyer Touchpoint&quot;. Si no lo ve, el campo debe añadirse mediante el Editor de formularios.

![La fecha de punto de contacto de una lista de marketing suele ser el ListMember creado](assets/dynamics-lists-6.png)

## Asignación de canales {#channel-mapping}

Las campañas de Dynamics se agrupan en los canales de marketing personalizados mediante el campo Tipo de campaña. Se pueden cambiar en el menú Personalizaciones de Dynamics.

Los valores del menú Tipo de campaña se extraen en la aplicación [!DNL Marketo Measure]. **[!UICONTROL Mi cuenta]** > **[!UICONTROL Configuración]** > **[!UICONTROL Canales sin conexión]**.

Para cada tipo de campaña, se puede asignar a una combinación de canal y subcanal para que cada punto de contacto que se derive de la campaña tenga los canales y subcanales asignados correctamente.

![Para cada tipo de campaña, se puede asignar a un canal y](assets/dynamics-lists-7.png)

![Para cada tipo de campaña, se puede asignar a un canal y](assets/dynamics-lists-8.png)

## Fecha de sincronización de campaña {#campaign-sync-date}

Esto no está disponible para los clientes de Dynamics

## Preguntas frecuentes {#faq}

**¿Se pueden habilitar puntos de contacto en las listas de marketing o solo en las campañas de Dynamics?**

Puede habilitar una lista de marketing, pero debe estar relacionada con una campaña, ya que la opción para sincronizar una lista de marketing reside en la campaña.

**¿Podemos usar las respuestas de campaña y las listas de marketing en una campaña?**

Sí.
