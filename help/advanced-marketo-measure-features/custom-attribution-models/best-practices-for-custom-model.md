---
description: 'Prácticas recomendadas para el modelo personalizado: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para el modelo personalizado
exl-id: 7c19bb6a-30fc-4cbd-a58e-f20751102afe
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# Prácticas recomendadas para el modelo personalizado {#best-practices-for-custom-model}

## Resumen {#overview}

Además del [!DNL Marketo Measure] de serie, los clientes de Nivel 2 y superiores tienen acceso a un modelo de atribución personalizado.

La variable [!DNL Marketo Measure] El modelo de atribución personalizada permite a los usuarios elegir qué posiciones de punto de contacto de hito y/o etapas personalizadas incluir en el modelo. Además, los usuarios pueden controlar el porcentaje de crédito atribuido a cada fase dentro del modelo (los usuarios pueden definir hasta 6 etapas personalizadas adicionales) o pueden utilizar los valores de porcentaje de atribución sugeridos por el [!DNL Marketo Measure] Modelo de aprendizaje automático.

Hay dos aspectos clave del modelo de atribución personalizado:

**Etapas personalizadas** permiten a los usuarios definir su canal en relación con su negocio y procesos. Las etapas personalizadas deben representar &quot;hitos&quot; a lo largo del recorrido del comprador, de forma similar a la [!DNL Marketo Measure] Los hitos (primer toque, contacto con la creación de posibles clientes, contacto con la creación de oportunidades y contacto cerrado con los resultados) se realizan dentro de los modelos de atribución de existencias. Es crucial que las etapas personalizadas estén correctamente definidas y asignadas dentro de su cuenta para garantizar que [!DNL Marketo Measure] está rastreando correctamente las transiciones de etapa. Esto sirve para identificar qué puntos de contacto deben asociarse con cada fase y atribuir el crédito de forma adecuada. La asignación de fase personalizada es esencialmente una extensión de la &quot;asignación de fase&quot; estándar y debe seguir las mismas prácticas.

>[!NOTE]
>
>Consulte el recurso Prácticas recomendadas de asignación de etapas para obtener más información

**Modelado de atribución personalizado** se define una vez que seleccione el canal de etapas personalizadas. Los usuarios pueden controlar cuánto crédito de atribución se debe asignar a cada fase personalizada, así como al [!DNL Marketo Measure] etapas de hitos. Los usuarios pueden asignar crédito a cada etapa según lo consideren oportuno o hacer referencia a la [!DNL Marketo Measure] Modelo de aprendizaje automático que actúa como &quot;modelo sugerente&quot; basado en datos históricos.

Es fundamental que estos dos aspectos del modelo personalizado se definan correctamente y con precisión para garantizar que [!DNL Marketo Measure] está produciendo un modelo de atribución personalizado preciso.

## Práctica recomendada {#best-practice}

Tanto si está configurando el modelo personalizado por primera vez como si está revisando lo que se ha establecido anteriormente, es importante tener en cuenta las siguientes prácticas recomendadas.

* Inicio simple
   * Identifique las etapas clave que desea agregar al modelo personalizado que son cruciales para el [!DNL Marketo Measure] informes. Normalmente, estas son etapas con las que se mide comúnmente o con las que se pretende obtener información
   * Siempre puede agregar al Modelo personalizado con el paso del tiempo
* Utilice el [!DNL Marketo Measure] Modelo de aprendizaje automático
   * Si tiene dificultades para decidir el desglose de atribución de porcentaje, la variable [!DNL Marketo Measure] El modelo de aprendizaje automático puede ayudarle a tomar decisiones informadas al configurar el modelo de atribución personalizado.
   * Al ver el modelo de aprendizaje automático, los porcentajes de atribución de cada fase reflejan el impacto potencial de los esfuerzos de marketing
      * Un porcentaje mayor significa que el marketing puede influir directamente en el movimiento del canal en ese punto
      * Un porcentaje de atribución menor significa que las etapas son menos importantes para que su equipo pueda monitorizarlas
* Debe definir la parte superior de las etapas de canal en función de las etapas de posible cliente o contacto, no entre ambas
   * Esto significa que debe asegurarse de que todas las personas pasen por esa etapa en el objeto relativo
      * Por ejemplo: Si define el escenario de MQL desde el objeto Lead , todas las personas deben entrar en su sistema como posible cliente y ser marcadas como MQL en su registro de posible cliente para que [!DNL Marketo Measure] para reflejar con precisión qué contacto estaba relacionado con la transición del posible cliente a MQL. Si este no es el caso, y algunas personas progresan a Contact antes de convertirse en MQL como posible cliente, [!DNL Marketo Measure] no será capaz de contabilizar con precisión esto en sus datos de Touchpoint y tendremos que asumir que la persona ya tiene MQLd. [!DNL Marketo Measure] no puede tener en cuenta el salto de escenario, así que deduciremos que las etapas han pasado aunque no lo hayan hecho.
* Asegúrese de que el seguimiento del historial de campos esté habilitado para todos los campos utilizados para definir etapas personalizadas que incorpora
* No utilice campos de fórmula para definir un escenario personalizado
   * Un campo booleano es una práctica recomendada.
* No incorpore etapas personalizadas en el modelo personalizado que coincidan con un [!DNL Marketo Measure] Posición del punto de contacto de Milestone (FT, LC, OC, Cerrado Won/Lost)
   * Si lo hace, estas posiciones siempre se producirán simultáneamente y pueden causar un crédito de atribución inflado a partes del canal.
* Trabaje con su equipo de ventas opp
   * Incorporar al equipo que trabaja más cerca de las etapas y su significado garantizará que esté utilizando las etapas correctas y que estén definidas correctamente

## Práctica recomendada para mantenimiento {#best-practice-for-maintenance}

Al revisar el modelo personalizado al menos dos veces al año, se asegurará de que los informes de atribución personalizados sean precisos y fiables.

Si el modelo personalizado utiliza el modelo de aprendizaje automático, debe revisar su aplicación dentro del modelo personalizado trimestralmente para asegurarse de que el modelo personalizado esté lo más actualizado posible.

Otras razones para esto podrían déclencheur una revisión del Modelo personalizado incluyen..

* Volumen de negocio en su equipo de marketing
* Cualquier cambio en las etapas de CRM
* Actualizaciones en el canal de organizaciones
* Al ver datos de ingresos inexactos en su [!DNL Marketo Measure] informes al aplicar el modelo personalizado
* Ver las posiciones de touchpoint rellenadas que ya no son relevantes para el canal de sus organizaciones

>[!MORELIKETHIS]
>
>* [Modelo de atribución personalizado y configuración](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)
>* [Activar El Seguimiento Del Historial De Campos Para El Modelo Personalizado](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
>* [Modelo de aprendizaje de máquina](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)

