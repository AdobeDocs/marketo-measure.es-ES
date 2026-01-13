---
description: Tablero de velocidad de oportunidad - [!DNL Marketo Measure] - Producto
title: Panel de control de velocidad de oportunidad
feature: Reporting
exl-id: d02455fd-8fca-435e-8ded-69abbbdcb3a4
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 4%

---


# Panel de control de velocidad de oportunidad {#opportunity-velocity-dashboard}

El tablero de Velocity ofrece una vista dinámica del ritmo al que los posibles clientes se mueven a través de funnel de ventas, lo que proporciona a los especialistas en marketing y a los equipos de ventas una perspectiva esencial de los tiempos de conversión en varios canales. Esta herramienta es muy valiosa para responder a preguntas clave sobre el ciclo de vida de la oportunidad y la eficiencia de la progresión a través de las fases de ventas, lo que le permite optimizar sus estrategias de participación para un crecimiento y conversiones acelerados.

Preguntas que responde este panel:

* En promedio, ¿cuánto tiempo se tarda en convertir una posible cliente?
* En promedio, para cada etapa, ¿cuánto tiempo tarda un posible cliente o contacto en pasar a la siguiente etapa? ¿Cómo cambia este periodo con el tiempo?

## Componentes del panel {#dashboard-components}

### Mosaico de KPI {#kpi-tile}

* **Velocidad de cierre de operaciones**: Cantidad media de días para las oportunidades &quot;Cerradas ganadas&quot; desde el primer paso hasta el cierre.

### Velocidad de oportunidad por fase {#opportunity-velocity-by-stage}

El gráfico de barras muestra la duración media, en días, de las oportunidades invertidas en cada fase de ventas durante un periodo de tiempo específico.

Preguntas que responde el gráfico:

* ¿En qué fase las oportunidades pasan la mayor cantidad de tiempo de media durante el periodo de tiempo especificado?
* ¿En qué se diferencia la duración promedio de las oportunidades en la fase de &quot;Creación de oportunidades&quot; de las fases &quot;Perspectivas&quot; y &quot;Cualificaciones de las oportunidades&quot;?

>[!NOTE]
>Las etapas anteriores a &quot;Creación de oportunidad&quot; utilizarán la fecha de punto de contacto más reciente como fecha de &quot;transición en&quot;.

![Velocidad de oportunidad por gráfico de barras de fase de ventas](assets/lead-velocity-dashboard-1.png)

### Velocidad de oportunidad en el tiempo {#opportunity-velocity-over-time}

El gráfico de líneas de serie temporal muestra el tiempo promedio, en días, que las oportunidades emplean en cada fase de ventas en el periodo de tiempo especificado.

* utilice las funcionalidades de exploración en profundidad y aumento para categorizar los datos por mes, trimestre o año.
* Pase el ratón sobre una línea para ver información detallada.

Preguntas que responde el gráfico:

* ¿Cuáles son las tendencias del tiempo empleado en cada etapa para las oportunidades a lo largo de los meses observados?
* ¿En qué mes experimentaron las oportunidades la progresión más rápida en las fases de venta?

![Gráfico de tendencias de velocidad de oportunidad a lo largo del tiempo](assets/lead-velocity-dashboard-2.png)

### Velocidad de oportunidad por canal {#opportunity-velocity-by-channel}

El gráfico de barras muestra la duración promedio, en días, que los posibles clientes/contactos permanecen en cada fase de funnel, segmentados por Canal.

* Pase el ratón sobre una línea para ver información detallada.

Preguntas que responde el gráfico:

* ¿Qué canal muestra la progresión más rápida en las fases de funnel?
* ¿Cómo varía la velocidad de oportunidad en la fase &quot;Canalización potencial&quot; en los distintos canales?

![Gráfico de comparación de velocidad de oportunidad por canal](assets/lead-velocity-dashboard-3.png)

## Panel de filtro {#filter-pane}

Este tablero está equipado con los siguientes ajustes y filtros:

* Fecha
   * Basado en: Transición en fecha
* Fase
* Canal
* Subcanal
* Campaña
* Segmento
