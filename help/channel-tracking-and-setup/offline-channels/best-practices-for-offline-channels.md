---
description: Prácticas recomendadas para canales sin conexión [!DNL Marketo Measure] - Documentación del producto
title: Prácticas recomendadas para canales sin conexión
exl-id: 71c50614-8d5b-469f-bc02-3cc489464a4e
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1057'
ht-degree: 0%

---

# Prácticas recomendadas para canales sin conexión {#best-practices-for-offline-channels}

## Resumen {#overview}

Para tener precisión [!DNL Marketo Measure] informes, los canales de marketing deben estar correctamente configurados. El[!UICONTROL Canal de marketing]El campo muestra el grupo de nivel más alto de tácticas de marketing al que puede pertenecer un punto de contacto (por ejemplo, eventos, seminarios web, distribución de contenido, etc.).

Existen dos aspectos para configurar los canales de marketing: en línea y sin conexión. Este documento se centrará en el [!DNL Marketo Measure] recomendaciones de prácticas recomendadas para configurar y mantener los canales sin conexión y cómo se sincronizan con [!DNL Marketo Measure] mediante campañas CRM.

Los canales sin conexión tienen dos aspectos clave:

1. Asignación de canales sin conexión, que es el marco que indica [!DNL Marketo Measure] a qué canal y subcanal pertenecen el punto de contacto sin conexión
1. Sincronización de campañas sin conexión, que es la creación de puntos de contacto sin conexión

Los puntos de contacto sin conexión se crean a partir de una campaña de CRM y están pensados para rastrear cualquier interacción de marketing de la que no se pueda realizar un seguimiento digital a través del [!DNL Marketo Measure] JavaScript que se implementa en las páginas del sitio web. Cuando se sincroniza una campaña de CRM con [!DNL Marketo Measure], los puntos de contacto se crean para los miembros de campaña definidos dentro de la campaña.

El valor &quot;Canal de marketing&quot; para estos puntos de contacto se basa en el campo &quot;Tipo&quot; de la campaña. La asignación de &quot;Tipo de campaña de CRM&quot; a &quot;Canal de marketing&quot; y &quot;Subcanal&quot; se administra en la pestaña &quot;Canales sin conexión&quot; de su [!DNL Marketo Measure] Configuración de la cuenta. Garantizar que la asignación de canales sin conexión sea precisa y esté actualizada garantizará que los datos de puntos de contacto sin conexión se atribuyan a los canales de marketing y subcanales correctos dentro de los [!DNL Marketo Measure] Informes.

## Práctica recomendada | Asignación de canales sin conexión {#best-practice-offline-channel-mapping}

Tanto si asigna los canales sin conexión por primera vez como si solo los revisa para comprobar la precisión, tenga en cuenta las siguientes prácticas recomendadas.

* Crear un marco deliberado para los canales sin conexión
   * Tómese un tiempo para pensar en la organización de sus campañas de marketing y en cómo encajan en el [!DNL Marketo Measure] marco. Determine qué canales y subcanales deben representarse en sus canales sin conexión, así como qué tipos de campaña de CRM diferencian entre sí
* Trabaje primero para utilizar los valores &quot;Type&quot; de su campaña de CRM actual.
   * Los canales sin conexión están definidos por el &quot;Tipo&quot; de la campaña de CRM, pero puede que sea necesario crear el valor &quot;Tipo&quot; de la campaña de CRM personalizada para dar cabida a los valores ideales de los canales sin conexión y los subcanales. Los valores &quot;Tipo&quot; de campaña de CRM personalizado ideal deben llevar la convención de nombres que se muestra a continuación:
      * CANAL - SUBCANAL
      * Ejemplo: Evento: Presentación
      * Esto garantiza que la asignación al nivel de Subcanal sea lo más sencilla y limpia posible
* Solo se puede asignar un subcanal a un &quot;tipo&quot; de campaña de CRM
   * Se pueden asignar varios tipos de campaña de CRM a un solo canal, pero solo se puede asignar un &quot;tipo&quot; de campaña de CRM a cada subcanal dentro de cada canal
* Solo los &quot;tipos&quot; de campaña de sin conexión de CRM deben asignarse a canales sin conexión, ya que solo las campañas sin conexión se deben sincronizar con [!DNL Marketo Measure] para crear touchpoints:
   * Los &quot;tipos&quot; de campaña de CRM ONLINE deben asignarse a un [!UICONTROL Canal de marketing] = &quot;NULL&quot;. Se recomienda este valor, ya que actúa como un &quot;indicador rojo&quot; que indica que los canales sin conexión se han revisado y que cualquier campaña de CRM &quot;Tipo&quot; asignada a &quot;NULL&quot; es un &quot;Tipo&quot; en línea y no debe sincronizarse con [!DNL Marketo Measure]. Los puntos de contacto relacionados con los &quot;tipos&quot; de la campaña de CRM en línea ya se seguirían mediante [!DNL Marketo Measure] Funcionalidad y canales en línea. Al sincronizar estas campañas, se corre el riesgo de que se dupliquen los puntos de contacto o se cuente dos veces

## Práctica recomendada | Sincronización de campañas sin conexión {#best-practice-offline-campaign-sync}

* Asegúrese de que el campo &quot;Tipo&quot; sea preciso en cada campaña de CRM
   * El tipo determina el canal de marketing y el subcanal para cualquier punto de contacto procedente de la campaña una vez sincronizada
* Si se utiliza el método de sincronización de campañas basado en CRM (Habilitar puntos de contacto de comprador) o [!DNL Marketo Measure] Método de sincronización basado en aplicaciones (sincronización de campaña personalizada dentro de la &#39;[!UICONTROL Campañas]la pestaña &#39; del [!UICONTROL Marketo Measure] Configuración de cuenta), los puntos de contacto sin conexión solo deben crearse si el miembro de la campaña tuvo una participación sin conexión real con la campaña y la marca:
   * Para canales sin conexión como eventos o seminarios web: los &quot;registros&quot; se suelen rastrear mediante envíos de formularios en el sitio web y [!DNL Marketo Measure] Funcionalidad en línea. Por lo tanto, los miembros de la campaña con un estado &quot;Registrado&quot; no deben recibir un punto de contacto sin conexión de la campaña para evitar el recuento doble. Los puntos de contacto sin conexión solo deben ser representativos de la &quot;asistencia&quot; al evento o al seminario web.
   * Algunos canales sin conexión, como la distribución de contenido, generalmente son más sencillos, ya que cada miembro de la campaña tiene el mismo estado &quot;respondido&quot; que representa que sí respondieron a la campaña; en este caso, descargue contenido en un sitio de terceros y, por lo tanto, debe recibir un punto de contacto sin conexión
* Al utilizar el método de sincronización de campaña personalizada en la variable [!DNL Marketo Measure] Aplicación, asegúrese de que el campo &quot;Fecha de punto de contacto&quot; se basa en el campo de fecha de la campaña o del miembro de la campaña que indica más cuándo se produjo realmente la interacción de punto de contacto
* Aproveche el botón &quot;Fecha de punto de contacto de actualización masiva&quot; si necesita anular la &quot;Fecha de punto de contacto&quot; para cualquiera de los puntos de contacto sin conexión procedentes de una campaña de CRM. &quot;Fecha de punto de contacto&quot; debe ser lo más precisa posible para garantizar que el punto de contacto tenga la &quot;Posición de punto de contacto&quot; más precisa posible y, por lo tanto, la cantidad adecuada de crédito de atribución

## Práctica recomendada para mantenimiento {#best-practice-for-maintenance}

Una vez configurada inicialmente, la configuración de canal sin conexión seguirá creando puntos de contacto sin conexión en consecuencia. Como práctica recomendada, le recomendamos que revise la configuración sin conexión al menos dos veces al año. Esto garantizará la limpieza y precisión de los datos de puntos de contacto del Comprador.

Además, si realiza cambios en la administración o los procesos de Campaign, debe asegurarse de que está actualizando la [!DNL Marketo Measure] Proceso de sincronización o asignación de canales sin conexión.

Cambios que podrían hacer que su equipo tenga déclencheur para actualizar la configuración de canales sin conexión en [!DNL Marketo Measure] puede incluir:

* &quot;Tipo(s)&quot; de campaña de CRM creada o editada
* &quot;Estado&quot; del miembro de la campaña creado o editado
* Si utiliza el método CRM Campaign Sync mediante el campo &quot;Habilitar puntos de contacto de comprador&quot;, asegúrese de que este campo se revise y actualice para cada campaña de CRM que se cree. Si se omite este campo, no habrá datos de puntos de contacto sin conexión relacionados
* Si encuentra algún punto de contacto sin conexión de una campaña de CRM que parezca ser un punto de contacto en línea (Canal de marketing = NULL), asegúrese de que la campaña de CRM relacionada esté revisada y de que la sincronización esté deshabilitada

Si su equipo ha experimentado recientemente cualquiera de las situaciones anteriores, [!DNL Marketo Measure] recomienda revisar la asignación de canales sin conexión y las campañas sin conexión para realizar los cambios correspondientes y asegurarse de que se sincronizan correctamente.

>[!MORELIKETHIS]
>
>* [Configuración de canales sin conexión](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [Sincronización de campañas personalizada: Sincronización de aplicaciones](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [Sincronización de campañas sin conexión: sincronización con CRM](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)
>* [Miembros de campaña y campañas sin conexión: sincronización de CRM](/help/channel-tracking-and-setup/offline-channels/campaigns-and-campaign-members.md)
>* [Fechas de sincronización de campaña - Sincronización de CRM](/help/channel-tracking-and-setup/offline-channels/campaign-sync-dates.md)
>* [Configuraciones para varios tipos de registros de campaña](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)
>* [Creación de una vista de lista de campañas](/help/channel-tracking-and-setup/offline-channels/creating-a-campaign-list-view-for-salesforce-campaigns.md)
>* [Sincronización de datos históricos](/help/channel-tracking-and-setup/offline-channels/syncing-historical-data.md)

