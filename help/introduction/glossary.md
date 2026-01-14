---
description: Glosario de campos de Marketo Measure
title: Glosario de campos de Marketo Measure
exl-id: 8e23b102-6d4f-4919-b361-04d1b184e710
feature: Fundamentals
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '3210'
ht-degree: 99%

---


# Glosario de campos de Marketo Measure {#glossary}

Este artículo contiene un glosario de todos los campos de Marketo Measure que se agregan a Salesforce desde el paquete base de Marketo Measure. También encontrará información sobre en qué objeto se puede encontrar el campo y cómo se rellena cada campo con información.

Para obtener un mapa del objeto con el que se relaciona cada campo de Marketo Measure, [haga clic aquí](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

[A](#a) · [B](#b) · [C](#c) · [D](#d) · [E](#e) · [F](#f) · [G](#g) · H · I · J · [K](#k) · [L](#l) · [M](#m) · N · [O](#o) · [P](#p) · Q · [R](#r) · [S](#s) · [T](#t) · [U](#u) · [V](#v) · W · X · Y · Z

## A {#a}

**Cuenta** | Se encuentra en el punto de contacto de atribución de comprador

Este campo se rellena con el nombre de la cuenta asociada al BAT.

**Id. de campaña de anuncios** | Se encuentra en el punto de contacto de comprador, punto de contacto de atribución de comprador

Existen tres formas de rellenar este campo:

`1)` Si el punto de contacto proviene de un esfuerzo de búsqueda de pago (ya sea AdWords o Bing Ads), el id. de campaña de anuncios de la plataforma de anuncios se mostrará aquí.

`2)` Si el punto de contacto no proviene de una búsqueda de pago, el campo se rellenará con el valor utm_campaign en la dirección URL de la página de destino.

P. ej.: `http://info.marketomeasure.com/adwords-for-lead-generation?utm_source=Event&utm_medium=booth&utm_campaign=Marketo%20Virtual%20Event%20sep2014`

En este ejemplo, el id. de campaña de anuncios mostraría: __GAId__ Evento virtual de marketing, septiembre de 2014

`3)` Si el punto de contacto proviene de una campaña sin conexión de Salesforce (una conferencia, una cena, etc.), el id. de campaña de anuncios mostrará el id. de campaña de Salesforce

Si no se encuentra ninguno de los anteriores, este campo estará en blanco.

**Nombre de campaña de anuncios** | Punto de contacto de comprador, punto de contacto de atribución de comprador

`1)` Si el punto de contacto proviene de una búsqueda de pago (AdWords/Bing Ads), el nombre de la campaña de anuncios de la plataforma de anuncios se mostrará aquí.

`2)` Si el punto de contacto no proviene de una búsqueda de pago y la dirección URL de la página de destino contiene el valor utm_campaign, ese valor se rellenará aquí.

`3)` Si el punto de contacto proviene de una campaña de Salesforce, el nombre de la campaña de Salesforce se mostrará aquí.

`4)` Esto se rellenará con el nombre de la campaña definido para los puntos de contacto generados a partir de las actividades creadas en su cuenta de Marketo Measure.

Si no se encuentra ninguno de los anteriores, este campo estará en blanco.

**Nombre de campaña de anuncios (FT)** | Punto de contacto de comprador

Este campo se rellena del mismo modo que el nombre de campaña de anuncios. Sin embargo, este campo muestra específicamente el nombre de la campaña de anuncios que generó el punto de contacto de primer contacto.

**Nombre de campaña de anuncios (LC)** | Punto de contacto de comprador

Este campo se rellena del mismo modo que el nombre de campaña de anuncios. Sin embargo, este campo muestra específicamente el nombre de la campaña de anuncios que generó el punto de contacto de creación de posibles clientes.

**Contenido de anuncios** | Punto de contacto de comprador, punto de contacto de atribución de comprador

`1)` Si el punto de contacto proviene de una búsqueda de pago (AdWords/Bing Ads), el campo mostrará la copia de anuncios completa en la plataforma de anuncios.

`2)` Si el punto de contacto no proviene de una búsqueda de pago, este campo mostrará el valor utm_content en la dirección URL de la página de destino.

`3)` Esto se rellenará con el valor Asunto de la actividad relacionada que generó el punto de contacto.

Si no se encuentra ninguno de los anteriores, este campo estará en blanco.

**Dirección URL de destino de anuncios** | Punto de contacto de comprador, punto de contacto de atribución de comprador

`1)` Si el punto de contacto proviene de una búsqueda de pago, este campo mostrará la URL de destino a la que se dirige después de hacer clic en el anuncio del motor de búsqueda.

Si el punto de contacto no proviene de una búsqueda de pago, el campo estará en blanco.

**Id. del grupo de anuncios** | Punto de contacto de comprador, punto de contacto de atribución de comprador

`1)` Si el punto de contacto proviene de una búsqueda de pago, el id. del grupo de anuncios de AdWords/Bing Ads se mostrará aquí.

Si el punto de contacto no proviene de una búsqueda de pago, el campo estará en blanco.

**Nombre del grupo de anuncios** | Punto de contacto de comprador, punto de contacto de atribución de comprador

`1)` Si el punto de contacto proviene de una búsqueda de pago, el nombre del grupo de anuncios de AdWords/Bing Ads se mostrará aquí.

Si el punto de contacto no proviene de una búsqueda de pago, el campo estará en blanco.

**Id. de anuncios** | Punto de contacto de comprador, punto de contacto de atribución de comprador

`1)` Si el punto de contacto proviene de una búsqueda de pago, el id. de anuncios de AdWords/Bing Ads se mostrará aquí.

`2)` Esto se rellenará con el id. externo de la actividad si el punto de contacto se genera a partir de una actividad de CRM.

Si el punto de contacto no proviene de una búsqueda de pago, el campo estará en blanco.

**% atribución según modelo personalizado** | Punto de contacto de atribución de comprador

Si utiliza un modelo de atribución personalizado, este campo muestra el porcentaje de ingresos atribuido a un punto de contacto según los valores establecidos en el modelo personalizado.

Si no utiliza un modelo personalizado, este campo estará en blanco.

**% atribución según modelo de primer contacto** | Punto de contacto de atribución de comprador

Este campo muestra el porcentaje de ingresos atribuido a un punto de contacto según un modelo de primer contacto.

**% atribución según modelo de ruta completa** | Punto de contacto de atribución de comprador

Este campo muestra el porcentaje de ingresos atribuido a un punto de contacto según un modelo de ruta completa.

**% atribución según modelo de creación de posibles clientes** | Punto de contacto de atribución de comprador

Este campo muestra el porcentaje de ingresos atribuido a un punto de contacto según un modelo de creación de posibles clientes.

**% atribución según modelo en forma de U** | Punto de contacto de atribución de comprador

Este campo muestra el porcentaje de ingresos atribuido a un punto de contacto según un modelo en forma de U.

**% atribución según modelo en forma de W** | Punto de contacto de atribución de comprador

Este campo muestra el porcentaje de ingresos atribuido a un punto de contacto según un modelo en forma de W.

[Haga clic aquí para volver a la parte superior de la página](#top)

## B {#b}

**Importe de oportunidad de Marketo Measure** | Oportunidad de Salesforce

Si utiliza el campo de importe personalizado para informar de los ingresos de oportunidad, Marketo Measure no podrá leer estos campos de importe personalizados. El importe de oportunidad de Marketo Measure es un campo oculto que se utiliza para crear un flujo de trabajo que permite a Marketo Measure leer campos de importe personalizados en la oportunidad.

**Navegador** | Punto de contacto de comprador, Punto de contacto de atribución de comprador

Este campo muestra el tipo de explorador web utilizado durante la sesión web (Chrome, Safari, Firefox, etc.).

[Haga clic aquí para volver a la parte superior de la página](#top)

## C {#c}

**Contacto** | Punto de contacto de comprador, Punto de contacto de atribución de comprador

El campo muestra el contacto al que pertenece el punto de contacto.

**Recuento: modelo personalizado** | Punto de contacto de atribución de comprador

Si utiliza un modelo de atribución personalizado, este campo muestra, en forma decimal, el porcentaje de crédito de ingresos proporcionado a un punto de contacto según los valores establecidos en el modelo personalizado.

Si no utiliza un modelo personalizado, este campo estará en blanco.

**Recuento: modelo personalizado** | Punto de contacto de comprador

Si utiliza un modelo de atribución personalizado, este campo muestra, en forma decimal, el porcentaje de crédito de atribución proporcionado a un punto de contacto según los valores establecidos en el modelo personalizado. Dado que este campo está relacionado con el objeto de punto de contacto de comprador, no es un reflejo del crédito de ingresos, sino solo de la atribución de crédito.

Si no utiliza un modelo personalizado, este campo estará en blanco.

**Recuento: primer contacto** | Punto de contacto de atribución de comprador

Este campo muestra, en forma decimal, el porcentaje de crédito de ingresos proporcionado a un punto de contacto según un modelo de primer contacto.

**Recuento: primer contacto** | Punto de contacto de comprador

Este campo muestra, en forma decimal, el porcentaje de crédito de atribución proporcionado a un punto de contacto según un modelo de primer contacto. Si el punto de contacto es el primer contacto, este campo siempre será 1,0 (lo que indica un crédito de atribución del 100 %). Si el punto de contacto no es el primer contacto, este campo siempre será 0 (lo que indica un crédito de atribución del 0 %).

Dado que este campo está relacionado con el objeto de punto de contacto de comprador, no es un reflejo del crédito de ingresos, sino solo de la atribución de crédito.

**Recuento: ruta completa** | Punto de contacto de atribución de comprador

Este campo muestra, en forma decimal, el porcentaje de ingresos proporcionado a un punto de contacto según un modelo de ruta completa.

**Recuento: contacto de creación de posibles clientes** | Punto de contacto de atribución de comprador

Este campo muestra, en forma decimal, el porcentaje de crédito de ingresos proporcionado a un punto de contacto según un modelo de creación de posibles clientes.

**Recuento: contacto de creación de posibles clientes** | Punto de contacto de comprador

Este campo muestra, en forma decimal, el porcentaje de crédito de atribución proporcionado a un punto de contacto según un modelo de creación de posibles clientes. Si el punto de contacto es el contacto de creación de posibles clientes, este campo siempre será 1,0 (lo que indica un crédito de atribución del 100 %). Si el punto de contacto no es el contacto de creación de posibles clientes, este campo siempre será 0 (lo que indica un crédito de atribución del 0 %).

Dado que este campo está relacionado con el objeto de punto de contacto de comprador, no es un reflejo del crédito de ingresos, sino solo de la atribución de crédito.

**Recuento: en forma de U** | Punto de contacto de atribución de comprador

Este campo muestra, en forma decimal, el porcentaje de crédito de ingresos proporcionado a un punto de contacto según un modelo en forma de U.

**Recuento: en forma de U** | Punto de contacto de comprador

Este campo muestra, en forma decimal, el porcentaje de crédito de atribución proporcionado a un punto de contacto según un modelo en forma de U. En el modelo en forma de U, el crédito se divide entre el primer contacto, el contacto de creación de posibles clientes y cualquier envío de formulario intermedio que se produzca entre el primer contacto y el contacto de creación de posibles clientes.

Dado que este campo está relacionado con el objeto de punto de contacto de comprador, no es un reflejo del crédito de ingresos, sino solo de la atribución de crédito.

**Recuento: en forma de W** | Punto de contacto de atribución de comprador

Este campo muestra, en forma decimal, el porcentaje de crédito proporcionado a un punto de contacto según un modelo en forma de W.

[Haga clic aquí para volver a la parte superior de la página](#top)

## D {#d}

Fecha de notificación | Prueba A/B de Marketo Measure, Evento de Marketo Measure

Evento de Marketo Measure: la fecha en la que un usuario realizó una acción específica en el sitio web al activar un evento

Prueba A/B de Marketo Measure: la fecha en la que un usuario participó en una prueba A/B en el sitio web

[Haga clic aquí para volver a la parte superior de la página](#top)

## E {#e}

**Nombre del evento** | Evento de Marketo Measure

Este campo muestra el nombre de la acción que activó el evento (por ejemplo, vista de página).

**Valor de evento** | Evento de Marketo Measure

La descripción del evento (por ejemplo, la página principal)

**Nombre del experimento** | Prueba A/B de Marketo Measure

Este campo muestra el nombre del experimento (por ejemplo, botón de prueba)

**ID de experimento** | Prueba AB de Marketo Measure

El código de identificación único para cada experimento

[Haga clic aquí para volver a la parte superior de la página](#top)

## F {#f}

URL del formulario | Punto de contacto de comprador, punto de contacto de atribución de comprador

Este campo muestra una versión abreviada de la dirección URL de una página donde se completó el formulario (sin parámetros UTM)

URL del formulario: sin procesar | Punto de contacto de comprador, punto de contacto de atribución de comprador

Este campo muestra la dirección URL de página completa donde se completó el formulario, incluidos los parámetros UTM

[Haga clic aquí para volver a la parte superior de la página](#top)

## G {#g}

Ciudad geográfica | Punto de contacto de comprador, Punto de contacto de atribución de comprador

Este campo muestra el nombre de la ciudad donde el posible cliente o contacto visitó su sitio web. Esto se realiza mediante la búsqueda inversa de IP.

País geográfico | Punto de contacto de comprador, Punto de contacto de atribución de comprador

Este campo muestra el país donde el posible cliente o contacto visitó su sitio web. Esto se realiza mediante la búsqueda inversa de IP.

Región geográfica | Punto de contacto de comprador, Punto de contacto de atribución de comprador

Este campo muestra la región o el estado donde el posible cliente o contacto visitó su sitio web. Esto se realiza mediante la búsqueda inversa de IP.

[Haga clic aquí para volver a la parte superior de la página](#top)

## K {#k}

**Id. de palabra clave** | Punto de contacto de comprador, punto de contacto de atribución de comprador

Si el punto de contacto proviene de una búsqueda de pago, este campo mostrará el id. de palabra clave en la plataforma de anuncios (AdWords/Bing Ads).

Si este punto de contacto no proviene de una búsqueda de pago, este campo estará en blanco.

**Tipo de coincidencia de palabra clave** | Punto de contacto de comprador, punto de contacto de atribución de comprador

Si el punto de contacto proviene de una búsqueda de pago, este campo mostrará el tipo de coincidencia en la plataforma de anuncios (AdWords/Bing).

**Texto de palabra clave** | Punto de contacto de comprador, punto de contacto de atribución de comprador

`1)` Si el punto de contacto proviene de una búsqueda de pago, este campo mostrará el texto de la palabra clave en la plataforma de anuncios (AdWords/Bing Ads) O el valor del parámetro _bk en la dirección URL de la página de destino.

P. ej.: `http://info.marketomeasure.com/intro-guide-b2b-marketing-attribution?_bt=12345678&_bk=marketing%20attribution&_bm=p&gclid=ABc123def456ghi789jkl`

`2)` Si el punto de contacto no proviene de una búsqueda de pago, este campo mostrará el valor utm_term en la dirección URL de la página de destino.

`http://www.marketomeasure.com/blog/lead-generation?utm_source=linkedin&utm_medium=Social&utm_campaign=ABC%20Blog&utm_content=Lead%20Gen&utm_term=lead%20gen`.

Si el punto de contacto no proviene de una búsqueda de pago, o no hay un valor utm_term, este campo estará en blanco.

[Haga clic aquí para volver a la parte superior de la página](#top)

## L {#l}

**Página de destino** | Punto de contacto de comprador, punto de contacto de atribución de comprador

Este campo muestra la versión abreviada de la URL (sin parámetros UTM) de la primera página web visitada durante una sesión web.

**Página de destino: sin procesar** | Punto de contacto de comprador, punto de contacto de atribución de comprador

Este campo muestra la dirección URL completa (incluidos los parámetros UTM) de la primera página web visitada durante una sesión web.

**Posible cliente** | Punto de contacto de comprador, persona de Marketo Measure

Este campo muestra el nombre del posible cliente al que pertenece un punto de contacto.

[Haga clic aquí para volver a la parte superior de la página](#top)

## M {#m}

**Canal de marketing** | Punto de contacto de comprador, Punto de contacto de atribución de comprador

Este campo muestra el grupo general de actividad de marketing o el canal de marketing al que pertenece el punto de contacto (por ejemplo, Búsqueda de pago, Directo, Social, etc.). Los puntos de contacto se agrupan según la configuración de sus canales en la aplicación Marketo Measure. Para obtener más información sobre canales de marketing o cómo configurarlos, [haga clic aquí](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

**Canal de marketing: ruta** | Punto de contacto de comprador, Punto de contacto de atribución de comprador

Este campo muestra el canal de marketing y el subcanal al que pertenece un punto de contacto. En el ejemplo siguiente, el “Canal de marketing: ruta” es Social.Linkedin, donde el canal de marketing es Social y el subcanal es LinkedIn.

![&#x200B; 3](assets/overview-resources-16.png)

**Medio** | Punto de contacto de comprador, Punto de contacto de atribución de comprador

`1)` Si el punto de contacto proviene de una búsqueda de pago, el medio de AdWords/Bing Ads se mostrará aquí (es decir, CPC).

`2)` Si el punto de contacto no proviene de una búsqueda de pago, este campo muestra el valor utm_medium en la dirección URL de la página de destino.

`3)` Si el punto de contacto proviene de una campaña sin conexión, este campo mostrará el campo “Tipo” en la campaña de Salesforce.

`4)` Esto se rellenará con el valor Tipo de actividad de la actividad relacionada que generó el punto de contacto.

Si no se encuentra ninguno de los anteriores, Marketo Measure establece automáticamente un valor Medio.

[Haga clic aquí para volver a la parte superior de la página](#top)

O

**Oportunidad** | Punto de contacto de atribución de comprador

Este campo muestra la oportunidad a la que pertenece el BAT.

[Haga clic aquí para volver a la parte superior de la página](#top)

P

**Plataforma** | Punto de contacto de comprador, Punto de contacto de atribución de comprador

Este campo muestra el tipo de equipo o teléfono y el tipo de sistema operativo que se utilizó durante la sesión web.

[Haga clic aquí para volver a la parte superior de la página](#top)

R

**Página del referente** | Punto de contacto de comprador, punto de contacto de atribución de comprador

Este campo muestra la dirección URL (sin parámetros UTM) de la última página web en la que se encontraba el posible cliente o contacto que los dirigió a su sitio web.

Por ejemplo:

- Si el punto de contacto proviene de una búsqueda de pago/orgánica, el campo mostrará la dirección URL del motor de búsqueda

- Si el punto de contacto proviene de Social, el campo mostrará la dirección URL del sitio web social (por ejemplo, LinkedIn)

**Página del referente: sin procesar** | Punto de contacto de comprador, punto de contacto de atribución de comprador

Este campo muestra la misma información que la página del referente, con la excepción de que mostrará la dirección URL de referencia completa (incluidos los parámetros UTM).

**Ingresos: modelo personalizado** | Punto de contacto de atribución de comprador

Si utiliza un modelo de atribución personalizado, este campo muestra el importe de ingresos en dólares atribuido a un punto de contacto según el porcentaje de atribución establecido en el modelo personalizado.

Si no utiliza un modelo personalizado, el importe en dólares será 0.

**Ingresos: primer contacto** | Punto de contacto de atribución de comprador

Este campo muestra el importe de ingresos en dólares atribuido a un punto de contacto según el porcentaje de atribución del modelo de primer contacto.

**Ingresos: ruta completa** | Punto de contacto de atribución de comprador

Este campo muestra el importe de ingresos en dólares atribuido a un punto de contacto según el porcentaje de atribución del modelo de ruta completa.

**Ingresos: contacto de creación de posibles clientes** | Punto de contacto de atribución de comprador

Este campo muestra el importe de ingresos en dólares atribuido a un punto de contacto según el porcentaje de atribución del modelo de creación de posibles clientes.

**Ingresos: en forma de U** | Punto de contacto de atribución de comprador

Este campo muestra el importe de ingresos en dólares atribuido a un punto de contacto según el porcentaje de atribución del modelo en forma de U.

**Ingresos: en forma de W** | Punto de contacto de atribución de comprador

Este campo muestra el importe de ingresos en dólares atribuido a un punto de contacto según el porcentaje de atribución del modelo en forma de W.

[Haga clic aquí para volver a la parte superior de la página](#top)

S

**Campaña de Salesforce** | Punto de contacto de comprador, Punto de contacto de atribución de comprador

Este campo muestra la campaña de Salesforce a la que pertenece el punto de contacto.

**Frase de búsqueda** | Punto de contacto de comprador, Punto de contacto de atribución de comprador

Si el punto de contacto proviene de una búsqueda orgánica o de pago, este campo mostrará la frase de búsqueda escrita en el motor de búsqueda. Sin embargo, por motivos de privacidad, esta información no suele estar disponible.

**Segmento** | Punto de contacto de atribución de comprador

Este campo muestra los segmentos a los que pertenece el punto de contacto. Esto dependerá de cómo haya configurado las reglas de segmentación en la aplicación Marketo Measure.

[Haga clic aquí para volver a la parte superior de la página](#top)

T

**Fecha de punto de contacto** | Punto de contacto de comprador, punto de contacto de atribución de comprador

`1)` Si el punto de contacto proviene de una fuente en línea, este campo mostrará la fecha y la hora en que se produjo el punto de contacto.

`2)` Si el punto de contacto proviene de un evento sin conexión, este campo mostrará la fecha y la hora establecidas en la campaña de Salesforce o en el campo de fecha seleccionado en las reglas de sincronización de campañas.

`3)` Si el punto de contacto proviene de una actividad, este campo mostrará la fecha y la hora del campo seleccionado como la fecha de punto de contacto en las reglas de actividad.

**Fecha de punto de contacto (FT)** | Punto de contacto de comprador

Este campo es el mismo que Fecha de punto de contacto; sin embargo, este campo muestra específicamente la fecha y la hora en que se produjo el punto de contacto del primer contacto.

**Fecha de punto de contacto (LC)** | Punto de contacto de comprador

Este campo es el mismo que Fecha de punto de contacto; sin embargo, este campo muestra específicamente la fecha y la hora en que se produjo el punto de contacto de la creación de posibles clientes.

**Posición del punto de contacto** | Punto de contacto de comprador, Punto de contacto de atribución de comprador

Este campo muestra la posición del punto de contacto. La posición del punto de contacto refleja los principales puntos de contacto de hito en el recorrido del cliente (es decir, FT, Formulario, LC, OC, Cerrado). La posición del punto de contacto depende de cuándo se produjo en el recorrido del cliente y un solo punto de contacto puede tener más de una posición. Las diferentes posiciones de los puntos de contacto son las siguientes:

Primer contacto (FT): la primera interacción de marketing que alguien tiene con su marca

Creación de posibles clientes (LC): la primera interacción de marketing conocida (normalmente un envío de formulario o una inclusión de campaña de Salesforce)

Formulario: cuando un visitante rellena un formulario en línea

Creación de oportunidades (OC): la interacción de marketing más cercana a cuando se crea la oportunidad

Cerrada: la interacción de marketing más cercana a cuando se cierra la oportunidad (ganada o perdida)

**Origen del punto de contacto** | Punto de contacto de comprador, Punto de contacto de atribución de comprador

`1)` Si el punto de contacto proviene de una búsqueda de pago, este campo mostrará el nombre de la plataforma de anuncios (AdWords/Bing Ads)

`2)` Si el punto de contacto proviene de una búsqueda orgánica, este campo mostrará el nombre del motor de búsqueda

`3)` Si no es #1 o #2, y el valor utm_source está presente en la dirección URL de la página de destino para el punto de contacto, ese valor se mostrará aquí

`4)` Esto se rellenará como campaña de CRM si el punto de contacto se genera a partir de una campaña de CRM.

`5)` Esto se rellenará como actividad de CRM si el punto de contacto se genera a partir de una actividad de CRM.

Si no se encuentra ninguno de los anteriores, este campo se rellenará como “Directo web” o “Web”.

**Origen del punto de contacto (FT)** | Punto de contacto de comprador

Este campo es el mismo que Origen del punto de contacto; sin embargo, este campo muestra específicamente el origen del punto de contacto del primer contacto.

**Origen del punto de contacto (LC)** | Punto de contacto de comprador

Este campo es el mismo que Origen del punto de contacto; sin embargo, este campo muestra específicamente el origen del punto de contacto de la creación de posibles clientes.

**Tipo de punto de contacto** | Se encuentra en el punto de contacto de comprador y el punto de contacto de atribución de comprador.

Este campo mostrará el tipo de interacción del punto de contacto. Se mostrará como: visita web, formulario web o chat en web para puntos de contacto de JavaScript. Para los puntos de contacto de campaña de CRM, se mostrará como CRM. Se rellenará con el tipo de tarea o evento para puntos de contacto de la actividad.

[Haga clic aquí para volver a la parte superior de la página](#top)

U

**Id. único** | Punto de contacto de comprador, Punto de contacto de atribución de comprador

El id. único asociado a cada punto de contacto

**Id. de usuario** | Prueba A/B de Marketo Measure

El código de identificación único de Optimizely para cada uso

[Haga clic aquí para volver a la parte superior de la página](#top)

## V {#v}

**Variación** | Prueba A/B de Marketo Measure

El nombre de la variación de la prueba A/B

**Id. de variación** | Prueba A/B de Marketo Measure

El código de identificación único para cada variación de prueba A/B.

[Haga clic aquí para volver a la parte superior de la página](#top)
