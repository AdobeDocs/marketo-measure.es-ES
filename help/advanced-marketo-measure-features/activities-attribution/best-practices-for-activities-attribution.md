---
description: Prácticas recomendadas para la atribución de actividades - [!DNL Marketo Measure]
title: Prácticas recomendadas para la atribución de actividades
exl-id: 66fb9f47-3912-40a6-b112-3efca789f321
feature: Attribution
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 4%

---

# Prácticas recomendadas para la atribución de actividades {#best-practices-for-activities-attribution}

## Información general {#overview}

El [!DNL Marketo Measure] La función de atribución de actividades permite a los clientes crear puntos de contacto a partir de registros de actividad en su CRM. Este método de creación de puntos de contacto es flexible. Permite crear reglas basadas en los campos &quot;Tarea&quot; o &quot;Evento&quot; para informar a [!DNL Marketo Measure] de qué registros de actividad debe producir puntos de contacto y, por lo tanto, recibir crédito de atribución.

El caso de uso más común de esta función es crear reglas que incorporen interacciones de ventas en los datos de puntos de contacto del comprador. La atribución de actividades permite alinear los datos de ventas y marketing en un recorrido.

Para muchos [!DNL Salesforce] En algunos casos, el objeto Activity puede alojar varios tipos de registros, por lo que es importante que las reglas de Activity sean específicas y se adapten a los registros que intenta traducir en puntos de contacto. Las siguientes prácticas recomendadas ayudan a garantizar que crea puntos de contacto significativos y valiosos a través de la atribución de actividades.

## Práctica recomendada {#best-practice}

Tanto si define reglas de actividad por primera vez como si simplemente revisa las reglas de actividad que se han configurado anteriormente, tenga en cuenta las siguientes prácticas recomendadas.

* Inicio simple
   * Identifique algunos tipos clave de actividades que desee incorporar en su [!DNL Marketo Measure] datos y, a continuación, agregue más tipos a medida que se sienta cómodo con cómo se atribuyen estos puntos de contacto
   * Como se ha mencionado, el caso de uso principal de esta función es crear puntos de contacto que realicen un seguimiento de la eficacia de su equipo de desarrollo de ventas, específicamente llamadas telefónicas salientes y correos electrónicos salientes

>[!NOTE]
>
>Lo es **NO** se recomienda realizar un seguimiento de las actividades de ventas que se producen después de crear la oportunidad, ya que el seguimiento de un proceso de ejecutivos de ventas no ofrece mucha información. El objetivo es rastrear la influencia de las ventas junto con la influencia del marketing, principalmente en el desarrollo de una nueva generación de oportunidad/canalización

* No utilice campos de fórmula para definir las reglas
* Crear reglas específicas y precisas
   * El umbral para la creación de un punto de contacto de actividad debe ser el mismo (o similar) que el de un formulario o la pertenencia a una campaña: respuestas a un correo electrónico saliente o conversaciones telefónicas completadas
* Validar siempre las nuevas reglas en [!DNL Salesforce] antes de guardar y procesar
   * La duplicación de las reglas de actividad en un tipo de informe de &quot;Tareas y eventos&quot; le permite comprender con claridad cuántos puntos de contacto de la regla son exactamente
* Trabaje con su equipo de ventas
   * Al incluir al equipo que más se aproxime a sus registros de actividad o a su herramienta de ventas, se asegurará de que está utilizando los campos correctos para definir sus reglas

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Al revisar las reglas de Atribución de actividad al menos dos veces al año, se garantiza que los puntos de contacto de la Actividad sean precisos y estén actualizados. Asegúrate de que estas reglas no creen puntos de contacto no deseados que diluyan los datos de Atribución del comprador. Una revisión de cómo se definen las reglas ayudará a usted y a su equipo a confiar en la atribución de actividades y en su función en [!DNL Marketo Measure] datos.

Otras razones que podrían déclencheur revisar las reglas de actividad son...

* Rotación en su equipo de marketing
* Cambios en los campos utilizados para definir los registros de actividad
* Cambios o actualizaciones en las herramientas de ventas

>[!MORELIKETHIS]
>
>* [Atribución de actividades](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [Preguntas frecuentes sobre atribución de actividades de ventas](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)
