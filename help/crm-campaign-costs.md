---
description: Guía de costes de CRM Campaign para usuarios de Marketo Measure
title: Costes de campañas de CRM
exl-id: d967cabe-b9f1-4ea1-a81b-e4484c703ecf
feature: Spend Management
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '1203'
ht-degree: 0%

---

# Costes de campañas de CRM {#crm-campaign-costs}

La mayoría de los clientes [!DNL Marketo Measure] utilizan campañas CRM para rastrear actividades de marketing sin conexión. Los especialistas en marketing que utilizan estas campañas también supervisan los costes dentro de CRM. Esta característica facilita las cosas a los especialistas en marketing, ya que permite que [!DNL Marketo Measure] lea esos costos y los aplique al gasto en marketing notificado en [!DNL Marketo Measure]. Hasta la fecha, los clientes han tenido que ingresar manualmente los costos de cada campaña por mes, pero con la información necesaria proporcionada a [!DNL Marketo Measure], los usuarios pueden automatizar este proceso para que los especialistas en marketing puedan dedicar más tiempo a analizar su gasto y el retorno de la inversión.

## Disponibilidad {#availability}

Esta característica está disponible para todos los clientes de [!DNL Salesforce] y Dynamics.

## Cómo funciona {#how-it-works}

[!DNL Marketo Measure] busca primero las campañas que se han &quot;habilitado&quot; para los puntos de contacto, por lo que existe una regla de sincronización de campañas que coincida con la que se creó, o bien el valor de Habilitar los puntos de contacto del comprador es &quot;Incluir todos los miembros de la campaña&quot; o &quot;Incluir los miembros de la campaña &quot;Respondidos&quot;.&quot; Además, [!DNL Marketo Measure] debe importar los valores correctos y saber cómo distribuir los costos, por lo que es necesario que los campos siguientes contengan un valor:

**[!DNL Salesforce]**: `ActualCost`, `StartDate`, `EndDate`

**[!DNL Microsoft Dynamics]**: `totalactualcost`, `actualstart`, `actualend`

Si a alguno de los tres campos les falta un valor, [!DNL Marketo Measure] no importará los costos. Puede corregir esto actualizando el registro de campaña en CRM. Los costos no se importan si se establece en $0 porque [!DNL Salesforce] trata los valores en blanco y $0 como iguales.

Para que [!DNL Marketo Measure] determine la distribución de una campaña entre meses, se usa la fecha de inicio y finalización de la campaña para distribuir la cantidad uniformemente por día.

![Para que Marketo Measure determine la distribución de una campaña en](assets/spend-management-3.jpg)

En este ejemplo, una campaña dura 109 días, por lo que con un coste total de 18 000 dólares, el gasto por día llega a ~ 165,14 dólares.

En función del número de días por mes, obtenemos estos totales mensuales, como puede ver en la tabla:

Jul de 2018: (18.000 $/109) x 31 = 5.119,27 $

Ago 2018: (18.000 $/109) x 31 = 5.119,27 $

Sep 2018: (18.000/109 $) x 30 = 4.954,13 $

Oct 2018: (18 000/109 USD) x 17 = 2 807,34 USD

## Gasto notificado histórico {#historical-reported-spend}

Si ha introducido gasto para campañas que se han seguido en el pasado y que se han asignado a una campaña de CRM, no anula ninguno de los costes introducidos. Si se modifica la misma campaña en CRM, se ignora y se da prioridad a los cambios realizados anteriormente en la carga CSV.

Si prefiere que tomemos el coste de la campaña de CRM a partir de ahora, cambie el valor del CSV a 0 $, que anula la entrada. La próxima vez que se ejecuten los trabajos para importar los costes, se incorporarán los informes editados anteriormente.

## Campañas sin puntos de contacto {#campaigns-with-no-touchpoints}

Muchos especialistas en marketing eligen informar sobre el gasto en marketing en campañas CRM que no generaron puntos de contacto o que no tienen miembros de campaña para los fines del seguimiento del gasto. Siempre que se rellenen los tres campos (fecha de inicio, fecha de finalización, costo) y la campaña esté habilitada para puntos de contacto, [!DNL Marketo Measure] extrae ese costo, aunque no haya puntos de contacto asociados a él.

Esto podría resultar útil para rastrear el gasto en costes de marketing excesivos o herramientas para resumirlo en los cálculos de ROI.

## Sincronización del programa Marketo {#marketo-program-sync}

Si introduce programas de Marketo en CRM como campañas, asegúrese de que tiene configuradas las asignaciones Fecha de inicio, Fecha de finalización y Coste de período en los campos de CRM necesarios. Dado que no hay ninguna asignación para el campo Habilitar puntos de contacto del comprador, aún debe habilitar estas campañas para poder recuperar los costes.

## Edición de los Costes {#editing-the-costs}

Una vez importada una campaña desde CRM, se trata de manera similar a un proveedor de anuncios de API y no aparecerá en el CSV para realizar cambios de coste.

Cualquier cambio en el coste o la distribución debe realizarse en CRM para que podamos señalar un único punto de verdad.

## Preguntas frecuentes {#faq}

**He hecho un cambio en mi campaña, ¿cuándo debería esperar ver los cambios en la tabla Gasto en marketing o en mis informes?**

3 a 4 horas

**Tengo la fecha de inicio, la fecha de finalización y el costo rellenados, pero ¿por qué no aparecen mis costos en [!DNL Marketo Measure]?**

Compruebe que tiene el valor &quot;Habilitar Buyer Touchpoint&quot; establecido en &quot;Incluir todos los miembros de la campaña&quot; o al menos &quot;Incluir miembros de la campaña &quot;respondidos&quot;&quot;, o que ha creado una regla de sincronización de campañas personalizada que incluye esta campaña. Si lo has confirmado y sigues sin ver la campaña, ponte en contacto con el [Soporte técnico de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} para que podamos comprobar que tus campañas se están importando correctamente.

**Debo cambiar la distribución de mi campaña para que pueda pesar más en ciertos meses. ¿Cómo hago eso?**

La distribución de los costes se basa exclusivamente en una distribución uniforme desde la fecha de inicio hasta la fecha de finalización. Desafortunadamente, no podemos cambiarlo para que sus costos tengan una ponderación diferente aparte de las fechas establecidas. Puede controlar esto ajustando las fechas de inicio y finalización de la campaña, ya que cada día del mes importa.

**Tengo costos configurados en mi campaña principal. ¿Cómo se asignan los costos de la campaña principal a las campañas secundarias?**

En realidad, la forma en que se recuperarán los costes será directamente desde una sola campaña, independientemente de cualquier relación con los padres o los hijos. Se recomienda que el coste se cargue en las Campañas para niños, junto con las fechas de la campaña, y que luego se use la Campaña principal como campaña general en la que la Campaña principal no se habilitaría para puntos de contacto.

**¿Cómo cambio el costo de un mes en [!DNL Marketo Measure]?**

Como dependemos del CRM como única fuente fiable, todos los cambios deben realizarse en el CRM. Una vez que [!DNL Marketo Measure] ha importado la campaña, los valores de la campaña no se pueden editar en [!DNL Marketo Measure] ni en el archivo CSV.

**¿En qué escenario aparecería una campaña en la tabla Gasto en mercadotecnia y dejaría de aparecer?**

Seguimos exigiendo que los tres campos clave tengan un valor: Fecha de inicio, Fecha de finalización y Coste. Nuestro comportamiento predeterminado es que solo importamos campañas con un valor mayor que 0 $. Lo ideal sería importar campañas donde haya un $0 explícito y no importar las que se queden en blanco, pero la API de Salesforce las importa como $0 independientemente del valor. Además, si el valor Habilitar Buyer Touchpoint cambia de &quot;Incluir todo&quot; o &quot;Incluir &quot;Respondido&quot; a &quot;Excluir todo&quot;, se eliminan la campaña y el coste de la tabla Gasto en marketing.

**¿Qué coste tendría prioridad si ya se ha descargado una fila del CRM y he introducido otra fila en el CSV con el mismo ID de campaña?**

Aunque es posible que pueda cargar el archivo correctamente, [!DNL Marketo Measure] no usará esa fila porque ya tenemos un identificador de campaña con el mismo valor que se extrajo automáticamente de la integración.

**¿Cómo sugeriría que le suministremos los costos de nuestras Campañas digitales que configuramos en CRM?**

Dado que nuestro javascript [!DNL Marketo Measure] ya está realizando un seguimiento de la actividad web desde su sitio, recomendamos que no sincronice ninguna campaña que realice un seguimiento de los miembros de la campaña desde formularios web u otras actividades del sitio, ya que contará dos veces los toques. Por ello, es posible que desee seguir utilizando la opción Cargar CSV en Gastos de marketing para rastrear esos costes digitales/en línea si aún no estamos integrados con esa plataforma (es decir, Twitter, Adroll).
