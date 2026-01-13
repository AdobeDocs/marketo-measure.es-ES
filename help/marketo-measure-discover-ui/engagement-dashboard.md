---
description: Tablero de participación - [!DNL Marketo Measure] - Producto
title: Panel de participación
feature: Reporting
exl-id: dc8bcbe4-d470-4cd3-a2d9-804fdebe7121
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---


# Panel de participación {#engagement-dashboard}

El panel de participación rastrea meticulosamente las métricas de participación del usuario. Muestra los puntos de contacto, la cantidad de personas comprometidas y el promedio de puntos de contacto por persona. Utilice el gráfico de barras de series temporales para una vista mensual, trimestral o anual, y el gráfico de barras para obtener información detallada sobre el canal, el subcanal y la campaña. Esta herramienta es esencial para comprender los patrones de participación y ajustar las estrategias de participación.

Rastreamos la interacción de cada cliente como puntos de contacto del usuario (UT), los puntos de datos recopilados &quot;sin procesar&quot;, que sirven como base para las métricas de participación en nuestro panel. No todos los TU evolucionan hacia puntos de contacto del comprador (BT) o puntos de contacto de atribución del comprador (BAT), ya que estos son resultados seleccionados para atribuir interacciones específicas del cliente a actividades relacionadas con los ingresos. Es importante tener en cuenta que las reglas de supresión no afectan a las UT ni al panel de participación.

* **Puntos de contacto del usuario**: puntos de contacto creados a partir de todas las participaciones.
* **Puntos de contacto del comprador**: puntos de contacto seleccionados para la atribución de contactos y posibles clientes. Los BT no están vinculados a Oportunidades y no tienen ingresos asociados.
* **Puntos de contacto de atribución del comprador**: Puntos de contacto seleccionados para atribución de oportunidad. Las MTD tienen implicaciones en los ingresos, ya que están vinculadas a Oportunidades.

El uso solo de MTD o MTD para medir la participación subestimaría el verdadero alcance de las interacciones de los clientes, ya que la participación es más amplia que solo la atribución.

Preguntas que responde el panel:

* ¿Cuántas personas estaban comprometidas? ¿Cuál es el número promedio de toques por persona comprometida?
* ¿En qué se diferencia el número de puntos de contacto de las personas tocadas dentro de un canal, subcanal o campaña específicos?
* ¿Cuántos puntos de contacto había en un canal o subcanal determinado? ¿Cómo cambió con el tiempo?

>[!NOTE]
>Las métricas de participación de cuenta y oportunidad están programadas para su lanzamiento en el primer semestre de 2024.

## Componentes del panel {#dashboard-components}

### Mosaicos KPI {#kpi-tiles}

* Puntos de contacto: número total de puntos de contacto sin procesar generados.
   * Los puntos de contacto de comprador y los puntos de contacto de atribución de comprador son resultados de atribución que se crean seleccionando puntos de contacto específicos para el crédito. No todos los puntos de contacto se seleccionan como BT y BAT.
* Personas tocadas: número total de personas que tienen puntos de contacto.
* Touchpoints per Person: Cantidad promedio de puntos de contacto por persona que se han tocado.

### Puntos de contacto y personas tocadas a lo largo del tiempo {#touchpoints-and-people-touched-over-time}

El gráfico de barras de series temporales muestra el número de puntos de contacto, personas tocadas y puntos de contacto por persona para cada mes, trimestre y año.

* utilice las funcionalidades de exploración en profundidad y aumento para categorizar los datos por mes, trimestre o año.
* Pase el ratón sobre una barra o una línea para mostrar información detallada.

Preguntas que responde el gráfico:

* ¿Cómo ha evolucionado el número de puntos de contacto y Personas tocadas con el paso del tiempo?
* ¿En qué se parecen los puntos de contacto por persona de un trimestre o mes al siguiente?

![Serie temporal del panel de participación de puntos de contacto y personas tocadas](assets/engagement-dashboard-1.png)

### Puntos de contacto/Personas tocadas por canal {#touchpoints-people-touched-by-channel}

Gráfico de barras que muestra los puntos de contacto o las personas tocadas segmentadas por canal, subcanal o campaña.

* utilice las funcionalidades de desglose y aumento para categorizar los datos por subcanal y campaña.
* Pase el ratón sobre cada barra para ver los puntos de contacto o las personas tocadas.

Preguntas que responde el gráfico:

* ¿Qué canal, subcanal o campaña logró la mayor participación?
* ¿En qué se diferencia el número de puntos de contacto de las personas tocadas dentro de un canal, subcanal o campaña específicos?

![Gráfico de barras del panel de participación de puntos de contacto y personas por canal](assets/engagement-dashboard-2.png)

## Panel de filtro {#filter-pane}

Este tablero está equipado con los siguientes ajustes y filtros:

* Fecha (basada en la fecha de Touchpoint)
* Canal, Subcanal
* Campaña
