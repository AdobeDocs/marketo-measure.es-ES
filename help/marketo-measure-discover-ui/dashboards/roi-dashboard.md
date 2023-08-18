---
description: Tablero de ROI - [!DNL Marketo Measure] - Producto
title: Tablero de ROI
feature: Reporting
source-git-commit: dc4dd001d319f13ebd1c4ce418acf2faa27cfe81
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 17%

---

# Tablero de ROI {#roi-dashboard}

El panel ROI proporciona a los especialistas en marketing una vista granular de la rentabilidad de la inversión en canales, subcanales y campañas. Desglosa meticulosamente los patrones de coste e ingresos, a la vez que destaca métricas como coste por cliente potencial, acuerdo y oportunidad, lo que garantiza una comprensión integral de la atribución de marketing.

Preguntas que el tablero responde:

* ¿Cuáles fueron los valores de ROI de cada canal, subcanal y campaña?
* ¿Cómo se distribuyeron los costes y los ingresos en cada canal, subcanal y campaña?
* ¿Cuál era el coste por posible cliente, el coste por acuerdo y el coste por oportunidad?

<table style="table-layout:auto"> 
<tbody>
 <tr> 
   <th>Componente</th> 
   <th>Descripción</th>
   <th>Tipo de fecha</th>
   <th>Explorar los campos</th>
   <th>Filtros</th>
  </tr>
  <tr>
    <td>Mosaico de coste</td>
    <td>Costo total incurrido</td>
    <td>Fecha de coste incurrido</td>
    <td><li>Identificación de la campaña</li>
<li>Nombre de la campaña</li>
<li>Canal</li>
<li>Subcanal</li>
<li>Fecha</li>
<li>Gastos</li></td>
    <td rowspan="15"><li>Fecha</li>
<li>Modelo de atribución (configuración)</li>
<li>Canal</li>
<li>Subcanal</li>
<li>Campaña</li></td>
  </tr>
  <tr>
    <td>Mosaico de ingresos atribuidos</td>
    <td>Ingresos atribuidos totales</td>
    <td>Fecha de cierre</td>
    <td><li>Identificación de oportunidad</li>
<li>Nombre de la oportunidad</li>
<li>Fecha de creación de la oportunidad</li>
<li>Fecha de cierre de oportunidad</li>
<li>Está cerrado (S/N)</li>
<li>Está ganado (S/N)</li>
<li>Modelo de atribución</li>
<li>Ingresos atribuidos</li>
<li>Ingresos realizados</li></td>
  </tr>
  <tr>
    <td>Mosaico de ROI simple</td>
    <td>ROI heredado: ingresos divididos por costes en un periodo de tiempo determinado. 
    <li>Coste: Coste incurrido en el período de fecha filtrado.</li>
    <li>Ingresos: Ingresos procedentes de oportunidades "ganadas cerradas" en ese periodo de tiempo.</li></td>
    <td>Fecha de cierre</td>
    <td>N/A</td>
  </tr>
  <tr>
    <td>Mosaico de ROI realizado</td>
    <td>ROI realizado: representa los resultados tangibles de los puntos de contacto generados por las campañas en un lapso de tiempo especificado.
    <li>Coste: Coste incurrido en el período de fecha filtrado.</li>
    <li>Ingresos: ingresos obtenidos a partir de todos los acuerdos "Cerrados ganados", específicamente aquellos influidos por puntos de contacto dentro del periodo de tiempo establecido.</li>
    <br/><img src="assets/roi-dashboard-1.png" width="600"></td>
    <td>Fecha de coste incurrido</td>
    <td>N/A</td>
  </tr>
  <tr>
    <td>Mosaico de nuevos posibles clientes totales</td>
    <td>Número total de posibles clientes nuevos (recuento completo) generados en un período especificado, incluidos los posibles clientes tocados y no tocados.</td>
    <td>Fecha de creación</td>
    <td rowspan="2">
    <li>Identificación del lead</li>
    <li>Email de cliente potencial</li>
    <li>Fecha LC</li></td>
  </tr>
  <tr>
    <td>Costo por nuevo mosaico de posibles clientes</td>
    <td>Número total de posibles clientes nuevos (recuento completo) dividido por costes.</td>
    <td>Fecha de creación</td>
  </tr>
  <tr>
    <td>Mosaico Total De Nuevas Oportunidades</td>
    <td>Número total de nuevas oportunidades (recuento completo) generadas en un período especificado, incluidos los posibles clientes tocados y no tocados.</td>
    <td>Fecha de creación</td>
    <td rowspan="2">
    <li>Identificación de oportunidad</li>
    <li>Nombre de la oportunidad</li>
    <li>Fecha de creación de la oportunidad</li>
    <li>Fecha de cierre de oportunidad</li>
    <li>Está cerrado (S/N)</li>
    <li>Está ganado (S/N)</li>
    <li>Etapa actual</li></td>
  </tr>
  <tr>
    <td>Costo por nuevo mosaico de oportunidad</td>
    <td>Número total de nuevas oportunidades (recuento completo) dividido por costes.</td>
    <td>Fecha de creación</td>
  </tr>
  <tr>
    <td>Mosaico de ofertas totales</td>
    <td>Número total de operaciones cerradas en un periodo especificado, incluidas las que no tienen puntos de contacto asociados.</td>
    <td>Fecha de cierre</td>
    <td><li>Identificación de oportunidad</li>
<li>Nombre de la oportunidad</li>
<li>Fecha de creación de la oportunidad</li>
<li>Fecha de cierre de oportunidad</li>
<li>Está cerrado (S/N)</li>
<li>Está ganado (S/N)</li>
<li>Etapa actual</li>
<li>Moneda</li>
<li>Modelo de atribución</li>
<li>Ingresos atribuidos</li>
<li>Ingresos realizados</li></td>
  </tr>
  <tr>
    <td>Gráfico de costes e ingresos por canal</td>
    <td>Gráfico de barras que ilustra el coste y los ingresos, diseñado para ofrecer una perspectiva comparativa de su magnitud en relación con varios canales, subcanales y campañas.
    <br/><img src="assets/roi-dashboard-2.png" width="600"></td>
    <td>Fecha de cierre</td>
    <td>Coste:
<br/>
<li>Identificación de la campaña</li>
<li>Nombre de la campaña</li>
<li>Canal</li>
<li>Subcanal</li>
<li>Fecha de coste incurrido</li>
<li>Moneda</li>
<li>Gastos</li>
<p>
Ingresos:
<br/>
<li>Identificación de oportunidad</li>
<li>Nombre de la oportunidad</li>
<li>Fecha de creación de la oportunidad</li>
<li>Fecha de cierre de oportunidad</li>
<li>Está cerrado (S/N)</li>
<li>Está ganado (S/N)</li>
<li>Ingresos atribuidos</li>
<li>Modelo de atribución</li>
<li>Ingresos atribuidos</li>
<li>Ingresos realizados</li></td>
  </tr>
  <tr>
    <td>Rendimiento de la inversión realizado frente a simple con el tiempo</td>
    <td>Gráfico de líneas de series temporales que muestra la comparación entre el ROI realizado y el simple, rastreando su progresión a lo largo del tiempo.
    <br/><img src="assets/roi-dashboard-3.png" width="600"></td>
    <td>ROI sencillo: fecha de coste incurrido y fecha de cierre
    <p>ROI realizado: fecha de coste incurrido y fecha de punto de contacto</td>
    <td>N/A</td>
  </tr>
  <tr>
    <td>Gráfico de coste con el tiempo</td>
    <td>Gráfico de barras apiladas que muestra los costes totales trimestrales/mensuales, segmentados por canales individuales para obtener un desglose detallado.
    <br/><img src="assets/roi-dashboard-4.png" width="600"></td>
    <td>Fecha de coste incurrido</td>
    <td rowspan="2"><li>Identificación de la campaña</li>
<li>Nombre de la campaña</li>
<li>Canal</li>
<li>Subcanal</li>
<li>Fecha de coste incurrido</li>
<li>Moneda</li>
<li>Gastos</li></td>
  </tr>
  <tr>
    <td>Gráfico de coste por canal</td>
    <td>Gráfico de barras que muestra el gasto de marketing segmentado por canales.
    <br/><img src="assets/roi-dashboard-5.png" width="600"></td>
    <td>Fecha de coste incurrido</td>
  </tr>
  <tr>
    <td>Tabla de resumen de ROI</td>
    <td>Tabla que muestra los ingresos atribuidos, los costes y el ROI segmentados por canales individuales para obtener un desglose detallado.
<p>
<b>Columnas:</b>
<p>
<li>Canal/Subcanal/Campaña</li>
<li>Coste</li>
<li>Ingresos atribuidos</li>
<li>ROI sencillo</li>
<li>ROI realizado</li>
<li>Canalización sin realizar</li>
<ul style="padding-left: 30px;"><li>Canalización desde puntos de contacto (oportunidades abiertas) asociados a campañas en un periodo de tiempo determinado</li></ul></td>
    <td>ROI sencillo: fecha de coste incurrido y fecha de cierre
    <p>ROI realizado: fecha de coste incurrido y fecha de punto de contacto</td>
    <td>N/A</td>
  </tr>
  <tr>
    <td>Tabla de gasto de marketing</td>
    <td>Tabla que muestra los costes, los nuevos posibles clientes, las oportunidades y las ofertas cerradas segmentadas por canales individuales para obtener un desglose detallado.
<p>
<b>Columnas:</b>
<p>
<li>Canal/Subcanal/Campaña</li>
<li>Coste</li>
<li>Nuevos posibles clientes</li>
<li>Coste por nuevo posible cliente</li>
<li>Nuevas oportunidades</li>
<li>Costo por nueva oportunidad</li>
<li>Acuerdos cerrados</li>
<li>Coste por acuerdo cerrado</li></td>
    <td><li>Coste: Fecha de coste incurrido</li>
<li>Nuevos posibles clientes: Fecha de creación</li>
<li>Nuevas oportunidades: Fecha de creación</li>
<li>Ofertas Cerradas: Fecha de cierre</li></td>
    <td>N/A</td>
  </tr>
</tbody>
</table>
