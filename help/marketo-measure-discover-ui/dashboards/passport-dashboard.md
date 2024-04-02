---
description: Panel de Passport - [!DNL Marketo Measure] - Producto
title: Panel de Passport
feature: Reporting
exl-id: 0fbd9714-7d9c-4330-b35f-d011e17c3bfe
source-git-commit: 403b31acce25ddc9c1dcafbd53008b6e2868b3df
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 3%

---

# Panel de Passport {#passport-dashboard}

El panel Passport ofrece a los especialistas en marketing una vista dinámica de los posibles clientes, los contactos y las oportunidades a medida que realizan la transición en varias fases dentro de un periodo especificado. Al filtrar por una fecha específica, los usuarios también pueden obtener una instantánea de los registros de ese día.

**Preguntas que el tablero responde:**

* ¿Cuántos posibles clientes, contactos u oportunidades existían en cada etapa no terminal en un día elegido?
* Durante un periodo especificado, ¿cuántos posibles clientes o contactos distintos han progresado en cada fase transitoria?
   * _Ejemplo_: Si el posible cliente A estaba en la fase 1 el 1/1/2023 y avanzó a la fase 5 el 31/3/2023, el análisis del pasaporte del primer trimestre de 2023 contaría el posible cliente A en las fases 1 a 5.
* ¿Cuántas oportunidades únicas pasaron por cada etapa transitoria durante un lapso de tiempo determinado?

## Componentes del panel {#dashboard-components}

### Oportunidades en fase por nombre de etapa {#opportunities-in-stage-by-stage-name}

* Cada fase muestra el número de oportunidades con puntos de contacto que han pasado a través de ellas en un periodo de tiempo determinado.
   * Si una oportunidad progresa a través de múltiples etapas dentro de ese intervalo, se cuenta en cada etapa que pasa.
* Se excluyen las fases de terminal como &quot;Cerrado ganado&quot; y &quot;Cerrado perdido&quot;.
* Las fechas de inicio y finalización son ambas inclusivas.

![](assets/passport-dashboard-1.png)

### Posibles clientes o contactos en la fase por nombre de fase {#leads-or-contacts-in-stage-by-stage-name}

* Cada fase muestra el número de posibles clientes o contactos con puntos de contacto que han pasado a través de ellos en un periodo de tiempo determinado.
   * La preferencia establecida en Configuración > Configuración de atribución > Objeto de panel predeterminado determina si se mostrará &quot;Posible cliente&quot; o &quot;Contacto&quot;.
   * Si un posible cliente o contacto progresa a través de varias etapas dentro de ese intervalo, se cuenta en cada etapa que pasa.
* Se excluyen las fases de terminal como &quot;Cerrado ganado&quot; y &quot;Cerrado perdido&quot;.
* Las fechas de inicio y finalización son ambas inclusivas.

![](assets/passport-dashboard-2.png)

## Panel de filtro {#filter-pane}

Este tablero está equipado con los siguientes ajustes y filtros:

* Fecha (según la fecha de transición)
* Canal, Subcanal
* Campaña
* Segmentos

>[!MORELIKETHIS]
>
>* [Descubra los conceptos básicos del panel](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
>* [Directiva de visibilidad de datos del panel](/help/marketo-measure-discover-ui/dashboards/dashboard-data-visibility-policy.md){target="_blank"}
