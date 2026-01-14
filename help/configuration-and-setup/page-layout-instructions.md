---
description: Instrucciones de diseño de página para usuarios de Marketo Measure
title: Instrucciones de diseño de página
exl-id: 627377f0-d0cf-448c-a7b5-7eb5634b9627
feature: Salesforce
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 92%

---

# Instrucciones de diseño de página {#page-layout-instructions}

>[!NOTE]
>
>Puede que vea instrucciones que especifican “[!DNL Marketo Measure]” en la documentación, pero seguirá viendo “Bizible” en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

Para ver fácilmente datos de [!DNL Marketo Measure], se recomienda actualizar los diseños de página para los objetos [!UICONTROL Cuenta], [!UICONTROL Contacto], [!UICONTROL Posible cliente], [!UICONTROL Oportunidad], y [!UICONTROL Campaña]. Las instrucciones se desglosan para cada Diseño de página de objeto siguiente.

Para empezar, primero vaya a sus ajustes de configuración de [!DNL Salesforce] y busque la pestaña [!UICONTROL Personalizar].

## Objeto de campaña {#campaign-object}

Se recomienda añadir los campos de [!DNL Marketo Measure] a su campaña de SFDC solo para su zona protegida. Los campos se pueden utilizar para probar la generación de Touchpoints. En producción, se recomienda añadir únicamente el botón de Fecha de Touchpoint de actualización masiva de [!DNL Marketo Measure]. No se recomienda añadir los campos de [!DNL Marketo Measure] a la producción, ya que puede crear reglas de sincronización de campaña.

1. En la opción Generar, seleccione **[!UICONTROL Campañas]**.

1. Haga clic en **[!UICONTROL Diseños de página]**.

   ![1. Haga clic en Diseños de página.](assets/marketo-salesforce-7.jpg)

1. Haga clic en **[!UICONTROL Editar]** situado junto al diseño de página que desea actualizar.

   ![1. Haga clic en Editar junto al diseño de página que desee](assets/marketo-salesforce-1.jpg)

1. Dentro de la opción [!UICONTROL campos], seleccione la opción **[!UICONTROL Habilitar Buyer Touchpoints]** y arrástrela a cualquier lugar de la página que desee. A continuación, añada los campos **[!UICONTROL Fecha de inicio de Touchpoint]** y **[!UICONTROL Fecha de finalización de Touchpoint]**.

   ![1. En la opción Campos, selecciona Habilitar puntos de contacto del comprador](assets/bizible-full-1.png)

1. A continuación, en la parte superior de la página, haga clic en la opción &quot;[!UICONTROL Botones]&quot; en el menú búsqueda rápida.

1. Arrastre el botón **[!UICONTROL Fecha de Touchpoint de actualización masiva]** a la sección de botones personalizados.

   ![1. Arrastre el botón Fecha de punto de contacto de actualización masiva a su &#x200B;](assets/bizible-taxonomy-1.png) personalizado

1. Haga clic en **[!UICONTROL Guardar]**.

   >[!NOTE]
   >
   >Si utiliza varios tipos de registros de campaña, debe actualizar los valores de la lista de selección para el campo **[!UICONTROL Habilitar Buyer Touchpoints]**. Consulte [este artículo](/help/channel-tracking-and-setup/configurations-record-types.md) para obtener instrucciones.

## Clientes potenciales {#leads}

1. En la opción Generar, seleccione **[!UICONTROL Posibles clientes]**.

1. Haga clic en **[!UICONTROL Diseños de página]**.

1. Haga clic en **[!UICONTROL Editar]** situado junto al diseño de página que desea actualizar. Tenga en cuenta que varios diseños de página pueden contener las secciones de Buyer Touchpoints.

1. Haga clic en la opción de la página VisualForce de la izquierda en el menú de búsqueda rápida.

1. Cree una sección y asígnele el nombre “Buyer Touchpoints”.

1. Arrastre la página **[!UICONTROL Lista relacionada con posibles clientes de Marketo Measure]** de VisualForce en la sección de diseño de página.

   ![1. Arrastre la página Marketo Measure Lead Related List de VisualForce a &#x200B;](assets/connect-salesforce-1.png)

1. Haga clic en la llave en la página de [!DNL VisualForce], cambie la altura a 100 y habilite las barras de desplazamiento.

1. En el menú, seleccione la opción [!UICONTROL Aplicaciones de lienzo] y cree una sección denominada “Marketo Measure Insights” bajo la sección Touchpoints de [!DNL VisualForce].

1. Arrastre la aplicación de lienzo de [!DNL Marketo Measure Insights] a esa sección recién creada. Haga clic en **Guardar**. A veces es necesario guardar primero el diseño de la página antes de soltarlo en la aplicación de lienzo porque Salesforce no lo reconoce instantáneamente. Por consiguiente, después de crear la sección, guarde el diseño de página y vuelva a editarlo para arrastrar la aplicación de lienzo dentro de esa sección.  Esto se aplica a cada objeto.

   >[!NOTE]
   >
   >Para que la aplicación de lienzo de [!DNL Marketo Measure Insights] funcione correctamente, [los permisos deben configurarse correctamente](/help/configuration-and-setup/marketo-measure-insights-configuration.md).

Si está utilizando la funcionalidad ABM de [!DNL Marketo Measure], [haga clic aquí para obtener instrucciones adicionales sobre el diseño de la página](/help/channel-tracking-and-setup/account-based-marketing-overview.md).

## Contactos {#contacts}

1. En la opción Generar, seleccione **[!UICONTROL Contactos]**.

1. Haga clic en **[!UICONTROL Diseños de página]**.

1. A continuación, seleccione el diseño de página que desea editar.

   Vaya a la opción Listas relacionadas del menú de búsqueda rápida y añada la lista relacionada **[!UICONTROL Buyer Touchpoints]**.

1. Haga clic en el icono de llave inglesa y añada las siguientes columnas en este orden:

   * Buyer Touchpoint
   * Canal de marketing
   * Origen del Touchpoint
   * Nombre de campaña de anuncios
   * Posición del Touchpoint
   * Fecha de Touchpoint

1. Ordenar Por: fecha de Touchpoint, ascendente.

   ![1. Ordenar por: Fecha de punto de contacto, ascendente.](assets/marketo-salesforce-15.jpg)

1. Expanda la opción Botones y deseleccione **[!UICONTROL Nuevo]**.

   ![1. Expanda la opción Botones y deseleccione Nuevo.](assets/marketo-salesforce-12.png)

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

1. A continuación, seleccione el diseño de página que desea editar.

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

1. A continuación, seleccione el diseño de página que desea editar.

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

Si está utilizando la funcionalidad ABM de [!DNL Marketo Measure], revise las [instrucciones adicionales de diseño de página](/help/channel-tracking-and-setup/account-based-marketing-overview.md).
