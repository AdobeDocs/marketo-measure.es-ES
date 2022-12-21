---
description: 'Prácticas recomendadas para la atribución de actividades: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para la atribución de actividades
exl-id: 66fb9f47-3912-40a6-b112-3efca789f321
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Prácticas recomendadas para la atribución de actividades {#best-practices-for-activities-attribution}

## Resumen {#overview}

La variable [!DNL Marketo Measure] La función de atribución de actividades permite a los clientes crear puntos de contacto a partir de registros de actividad en su CRM. Este método de creación de puntos de contacto es flexible, ya que le permite crear reglas basadas en campos Tarea o Evento para informar [!DNL Marketo Measure] qué actividad registra debe producir puntos de contacto desde y, posteriormente, recibir crédito de atribución.

El caso de uso más común para esta función es crear reglas que incorporen interacciones de ventas en los datos de puntos de contacto del comprador. La atribución de actividades permite alinear los datos de ventas y marketing en un recorrido.

Para muchos [!DNL Salesforce] , el objeto Actividad puede albergar varios tipos de registros, por lo que es importante que las reglas de Actividad sean específicas y estén adaptadas a los registros que intenta traducir en puntos de contacto. Las siguientes prácticas recomendadas le ayudarán a asegurarse de que está creando puntos de contacto significativos y valiosos a través de la atribución de actividades.

## Práctica recomendada {#best-practice}

Tanto si define reglas de actividad por primera vez como si solo revisa las reglas de actividad que ya se han configurado, tenga en cuenta las siguientes prácticas recomendadas.

* Inicio simple
   * Identifique los tipos clave de actividades que desea incorporar en su [!DNL Marketo Measure] a continuación, añada más tipos a medida que se sienta cómodo con la atribución de estos puntos de contacto.
   * Como se ha mencionado, el caso de uso principal de esta función es crear puntos de contacto que hagan un seguimiento de la eficacia de su equipo de desarrollo de ventas, específicamente llamadas telefónicas salientes y correos electrónicos salientes

>[!NOTE]
>
>Es **NOT** se recomienda realizar el seguimiento de las actividades de ventas que se producen después de crear la oportunidad, ya que el seguimiento de un proceso de ejecutivos de ventas no ofrece mucha perspectiva. El objetivo es rastrear la influencia de las ventas junto con la influencia de Marketing, principalmente en el desarrollo de una nueva generación de oportunidades/canalización

* No utilice campos de fórmula para definir las reglas
* Crear reglas específicas y precisas
   * Desea que el umbral para la creación de un punto de contacto de actividad sea el mismo (o similar) que un relleno de formulario o una pertenencia a campaña, por ejemplo: (Respuestas a un correo electrónico saliente o conversaciones telefónicas completadas)
* Validar siempre las nuevas reglas de [!DNL Salesforce] antes de guardar y procesar
   * La replicación de las reglas de actividad en un tipo de informe &quot;Tareas y eventos&quot; le proporcionará una idea clara de cuántos puntos de contacto se crearán a partir de dicha regla
* Trabaje con su equipo de ventas opp
   * Al incluir el equipo que trabaje más cerca posible de la herramienta de habilitación de ventas o registros de actividad, se asegurará de que está utilizando los campos correctos para definir las reglas

## Práctica recomendada para mantenimiento {#best-practice-for-maintenance}

Al revisar las reglas de atribución de actividad al menos dos veces al año, se asegurará de que los puntos de contacto de la actividad sean precisos y estén actualizados. Asegúrese de que estas reglas no crean puntos de contacto no deseados que diluyan los datos de atribución del comprador. Una revisión del modo en que se definen las reglas le ayudará a usted y a su equipo a sentirse seguros de la atribución de actividades y de su papel en su [!DNL Marketo Measure] datos.

Otras razones que pueden déclencheur para revisar las reglas de actividad son:

* Volumen de negocio en su equipo de marketing
* Cambios en los campos que se utilizan para definir los registros de actividad
* Cambios o actualizaciones en las herramientas de habilitación de ventas

>[!MORELIKETHIS]
>
>* [Atribución de actividades](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [Preguntas frecuentes sobre la atribución de actividades de ventas](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)


