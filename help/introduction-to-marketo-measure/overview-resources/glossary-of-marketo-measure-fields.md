---
unique-page-id: 18874586
description: Glosario de campos de Marketo Measure - Marketo Measure - Documentación del producto
title: Glosario de campos de Marketo Measure
exl-id: 8e23b102-6d4f-4919-b361-04d1b184e710
source-git-commit: 334dcd3dcbddacc4920d182d94908babd3cb8c89
workflow-type: tm+mt
source-wordcount: '3211'
ht-degree: 0%

---

# Glosario de campos de Marketo Measure {#glossary-of-marketo-measure-fields}

Este artículo contiene un glosario de todos los campos de Marketo Measure que se agregan a Salesforce desde el paquete base de Marketo Measure. También encontrará información sobre en qué objeto se puede encontrar el campo y cómo se rellena cada campo con información.

Para obtener un mapa del objeto con el que se relaciona cada campo de Marketo Measure, [haga clic aquí](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

[A](#a) ・ [B](#b) ・ [C](#c) ・ [D](#d) ・ [E](#e) ・ [F](#f) ・ [G](#g) ・ H ・ I ・ J ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ ・ [K](#k) ・ [L](#l) ・ [M](#m) ・ N [O](#o) ・ [P](#p) ・ P ・ [R](#r) ・ [S](#s) ・ [T](#t) ・ [U](#u) ・ [V](#v) ・ W ・ X ・ Y ・ Z

## A {#a}

**Cuenta** | Encontrado en el punto de contacto de atribución del comprador

Este campo se rellena con el nombre Cuenta asociado a la MTD.

**ID de campaña de publicidad** | Encontrado en Punto de contacto del comprador, Punto de contacto de atribución del comprador

Existen tres formas de rellenar este campo:

`1)` Si el punto de contacto proviene de un esfuerzo de búsqueda de pago (ya sea AdWords o BingAds), el ID de campaña de publicidad de la plataforma de publicidad se mostrará aquí.

`2)` Si el punto de contacto no proviene de la búsqueda de pago, el campo se rellenará con el valor utm_campaign de la dirección URL de la página de aterrizaje.

p. ej., `http://info.marketomeasure.com/adwords-for-lead-generation?utm_source=Event&utm_medium=booth&utm_campaign=Marketo%20Virtual%20Event%20sep2014`

En este ejemplo, se mostraría el ID de campaña de publicidad: __GAId__ Evento virtual de marketing, septiembre de 2014

`3)` Si el punto de contacto proviene de una campaña sin conexión de Salesforce (una conferencia, cena, etc.), el ID de campaña de anuncio mostrará el ID de campaña de Salesforce

Si no se encuentra ninguno de los anteriores, este campo estará en blanco.

**Nombre de campaña de publicidad** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

`1)` Si el punto de contacto proviene de la búsqueda de pago (AdWords/Bing Ads), el nombre de la campaña de publicidad de la plataforma de publicidad se mostrará aquí.

`2)` Si el punto de contacto no proviene de una búsqueda de pago y la dirección URL de la página de aterrizaje contiene un valor para utm_campaign, ese valor se rellenará aquí.

`3)` Si el punto de contacto procede de una campaña de Salesforce, el nombre de la campaña de Salesforce se muestra aquí.

`4)` Esto se rellenará con el Nombre de campaña definido para los touchpoints generados a partir de las actividades creadas dentro de la cuenta de Marketo Measure.

Si no se encuentra ninguno de los anteriores, este campo estará en blanco.

**Nombre de campaña de publicidad (FT)** | Punto de contacto del comprador

Este campo se rellena del mismo modo que el Nombre de campaña de publicidad. Sin embargo, este campo muestra específicamente el nombre de la campaña de publicidad que generó el punto de contacto de primer toque.

**Nombre de campaña de publicidad (LC)** | Punto de contacto del comprador

Este campo se rellena del mismo modo que el Nombre de campaña de publicidad. Sin embargo, este campo muestra específicamente el nombre de la campaña de publicidad que generó el punto de contacto de Creación de posibles clientes.

**Contenido de la publicidad** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

`1)` Si el punto de contacto es de búsqueda de pago (AdWords/Bing Ads), el campo mostrará la copia de publicidad completa desde la plataforma de publicidad.

`2)` Si el punto de contacto no es de búsqueda de pago, este campo mostrará el valor utm_content en la dirección URL de la página de aterrizaje.

`3)` Esto se rellenará con el valor Asunto de la actividad relacionada que generó el Touchpoint.

Si ninguno de los anteriores, este campo estará en blanco.

**Dirección URL del destino de la publicidad** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

`1)` Si el punto de contacto es de búsqueda de pago, este campo mostrará el destino URL al que se dirige después de hacer clic en la publicidad desde el motor de búsqueda.

Si el punto de contacto no es de búsqueda de pago, el campo estará en blanco.

**ID del grupo de publicidad** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

`1)` Si el punto de contacto proviene de una búsqueda de pago, el ID del grupo de publicidad de AdWords/Bing Ads se mostrará aquí.

Si el punto de contacto no proviene de una búsqueda de pago, el campo estará en blanco.

**Nombre del grupo de publicidad** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

`1)` Si el punto de contacto proviene de una búsqueda de pago, el nombre del grupo de publicidad de AdWords/Bing Ads se mostrará aquí.

Si el punto de contacto no proviene de una búsqueda de pago, el campo estará en blanco.

**ID de anuncio** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

`1)` Si el punto de contacto proviene de una búsqueda de pago, el ID de anuncio de AdWords/Bing Ads se mostrará aquí.

`2)` Esto se rellenará con el ID externo de la actividad si el Touchpoint se genera a partir de una actividad de CRM.

Si el punto de contacto no proviene de una búsqueda de pago, el campo estará en blanco.

**Modelo personalizado de atribución %** | Punto de contacto de atribución del comprador

Si utiliza un modelo de atribución personalizado, este campo muestra el porcentaje de ingresos atribuido a un punto de contacto según los valores establecidos en el modelo personalizado.

Si no utiliza un modelo personalizado, este campo estará en blanco.

**Atribución % Primer toque** | Punto de contacto de atribución del comprador

Este campo muestra el porcentaje de ingresos atribuido a un punto de contacto según un modelo de primer contacto.

**Atribución % completa** | Punto de contacto de atribución del comprador

Este campo muestra el porcentaje de ingresos atribuido a un punto de contacto según un modelo de ruta completa.

**Creación de posible cliente de atribución %** | Punto de contacto de atribución del comprador

Este campo muestra el porcentaje de ingresos atribuido a un punto de contacto, según un modelo de creación de posibles clientes.

**Atribución % Forma de U** | Punto de contacto de atribución del comprador

Este campo muestra el porcentaje de ingresos atribuido a un punto de contacto según un modelo en forma de U.

**Atribución % Forma W** | Punto de contacto de atribución del comprador

Este campo muestra el porcentaje de ingresos atribuido a un punto de contacto según un modelo con forma de W.

[Haga clic aquí para volver a la parte superior de la página](#top)

## B {#b}

**Cantidad de oportunidad de Marketo Measure** | Oportunidad de Salesforce

Si utiliza un campo Importe personalizado para informar de los ingresos de oportunidad, Marketo Measure no puede leer estos campos de cantidad personalizados. La cantidad de oportunidad de Marketo Measure es un campo oculto que se utiliza para crear un flujo de trabajo que permite a Marketo Measure leer campos de cantidad personalizados en la oportunidad.

**Navegador** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra el tipo de explorador web utilizado durante la sesión web (Chrome, Safari, Firefox, etc.).

[Haga clic aquí para volver a la parte superior de la página](#top)

## C {#c}

**Contacto** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

El campo muestra el contacto al que pertenece el punto de contacto.

**Recuento: Modelo personalizado** | Punto de contacto de atribución del comprador

Si utiliza un Modelo de atribución personalizado, este campo muestra, en forma decimal, el porcentaje de crédito de ingresos dado a un punto de contacto según los valores establecidos en el Modelo personalizado.

Si no utiliza un modelo personalizado, este campo estará en blanco.

**Recuento: Modelo personalizado** | Punto de contacto del comprador

Si utiliza un Modelo de atribución personalizado, este campo muestra, en forma decimal, el porcentaje de crédito de atribución dado a un punto de contacto según los valores establecidos en el Modelo personalizado. Dado que este campo está relacionado con el objeto Touchpoint de Comprador, no es un reflejo del crédito de los ingresos, sino solo de la atribución de crédito.

Si no utiliza un modelo personalizado, este campo estará en blanco.

**Recuento: primer toque** | Punto de contacto de atribución del comprador

Este campo muestra, en forma decimal, el porcentaje de crédito de ingresos dado a un punto de contacto según un modelo de primer toque.

**Recuento: primer toque** | Punto de contacto del comprador

Este campo muestra, en forma decimal, el porcentaje de crédito de atribución dado a un punto de contacto según un modelo de primer toque. Si el punto de contacto es el primer contacto, este campo siempre será 1,0 (lo que indica un 100% de crédito de atribución). Si el punto de contacto no es el primer contacto, este campo siempre será 0 (indicando un crédito de atribución del 0 %).

Dado que este campo está relacionado con el objeto Touchpoint de Comprador, no es un reflejo del crédito de los ingresos, sino solo de la atribución de crédito.

**Recuento: ruta completa** | Punto de contacto de atribución del comprador

Este campo muestra, en forma decimal, el porcentaje de ingresos dado a un punto de contacto según un modelo de ruta completa.

**Recuento: toque de creación de posibles clientes** | Punto de contacto de atribución del comprador

Este campo muestra, en forma decimal, el porcentaje de crédito por ingresos dado a un punto de contacto según un Modelo de creación de posibles clientes.

**Recuento: toque de creación de posibles clientes** | Punto de contacto del comprador

Este campo muestra, en forma decimal, el porcentaje de crédito de atribución dado a un punto de contacto según un Modelo de creación de posibles clientes. Si el punto de contacto es el contacto Creación de posibles clientes, este campo siempre será 1,0 (indicando un crédito de atribución del 100%). Si el punto de contacto no es el contacto Creación de posibles clientes, este campo siempre será 0 (indicando un crédito de atribución del 0 %).

Dado que este campo está relacionado con el objeto Touchpoint de Comprador, no es un reflejo del crédito de los ingresos, sino solo de la atribución de crédito.

**Recuento: Forma de U** | Punto de contacto de atribución del comprador

Este campo muestra, en forma decimal, el porcentaje de crédito de ingresos dado a un punto de contacto según un modelo en forma de U.

**Recuento: Forma de U** | Punto de contacto del comprador

Este campo muestra, en forma decimal, el porcentaje de crédito de atribución dado a un punto de contacto según un modelo en forma de U. En el modelo en forma de U, el crédito se divide entre el primer contacto, el contacto de creación de posibles clientes y cualquier envío de formulario intermedio que se produzca entre el primer contacto y el contacto de creación de posibles clientes.

Dado que este campo está relacionado con el objeto Touchpoint de Comprador, no es un reflejo del crédito de los ingresos, sino solo de la atribución de crédito.

**Recuento: Forma de W** | Punto de contacto de atribución del comprador

Este campo muestra, en forma decimal, el porcentaje de crédito dado a un punto de contacto según un modelo con forma de W.

[Haga clic aquí para volver a la parte superior de la página](#top)

## D {#d}

Fecha de informe | Marketo Measure ABTest, Evento de Marketo Measure

Evento de Marketo Measure: la fecha en la que un usuario realizó una acción específica en el sitio web, al activar un Evento

Marketo Measure ABTest : la fecha en la que un usuario participó en una prueba A/B en su sitio web.

[Haga clic aquí para volver a la parte superior de la página](#top)

## E {#e}

**Nombre del evento** | Evento de Marketo Measure

Este campo muestra el nombre de la acción que activó el evento (es decir, vista de página).

**Valor de evento** | Evento de Marketo Measure

La descripción del evento (es decir, la página principal)

**Nombre del experimento** | Marketo Measure ABTest

Este campo muestra el nombre del experimento (por ejemplo, Botón de prueba)

**ID del experimento** |Prueba Marketo Measure AB

El código de identificación único para cada experimento

[Haga clic aquí para volver a la parte superior de la página](#top)

## F {#f}

URL del formulario | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra una versión abreviada de la dirección URL de una página donde se ha completado el formulario (sin parámetros de UTM)

URL del formulario: sin procesar | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra la dirección URL de toda la página donde se completó el formulario, incluidos los parámetros de la UTM

[Haga clic aquí para volver a la parte superior de la página](#top)

## G {#g}

Ciudad geográfica | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra el nombre de la ciudad donde el posible cliente o contacto visitó su sitio web. Esto se realiza mediante la búsqueda inversa de IP.

País geográfico | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra el país donde el posible cliente o contacto visitó el sitio web. Esto se realiza mediante la búsqueda inversa de IP.

Región geográfica | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra la región o el estado en el que el posible cliente o contacto visitó el sitio web. Esto se realiza mediante la búsqueda inversa de IP.

[Haga clic aquí para volver a la parte superior de la página](#top)

## K {#k}

**Id De Palabra Clave** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Si el punto de contacto proviene de la búsqueda de pago, este campo mostrará el ID de palabra clave de la plataforma de publicidad (AdWords/BingAds).

Si este punto de contacto no proviene de una búsqueda de pago, este campo estará en blanco.

**Tipo de coincidencia de palabra clave** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Si el punto de contacto proviene de la búsqueda de pago, este campo mostrará el tipo de coincidencia de la plataforma de publicidad (AdWords/Bing).

**Texto de palabra clave** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

`1)` Si el punto de contacto proviene de la búsqueda de pago, este campo mostrará el texto de la palabra clave desde la plataforma de publicidad (AdWords/BingAds) O el valor del parámetro _bk en la dirección URL de la página de aterrizaje.

p. ej., `http://info.marketomeasure.com/intro-guide-b2b-marketing-attribution?_bt=12345678&_bk=marketing%20attribution&_bm=p&gclid=ABc123def456ghi789jkl`

`2)` Si el punto de contacto no proviene de la búsqueda de pago, este campo mostrará el valor utm_term de la dirección URL de la página de aterrizaje.

`http://www.marketomeasure.com/blog/lead-generation?utm_source=linkedin&utm_medium=Social&utm_campaign=ABC%20Blog&utm_content=Lead%20Gen&utm_term=lead%20gen`.

Si el punto de contacto no proviene de una búsqueda de pago o no hay ningún valor utm_term, este campo estará en blanco.

[Haga clic aquí para volver a la parte superior de la página](#top)

## L {#l}

**Página de aterrizaje** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra la versión abreviada de la URL (sin parámetros de UTM) de la primera página web visitada durante una sesión web.

**Página de aterrizaje: sin procesar** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra la dirección URL completa (incluidos los parámetros de UTM) de la primera página web visitada durante una sesión web.

**Posible cliente** | Punto de contacto del comprador, persona de Marketo Measure

Este campo muestra el nombre del posible cliente al que pertenece un punto de contacto.

[Haga clic aquí para volver a la parte superior de la página](#top)

## M {#m}

**Canal de marketing** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra el grupo general de actividad de marketing o el canal de marketing al que pertenece el punto de contacto (por ejemplo, búsqueda de pago, directa, social, etc.). Los puntos de contacto se agrupan según la configuración de sus canales en la aplicación Marketo Measure. Para obtener más información sobre canales de marketing o cómo configurarlos, [haga clic aquí](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

**Canal de marketing: ruta** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra el canal de marketing y el subcanal al que pertenece un punto de contacto. En el ejemplo siguiente, Canal de marketing: la ruta es Social.Linkedin, donde el canal de marketing es Social y el subcanal es LinkedIn.

![](assets/1-3.png)

**Medio** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

`1)` Si el punto de contacto proviene de una búsqueda de pago, el medio de Adwords/BingAds se mostrará aquí (es decir, CPC).

`2)` Si el punto de contacto no proviene de la búsqueda de pago, este campo muestra el valor utm_medium de la dirección URL de la página de aterrizaje.

`3)` Si el punto de contacto proviene de una campaña sin conexión, este campo mostrará el campo &quot;Tipo&quot; en la campaña de Salesforce.

`4)` Esto se rellenará con el valor Tipo de actividad de la actividad relacionada que generó el Touchpoint.

Si ninguno de los anteriores, Marketo Measure establece automáticamente un valor Medio.

[Haga clic aquí para volver a la parte superior de la página](#top)

O

**Oportunidad** | Punto de contacto de atribución del comprador

Este campo muestra la oportunidad a la que pertenece la MTD.

[Haga clic aquí para volver a la parte superior de la página](#top)

P

**Plataforma** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra el tipo de equipo o teléfono y el tipo de sistema operativo que se utilizó durante la sesión web.

[Haga clic aquí para volver a la parte superior de la página](#top)

R

**Página Referente** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra la dirección URL (sin parámetros de UTM) de la última página web en la que se encontraba el posible cliente o contacto que los dirige a su sitio web.

Por ejemplo:

- Si el punto de contacto proviene de la búsqueda de pago/orgánica, el campo mostrará la dirección URL del motor de búsqueda

- Si el punto de contacto proviene de Social, el campo mostrará la dirección URL del sitio web social (por ejemplo, LinkedIn)

**Página Referente - Sin procesar** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra la misma información que la página de referente, excepto que este campo muestra la dirección URL de referencia completa (incluidos los parámetros de UTM).

**Ingresos: Modelo personalizado** | Punto de contacto de atribución del comprador

Si utiliza un modelo de atribución personalizado, este campo muestra la cantidad de ingresos en dólares atribuida a un punto de contacto según el porcentaje de atribución establecido en el modelo personalizado.

Si no utiliza un modelo personalizado, la cantidad en dólares será 0.

**Ingresos: primer toque** | Punto de contacto de atribución del comprador

Este campo muestra la cantidad de ingresos en dólares atribuida a un punto de contacto según el porcentaje de atribución del Modelo de primer toque.

**Ingresos: ruta completa** | Punto de contacto de atribución del comprador

Este campo muestra la cantidad de ingresos en dólares atribuida a un punto de contacto según el porcentaje de atribución del Modelo de ruta completa.

**Ingresos: contacto para la creación de posibles clientes** | Punto de contacto de atribución del comprador

Este campo muestra la cantidad de ingresos en dólares atribuida a un punto de contacto según el porcentaje de atribución del Modelo de creación de posibles clientes.

**Ingresos: Forma de U** | Punto de contacto de atribución del comprador

Este campo muestra la cantidad de ingresos en dólares atribuida a un punto de contacto según el porcentaje de atribución del Modelo en Forma de U.

**Ingresos: Forma de W** | Punto de contacto de atribución del comprador

Este campo muestra la cantidad de ingresos en dólares atribuida a un punto de contacto según el porcentaje de atribución del modelo en forma de W.

[Haga clic aquí para volver a la parte superior de la página](#top)

S

**Campaña de Salesforce** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra la campaña de Salesforce a la que pertenece el punto de contacto.

**Frase de búsqueda** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Si el punto de contacto proviene de una búsqueda orgánica o de pago, este campo mostrará la frase de búsqueda escrita en el motor de búsqueda. Sin embargo, por motivos de privacidad, esta información no suele estar disponible.

**Segmento** | Punto de contacto de atribución del comprador

Este campo muestra los segmentos a los que pertenece el punto de contacto. Esto dependerá de cómo haya configurado las reglas de segmentación en la aplicación Marketo Measure.

[Haga clic aquí para volver a la parte superior de la página](#top)

T

**Fecha de Touchpoint** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

`1)` Si el punto de contacto proviene de una fuente en línea, este campo mostrará la fecha y la hora en que se produjo el punto de contacto.

`2)` Si el punto de contacto proviene de un evento sin conexión, este campo mostrará la fecha y la hora establecidas en la campaña de Salesforce o desde el campo de fecha seleccionado en las reglas de sincronización de campañas.

`3)` Si el punto de contacto proviene de una actividad, este campo mostrará la fecha y la hora del campo seleccionado como Fecha de punto de contacto en las reglas de actividad.

**Fecha de punto de contacto (FT)** | Punto de contacto del comprador

Este campo es el mismo que Fecha de punto de contacto; sin embargo, este campo muestra específicamente la fecha y la hora en que se produjo el punto de contacto del primer contacto.

**Fecha Touchpoint (LC)** | Punto de contacto del comprador

Este campo es el mismo que Fecha de punto de contacto; sin embargo, este campo muestra específicamente la fecha y la hora en que se produjo el punto de contacto Creación de posibles clientes.

**Posición del punto de contacto** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

Este campo muestra la posición del punto de contacto. La posición del punto de contacto refleja los principales puntos de contacto del hito en el recorrido del cliente (es decir, FT, Form, LC, OC, Closed). La posición del punto de contacto depende de cuándo se produjo en el recorrido del cliente y un solo punto de contacto puede tener más de una posición. Las diferentes posiciones de los puntos de contacto son las siguientes:

Primer toque (FT): la primera interacción de marketing que alguien tiene con su marca

Creación de posibles clientes (LC): la primera interacción de marketing conocida (normalmente un envío de formulario o una inclusión de Salesforce Campaign)

Formulario: cuando un visitante rellena un formulario en línea

Creación de oportunidades (OC): la interacción de marketing más cercana a cuando se crea la opción Opp

Cerrado: la interacción de marketing más cercana a cuando se cierra la opción Opp (Ganada o Perdida)

**Origen de touchpoint** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

`1)` Si el punto de contacto proviene de la búsqueda de pago, este campo mostrará el nombre de la plataforma de publicidad (AdWords/BingAds)

`2)` Si el punto de contacto proviene de una búsqueda orgánica, este campo mostrará el nombre del motor de búsqueda

`3)` Si no es #1 o #2, y el valor utm_source está presente en la dirección URL de la página de aterrizaje para el punto de contacto, ese valor se mostrará aquí

`4)` Esto se rellenará como Campaña de CRM si el Touchpoint se genera a partir de una campaña de CRM.

`5)` Esto se rellenará como actividad de CRM si el Touchpoint se genera a partir de una actividad de CRM.

Si no se encuentra ninguno de los anteriores, este campo se rellenará como &#39;Web Direct&#39; o &#39;Web&#39;.

**Origen de punto de contacto (FT)** | Punto de contacto del comprador

Se trata del mismo campo que el origen de punto de contacto, pero este campo muestra específicamente el origen del punto de contacto de primer contacto.

**Fuente de Touchpoint (LC)** | Punto de contacto del comprador

Se trata del mismo campo que el origen de punto de contacto, pero este campo muestra específicamente el origen del punto de contacto de creación de posibles clientes.

**Tipo de punto de contacto** | Se encuentra en el punto de contacto de atribución del comprador y el punto de contacto de atribución del comprador.

Este campo muestra el tipo de interacción del Touchpoint. Se mostrará como: Visita web, formulario web o chat web para puntos de contacto de JavaScript. Para los puntos de contacto de CRM Campaign, se mostrará como CRM. Se rellenará con la tarea o el tipo de evento para los puntos de contacto de la actividad.

[Haga clic aquí para volver a la parte superior de la página](#top)

U

**UniqueId** | Punto de contacto del comprador, Punto de contacto de atribución del comprador

El identificador único asociado a cada punto de contacto

**ID de usuario** | Marketo Measure ABTest

Código de identificación único de Optimize para cada uso

[Haga clic aquí para volver a la parte superior de la página](#top)

## V {#v}

**Variación** | Marketo Measure ABTest

Nombre de la variación de la prueba A/B

**ID de variación** | Marketo Measure ABTest

El código de identificación único para cada variación de prueba A/B.

[Haga clic aquí para volver a la parte superior de la página](#top)
