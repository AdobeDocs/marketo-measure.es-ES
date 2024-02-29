---
unique-page-id: 18874558
description: 'Etapas y puntos de contacto de Boomerang: [!DNL Marketo Measure]'
title: Fases y puntos de contacto de Boomerang
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
feature: Boomerang, Touchpoints
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 1%

---

# Fases y puntos de contacto de Boomerang {#boomerang-stages-and-touchpoints}

>[!AVAILABILITY]
>
>La función Boomerang solo está habilitada para clientes de nivel 3. Para solicitar un nivel de cuenta superior, póngase en contacto con el equipo de cuenta de Adobe (su administrador de cuentas).

[!DNL Marketo Measure] ha lanzado la función Boomerang Stage! La función Boomerang Stage se ha creado para proporcionar una mayor visibilidad del recorrido del cliente para [!DNL Marketo Measure] clientes con ciclos de ventas largos. Esta función permite a los especialistas en marketing crear puntos de contacto para todas las transiciones de etapa que se producen en el recorrido de oportunidad, como cuando un contacto usa MQL, luego se mueve a SAL y luego vuelve al escenario de MQL. Cuando los contactos &quot;vuelven a entrar en la fase MQL&quot; o &quot;re-MQL&quot;, el MQL se considera una fase boomerang. La función Boomerang Stage funciona junto con el [!DNL Marketo Measure] Fases personalizadas.

## Qué hace esta función {#what-this-feature-does}

* Crea un punto de contacto &quot;bumerán&quot; para todas las transiciones de fase que se producen en el recorrido de una oportunidad
* Rastrea transiciones repetidas entre cualquier fase personalizada (por ejemplo, cuando un MQL de contacto, se mueve a SAL y luego vuelve a la fase MQL)
* Permite especificar cuántas transiciones de fase y qué conjunto de transiciones desea incluir en la oportunidad (por ejemplo, Los primeros 10 MQL O los últimos 5 MQL
* Si es usuario de un modelo personalizado, puede determinar la ponderación de atribución y el porcentaje de crédito que desea asignar a cada una de estas fases (por ejemplo, designar la ponderación de atribución a la primera o la última ocurrencia de MQL, o distribuir la ponderación de atribución equitativamente entre todas las ocurrencias)

>[!NOTE]
>
>[Instrucciones sobre cómo configurar las etapas de Boomerang](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md).

## Aspecto de las etapas y los puntos de contacto de Boomerang en su CRM {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

Sin las fases de Boomerang (el &quot;antes&quot;), solo ve el punto de contacto de SQL más reciente o el MQL más reciente asociado a un registro de posible cliente/contacto.

![](assets/1.png)

Con las etapas de Boomerang y los puntos de contacto, verá los puntos de contacto que se producen para cada transición de etapa. La convención de nombres para estos puntos de contacto boomerang es:

**[Nombre del escenario]-00.**

Utilizando el ejemplo siguiente, esto [!DNL Marketo Measure] La cuenta de ha incluido MQL y SQL en sus etapas de bumerang y ha elegido mostrar 2 puntos de contacto de bumerang por etapa.

![](assets/2.png)

**MQL-01** es la primera transición de fase MQL.

El valor numérico en la posición del punto de contacto indica el orden en que se produjo la transición de fase. El último punto de contacto boomerang debe marcarse como:

MQL-02 **(Último)**

## Cómo cambian las etapas de boomerang los datos existentes {#how-boomerang-stages-change-your-existing-data}

Impacto de etapas boomerang:

**Atribución por canal**

* Desde [!DNL Boomerang Stages] crea más puntos de contacto, esto cambia la forma en que se distribuye la atribución entre los puntos de contacto que existen actualmente en los datos. Como resultado, esto puede significar que los valores de los ingresos cambian entre los canales de marketing. Tenga esto en cuenta antes de implementar [!DNL Boomerang stages]o póngase en contacto con su administrador de cuentas para obtener más información.

**Cualquier informe que utilice &quot;es igual que&quot; [Posición del punto de contacto]&quot;**

* Las fases boomerang introducen nuevas posiciones de puntos de contacto en los datos. [!DNL Marketo Measure] está cambiando el formato de la posición del punto de contacto para incluir la aparición del escenario, como &quot;MQL-01&quot; o &quot;MQL-05 (último)&quot;. Con este ejemplo, las fases de boomerang afectan a cualquier informe que utilice &quot;La posición del punto de contacto es igual a MQL&quot;. Para ajustar estos informes, el filtro debe utilizar el operador &quot;contains&quot; en su lugar.

## Preguntas frecuentes {#faq}

**¿Cuántas etapas de bumerán puedo incluir en mi modelo de atribución?**

Puede seleccionar hasta 15 etapas.

**P: ¿Cuántos puntos de contacto &quot;boomerang&quot; puedo tener por etapa?**

Puede seleccionar hasta diez puntos de contacto boomerang por fase.

**P: ¿Por qué hay un límite de diez boomerangs por etapa?**

[!DNL Marketo Measure] debe establecer un límite en el número de etapas para mantener los tiempos de procesamiento bajo control. Si elige incluir las 15 etapas de boomerang en el modelo de atribución y 10 puntos de contacto de boomerang por etapa, podría tener más de 150 puntos de contacto por registro de posible cliente/contacto.

**P: Tengo Data Warehouse. ¿Obtengo todos los datos o también se me aplica el límite de etapas boomerang?**

El límite se aplica a Data Warehouse y CRM debido a los límites de procesamiento que [!DNL Marketo Measure] tiene en su lugar. Data Warehouse también verá el límite de diez puntos de contacto por fase.

**P: ¿Cuál es el beneficio de utilizar las fases de boomerang con el modelado personalizado?**

Uso de [!UICONTROL Bumerán] Las fases con modelado personalizado le permiten asignar una ponderación de atribución a [!UICONTROL Bumerán] puntos de contacto, que asignan crédito de ingresos a estas fases.

Sin modelado personalizado, [!DNL Marketo Measure] crea puntos de contacto para cada búmeran y transición de fase, pero no asigna ningún crédito de atribución a estos puntos de contacto. Los únicos puntos de contacto de boomerang que reciben créditos de atribución son los puntos de contacto de envío. Sin modelo personalizado, [!DNL Boomerang] los puntos de contacto se consideran lo mismo que un &quot;contacto intermedio&quot; y reciben crédito de atribución en consecuencia.
