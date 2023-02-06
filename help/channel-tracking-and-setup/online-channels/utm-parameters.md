---
unique-page-id: 18874606
description: 'Parámetros de UTM: [!DNL Marketo Measure] - Documentación del producto'
title: Parámetros de UTM
exl-id: 2b20f3c4-1f39-4ac5-bad1-cb1d630d60e9
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 0%

---

# Parámetros de UTM {#utm-parameters}

Etiquetar direcciones URL es una forma sencilla y eficaz de capturar datos sobre los esfuerzos de marketing digital. Es el proceso de agregar parámetros al final de las direcciones URL que recopilan y registran datos. Los parámetros más utilizados son los módulos de seguimiento de URL (UTM), que son compatibles con Google. Hay cinco parámetros principales de UTM disponibles: Medio, Origen, Campaña, Contenido y Término. Estos se tratan con más detalle en la siguiente sección.

Los parámetros de UTM se pueden agregar manualmente a las direcciones URL o anexar mediante el etiquetado automático con determinadas plataformas, como AdWords . El etiquetado automático automatiza el proceso de adición de parámetros a las direcciones URL. También existe la opción de [Generadores de URL](https://ga-dev-tools.appspot.com/campaign-url-builder/){target="_blank"} para acelerar el etiquetado de direcciones URL manualmente. Con un generador de direcciones URL, simplemente debe especificar los valores que se utilizarán para cada parámetro y el generador dará formato a la dirección URL.

## ¿Qué son los parámetros de UTM? {#what-are-utm-parameters}

Para comprender cómo funcionan los parámetros de la UTM, veamos una URL típica sin UTM:

`http://www.adobe.com`

Ahora, veamos una URL con UTM:

`http://www.adobe.com?utm_medium=socialmedia&utm_source =facebook&utm_campaign=seasonal-sale&utm_content=photo-400x700px`

Como puede ver, el segundo vínculo contiene mucho más texto. Los parámetros de UTM siempre van después del dominio de nivel superior (.com en este ejemplo) y comienzan con un signo de interrogación. Después de esto, el orden de los parámetros no importa, pero se recomienda seguir una convención de nombres coherente. Los símbolos deben colocarse entre cada parámetro para separar cada UTM. Ahora podemos entrar en más detalles sobre lo que representa cada parámetro.

Obtenga información sobre [prácticas recomendadas para configurar parámetros de UTM](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md).

**utm_medium**

* Medium identifica los vehículos que utiliza para comercializar su empresa.
* Responde a la pregunta: &quot;¿Cómo te llegan?&quot;
* Indica el canal de nivel más alto.
* Los medios sociales, el correo electrónico, la búsqueda orgánica y la búsqueda de pago son ejemplos de valores medianos potenciales.
* Este parámetro asigna los datos al [!DNL Marketo Measure] Campo &quot;Medio&quot;.
* _[!DNL Marketo Measure]Práctica recomendada:_ No utilice este campo para llamar a un subcanal; de lo contrario, puede que experimente dificultades para generar informes en el canal real. Utilícelo para identificar su vehículo o canal de marketing. Por ejemplo, si desea utilizar el correo electrónico para promocionar su producto, el medio es el correo electrónico.

**utm_source**

* Fuente identifica el subcanal que es la fuente del tráfico.
* Responde a la pregunta: &quot;¿De dónde viene esta persona?&quot;
* En un ejemplo de medio social, la fuente del tráfico es la plataforma de medios sociales que se está utilizando.
   * En este ejemplo, [!DNL Facebook] es el valor de origen. Otros ejemplos son Twitter y Instagram. Si el medio de la UTM es [!DNL Paid Search]Por otro lado, la fuente de la UTM podría ser AdWords o BingAds.

* Este parámetro se asigna a la variable [!DNL Marketo Measure] Campo &quot;Origen de punto de contacto&quot; en SFDC.
* _[!DNL Marketo Measure]Práctica recomendada:_ Este parámetro rastrea el origen del tráfico, por lo que no es adecuado utilizarlo para indicar el tipo de anuncio, por ejemplo: retargeting, patrocinado, etc. Se recomienda utilizarlo para rastrear el subcanal de nivel superior. Recuerden, están respondiendo a la pregunta &quot;¿de dónde viene mi tráfico?&quot; Está buscando el referente. En este ejemplo, el origen de UTM es el lugar donde se encuentra la publicidad (no la página web real, ya que se rastrea automáticamente fuera de las etiquetas). Si está realizando un seguimiento de una campaña de correo electrónico de gota, la fuente es el correo electrónico goteo.

**utm_campaign**

* La campaña se utiliza para identificar una campaña de marketing específica.
* Responde a la pregunta: &quot;¿Por qué vienen a ti?&quot;
* Utilice esta etiqueta para indicar el nombre de la campaña de publicidad tal como existe en [!DNL Google AdWords] o [!DNL BingAds]o para indicar el nombre con el que se identifica la campaña internamente. Incluso puede utilizar esta etiqueta para especificar otra información, como la geolocalización o el tipo de red de publicidad.
* Este parámetro se asigna a la variable [!DNL Marketo Measure] &quot;Campo Nombre de campaña de publicidad&quot; en SFDC.
* _[!DNL Marketo Measure]Práctica recomendada_: Al determinar los nombres de las campañas, evite utilizar signos de puntuación o espacios vacíos entre las palabras, ya que su uso puede provocar errores de codificación en el explorador. Para obtener los mejores resultados, utilice guiones bajos en su lugar.

**utm_content**

* Utilice el parámetro Contenido de la UTM cuando quiera rastrear más de una pieza de marketing existente en una sola página web. Por ejemplo, si tiene el botón &quot;Solicitar una demostración&quot; y el botón &quot;Suscribirse a nuestro boletín semanal&quot;, y desea saber cuál genera la mayor cantidad de tráfico, debe asignarles un nombre y usar una etiqueta Contenido de UTM para rastrearlos. El nombre de cada parte de &quot;contenido&quot; es el valor de la etiqueta.
* Este parámetro se asigna a la variable [!DNL Marketo Measure] Campo &quot;Contenido de publicidad&quot; en SFDC.
* _[!DNL Marketo Measure]Práctica recomendada_: Se trata de un valor opcional, pero [!DNL Marketo Measure] recomienda utilizarlo. Esta etiqueta está asociada con el título de la publicidad o artículo de marketing que desee rastrear. Si utiliza una publicidad de imagen, asegúrese de escribir las dimensiones de la imagen en su título.

**utm_term**

* El término es similar al parámetro de contenido de la UTM. El término es bueno para identificar palabras clave en publicidades para campañas pagadas. Si utiliza la función de etiquetado automático, esto se hace por usted. Si no utiliza la función de etiquetado automático de su plataforma de publicidad, asegúrese de agregar cuidadosamente todas las palabras clave que desee rastrear.
* Este parámetro se asigna a la variable [!DNL Marketo Measure] Campo &quot;Texto de palabra clave&quot; en SFDC.
* _[!DNL Marketo Measure]Práctica recomendada_: La etiqueta Término de UTM es opcional pero buena para rastrear palabras clave. Compruebe la ortografía y evite utilizar caracteres especiales. Si se necesita más de una palabra, intente utilizar guiones bajos o ningún espacio.

Cada parámetro recopila información relevante para el valor asignado. El valor de cada etiqueta le permite rastrear y ordenar todas las campañas digitales y responder a las preguntas: ¿dónde, cómo y por qué?

A continuación se muestra un gráfico de los parámetros de la UTM [!DNL Marketo Measure] análisis y el campo Touchpoint correspondiente al que están vinculados:

| **Parámetro UTM** | **Correspondiente [!DNL Marketo Measure] Campo** |
|---|---|
| utm_medium | Media |
| utm_source | Fuente del Touchpoint |
| utm_campaign | Nombre de campaña de publicidad |
| utm_content | Contenido de la publicidad |
| utm_term | Texto de palabra clave |
