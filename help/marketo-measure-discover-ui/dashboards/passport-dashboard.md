---
description: Panel de Passport - [!DNL Marketo Measure] - Producto
title: Panel de Passport
feature: Reporting
source-git-commit: 436e30c2a4138d780232d6ba9e64456d6277ac9b
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 8%

---

# Panel de Passport {#passport-dashboard}

El panel Passport ofrece a los especialistas en marketing una vista dinámica de los posibles clientes, los contactos y las oportunidades a medida que realizan la transición en varias fases dentro de un periodo especificado. Al filtrar por una fecha específica, los usuarios también pueden obtener una instantánea de los registros de ese día.

Preguntas que el tablero responde:

* ¿Cuántos posibles clientes, contactos u oportunidades existían en cada etapa no terminal en un día elegido?
* Durante un periodo especificado, ¿cuántos posibles clientes o contactos distintos han progresado en cada fase transitoria?
   * _Ejemplo_: Si el posible cliente A estaba en la fase 1 el 1/1/2023 y avanzó a la fase 5 el 31/3/2023, el análisis del pasaporte del primer trimestre de 2023 contaría el posible cliente A en las fases 1 a 5.
* ¿Cuántas oportunidades únicas pasaron por cada etapa transitoria durante un lapso de tiempo determinado?

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
    <td>Oportunidades</td>
    <td><li>Cada fase muestra el número de oportunidades con MTD que han pasado a través de ellas en un periodo de tiempo determinado.</li>
<ul style="padding-left: 30px;"><li>Si una oportunidad progresa a través de varias etapas dentro de ese intervalo, se cuentan en cada etapa que pasa.</li></ul>
<li>Se excluyen las fases de terminal como "Cerrado ganado" y "Cerrado perdido".</li>
<li>Las fechas de inicio y finalización son ambas inclusivas.</li>
<br/><img src="assets/passport-dashboard-1.png" width="600"></td>
    <td rowspan="2">Fecha de transición</td>
    <td></td>
    <td rowspan="2"><li>Fecha</li>
<li>Canal</li>
<li>Subcanal</li>
<li>Campaña</li>
<li>Segmentos</li></td>
  </tr>
  <tr>
    <td>Clientes potenciales/contactos</td>
    <td><li>Cada fase muestra el número de posibles clientes o contactos con BT que han pasado a través de ellos en un periodo de tiempo determinado.</li>
<ul style="padding-left: 30px;"><li>La preferencia establecida en Configuración &gt; Configuración de atribución &gt; Objeto de panel predeterminado determina si se mostrará "Posible cliente" o "Contacto".</li></ul>
<li>Se excluyen las fases de terminal como "Cerrado ganado" y "Cerrado perdido".</li>
<li>Las fechas de inicio y finalización son ambas inclusivas.</li>
<br/><img src="assets/passport-dashboard-2.png" width="600"></td>
    <td><li>Identificador de contacto/posible cliente</li>
<li>Correo electrónico del posible cliente/contacto</li>
<li>Fecha de creación</li>
<li>Etapa actual</li>
<li>Transición de entrada de Fecha</li>
<li>Fecha de transición de salida</li></td>
  </tr>
</tbody>
</table>

>[!MORELIKETHIS]
>
>[Descubra los conceptos básicos del panel](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
