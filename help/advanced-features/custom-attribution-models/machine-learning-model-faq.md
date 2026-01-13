---
description: Preguntas frecuentes sobre el modelo de aprendizaje automático - [!DNL Marketo Measure]
title: Preguntas frecuentes sobre el modelo de aprendizaje automático
exl-id: 2fc142b2-8ac4-4c48-a8f1-398e29ccfe97
feature: Custom Models
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 1%

---


# Preguntas frecuentes sobre el modelo de aprendizaje automático {#machine-learning-model-faq}

El modelo de aprendizaje automático [!DNL Marketo Measure] utiliza los datos de punto de contacto para calcular la ponderación de atribución que debe asignarse a cada fase. Esto está determinado por la importancia de cada etapa en las ofertas de manejo para cerrar.

¿Qué me dicen los porcentajes de atribución del modelo de aprendizaje automático sobre cada fase?

Los porcentajes de atribución de cada fase reflejan el impacto potencial de sus esfuerzos de marketing. Un porcentaje mayor significa que el marketing puede influir directamente en el movimiento de la funnel en ese punto. Un porcentaje de atribución menor significa que las fases son menos importantes para que el equipo las supervise.

¿Cómo se calcula el modelo de aprendizaje automático?

[!DNL Marketo Measure] calcula la importancia de cada fase personalizada mediante los datos de punto de contacto de su cuenta. Los criterios utilizados para determinar la importancia de cada etapa son:

* Precisión del modelo: Si construimos un modelo predictivo con los datos del punto de contacto para predecir si vamos a ganar un acuerdo en algún momento, ¿cuán preciso será el modelo? Una mayor precisión predictiva significa que los detalles de esta etapa se correlacionan más con si un acuerdo se cerrará
* Tasa de conversión: si los posibles clientes u oportunidades en esta fase concreta se convierten a la siguiente a una tasa alta, esto sugiere que las actividades de marketing que se produjeron en esta fase no importaban demasiado. Por el contrario, si una determinada fase pasa a la siguiente con una tasa baja, esto puede sugerir que las actividades de marketing que se produjeron en esta fase influyeron en la conversión.
* Peso de unicidad de punto de contacto: si una fase se produce como una transición independiente, lo que significa que no hubo ninguna otra transición de fase que se produjera al mismo tiempo, esta fase podría recibir un peso de atribución más alto. Por el contrario, si un punto de contacto de una fase se comparte con otras fases (por ejemplo, el punto de contacto comparte las fases de primer contacto, conversión de posible cliente y conversión de oportunidad), esta fase podría recibir una ponderación de atribución más baja.

El peso final de una fase personalizada se calcula de esta manera:

**_Porcentaje del modelo = Precisión del modelo x Tasa de conversión x Peso de unicidad del punto de contacto_**

Al final, todas las ponderaciones de escenario personalizadas se normalizan y se convierten a % como se muestra a continuación.

¿Por qué no veo ningún número en la columna Aprendizaje automático?

Cuando el modelo de atribución personalizado está habilitado para su cuenta, generalmente tarda entre 3 y 7 días para que nuestro modelo se ejecute y cree estos números, en función de los datos históricos.

¿Con qué frecuencia se actualiza el modelo de aprendizaje automático?

Volvemos a ejecutar el modelo cada 7 días.

¿Por qué el modelo siempre establece Middle Touches en 10%?

Asignar un 10% de crédito de atribución a los toques medios es una configuración estándar en todos nuestros modelos de atribución.

¿Cuándo debo cambiar la distribución de atribución?

Póngase en contacto con el administrador de cuentas para discutir las implicaciones de cambiar los porcentajes de atribución y qué etapas se deben incluir en el modelo personalizado. Cada [!DNL Salesforce] y proceso de ventas son únicos y queremos asegurarnos de que el modelo personalizado se modele con precisión.

Dicho esto, hemos identificado algunas tendencias generales en nuestros clientes:

Una tendencia que hemos observado es que no siempre es beneficioso incluir más etapas en el modelo. Por ejemplo, cuando los clientes han agregado varias fases de oportunidad hacia la parte inferior de funnel, estas fases tienden a recibir valores de porcentaje de atribución muy bajos. Los valores de porcentaje bajos indican una tasa de conversión alta, lo que generalmente significa que estas etapas no son tan impactantes para lograr acuerdos para cerrar. En última instancia, algunos clientes deciden no incluir estas fases en funnel. Si decide quitar una etapa del modelo de atribución, el modelo del equipo recalculará y redistribuirá los porcentajes.

También hemos observado que existe una alta tasa de conversión de la Creación de posibles clientes a las fases Cualificadas de marketing y, en consecuencia, la fase Cualificado de marketing podría recibir una ponderación de atribución de porcentaje más baja. Según el ciclo comercial y de ventas, puede resultar beneficioso eliminar esta fase del modelo personalizado.

Tenga en cuenta que si desea rastrear las actividades de marketing a través de una transición de etapa específica pero no desea que esta etapa reciba crédito de atribución, puede incluir esta etapa en el modelo y asignar un crédito de atribución del 0% a esa etapa.
