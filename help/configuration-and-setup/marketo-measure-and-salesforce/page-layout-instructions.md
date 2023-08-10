---
unique-page-id: 18874799
description: 'Instrucciones de diseño de página: [!DNL Marketo Measure] - Documentación del producto'
title: Instrucciones de diseño de página
exl-id: 627377f0-d0cf-448c-a7b5-7eb5634b9627
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 7%

---

# Instrucciones de diseño de página {#page-layout-instructions}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero sigue viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

Para ver fácilmente [!DNL Marketo Measure] , se recomienda actualizar los diseños de página para el [!UICONTROL Cuenta], [!UICONTROL Contacto], [!UICONTROL Posible cliente], [!UICONTROL Oportunidad], y [!UICONTROL Campaign] Objetos. Las instrucciones se desglosan para cada Diseño de página de objeto a continuación.

Para empezar, primero vaya a su [!DNL Salesforce] Configure las opciones de y busque [!UICONTROL Personalizar] pestaña.

## Objeto de campaña {#campaign-object}

Recomendamos añadir el [!DNL Marketo Measure] a la campaña de SFDC solo para su zona protegida. Los campos se pueden utilizar para probar la generación de puntos de contacto. En producción, se recomienda añadir únicamente la variable [!DNL Marketo Measure] Botón Fecha de punto de contacto de actualización masiva. No se recomienda añadir el [!DNL Marketo Measure] a producción, ya que puede crear reglas de reglas de sincronización de Campaign.

1. En la opción Generar, seleccione **[!UICONTROL Campañas]**.

1. Clic **[!UICONTROL Diseños de página]**.

   ![](assets/1-1.jpg)

1. Clic **[!UICONTROL Editar]** situado junto al diseño de página que desee actualizar.

   ![](assets/2-1.jpg)

1. Dentro de [!UICONTROL campos] , seleccione la opción **[!UICONTROL Activar puntos de contacto del comprador]** y arrástrelo a cualquier lugar de la página que desee. A continuación, añada el **[!UICONTROL Fecha de inicio de Touchpoint]** y **[!UICONTROL Fecha de finalización de Touchpoint]** campos.

   ![](assets/3-2.png)

1. A continuación, en la parte superior de la página, haga clic en el botón &quot;[!UICONTROL Botones]&quot; en el menú búsqueda rápida.

1. Arrastre el **[!UICONTROL Fecha de punto de contacto de actualización masiva]** a la sección de botones personalizados.

   ![](assets/4-1.jpg)

1. Clic **[!UICONTROL Guardar]**.

   >[!NOTE]
   >
   >Si utiliza varios tipos de registros de Campaign, seleccione los valores de la lista de selección para **[!UICONTROL Activar puntos de contacto del comprador]** será necesario actualizar el campo. Consulte la [este artículo](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md) para obtener instrucciones.

## Leads {#leads}

1. En la opción Generar, seleccione **[!UICONTROL Posibles clientes]**.

1. Clic **[!UICONTROL Diseños de página]**.

1. Clic **[!UICONTROL Editar]** situado junto al diseño de página que desee actualizar. Ten en cuenta que varios diseños de página pueden contener las secciones Puntos de contacto del comprador.

1. Haga clic en la opción de página VisualForce de la izquierda en el menú de búsqueda rápida.

1. Cree una nueva sección y asígnele el nombre &quot;Puntos de contacto del comprador&quot;.

   >[!NOTE]
   >
   >Seleccione el formato &quot;una columna&quot; para cada una de estas secciones.

1. Arrastre el **[!UICONTROL Lista relacionada con posibles clientes de Marketo Measure]** Página de VisualForce en la sección de diseño de página.

   ![](assets/5-1.png)

1. Haga clic en la llave dentro de la [!DNL VisualForce] y cambie la altura a 100 y habilite las barras de desplazamiento.

1. En el menú, seleccione la opción [!UICONTROL Canvas Apps] y cree una nueva sección llamada &quot;Marketo Measure Insights&quot; debajo de los puntos de contacto [!DNL VisualForce] sección que acaba de crear.

   >[!NOTE]
   >
   >Seleccione el formato &quot;una columna&quot; para cada una de estas secciones.

1. Arrastre el [!DNL Marketo Measure Insights] Canvas App a esa sección recién creada. Clic **Guardar**. A veces es necesario guardar primero el diseño de la página antes de soltarlo en la aplicación de lienzo porque Salesforce no lo reconoce instantáneamente. Por lo tanto, después de crear la nueva sección, guarde el diseño de página y vuelva a editarlo para arrastrar la aplicación de lienzo dentro de esa sección. Esto se aplica a todos los objetos.

   >[!NOTE]
   >
   >Para el [!DNL Marketo Measure Insights] Canvas App para funcionar correctamente, [Los permisos de deben configurarse correctamente](/help/configuration-and-setup/marketo-measure-insights-canvas-app/marketo-measure-insights-configuration.md).

   >[!TIP]
   >
   >La mayoría de los clientes no utilizan los campos que terminan en (FT) o (LC) porque son campos heredados de antes de [!DNL Marketo Measure] Touchpoint existía como un objeto.

Si está aprovechando el [!DNL Marketo Measure] Función ABM, [haga clic aquí para obtener instrucciones adicionales sobre el diseño de la página](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md).

## Contactos {#contacts}

1. En la opción Generar, seleccione **[!UICONTROL Contactos]**.

1. Clic **[!UICONTROL Diseños de página]**.

1. Seleccione el diseño de página que desee editar.

   Vaya a la opción Listas relacionadas del menú de búsqueda rápida y añada **[!UICONTROL Puntos de contacto del comprador]** lista relacionada.

1. Haga clic en el icono de llave inglesa y añada las siguientes columnas en este orden:

   * Punto de contacto del comprador
   * Canal de marketing
   * Origen del punto de contacto
   * Nombre de campaña de anuncios
   * Posición del Touchpoint
   * Fecha de Touchpoint

1. Ordenar Por: Fecha De Punto De Contacto, Ascendente.

   ![](assets/6.jpg)

1. Expanda la opción Botones y deseleccione **[!UICONTROL Nuevo]**.

   ![](assets/7.png)

1. Vuelva a la [!UICONTROL Lista relacionada] en el menú y, a continuación, añada la opción **[!UICONTROL Punto de contacto de atribución del comprador]** lista relacionada.

1. Haga clic en el icono de llave inglesa y añada las siguientes columnas en este orden:

   * Attribution Touchpoint
   * Canal de marketing
   * Oportunidad
   * Nombre de campaña de anuncios
   * Tipo de Touchpoint
   * Posición del Touchpoint
   * % Forma de W de atribución (_Para el modelo de atribución más robusto, como Ruta completa o Personalizado_)
   * Forma de W de ingresos (_Para el modelo de atribución más robusto, como Ruta completa o Personalizado_)
   * Fecha de Touchpoint

1. Ordenar por Touchpoint [!UICONTROL Fecha] > [!UICONTROL Ascendente].

1. Expanda la sección Botones y deseleccione **[!UICONTROL Nuevo]**.

1. Clic **[!UICONTROL Guardar]**.

## Oportunidades {#opportunities}

1. En la opción Generar, seleccione **[!UICONTROL Oportunidades]**.

1. Clic **[!UICONTROL Diseños de página]**.

1. Seleccione el diseño de página que desee editar.

1. Añada el **[!UICONTROL Punto de contacto de atribución del comprador]** Lista relacionada y haga clic en la llave inglesa para añadir las siguientes columnas para Oportunidades:

   * Attribution Touchpoint
   * Canal de marketing
   * Contacto
   * Nombre de campaña de anuncios
   * Tipo de Touchpoint
   * Posición del Touchpoint
   * % Forma de W de atribución (_Para el modelo de atribución más robusto, como Ruta completa o Personalizado_)
   * Forma de W de ingresos (_Para el modelo de atribución más robusto, como Ruta completa o Personalizado_)
   * Fecha de Touchpoint

1. Ordenar por [!UICONTROL Fecha de Touchpoint] > [!UICONTROL Ascendente].

1. Anular selección **[!UICONTROL Nuevo]** dentro de [!UICONTROL Botones] sección.

1. Clic **[!UICONTROL Guardar]**.

## Cuentas {#accounts}

1. En la opción Generar, seleccione **[!UICONTROL Cuentas]**.

1. Clic **[!UICONTROL Diseños de página]**.

1. Seleccione el diseño de página que desee editar.

1. Añada el **[!UICONTROL Punto de contacto de atribución del comprador]** Related List y haga clic en la llave inglesa para añadir las siguientes columnas:

   * Attribution Touchpoint
   * Canal de marketing
   * Oportunidad
   * Nombre de campaña de anuncios
   * Tipo de Touchpoint
   * Posición del Touchpoint
   * % Forma de W de atribución (_Para el modelo de atribución más robusto, como Ruta completa o Personalizado_)
   * Forma de W de ingresos (_Para el modelo de atribución más robusto, como Ruta completa o Personalizado_)
   * Fecha de Touchpoint

1. Ordenar por Fecha de punto de contacto > Ascendente.

1. Anular selección **[!UICONTROL Nuevo]** dentro de [!UICONTROL Botones] sección.

1. Clic **[!UICONTROL Guardar]**.

Si está aprovechando el [!DNL Marketo Measure] Función ABM,  [haga clic aquí para obtener instrucciones adicionales sobre el diseño de la página](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md).
