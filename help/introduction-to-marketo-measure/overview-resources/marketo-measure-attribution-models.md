---
unique-page-id: 18874568
description: Modelos de atribución de medida de Marketo - Medida de Marketo - Documentación del producto
title: Modelos de atribución de medida de Marketo
exl-id: d8f76f29-e7c9-4b2d-b599-e80fd93c4687
source-git-commit: 0aa263053aa8dd804b03a67ab446dc0cda3850c5
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 2%

---

# Modelos de atribución de medida de Marketo {#marketo-measure-attribution-models}

Marketo Measure ofrece seis tipos de modelos de atribución:

* Primera instancia de interacción
* Creación de cliente potencial
* En forma de U
* En forma de W
* Ruta completa
* Modelo personalizado

Estos modelos varían en complejidad. El primer toque y la creación de posibles clientes son nuestros sencillos modelos de un solo toque. Los otros cuatro son nuestros modelos más complejos y multitáctiles. La estructura de los modelos de atribución de la medida de Marketo refleja los cuatro puntos de contacto principales que se producen en el recorrido del cliente:

* Primera instancia de interacción (FT)
* Creación de cliente potencial (LC)
* Creación de oportunidades (OC)
* Acuerdo de ganancia cerrada (CW)

![](assets/1-1.png)

En el **modelos de un solo contacto**, el crédito de atribución solo se atribuye a un punto de contacto de hito; de ahí el nombre &quot;solo contacto&quot;.
En el **modelos multitáctiles**, la mayor parte del crédito de atribución se asigna a dos o más puntos de contacto de hitos. El crédito restante se atribuye a los puntos de contacto que se producen entre los puntos de contacto del hito.

Las siguientes secciones tratan sobre cada modelo de atribución y cómo se asigna el crédito de atribución.

## Modelos de un solo contacto {#single-touch-models}

**Modelo de primer toque**

El modelo Primer toque solo se centra en la primera interacción que un posible cliente tiene con su organización. Este modelo atribuye el 100% del crédito de atribución a la primera vez que el posible cliente se dio cuenta de su empresa, el Primer toque (FT).

Say Kate visita www.adobe.com por primera vez a través de un anuncio de AdWords y ve un documento técnico. El canal Adwords recibirá el 100% del crédito de atribución de esa oportunidad.

![](assets/2.png)

**Modelo de creación de posibles clientes**

El modelo de creación de posibles clientes atribuye el 100% del crédito de atribución al punto de contacto LC, cuando un cliente potencial proporciona su información de contacto y se convierte en un posible cliente.

Continuando con el ejemplo anterior, después de la primera visita de Kate a www.adobe.com a través de Adwords, Austin visita el sitio web a través de una publicación de Linkedin. Austin rellena un formulario y se convierte en un posible cliente. En este modelo, Linkedin recibiría el 100% del crédito de atribución.

![](assets/3.png)

## Modelos multitáctiles {#multi-touch-models}

Los modelos multitáctiles se utilizan para ciclos de ventas más largos y complicados. Estos modelos son especialmente útiles si varias personas de una cuenta o empresa participan en el recorrido del comprador.

**Modelo en forma de U**

El modelo en forma de U se centra en los puntos de contacto FT y LC. En este modelo, los puntos de contacto FT y LC reciben cada uno el 50% del crédito de ingresos.

La primera visita de Kate a www.adobe.com a través de un anuncio de Adwords recibiría el 50% del crédito de atribución. El 50% restante sería atribuido al post de Linkedin que llevó a Austin a llenar un formulario y convertirse en un líder.

![](assets/4.png)

**Modelo en forma de W**

Tres de los puntos de contacto de hitos se incluyen en el modelo con forma de W. En este modelo, los puntos de contacto FT, LC y OC se atribuyen cada uno al 30% del crédito de atribución. El 10 % restante se atribuye proporcionalmente a cualquier punto de contacto intermedio que se produzca entre los tres puntos de contacto de hitos.

Kate y Austin mencionan Marketo Measure a su compañero, Hillary. Ella encuentra un fragmento de contenido a través de una búsqueda en google y rellena un formulario. Más tarde, Austin recibe un correo electrónico para un registro a un seminario web y rellena el formulario de registro en el sitio web. Kate tiene una conversación con un representante de ventas sobre el producto Marketo Measure.

Hillary recibe un correo electrónico con un vínculo a la página de precios y visita la página. A continuación, se crea una oportunidad para su cuenta. La visita web de Hillary a la página de precios recibe el crédito por la creación de oportunidades porque fue la interacción de marketing más cercana a la fecha de creación de oportunidades. A cada uno de los puntos de contacto de hitos se les asigna el 30 % del crédito de atribución y a los puntos de contacto intermedios se les atribuye el 10 % restante.

![](assets/5.png)

**Modelo de ruta completa**

El modelo de ruta completa incluye los cuatro puntos de contacto de hitos. FT, LC, OC y CW reciben cada uno un 22,5% del crédito de ingresos, y el 10% restante se distribuye equitativamente entre los toques intermedios.

Después de la creación de la oportunidad, Kate, Austin, y Hillary decidieron presentar Marketo Measure a su CMO, Elizabeth. Elizabeth asiste a una conferencia donde Marketo Measure organiza un evento. Kate ve un post de Linkedin acerca de un caso práctico y rellena un formulario para descargar el contenido. Elizabeth asiste a una cena de ventas organizada por Marketo Measure. Después de la cena, decide comprar Marketo Measure y se convierte en cliente. En este escenario, la cena de ventas sería atribuida al 22,5% del crédito de ingresos del acuerdo cerrado. Los puntos de contacto FT, LC y OC también reciben el 22,5% del crédito. A los puntos de contacto intermediarios se les asigna igualmente el 10 % restante del crédito por ingresos.

![](assets/6.png)

**Modelo de atribución personalizado**

Marketo Measure también ofrece un modelo de atribución personalizada que permite a los usuarios elegir qué puntos de contacto o etapas personalizadas incluir en su modelo. Además, los usuarios pueden controlar el porcentaje de crédito de atribución atribuido a estos puntos de contacto y etapas.
