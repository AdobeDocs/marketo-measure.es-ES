---
description: Tablero de ROI de palabras clave - [!DNL Marketo Measure] - Producto
title: Panel de control del retorno de la inversión de palabra clave
feature: Reporting
exl-id: 9c85a3ad-1806-4e30-b0fb-686760aea587
source-git-commit: f1adf53a9bf3adbc77d52c12dbafb09a28e51178
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 3%

---

# Panel de control del retorno de la inversión de palabra clave {#keyword-roi-dashboard}

El panel ROI de palabras clave proporciona una perspectiva detallada sobre el rendimiento de las campañas de búsqueda de pago. Ofrece un análisis completo de los costes a nivel de palabra clave, los ingresos atribuidos y los nuevos posibles clientes y oportunidades generados, lo que garantiza una comprensión clara del ROI de la palabra clave.

Preguntas que responde el panel:

* ¿Cuál es el ROI de cada palabra clave en Google AdWords, Linkedin y Bing Ads?
* ¿Cómo se desglosan los costes y los ingresos atribuidos por palabras clave individuales?
* ¿Cuántos posibles clientes y oportunidades se crearon a partir de cada palabra clave?

## Componentes del panel {#dashboard-components}

### Tabla de resumen de ROI de palabras clave {#keyword-roi-summary-table}

Tabla que muestra los ingresos atribuidos, los costes y el ROI segmentados por palabras clave individuales para un desglose detallado.

Desglose por palabras clave específicas para ver las oportunidades influenciadas por cada una.

**Columnas:**

* **Palabra clave**
* **Campaña**
* **ID de cuenta de publicidad**
* **Nombre de cuenta de publicidad**
* **Id. de grupo de anuncios**
* **Nombre del grupo de anuncios**
* **Costo**: costos totales de orígenes de datos conectados.
* **Ingresos atribuidos**: Contribución de ingresos total, basada en el modelo de atribución elegido, de Oportunidades con puntos de contacto que se cerraron dentro del período de fecha filtrado
* **Ingresos atribuidos realizados**: Contribución de ingresos totales, basada en el modelo de atribución elegido, de Oportunidades con puntos de contacto dentro del período de fecha filtrado, independientemente del momento en que se cerraron.
* **Ingresos de canalización atribuidos no realizados**: Ingresos de canalización vinculados a puntos de contacto (oportunidades abiertas) creados dentro del período de fecha filtrado.
* **ROI simple**: Ingresos atribuidos divididos por costos en el período de fecha filtrado.
* **ROI realizado**: Ingresos atribuidos realizados divididos por los costos en el período de fecha filtrado.

### Posibles clientes y oportunidades por tabla de palabras clave {#leads-and-opportunities-by-keyword-table}

Tabla que muestra los nuevos posibles clientes, las oportunidades y los costes asociados segmentados por palabras clave individuales para obtener un desglose detallado.

Desglose por palabras clave específicas para ver las oportunidades influenciadas por cada una.

**Columnas:**

* **Palabra clave**
* **Campaña**
* **ID de cuenta de publicidad**
* **Nombre de cuenta de publicidad**
* **Id. de grupo de anuncios**
* **Nombre del grupo de anuncios**
* **Costo**
* **Nuevos posibles clientes**: Número total de nuevos posibles clientes generados, incluidos los posibles clientes tocados y no tocados.
* **Costo por nuevo cliente potencial**: El costo promedio por nuevo cliente potencial, derivado del costo total dividido por el número total de nuevos clientes potenciales.
* **Nuevas oportunidades**: Número total de nuevas oportunidades generadas, incluidas las oportunidades tocadas y no tocadas.
* **Costo por nueva oportunidad**: El costo promedio por nueva oportunidad, derivado del costo total dividido por el número total de nuevas oportunidades.

## Panel de filtro {#filter-pane}

Este tablero está equipado con los siguientes ajustes y filtros:

* Fecha
   * Basado en:
      * Fecha de creación: Posibles clientes, nuevas oportunidades
      * Fecha de coste incurrido: coste
      * Fecha de cierre: ingresos atribuidos (ROI simple), ofertas
      * Touchpoint date: puntos de contacto de los ingresos atribuidos realizados (ROI realizado)
* Modelo de atribución
* Palabra clave
* Campaña
