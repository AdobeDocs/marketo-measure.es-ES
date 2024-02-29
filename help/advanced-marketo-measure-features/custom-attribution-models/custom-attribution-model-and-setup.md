---
unique-page-id: 18874779
description: 'Configuración y modelo de atribución personalizado: [!DNL Marketo Measure]'
title: Modelo de atribución personalizado y configuración
exl-id: 7b156db2-9ac6-4d32-ac67-06c0aa15d651
feature: Attribution, Custom Models
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 1%

---

# Modelo de atribución personalizado y configuración {#custom-attribution-model-and-setup}

Consulte a continuación una descripción general del [!DNL Marketo Measure] modelo de atribución personalizado y cómo configurarlo.

## Modelo de atribución personalizado {#custom-attribution-model}

El [!DNL Marketo Measure] El modelo de atribución personalizado permite a los usuarios elegir qué puntos de contacto o etapas personalizadas incluir en el modelo. Los usuarios pueden controlar el porcentaje de crédito de ingresos atribuido a estos puntos de contacto y fases o pueden utilizar los valores de porcentaje de atribución sugeridos por el [!DNL Marketo Measure] Modelo de aprendizaje automático.

## Configuración del modelo de atribución personalizado {#how-to-set-up-your-custom-attribution-model}

1. Determine qué fases desea incluir en el modelo personalizado.

   Para empezar a crear el modelo de atribución personalizado, deberá seleccionar qué etapas son importantes para el equipo de marketing. Además de las [!DNL Marketo Measure] fases de hito (FT, LC, OC, Cerrado) puede añadir hasta seis fases adicionales de posible cliente/contacto o de oportunidad en el modelo personalizado. Por ejemplo, es común que la fase MQL se incluya en el modelo personalizado. Los equipos de marketing suelen querer saber qué esfuerzos o canales están impulsando las transiciones al escenario de MQL.

   Iniciar sesión en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. Ir a [!UICONTROL Mi cuenta] > [!UICONTROL Configuración] > y en la sección CRM, seleccione **[!UICONTROL Asignación de etapas]**.

   A continuación, seleccione las fases de posibles clientes/contactos y oportunidad que desea incluir seleccionando la **[!UICONTROL Incluir en el modelo]** cuadro.

   >[!NOTE]
   >
   >Se le permiten hasta seis fases personalizadas (sin incluir las predeterminadas: FT, LC, OC y Cerrado).

   ![](assets/1-1.png)

   >[!NOTE]
   >
   >_Todo_ Las fases de posibles clientes/contactos y oportunidad aparecerán aquí, incluso si la fase está inactiva o ya no se utiliza en [!DNL Salesforce]. Si desea eliminar estas fases, deberá eliminarlas completamente en [!DNL Salesforce].

   Cuando haya seleccionado las fases, asegúrese de hacer clic en **[!UICONTROL Guardar y procesar]** en la parte inferior de la página. Las fases aparecerán ahora en el **[!UICONTROL Configuración de atribución]** y podrá asignar porcentajes de atribución a cada fase. Las fases personalizadas también se mostrarán en el conjunto de rendimiento de marketing como una fase de posible cliente u oportunidad dentro de la cascada de la demanda.

   Si hay otras fases que desea incluir en el modelo, pero no están en el [!UICONTROL Estado del posible cliente/contacto] o [!UICONTROL Fase de oportunidad] , puede definir su propia fase personalizada en función de los campos de su CRM.

   En el ejemplo siguiente, se define una fase &quot;MQL&quot; personalizada mediante un campo de fecha. La regla simplemente establece que si el campo Fecha de MQL no está vacío, debe considerarse un MQL y debe incluirse en el modelo personalizado. También es importante ordenar las fases personalizadas una vez creadas para que sigan la progresión del ciclo de ventas.

   ![](assets/2-1.png)

   >[!CAUTION]
   >
   >No olvide habilitar el seguimiento del historial para los campos personalizados.

Si se utiliza un campo personalizado en el modelo personalizado, el seguimiento del historial de campos DEBE estar habilitado en CRM. Para obtener instrucciones para habilitar el seguimiento del historial de campos, consulte [Configuración del modelo personalizado: Habilitar el seguimiento del historial de campos](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md).

1. Determine los porcentajes de atribución para el modelo personalizado.

   Vaya a la **[!UICONTROL Configuración de atribución]** in [!DNL Marketo Measure] Aplicaciones; las fases personalizadas aparecerán aquí en la tabla de atribución. La tabla de atribución muestra todas las [!DNL Marketo Measure] modelos de atribución y la ponderación de atribución de cada modelo. Los porcentajes de atribución de los cinco primeros modelos son fijos y no se pueden cambiar.

   En la columna del extremo derecho rotulada &quot;**[!UICONTROL Personalizado]**,&quot; puede establecer la ponderación porcentual para cada fase del modelo de atribución personalizado. Solo tiene que introducir los valores de cada fase en la columna Personalizado. Entonces **[!UICONTROL Guardar y volver a procesar]** una vez finalizado.

   A la izquierda del _Personalizado_ es la columna **[!DNL Marketo Measure]Modelo de aprendizaje automático**. El modelo de aprendizaje automático calcula la ponderación de atribución en función de la importancia relativa para ganar un acuerdo, según lo que haya sucedido en cada fase personalizada. Para obtener más información sobre el modelo de aprendizaje automático, consulte [Preguntas frecuentes sobre el modelo de aprendizaje automático](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).

   ![](assets/3.png)

## Posiciones de Touchpoint {#touchpoint-positions}

Una vez guardados y procesados los porcentajes de atribución, los puntos de contacto se actualizarán y recibirán sus nuevas fases y posiciones. El punto de contacto que se haya producido más recientemente, antes de una transición de fase, recibirá crédito por esa fase (como se muestra a continuación). La ponderación personalizada y los ingresos también se redistribuyen.

![](assets/4.png)

## La diferencia entre las fases de canal y las fases del modelo personalizado {#the-difference-between-funnel-stages-and-custom-model-stages}

Ahora puede ver etapas personalizadas en el canal de marketing, incluso si no tiene habilitado el modelo personalizado. Esto se lograría mediante el uso de la funcionalidad Ensayo de canal. Las fases de canal ahora permiten agregar fases al canal, pero no ver la atribución para ellas.

Las etapas de canal seguirán rastreándose como puntos de contacto y seguirán apareciendo como posiciones de punto de contacto en su CRM. Sin el modelo personalizado, estos puntos de contacto pueden seguir recibiendo una atribución de contacto medio si hay un relleno de formulario (10 % para los toques medios), pero sin crédito de atribución si solo es una visita web.

Como puede ver a continuación, hemos incluido la fase de diligencia como parte de nuestras fases de canal. Esto significa que tendremos puntos de contacto en los que la posición contenga Diligencia, pero esos puntos de contacto solo recibirán crédito de atribución de contacto medio si el modelo personalizado no está habilitado (como máximo un 10 %).

![](assets/5.png)

>[!NOTE]
>
>El comportamiento de los modelos personalizados BAT es dividir el porcentaje de contacto medio del modelo personalizado de forma uniforme en otras etapas, siempre que no haya toques medios.
