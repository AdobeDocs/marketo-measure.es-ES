---
description: Guía de puntos de contacto y etapas boomerang para usuarios de Marketo Measure
title: Fases y puntos de contacto de Boomerang
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
feature: Boomerang, Touchpoints
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 1%

---

# Fases y puntos de contacto de Boomerang {#boomerang-stages-and-touchpoints}

>[!AVAILABILITY]
>
>La función Boomerang solo está habilitada para clientes de nivel 2 y 3. Para solicitar un nivel de cuenta superior, póngase en contacto con el equipo de cuenta de Adobe (su administrador de cuentas).

[!DNL Marketo Measure] ha lanzado la función Escenario boomerang. La característica Boomerang Stage se creó para dar mayor visibilidad al recorrido del cliente para [!DNL Marketo Measure] clientes con ciclos de ventas largos. Esta función permite a los especialistas en marketing crear puntos de contacto para todas las transiciones de etapa que se producen en el recorrido de oportunidad, como cuando un contacto usa MQL, luego se mueve a SAL y luego vuelve al escenario de MQL. Cuando los contactos &quot;vuelven a entrar en la fase MQL&quot; o &quot;re-MQL&quot;, el MQL se considera una fase boomerang. La función Escenario boomerang funciona junto con las fases personalizadas de [!DNL Marketo Measure].

## Qué hace esta función {#what-this-feature-does}

* Crea un punto de contacto &quot;bumerán&quot; para todas las transiciones de fase que se producen en el recorrido de una oportunidad
* Rastrea transiciones repetidas entre cualquier fase personalizada (por ejemplo, cuando un MQL de contacto, se mueve a SAL y luego vuelve a la fase MQL)
* Permite especificar cuántas transiciones de fase y qué conjunto de transiciones desea incluir en la oportunidad (por ejemplo, Los primeros 10 MQL O los últimos 5 MQL
* Si es usuario de un modelo personalizado, puede determinar la ponderación de atribución y el porcentaje de crédito que desea asignar a cada una de estas fases (por ejemplo, designar la ponderación de atribución a la primera o la última ocurrencia de MQL, o distribuir la ponderación de atribución equitativamente entre todas las ocurrencias)

>[!NOTE]
>
>[Instrucciones sobre cómo configurar las fases de boomerang](/help/advanced-features/boomerang/setting-up-boomerang-stages.md).

## Aspecto de las etapas y los puntos de contacto de Boomerang en su CRM {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

Sin las fases de Boomerang (el &quot;antes&quot;), solo ve el punto de contacto de SQL más reciente o el MQL más reciente asociado a un registro de posible cliente/contacto.

![](assets/boomerang-boomerang-18.png)

Con las etapas de Boomerang y los puntos de contacto, verá los puntos de contacto que se producen para cada transición de etapa. La convención de nombres para estos puntos de contacto boomerang es:

**[Nombre del escenario]-00.**

En el ejemplo siguiente, esta cuenta de [!DNL Marketo Measure] ha incluido MQL y SQL en las fases del boomerang y ha elegido mostrar 2 puntos de contacto del boomerang por fase.

![](assets/boomerang-boomerang-19.png)

**MQL-01** es la primera transición de etapa de MQL.

El valor numérico en la posición del punto de contacto indica el orden en que se produjo la transición de fase. El último punto de contacto boomerang debe marcarse como:

MQL-02 **(último)**

## Cómo cambian las etapas de boomerang los datos existentes {#how-boomerang-stages-change-your-existing-data}

Impacto de etapas boomerang:

**Atribución por canal**

* Dado que [!DNL Boomerang Stages] crea más puntos de contacto, esto cambia la forma en que se distribuye la atribución entre los puntos de contacto que existen actualmente en los datos. Como resultado, esto puede significar que los valores de los ingresos cambian entre los canales de marketing. Tenga esto en cuenta antes de implementar [!DNL Boomerang stages], o comuníquese con el administrador de cuentas para obtener más información.

**Cualquier informe que utilice &quot;es igual a [Posición del punto de contacto]&quot;**

* Las fases boomerang introducen nuevas posiciones de puntos de contacto en los datos. [!DNL Marketo Measure] está cambiando el formato de la posición del punto de contacto para incluir la aparición del escenario, como &quot;MQL-01&quot; o &quot;MQL-05 (último)&quot;. Con este ejemplo, las fases de boomerang afectan a cualquier informe que utilice &quot;La posición del punto de contacto es igual a MQL&quot;. Para ajustar estos informes, el filtro debe utilizar el operador &quot;contains&quot; en su lugar.

## Preguntas frecuentes {#faq}

**¿Cuántas etapas de boomerang puedo incluir en mi modelo de atribución?**

Puede seleccionar hasta 15 etapas.

**Q: ¿Cuántos puntos de contacto &quot;boomerang&quot; puedo tener por etapa?**

Puede seleccionar hasta diez puntos de contacto boomerang por fase.

**Q: ¿Por qué hay un límite de diez boomerangs por etapa?**

[!DNL Marketo Measure] debe establecer un límite en el número de etapas para mantener los tiempos de procesamiento bajo control. Si elige incluir las 15 etapas de boomerang en el modelo de atribución y 10 puntos de contacto de boomerang por etapa, podría tener más de 150 puntos de contacto por registro de posible cliente/contacto.

**Q: tengo Data Warehouse. ¿Se obtienen todos los datos o también se aplica el límite de etapas de boomerang?**

El límite se aplica a Data Warehouse y CRM debido a los límites de procesamiento que [!DNL Marketo Measure] tiene establecidos. Data Warehouse también verá el límite de diez puntos de contacto por fase.

**Q: ¿Cuál es el beneficio de usar las fases de boomerang con el modelado personalizado?**

El uso de fases [!UICONTROL Boomerang] con modelado personalizado le permite asignar ponderación de atribución a puntos de contacto [!UICONTROL Boomerang], que asignan crédito de ingresos a estas fases.

Sin modelado personalizado, [!DNL Marketo Measure] crea puntos de contacto para cada transición de fase y boomerang, pero no asigna crédito de atribución a estos puntos de contacto. Los únicos puntos de contacto de boomerang que reciben créditos de atribución son los puntos de contacto de envío. Sin el modelo personalizado, [!DNL Boomerang] puntos de contacto se consideran los mismos que un &quot;contacto intermedio&quot; y reciben crédito de atribución en consecuencia.
