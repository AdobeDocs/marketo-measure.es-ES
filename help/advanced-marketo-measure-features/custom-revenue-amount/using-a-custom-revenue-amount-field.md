---
unique-page-id: 18874793
description: Uso de un campo de importe de ingresos personalizado - [!DNL Marketo Measure] - Documentación del producto
title: Uso de un campo de importe de ingresos personalizado
exl-id: 517ea4f9-aa83-48d0-8ce7-003f4a907430
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# Uso de un campo de importe de ingresos personalizado {#using-a-custom-revenue-amount-field}

De forma predeterminada, los puntos de contacto de atribución de comprador extraerán la cantidad de oportunidad de uno de los dos campos:

* Cantidad (SFDC predeterminado)
* [!DNL Marketo Measure] Cantidad de oportunidad (personalizada)

Si utiliza un campo Importe personalizado en sus Oportunidades, tendremos que configurar un flujo de trabajo para calcular los Ingresos de punto de contacto del comprador. Esto requiere un conocimiento más avanzado de [!DNL Salesforce], por lo que puede requerir asistencia del administrador de SFDC.

A partir de esta fecha, se necesita la siguiente información:

* Nombre de API del campo Importe

A partir de aquí, empezaremos a crear el flujo de trabajo.

1. Vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Crear]** > **[!UICONTROL Flujo de trabajo y aprobaciones]** > **[!UICONTROL Reglas de flujo de trabajo]**.

   ![](assets/1.jpg)

1. Select **[!UICONTROL Nueva regla]**, establezca el objeto como &quot;Oportunidad&quot; y haga clic en **[!UICONTROL Siguiente]**.

   ![](assets/2.jpg)

   ![](assets/3.jpg)

1. Configure el flujo de trabajo. Configure el nombre de regla como &quot;Actualizar&quot; [!DNL Marketo Measure] Cantidad de oportunidad&quot;. Defina los criterios de evaluación en &quot;Creado y cada vez que se edite&quot;. En Criterios de regla, seleccione el campo Cantidad personalizada y elija el Operador [!UICONTROL como &quot;Not Equal To&quot;] y deje el campo &quot;Value&quot; en blanco.

   ![](assets/4.jpg)

1. Añada una acción de flujo de trabajo. Establezca esta lista de selección como &quot;[!UICONTROL Actualización de campo nuevo].&quot;

   ![](assets/5.jpg)

1. Aquí rellenará la información de campo. En el campo &quot;Nombre&quot;, se recomienda utilizar este nombre: &quot;[!DNL Marketo Measure] Cantidad Opp&quot;. El &quot;Nombre único&quot; se rellenará automáticamente en función del campo &quot;Nombre&quot;. En la lista de selección &quot;Campo para actualizar&quot;, seleccione &quot;[!DNL Marketo Measure] Cantidad de oportunidad&quot;. Después de seleccionar el campo, seleccione el cuadro &quot;Volver a evaluar las reglas de flujo de trabajo después del cambio de campo&quot;. En &quot;Especificar nuevo valor de campo&quot;, seleccione &quot;Usar una fórmula para establecer el nuevo valor&quot;. En el cuadro vacío, suelte el nombre de la API del campo Cantidad personalizada. Haga clic en **[!UICONTROL Guardar]**.

   ![](assets/6.png)

1. Volverá a una página de resumen para el flujo de trabajo, asegúrese de &quot;Activar&quot; y estará listo para irse. Para activar, haga clic en **Editar** junto al nuevo flujo de trabajo y haga clic en **Activar**.

   Una vez que haya completado estos pasos, será necesario actualizar las oportunidades para obtener el déclencheur del flujo de trabajo y tener el nuevo valor de la variable [!UICONTROL oportunidad personalizada] campo .

   Esto se puede lograr ejecutando las oportunidades a través del cargador de datos dentro de SFDC. Encontrará detalles sobre el uso de Data Loader en [este artículo](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md).

Si hay alguna pregunta en el camino, no dude en ponerse en contacto con su gestor de éxito de clientes o [[!DNL Marketo] Asistencia](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
