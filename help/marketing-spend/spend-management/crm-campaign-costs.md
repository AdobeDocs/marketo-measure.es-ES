---
unique-page-id: 18874688
description: Costes de campaña de CRM - [!DNL Marketo Measure] - Documentación del producto
title: Costes de campaña de CRM
exl-id: d967cabe-b9f1-4ea1-a81b-e4484c703ecf
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '1230'
ht-degree: 0%

---

# Costes de campaña de CRM {#crm-campaign-costs}

Más [!DNL Marketo Measure] los clientes de utilizan campañas CRM para realizar el seguimiento de actividades de marketing sin conexión. Los especialistas en marketing que utilizan estas campañas también supervisarán los costes dentro de CRM, por lo que esta función facilita a los especialistas en marketing al permitir [!DNL Marketo Measure] para leer esos costes y aplicarlos al gasto de marketing registrado en [!DNL Marketo Measure]. Hasta la fecha, los clientes han tenido que introducir manualmente los costes de cada campaña por mes, pero con la información necesaria que se nos ha proporcionado, [!DNL Marketo Measure] puede automatizar este proceso para que los especialistas en marketing puedan invertir más tiempo analizando su gasto y su ROI.

## Disponibilidad {#availability}

Esta función está disponible para todas las [!DNL Salesforce] y clientes de Dynamics.

## Cómo funciona {#how-it-works}

[!DNL Marketo Measure] primero busca campañas que se hayan &quot;habilitado&quot; para puntos de contacto, por lo que se ha creado una regla de sincronización de campaña coincidente o el valor Habilitar puntos de contacto de comprador es &quot;Incluir todos los miembros de campaña&quot; o &quot;Incluir miembros de campaña &#39;respondidos&#39;&quot;. Además, [!DNL Marketo Measure] debe importar los valores correctos y saber distribuir los costes, por lo que es necesario que los campos siguientes contengan un valor:

**[!DNL Salesforce]**: ActualCost, StartDate, EndDate

**[!DNL Microsoft Dynamics]**: coste total actualcost, real start, real-end

Si falta un valor en alguno de los 3 campos, [!DNL Marketo Measure] no importa los costes. Puede corregirlo actualizando el registro de campaña en CRM. También es importante tener en cuenta que no importaremos los costes si se establece explícitamente en $0 porque [!DNL Salesforce] trata blank y $0 como lo mismo.

Para [!DNL Marketo Measure] para determinar la distribución de una campaña entre meses, utilizamos la fecha de inicio y finalización de la campaña y distribuimos la cantidad uniformemente por día.

![](assets/1.jpg)

En este ejemplo, tenemos una campaña que dura 109 días, por lo que con un costo total de 18.000 dólares, el gasto diario llega a ~$165,14.

Según la cantidad de días por mes, obtenemos estos totales mensuales, como puede ver en la tabla:

Julio de 2018: (18.000/109 dólares) x 31 = 5.119,27 dólares

Ago de 2018: (18.000/109 dólares) x 31 = 5.119,27 dólares

Septiembre de 2018: (18.000/109 dólares) x 30 = 4.954,13 dólares

Octubre de 2018: (18.000/109 dólares) x 17 = 2.807,34 dólares

## Gasto registrado históricamente {#historical-reported-spend}

¡No te preocupes! Si ha introducido gastos para campañas de las que hemos hecho un seguimiento en el pasado y que estaban asignados a una campaña de CRM, no anularemos ninguno de los costes que ha introducido. Si se modifica la misma campaña en CRM, todavía la ignoraremos y daremos prioridad a los cambios que haya realizado anteriormente en la carga CSV.

Si prefiere que el coste de la campaña de CRM avance, lo que puede hacer es cambiar el valor en el CSV a $0, lo que anulará la entrada. Luego, la próxima vez que ejecutemos nuestros trabajos para importar los costos, analizaremos los registros que hayan sido editados anteriormente y los incorporaremos.

## Campañas sin puntos de contacto {#campaigns-with-no-touchpoints}

Muchos especialistas en marketing eligen informar de los gastos de marketing en campañas CRM que no generaron ningún punto de contacto o que, a sabiendas, no tienen miembros de campaña para los fines de rastrear los gastos. Siempre y cuando se rellenen los 3 campos (fecha de inicio, fecha de finalización, coste) y la campaña esté habilitada para los puntos de contacto, [!DNL Marketo Measure] seguirá incluyendo ese coste independientemente de si hay o no puntos de contacto asociados a él.

Esto podría ser útil para rastrear el gasto en costos o herramientas de marketing excesivos para resumir eso en los cálculos de ROI.

## Sincronización del programa de Marketo {#marketo-program-sync}

Si introduce programas de Marketo en CRM como campañas, debe asegurarse de que la asignación Fecha de inicio, Fecha de finalización y Coste de período esté configurada en los campos CRM requeridos. Dado que no hay ninguna asignación al campo Habilitar puntos de contacto de comprador , tendrá que habilitar estas campañas para que sepamos que se obtienen los costes correspondientes.

## Edición de los costes {#editing-the-costs}

Una vez importada una campaña desde CRM, se tratará de forma similar a un proveedor de anuncios de API y no aparecerá en el CSV para realizar ningún cambio en los costes.

Cualquier cambio en el coste o la distribución debe realizarse en el CRM para que podamos señalar a un solo punto de verdad.

## Preguntas frecuentes {#faq}

**He realizado un cambio en mi campaña: ¿cuándo debo esperar ver los cambios en la tabla Gastos de marketing o en mis informes?**

3 a 4 horas

**Tengo la fecha de inicio, la fecha de finalización y el coste completado, pero ¿por qué mis costes aún no aparecen en [!DNL Marketo Measure]?**

Compruebe que tiene el valor Habilitar punto de contacto de comprador establecido en &quot;Incluir todos los miembros de campaña&quot; o al menos en &quot;Incluir miembros de campaña &#39;respondidos&#39;, o que ha creado una regla de sincronización de campaña personalizada que incluya esta campaña. Si lo ha confirmado y aún no ve la campaña, póngase en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;} para que podamos comprobar que las campañas se importan correctamente.

**Necesito cambiar la distribución de mi campaña para que pueda pesarla más en ciertos meses. ¿Cómo lo hago?**

La distribución de los costes se basa exclusivamente en una distribución uniforme desde la fecha de inicio hasta la de finalización. Desafortunadamente, no podemos cambiarlo para que sus costos tengan una ponderación diferente a la establecida. Puede controlar esto ajustando la fecha de inicio y finalización de la campaña, ya que cada día del mes importa.

**Tengo los costes configurados en mi Campaña principal. ¿Cómo se asigna el coste de la Campaña principal a las Campañas secundarias?**

En realidad, la forma en que se extraerán los costes será directamente desde una sola campaña, independientemente de cualquier relación con el padre o el hijo. Se recomienda que el coste se destine a las Campañas infantiles, junto con las fechas de la campaña, y que luego se utilice el elemento principal como campaña general donde la campaña principal no se habilite para los puntos de contacto.

**¿Cómo puedo cambiar el coste de un mes en [!DNL Marketo Measure]?**

Dado que confiamos en CRM como la única fuente de verdad, todos los cambios deben realizarse en CRM. Una vez que la campaña ha sido importada por [!DNL Marketo Measure], los valores de Campaña no se pueden editar en [!DNL Marketo Measure] o en el archivo CSV.

**¿En qué escenario aparecería una campaña en la tabla Gastos de marketing, y luego ya no aparecerá?**

Seguiremos requiriendo que los tres campos clave tengan un valor: Fecha de inicio, Fecha de finalización y Coste. Nuestro comportamiento predeterminado es que solo importamos campañas con un valor bueno a más de $0. Idealmente, importaríamos campañas en las que haya un valor explícito de 0 $ y no importaríamos las que se queden en blanco, pero la API de Salesforce las importa como 0 $ independientemente del valor. Además, si el valor Habilitar punto de contacto de comprador cambia de &quot;Incluir todo&quot; o &quot;Incluir &quot;Respondido&quot; a &quot;Excluir todo&quot;, se eliminará la campaña y el coste de la tabla Gastos de marketing.

**¿Qué coste tendría prioridad si ya se hubiera descargado una fila de CRM y yo ingresara otra fila en el CSV con el mismo ID de campaña?**

Aunque es posible que pueda cargar el archivo correctamente, [!DNL Marketo Measure] no usará esa fila porque ya tenemos un ID de campaña con el mismo valor que se extrajo automáticamente de la integración.

**¿Cómo sugeriríamos que los costes de nuestras campañas digitales que configuramos en CRM?**

Porque [!DNL Marketo Measure] javascript ya está realizando un seguimiento de la actividad web desde su sitio, recomendamos que no sincronice ninguna campaña que rastree a los miembros de la campaña desde formularios web u otras actividades del sitio, ya que contará dos veces los toques. Por ello, es posible que desee seguir utilizando la opción Carga de CSV en Gastos de marketing para realizar un seguimiento de esos costes en línea/digitales si no estamos integrados con esa plataforma (es decir, Twitter, Adroll).
