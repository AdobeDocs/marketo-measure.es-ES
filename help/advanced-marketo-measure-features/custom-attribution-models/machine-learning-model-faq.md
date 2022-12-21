---
unique-page-id: 18874775
description: 'Preguntas frecuentes sobre el modelo de aprendizaje automático: [!DNL Marketo Measure] - Documentación del producto'
title: Preguntas frecuentes sobre el modelo de aprendizaje automático
exl-id: 2fc142b2-8ac4-4c48-a8f1-398e29ccfe97
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---

# Preguntas frecuentes sobre el modelo de aprendizaje automático {#machine-learning-model-faq}

La variable [!DNL Marketo Measure] El modelo de aprendizaje automático utiliza los datos de punto de contacto para calcular la ponderación de atribución que se debe asignar a cada fase. Esto está determinado por la importancia que cada etapa tenía para que los acuerdos se cerraran.

¿Qué me dicen los porcentajes de atribución del Modelo de Aprendizaje automático de cada etapa?

Los porcentajes de atribución de cada fase reflejan el impacto potencial de sus esfuerzos de marketing. Un porcentaje mayor significa que el marketing puede influir directamente en el movimiento del canal en ese momento. Un porcentaje de atribución menor significa que las etapas son menos importantes para que su equipo las supervise.

¿Cómo se calcula el modelo de aprendizaje automático?

[!DNL Marketo Measure] calcula la importancia de cada etapa personalizada mediante el uso de los datos de punto de contacto de su cuenta. Los criterios utilizados para determinar la importancia de cada etapa son:

* Precisión del modelo: Si construimos un modelo predictivo con los datos de los puntos de contacto para predecir si finalmente ganaremos un acuerdo, ¿cuán preciso será el modelo? Una mayor precisión predictiva significa que los detalles de esta etapa se correlacionan más con si una operación se cerrará
* Tasa de conversión: Si los posibles clientes u oportunidades en esta fase determinada se convierten a la siguiente fase a una tasa alta, esto sugiere que las actividades de marketing que se produjeron en esta fase no importaron mucho. Por el contrario, si una determinada fase se convierte a la siguiente fase a una tasa baja, esto puede sugerir que las actividades de marketing que se produjeron en esta fase influyeron en la generación de la conversión.
* Peso de la unicidad de Touchpoint: Si una etapa se produce como una transición independiente, lo que significa que no hubo ninguna otra transición de etapa que se produjera al mismo tiempo, esta fase podría recibir un peso de atribución mayor. Por el contrario, si un punto de contacto para un escenario se comparte con otras etapas (p. ej., si el punto de contacto comparte las fases Primer toque, Conversión de posibles clientes y Conversión de oportunidades), este paso podría recibir una ponderación de atribución más baja.

El peso final de una etapa personalizada se calcula de la siguiente manera:

**_Porcentaje de modelo = Precisión de modelo x Tasa de conversión x Peso de punto de contacto_**

Al final, todos los pesos de escenario personalizados se normalizan y se convierten a %, como se muestra a continuación.

¿Por qué no veo ningún número en la columna Aprendizaje automático?

Cuando el modelo de atribución personalizada está habilitado para su cuenta, generalmente se tarda entre 3 y 7 días en que nuestro modelo ejecute y genere estos números, en función de sus datos históricos.

¿Con qué frecuencia se actualiza el modelo de aprendizaje automático?

Volvemos a ejecutar el modelo cada 7 días.

¿Por qué el modelo siempre establece los toques medios en 10%?

Asignar un 10% de crédito de atribución a los toques medios es una configuración estándar en todos nuestros modelos de atribución.

¿Cuándo debo cambiar mi distribución de atribución?

Póngase en contacto con el administrador de su cuenta para analizar las implicaciones de cambiar los porcentajes de atribución y qué etapas incluir en el modelo personalizado. Cada [!DNL Salesforce] y el proceso de ventas es único, y queremos asegurarnos de que su modelo personalizado esté modelado con precisión.

Dicho esto, hemos identificado algunas tendencias generales en nuestros clientes:

Una tendencia que hemos notado es que no siempre es beneficioso incluir más etapas en el modelo. Por ejemplo, cuando los clientes han agregado varias etapas de Oportunidad hacia la parte inferior del canal, estas etapas tienden a recibir valores de porcentaje de atribución muy bajos. Los valores de porcentaje bajos indican una tasa de conversión alta, lo que generalmente significa que estas etapas no tienen el mismo impacto en hacer que las ofertas se cierren. Algunos clientes deciden no incluir estas etapas en el canal. Si decide eliminar una etapa del modelo de atribución, el modelo de máquina volverá a calcular y redistribuirá los porcentajes.

También hemos observado que existe una tasa de conversión alta desde la creación de posibles clientes hasta las etapas de marketing cualificadas, y por lo tanto, la fase de marketing cualificado podría recibir una ponderación de atribución de porcentaje más baja. Dependiendo del ciclo de ventas y del negocio, puede ser beneficioso eliminar esta etapa del modelo personalizado.

Tenga en cuenta que si desea rastrear las actividades de marketing a través de una transición de etapa específica pero no desea que esta fase reciba crédito de atribución, puede incluir esta fase en el modelo y asignar un crédito de atribución del 0 % a esa fase.
