---
unique-page-id: 18874606
description: Parámetros UTM - [!DNL Marketo Measure] - Documentación del producto
title: Parámetros UTM
exl-id: 2b20f3c4-1f39-4ac5-bad1-cb1d630d60e9
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: ht
source-wordcount: '946'
ht-degree: 100%

---

# Parámetros UTM {#utm-parameters}

Etiquetar direcciones URL es una forma sencilla y eficaz de capturar datos sobre los esfuerzos de marketing digital. Es el proceso de agregar parámetros al final de las direcciones URL que recopilan y registran datos. Los parámetros más utilizados son los módulos de seguimiento Urchin (UTM, por sus siglas en inglés), que son compatibles con Google. Hay cinco parámetros principales de UTM disponibles: medio, origen, campaña, contenido y término. Estos se tratan con más detalle en la siguiente sección.

Los parámetros UTM se pueden agregar manualmente a las direcciones URL o agregar mediante el etiquetado automático con determinadas plataformas, como AdWords. El etiquetado automático automatiza el proceso de adición de parámetros a las direcciones URL. También existe la opción de utilizar [generadores de URL](https://ga-dev-tools.appspot.com/campaign-url-builder/){target="_blank"} para acelerar el etiquetado de direcciones URL manualmente. Con un generador de direcciones URL, simplemente debe especificar los valores que se utilizarán para cada parámetro y el generador dará formato a la dirección URL.

## ¿Qué son los parámetros UTM? {#what-are-utm-parameters}

Para comprender cómo funcionan los parámetros UTM, veamos una URL típica sin UTM:

`http://www.adobe.com`

Ahora, veamos una URL con UTM:

`http://www.adobe.com?utm_medium=socialmedia&utm_source =facebook&utm_campaign=seasonal-sale&utm_content=photo-400x700px`

Como puede ver, el segundo vínculo contiene mucho más texto. Los parámetros UTM siempre van después del dominio de nivel superior (.com en este ejemplo) y comienzan con un signo de interrogación. Después de esto, el orden de los parámetros no importa, pero se recomienda seguir una convención de nombres coherente. Los símbolos de unión deben colocarse entre cada parámetro para separar cada UTM. Ahora podemos entrar en más detalles sobre lo que representa cada parámetro.

Obtenga información sobre las [prácticas recomendadas para configurar parámetros UTM](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md).

**utm_medium**

* Medio identifica los vehículos que utiliza para comercializar su empresa.
* Responde a la pregunta: “¿cómo le llegan?”
* Indica el canal de nivel más alto.
* Los medios sociales, el correo electrónico, la búsqueda orgánica y la búsqueda de pago son ejemplos de valores medios potenciales.
* Este parámetro asigna los datos al campo “Medio” de [!DNL Marketo Measure].
* _[!DNL Marketo Measure]Práctica recomendada:_ no utilice este campo para llamar a un subcanal; de lo contrario, puede que experimente dificultades para generar informes en el canal real. Utilícelo para identificar su vehículo o canal de marketing. Por ejemplo, si desea utilizar el correo electrónico para promocionar su producto, el medio es el correo electrónico.

**utm_source**

* Origen identifica el subcanal que es la fuente del tráfico.
* Responde a la pregunta: “¿de dónde viene esta persona?”
* En un ejemplo de medio social, el origen del tráfico es la plataforma de medios sociales que se está utilizando.
   * En este ejemplo, [!DNL Facebook] es el valor de origen. Otros ejemplos son Twitter e Instagram. Si el medio de UTM es [!DNL Paid Search], por otro lado, el origen de UTM podría ser AdWords o Bing Ads.

* Este parámetro se asigna al campo “Origen del punto de contacto” de [!DNL Marketo Measure] en SFDC.
* _[!DNL Marketo Measure]Práctica recomendada:_ este parámetro rastrea el origen del tráfico, por lo que no es adecuado utilizarlo para indicar el tipo de anuncio, por ejemplo: redireccionamiento, patrocinado, etc. Se recomienda utilizarlo para rastrear el subcanal de nivel superior. Recuerde que está respondiendo a la pregunta: “¿de dónde proviene mi tráfico?” Está buscando el referente. En este ejemplo, el origen de UTM es el lugar donde se encuentra el anuncio (no la página web real, ya que se rastrea automáticamente fuera de las etiquetas). Si está realizando un seguimiento de una campaña de correo electrónico por goteo gota, el origen es el correo electrónico por goteo.

**utm_campaign**

* La campaña se utiliza para identificar una campaña de marketing específica.
* Responde a la pregunta: “¿por qué vienen a usted?”
* Utilice esta etiqueta para indicar el nombre de la campaña de anuncios tal como existe en [!DNL Google AdWords] o [!DNL BingAds], o para indicar el nombre con el que se identifica la campaña internamente. Incluso puede utilizar esta etiqueta para especificar otra información, como la geolocalización o el tipo de red de anuncios.
* Este parámetro se asigna al campo “Nombre de campaña de anuncios” de [!DNL Marketo Measure] en SFDC.
* _[!DNL Marketo Measure]Práctica recomendada_: al determinar los nombres de las campañas, evite utilizar signos de puntuación o espacios vacíos entre las palabras, ya que su uso puede provocar errores de codificación en el explorador. Para obtener los mejores resultados, utilice guiones bajos en su lugar.

**utm_content**

* Utilice el parámetro Contenido de UTM cuando quiera rastrear más de un fragmento de marketing existente en una sola página web. Por ejemplo, si tiene el botón “Solicitar una demostración” y el botón “Suscribirse a nuestro boletín semanal”, y desea saber cuál genera la mayor cantidad de tráfico, debe asignarles un nombre y usar la etiqueta Contenido de UTM para rastrearlos. El nombre de cada fragmento de “contenido” es el valor de la etiqueta.
* Este parámetro se asigna al campo “Contenido de anuncios” de [!DNL Marketo Measure] en SFDC.
* _[!DNL Marketo Measure]Práctica recomendada_: se trata de un valor opcional, pero [!DNL Marketo Measure] recomienda utilizarlo. Esta etiqueta está asociada con el título del anuncio o materiales de marketing que desee rastrear. Si utiliza un anuncio de imagen, asegúrese de escribir las dimensiones de la imagen en su título.

**utm_term**

* El término es similar al parámetro Contenido UTM. El término es ideal para identificar palabras clave en anuncios para campañas de pago. Si utiliza la función de etiquetado automático, esto se realizará de forma automática. Si no utiliza la función de etiquetado automático de su plataforma de anuncios, asegúrese de agregar cuidadosamente todas las palabras clave que desee rastrear.
* Este parámetro se asigna al campo “Texto de palabra clave” de [!DNL Marketo Measure] en SFDC.
* _[!DNL Marketo Measure]Práctica recomendada_: la etiqueta Término de UTM es opcional, pero ideal para rastrear palabras clave. Compruebe la ortografía y evite utilizar caracteres especiales. Si se necesita más de una palabra, intente utilizar guiones bajos o ningún espacio.

Cada parámetro recopila información relevante para el valor asignado. El valor de cada etiqueta le permite rastrear y ordenar todas las campañas digitales y responder a las preguntas: ¿dónde, cómo y por qué?

A continuación se muestra un gráfico de los parámetros UTM que analiza [!DNL Marketo Measure] y el campo Punto de contacto correspondiente al que están vinculados:

| **Parámetro UTM** | **Campo de [!DNL Marketo Measure] correspondiente** |
|---|---|
| utm_medium | Medio |
| utm_source | Origen del punto de contacto |
| utm_campaign | Nombre de campaña de anuncios |
| utm_content | Contenido de anuncios |
| utm_term | Texto de palabra clave |
