---
unique-page-id: 18874793
description: Uso de un campo Importe de ingresos personalizado - [!DNL Marketo Measure] - Documentación del producto
title: Uso de un campo de importe de ingresos personalizado
exl-id: 517ea4f9-aa83-48d0-8ce7-003f4a907430
feature: Custom Revenue Amount
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 3%

---

# Uso de un campo de importe de ingresos personalizado {#using-a-custom-revenue-amount-field}

De forma predeterminada, los puntos de contacto de atribución del comprador extraerán el importe de la oportunidad de uno de los dos campos siguientes:

* Importe (valor predeterminado de SFDC)
* [!DNL Marketo Measure] Importe de oportunidad (personalizado)

Si utilizas un campo de importe personalizado en tus oportunidades, necesitaremos configurar un flujo de trabajo para calcular los ingresos del punto de contacto del comprador. Esto requiere un conocimiento más avanzado de [!DNL Salesforce], por lo que puede requerir asistencia de su administrador de SFDC.

Para empezar, necesitaremos la siguiente información:

* Nombre de API del campo Importe

A partir de aquí, empezaremos a crear el flujo de trabajo.

1. Vaya a **[!UICONTROL Configurar]** > **[!UICONTROL Crear]** > **[!UICONTROL Flujo de trabajo y aprobaciones]** > **[!UICONTROL Reglas de flujo de trabajo]**.

   ![](assets/1.jpg)

1. Seleccionar **[!UICONTROL Nueva regla]**, establezca el objeto como &quot;Oportunidad&quot; y haga clic en **[!UICONTROL Siguiente]**.

   ![](assets/2.jpg)

   ![](assets/3.jpg)

1. Configure el flujo de trabajo. Establezca el nombre de la regla como &quot;Actualizar&quot; [!DNL Marketo Measure] Importe de oportunidad&quot;. Defina los Criterios de evaluación en &quot;Creado&quot; y cada vez que se edite. En Criterios de regla, seleccione el campo Importe personalizado y seleccione el Operador [!UICONTROL como &quot;No es igual a&quot;] y deje el campo &quot;Valor&quot; en blanco.

   ![](assets/4.jpg)

1. Añada una acción de flujo de trabajo. Establecer esta lista desplegable en &quot;[!UICONTROL Nueva actualización de campo].&quot;

   ![](assets/5.jpg)

1. Aquí rellenará la información de campo. En el campo &quot;Nombre&quot;, se recomienda utilizar este nombre:[!DNL Marketo Measure] Importe de Opp.&quot; El &quot;Nombre único&quot; se rellenará automáticamente en función del campo &quot;Nombre&quot;. En la lista de selección &quot;Campo para actualizar&quot;, seleccione &quot;[!DNL Marketo Measure] Importe de oportunidad&quot;. Después de seleccionar el campo, seleccione la casilla &quot;Volver a evaluar las reglas de flujo de trabajo después de cambiar el campo&quot;. En &quot;Especificar nuevo valor de campo&quot;, seleccione &quot;Usar una fórmula para establecer el nuevo valor&quot;. En el cuadro vacío, suelte el nombre de API del campo Cantidad personalizado. Clic **[!UICONTROL Guardar]**.

   ![](assets/6.png)

1. Se le volverá a una página de resumen para su flujo de trabajo, asegúrese de &quot;Activar&quot; y ya está listo para comenzar. Para activarlo, haga clic en **Editar** junto al nuevo flujo de trabajo y haga clic en **Activar**.

   Una vez que haya completado estos pasos, las oportunidades deberán actualizarse para almacenar en déclencheur el flujo de trabajo y obtener el nuevo valor de la variable [!UICONTROL oportunidad personalizada] field.

   Esto se puede lograr ejecutando sus oportunidades a través del Data Loader dentro de SFDC. Descubra los detalles sobre el uso del cargador de datos en [este artículo](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md).

Si tiene alguna pregunta, no dude en ponerse en contacto con el equipo de cuenta de Adobe (su administrador de cuentas) o [[!DNL Marketo] Asistencia](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
