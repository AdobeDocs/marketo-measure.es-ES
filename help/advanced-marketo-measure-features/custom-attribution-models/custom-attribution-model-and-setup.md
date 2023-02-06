---
unique-page-id: 18874779
description: Modelo de atribución personalizado y configuración - [!DNL Marketo Measure] - Documentación del producto
title: Modelo de atribución personalizado y configuración
exl-id: 7b156db2-9ac6-4d32-ac67-06c0aa15d651
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 0%

---

# Modelo de atribución personalizado y configuración {#custom-attribution-model-and-setup}

Consulte a continuación para obtener una descripción general del [!DNL Marketo Measure] modelo de atribución personalizado y cómo configurarlo.

## Modelo de atribución personalizado {#custom-attribution-model}

La variable [!DNL Marketo Measure] El modelo de atribución personalizada permite a los usuarios elegir qué puntos de contacto o etapas personalizadas incluir en el modelo. Los usuarios pueden controlar el porcentaje de crédito de ingresos atribuido a estos puntos de contacto y etapas, o pueden utilizar los valores de porcentaje de atribución sugeridos por la variable [!DNL Marketo Measure] Modelo de aprendizaje automático.

## Cómo configurar el modelo de atribución personalizado {#how-to-set-up-your-custom-attribution-model}

1. Determine qué etapas desea incluir en el modelo personalizado.

   Para empezar a crear el modelo de atribución personalizado, deberá seleccionar qué etapas son importantes para su equipo de Marketing. Además del [!DNL Marketo Measure] etapas de hitos (FT, LC, OC, Cerrado) puede agregar hasta seis estados de posible cliente o contacto adicionales o etapas de oportunidad en su modelo personalizado. Por ejemplo, es común que el escenario de MQL se incluya en el modelo personalizado. Los equipos de marketing suelen querer saber qué esfuerzos o canales están impulsando transiciones al escenario de MQL.

   Iniciar sesión en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. Vaya a [!UICONTROL Mi cuenta] > [!UICONTROL Configuración] > y en la sección CRM , seleccione **[!UICONTROL Asignación de fases]**.

   Una vez aquí, tendrá que seleccionar qué etapas de posibles clientes/contactos y oportunidad incluir seleccionando la **[!UICONTROL Incluir en modelo]** en la ventana

   >[!NOTE]
   >
   >Se le permiten hasta seis etapas personalizadas (sin incluir los valores predeterminados: FT, LC, OC, Cerrado).

   ![](assets/1-1.png)

   >[!NOTE]
   >
   >_Todo_ Aquí aparecerán los posibles clientes/contactos y las fases de oportunidad, aunque el escenario esté inactivo o ya no se utilice en [!DNL Salesforce]. Si desea eliminar estas etapas, tendrá que eliminarlas en [!DNL Salesforce].

   Cuando haya seleccionado las etapas, asegúrese de hacer clic en el **[!UICONTROL Guardar y procesar]** en la parte inferior de la página. Las etapas aparecerán ahora en la variable **[!UICONTROL Configuración de atribución]** y podrá asignar porcentajes de atribución a cada etapa. Las etapas personalizadas también se mostrarán en Marketing Performance Suite como una etapa de posible cliente u oportunidad dentro de Demand Waterfall.

   Si hay otras etapas que desea incluir en el modelo, pero no están en la variable [!UICONTROL Estado de posible cliente/contacto] o [!UICONTROL Fase de oportunidad] , puede definir su propio escenario personalizado basado en los campos de su CRM.

   En el ejemplo siguiente, se define una etapa personalizada de &quot;MQL&quot; mediante un campo de fecha. La regla simplemente indica que si el campo Fecha de MQL no está vacío, debe considerarse un MQL y incluirse en el modelo personalizado. Tenga en cuenta que también es importante ordenar las etapas personalizadas una vez creadas para que sigan la evolución de su ciclo de ventas.

   ![](assets/2-1.png)

   >[!CAUTION]
   >
   >No olvide habilitar el seguimiento del historial para campos personalizados.

Si se está utilizando un campo personalizado en el modelo personalizado, el seguimiento del historial de campos DEBE estar habilitado en CRM. Para obtener instrucciones sobre cómo habilitar el seguimiento del historial de campos, [haga clic aquí](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md).

1. Determine los porcentajes de atribución para el modelo personalizado.

   Vaya a la **[!UICONTROL Configuración de atribución]** en [!DNL Marketo Measure] Aplicaciones; las etapas personalizadas aparecen aquí en la tabla de atribución. La tabla de atribución muestra todas las [!DNL Marketo Measure] modelos de atribución y la ponderación de atribución de cada modelo. Los porcentajes de atribución de los cinco primeros modelos son fijos y no se pueden cambiar.

   En la columna del extremo derecho denominada &quot;**[!UICONTROL Personalizado]**,&quot; puede establecer la ponderación porcentual para cada etapa en el modelo de atribución personalizado. Simplemente introduzca los valores para cada etapa en la columna Personalizado . Entonces **[!UICONTROL Guardar y volver a procesar]** una vez finalizado.

   A la izquierda de la columna &quot;Personalizado&quot; se encuentra la **[!DNL Marketo Measure]Modelo de aprendizaje automático**. El modelo de aprendizaje automático calcula la ponderación de atribución en función de la importancia relativa de ganar una oferta en función de lo que haya sucedido en cada fase personalizada. Para obtener más información sobre el modelo de aprendizaje automático, [haga clic aquí](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).

   ![](assets/3.png)

## Posiciones de Touchpoint {#touchpoint-positions}

Una vez guardados y procesados los porcentajes de atribución, los puntos de contacto se actualizarán y recibirán sus nuevas etapas y posiciones. El punto de contacto que se produjo más recientemente, antes de una transición de fase, recibirá crédito para esa fase (como se muestra a continuación). La ponderación y los ingresos personalizados también se redistribuyen.

![](assets/4.png)

## La diferencia entre las etapas del canal y las etapas del modelo personalizado {#the-difference-between-funnel-stages-and-custom-model-stages}

Ahora puede ver etapas personalizadas en el canal de marketing, aunque no tenga el modelo personalizado habilitado. Esto sería a través del uso de la funcionalidad de la fase de canal. Ahora, los escenarios de canal le permiten agregar etapas al canal, pero no ver la atribución para ellos.

Los escenarios de canal se seguirán rastreando como puntos de contacto y seguirán apareciendo como posiciones de punto de contacto en su CRM. Sin el modelo personalizado, estos touchpoints pueden seguir recibiendo atribución de contacto intermedio si hay un relleno de formulario (10 % para intermedios), pero no crédito de atribución cero si se trata de una visita web.

Como pueden ver a continuación, hemos incluido la etapa de Diligencia como parte de nuestras etapas de canal. Esto significa que tendremos Touchpoints donde la posición contenga Diligence, pero esos Touchpoints solo recibirán crédito de atribución de Middle Touch si el Modelo personalizado no está habilitado (como máximo, 10%).

![](assets/5.png)

>[!NOTE]
>
>El comportamiento de los modelos personalizados de MTD es dividir el porcentaje de contacto medio del modelo personalizado uniformemente en otras etapas, siempre que no haya toques intermedios.
