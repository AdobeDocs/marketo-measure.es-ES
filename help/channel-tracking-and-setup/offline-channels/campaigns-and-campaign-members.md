---
unique-page-id: 18874578
description: 'Campañas y miembros de campañas: [!DNL Marketo Measure] - Documentación del producto'
title: Campañas y miembros de campañas
exl-id: e4e2b154-39ac-4295-a541-7fa6112672e3
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 0%

---

# Campañas y miembros de campañas {#campaigns-and-campaign-members}

[!DNL Salesforce] Las campañas están diseñadas para realizar el seguimiento de listas de posibles clientes y contactos asociados a un programa o actividad de marketing. Normalmente han sido seminarios web, registros o visitas individuales, por ejemplo. Los especialistas en marketing pueden seleccionar si una campaña debe recibir o no crédito en un recorrido de punto de contacto.

## Habilitación de puntos de contacto {#enabling-touchpoints}

La variable [!DNL Marketo Measure] [!DNL Salesforce] El paquete incluye un campo denominado &quot;Habilitar puntos de contacto de comprador&quot; en el objeto de campaña. Una vez que el campo se haya agregado a la presentación de la página, aparecerá de forma similar a:

![](assets/1.png)

Las opciones disponibles en la lista de selección son:

![](assets/2.png)

* Incluir todos los miembros de la campaña: cada posible cliente o contacto que se agregue a la campaña recibirá un touchpoint asociado a dicha campaña.
* Incluir solo miembros de campaña &quot;Respondidos&quot;: solo los posibles clientes o contactos que tengan un estado de miembro de campaña de &quot;Respondido&quot; recibirán un touchpoint asociado a esa campaña.
* Excluir todos los miembros de la campaña: ninguno de los posibles clientes o contactos recibirá un touchpoint asociado a la campaña.

Tenga en cuenta que los miembros de la campaña deben tener una dirección de correo electrónico asociada a su registro para que [!DNL Marketo Measure] para crear un touchpoint. Sin una dirección de correo electrónico, [!DNL Marketo Measure] no asignará un touchpoint al miembro de la campaña.

## Fechas de sincronización de campañas {#campaign-sync-dates}

Con la instalación del paquete, [!DNL Marketo Measure] también incluye 2 campos de fecha en el objeto Campaign: Fecha de inicio de Touchpoint y Fecha de finalización de Touchpoint.

Estas fechas indican [!DNL Marketo Measure] cuándo se debe iniciar o detener la inclusión de miembros de campaña desde la campaña al recorrido de punto de contacto. Puede establecer una fecha, ambas, o ninguna.

## Caso de uso para la fecha de inicio de Touchpoint {#use-case-for-touchpoint-start-date}

La fecha de inicio se puede utilizar en caso de que se utilice una campaña existente para realizar el seguimiento de posibles clientes y contactos, pero el usuario solo desea empezar a medir una vez que se hayan implantado nuevos sistemas o procesos, por lo que decide establecer una fecha de inicio una vez [!DNL Marketo Measure] debe empezar a rastrear a esos miembros de la campaña.

## Caso de uso para la fecha de finalización de Touchpoint {#use-case-for-touchpoint-end-date}

Si antes de utilizar [!DNL Marketo Measure], utilizó una plataforma de automatización de marketing que rastreaba las interacciones digitales de posibles clientes (envíos de formularios de IE) y, a continuación, cargó esos posibles clientes en una [!DNL Saleforce] Campaign, puede aprovechar el campo Fecha de finalización de Touchpoint . Establecería la fecha de finalización del punto de contacto como fecha de inicio con [!DNL Marketo Measure] y habilite Puntos de contacto del comprador, cada una de estas interacciones digitales de posibles clientes se crearía como un punto de contacto. El motivo por el que configurará la Fecha de finalización de Touchpoint como Fecha de inicio con [!DNL Marketo Measure] es porque, avanzando, seguiremos estas interacciones digitales a través de nuestro javascript.

![](assets/3.png)

## Miembros de campaña {#campaign-members}

Los miembros de la campaña están anidados en [!UICONTROL Campañas]y están relacionados con un posible cliente o contacto. Un posible cliente o un contacto solo se puede añadir una vez a una campaña, lo que puede resultar problemático en función del caso de uso de la campaña. Cuando se sincroniza una campaña, la pertenencia a la campaña se utiliza como actividad de marketing que se coloca en el recorrido de punto de contacto y se trata como un relleno de formulario.

## Estado del punto de contacto del comprador {#buyer-touchpoint-status}

Si está habilitado, [!DNL Marketo Measure] inserta un valor de estado en el miembro de la campaña entre 4 campos diferentes que se incluyen en el paquete instalado: Estado de Touchpoint (posible cliente), Estado de Touchpoint (contacto), Estado de Touchpoint (oportunidad) y Fecha de estado de Touchpoint. Esto ayuda a los clientes a auditar si un punto de contacto se ha creado como punto de contacto de comprador o punto de contacto de atribución de comprador, en función del objeto al que esté relacionado. La fecha de estado de Touchpoint es simplemente la última fecha en que se actualizó el estado en el miembro de la campaña.

![](assets/4.png)

## Fecha de punto de contacto del comprador {#buyer-touchpoint-date}

Con la instalación del paquete, [!DNL Marketo Measure] también incluye un campo en el miembro de la campaña denominado &quot;Fecha de punto de contacto del comprador&quot;. Esto permite al usuario anular la fecha en la que [!DNL Marketo Measure] se utilizaría para la fecha de punto de contacto en el registro de punto de contacto.

Esto puede ser necesario si se carga una lista días/semanas/meses después de que se produzca un evento. Hay maneras de actualizar todos los registros a la vez, como se explica a continuación.

![](assets/5.png)

Para saber si necesita utilizar o no la Fecha de punto de contacto del comprador, estas son las fechas que determinan [!DNL Marketo Measure] según la variable [!UICONTROL Tipo de sincronización] que se selecciona para la campaña.

Si la variable [!UICONTROL Tipo de sincronización] se configura como &quot;Incluir todos los miembros de la campaña&quot;, la prioridad de establecer la fecha del punto de contacto es de arriba abajo:

* Fecha de punto de contacto del comprador
* Fecha de creación del miembro de la campaña

Si la variable [!UICONTROL Tipo de sincronización] se configura como &quot;Incluir solo miembros de campaña &#39;respondidos&#39;&quot;, la prioridad de establecer la fecha del punto de contacto es de arriba abajo:

* Fecha de punto de contacto del comprador
* Primera fecha de respuesta
   * La primera fecha de respuesta se establece automáticamente en cuanto se cambia el estado a &quot;Respondido&quot; y es un valor estándar [!DNL Salesforce] campo que no se puede cambiar

* Fecha de creación del miembro de la campaña

## Fecha de punto de contacto de actualización masiva {#bulk-update-touchpoint-date}

La fecha del punto de contacto de actualización masiva se incluye en la [!DNL Marketo Measure] [!DNL Salesforce] el paquete y el botón deberán añadirse al diseño de la página.

![](assets/6.png)

Si es necesario actualizar un gran número de registros de miembros de Campaign, puede utilizar la variable [!UICONTROL Fecha de punto de contacto de actualización masiva] para editar en masa.

Si hay casos de uso únicos que esta interfaz no cubre, también puede usar la variable [Cargador de datos](https://dataloader.io/){target="_blank"} para exportar los registros, realice el cambio y vuelva a cargar los registros.

Comience por buscar los registros y filtrar los que desea establecer como Fecha de punto de contacto del comprador.

>[!CAUTION]
>
>Hay una búsqueda que no funciona, que se muestra en el siguiente ejemplo. La interfaz de usuario no admite la búsqueda de fechas de punto de contacto del comprador nulas (la siguiente búsqueda no funcionaría):

![](assets/7.png)

Si no necesita utilizar la búsqueda y solo aplica las fechas a cada registro de miembro de la campaña, use la opción[!UICONTROL Incluir todos los registros]&quot; casilla de verificación (ver captura de pantalla abajo), que comprobará todos los registros de todas las páginas.

Seleccione la fecha y la hora en el selector de calendario. Si desea seleccionar la fecha y la hora actuales, haga clic en la fecha y la hora que se muestran junto al selector de calendario.

Una vez configurada la fecha y la hora, haga clic en el **[!UICONTROL Actualizar registros seleccionados]** para aplicar los cambios.

![](assets/8.png)

## Costes de campaña {#campaign-costs}

Obtenga información sobre los costes de campaña [en este artículo](/help/marketing-spend/spend-management/crm-campaign-costs.md).

## Eliminación de miembros de campaña {#campaign-member-removal}

La manera en que [!DNL Marketo Measure] se mantiene al día con los registros eliminados en Salesforce, tanto si se eliminan posibles clientes como cuentas u oportunidades, se trata de ver esos registros en la API y rastrear que una entrada esté marcada como &quot;IsDeleted&quot;. Lamentablemente con los miembros de la campaña, Salesforce introdujo una forma diferente de eliminar a estos miembros de la campaña y en realidad solo están marcados como &quot;eliminados&quot; en lugar de como &quot;eliminados&quot;, por lo que el problema es que los puntos de contacto seguían viviendo en Salesforce, que estaban relacionados con miembros de la campaña eliminados.

Para evitar este problema, [!DNL Marketo Measure] creado un [!DNL Marketo Measure] El objeto Historial y un déclencheur que se rastrearán cada vez que se eliminen miembros de Campaign y, a continuación, eliminarán el punto de contacto correspondiente. **Necesitará [!DNL Marketo Measure] Paquete de Marketing Analytics V6.15 o superior** para utilizar esta función.

>[!CAUTION]
>
>Tenga en cuenta que este déclencheur no rastrea ningún miembro de la campaña que se haya eliminado en el pasado, por lo que esto solo funciona para avanzar. Si necesita eliminar un gran número de puntos de contacto de miembros de campañas anteriores, póngase en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Universidad: Campos de objeto de campaña](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
>
>[[!DNL Marketo Measure] Universidad: Asignación de canales sin conexión](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
