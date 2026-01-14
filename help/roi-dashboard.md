---
description: Explore el panel ROI para comparar costes, ingresos y ROI entre canales, subcanales y campañas a lo largo del tiempo
title: 'Panel de control de ROI '
feature: Reporting
exl-id: 878db6e0-3ac7-4f4c-b993-bd7a1cfa0638
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 2%

---

# Panel de control de ROI  {#roi-dashboard}

El panel ROI proporciona a los especialistas en marketing una vista granular de la rentabilidad de la inversión en canales, subcanales y campañas. Desglosa meticulosamente los patrones de coste e ingresos, a la vez que destaca métricas como coste por cliente potencial, acuerdo y oportunidad, lo que garantiza una comprensión integral de la atribución de marketing.

**Preguntas que el tablero responde**

* ¿Cuáles fueron los valores de ROI de cada canal, subcanal y campaña?
* ¿Cómo se distribuyeron los costes y los ingresos en cada canal, subcanal y campaña?
* ¿Cuál era el coste por posible cliente, el coste por acuerdo y el coste por oportunidad?

## Componentes del panel {#dashboard-components}

### Mosaicos KPI {#kpi-tiles}

* **Costo**: Costos totales de orígenes de datos conectados y costos cargados manualmente.
* **Ingresos atribuidos**: Contribución de ingresos total, basada en el modelo de atribución elegido, de Oportunidades con puntos de contacto que se cerraron dentro del período de fecha filtrado.
* **Ingresos atribuidos realizados**: Contribución de ingresos totales, basada en el modelo de atribución elegido, de Oportunidades con puntos de contacto dentro del período de fecha filtrado, independientemente del momento en que se cerraron.
* **Total de nuevos posibles clientes**: Número total de nuevos posibles clientes generados, incluidos los posibles clientes tocados y no tocados.
* **Costo por nuevo cliente potencial**: El costo promedio por nuevo cliente potencial, derivado del costo total dividido por el número total de nuevos clientes potenciales.
* **Total de nuevas oportunidades**: Número total de nuevas oportunidades generadas, incluidas las oportunidades tocadas y no tocadas.
* **Costo por nueva oportunidad**: El costo promedio por nueva oportunidad, derivado del costo total dividido por el número total de nuevas oportunidades.
* **Ofertas totales**: La cantidad de oportunidades &quot;Cerradas ganadas&quot;, incluidas las oportunidades sin puntos de contacto.
* **ROI simple**: Ingresos atribuidos divididos por costos en el período de fecha filtrado.
* **ROI realizado**: Ingresos atribuidos realizados divididos por los costos en el período de fecha filtrado.

![ROI realizado: Ingresos atribuidos realizados divididos por costos en la fecha filtrada](assets/roi-dashboard-9.png)

### Gráfico de costes e ingresos por canal {#cost-and-revenue-by-channel-graph}

Gráfico de barras que ilustra el coste y los ingresos, diseñado para ofrecer una perspectiva comparativa de su magnitud en relación con varios canales, subcanales y campañas.

* utilice las funcionalidades de desglose y aumento para categorizar los datos por subcanal y campaña.
* Pase el ratón sobre cada barra para ver los ROI simples y reales.

**Preguntas sobre las respuestas del gráfico**

* ¿Cuáles fueron los valores de ROI de cada canal, subcanal y campaña?
* ¿Existen canales o subcanales periféricos con costes inusualmente altos o bajos en relación con sus ingresos?

![Hay canales periféricos o subcanales con valores inusualmente altos o bajos](assets/roi-dashboard-8.png)

### ROI realizado frente a simple con el tiempo {#realized-vs-simple-roi-over-time}

Gráfico de líneas de series temporales que muestra la comparación entre el ROI realizado y el simple, rastreando su progresión a lo largo del tiempo.

* Pase el ratón sobre una sección del gráfico para ver los ROI simples y realizados.

**Preguntas sobre las respuestas del gráfico**

* ¿Cómo se compara el ROI realizado con el ROI simple en periodos de tiempo específicos?
* ¿Cómo se relaciona la tendencia del ROI realizado con cualquier evento de marketing significativo durante el mismo periodo?

![Cómo se relaciona la tendencia de ROI realizado con cualquier marketing significativo](assets/roi-dashboard-7.png)

### Gráfico de coste con el tiempo {#cost-over-time-graph}

Gráfico de barras apiladas que muestra los costos totales, segmentados por canales asociados para cada mes/trimestre/año.

* utilice las funcionalidades de exploración en profundidad y aumento para categorizar los datos por mes, trimestre o año.
* Pase el ratón sobre un segmento de barra o el espacio entre barras para ver información detallada.

**Preguntas sobre las respuestas del gráfico**

* ¿En qué se diferencia el coste combinado de todos los canales de un trimestre/mes al siguiente?
* ¿Cómo han evolucionado los costes de un canal específico con el paso del tiempo?

![¿Cómo han evolucionado los costes de un canal específico con el paso del tiempo?](assets/roi-dashboard-6.png)

### Gráfico de coste por canal {#cost-by-channel-graph}

Gráfico de barras que muestra el gasto de marketing segmentado por canal, subcanal o campaña.

* utilice las funcionalidades de exploración en profundidad y aumento para categorizar los datos por canal, subcanal o campaña.

**Preguntas sobre las respuestas del gráfico**

* ¿Qué subcanales o campañas dentro de un canal principal tienen la asignación más alta?
* ¿Qué vías de marketing (canal, subcanal o campaña) parecen no tener fondos suficientes en comparación con otras?

![¿Qué avenidas de marketing (canal, subcanal o campaña) parecen no tener fondos suficientes en comparación con otras?](assets/roi-dashboard-5.png)

### Tabla de resumen de ROI {#roi-summary-table}

Tabla que muestra los ingresos atribuidos, los costes y el ROI segmentados por canales individuales para obtener un desglose detallado.

* Haga clic en el icono &quot;+&quot; junto a cada canal para mostrar el desglose por subcanal y campaña.

**Columnas**

* Canal/Subcanal/Campaña
* Coste
* Ingresos atribuidos
* Ingresos atribuidos realizados
* ROI sencillo
* ROI realizado
* Ingresos de canalización atribuidos no realizados: Ingresos de canalización vinculados a puntos de contacto (oportunidades abiertas) creados dentro del período de fecha filtrado.

### Tabla de gasto de marketing {#marketing-spend-table}

Tabla con costes, nuevos posibles clientes, oportunidades y ofertas cerrados segmentados por canales individuales para obtener un desglose detallado.

* Haga clic en el icono &quot;+&quot; junto a cada canal para mostrar el desglose por subcanal y campaña.

**Columnas**

* Canal/Subcanal/Campaña
* Coste
* Nuevos leads
* Coste por nuevo posible cliente
* Nuevas oportunidades
* Costo por nueva oportunidad
* Acuerdos
* Costo por trato

## Panel de filtro {#filter-pane}

Este tablero está equipado con los siguientes ajustes y filtros:

* Fecha
   * Basado en:
      * Fecha de creación: Posibles clientes, nuevas oportunidades
      * Fecha de coste incurrido: coste
      * Fecha de cierre: ingresos atribuidos (ROI simple), ofertas
      * Touchpoint date: puntos de contacto de los ingresos atribuidos realizados (ROI realizado)
* Modelo de atribución
* Canal, Subcanal
* Campaña

>[!MORELIKETHIS]
>
>* [Descubra los conceptos básicos del panel de control](/help/discover-dashboard-basics.md){target="_blank"}
>* [Directiva de visibilidad de datos del panel](/help/dashboard-data-visibility-policy.md){target="_blank"}

