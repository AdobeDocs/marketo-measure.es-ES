---
unique-page-id: 18874578
description: 'Campañas y miembros de la campaña: [!DNL Marketo Measure] - Documentación del producto'
title: Campañas y miembros de campañas
exl-id: e4e2b154-39ac-4295-a541-7fa6112672e3
feature: Channels
source-git-commit: 38c721d10ac33ae85da1d425b6af53b9e3dfd0a1
workflow-type: tm+mt
source-wordcount: '1188'
ht-degree: 1%

---

# Campañas y miembros de campañas {#campaigns-and-campaign-members}

[!DNL Salesforce] Las campañas están pensadas para rastrear listas de posibles clientes y contactos asociados a un programa o una actividad de marketing. Esto ha sido, por lo general, seminarios web, inscripciones o visitas en ambos sitios, por ejemplo. Los especialistas en marketing pueden seleccionar si una campaña debe recibir crédito en un recorrido de punto de contacto o no.

>[!NOTE]
>
>Este artículo trata sobre un proceso obsoleto. Recomendamos a los usuarios que utilicen [proceso en la aplicación nuevo y mejorado](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

## Habilitar puntos de contacto {#enabling-touchpoints}

El [!DNL Marketo Measure] [!DNL Salesforce] El paquete incluirá un campo denominado &quot;Habilitar puntos de contacto del comprador&quot; en el objeto de campaña. Una vez añadido el campo al diseño de página, aparecerá de forma similar a esto:

![](assets/1.png)

Las opciones disponibles en la lista desplegable son las siguientes:

![](assets/2.png)

* Incluir todos los miembros de la campaña: cada posible cliente o contacto añadido a la campaña recibirá un punto de contacto asociado a esa campaña.
* Incluir solo los miembros de la campaña &quot;Respondidos&quot;: solo los posibles clientes o contactos que tengan el estado de miembro de campaña &quot;Respondido&quot; recibirán un punto de contacto asociado a esa campaña.
* Excluir todos los miembros de la campaña: ninguno de los posibles clientes o contactos recibirá un punto de contacto asociado a esa campaña.

Tenga en cuenta que los miembros de la campaña deben tener una dirección de correo electrónico asociada a su registro para [!DNL Marketo Measure] para crear un punto de contacto. Sin una dirección de correo electrónico, [!DNL Marketo Measure] no asignará ningún punto de contacto al miembro de la campaña.

## Fechas de sincronización de campañas {#campaign-sync-dates}

Con la instalación del paquete, [!DNL Marketo Measure] también incluye 2 campos de fecha en el objeto de campaña: Fecha de inicio del punto de contacto y Fecha de finalización del punto de contacto.

Estas fechas indican [!DNL Marketo Measure] cuándo se debe comenzar o detener la inclusión de miembros de campaña de la campaña en el recorrido de punto de contacto. Puede establecer una fecha, o ambas, o ninguna.

## Caso de uso para la fecha de inicio de Touchpoint {#use-case-for-touchpoint-start-date}

La fecha de inicio se puede utilizar en caso de que se utilice una campaña existente para rastrear posibles clientes y contactos, pero el usuario solo desea comenzar a medir una vez que se han establecido nuevos sistemas o procesos, por lo que decide establecer una fecha de inicio una vez [!DNL Marketo Measure] debería empezar a rastrear a esos miembros de la campaña.

## Caso de uso para la fecha de finalización de Touchpoint {#use-case-for-touchpoint-end-date}

Si antes de usar [!DNL Marketo Measure], ha utilizado una plataforma de automatización de marketing que realiza un seguimiento de las interacciones digitales de los posibles clientes (es decir, los envíos de formularios) y, a continuación, ha cargado dichos posibles clientes en una [!DNL Saleforce] En Campaign, puede aprovechar el campo Fecha de finalización del punto de contacto. Establecería la fecha de finalización del punto de contacto como la fecha de inicio con [!DNL Marketo Measure] y activar los puntos de contacto del comprador, la interacción digital de cada uno de estos posibles clientes se crearía como un punto de contacto. El motivo por el que establecerás la fecha de finalización del punto de contacto en la fecha de inicio [!DNL Marketo Measure] Esto se debe a que, en adelante, rastrearemos estas interacciones digitales a través de nuestro javascript.

![](assets/3.png)

## Miembros de campaña {#campaign-members}

Los miembros de la campaña están anidados en [!UICONTROL Campañas]y están relacionados con un posible cliente o contacto. Un posible cliente o un contacto solo se pueden agregar una vez a una campaña, lo que puede resultar problemático según el caso de uso de la campaña. Cuando se sincroniza una campaña, la pertenencia a la campaña se utiliza como actividad de marketing que se coloca en el recorrido de punto de contacto y se trata como un relleno de formulario.

## Estado de Touchpoint del comprador {#buyer-touchpoint-status}

Si está activado, [!DNL Marketo Measure] insertará un valor de estado en el miembro de la campaña en 4 campos diferentes que se incluyen en el paquete instalado: estado de Touchpoint (posible cliente), estado de Touchpoint (contacto), estado de Touchpoint (oportunidad) y fecha de estado de Touchpoint. Esto ayuda a los clientes a auditar si se ha creado o no un punto de contacto como punto de contacto de comprador o punto de contacto de atribución de comprador, según el objeto con el que esté relacionado. La fecha de estado del punto de contacto es simplemente la última fecha en la que se actualizó el estado en el miembro de la campaña.

![](assets/4.png)

## Fecha de Touchpoint del comprador {#buyer-touchpoint-date}

Con la instalación del paquete, [!DNL Marketo Measure] también incluye un campo en el miembro de la campaña con la etiqueta &quot;Fecha del punto de contacto del comprador&quot;. Esto permite al usuario anular la fecha [!DNL Marketo Measure] utilizaría para la fecha de punto de contacto en el registro de punto de contacto.

Esto podría ser necesario si se cargó una lista días/semanas/meses después de que se produjera un evento. Existen maneras de actualizar todos los registros a la vez, que se explican a continuación.

![](assets/5.png)

Para saber si necesitas utilizar o no la fecha de Touchpoint del comprador, así es como se determinan las fechas [!DNL Marketo Measure] según la variable [!UICONTROL Tipo de sincronización] que se selecciona para la campaña.

Si la variable [!UICONTROL Tipo de sincronización] se establece en &quot;Incluir todos los miembros de la campaña&quot;, la prioridad de establecer la fecha del punto de contacto es de arriba abajo:

* Fecha de Touchpoint del comprador
* Fecha de creación del miembro de campaña

Si la variable [!UICONTROL Tipo de sincronización] se establece en &quot;Incluir solo los miembros de campaña &quot;respondidos&quot;&quot;, la prioridad de establecer la fecha de punto de contacto es de arriba abajo:

* Fecha de Touchpoint del comprador
* Primera fecha de respuesta
   * La primera fecha de respuesta se establece automáticamente en cuanto el estado se cambia a &quot;Respondido&quot; y es un estándar [!DNL Salesforce] campo que no se puede cambiar

* Fecha de creación del miembro de campaña

## Fecha de punto de contacto de actualización masiva {#bulk-update-touchpoint-date}

La fecha del punto de contacto de actualización masiva se incluye en el [!DNL Marketo Measure] [!DNL Salesforce] El paquete y el botón deberán añadirse al diseño de página.

![](assets/6.png)

Si es necesario actualizar un gran número de registros de miembros de la campaña, puede utilizar el [!UICONTROL Fecha de punto de contacto de actualización masiva] para la edición masiva.

Si hay casos de uso únicos que esta interfaz no cubre, también puede utilizar la variable [Cargador de datos](https://dataloader.io/){target="_blank"} para exportar los registros, realice el cambio y vuelva a cargar los registros en.

Comience por buscar los registros y filtrar los que desea establecer como fecha de punto de contacto del comprador.

>[!CAUTION]
>
>Hay una búsqueda que no funciona y que se muestra en el ejemplo siguiente. La IU no admite la búsqueda de fechas de punto de contacto de comprador nulas (la siguiente búsqueda no funcionaría):

![](assets/7.png)

Si no necesita utilizar la búsqueda y aplicar las fechas a cada registro de miembro de la campaña, utilice el icono &quot;[!UICONTROL Incluir todos los registros]&quot; (véase la captura de pantalla siguiente), que comprobará todos los registros de todas las páginas.

Seleccione la fecha y la hora en el selector de calendario. Si desea seleccionar la fecha y la hora actuales, haga clic en la fecha y la hora que se muestran junto al selector de calendario.

Una vez que haya establecido la fecha y la hora, haga clic en **[!UICONTROL Actualizar registros seleccionados]** para aplicar los cambios.

![](assets/8.png)

## Costes de campaña {#campaign-costs}

Obtenga más información sobre los costes de Campaign [en este artículo](/help/marketing-spend/spend-management/crm-campaign-costs.md).

## Eliminación de miembros de campaña {#campaign-member-removal}

La forma en que [!DNL Marketo Measure] sigue el ritmo de los registros eliminados en Salesforce, independientemente de si se eliminan posibles clientes, cuentas u oportunidades, es posible ver esos registros en la API y realizar un seguimiento de que una entrada esté marcada como &quot;IsDeleted&quot;. Desafortunadamente con los miembros de Campaign, Salesforce introdujo una forma diferente de eliminar a estos miembros de Campaign de una campaña y, en realidad, solo están marcados como &quot;eliminados&quot; en lugar de &quot;eliminados&quot;, por lo que el problema es que los puntos de contacto aún vivían en Salesforce que estaban relacionados con los miembros de Campaign eliminados.

Para evitar este problema, [!DNL Marketo Measure] creó un [!DNL Marketo Measure] Un objeto de historial y un déclencheur para rastrear cada vez que se quitan miembros de campaña y luego eliminar el punto de contacto correspondiente. **Necesitará lo siguiente [!DNL Marketo Measure] Paquete de Marketing Analytics V6.15 o superior** para utilizar esta función.

>[!CAUTION]
>
>Tenga en cuenta que este déclencheur no rastrea ningún miembro de la campaña que se eliminó en el pasado, por lo que solo funciona en adelante. Si necesita eliminar un gran número de puntos de contacto de miembros de campañas anteriores, póngase en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] University: Campos de objetos de campaña](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
>
>[[!DNL Marketo Measure] Universidad: Asignación de canales sin conexión](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
