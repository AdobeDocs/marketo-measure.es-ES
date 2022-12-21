---
unique-page-id: 18874558
description: Etapas y puntos de contacto de Boomerang - [!DNL Marketo Measure] - Documentación del producto
title: Etapas y puntos de contacto de Boomerang
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 0%

---

# Etapas y puntos de contacto de Boomerang {#boomerang-stages-and-touchpoints}

[!DNL Marketo Measure] ha lanzado nuestra función Boomerang Stage! La función Boomerang Stage se creó para proporcionar buena visibilidad del recorrido del cliente para [!DNL Marketo Measure] clientes con largos ciclos de ventas. Esta función permite a los especialistas en marketing crear puntos de contacto para todas las transiciones de fase que se producen en el recorrido de oportunidad, como cuando un MQL de contacto, luego se mueve a SAL y, a continuación, vuelve al escenario de MQL. Cuando los contactos &quot;entran de nuevo a la etapa de MQL&quot; o &quot;vuelven a MQL&quot;, consideramos que MQL es una etapa de boomerang. La función Boomerang Stage funciona junto con la función [!DNL Marketo Measure] Etapas personalizadas.

## Qué hace esta función {#what-this-feature-does}

* Crea un punto de contacto &quot;boomerang&quot; para todas las transiciones de etapa que se producen en el recorrido de una oportunidad
* Rastrea transiciones repetidas entre cualquier escenario personalizado (por ejemplo, cuando un MQL de contacto, se mueve a SAL y, a continuación, vuelve al escenario de MQL)
* Permite especificar cuántas transiciones de escenario y qué conjunto de transiciones de escenario desea incluir en la oportunidad (por ejemplo, Los primeros 10 MQL (o los últimos 5 MQL)
* Si es un usuario de Modelo personalizado, puede determinar la ponderación de atribución y el crédito porcentual que desea asignar a cada una de estas etapas (por ejemplo, designar el peso de la atribución para la primera o última incidencia de MQL, o distribuir la ponderación de la atribución uniformemente entre todas las ocurrencias)

>[!NOTE]
>
>[Instrucciones sobre cómo configurar las etapas de Boomerang](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md).

## Aspecto de los escenarios y puntos de contacto de Boomerang en su CRM {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

Sin etapas de Boomerang (el &quot;antes&quot;), solo verá el punto de contacto MQL más reciente o SQL más reciente asociado a un registro de posible cliente/contacto.

![](assets/1.png)

Con las etapas y los puntos de contacto de Boomerang, verá los puntos de contacto que se producen en cada transición de fase. La convención de nomenclatura para estos puntos de contacto boomerang será la siguiente:

**[Nombre de la fase]-00.**

Si utilizamos el ejemplo siguiente, [!DNL Marketo Measure] La cuenta ha incluido MQL y SQL en sus etapas boomerang, y ha elegido mostrar 2 puntos de contacto boomerang por fase.

![](assets/2.png)

**MQL-01** es la primera transición de etapa de MQL.

El valor numérico en la posición del punto de contacto indica el orden en que se produjo la transición de la fase. El último punto de contacto de boomerang debe marcarse como:

MQL-02 **(Último)**

## Cómo cambian las etapas de Boomerang los datos existentes {#how-boomerang-stages-change-your-existing-data}

Los escenarios de boomerang afectarán:

**Atribución por canal**

* Since [!DNL Boomerang Stages] creará más touchpoints, lo que cambiará la forma en que se distribuye la atribución entre los touchpoints que existen actualmente en sus datos. Como resultado, esto puede significar que los valores de ingresos cambiarán entre canales de marketing. Tenga esto en cuenta antes de implementar [!DNL Boomerang stages]o póngase en contacto con su administrador de cuentas para obtener más información.

**Cualquier informe que utilice &quot;es igual que [Posición del punto de contacto]&quot;**

* Las etapas de Boomerang introducirán nuevas posiciones de puntos de contacto en sus datos. [!DNL Marketo Measure] está cambiando el formato de la posición del punto de contacto para incluir la aparición del escenario, como &quot;MQL-01&quot; o &quot;MQL-05 (Last)&quot;. Con este ejemplo, los escenarios de Boomerang afectarán a los informes que utilicen &quot;La posición del punto de contacto es igual a MQL&quot;. Para ajustar estos informes, el filtro debe utilizar el operador &quot;contiene&quot; en su lugar.

## Preguntas frecuentes {#faq}

**¿Cuántas etapas del boomerang puedo incluir en mi modelo de atribución?**

Puede seleccionar hasta 15 etapas.

**P: ¿Cuántos puntos de contacto &quot;boomerang&quot; puedo tener por escenario?**

Puede seleccionar hasta 10 puntos de contacto de boomerang por escenario.

**P: ¿Por qué solo estamos limitados a 10 boomerang por fase?**

[!DNL Marketo Measure] debe establecer un límite en el número de etapas para mantener los tiempos de procesamiento bajo control. Si decide incluir las 15 etapas de Boomerang en su modelo de atribución y los 10 puntos de contacto de boomerang por fase, podría tener más de 150 puntos de contacto por registro de posible cliente/contacto.

**P: Tengo Data Warehouse. ¿Obtengo todos los datos o el límite de las etapas de Boomerang también se aplica a mí?**

El límite se aplicará a la Data Warehouse y a los CRM debido a los límites de procesamiento que [!DNL Marketo Measure] tiene lugar. La Data Warehouse también verá el límite de 10 puntos de contacto por fase.

**P: ¿Cuál es la ventaja de utilizar escenarios de Boomerang con modelos personalizados?**

Uso [!UICONTROL Boomerang] Los pasos con el modelado personalizado le permitirán asignar la ponderación de atribución a [!UICONTROL Boomerang] touchpoints, que asignarán crédito por ingresos a estas etapas.

Sin modelado personalizado, [!DNL Marketo Measure] creará puntos de contacto para cada boomerang y transición de etapa, pero no asignará crédito de atribución a estos puntos de contacto. Los únicos puntos de contacto de boomerang que recibirán créditos de atribución son los puntos de contacto de envío de formularios. Sin modelo personalizado, [!DNL Boomerang] los puntos de contacto se consideran el mismo que un &quot;contacto medio&quot; y reciben el crédito de atribución en consecuencia.
