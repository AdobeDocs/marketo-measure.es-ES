---
unique-page-id: 18874656
description: Filtros - [!DNL Marketo Measure] - Documentación del producto
title: Filtros
exl-id: 249266c8-9ff5-4895-979c-4f377423d031
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '1290'
ht-degree: 3%

---

# Filtros {#filters}

Obtenga más información sobre los diferentes filtros disponibles en Discover y cómo puede utilizarlos.

>[!NOTE]
>
>Los operadores &quot;coincide con un atributo del usuario&quot; y &quot;coincide con (avanzado)&quot; dentro de los filtros de Discover son puramente administrativos y se pueden ignorar con seguridad.

**Identificación de la cuenta**

_Se utiliza en: Marketing basado en cuentas_

Seleccione o pegue una serie de ID de cuenta de CRM para filtrar los resultados. Los identificadores de cuenta ofrecen más exclusividad que el nombre de cuenta, ya que los nombres pueden ser los mismos.

**Nombre de la cuenta**

_Se utiliza en: Marketing basado en cuentas_

Seleccione o pegue una serie de Nombres de cuenta de CRM para filtrar los resultados. Las cadenas pueden tener duplicados, por lo que es posible tener varios &quot;[!DNL Marketo Measure]&quot; cuentas, por ejemplo. Si se necesita una sola cuenta en este caso, utilice el filtro Account Id en su lugar.

**Modelo de atribución**

_Se utiliza en: Información general, gasto en marketing, ROI de anuncios, marketing basado en cuentas, tráfico web, CMO, medios pagados, marketing de contenido, Passport_

Elija un modelo de atribución único para aplicarlo al tablero: Primer toque, Tacto de creación de posibles clientes, Forma de U, Forma de W, Ruta completa o Modelo personalizado. Ruta completa y Modelo personalizado no están disponibles en todos los niveles.

**Campaña**

_Se utiliza en: Información general, crecimiento, retorno de la inversión en anuncios, tráfico web, CMO, medios de pago, marketing de contenido, Passport_

Filtre el tablero por uno o varios nombres de campaña. Los operadores proporcionan al filtro flexibilidad adicional, como el uso de los operadores &quot;contiene&quot; o &quot;comienza con&quot;. Si se ha aplicado un filtro de canal o subcanal, la lista de campañas que aparecen será un subconjunto de los filtros aplicados.

**Categoría 1-10**

_Se utiliza en: Información general, crecimiento, retorno de la inversión en anuncios, CMO, medios pagados, marketing de contenido, velocidad, instantánea, canal de cohorte, Passport_

Aplique filtros de segmento al tablero, utilizando las Categorías y Segmentos que ha creado en la [!DNL Marketo Measure] Configuración. La lista de Categorías que ha creado aparecerá en el menú de filtros, por lo que si no se ha configurado ninguna Categoría, no habrá filtros de Categoría en el menú. Las categorías de segmentos no están disponibles en todos los niveles y el número de categorías disponibles también varía según el nivel.

**Canal**

_Se utiliza en: Información general, crecimiento, gasto en marketing, ROI de anuncios, tráfico web, CMO, medios pagados, marketing de contenido, Velocity, Passport_

Filtre el tablero por uno o varios canales. Los operadores proporcionan al filtro flexibilidad adicional, como el uso de los operadores &quot;contiene&quot; o &quot;comienza con&quot;. Una vez introducido un canal, los valores que se muestran en los filtros Subcanal y Campaña proceden del filtro de subcanal aplicado.

**Etapa de cohorte**

_Se utiliza en: Canal de cohorte_

Seleccione el escenario en el que desea ver una cohorte. El escenario que seleccione aparecerá en la parte superior del canal, con todas las conversiones bajando desde la parte superior.

**Fecha**

_Se utiliza en: Información general, crecimiento, gasto en marketing, retorno de la inversión en anuncios, marketing basado en cuentas, tráfico web, CMO, medios pagados, marketing de contenido, velocidad, instantánea, canal de cohorte, Passport_

Seleccione un intervalo de fechas para filtrar los datos de los tableros mediante operadores de fechas flexibles como &quot;está en el intervalo&quot;, &quot;está en el año&quot; o &quot;es antes&quot;, por ejemplo. La excepción es Instantánea, donde se selecciona una sola fecha para ver una instantánea de los datos.

**Tipo de fecha**

_Se utiliza en: Información general, crecimiento, gasto en marketing, retorno de la inversión en anuncios, marketing basado en cuentas, tráfico web, CMO, medios pagados, marketing de contenido, Passport_

Elija el tipo de fecha que desee utilizar, vinculada al filtro Fecha . El tipo de fecha predeterminado varía según el tablero. La fecha de punto de contacto hace referencia a la fecha en la que se produjo la actividad de marketing, la fecha de creación es la fecha en la que se creó el posible cliente o contacto u oportunidad en CRM y la fecha de cierre es la fecha en la que se cerró la oportunidad.

**Dimensión**

_Se utiliza en: Medios de pago_

Dimension es similar a la función Agrupar por , excepto que se utiliza en el tablero Medios de pago de una manera ligeramente diferente. En lugar de apilar un gráfico, el Dimension cambia las líneas del gráfico Información general, así como el objeto inicial de las tablas.

![](assets/1.png)

De forma predeterminada, el Dimension está establecido en Subcanal y se puede cambiar a:

* Ninguno: Muestra todo en acumulado sin desglose
* Canal: Enumera los datos por canal de marketing
* Subcanal: Muestra los datos por subcanal de marketing
* Campaña: Muestra los datos por campaña
* Cuenta: Muestra los datos por cuenta. Se aplica a [!DNL AdWords], [!DNL Bing]y [!DNL Facebook].
* Grupo de publicidad: Muestra los datos por grupo de anuncios. Se aplica a [!DNL AdWords], [!DNL Bing]y [!DNL Facebook].
* Anuncio: Muestra los datos por anuncio. Se aplica a los anuncios de Doubleclick, por lo que si no se utiliza Doubleclick, no aparecerán resultados
* Anunciante: Muestra los datos por anunciante. Se aplica al anunciante de Doubleclick, por lo que si no se utiliza Doubleclick, no aparecerán resultados
* Creativo: Muestra los datos por creativo. Se aplica a [!DNL AdWords], [!DNL Bing]y [!DNL Facebook].
* Palabra clave: Muestra los datos por palabra clave. Se aplica a [!DNL AdWords], [!DNL Bing]y [!DNL Facebook].
* Colocación: Muestra los datos por ubicación. Se aplica a las ubicaciones de Doubleclick, de modo que si no se utiliza Doubleclick, no aparecerán resultados
* Sitio: Muestra los datos por sitio. Se aplica a los sitios de Doubleclick, por lo que si no se utiliza Doubleclick, no aparecerán resultados

**Agrupar por**

_Se utiliza en: Información general, crecimiento, gasto de marketing, marketing basado en cuentas, tráfico web, CMO_

Ajusta los gráficos para cambiar la dimensión que se está apilando y agrupando. De forma predeterminada, Agrupar por está establecido en Canal y se puede cambiar a:

* Ninguno: Muestra todo en acumulado sin desglose
* Canal: Agrupa los datos por canal de marketing
* Subcanal: Agrupa los datos por subcanal de marketing
* Campaña: Agrupa los datos por campaña
* Cuenta: Agrupa los datos por cuenta. Se aplica a [!DNL AdWords], [!DNL Bing]y [!DNL Facebook].
* Grupo de publicidad: Agrupa los datos por grupo de anuncios. Se aplica a [!DNL AdWords], [!DNL Bing]y [!DNL Facebook].
* Anuncio: Agrupa los datos por anuncio. Se aplica a los anuncios de Doubleclick, por lo que si no se utiliza Doubleclick, no aparecerán resultados
* Anunciante: Agrupa los datos por anunciante. Se aplica al anunciante de Doubleclick, por lo que si no se utiliza Doubleclick, no aparecerán resultados
* Creativo: Agrupa los datos por elemento creativo. Se aplica a [!DNL AdWords], [!DNL Bing]y [!DNL Facebook].
* Palabra clave: Agrupa los datos por palabra clave. Se aplica a [!DNL AdWords], [!DNL Bing]y [!DNL Facebook].
* Colocación: Agrupa los datos por ubicación. Se aplica a las ubicaciones de Doubleclick, de modo que si no se utiliza Doubleclick, no aparecerán resultados
* Sitio: Agrupa los datos por sitio. Se aplica a los sitios de Doubleclick, por lo que si no se utiliza Doubleclick, no aparecerán resultados

![](assets/2.png)

**Página de aterrizaje**

_Se utiliza en: Marketing de contenido_

Explore el rendimiento de una sola página de aterrizaje, o quizás páginas de aterrizaje que contienen una palabra determinada como &quot;blog&quot;.

**Métrica**

_Se utiliza en: Información general, tráfico web, CMO, medios de pago, marketing de contenido_

Hay dos selectores de métricas diferentes que se utilizan en diferentes tableros. El selector de métricas cambia la medida en un gráfico, por lo que puede cambiar entre ver ingresos, gastos o impresiones, por ejemplo.

En las placas Información general y CMO, hay una lista abreviada de valores relacionados con las métricas de ROI:

* Ingresos
* Gastos
* Tratos
* Ingresos del canal
* Oportunidades
* Contactos
* Leads

En los paneles Tráfico web, Medios pagados y Marketing de contenido, hay una lista más larga de valores relacionados con las métricas de ROI y canal:

* Ingresos
* Gastos
* Tratos
* Ingresos del canal
* Oportunidades
* Contactos
* Leads
* Clics
* impresiones
* Visitas
* Visitas únicas
* Vistas de páginas
* Formularios

**Etapa**

_Se utiliza en: Velocity_

De forma predeterminada, el tablero Velocity muestra los tiempos de todas las etapas, pero para profundizar en una etapa específica, utilice el filtro Etapa para seleccionar la etapa.

**Subcanal**

_Se utiliza en: Información general, crecimiento, gasto en marketing, ROI de anuncios, tráfico web, CMO, medios de pago, marketing de contenido, Passport_

Filtre el tablero por uno o varios subcanales. Los operadores proporcionan al filtro flexibilidad adicional, como el uso de los operadores &quot;contiene&quot; o &quot;comienza con&quot;. Si se ha aplicado un filtro de canal, la lista de subcanales que aparecen será un subconjunto de los filtros aplicados. Una vez introducido un subcanal, los valores mostrados en los filtros de campaña proceden del filtro de subcanal aplicado.

**URL**

_Se utiliza en: Tráfico web_

Explorar en profundidad el tráfico de una sola dirección URL, o quizá las direcciones URL que contienen una palabra determinada como &quot;producto&quot;.

**Ganado**

_Se utiliza en: Velocity_

De forma predeterminada, el panel Velocity informa solamente de las oportunidades ganadas cerradas, pero ajusta este filtro para ver la velocidad de las oportunidades ganadas cerradas o perdidas cerradas.
