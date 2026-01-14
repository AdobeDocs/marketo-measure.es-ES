---
description: Prácticas recomendadas para la guía de modelos personalizados para usuarios de Marketo Measure
title: Prácticas recomendadas para el modelo personalizado
exl-id: 7c19bb6a-30fc-4cbd-a58e-f20751102afe
feature: Custom Models
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 2%

---

# Prácticas recomendadas para el modelo personalizado {#best-practices-for-custom-model}

## Información general {#overview}

Además de los modelos de atribución predeterminados de [!DNL Marketo Measure], los clientes de nivel 2 y superiores tienen acceso a un modelo de atribución personalizado.

El modelo de atribución personalizada [!DNL Marketo Measure] permite a los usuarios elegir qué posiciones de punto de contacto de hito y/o etapas personalizadas se incluirán en el modelo. Además, los usuarios pueden controlar el porcentaje de crédito atribuido a cada fase del modelo (pueden definir hasta 6 fases personalizadas adicionales) o pueden utilizar los valores de porcentaje de atribución sugeridos por el modelo de aprendizaje automático [!DNL Marketo Measure].

Existen dos aspectos clave del modelo de atribución personalizado:

**Fases personalizadas** permiten que los usuarios definan su funnel en relación con su negocio y procesos. Las fases personalizadas deben representar &quot;hitos&quot; a lo largo del recorrido del comprador, de forma muy similar a los hitos [!DNL Marketo Measure] (Primer contacto, Contacto de creación de posibles clientes, Contacto de creación de oportunidades y Cerrado contacto ganado) de los modelos de atribución de existencias. Es crucial que las etapas personalizadas estén definidas y asignadas correctamente en su cuenta para garantizar que [!DNL Marketo Measure] esté realizando un seguimiento adecuado de las transiciones de etapas. Esto sirve para identificar qué puntos de contacto deben asociarse con cada fase y atribuir correctamente el crédito. La asignación de etapas personalizada es esencialmente una extensión de la asignación de etapas estándar y debe seguir las mismas prácticas.

>[!NOTE]
>
>Consulte el recurso Prácticas recomendadas de asignación de etapas para obtener más información

**Modelado de atribución personalizado** se define una vez que haya seleccionado su funnel de fases personalizadas. Los usuarios pueden controlar cuánto crédito de atribución se debe asignar a cada etapa personalizada, así como a las etapas de hito [!DNL Marketo Measure]. Los usuarios pueden asignar crédito a cada etapa según lo consideren conveniente o hacer referencia al modelo de aprendizaje automático [!DNL Marketo Measure] que actúa como un &quot;modelo sugestivo&quot; basado en los datos históricos.

Es crucial que estos dos aspectos del modelo personalizado se definan correctamente y con precisión para garantizar que [!DNL Marketo Measure] produzca un modelo de atribución personalizado preciso.

## Práctica recomendada {#best-practice}

Tanto si configura el modelo personalizado por primera vez como si revisa lo que se ha establecido anteriormente, es importante tener en cuenta las siguientes prácticas recomendadas.

* Inicio simple
   * Identifique las etapas clave que desee agregar al modelo personalizado y que son cruciales para los informes de [!DNL Marketo Measure]. Normalmente, estas son etapas con las que se suele medir o con las que se pretende obtener insight
   * Siempre puede agregar al modelo personalizado con el tiempo
* Utilizar el modelo de aprendizaje automático [!DNL Marketo Measure]
   * Si tiene dificultades para decidir el desglose de atribución porcentual, el modelo de aprendizaje automático de [!DNL Marketo Measure] puede ayudarle a tomar decisiones informadas al configurar el modelo de atribución personalizado.
   * Al ver el modelo de aprendizaje automático, los porcentajes de atribución de cada fase reflejan el impacto potencial de sus esfuerzos de marketing
      * Un porcentaje mayor significa que el marketing puede influir directamente en el movimiento de la funnel en ese punto
      * Un porcentaje de atribución menor significa que las fases son menos importantes para que el equipo las supervise
* Debe definir la parte superior de las fases de funnel en función de las fases Posible cliente o Contacto, no en ambas
   * Esto significa que debe asegurarse de que todas las personas pasen por esa etapa en el objeto relativo
      * Por ejemplo: si define la etapa MQL a partir del objeto de posible cliente, todas las personas deben entrar en su sistema como posible cliente y marcarse como un MQL en su registro de posible cliente para que [!DNL Marketo Measure] refleje con precisión qué contacto estaba relacionado con la transición del posible cliente a MQL. Si este no es el caso, y algunas personas progresan a Contacto antes de convertirse en MQL como posible cliente, [!DNL Marketo Measure] no podrá explicar esto con precisión en sus datos de Touchpoint y tendremos que suponer que esa persona ya ha cambiado de MQL. [!DNL Marketo Measure] no puede contabilizar el salto de etapa, por lo que deduciremos que las etapas se han pasado aunque no lo hayan hecho.
* Asegúrese de que el seguimiento del historial de campos esté habilitado para todos los campos utilizados para definir las fases personalizadas que incorpora
* No utilice campos de fórmula para definir una fase personalizada
   * Una recomendación de prácticas recomendadas es un campo booleano
* No incorpore etapas personalizadas al modelo personalizado que coincidan con una posición de punto de contacto de hito [!DNL Marketo Measure] (FT, LC, OC, ganados/perdidos cerrados)
   * Si lo hace, estas posiciones siempre se producen simultáneamente y pueden causar un crédito de atribución inflado a partes de su funnel.
* Trabaje con su equipo de ventas
   * La inclusión del equipo que trabaja más cerca de las fases y su significado garantiza que está utilizando las fases correctas y que están definidas correctamente

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Revisar el modelo personalizado al menos dos veces al año garantizará que los informes de atribución personalizados sean precisos y fiables.

Si el modelo personalizado utiliza el modelo de aprendizaje automático, debe revisar su aplicación dentro del modelo personalizado trimestralmente para asegurarse de que el modelo personalizado esté lo más actualizado posible.

Otras razones que podrían déclencheur una revisión de su modelo personalizado incluyen...

* Rotación en su equipo de marketing
* Cualquier cambio en las fases de CRM
* Actualizaciones en funnel de sus organizaciones
* Ver datos de ingresos inexactos en los informes de [!DNL Marketo Measure] al aplicar el modelo personalizado
* Ver posiciones de puntos de contacto rellenadas que ya no son relevantes para su organización funnel

>[!MORELIKETHIS]
>
>* [Modelo de atribución personalizada y configuración](/help/advanced-features/custom-attribution-models/custom-attribution-model-and-setup.md)
>* [Habilitar El Seguimiento Del Historial De Campos Para El Modelo Personalizado](/help/advanced-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
>* [Modelo de aprendizaje automático](/help/advanced-features/custom-attribution-models/machine-learning-model-faq.md)
