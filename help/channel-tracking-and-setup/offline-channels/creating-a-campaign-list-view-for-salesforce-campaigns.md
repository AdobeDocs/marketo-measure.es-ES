---
unique-page-id: 18874718
description: Creación de una vista de lista de campañas para [!DNL Salesforce Campaigns] - [!DNL Marketo Measure] - Documentación del producto
title: Creación de una vista de lista de campañas para [!DNL Salesforce] Campañas
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# Creación de una vista de lista de campañas para [!DNL Salesforce] Campañas {#creating-a-campaign-list-view-for-salesforce-campaigns}

Aprenda a crear una vista de lista para las campañas que desee sincronizar con los puntos de contacto del comprador.

La vista de lista de campañas que se puede crear le permite tener una ubicación de &quot;acceso&quot; para ver y administrar los campos &quot;Tipo&quot; y &quot;Habilitar puntos de contacto del comprador&quot; para asegurarse de que cada uno de sus [!DNL Salesforce] las campañas que informan a los canales de marketing sin conexión están configuradas correctamente.

1. Vaya a la pestaña Campañas en [!DNL Salesforce] y crear una nueva vista de lista
1. Asigne un nombre a la vista &quot;Campañas para sincronizar con [!DNL Marketo Measure].&quot;
1. Queremos que esta lista solo muestre las campañas con las que queremos sincronizar [!DNL Marketo Measure] necesitamos un par de filtros:

   * **Tipo** [IGUAL A] &quot;Todos los tipos de campaña que hemos asignado a sus canales sin conexión&quot;. Consulte el plan de implementación o la pestaña Canales sin conexión en [!DNL Marketo Measure] ([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} -> Mi cuenta -> Configuración -> Canales sin conexión). Puede seleccionar los tipos que desee (los que están asignados a un canal de marketing sin conexión) mediante el icono de lupa.

      * Elija un máximo de 3 tipos para cada filtro. Puede tener un límite de caracteres en un campo de filtro. Comience con 3 tipos por filtro y añada filas adicionales de filtros &quot;Tipo&quot; si es necesario.
   * **Fecha de creación** [BUENO O IGUAL] your [!DNL Marketo Measure] fecha de inicio. Puede encontrar la fecha de inicio en el panel de ROI dentro del [!DNL Marketo Measure] Aplicación. Simplemente seleccione &quot;Desde fecha de creación&quot; en el intervalo de fechas del guión y mostrará la fecha de inicio.
   * **&#42;Tipo de registro&#42;** - Para realizar ediciones en la vista de lista, debe agregar un filtro para el tipo de registro. Cada registro de campaña que necesite editar debe ser el mismo Tipo de registro.


1. Edite los campos Seleccionados para mostrarlos en la vista de lista. La configuración completa de la vista de lista debería ser similar al ejemplo siguiente:

   Esta vista le permite ver sus campañas y editar los campos &quot;Tipo&quot; y &quot;Habilitar puntos de contacto del comprador&quot; si es necesario. A medida que crea nuevas campañas que deben sincronizarse con [!DNL Marketo Measure], aparecerán en esta vista y podrá administrar toda la configuración de esas campañas directamente desde la lista.

   Para realizar ediciones en línea desde la vista de lista, debe asegurarse de que lo siguiente también sea cierto dentro de su [!DNL Salesforce] configuración:

   * **[!UICONTROL Configuración]** > **[!UICONTROL Interfaz de usuario]** > **[!UICONTROL Habilitar edición en línea]**
   * También es necesario activar las listas mejoradas marcadas (justo debajo de la casilla para la edición en línea)
   * Asegúrese de tener permisos para los campos

>[!MORELIKETHIS]
>
>[Solución de problemas comunes con la edición en línea de la vista de lista](http://help.salesforce.com/articleView?id=000003911&amp;language=en_US&amp;type=1){target="_blank"}
