---
unique-page-id: 27656737
description: Gasto en marketing de informes - [!DNL Marketo Measure] - Documentación del producto
title: Gasto en marketing de informe
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# Gasto en marketing de informe {#report-marketing-spend}

## Tabla de gasto de marketing {#marketing-spend-table}

La tabla Gastos de marketing ahora contendrá una nueva columna para mostrar la moneda de cada fila Canal, Subcanal y Campaña. Esta nueva columna se mostrará para todos los clientes, aunque no tengan activada la opción Varias monedas.

La tabla ahora contendrá una mezcla de distintas monedas. Consulte el panel Gastos de marketing si necesita obtener una suma de canales, subcanales o campañas en una sola moneda.

## Cargar costes {#upload-costs}

Cuando un usuario descarga el archivo de coste, el archivo también contiene una nueva columna con la moneda para cada fila. Las únicas monedas aceptables son las que se han establecido y almacenado en CRM. Deberá conocer el código abreviado de 3 letras para su moneda (es decir, USD, CAD, JPY, EUR) y si un archivo se carga con una moneda no reconocida, la carga del archivo fallará.

## Costes de integraciones de publicidad {#costs-from-ad-integrations}

When [!DNL Marketo Measure] importa el coste de plataformas conectadas como AdWords, Bing, Facebook o Doubleclick, también utilizamos la moneda registrada. La moneda se mostrará junto al canal, el subcanal y la campaña cuando se muestre en la tabla Gastos de marketing .

Si la moneda del proveedor de publicidad no coincide con una moneda extraída de CRM, puede que aparezca el error &quot;Monedas mixtas&quot; en [!DNL Marketo Measure Discover] porque no hemos podido realizar una conversión en esa moneda. Para solucionarlo, su administrador de CRM debe agregar una conversión para la moneda desconocida.

## Migrar a inversión convertida en marketing {#migrate-to-converted-marketing-spend}

Debido a que nuestro gasto en marketing históricamente solo ha estado en una moneda única (USD), hay una pequeña cantidad de trabajo necesario para cambiar todo el gasto registrado a la nueva moneda. Incluso si su cuenta no tiene activada la opción Varias monedas, si tiene una sola moneda corporativa que no sea USD, querrá realizar esta migración.

1. Descargar el archivo de gastos actual en un archivo CSV
1. La columna de moneda mostrará &quot;[!UICONTROL USD]&quot; como la moneda asumida. Puede reemplazar manualmente todas las ocurrencias de &quot;[!UICONTROL USD]&quot; o utilice Buscar+Reemplazar para cambiar todas las &quot;[!UICONTROL USD]&quot; a su propia moneda corporativa, como &quot;[!UICONTROL EUR]&quot; o &quot;[!UICONTROL GBP]&quot;, por ejemplo.
1. Guarde el archivo y vuelva a cargarlo en [!DNL Marketo Measure].
1. Todos los costes notificados ahora se mostrarán como la nueva moneda.
