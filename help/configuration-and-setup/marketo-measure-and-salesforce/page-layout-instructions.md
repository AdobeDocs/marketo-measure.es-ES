---
unique-page-id: 18874799
description: 'Instrucciones de diseño de página: [!DNL Marketo Measure]'
title: Instrucciones de diseño de página
exl-id: 627377f0-d0cf-448c-a7b5-7eb5634b9627
feature: Salesforce
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 69%

---

# Instrucciones de diseño de página {#page-layout-instructions}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en la documentación, pero sigue viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

Para ver fácilmente datos de [!DNL Marketo Measure], se recomienda actualizar los diseños de página para los objetos [!UICONTROL Cuenta], [!UICONTROL Contacto], [!UICONTROL Posible cliente], [!UICONTROL Oportunidad], y [!UICONTROL Campaña]. Las instrucciones se desglosan para cada Diseño de página de objeto siguiente.

Para empezar, primero vaya a sus ajustes de configuración de [!DNL Salesforce] y busque la pestaña [!UICONTROL Personalizar].

## Objeto de campaña {#campaign-object}

Se recomienda añadir el [!DNL Marketo Measure] a la campaña de SFDC solo para su zona protegida. Los campos se pueden utilizar para probar la generación de Touchpoints. En producción, se recomienda solo añadir la variable [!DNL Marketo Measure] Botón Fecha de punto de contacto de actualización masiva. No se recomienda añadir el [!DNL Marketo Measure] a producción, ya que puede crear la regla de sincronización de Campaign.

1. En la opción Generar, seleccione **[!UICONTROL Campañas]**.

1. Haga clic en **[!UICONTROL Diseños de página]**.

   ![](assets/1-1.jpg)

1. Clic **[!UICONTROL Editar]** situado junto al diseño de página que desea actualizar.

   ![](assets/2-1.jpg)

1. Dentro de la opción [!UICONTROL campos], seleccione la opción **[!UICONTROL Habilitar Buyer Touchpoints]** y arrástrela a cualquier lugar de la página que desee. A continuación, añada los campos **[!UICONTROL Fecha de inicio de Touchpoint]** y **[!UICONTROL Fecha de finalización de Touchpoint]**.

   ![](assets/3-2.png)

1. A continuación, en la parte superior de la página, haga clic en la opción &quot;[!UICONTROL Botones]&quot; en el menú búsqueda rápida.

1. Arrastre el botón **[!UICONTROL Fecha de Touchpoint de actualización masiva]** a la sección de botones personalizados.

   ![](assets/4-1.jpg)

1. Haga clic en **[!UICONTROL Guardar]**.

   >[!NOTE]
   >
   >Si utiliza varios tipos de registros de Campaign, debe actualizar los valores de la lista de selección para el **[!UICONTROL Activar puntos de contacto del comprador]** field. Consulte [este artículo](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md) para obtener instrucciones.

## Clientes potenciales {#leads}

1. En la opción Generar, seleccione **[!UICONTROL Posibles clientes]**.

1. Haga clic en **[!UICONTROL Diseños de página]**.

1. Clic **[!UICONTROL Editar]** situado junto al diseño de página que desea actualizar. Tenga en cuenta que varios diseños de página pueden contener las secciones Buyer Touchpoints.

1. Haga clic en la opción de página VisualForce de la izquierda en el menú de búsqueda rápida.

1. Cree una sección y asígnele el nombre &quot;Puntos de contacto del comprador&quot;.

   >[!NOTE]
   >
   >Seleccione el formato &quot;una columna&quot; para cada una de estas secciones.

1. Arrastre la página **[!UICONTROL Lista relacionada con posibles clientes de Marketo Measure]** de VisualForce en la sección de diseño de página.

   ![](assets/5-1.png)

1. Haga clic en la llave dentro de [!DNL VisualForce] y cambie la altura a 100 y habilite las barras de desplazamiento.

1. En el menú, seleccione la opción [!UICONTROL Canvas Apps] y cree una sección llamada &quot;Perspectivas de Marketo Measure&quot; debajo de los puntos de contacto [!DNL VisualForce] sección que ha creado.

   >[!NOTE]
   >
   >Seleccione el formato &quot;una columna&quot; para cada una de estas secciones.

1. Arrastre la aplicación de lienzo de [!DNL Marketo Measure Insights] a esa sección recién creada. Haga clic en **Guardar**. A veces es necesario guardar primero el diseño de la página antes de soltarlo en la aplicación de lienzo porque Salesforce no lo reconoce instantáneamente. Por lo tanto, después de crear la sección, guarde el diseño de página y vuelva a editarlo para arrastrar la aplicación de lienzo dentro de esa sección. Esto se aplica a cada objeto.

   >[!NOTE]
   >
   >Para el [!DNL Marketo Measure Insights] Canvas App para funcionar correctamente, [los permisos deben configurarse correctamente](/help/configuration-and-setup/marketo-measure-insights-canvas-app/marketo-measure-insights-configuration.md).

   >[!TIP]
   >
   >La mayoría de los clientes no utilizan los campos que terminan en (FT) o (LC) porque son campos heredados de antes de que el Touchpoint de [!DNL Marketo Measure] existiera como objeto.

Si está utilizando el [!DNL Marketo Measure] Función ABM, [haga clic aquí para obtener instrucciones adicionales sobre el diseño de la página](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md).

## Contactos {#contacts}

1. En la opción Generar, seleccione **[!UICONTROL Contactos]**.

1. Haga clic en **[!UICONTROL Diseños de página]**.

1. Seleccione el Diseño de página que desee editar.

   Vaya a la opción Listas relacionadas del menú de búsqueda rápida y añada la lista relacionada **[!UICONTROL Buyer Touchpoints]**.

1. Haga clic en el icono de llave inglesa y añada las siguientes columnas en este orden:

   * Buyer Touchpoint
   * Canal de marketing
   * Origen del Touchpoint
   * Nombre de campaña de anuncios
   * Posición del Touchpoint
   * Fecha de Touchpoint

1. Ordenar Por: fecha de Touchpoint, ascendente.

   ![](assets/6.jpg)

1. Expanda la opción Botones y deseleccione **[!UICONTROL Nuevo]**.

   ![](assets/7.png)

1. Vuelva a la opción [!UICONTROL Lista relacionada] en el menú y, a continuación, añada la lista relacionada **[!UICONTROL Buyer Attribution Touchpoint]**.

1. Haga clic en el icono de llave inglesa y añada las siguientes columnas en este orden:

   * Touchpoint de atribución
   * Canal de marketing
   * Oportunidad
   * Nombre de campaña de anuncios
   * Tipo de Touchpoint
   * Posición del Touchpoint
   * % en forma de W de atribución (_o el modelo de atribución más robusto, como ruta completa o personalizado_)
   * Forma de W de ingresos (_o el modelo de atribución más robusto, como ruta completa o personalizado_)
   * Fecha de Touchpoint

1. Orden por [!UICONTROL Fecha] de Touchpoint > [!UICONTROL Ascendente].

1. Expanda la sección Botones y deseleccione **[!UICONTROL Nuevo]**.

1. Haga clic en **[!UICONTROL Guardar]**.

## Oportunidades {#opportunities}

1. En la opción Generar, seleccione **[!UICONTROL Oportunidades]**.

1. Haga clic en **[!UICONTROL Diseños de página]**.

1. Seleccione el Diseño de página que desee editar.

1. Añada la lista relacionada **[!UICONTROL Buyer Attribution Touchpoint]** y haga clic en la llave inglesa para añadir las siguientes columnas para Oportunidades:

   * Touchpoint de atribución
   * Canal de marketing
   * Contacto
   * Nombre de campaña de anuncios
   * Tipo de Touchpoint
   * Posición del Touchpoint
   * % en forma de W de atribución (_o el modelo de atribución más robusto, como ruta completa o personalizado_)
   * Forma de W de ingresos (_o el modelo de atribución más robusto, como ruta completa o personalizado_)
   * Fecha de Touchpoint

1. Ordene por [!UICONTROL Fecha de Touchpoint] > [!UICONTROL Ascendente].

1. Deseleccione **[!UICONTROL Nuevo]** dentro de la sección [!UICONTROL Botones].

1. Haga clic en **[!UICONTROL Guardar]**.

## Cuentas {#accounts}

1. En la opción Generar, seleccione **[!UICONTROL Cuentas]**.

1. Haga clic en **[!UICONTROL Diseños de página]**.

1. Seleccione el Diseño de página que desee editar.

1. Añada la lista relacionada **[!UICONTROL Buyer Attribution Touchpoint]** y haga clic en la llave inglesa para añadir las siguientes columnas:

   * Touchpoint de atribución
   * Canal de marketing
   * Oportunidad
   * Nombre de campaña de anuncios
   * Tipo de Touchpoint
   * Posición del Touchpoint
   * % en forma de W de atribución (_o el modelo de atribución más robusto, como ruta completa o personalizado_)
   * Forma de W de ingresos (_o el modelo de atribución más robusto, como ruta completa o personalizado_)
   * Fecha de Touchpoint

1. Ordene por Fecha de Touchpoint > Ascendente.

1. Deseleccione **[!UICONTROL Nuevo]** dentro de la sección [!UICONTROL Botones].

1. Haga clic en **[!UICONTROL Guardar]**.

Si utiliza el complemento [!DNL Marketo Measure] Función ABM, revise la [instrucciones adicionales de diseño de página](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md).
