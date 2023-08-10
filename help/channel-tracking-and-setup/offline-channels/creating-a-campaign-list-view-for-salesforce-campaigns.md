---
unique-page-id: 18874718
description: Creación de una vista de lista de campaña para [!DNL Salesforce Campaigns] - [!DNL Marketo Measure] - Documentación del producto
title: Creación de una vista de lista de campañas para campañas de  [!DNL Salesforce]
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 3%

---

# Creación de una vista de lista de campañas para campañas de [!DNL Salesforce] {#creating-a-campaign-list-view-for-salesforce-campaigns}

Aprenda a crear una vista de lista para las campañas que desee sincronizar con los puntos de contacto del comprador.

La vista de lista de campañas que se puede crear le permite tener una ubicación de &quot;acceso&quot; para ver y administrar los campos &quot;Tipo&quot; y &quot;Habilitar puntos de contacto del comprador&quot; para garantizar que cada uno de sus [!DNL Salesforce] las campañas que informan a sus canales de marketing sin conexión se han configurado correctamente.

1. Vaya a la pestaña Campañas en [!DNL Salesforce] y cree una nueva vista de lista
1. Asigne un nombre a la vista &quot;Campañas con las que sincronizar&quot; [!DNL Marketo Measure].&quot;
1. Queremos que esta lista solo muestre las campañas con las que queremos sincronizar [!DNL Marketo Measure] así que necesitamos un par de filtros:

   * **Tipo** [IGUAL A] &quot;Todos los tipos de campaña que hemos asignado a sus canales sin conexión&quot;. Consulte su plan de implementación o la pestaña Canales sin conexión en [!DNL Marketo Measure] ([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} -> Mi cuenta -> Configuración -> Canales sin conexión). Puede seleccionar los tipos que desee (los que estén asignados a un canal de marketing sin conexión) mediante el icono de lupa.

      * Elija 3 tipos como máximo para cada filtro. Hay un límite de caracteres que puede tener en un campo de filtro. Comience con 3 tipos por filtro y añada filas adicionales de filtros &quot;Tipo&quot; si es necesario.

   * **Fecha de creación** [BUENO O IGUAL QUE] su [!DNL Marketo Measure] fecha de inicio. Puede encontrar la fecha de inicio en el panel ROI dentro de la variable [!DNL Marketo Measure] Aplicación. Solo tiene que seleccionar &quot;Desde la fecha de creación&quot; en el intervalo de fechas del guión y se mostrará su fecha de inicio.
   * **&#42;Tipo de registro&#42;** : para realizar ediciones en la vista de lista, debe agregar un filtro para el tipo de registro. Cada registro de campaña que necesite editar debe ser del mismo tipo de registro.

1. Edite los campos seleccionados para mostrarlos en la vista de lista. La configuración completa de la vista de lista debería ser similar al ejemplo siguiente:

   Esta vista permite ver las campañas y editar los campos &quot;Tipo&quot; y &quot;Habilitar puntos de contacto del comprador&quot; si es necesario. A medida que crea nuevas campañas que deben sincronizarse con [!DNL Marketo Measure], aparecerán en esta vista y puede administrar toda la configuración de esas campañas desde la lista.

   Para realizar ediciones en línea desde la vista de lista, debe asegurarse de que lo siguiente también sea verdadero en su [!DNL Salesforce] configuración:

   * **[!UICONTROL Configurar]** > **[!UICONTROL Interfaz de usuario]** > **[!UICONTROL Activar edición en línea]**
   * También es necesario activar las listas mejoradas marcadas (justo debajo del cuadro para la edición en línea)
   * Asegúrese de tener permisos en los campos

>[!MORELIKETHIS]
>
>[Solución de problemas comunes con la edición en línea de vistas de lista](http://help.salesforce.com/articleView?id=000003911&amp;language=en_US&amp;type=1){target="_blank"}
