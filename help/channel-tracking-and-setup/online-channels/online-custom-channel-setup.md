---
unique-page-id: 18874596
description: Configuración de canales personalizados en línea,  [!DNL Marketo Measure]
title: Configuración de canales personalizados en línea
exl-id: 170ac564-6cdd-4036-abf0-b9b230bed4f7
feature: Channels
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: ht
source-wordcount: '1219'
ht-degree: 100%

---

# Configuración de canales personalizados en línea {#online-custom-channel-setup}

Para disponer de un sistema de informes preciso, se deben configurar canales de marketing para que reflejen la estrategia de UTM de su organización.  Esta guía le orienta acerca de la mejor manera de configurar sus reglas de canales personalizados.

## Antes de empezar {#before-you-begin}

Antes de empezar a crear las reglas de canales de [!DNL Marketo Measure], dedique un poco de tiempo a pensar en la organización de sus campañas de marketing y en cómo encajan en el marco de trabajo de [!DNL Marketo Measure]. Determine qué canales, subcanales, campañas y sitios web de referencia desea rastrear.

Cosas que hay que tener en cuenta:

* Su organización puede crear un máximo de 40 canales de marketing personalizados. Esto incluye canales sin conexión y en línea.
* Su organización puede crear hasta 200 subcanales.
* Cada recopilación, o bloque, de datos necesita su propia regla (fila de la hoja de cálculo) para especificar cómo se organizarán los datos. Sea lo más específico posible.
* La lógica de [!DNL Marketo Measure] da prioridad a los datos en orden descendente, empezando por la fila superior de la hoja de cálculo y bajando. Lee cada bloque, o celda, fila a fila, buscando el primer ajuste. A continuación, los datos se ordenan según los valores de estos bloques. Más información a continuación.
* No ordene la hoja en orden alfabético, ya que esto interfiere con las reglas lógicas.
* Una vez cargado el archivo, no se puede cambiar ninguna de las reglas durante siete días. [!DNL Marketo Measure] utiliza este tiempo para procesar y actualizar los puntos de contacto.

## Lógica y prioridades de [!DNL Marketo Measure] {#marketo-measure-logic-and-priorities}

El primer paso es descargar la hoja de cálculo de canales personalizados desde la aplicación [!DNL Marketo Measure]. Vaya a **Configuración** en la pestaña **Mi cuenta** y seleccione **En línea**. Puede seleccionar **Descargar plantilla original** o **Descargar reglas actuales**.

![](assets/1.png)

La hoja de cálculo tiene siete columnas:

![](assets/2.png)

* **Canal:** agregue los distintos canales de marketing aquí
* **Subcanal:** agregue los subcanales correspondientes aquí
* **Campaña:** añada nombres de campaña aquí, ya sea que el valor provenga de UTM o de campañas de Salesforce para la funcionalidad de las actividades de [!DNL Marketo Measure]
* **Medio:** la columna Medio representa el valor del parámetro utm_medium
* **Origen:** la columna Origen representa el valor del parámetro utm_source
* **Página de destino:** agregue la página de destino aquí
* **Sitio web de referencia:** las direcciones URL de los sitios web que hacen referencia al tráfico de sus páginas o la lógica integrada de [!DNL Marketo Measure] (indicada entre corchetes)

La octava columna indica qué reglas no se pueden eliminar de la hoja de cálculo con “No eliminar”.  La parte superior de la hoja de cálculo tiene reglas de canal predeterminadas que [!DNL Marketo Measure] recomienda no cambiar ni eliminar aunque no utilice estos canales. [!DNL Marketo Measure] tiene integraciones profundas con estas plataformas, por lo que se incluyen de forma predeterminada.

Las filas representan reglas y el orden en el que [!DNL Marketo Measure] da prioridad a los datos. La primera fila tiene prioridad sobre la segunda fila, la segunda tiene prioridad sobre la tercera y así sucesivamente. Al determinar en qué canal y subcanal de marketing se incluirán los puntos de contacto, [!DNL Marketo Measure] lee de arriba a abajo, de izquierda a derecha, hasta que encuentra una fila que cumple los criterios del punto de contacto. (Si un punto de contacto tiene un elemento `utm_source=Facebook`, el punto de contacto se incluye en el canal Social.Facebook debido a la regla 15 de la captura de pantalla).

![](assets/3.png)

[!DNL Marketo Measure] incluye 12 canales predeterminados para su uso. Estos canales se correlacionan con plataformas con las que [!DNL Marketo Measure] está totalmente integrado. Tanto si los usa como si no, no los elimine. Si utiliza una de estas plataformas (por ejemplo, Bing Ads), pero prefiere usar una convención de nombres diferente para el canal o subcanal, puede actualizar el nombre. Se muestra un ejemplo en la siguiente imagen.

![](assets/4.png)

La estructura de las reglas también es importante. Es posible que parezca que las reglas contengan información repetida y que falten datos en ellas, pero esta estructura es intencional. Para obtener una clasificación de datos precisa, es necesario asignar cada fuente individual al canal apropiado por separado, incluso las fuentes que comparten subcanales y canales. Cuanto más detalladas y granulares sean las reglas, más esclarecedores serán los resultados. Básicamente, se recomienda escribir una regla detallada para cada esfuerzo de marketing que se desee rastrear.

Consideremos la siguiente situación: tiene otros anuncios que no desea rastrear por alguna razón o recibe visitas a su sitio web desde un canal familiar, pero no una fuente familiar. Esta situación podría provocar la pérdida de datos si [!DNL Marketo Measure] no encuentra la regla adecuada para ordenar los datos. Para evitar que esto ocurra, [!DNL Marketo Measure] le aconseja romper la regla en varias filas.

Cada parámetro o componente de la regla se asigna por separado al canal. Por ejemplo, cuando [!DNL Marketo Measure] tiene datos de [!DNL Facebook] para ordenar, busca reglas relacionadas con [!DNL Facebook]. Analiza de arriba a abajo. En el ejemplo que se muestra a continuación, [!DNL Marketo Measure] entendería eso para el primer subcanal de [!DNL Facebook], todo lo que tiene que leer es el parámetro de origen para soltar datos en el bloque de esa regla.

![](assets/5.png)

La siguiente regla solo solicita el parámetro Medio, por lo que todos los datos con ese parámetro se agrupan en este canal. Por último, para [!DNL Facebook], cualquier dato proveniente de la URL de Facebook se coloca en el último bloque de Facebook.

El canal predeterminado “Otros” existe para capturar datos que no cumplen los criterios de ninguna regla. Observe que algunos de los bloques del canal Otros contienen asteriscos (&#42;). Estos asteriscos representan caracteres comodín que actúan como captador global.

![](assets/6.png)

Dado que la lógica de [!DNL Marketo Measure] funciona al máximo, tenga en cuenta de que la regla comodín, indicada con un asterisco (&#42;), debe colocarse al final de la hoja de reglas.  Todos los datos que el resto de reglas no hayan capturado o clasificado se agregan automáticamente a este bloque comodín.

A continuación se muestran más ejemplos de lógica comodín:

* &#42;correo&#42; = contiene “correo”
* &#42;correo = termina con “correo”
* correo&#42; = [!UICONTROL comienza con correo]

Además, tenga en cuenta que si crea un subcanal para uno de los canales, deberá crear un subcanal para todas las reglas de dicho canal.  En otras palabras, si crea un subcanal, no puede dejar en blanco el resto de las columnas.

## Configuración de las reglas de canales personalizados {#setting-up-your-custom-channels-rules}

Una vez que haya decidido cómo desea organizar y priorizar los datos, estará listo para agregar las reglas a la hoja de cálculo.  A continuación se indican algunas prácticas recomendadas:

* Mantenga las reglas tan sencillas como sea posible desde el principio. Siempre puede basarse en las reglas a medida que avanza.
* No agregue ningún carácter especial en los nombres de canal (por ejemplo, $%#&amp;&#42;@)
* No edite las reglas asociadas a Bing Ads y AdWords. Estas reglas son cruciales para agrupar los datos que proceden automáticamente de la integración de API de [!DNL Marketo Measure] con estas plataformas. No obstante, no supone ningún problema cambiar el nombre del subcanal y del canal para adaptarlo a sus necesidades.
* No elimine las reglas que contengan la nota “No eliminar”.
* Las reglas de búsqueda orgánicas siempre se colocan después de las [!UICONTROL reglas de búsqueda de pago]
* No se pueden crear reglas basadas en subdominios distintos.
* Si tiene más de un valor para agregar en una celda de la hoja de cálculo, asegúrese de separar los valores solo con un punto y coma (`;`). Sin comas ni espacios.
* No es necesario añadir punto com (.com) al final de la URL de referencia.
* Al añadir una dirección URL de referencia, no la ponga entre corchetes como las demás reglas relacionadas con la API.

## Cargar las reglas de los canales personalizados {#uploading-your-custom-channels-rules}

Asegúrese de que los nuevos valores de canal y subcanal que está agregando en el CSV ya se hayan agregado en el área de configuración de canal de la cuenta Bizible.  Compruebe si todos los nombres de canal y subcanal coinciden en el CSV con el área de configuración de canal de su cuenta de [!DNL Marketo Measure]. Asegúrese de comprobar la existencia de comas y espacios.

Si recibe un mensaje de error durante la carga, corrija el problema y vuelva a cargar.  Si no recibe ningún mensaje de error, haga clic en **Guardar y procesar** en la parte inferior de la página.
