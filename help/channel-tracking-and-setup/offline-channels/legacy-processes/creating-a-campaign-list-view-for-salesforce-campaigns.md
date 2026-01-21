---
unique-page-id: 18874718
description: Creando una vista de lista de campaña para  [!DNL Salesforce Campaigns] - [!DNL Marketo Measure]
title: 'Creación de una vista de lista de campañas para campañas de  [!DNL Salesforce] '
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
feature: Channels
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 5%

---

# Creando una vista de lista de campaña para [!DNL Salesforce] campañas {#creating-a-campaign-list-view-for-salesforce-campaigns}

Aprenda a crear una vista de lista para las campañas que desee sincronizar con los puntos de contacto del comprador.

>[!NOTE]
>
>Este artículo trata sobre un proceso obsoleto. Recomendamos a los usuarios que utilicen el [proceso en la aplicación nuevo y mejorado](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

La vista de lista de campañas que se puede crear le permite tener una ubicación de &quot;visita&quot; para ver y administrar los campos &quot;Tipo&quot; y &quot;Habilitar puntos de contacto del comprador&quot; a fin de garantizar que cada una de sus campañas de [!DNL Salesforce] que informan a sus canales de marketing sin conexión esté configurada correctamente.

1. Vaya a la pestaña Campañas en [!DNL Salesforce] y cree una nueva vista de lista
1. Asigne un nombre a la vista &quot;Campañas que sincronizar con [!DNL Marketo Measure]&quot;.
1. Queremos que esta lista muestre solamente las campañas que queremos sincronizar con [!DNL Marketo Measure], así que necesitamos un par de filtros:

   * **Escriba** [ES IGUAL QUE] &#39;Todos los tipos de campaña que hemos asignado a sus canales sin conexión&#39;. Consulte su plan de implementación o la pestaña Canales sin conexión en [!DNL Marketo Measure] ([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} -> Mi cuenta -> Configuración -> Canales sin conexión). Puede seleccionar los tipos que desee (los que estén asignados a un canal de marketing sin conexión) mediante el icono de lupa.

      * Elija 3 tipos como máximo para cada filtro. Hay un límite de caracteres que puede tener en un campo de filtro. Comience con 3 tipos por filtro y añada filas adicionales de filtros &quot;Tipo&quot; si es necesario.

   * **Fecha de creación** [MAYOR O IGUAL QUE] tu fecha de inicio de [!DNL Marketo Measure]. Puede encontrar la fecha de inicio en el panel ROI de la aplicación [!DNL Marketo Measure]. Solo tiene que seleccionar &quot;Desde la fecha de creación&quot; en el intervalo de fechas del guión y se mostrará su fecha de inicio.
   * **&#42;Tipo de registro&#42;**: para poder realizar modificaciones en la vista de lista, debe agregar un filtro para el tipo de registro. Cada registro de campaña que necesite editar debe ser del mismo tipo de registro.

1. Edite los campos seleccionados para mostrarlos en la vista de lista. La configuración completa de la vista de lista debería ser similar al ejemplo siguiente:

   Esta vista permite ver las campañas y editar los campos &quot;Tipo&quot; y &quot;Habilitar puntos de contacto del comprador&quot; si es necesario. A medida que crea nuevas campañas que deben sincronizarse con [!DNL Marketo Measure], aparecerán en esta vista y puede administrar toda la configuración de dichas campañas desde la lista.

   Para realizar ediciones en línea desde la vista de lista, debe asegurarse de que lo siguiente también sea verdadero en la configuración de [!DNL Salesforce]:

   * **[!UICONTROL Configuración]** > **[!UICONTROL Interfaz de usuario]** > **[!UICONTROL Habilitar la edición en línea]**
   * También es necesario activar las listas mejoradas marcadas (justo debajo del cuadro para la edición en línea)
   * Asegúrese de tener permisos en los campos

>[!MORELIKETHIS]
>
>[Resolución de problemas comunes con la edición en línea de la vista de lista](http://help.salesforce.com/articleView?id=000003911&language=en_US&type=1){target="_blank"}
