---
unique-page-id: 18874596
description: 'Configuración de canal personalizado en línea: [!DNL Marketo Measure] - Documentación del producto'
title: Configuración de canal personalizado en línea
exl-id: 170ac564-6cdd-4036-abf0-b9b230bed4f7
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '1236'
ht-degree: 0%

---

# Configuración de canal personalizado en línea {#online-custom-channel-setup}

Para disponer de informes precisos, se deben configurar canales de marketing para que reflejen la estrategia de UTM de su organización. Esta guía le guiará por la mejor manera de configurar sus reglas de canal personalizadas.

## Antes de empezar {#before-you-begin}

Antes de empezar a crear las reglas de canal de [!DNL Marketo Measure], dedique un poco de tiempo a pensar en la organización de sus campañas de marketing y en cómo encajan en el [!DNL Marketo Measure] marco. Debe determinar qué canales, subcanales, campañas y sitios web de referencia desea rastrear.

Cosas que hay que tener en cuenta:

* Su organización puede crear un máximo de 40 canales de marketing personalizados. Esto incluye canales sin conexión y en línea.
* Su organización puede crear hasta 200 subcanales.
* Cada recopilación, o bloque, de datos necesita su propia regla (fila de la hoja de cálculo) para especificar cómo se organizarán los datos. Sea lo más específico posible.
* [!DNL Marketo Measure] da prioridad a los datos en orden descendente, empezando por la fila superior de la hoja de cálculo y bajando. Lee cada cubo, o celda, fila a fila buscando el primer ajuste. A continuación, los datos se ordenan según los valores de estos bloques. Más información a continuación.
* No ordene la hoja en orden alfabético, ya que esto interferirá con las reglas lógicas.
* Una vez cargado el archivo, no se puede cambiar ninguna de las reglas durante siete días. [!DNL Marketo Measure] utiliza esta vez para procesar y actualizar los touchpoints.

## [!DNL Marketo Measure] Lógica y prioridades {#marketo-measure-logic-and-priorities}

El primer paso es descargar la hoja de cálculo de canal personalizada desde el [!DNL Marketo Measure] aplicación. Vaya a **Configuración** en el **Mi cuenta** y seleccione **En línea**. Puede seleccionar: **Descargar plantilla original** o **Descargar reglas actuales**.

![](assets/1.png)

La hoja de cálculo tiene 7 columnas:

![](assets/2.png)

* **Canal:** agregue los distintos canales de marketing aquí
* **Subcanal:** agregue los subcanales correspondientes aquí
* **Campaña:** agregue nombres de campaña aquí, ya sea que el valor provenga de UTM o de campañas de Salesforce para [!DNL Marketo Measure] Funcionalidad de las actividades
* **Medio:** la columna medium representa el valor del parámetro utm_medium
* **Fuente:** la columna de origen representa el valor del parámetro utm_source
* **Página de aterrizaje:** agregar página de aterrizaje aquí
* **Sitio web de referencia:** las direcciones URL de los sitios web que hacen referencia al tráfico de sus páginas o integrados [!DNL Marketo Measure] lógica (indicada entre corchetes)

La octava columna indica qué reglas no se pueden eliminar de la hoja de cálculo con &quot;No eliminar&quot;. La parte superior de la hoja de cálculo tiene reglas de canal predeterminadas que [!DNL Marketo Measure] recomienda no cambiar ni eliminar aunque no utilice estos canales. [!DNL Marketo Measure] tiene integraciones profundas con estas plataformas, por lo que se incluyen de forma predeterminada.

Las filas representan reglas y el orden en el que [!DNL Marketo Measure] prioriza los datos. La primera fila tiene prioridad sobre la segunda fila, la segunda tiene prioridad sobre la tercera y así sucesivamente. Al determinar en qué canal de marketing y subcanal se incluyen los puntos de contacto, [!DNL Marketo Measure] lee de arriba a abajo, de izquierda a derecha, hasta que encuentra una fila que cumple los criterios del punto de contacto. (Es decir, si un punto de contacto tiene un utm_source=Facebook, el punto de contacto se agrupará en el canal Social.Facebook debido a la regla 15 de la captura de pantalla).

![](assets/3.png)

[!DNL Marketo Measure] incluye 12 canales predeterminados para su uso. Estos canales se correlacionan con plataformas con las que [!DNL Marketo Measure] está totalmente integrado. Tanto si los usa como si no, no los elimine. Si utiliza una de estas plataformas, por ejemplo Bing Ads, pero prefiere usar una convención de nombres diferente para el canal o subcanal, puede actualizar el nombre. Se muestra un ejemplo en la siguiente imagen.

![](assets/4.png)

La estructura de las reglas también es importante. Las reglas pueden parecer información repetida y falta datos, pero esta estructura es intencional. Para una clasificación de datos precisa, es necesario asignar cada fuente individual al canal apropiado por separado, incluso las fuentes que comparten subcanales y canales. Cuanto más detalladas y detalladas sean las reglas, más profundos serán los resultados. Básicamente, se recomienda escribir una regla detallada para cada esfuerzo de marketing que se desee rastrear.

Consideremos la siguiente situación: tiene otras publicidades que no desea rastrear por alguna razón o recibe visitas a su sitio web desde un canal familiar, pero no una fuente familiar. Esta situación podría provocar la pérdida de datos si [!DNL Marketo Measure] no encuentra la regla adecuada para ordenar los datos. Para evitar que esto ocurra, [!DNL Marketo Measure] le aconseja romper la regla en varias filas.

Cada parámetro o componente de la regla se asigna por separado al canal. Por ejemplo, cuando [!DNL Marketo Measure] has [!DNL Facebook] para ordenar, busca reglas relacionadas con [!DNL Facebook]. Analiza de arriba a abajo. En el ejemplo que se muestra a continuación, [!DNL Marketo Measure] entendería eso por primera vez [!DNL Facebook] subcanal, todo lo que tiene que leer es el parámetro de origen para soltar datos en el bloque de esa regla.

![](assets/5.png)

La siguiente regla solo solicita el parámetro medium , por lo que todos los datos con ese parámetro se agrupan en este canal. Por último, para [!DNL Facebook], cualquier dato proveniente de la URL de Facebook se colocará en el último bloque de Facebook.

El canal predeterminado &quot;Otro&quot; existe para capturar datos que no cumplen los criterios de ninguna regla. Observe que algunos de los bloques del canal Otros contienen asteriscos (&#42;). Estos asteriscos representan caracteres comodín que actúan como captador global.

![](assets/6.png)

Debido a [!DNL Marketo Measure] que funciona de arriba a abajo, tenga en cuenta que la regla comodín, indicada con un asterisco (&#42;), debe colocarse al final de la hoja de reglas. Todos los datos que no se hayan capturado o clasificado por las demás reglas se agregarán automáticamente a este bloque comodín.

A continuación se muestran más ejemplos de lógica comodín:

* &#42;email&#42; = contiene &quot;email&quot;
* &#42;email = termina con &quot;email&quot;
* email&#42; = [!UICONTROL comienza con el correo electrónico]

Además, tenga en cuenta que si crea un subcanal para uno de los canales, deberá crear un subcanal para todas las reglas de dicho canal. En otras palabras, si crea un subcanal, no puede dejar en blanco el resto de las columnas.

## Configuración de las reglas de canales personalizados {#setting-up-your-custom-channels-rules}

Una vez que haya decidido cómo desea organizar y priorizar los datos, estará listo para agregar las reglas a la hoja de cálculo. A continuación se indican algunas prácticas recomendadas:

* Mantenga las reglas tan sencillas como sea posible desde el principio. Siempre puede basarse en las reglas a medida que avanza.
* No agregue ningún carácter especial en los nombres de canal (por ejemplo, $%#&amp;&#42;@)
* No edite las reglas asociadas con BingAds y AdWords. Estas reglas son cruciales para agrupar los datos que proceden automáticamente de la variable [!DNL Marketo Measure] Integración de API con estas plataformas. No obstante, no supone ningún problema cambiar el nombre del subcanal y del canal para adaptarlo a sus necesidades.
* No elimine las reglas que contengan una nota &quot;No eliminar&quot;.
* Las reglas de búsqueda orgánicas siempre se colocan después del [!UICONTROL Reglas de búsqueda de pago]
* No se pueden crear reglas basadas en subdominios distintos.
* Si tiene más de un valor para agregar en una celda de la hoja de cálculo, asegúrese de separar los valores con un punto y coma `;` solo. Sin comas ni espacios.
* No es necesario añadir puntos com (.com) al final de la URL de referencia.
* Al añadir una dirección URL de referencia, no la ponga entre corchetes como las demás reglas relacionadas con la API.

## Cargar las reglas de los canales personalizados {#uploading-your-custom-channels-rules}

Asegúrese de que los nuevos valores de canal y subcanal que está agregando en el CSV ya se hayan agregado en el área de configuración de canal de la cuenta Bizible. Compruebe si todos los nombres de canal y subcanal coinciden en el CSV con el área de configuración de canal de su [!DNL Marketo Measure] cuenta. Asegúrese de comprobar la existencia de comas y espacios.

Si recibe un mensaje de error durante la carga, corrija el problema y vuelva a cargar. Si no se recibe ningún mensaje de error, haga clic en **Guardar y procesar** en la parte inferior de la página.
