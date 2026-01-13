---
description: Informe de gastos de marketing
title: Informe de gastos de marketing
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
feature: Reporting, Spend Management
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 2%

---


# Informe de gastos de marketing {#report-marketing-spend}

## Tabla de gasto de marketing {#marketing-spend-table}

La tabla Gastos de marketing contiene una nueva columna para mostrar la moneda de cada fila de canal, subcanal y campaña. Esta nueva columna se muestra para todos los clientes, incluso si no tienen habilitada la opción Varias monedas.

La tabla contiene una combinación de distintas monedas. Consulte el panel Gasto en marketing para obtener una suma de cualquier canal, subcanal o campaña en una sola moneda.

## Cargar costes {#upload-costs}

Cuando un usuario descarga el archivo de coste, el archivo también contiene una nueva columna con la moneda de cada fila. Las únicas monedas aceptables son las que se han establecido y almacenado en CRM. Necesita conocer el código abreviado de 3 letras para su moneda (USD, CAD, JPY, EUR) y si se carga un archivo con una moneda no reconocida, la carga del archivo falla.

## Costos de las integraciones de publicidad {#costs-from-ad-integrations}

Cuando [!DNL Marketo Measure] importa el costo desde plataformas conectadas como AdWords, Bing, Facebook o Doubleclick, también usamos la moneda registrada. La moneda se muestra junto al canal, subcanal y campaña cuando se muestra en la tabla Gasto en marketing.

Si la moneda del proveedor de publicidad no coincide con una moneda extraída de CRM, puede que vea el error &quot;Divisas mixtas&quot; en [!DNL Marketo Measure Discover]. Para solucionarlo, el administrador de CRM debe añadir una conversión para la moneda desconocida.

## Migrar a gasto de marketing convertido {#migrate-to-converted-marketing-spend}

Debido a que históricamente el gasto en marketing solo se ha realizado en una sola moneda (USD), se necesita una pequeña cantidad de trabajo para cambiar todos los gastos notificados a la nueva moneda. Incluso si su cuenta no tiene habilitada la opción Varias monedas, si tiene una sola moneda corporativa distinta del USD, deberá realizar esta migración.

1. Descargar el archivo de gasto actual en un CSV
1. La columna de moneda muestra &quot;[!UICONTROL USD]&quot; como la moneda supuesta. Puede reemplazar manualmente todas las instancias de &quot;[!UICONTROL USD]&quot; o usar Buscar+Reemplazar para cambiar todas las instancias de &quot;[!UICONTROL USD]&quot; a su propia moneda corporativa, como &quot;[!UICONTROL EUR]&quot; o &quot;[!UICONTROL GBP]&quot;.
1. Guarde el archivo y vuelva a cargarlo en [!DNL Marketo Measure].
1. Todos los costes notificados se mostrarán ahora como la nueva moneda.
