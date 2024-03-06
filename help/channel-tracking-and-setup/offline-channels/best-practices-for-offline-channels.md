---
description: 'Prácticas recomendadas para canales sin conexión: [!DNL Marketo Measure]'
title: Prácticas recomendadas para canales sin conexión
exl-id: 71c50614-8d5b-469f-bc02-3cc489464a4e
feature: Channels
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '1056'
ht-degree: 4%

---

# Prácticas recomendadas para canales sin conexión {#best-practices-for-offline-channels}

## Información general {#overview}

Para tener precisión [!DNL Marketo Measure] En los informes de, los canales de marketing deben estar correctamente configurados. El &#39;[!UICONTROL Canal de marketing]El campo muestra el grupo de nivel superior de tácticas de marketing a las que puede pertenecer un punto de contacto (por ejemplo, eventos, seminarios web, distribución de contenido, etc.).

Existen dos aspectos para configurar los canales de marketing: en línea y sin conexión. Este documento se centra en la [!DNL Marketo Measure] prácticas recomendadas para configurar y mantener sus canales sin conexión y cómo se sincronizan con [!DNL Marketo Measure] a través de campañas CRM.

Los canales sin conexión tienen dos aspectos clave:

1. Asignación de canales sin conexión, que es el marco que indica a [!DNL Marketo Measure] a qué canal y subcanal pertenecen el punto de contacto sin conexión
1. Sincronización de campañas sin conexión, que es la creación de los puntos de contacto sin conexión

Los puntos de contacto sin conexión se crean a partir de una campaña de CRM y están pensados para rastrear cualquier interacción de marketing que no se pueda rastrear digitalmente mediante el [!DNL Marketo Measure] JavaScript que se implementa en las páginas del sitio web. Cuando una campaña de CRM se sincroniza con [!DNL Marketo Measure], se crean puntos de contacto para los miembros de campaña definidos dentro de la campaña.

El valor &quot;Canal de marketing&quot; para estos puntos de contacto se basa en el campo &quot;Tipo&quot; de la campaña. La asignación de &quot;Tipo de campaña de CRM&quot; a &quot;Canal de marketing&quot; y &quot;Subcanal&quot; se administra en la pestaña &quot;Canales sin conexión&quot; de su [!DNL Marketo Measure] Configuración de cuenta. Garantizar que la asignación del canal sin conexión sea precisa y esté actualizada garantizará que los datos del punto de contacto sin conexión se atribuyan a los canales y subcanales de marketing correctos dentro de su [!DNL Marketo Measure] Informes.

## Práctica recomendada | Asignación de canales sin conexión {#best-practice-offline-channel-mapping}

Tanto si asigna los canales sin conexión por primera vez como si solo los revisa para comprobar su precisión, tenga en cuenta las siguientes prácticas recomendadas.

* Crear un marco de trabajo deliberado para los canales sin conexión
   * Dedique un tiempo a pensar en la organización de sus campañas de marketing y en cómo encajan en el marco de trabajo de [!DNL Marketo Measure]. Determine qué canales y subcanales deben representarse en sus canales sin conexión y qué tipos de campañas de CRM diferencian esos canales entre sí
* Trabaje para utilizar primero los valores &quot;Type&quot; de la campaña de CRM actual
   * Los canales sin conexión se definen mediante la campaña de CRM &quot;Tipo&quot;; sin embargo, es posible que sea necesario crear un valor &quot;Tipo&quot; de campaña de CRM personalizado para dar cabida a los valores ideales de canal sin conexión y subcanal. Los valores &quot;Tipo&quot; de campaña de CRM personalizada ideal deben llevar la convención de nombres que se muestra a continuación:
      * CANAL: SUBCANAL
      * Ejemplo: Evento - Feria
      * Esto garantiza que la asignación al nivel de subcanal sea lo más fácil y limpia posible
* Un subcanal solo se puede asignar a un tipo de campaña de CRM
   * Se pueden asignar varios &quot;tipos&quot; de campañas CRM a un solo canal, pero solo se puede asignar un &quot;tipo&quot; de campaña CRM a cada subcanal dentro de cada canal
* Solo los &quot;Tipos&quot; de campañas de CRM SIN CONEXIÓN deben asignarse a canales sin conexión, ya que solo las campañas sin conexión deben sincronizarse con [!DNL Marketo Measure] para crear puntos de contacto:
   * Los &quot;tipos&quot; de campaña de CRM en LÍNEA deben asignarse a una [!UICONTROL Canal de marketing] = &quot;NULL&quot;. Este valor se recomienda, ya que actúa como un &quot;indicador rojo&quot; que indica que sus canales sin conexión se han revisado y que cualquier &quot;tipo&quot; de campaña de CRM asignado a &quot;NULL&quot; es un &quot;tipo&quot; EN LÍNEA y no se debe sincronizar con [!DNL Marketo Measure]. Los puntos de contacto relacionados con los &quot;tipos&quot; de campañas de CRM en línea ya se rastrearían mediante [!DNL Marketo Measure] Funcionalidad y canales en línea. La sincronización de estas campañas corre el riesgo de &quot;duplicar&quot; puntos de contacto/recuento doble

## Práctica recomendada | Sincronización de campañas sin conexión {#best-practice-offline-campaign-sync}

* Asegúrese de que el campo Tipo sea preciso en cada campaña de CRM
   * &quot;Tipo&quot; determina el canal de marketing y el subcanal para cualquier punto de contacto procedente de la campaña una vez sincronizados
* Si utiliza el método de sincronización de campaña basado en CRM (habilitar puntos de contacto del comprador) o el [!DNL Marketo Measure] Método de sincronización basado en la aplicación (sincronización de campaña personalizada dentro de &#39;[!UICONTROL Campañas]&#39; de su [!UICONTROL Marketo Measure] Configuración de cuenta), los puntos de contacto sin conexión solo deben crearse si el miembro de la campaña tuvo una participación sin conexión real con la campaña y con su marca:
   * Para canales sin conexión como eventos o seminarios web: el seguimiento de los &quot;registros&quot; se suele realizar mediante envíos de formularios en el sitio web y [!DNL Marketo Measure] Funcionalidad en línea. Por lo tanto, los miembros de la campaña con el estado &quot;Registrados&quot; no deben recibir un punto de contacto sin conexión de la campaña para evitar el recuento doble. Los puntos de contacto sin conexión solo deben ser representativos de la &quot;asistencia&quot; al evento o al seminario web.
   * Algunos canales sin conexión, como la distribución de contenido, son más directos, ya que cada miembro de la campaña tiene el mismo estado &quot;respondido&quot; que representa que efectivamente respondió a la campaña, en este caso, descargue contenido en un sitio de terceros y, por lo tanto, debe recibir un punto de contacto sin conexión
* Cuando se utiliza el método de sincronización de campaña personalizada en la variable [!DNL Marketo Measure] En la aplicación, asegúrese de que el campo &quot;Fecha del punto de contacto&quot; se basa en el campo de fecha del miembro de la campaña o de la campaña que indica mejor cuándo se produjo realmente la interacción del punto de contacto
* Utilice el botón &quot;Actualización masiva de fecha de punto de contacto&quot; si necesita anular la &quot;Fecha de punto de contacto&quot; para cualquiera de los puntos de contacto sin conexión procedentes de una campaña CRM. La &quot;Fecha del punto de contacto&quot; debe ser lo más precisa posible para garantizar que el punto de contacto tenga la &quot;Posición del punto de contacto&quot; más precisa posible y, por lo tanto, la cantidad adecuada de crédito de atribución

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Una vez configurada inicialmente, la configuración del canal sin conexión sigue creando puntos de contacto sin conexión en consecuencia. Como práctica recomendada, le recomendamos que revise la configuración sin conexión al menos dos veces al año. Esto garantiza unos datos de punto de contacto del comprador precisos y precisos.

Además, si realiza cambios en la administración o los procesos de Campaign, debe asegurarse de actualizar la [!DNL Marketo Measure] Asignación de canales sin conexión o proceso de sincronización.

Cambios que podrían poner a su equipo en déclencheur para realizar actualizaciones en la configuración del canal sin conexión en [!DNL Marketo Measure] puede incluir:

* &quot;Tipos&quot; de campañas CRM creadas o editadas
* Se ha creado o editado el estado del miembro de la campaña
* Si utiliza el método de sincronización de campaña de CRM a través del campo &quot;Habilitar puntos de contacto del comprador&quot;, asegúrese de que este campo se revise y actualice para cada campaña de CRM que se cree. Si se omite este campo, no habrá ningún dato de punto de contacto sin conexión relacionado
* Si encuentra puntos de contacto sin conexión desde una campaña CRM que parecen ser puntos de contacto en línea (Canal de marketing = NULL), asegúrese de que la campaña CRM relacionada se revise y la sincronización esté deshabilitada

Si su equipo ha experimentado recientemente cualquiera de las situaciones anteriores, [!DNL Marketo Measure] le recomienda que revise su asignación de canales sin conexión y sus campañas sin conexión para realizar los cambios correspondientes y asegurarse de que se sincronizan correctamente.

>[!MORELIKETHIS]
>
>* [Configuración de canal sin conexión](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [Sincronización de campaña personalizada: sincronización de aplicación](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [Sincronización de campañas sin conexión: sincronización CRM](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)
>* [Campaign y miembros de Campaign sin conexión: sincronización de CRM](/help/channel-tracking-and-setup/offline-channels/legacy-processes/campaigns-and-campaign-members.md)
>* [Fechas de sincronización de Campaign: sincronización de CRM](/help/channel-tracking-and-setup/offline-channels/legacy-processes/campaign-sync-dates.md)
>* [Configuraciones para varios tipos de registros de campaña](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)
>* [Creación de una vista de lista de campaña](/help/channel-tracking-and-setup/offline-channels/legacy-processes/creating-a-campaign-list-view-for-salesforce-campaigns.md)
>* [Sincronización de datos históricos](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-historical-data.md)
