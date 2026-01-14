---
description: Modelo de atribución personalizado y directrices de configuración para usuarios de Marketo Measure
title: Modelo de atribución personalizado y configuración
exl-id: 7b156db2-9ac6-4d32-ac67-06c0aa15d651
feature: Attribution, Custom Models
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 1%

---

# Modelo de atribución personalizado y configuración {#custom-attribution-model-and-setup}

Vea a continuación una descripción general del modelo de atribución personalizado [!DNL Marketo Measure] y cómo configurarlo.

## Modelo de atribución personalizado {#custom-attribution-model}

El modelo de atribución personalizada [!DNL Marketo Measure] permite a los usuarios elegir qué puntos de contacto o fases personalizadas incluir en el modelo. Los usuarios pueden controlar el porcentaje de crédito de ingresos atribuido a estos puntos de contacto y fases o pueden utilizar los valores de porcentaje de atribución sugeridos por el modelo de aprendizaje automático de [!DNL Marketo Measure].

## Configuración del modelo de atribución personalizado {#how-to-set-up-your-custom-attribution-model}

1. Determine qué fases desea incluir en el modelo personalizado.

   Para empezar a crear el modelo de atribución personalizado, deberá seleccionar qué etapas son importantes para el equipo de marketing. Además de las fases del hito [!DNL Marketo Measure] (FT, LC, OC, Cerrado), puede agregar hasta seis fases adicionales de posible cliente/contacto o de oportunidad en el modelo personalizado. Por ejemplo, es común que la fase MQL se incluya en el modelo personalizado. Los equipos de marketing suelen querer saber qué esfuerzos o canales están impulsando las transiciones al escenario de MQL.

   Iniciar sesión en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. Vaya a [!UICONTROL Mi cuenta] > [!UICONTROL Configuración] > y en la sección CRM, seleccione **[!UICONTROL Asignación de etapas]**.

   A continuación, elija qué fases de posibles clientes/contactos y oportunidad desea incluir seleccionando el cuadro **[!UICONTROL Incluir en modelo]**.

   >[!NOTE]
   >
   >Se le permiten hasta seis fases personalizadas (sin incluir las predeterminadas: FT, LC, OC y Cerrado).

   ![Se le permiten hasta seis fases personalizadas (sin incluir los valores predeterminados:](assets/custom-models-1.png)

   >[!NOTE]
   >
   >_Todos_ los posibles clientes/contactos y las fases de oportunidad aparecerán aquí, aunque la fase esté inactiva o ya no se utilice en [!DNL Salesforce]. Si desea eliminar estas fases, deberá eliminarlas en [!DNL Salesforce].

   Cuando hayas seleccionado las fases, asegúrate de hacer clic en el botón **[!UICONTROL Guardar y procesar]** en la parte inferior de la página. Las fases ahora aparecerán en la pestaña **[!UICONTROL Configuración de atribución]** y podrá asignar porcentajes de atribución a cada fase. Las fases personalizadas también se mostrarán en el conjunto de rendimiento de marketing como una fase de posible cliente u oportunidad dentro de la cascada de la demanda.

   Si hay otras fases que desea incluir en el modelo, pero no están en la lista [!UICONTROL Estado del posible cliente/contacto] o [!UICONTROL Fase de oportunidad], puede definir su propia fase personalizada en función de los campos de su CRM.

   En el ejemplo siguiente, se define una fase &quot;MQL&quot; personalizada mediante un campo de fecha. La regla simplemente establece que si el campo Fecha de MQL no está vacío, debe considerarse un MQL y debe incluirse en el modelo personalizado. También es importante ordenar las fases personalizadas una vez creadas para que sigan la progresión del ciclo de ventas.

   ![En el ejemplo siguiente, se define una etapa de &quot;MQL&quot; personalizada usando ](assets/custom-models-10.png)

   >[!CAUTION]
   >
   >No olvide habilitar el seguimiento del historial para los campos personalizados.

Si se utiliza un campo personalizado en el modelo personalizado, el seguimiento del historial de campos DEBE estar habilitado en CRM. Para obtener instrucciones para habilitar el seguimiento del historial de campos, consulte [Configuración del modelo personalizado: Habilitar el seguimiento del historial de campos](/help/channel-tracking-and-setup/custom-model-setup-enable-field-history-tracking.md).

1. Determine los porcentajes de atribución para el modelo personalizado.

   Vaya a **[!UICONTROL Configuración de atribución]** en [!DNL Marketo Measure] aplicaciones; las fases personalizadas aparecerán aquí en la tabla de atribución. La tabla de atribución muestra todos los modelos de atribución [!DNL Marketo Measure] y la ponderación de atribución de cada modelo. Los porcentajes de atribución de los cinco primeros modelos son fijos y no se pueden cambiar.

   En la columna del extremo derecho denominada &quot;**[!UICONTROL Personalizado]**&quot;, puede establecer la ponderación porcentual para cada etapa en el modelo de atribución personalizado. Introduzca los valores de cada etapa en la columna Personalizado y haga clic en **[!UICONTROL Guardar y volver a procesar]** cuando haya terminado.

   A la izquierda de la columna _Personalizado_ se encuentra el modelo de aprendizaje automático **[!DNL Marketo Measure]**. El modelo de aprendizaje automático calcula la ponderación de atribución en función de la importancia relativa para ganar un acuerdo, según lo que haya sucedido en cada fase personalizada. Para obtener más información sobre el modelo de aprendizaje automático, consulte [Preguntas frecuentes sobre el modelo de aprendizaje automático](/help/channel-tracking-and-setup/machine-learning-model-faq.md).

   ![A la izquierda de la columna Personalizada se encuentra Marketo Measure](assets/custom-models-2.png)

## Posiciones de Touchpoint {#touchpoint-positions}

Una vez guardados y procesados los porcentajes de atribución, los puntos de contacto se actualizarán y recibirán sus nuevas fases y posiciones. El punto de contacto que se haya producido más recientemente, antes de una transición de fase, recibirá crédito por esa fase (como se muestra a continuación). La ponderación personalizada y los ingresos también se redistribuyen.

![Después de guardar y procesar los porcentajes de atribución, los puntos de contacto serán](assets/custom-models-3.png)

## La diferencia entre las etapas de Funnel y las etapas de modelo personalizadas {#the-difference-between-funnel-stages-and-custom-model-stages}

Ahora puede ver fases personalizadas en el Funnel de marketing aunque no tenga habilitado el modelo personalizado. Esto se lograría mediante el uso de la funcionalidad Funnel Stage. Las fases de funnel ahora permiten agregar fases a funnel, pero no ver la atribución para ellas.

Las etapas de funnel seguirán rastreándose como puntos de contacto y seguirán apareciendo como posiciones de punto de contacto en su CRM. Sin el modelo personalizado, estos puntos de contacto pueden seguir recibiendo una atribución de contacto medio si hay un relleno de formulario (10 % para los toques medios), pero sin crédito de atribución si solo es una visita web.

Como puede ver a continuación, hemos incluido la fase de diligencia como parte de nuestras fases de Funnel. Esto significa que tendremos puntos de contacto en los que la posición contenga Diligencia, pero esos puntos de contacto solo recibirán crédito de atribución de contacto medio si el modelo personalizado no está habilitado (como máximo un 10 %).

![Como puede ver a continuación, hemos incluido la fase de diligencia como elemento aparte](assets/custom-models-7.png)

>[!NOTE]
>
>El comportamiento de los modelos personalizados de BAT es dividir el porcentaje de contacto medio del modelo personalizado de forma uniforme en otras fases, siempre que no haya toques intermedios.
