---
description: 'Prácticas recomendadas para el modelo personalizado: [!DNL Marketo Measure]'
title: Prácticas recomendadas para el modelo personalizado
exl-id: 7c19bb6a-30fc-4cbd-a58e-f20751102afe
feature: Custom Models
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 2%

---

# Prácticas recomendadas para el modelo personalizado {#best-practices-for-custom-model}

## Información general {#overview}

Además de las [!DNL Marketo Measure] Los modelos de atribución predeterminados, los clientes de nivel 2 y superiores tienen acceso a un modelo de atribución personalizado.

El [!DNL Marketo Measure] El modelo de atribución personalizado permite a los usuarios elegir qué posiciones de punto de contacto de hito y/o etapas personalizadas incluir en el modelo. Además, los usuarios pueden controlar el porcentaje de crédito atribuido a cada fase dentro del modelo (los usuarios pueden definir hasta 6 fases personalizadas adicionales) o pueden utilizar los valores de porcentaje de atribución sugeridos por el [!DNL Marketo Measure] Modelo de aprendizaje automático.

Existen dos aspectos clave del modelo de atribución personalizado:

**Fases personalizadas** permiten a los usuarios definir su canal en relación con su negocio y procesos. Las fases personalizadas deben representar &quot;hitos&quot; a lo largo del recorrido del comprador de forma muy similar a la [!DNL Marketo Measure] Los hitos (primer contacto, contacto de creación de posibles clientes, contacto de creación de oportunidades y contacto ganado cerrado) se realizan dentro de los modelos de atribución de stock. Es crucial que las fases personalizadas se definan y asignen correctamente dentro de la cuenta para garantizar que [!DNL Marketo Measure] está rastreando correctamente las transiciones de fase. Esto sirve para identificar qué puntos de contacto deben asociarse con cada fase y atribuir correctamente el crédito. La asignación de etapas personalizada es esencialmente una extensión de la asignación de etapas estándar y debe seguir las mismas prácticas.

>[!NOTE]
>
>Consulte el recurso Prácticas recomendadas de asignación de etapas para obtener más información

**Modelado de atribución personalizado** se define una vez que seleccione el canal Etapas personalizadas. Los usuarios pueden controlar cuánto crédito de atribución debe asignarse a cada fase personalizada, así como la variable [!DNL Marketo Measure] fases de hito. Los usuarios pueden asignar crédito a cada fase según lo consideren adecuado o hacer referencia al [!DNL Marketo Measure] Modelo de aprendizaje automático que actúa como un &quot;modelo sugerente&quot; basado en datos históricos.

Es crucial que estos dos aspectos del modelo personalizado se definan correctamente y con precisión para garantizar que [!DNL Marketo Measure] está produciendo un modelo de atribución personalizado preciso.

## Práctica recomendada {#best-practice}

Tanto si configura el modelo personalizado por primera vez como si revisa lo que se ha establecido anteriormente, es importante tener en cuenta las siguientes prácticas recomendadas.

* Inicio simple
   * Identifique las fases clave que desee añadir al modelo personalizado y que son cruciales para su [!DNL Marketo Measure] informes. Por lo general, estas son etapas con las que se suele medir o con las que se pretende obtener información
   * Siempre puede agregar al modelo personalizado con el tiempo
* Utilice el [!DNL Marketo Measure] Modelo de aprendizaje automático
   * Si tiene problemas para decidir el desglose de atribución porcentual, la variable [!DNL Marketo Measure] El modelo de aprendizaje automático puede ayudarle a tomar decisiones informadas al configurar el modelo de atribución personalizado.
   * Al ver el modelo de aprendizaje automático, los porcentajes de atribución de cada fase reflejan el impacto potencial de sus esfuerzos de marketing
      * Un porcentaje mayor significa que el marketing puede influir directamente en el movimiento del canal en ese punto
      * Un porcentaje de atribución menor significa que las fases son menos importantes para que el equipo las supervise
* Debe definir la parte superior de las fases del embudo en función de las fases Cliente potencial o Contacto, no en ambas
   * Esto significa que debe asegurarse de que todas las personas pasen por esa etapa en el objeto relativo
      * Por ejemplo: si define la etapa MQL a partir del objeto de posible cliente, todas las personas deben entrar en el sistema como posible cliente y marcarse como un MQL en su registro de posible cliente para [!DNL Marketo Measure] para reflejar con precisión qué contacto se relacionó con la transición del posible cliente a MQL. Si este no es el caso, y algunas personas progresan a Contacto antes de convertirse en MQL como posible cliente, [!DNL Marketo Measure] no podrá explicar esto con precisión en sus datos de Touchpoint y tendremos que suponer que esa persona ya ha cambiado de MQL. [!DNL Marketo Measure] no puede explicar el salto de etapa, por lo que deduciremos que las etapas se han pasado incluso si no lo han hecho.
* Asegúrese de que el seguimiento del historial de campos esté habilitado para todos los campos utilizados para definir las fases personalizadas que incorpora
* No utilice campos de fórmula para definir una fase personalizada
   * Una recomendación de prácticas recomendadas es un campo booleano
* No incorpore fases personalizadas al modelo personalizado que coincidan con un [!DNL Marketo Measure] Posición de punto de contacto de hito (FT, LC, OC, ganados/perdidos cerrados)
   * Si lo hace, estas posiciones siempre se producirán simultáneamente y pueden causar un crédito de atribución inflado a partes del embudo.
* Trabaje con su equipo de ventas
   * Al incluir al equipo que trabaja más cerca de las fases y su significado, se garantiza que está utilizando las fases correctas y que están definidas correctamente

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Revisar el modelo personalizado al menos dos veces al año garantizará que los informes de atribución personalizados sean precisos y fiables.

Si el modelo personalizado utiliza el modelo de aprendizaje automático, debe revisar su aplicación dentro del modelo personalizado trimestralmente para asegurarse de que el modelo personalizado esté lo más actualizado posible.

Otras razones que podrían déclencheur una revisión de su modelo personalizado incluyen...

* Rotación en su equipo de marketing
* Cualquier cambio en las fases de CRM
* Actualizaciones en el canal de sus organizaciones
* Ver datos de ingresos inexactos en su [!DNL Marketo Measure] creación de informes al aplicar el modelo personalizado
* Ver las posiciones de puntos de contacto rellenadas que ya no son relevantes para el canal de sus organizaciones

>[!MORELIKETHIS]
>
>* [Configuración y modelo de atribución personalizados](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)
>* [Habilitar El Seguimiento Del Historial De Campos Para El Modelo Personalizado](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
>* [Modelo de aprendizaje automático](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)
