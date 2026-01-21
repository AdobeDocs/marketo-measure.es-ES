---
unique-page-id: 18874692
description: 'Escenarios de escenario de boomerang:  [!DNL Marketo Measure]'
title: Escenarios de fases de Boomerang
exl-id: 150db070-eef5-4741-845c-775ab4034ead
feature: Boomerang
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '1504'
ht-degree: 0%

---

# Escenarios de fases de Boomerang {#boomerang-stage-scenarios}

>[!AVAILABILITY]
>
>La función Boomerang solo está habilitada para clientes de nivel 2 y 3. Para solicitar un nivel de cuenta superior, póngase en contacto con el equipo de cuenta de Adobe (su administrador de cuentas).

A continuación se muestran algunos ejemplos de escenarios de escenario de boomerang para comprender cómo [!DNL Marketo Measure] crea puntos de contacto en cada situación.

## Escenarios de posible cliente único {#single-lead-scenarios}

**Escenario 1: puntos de contacto de boomerang estándar para un posible cliente**

Este es el escenario más simple de Boomerang. La línea superior (con la etiqueta Posible cliente 1) representa el recorrido de cada posible cliente y cómo aparecen sus puntos de contacto en el registro de posibles clientes. La línea inferior (con la etiqueta Oportunidad) muestra cómo los puntos de contacto de los posibles clientes se traducen en la oportunidad. La progresión de los puntos de contacto se explica en forma cronológica, de izquierda a derecha.

En este escenario, un cliente ha elegido que sus etapas **MQL** y **SQL** se rastreen con Boomerangs. Cada posición de punto de contacto de Boomerang está etiquetada con la etapa y el número en el que se produce (MQL-01, SQL-01, MQL-02). El último punto de contacto boomerang de esa fase tiene &quot;(último)&quot; en la posición del punto de contacto.

El posible cliente 1 se convierte en un contacto con una oportunidad, que se considera el contacto OC.

![](assets/1-1.png)

**Escenario 2: puntos de contacto boomerang y etapas personalizadas para un posible cliente**

En este escenario, un cliente ha elegido solo rastrear la **fase SQL** con puntos de contacto de boomerang. Las fases MQL y SAL se siguen rastreando, pero con la función de fase personalizada [!DNL Marketo Measure].

![](assets/2-1.png)

Observe que la posición del punto de contacto de MQL no está etiquetada con un número. Esto se debe a que no se seleccionó para rastrearse con puntos de contacto Boomerang. Al crear puntos de contacto para las fases incluidas en el modelo personalizado, pero que no se rastrean con Boomerang, [!DNL Marketo Measure] toma la última incidencia de esa fase.

Para la fase SAL, [!DNL Marketo Measure] ignora las dos primeras ocurrencias de esta fase. [!DNL Marketo Measure] solo crea un punto de contacto SAL para la _última_ ocurrencia. En el ejemplo anterior, esto sucede justo antes del punto de contacto OC.

La etapa SQL se rastrea con puntos de contacto boomerang, y se han creado y etiquetado tres puntos de contacto en consecuencia.

El posible cliente 1 se convierte en un contacto con una oportunidad, que se considera el contacto OC.

**Escenario 3: cuando los posibles clientes no alcanzan ni omiten una fase**

Este escenario utiliza los mismos criterios que el escenario 2. Un cliente solo ha elegido rastrear la fase SQL con puntos de contacto boomerang. Se sigue realizando el seguimiento de MQL y SAL, pero con la función de fase personalizada [!DNL Marketo Measure].

![](assets/3.png)

En este escenario, el posible cliente nunca pasa realmente a la fase de SAL. Se convierte en un Contacto antes de que llegue a la fase de SAL, esencialmente &quot;saltándose&quot; la fase de SAL. En este caso, [!DNL Marketo Measure] supone que la SAL se produce con el punto de contacto OC, y que tanto la posición SAL como la OC aparecerán en el mismo punto de contacto.

El posible cliente 1 se convierte en un contacto con una oportunidad, que se considera el contacto OC.

## Escenarios con varios posibles clientes {#scenarios-with-multiple-leads}

Los siguientes escenarios son donde las etapas de boomerang pueden complicarse más, ya que estamos viendo cómo múltiples posibles clientes pueden influir en el recorrido de oportunidad.

La línea superior (con la etiqueta Posible cliente 1 en azul) representa el recorrido de cada posible cliente y cómo aparecen sus puntos de contacto en el registro de posibles clientes. Lo mismo se aplica al plomo 2 (en rosa) y al plomo 3 (en naranja). La línea inferior (con la etiqueta Oportunidad) muestra cómo los puntos de contacto de estos posibles clientes se traducen en la oportunidad. La progresión de los puntos de contacto se explica en forma cronológica, de izquierda a derecha.

**Escenario 1: [!UICONTROL Tres posibles clientes con oportunidad]**

En este escenario, un cliente ha elegido rastrear las **etapas de MQL** y **SAL** con puntos de contacto de boomerang. Las fases personalizadas estándar están realizando un seguimiento de la fase SQL.

![](assets/4.png)

Los puntos de contacto de FT y LC en la oportunidad provienen del posible cliente 1 (azul), porque ocurrieron antes de la FT y la LC del posible cliente 2 (rosa). El punto de contacto LC para el posible cliente 2 aparecerá como un punto de contacto de &quot;Formulario&quot; en la oportunidad.

El MQL-01 (último) del posible cliente 2 se convertirá en el primer MQL de la oportunidad. El MQL-01 del posible cliente 1 no aparecerá como punto de contacto en la oportunidad porque el MQL del posible cliente 2 se produjo primero. Sin embargo, el MQL-02 y el MQL-03 del posible cliente 1 aparecerán en la oportunidad.

El seguimiento de la fase SQL se realiza con fases personalizadas y no con fases boomerang. Aunque hay tres incidencias de la fase SQL entre el posible cliente 1 y el posible cliente 2, solo la última incidencia SQL se incluirá como punto de contacto en la oportunidad.

El punto de contacto SAL-01 (último) del cliente potencial 1 se transfiere como punto de contacto en la oportunidad. El posible cliente 1 se convierte en un contacto con una oportunidad, que se considera el contacto OC. El punto de contacto SAL-01 (último) del posible cliente 2 no se creará como punto de contacto porque esta transición de fase se produjo _después_ del contacto OC.

Los puntos de contacto FT, LC y MQL, SQL, SAL (naranja) del posible cliente 3 se produjeron después del punto de contacto OC en la oportunidad. Estos puntos de contacto se incluyen en la oportunidad, pero se consideran &quot;toques intermedios&quot;.

Cuando el posible cliente 2 y 3 se convierten en contactos, [!DNL Marketo Measure] no creará otro punto de contacto de OC porque solo puede haber una fase de creación de oportunidad.

**Escenario 2: puntos de contacto de visita web Boomerang**

En este escenario, un cliente ha elegido rastrear las fases **MQL**, **SQL** y **SAL** con puntos de contacto boomerang. Este escenario es casi idéntico al anterior, con algunas excepciones.

![](assets/6.png)

Todos los puntos de contacto del cliente potencial 1 se incluirán en la oportunidad, desde FT hasta SAL-01 (último). El punto de contacto LC de Lead 2 se incluirá como punto de contacto de formulario entre los puntos de contacto LC y MQL-01 en la oportunidad.

El MQL-01 (último) (visita web) del posible cliente 2 no se creará como punto de contacto en la Opp. Esto se debe a que este punto de contacto era una visita web que se produce después de la última aparición de la fase SQL y no ayuda a sacar adelante la oportunidad.

La etapa del posible cliente 1 cambia a SAL y, a continuación, se convierte en un contacto con una oportunidad; en este caso, las posiciones SAL-01 (último) y OC se combinan en el mismo punto de contacto.

El toque FT,LC de Lead 3 se crea como un punto de contacto de Form en el Opp. Solo las acciones de rellenado de formulario se crearán como puntos de contacto después del contacto con OC. Por este motivo, las transiciones de fase SQL-01 (último) y SAL-01 (último) para el posible cliente dos no se crearán como puntos de contacto porque estos puntos de contacto fueron visitas web.

Los toques de MQL, SQL y SAL del posible cliente 3 se incluyen como punto de contacto porque era una acción de rellenado de formulario.

**Escenario 3 - Ponderación de atribución Boomerang**

En este escenario, un cliente ha elegido rastrear las fases **MQL**, **SQL** y **SAL** con puntos de contacto boomerang.

![](assets/7.png)

Los puntos de contacto de FT y LC en la oportunidad provienen del posible cliente 1 (azul), porque ocurrieron antes de la FT y la LC del posible cliente 2 (rosa). El punto de contacto LC para el posible cliente 2 aparece como un punto de contacto de &quot;Formulario&quot; en la oportunidad.

El MQL-01 (último) del posible cliente 2 se convierte en el primer MQL de la oportunidad. El MQL-01 del posible cliente 1 no aparecerá como punto de contacto en la oportunidad porque el MQL del posible cliente 2 se produjo primero.

El SQL-01 (último) del cliente potencial 2 se convierte en SQL-01 en la oportunidad. El SQL-01 en el posible cliente 1 no aparecerá como punto de contacto en la oportunidad porque el SQL-01 en el posible cliente 2 se produjo primero.

Tenga en cuenta que el posible cliente 1 se interpone entre MQL y SQL un par de veces antes de alcanzar finalmente la fase SAL. SQL-01, MQL-02, SQL-02, MQL-03, SQL-03 _no se incluirán como puntos de contacto en la oportunidad porque estas transiciones de fase no ayudan a impulsar la oportunidad en el recorrido._

El punto de contacto SAL-01 (último) del posible cliente 1 es el siguiente punto de contacto que se incluirá en el Opp. A continuación, Lead 1 se convierte en un contacto con una oportunidad y crea el punto de contacto de OC.

Los puntos de contacto FT y LC del posible cliente 3, y MQL, SQL y SAL aparecen como un formulario que toca la oportunidad.

El punto de contacto SQL-01 (último) del posible cliente 2 no se incluirá como punto de contacto en la Opp porque se produjo después del punto de contacto de OC. Además, la transición de fase SQL del posible cliente 2 se produjo _después de la transición de fase final de SAL_, y no ayuda a impulsar el recorrido de oportunidades.

## Escenarios de oportunidad {#opportunity-scenarios}

**Escenario 1 - Contactos con oportunidad y seguimiento de bumerán**

En este escenario, un cliente ha elegido rastrear las **transiciones de fase de demostración y negociación** en **Contacto**. Cada fase boomerang puede recibir hasta dos puntos de contacto. La diferencia entre las transiciones de etapa en un contacto y las transiciones de etapa en un posible cliente es que las transiciones de etapa de contacto pueden aparecer como puntos de contacto Boomerang en la oportunidad _después_ del punto de contacto OC. Esto no es así para las transiciones de fase que se producen en el posible cliente, ya que aparecen como un punto de contacto de formulario.

![](assets/8.png)

En este ejemplo, las transiciones de fase de demostración y negociación de Contact 1 se incluyen como puntos de contacto de Demo-01 y Negotiation-01 en la oportunidad. La transición de fase de demostración de Contact 2 se produce _después de_ Contact 1 y aparece como el punto de contacto Demo-02 (último) en la oportunidad.

Observe que no hay una segunda transición a la fase Negociación; la oportunidad salta inmediatamente de Demo-02 (Último) se mueve a Cerrar ganado. En este caso, [!DNL Marketo Measure] incluirá la transición de negociación con el punto de contacto Ganado cerrado.
