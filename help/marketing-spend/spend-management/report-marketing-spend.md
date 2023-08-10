---
unique-page-id: 27656737
description: Informe de gasto en marketing - [!DNL Marketo Measure] - Documentación del producto
title: Informe de gastos de marketing
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
feature: Reporting, Spend Management
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 1%

---

# Informe de gastos de marketing {#report-marketing-spend}

## Tabla de gasto de marketing {#marketing-spend-table}

La tabla de gasto en marketing ahora contiene una nueva columna para mostrar la moneda de cada fila de canal, subcanal y campaña. Esta nueva columna se mostrará para todos los clientes, incluso si no tienen habilitada la opción Varias monedas.

La tabla ahora contiene una combinación de distintas monedas. Consulte el panel Gasto en marketing si necesita obtener una suma de cualquier canal, subcanal o campaña en una sola moneda.

## Cargar costes {#upload-costs}

Cuando un usuario descarga el archivo de coste, el archivo también contiene una nueva columna con la moneda de cada fila. Las únicas monedas aceptables son las que se han establecido y almacenado en CRM. Necesitará conocer el código abreviado de 3 letras de su moneda (es decir, USD, CAD, JPY, EUR) y si un archivo se carga con una moneda no reconocida, la carga del archivo fallará.

## Costos de las integraciones de publicidad {#costs-from-ad-integrations}

Cuándo [!DNL Marketo Measure] importa el coste desde plataformas conectadas como AdWords, Bing, Facebook o Doubleclick, también utilizamos la divisa registrada. La moneda se mostrará junto al canal, subcanal y campaña cuando se muestre en la tabla Gasto en marketing.

Si la moneda del proveedor de publicidad no coincide con una moneda extraída de CRM, puede que vea el error &quot;Divisas mixtas&quot; en [!DNL Marketo Measure Discover] porque no pudimos hacer una conversión en esa moneda. Para solucionarlo, el administrador de CRM debe añadir una conversión para la moneda desconocida.

## Migrar a gasto de marketing convertido {#migrate-to-converted-marketing-spend}

Debido a que históricamente nuestro gasto en marketing solo se ha realizado en una sola moneda (USD), se necesita una pequeña cantidad de trabajo para cambiar todo el gasto notificado a la nueva moneda. Incluso si su cuenta no tiene habilitada la opción Varias monedas, si tiene una sola moneda corporativa distinta del USD, querrá realizar esta migración.

1. Descargar el archivo de gasto actual en un CSV
1. La columna de moneda mostrará &quot;[!UICONTROL USD]&quot; como la moneda supuesta. Puede reemplazar manualmente todas las apariciones de &quot;[!UICONTROL USD]&quot; o use Buscar+Reemplazar para cambiar todos los &quot;[!UICONTROL USD]&quot; instancias de a su propia moneda corporativa, como &quot;[!UICONTROL EUR]&quot; o &quot;[!UICONTROL GBP]&quot; por ejemplo.
1. Guarde el archivo y vuelva a cargarlo en [!DNL Marketo Measure].
1. Todos los costes notificados se mostrarán ahora como la nueva moneda.
