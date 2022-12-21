---
description: "[!DNL Marketo Measure] Guía de informes - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Guía de informes"
exl-id: 9b991f9e-c187-4b43-b0a8-8ed3e9a6056b
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '6392'
ht-degree: 1%

---

# [!DNL Marketo Measure] Guía de informes {#marketo-measure-reporting-guide}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero aún así ver &quot;Bizible&quot; en su CRM. Estamos trabajando para que esto se actualice y el cambio de marca se reflejará pronto en su CRM.

Antes de crear un [!DNL Marketo Measure] es fundamental confirmar el informe [!DNL Marketo Measure] La configuración de la cuenta se ha revisado y configurado para garantizar que los datos de los informes sean precisos y reflejen las características específicas de su empresa. Además, los informes de proyectos funcionan mejor cuando siguen un proceso estructurado. Justin Norris, un [!DNL Marketo Measure] usuario avanzado, abogado y socio de [Perkuto](https://perkuto.com/) resumen de forma experta [cómo enfocar los informes en [!DNL Marketo Measure]](https://perkuto.com/blog/turning-attribution-data-into-actionable-insights/):

**Establecer objetivos**: &quot;La primera pregunta que hay que hacer es &quot;¿por qué medimos?&quot; Lori Wizard de [Forrester Research](https://go.forrester.com/) lo resumió bien en un [Seminario web de Marketo](https://www.marketo.com/webinars/beyond-revenue-performance-real-kpis-of-b2b-marketing/). Según ella, &quot;medimos para probar o validar una decisión o el valor del marketing o para mejorar (mejora del proceso)&quot;. Se agregaría que las perspectivas de una buena medición también proporcionan información y orientación en el proceso de planificación de marketing.

Así que antes de comenzar, es esencial ser claro como el cristal en sus objetivos, las preguntas que están tratando de responder, o los problemas que están tratando de resolver. ¿Qué historia quieres contar? ¿Qué decisiones se tomarán en consecuencia? Con demasiada frecuencia estos fundamentos están mal pensados, lo que lleva a la frustración de todos los involucrados&quot;.

**Diseño de informes**: &quot;A continuación, debe diseñar el informe y determinar las dimensiones, métricas y conjuntos de datos específicos que contendrá. Una experiencia común es proporcionar a un usuario empresarial exactamente lo que solicita, solo para que sienta que sus necesidades no se satisfacen. Esto se debe a que la perspectiva que busca un usuario empresarial no siempre está contenida en el informe que solicita. Un buen analista (o una persona del MPS con un analista que esté en funcionamiento) hará preguntas aclaratorias, establecerá definiciones comunes (&quot;entonces, ¿qué quieres decir con el posible cliente?&quot;) e incluso esbozará una imagen del informe final para asegurarse de que haya alineación. Sólo entonces construye el informe, sabiendo que tiene un sólido conjunto de requisitos&quot;.

**Creación de informes**: &quot;Una vez que vas a construir, no es raro que te encuentres con barricadas o callejones sin salida. Por ejemplo, es posible que descubra que carece de un punto de datos esencial o que los objetos no se vinculan de la manera que necesita. Para resolver estos problemas, también creo que es crítico entender lo que está pasando &quot;bajo el capullo&quot; en tu &quot;máquina&quot; de reportes. Esta fluidez le permitirá dimensionar rápidamente una solicitud de informes y evaluar si es factible (y, cuando no lo sea, idear soluciones creativas más fácilmente).&quot;

Echemos un vistazo a &quot;debajo del capó&quot; para entender mejor qué hace que el [!DNL Marketo Measure] ejecución del equipo de informes de atribución.

## Objetos de punto de contacto del comprador (CRM) {#buyer-touchpoint-objects-crm}

En el nivel más alto, hay dos categorías de informes basadas en los dos objetos de Touchpoint de Comprador diferentes: Estas categorías determinan qué tipo de [!DNL Marketo Measure] datos sobre los que desee informar: datos relacionados con un _individual_ o datos relacionados con un _oportunidad_.

1. **Puntos de contacto del comprador** (BT) / Individuos / Participación total

   * Se utiliza comúnmente para métricas de &quot;inicio del canal&quot; (TOFU) y para informes relacionados con _individuales_ (Posibles clientes, contactos, [!DNL Marketo Measure] Personas)
   * Los BT se utilizan para comprender todas las interacciones de marketing relacionadas con **people**, ya que contienen el historial de puntos de contacto completo para cada persona. Como recordatorio, estos puntos de contacto se crean en CRM para el primer contacto anónimo, el contacto de creación de posibles clientes y cualquier envío de formulario o punto de contacto posterior que elija sincronizar desde una campaña o actividad sin conexión.

1. **Puntos de contacto de atribución del comprador** (MTD) / Oportunidad / Nivel de cuenta / Ingresos

   * Se utiliza comúnmente para métricas y sistemas de informes relacionados con las métricas &quot;central y/o inferior del canal&quot; (MOFU y BOFU) _Oportunidades_.
   * Las MTD representan los puntos de contacto relevantes de todas las personas conectadas a la **oportunidad** (ya sea a través de las funciones de contacto de oportunidad o a través de un ID de cuenta compartido, según la configuración). A diferencia de los BT que se refieren únicamente a personas, las MTD también pueden asociarse con **ingresos**. Como tal, utilizará las MTD para responder preguntas relacionadas con las oportunidades, incluyendo cuántas oportunidades se abrieron o cerraron, o el valor de la canalización y los ingresos obtenidos.

>[!NOTE]
>
>Las MTD se crean a partir de los MTD. Básicamente, el seguimiento comienza a nivel individual a través de los BT. Una vez creada una oportunidad en una cuenta, se hace referencia a todos los BT de Contactos bajo la misma cuenta y se pueden crear MTD relacionadas con la oportunidad, por lo que querrá usar uno u otro según las preguntas que esté intentando responder: preguntas relacionadas con las métricas &quot;Personas&quot; (informes de BT) o preguntas relacionadas con las métricas &quot;Oportunidad&quot; (informes de BAT)

Artículo de soporte: [Diferencia entre puntos de contacto del comprador y puntos de contacto de atribución del comprador](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md#configuration-and-setup)

## Punto de contacto del comprador (BT) {#buyer-touchpoint-bt}

El punto de contacto del comprador (BT) es el objeto que se utiliza para rastrear cada interacción de marketing que alguien tiene con sus materiales de marketing. Cada individuo (posible cliente/contacto/[!DNL Marketo Measure] Persona) El recorrido estaría representado por sus OE conexos. En [!DNL Marketo Measure], el recorrido de una persona consiste en:

1. ¿Cómo interactuó esta persona con nuestra marca por primera vez? (Primer toque o _FT_)
1. ¿Cómo se convirtió esta persona/se hizo conocida/se convirtió en posible cliente? (Creación de posibles clientes o _LC_)
1. ¿De qué otra manera ha interactuado esta persona con nuestra marca y materiales de marketing desde que se convirtió en líder? (_PostLC_)

Los puntos de contacto del comprador se utilizan para responder preguntas relacionadas con _people_ (&quot;personas&quot; están representadas por posibles clientes o contactos dentro de un CRM), como métricas de adquisición o generación de posibles clientes/contactos, en lugar de métricas relacionadas con oportunidades. Por ejemplo:

* ¿Qué canales ofrecen la mayor cantidad de posibles clientes?
* ¿Qué canales son más o menos costosos para crear un nuevo posible cliente?
* ¿Con qué contenido están relacionados mis posibles clientes/contactos?
* ¿Cuál es la historia de marketing de títulos, roles, personalidades particulares?
* ¿Qué canales controlan los MQL u otros estados de posible cliente/contacto?

Principalmente, las empresas necesitan saber, &quot;¿de dónde vienen mis posibles clientes/contactos?&quot;. Históricamente, esto se respondió con un solo valor dimensional (por ejemplo, la fuente de posibles clientes). Sin embargo, como se describe en los números 1 y 2, sabemos que los posibles clientes pueden tener múltiples puntos de contacto durante su recorrido de convertirse en posibles clientes. El punto de contacto del comprador nos permite conocer las dos interacciones más cruciales que representan cómo se generó un posible cliente: su primer toque y su toque de creación de posibles clientes. Los puntos de contacto del comprador también son _multidimensional_ lo que significa que transportan cargas de datos de marketing, principalmente de dónde viene la persona (Canal de marketing) y con qué participa la persona (Contenido).

La variable [modelos de atribución](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md) para obtener la mejor perspectiva de las métricas basadas en personas, consulte:

* **Primer toque** - 100% de crédito de atribución al primer contacto del posible cliente (FT)
* **Creación de posibles clientes** - 100% de crédito de atribución al contacto de creación de posibles clientes (LC)
* **Forma de U** - enfoque multitáctil, con un 40% de crédito a FT, un 40% de crédito a LC

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-1.png"></td> 
   <td>El Modelo de Forma de U está diseñado para dar crédito a cualquier punto de contacto del comprador que resuma cómo un posible cliente se convirtió en posible cliente. Aunque también se puede informar de los puntos de contacto subsiguientes de estos posibles clientes para comprender la participación adicional (Post LC), no forman parte del <strong>Recorrido de creación de posibles clientes</strong> por lo tanto, no obtienen ningún crédito de atribución en los modelos FT, LC o U.<p>

&#42;Normalmente, la atribución en forma de U refleja una división incluso 50/50 entre FT y LC. Si el posible cliente se convierte en la misma sesión que el primer contacto, un solo punto de contacto representaría las posiciones de los puntos de contacto FT y LC. Por lo tanto, el 100 % de la atribución se asignaría a un solo punto de contacto.</td>
</tr>
 </tbody>
</table>

Estos modelos hacen mucho hincapié en las interacciones de las primeras etapas y en la participación de los canales. La atribución de Forma de U es el modelo recomendado, ya que tiene en cuenta tanto los puntos de contacto FT como LC, lo que garantiza que se da crédito a cualquier contacto que haya influido en el posible cliente en la creación. Sin embargo, se puede obtener información adicional de los modelos de primer toque y de creación de posibles clientes si desea comprender mejor esas partes específicas del recorrido de posibles clientes.

## Informes recomendados con el punto de contacto del comprador (BT) {#recommended-reports-using-the-buyer-touchpoint-bt}

1. **POSIBLES CLIENTES CON PUNTOS DE CONTACTO DEL COMPRADOR**

**1,1 | Nuevos posibles clientes por canal de marketing**

Resumiendo los datos de los puntos de contacto del comprador de posibles clientes según el campo &quot;Canal de marketing&quot; es la vista de nivel más alto que representa qué canales/tácticas están influyendo en los nuevos posibles clientes en la creación. Estructurar este informe en torno a un &quot;Tipo de fecha&quot; = &quot;Fecha de creación&quot; garantiza que se establezca en el informe una cohorte de &quot;nuevos posibles clientes netos&quot; (cuando el posible cliente se creó en su CRM).

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>¿Qué canales de marketing influyen en los posibles clientes en la creación?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Posibles clientes y puntos de contacto del comprador (CRM)<br>
   Métrica: Posibles clientes ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Campo de fecha/Tipo de fecha</td> 
   <td>Fecha de creación de posible cliente (CRM) / Fecha de creación (Discover)</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccionar el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Canal de marketing</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Primer toque, Creación de posibles clientes, <strong>Forma de U</strong><br>
   *SUME los campos "Recuento" en los informes CRM (Recuento: Primer toque, Recuento: Creación de posibles clientes, Recuento: Forma de U)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Para cualquier tipo de informe &quot;Posibles clientes con puntos de contacto del comprador&quot;, comience personalizando el informe pregenerado llamado &quot;[!DNL Marketo Measure] 101 | Posibles clientes por canal&quot;. Este informe está disponible de forma predeterminada y es un bueno simulador de pruebas creado previamente, tal y como se describe en la tabla anterior, y se puede personalizar rápidamente para satisfacer necesidades de informes más específicas.

**1,2 | Nuevos posibles clientes por campaña (o perspectivas más detalladas)**

Para obtener información más detallada sobre los datos resumidos en el informe &quot;Nuevos posibles clientes por canal de marketing&quot; (1.1), agregue un resumen adicional a nivel de campaña. Esto le permitirá no solo comprender qué son los &quot;Canales de marketing&quot; que llevan a los nuevos posibles clientes a la creación, sino también, más específicamente, qué campañas dentro de esos canales están teniendo el mejor rendimiento:

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué <i>campañas</i> ¿están influyendo los posibles clientes en la creación?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Posibles clientes y puntos de contacto del comprador (CRM)<br>
   Métrica: Posibles clientes ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Campo de fecha/Tipo de fecha</td> 
   <td>Fecha de creación de posible cliente (CRM) / Fecha de creación (Discover)</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccionar el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Nombre de campaña de publicidad (CRM)</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Primer toque, Creación de posibles clientes, <strong>Forma de U</strong><br>
   *SUME los campos "Recuento" en los informes CRM (Recuento: Primer toque, Recuento: Creación de posibles clientes, Recuento: Forma de U)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Obtenga una perspectiva aún más granular al resumir el informe con otros campos disponibles del objeto Punto de contacto del comprador. Para ello, configure agrupaciones (CRM) o dimensiones adicionales (Discover). Según el canal (que puede ser representativo de su función), puede haber detalles adicionales más allá del nivel de campaña en el que busca obtener información. Vamos a explorar en profundidad &#39;Búsqueda paga&#39;, por ejemplo, en la siguiente tabla...

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué <i>keywords</i> ¿están influyendo los posibles clientes en la creación?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Posibles clientes y puntos de contacto del comprador (CRM)<br>
   Métrica: Posibles clientes ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td>Canal de marketing = Búsqueda paga</td> 
  </tr>
  <tr>
   <td>Campo de fecha/Tipo de fecha</td> 
   <td>Fecha de creación de posible cliente (CRM) / Fecha de creación (Discover)</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccionar el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Texto de palabra clave (CRM)/Palabra clave (Discover)</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Primer toque, Creación de posibles clientes, <strong>Forma de U</strong><br>
   *SUME los campos "Recuento" en los informes CRM (Recuento: Primer toque, Recuento: Creación de posibles clientes, Recuento: Forma de U)</td> 
  </tr>
 </tbody>
</table>

El nivel de granularidad puede variar según el canal. El enfoque recomendado sería preguntarse: &quot;¿qué hay del canal X que estoy buscando entender con más detalle?&quot;. Los administradores de búsqueda pagada también pueden estar interesados en dimensiones adicionales como:

* Nombre de campaña de publicidad
* Contenido de la publicidad
* Grupo de anuncio

Sin embargo, los administradores de eventos pueden estar más interesados en saber qué eventos específicos o qué tipos de eventos influyeron más en los posibles clientes en la creación:

* Nombre de campaña de publicidad/Campaña de Salesforce = Evento específico
* Medio = &quot;Tipo&quot; de campaña

**RECORDATORIO**: Es posible que sea necesario agregar filtros adicionales a cualquiera de las variaciones de informe que se describen más arriba o más abajo. Estos filtros serían específicos de su organización y serían algo que los equipos de operaciones de marketing u operaciones de ventas podrían ayudarle a asesorar. No es inusual que una organización ejecute los mismos filtros en todos los informes para garantizar que el informe sea lo más limpio y preciso posible. Algunos ejemplos comunes podrían ser:

* Filtrado de registros internos de pruebas, generalmente por dirección de correo electrónico
* Filtrado basado en ciertos &quot;tipos de registros&quot; que pueden ser específicos de su unidad de negocio

**1,3 | Nuevos posibles clientes por contenido (solo informes CRM)**

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué <i>contenido</i> ¿están influyendo los posibles clientes en la creación?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Posibles clientes y puntos de contacto del comprador (CRM)</td> 
  </tr>
  <tr>
   <td>Campo de fecha</td> 
   <td>Fecha de creación de cliente potencial</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccionar el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Página de aterrizaje<br> 
   URL del formulario</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Primer toque, Creación de posibles clientes, <strong>Forma de U</strong><br></td> 
  </tr>
 </tbody>
</table>

**RECORDATORIO**: Los dos campos principales para la creación de informes sobre contenido o recursos digitales son &quot;Página de aterrizaje&quot; y &quot;URL del formulario&quot;. Estos dos valores pueden ser los mismos si el posible cliente convierte (envía un formulario) en la misma página en la que &quot;aterrizó&quot; (página de aterrizaje). _without_, a veces estos valores son diferentes. Por ejemplo, el posible cliente puede hacer clic en un vínculo de Facebook que les lleve a una página de su sitio web (sería el valor &quot;Página de aterrizaje&quot;). El posible cliente puede salir de esa página, continuar con la sesión en el sitio y terminar enviando un formulario a otra página (URL del formulario). Esto se resumiría en un solo punto de contacto que representa de dónde viene el posible cliente (Canal de marketing), qué contenido los trajo al sitio (Página de aterrizaje) y qué contenido terminaron descargando (URL del formulario). &#39;URL del formulario&#39; también es el campo de referencia para los informes de otros formularios que no están asociados con contenido descargable, como los formularios &#39;Contacto&#39; o &#39;Solicitud de demostración&#39;.

>[!TIP]
>
>Obtenga información sobre el contenido específico con filtros adicionales
>
>* Filtrar por: &quot;Página de aterrizaje&quot; CONTIENE (por ejemplo:
   >   * /blog
   >   * /ebook
   >   * /webinar
>
>* O: &quot;URL del formulario&quot; CONTIENE (por ejemplo)
   >   * /contact
   >   * /demo


Los informes basados en &quot;contenido&quot; proporcionan un valor bueno al realizar informes en cualquier parte del canal; sin embargo, lo más común es que se utilicen en la parte superior del canal para proporcionar información adicional sobre una participación inicial de posibles clientes. Considerando que la &quot;Búsqueda orgánica&quot; tiende a ser el canal más fuerte a la hora de impulsar la participación inicial (FT), no hay tantos datos a nivel de &quot;Campaña&quot;.

Los informes basados en &quot;contenido&quot; son buenos para comprender qué es lo que impulsa los posibles clientes de forma más específica dentro del canal de marketing de nivel superior, en este caso &quot;Búsqueda orgánica&quot;.

**1,4 | Participación total de posibles clientes en un intervalo de fechas determinado**

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué canales de marketing han tenido la mayor cantidad <i>participación total de posibles clientes</i> en el pasado (semana/mes/trimestre)?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Posibles clientes y puntos de contacto del comprador (CRM)<br> 
   Métrica: Posibles clientes ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Campo de fecha/Tipo de fecha</td> 
   <td>Fecha de Touchpoint</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccionar el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Canal de marketing (o más granular)</td> 
  </tr>
  <tr>
   <td>Modelos óptimos*</td> 
   <td>*Este informe trata menos de medir de dónde provienen los posibles clientes con un modelo de atribución, pero más acerca de la variable <i>número total de puntos de contacto (cantidad de participación)</i>, incluidas las que siguen al contacto de creación de posibles clientes. El recuento total de registros de puntos de contacto reflejaría qué canales han visto la mayor participación de posibles clientes.</td> 
  </tr>
 </tbody>
</table>

**RECORDATORIO**: Basar los informes en &quot;Fecha de punto de contacto&quot; es la forma más reflexiva de comprender el rendimiento de marketing durante un intervalo de fechas determinado. &quot;Fecha de punto de contacto&quot; estructura el informe de forma que la atribución no solo esté relacionada con el canal, la campaña o el contenido, sino que también muestre cuándo se produjo el punto de contacto. Esta es la manera más efectiva de comprender qué compromiso de marketing estaba ocurriendo en un momento determinado y también la manera recomendada de medir el impacto del marketing en comparación con el gasto de marketing invertido durante el mismo tiempo. Se recomienda cuando se realiza cualquier gasto de marketing o análisis de ROI (ver 5.1).

**2. POSIBLES CLIENTES EN MARKETING CALIFICADOS CON PUNTOS DE CONTACTO DEL COMPRADOR**

Uno de los informes más comunes se centra no solo en los nuevos posibles clientes o la participación de los posibles clientes, sino también, más específicamente, en los &quot;posibles clientes cualificados de marketing&quot; (MQL). Hay un par de enfoques diferentes en lo que se refiere a informar sobre MQL según qué [!DNL Marketo Measure] funciones y funcionalidades a las que tiene acceso.

**2,1 | Marketing de posibles clientes calificados por canal (multitáctil)**

Este enfoque para medir el impacto del marketing en la influencia de MQL es esencialmente una continuación del informe &quot;Nuevos posibles clientes por canal de marketing&quot; (1.1), pero con los criterios adicionales que se miden los posibles clientes son, más específicamente, MQL. El modelo de atribución en Forma de U sigue siendo recomendado aquí para identificar qué canales de marketing y contenido generan posibles clientes que _probable_ para convertirse en un MQL:

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>¿Qué canales de marketing son los mejores para generar nuevos posibles clientes que se convierten en <i>MQL</i>?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Posibles clientes y puntos de contacto del comprador (CRM)<br> 
   Métrica: Posibles clientes ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td>MQL = true*<br>
   *<i>Los MQL pueden definirse de forma diferente por organización. Asegúrese de que la variable [!DNL Marketo Measure] El informe se filtra para MQL que utilizan los mismos campos que otros informes basados en MQL. Se tendría que crear un filtro de segmento de la misma manera para generar informes sobre MQL en [!DNL Marketo Measure] Discover.</i></td> 
  </tr>
  <tr>
   <td>Campo de fecha/Tipo de fecha</td> 
   <td>Fecha de MQL (o equivalente) / Fecha de creación ([!DNL Marketo Measure] Discover)<br> <i>La Fecha de creación de posibles clientes también se podría usar en los informes CRM si "Fecha de MQL" no es una opción en su CRM. Es importante tener en cuenta qué campo de fecha utiliza para definir el conjunto de datos cohortados.</i></td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccionar el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Canal de marketing</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Primer toque, Creación de posibles clientes, <strong>Forma de U</strong><br> 
   SUME los campos "Recuento" en los informes CRM (Recuento: Primer toque, Recuento: Creación de posibles clientes, Recuento: Forma de U)</td> 
  </tr>
 </tbody>
</table>

**2,2 | Marketing de posibles clientes calificados por canal (de un solo contacto, solo CRM)**

Este enfoque para medir el impacto del marketing en la influencia de MQL se centra más en identificar qué _punto de contacto único_ fue el último contacto antes de que el posible cliente llegara a MQL.

>[!NOTE]
>
>Para ejecutar este informe, se requiere un valor &quot;Estado de posible cliente&quot; de &quot;MQL&quot; para definir el escenario de MQL con fines de seguimiento (Etapa de canal). Si no se realiza el seguimiento de los MQL mediante el campo &quot;Estado de posible cliente&quot;, la función Modelo de atribución personalizado con etapas personalizadas es necesaria para crear un escenario &quot;MQL&quot; personalizado en el [!DNL Marketo Measure] Configuración de la cuenta.

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>¿Qué canales de marketing son los más fuertes para presionar a los posibles clientes para que alcancen el estado de MQL?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Posibles clientes y puntos de contacto del comprador (CRM)<br>
   <i>este informe solo es posible dentro de los informes de CRM. No es posible filtrar ciertos valores de "Posición del punto de contacto" en [!DNL Marketo Measure] Discover</i></td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td><strong>La posición de Touchpoint CONTIENE "MQL"</strong></td> 
  </tr>
  <tr>
   <td>Campo de fecha/Tipo de fecha</td> 
   <td>Fecha MQL (o equivalente)</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccionar el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Canal de marketing</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td><i>Dado que este informe se filtra en un solo punto de contacto, los modelos de atribución de nivel de posible cliente no son tan relevantes. Al igual que el "Informe de participación de posibles clientes" (1.4), el número de registros de puntos de contacto se aprovecharía aquí para comprender qué canales son los más sólidos (cada posible cliente solo tendría un punto de contacto MQL).</i></td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Explore otras agrupaciones o dimensiones para obtener información adicional sobre los MQL. Como se menciona en los demás informes &quot;Posibles clientes con puntos de contacto del comprador&quot;, el punto de contacto del comprador ofrece mucha más granularidad que solo el canal de marketing. Un informe basado en &quot;contenido&quot; también podría combinarse con cualquiera de los informes de MQL anteriores para comprender mejor qué contenido influye mejor en los MQL.

**3. [!DNL MARKETO MEASURE] PERSONAS CON PUNTOS DE CONTACTO DEL COMPRADOR**

Hay una tercera personalización [!DNL Marketo Measure] objeto en Salesforce que puede resultar muy útil al crear informes de métricas relacionadas con personas: **el [!DNL Marketo Measure] Persona (BP)**. La BP resuelve el antiguo problema de cómo representar la información de posibles clientes y contactos en el mismo informe. Une todos los BT relacionados con una &quot;persona&quot; (a [!DNL Marketo Measure] El ID de la persona es su dirección de correo electrónico). Ya sea que existan como posible cliente o contacto, la BP actúa como un objeto de puente, para ayudar a que los informes abarquen todo el posible cliente y contacto, y es muy útil para producir informes más sofisticados sobre las personas.

La variable [!DNL Marketo Measure] Persona se refiere únicamente a uno de los objetos de punto de contacto, el punto de contacto del comprador (BT). Esto significa que no se puede aprovechar para métricas relacionadas con oportunidades o ingresos. Un[!DNL Marketo Measure] El tipo de informe de puntos de contacto de persona y comprador es bueno para comprender _participación total_ ya que aparece todos los BTs si el BT se relaciona con un posible cliente o contacto más específicamente. Por ejemplo: si tiene una campaña de Salesforce utilizada para rastrear un evento, puede tener miembros de campaña dentro de la campaña de CRM que existan como posibles clientes o contactos. [!DNL Marketo Measure] creará puntos de contacto para los miembros de la campaña de todas formas, pero sin la variable [!DNL Marketo Measure] Persona, los informes estándar de Salesforce requerirían dos informes separados para comprender cuántos _total_ puntos de contacto que tiene desde el evento: uno que es &quot;Leads with Buyer Touchpoints&quot; y otro que es &quot;Contacts with Buyer Touchpoints&quot;. Otros [!DNL Marketo Measure] A continuación se enumeran los casos de uso de informes basados en personas:

**3.1 [!DNL Marketo Measure] Personas que tienen &quot;libros electrónicos&quot; o &quot;documentos técnicos&quot; descargados (descargas totales)**

Este informe sería el mismo que un informe basado en &quot;Contenido&quot; en el nivel de posible cliente. Sin embargo, en lugar de buscar medir el número de posibles clientes atribuibles a cada parte de contenido, utilizando un [!DNL Marketo Measure] El informe Personas será útil para comprender el total _número de descargas_ si se cierra el recurso (el número total de puntos de contacto representaría el número total de descargas/envíos de formularios).

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>¿Cuántas personas han descargado un recurso concreto?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>[!DNL Marketo Measure] Personas y puntos de contacto del comprador (CRM)</td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td>"URL del formulario" CONTIENE (por ejemplo)<br>
   <li>/ebook</li>
   <li>/whitepaper</li>
   <i>Los valores de filtro anteriores son solo ejemplos. El valor real se basará en la estructura de URL de cada organización.</i></td> 
  </tr>
  <tr>
   <td>Campo de fecha/Tipo de fecha</td> 
   <td>Fecha de Touchpoint <i>(cuándo se descargó el recurso)</i></td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccionar el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Formulario/URL</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Este informe trata menos de medir de dónde provienen los posibles clientes o los contactos con un modelo de atribución, pero más acerca del <i>número total de puntos de contacto (cantidad de participación)</i>, incluidas las que siguen al contacto de creación de posibles clientes. Con este informe estamos buscando comprender el <i>cantidad de participación total</i>. El recuento total de registros de puntos de contacto reflejaría qué recursos se han descargado más.</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Para cualquier &quot;Posibles clientes&quot; con [!DNL Marketo Measure] Tipo de informe de personas, comience personalizando el informe creado previamente titulado &quot;**[!DNL Marketo Measure]101 | Posibles clientes/contactos por canal**&#39;. Este informe está disponible de forma predeterminada y es un bueno [!DNL Marketo Measure] Sandbox basado en personas. Está prediseñada y se puede personalizar rápidamente para satisfacer necesidades de informes más específicas.

>[!TIP]
>
>Puede utilizar este informe para obtener información sobre la participación total de cualquier dimensión de marketing desde el objeto Punto de contacto del comprador, no solo las descargas de contenido como se muestra en el ejemplo. El informe se podría agrupar o filtrar en dimensiones como &quot;Canal de marketing&quot; o &quot;Nombre de campaña de publicidad&quot; para comprender mejor la participación total de posibles clientes y contactos en la base de datos. Simplemente cambie los filtros o agrupaciones dentro del informe a cero en otras dimensiones representadas por otros campos desde el objeto touchpoint.

**3,2 [!DNL Marketo Measure] Personas que se han registrado para un evento (solo CRM)**

_Este informe solo es aplicable si los formularios de registro están alojados en su sitio web que [!DNL Marketo Measure] puede rastrearse digitalmente._

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>¿Qué canales de marketing están impulsando mis registros de eventos?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>[!DNL Marketo Measure] Personas y puntos de contacto del comprador (CRM)</td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td>"URL del formulario" CONTIENE (por ejemplo)<br>
   <li>/evento</li>
   <i>El valor de filtro anterior son solo ejemplos. El valor real se basará en la estructura de URL de cada organización.</i></td> 
  </tr>
  <tr>
   <td>Campo de fecha/Tipo de fecha</td> 
   <td>Fecha de Touchpoint <i>(cuando se presentó el formulario de registro)</i></td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccionar el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>URL del formulario<br>
   Canal de marketing</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Este informe trata menos de medir de dónde provienen los posibles clientes o los contactos con un modelo de atribución, pero más acerca del <i>número total de puntos de contacto (número de registros)</i>, incluidas las que siguen al contacto de creación de posibles clientes. Con este informe buscamos obtener información sobre lo que está impulsando los registros de eventos. El recuento total de registros de puntos de contacto por "Canal de marketing" reflejaría qué canales condujeron la mayoría de los registros.</td> 
  </tr>
 </tbody>
</table>

La clave de este informe es que los datos de punto de contacto del comprador también proporcionarán datos del canal de marketing. Aunque es posible que ya tenga información sobre la cantidad de personas que se han registrado en sus eventos, este informe también proporciona información sobre los canales de marketing digital, las fuentes y/o las campañas que atraen a las personas a su sitio web para que luego se registren en el evento.

>[!TIP]
>
>Este mismo método se puede seguir cuando se desea obtener información sobre los registros de seminarios web o quizá descargas de seminarios web a petición (si se trata de un recurso cerrado). La única diferencia sería el valor de filtro en la &quot;URL del formulario&quot; si esos formularios están alojados en páginas únicas del sitio web. Sin embargo, el objetivo es el mismo. Responde a las preguntas: &quot;cuál de mis canales de marketing está generando la mayor cantidad de registros/descargas de seminarios web bajo demanda.

**3,3 [!DNL Marketo Measure] Personas con puntos de contacto de comprador (validación de punto de contacto)**

Si se considera la variable [!DNL Marketo Measure] Persona nos permite informar sobre todos los puntos de contacto en un solo informe; es el tipo de informe ideal para usar al buscar validar sus datos. Queremos asegurarnos de que no se pasa por alto ningún punto de contacto que pueda revelar dónde, por ejemplo, hay un problema en la configuración de sus canales de marketing (consulte los artículos de soporte vinculados a continuación para obtener más información sobre la configuración de sus canales de marketing).

* [Configuración de canal personalizado en línea](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
* [Configuración de canal personalizado sin conexión](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)

Esencialmente, los datos de puntos de contacto reflejarán el seguimiento realizado por [!DNL Marketo Measure] y se pueden auditar para garantizar que la configuración coincida con las entradas en función de cosas como: Valores de parámetro UTM, Páginas de referencia o Tipos de campaña. Si los datos de punto de contacto no coinciden con su configuración, es muy probable que haya que ajustar algo. Más allá de la configuración &quot;Canal de marketing&quot;, puede consultar los datos de puntos de contacto para determinar qué puntos de contacto pueden necesitar [suprimido](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md) o [segmentado](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md). Se recomienda auditar los datos de puntos de contacto en un[!DNL Marketo Measure] Informe de personas y puntos de contacto del comprador al final de cada mes o trimestre, si es posible. Esto garantizará que la atribución sea lo más precisa posible. El[!DNL Marketo Measure] 101 | El informe de posibles clientes/contactos por canal disponible de forma predeterminada es un bueno lugar para empezar. Incluya los siguientes campos si no están incluidos para revisar algunos de los elementos de configuración más importantes:

* **Canal de marketing** - Ruta = Canal de marketing.Subcanal (valores configurados en [!DNL Marketo Measure])
* **Origen de touchpoint** = utm_source
* **Medio** = utm_medium (puntos de contacto en línea) O tipo de campaña de CRM (puntos de contacto sin conexión)
* **Página Referente** (se ha utilizado la configuración &quot;Canales en línea&quot;)
* **Página de aterrizaje: sin procesar** (se usa la configuración &quot;Canales en línea&quot;) también es una entrada común para la supresión de puntos de contacto en la pestaña &quot;Configuración de puntos de contacto&quot; de su Configuración)
* **URL del formulario** (una entrada común para la supresión de puntos de contacto en la pestaña &quot;Configuración de puntos de contacto&quot; de la Configuración)

**PUNTO DE CONTACTO DE ATRIBUCIÓN DEL COMPRADOR (MTD)**

Los puntos de contacto de atribución de comprador (BAT) representan los puntos de contacto relevantes de todos los contactos conectados a la oportunidad (ya sea a través de las funciones de contacto de oportunidad o a través de un ID de cuenta compartido, según su configuración). A diferencia de los BT (que están principalmente conectados a las personas), las MTD pueden estar asociadas con los ingresos. Como tal, utilizará las MTD para responder preguntas relacionadas con las oportunidades, principalmente abiertas _Oportunidades/Ingresos de canalización_ y cerrada _Oportunidades/Ofertas/Ingresos_. Una MTD se crea a través de los registros BT de un Contacto tan pronto como se crea una Oportunidad bajo la misma Cuenta que el Contacto (el BT no se convierte en una MTD. Simplemente se hace referencia a los datos BT para crear un registro adicional (el MTD que luego se relaciona con la Oportunidad).

El punto de contacto de atribución de comprador nos permite medir el impacto de marketing más profundamente en el canal. _La profundidad del canal en el que desea medir puede representarse por los distintos modelos de atribución de varios contactos_.

Teniendo en cuenta que la relación principal de las MTD es con la Oportunidad, se utilizan para responder preguntas como:

* ¿Cuál de mis esfuerzos de marketing ha influido más en las oportunidades?
* ¿Cuántos ingresos de canalización nuevos puedo atribuir a cada uno de mis canales de marketing?
* ¿Cuál de mis campañas vio el retorno de la inversión bueno del último trimestre?

La variable [modelos de atribución](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md) para obtener información más detallada sobre las métricas basadas en oportunidades, consulte:

**Forma de W** - El _Modelo de canalización_&#39;. En el modelo con forma de W se incluyen tres puntos de contacto de hito. En este modelo, los puntos de contacto FT, LC y OC se atribuyen cada uno al 30% del crédito de atribución. El 10 % restante se atribuye de forma equitativa a cualquier punto de contacto intermedio que se produzca entre los tres puntos de contacto de hitos.

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-2.png"></td> 
   <td>Este modelo resume esencialmente el recorrido de una nueva oportunidad que es generalmente sinónimo de la generación de nuevos ingresos de canalización.<p>
   <p>
   Al buscar medir el impacto del marketing en las nuevas oportunidades o en la nueva canalización generada, se recomienda el modelo con forma de W.</td> 
  </tr>
 </tbody>
</table>

**Ruta completa** - El _Modelo Won cerrado_&#39;. Este modelo incluye los cuatro puntos de contacto de hito: FT, LC, OC y Cerrado. Cada uno recibe el 22,5% del crédito de oportunidad y el 10% restante se distribuye equitativamente entre los toques intermedios.

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-3.png"></td> 
   <td>Este modelo resume esencialmente el recorrido de un acuerdo cerrado ganado que es típicamente sinónimo de ingresos/reservas ganados cerrados.<p>
   <p>
   Cuando se busca medir el impacto del marketing en los acuerdos ganados cerrados o en los ingresos ganados cerrados, se recomienda el modelo de ruta completa.</td> 
  </tr>
 </tbody>
</table>

Este modelo resume esencialmente el recorrido de un acuerdo cerrado ganado que es típicamente sinónimo de ingresos/reservas ganados cerrados.

Cuando se busca medir el impacto del marketing en los acuerdos ganados cerrados o en los ingresos ganados cerrados, se recomienda el modelo de ruta completa.

**Personalizado** - [!DNL Marketo Measure] también ofrece un modelo de atribución personalizada que permite a los usuarios elegir qué puntos de contacto o etapas personalizadas incluir en su modelo. Además, los usuarios pueden controlar el porcentaje de crédito de atribución atribuido a estos puntos de contacto y etapas. Dependiendo de la configuración de su modelo personalizado, se puede utilizar más apropiadamente para medir Oportunidades y Canalización O, Ofertas e Ingresos Cerrados Ganados. Tenga esto en cuenta cuando lo use en sus informes.

>[!NOTE]
>
>El Modelo de atribución personalizado es una característica adicional que no está disponible para todos los clientes. Póngase en contacto con el gestor de éxito del cliente para obtener más información sobre cómo añadir esta función a su cuenta.

Normalmente, los especialistas en marketing necesitan saber, &quot;¿de dónde vienen mis oportunidades?&quot;. De forma similar a los informes de nivel de posible cliente, esta pregunta se ha respondido históricamente con un solo valor unidimensional (por ejemplo, la fuente de campaña principal). Sin embargo, sabemos que mucho más se destina al desarrollo de una oportunidad que un solo punto de contacto de un solo contacto. Normalmente, existen varios puntos de contacto de varios canales y de múltiples partes interesadas que influyen en una oportunidad en la creación. con [!DNL Marketo Measure], podemos mostrar todos los puntos de contacto de una cuenta para comprender mejor de dónde proviene una oportunidad. Sin embargo, más allá de eso, podemos seguir mostrando cualquier punto de contacto que haya ocurrido después de la creación de la oportunidad y hasta el momento la oportunidad está cerrada. Esto nos permite no solo tomar un enfoque de múltiples contactos para comprender de dónde vino una oportunidad, sino también qué lo influyó para cerrarla y, en última instancia, para representar ingresos ganados cerrados. Esto proporciona una perspectiva de diferentes preguntas, como &quot;¿cuál es el impacto del marketing en la influencia que influye en el cierre de las ofertas?&quot;, &quot;¿qué marketing está impulsando el cierre de los ingresos ganados?&quot; y finalmente, &quot;¿cuáles son mis esfuerzos de marketing que están viendo el retorno de la inversión bueno?&quot;

## INFORMES RECOMENDADOS CON EL PUNTO DE CONTACTO DE ATRIBUCIÓN DEL COMPRADOR (BAT) {#recommended-reports-using-the-buyer-attribution-touchpoint}

**4,1 | Nuevas oportunidades por canal de marketing**

Resumiendo los datos de Touchpoint de atribución de Comprador de Oportunidades por el campo &quot;Canal de Marketing&quot; es la vista de más alto nivel que representa qué canales/tácticas están influyendo en las nuevas Oportunidades en la creación. Estructurar este informe en torno a un &quot;Tipo de fecha&quot; = &quot;Fecha de creación de oportunidad&quot; garantiza que también se resuma el informe en función del momento en que la oportunidad se creó realmente en su CRM. Los puntos de contacto pueden haber sido de un tiempo anterior, pero siguen estando relacionados con las oportunidades que se han creado dentro del intervalo de fechas definido y, por lo tanto, reciben crédito de atribución, ya que se reconoce que influyen en la oportunidad.

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué <i>canales de marketing</i> ¿están influyendo las oportunidades en la creación?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Puntos de contacto de atribución de comprador con oportunidades (CRM)<br> 
   Métrica: Oportunidades ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td>
   <li>Etapa de oportunidad* <i>(opcional en función de las oportunidades específicas que desee limitar al informe. Solo es posible que desee informar sobre las MTD que siguen asociadas únicamente a las oportunidades "abiertas" (por ejemplo)</i></li>
   <li>Tipo de oportunidad (es común filtrar en determinadas oportunidades, por ejemplo 'New Business' en oposición a <i>all</i> Oportunidades)</li><br>
   *Se debe aprovechar un filtro de segmento para "Tipo de oportunidad" en [!DNL Marketo Measure] Discover</td> 
  </tr>
  <tr>
   <td>Campo de fecha/Tipo de fecha</td> 
   <td>Fecha de creación de oportunidad (CRM)/Fecha de creación (Discover)</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccionar el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Canal de marketing</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td><strong>Forma de W</strong><br>
   SUME los campos "Forma de W" en los informes CRM (Recuento: Forma de W, Ingresos: Forma de W)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Para cualquier tipo de informe &quot;Puntos de contacto de atribución de Comprador con Oportunidades&quot;, comience personalizando el informe creado previamente titulado &quot;[!DNL Marketo Measure] 101 | Oportunidades por Canal&quot;. Este informe está disponible de forma predeterminada y es un bueno simulador de pruebas creado previamente como se describe en la tabla anterior y se puede personalizar rápidamente para necesidades de informes más específicas (el informe utiliza un modelo de Ruta completa listo para usar, por lo que asegúrese de personalizar el informe para incluir cualquier otro modelo de atribución, en este caso, el modelo Forma de W).

>[!TIP]
>
>El informe descrito anteriormente también se utilizaría para comprender cuánto dinero se debe atribuir. Cuando se generan informes a nivel de oportunidad mediante MTD, hay dos métricas clave que se pueden resumir: moneda (la cantidad de la Oportunidad) y el propio registro de la Oportunidad. En el ejemplo anterior, estamos midiendo de forma más específica las oportunidades de apertura y los nuevos ingresos por oleoductos.

>[!TIP]
>
>Obtenga una perspectiva aún más granular al resumir el informe con otros campos disponibles del objeto Touchpoint de Atribución del comprador. Esto se hace de la misma manera que lo hacía a nivel de posible cliente con puntos de contacto del comprador (1.2). Para ello, agregue agrupaciones (CRM) o dimensiones adicionales (Discover). Según el canal (que puede ser representativo de su función), puede haber detalles adicionales más allá del nivel de campaña en el que busca obtener más información. Vamos a profundizar en la búsqueda de pago a continuación:

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué <i>keywords</i> desde mis anuncios de búsqueda pagada están generando la mayor cantidad de ingresos de canalización?
</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Puntos de contacto de atribución de comprador con oportunidades (CRM)<br> 
   Métrica: Oportunidades ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td>
   <li>Canal de marketing = Búsqueda paga</li>
   <li>Etapa de oportunidad* <i>(opcional en función de las oportunidades específicas que desee limitar al informe. Este ejemplo se basa en los ingresos de canalización definidos en [!DNL Marketo Measure] por "Abrir" Oportunidades que representan posibles ingresos/abrir canalización)</i></li>
   <li>Tipo de oportunidad (es común filtrar en determinadas oportunidades, por ejemplo 'New Business' en oposición a <i>all</i> Oportunidades)</li><br>
   *Se debe aprovechar un filtro de segmento para "Tipo de oportunidad" en [!DNL Marketo Measure] Discover</td> 
  </tr>
  <tr>
   <td>Campo de fecha/Tipo de fecha</td> 
   <td>Fecha de creación de la oportunidad</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccionar el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Texto de palabra clave (CRM)<br> 
   Palabra clave (Discover)</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td><strong>Forma de W</strong><br>
   SUME los campos "Forma de W" en los informes CRM (Recuento: Forma de W, Ingresos: Forma de W)</td> 
  </tr>
 </tbody>
</table>

**4,2 | Ofertas por canal de mercadotecnia**

Este informe sería esencialmente el mismo que el primer ejemplo de punto de contacto de atribución de comprador (4.1), excepto que la métrica ahora ha cambiado de Oportunidades abiertas a Ofertas ganadas cerradas. La métrica siempre debe ser la que informe qué modelo de atribución utilizar. Teniendo en cuenta que ahora estamos viendo acuerdos cerrados ganados y sus MTD relacionados, deberíamos usar un modelo que represente todo el recorrido del comprador (acuerdo). Esto garantiza que cualquier rastreo táctil de marketing durante el recorrido del comprador reciba crédito de atribución:

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué <i>canales de marketing</i> ¿está influyendo en el cierre de los acuerdos?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Puntos de contacto de atribución de comprador con oportunidades (CRM)<br> 
   Métrica: Ofertas ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td>
   <li>Fase de oportunidad (<i>Sólo Closed Won Oportunidades debe estar en el informe</i>) O</li>
   <li>Ganancia de oportunidad = Verdadero</li>
   <li>Tipo de oportunidad (es común filtrar en determinadas oportunidades, por ejemplo 'New Business' en oposición a todas las oportunidades)<br>
   </td> 
  </tr>
  <tr>
   <td>Campo de fecha/Tipo de fecha</td> 
   <td>Fecha de cierre de oportunidad</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccionar el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Canal de marketing</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td><strong>Ruta completa</strong><br>
   SUME los campos "Ruta completa" en los informes CRM (Recuento: Ruta completa, Ingresos: Ruta completa)</td> 
  </tr>
 </tbody>
</table>

**RECORDATORIO**: Es crucial recordar filtrar por las oportunidades específicas que desea incluir en los informes basados en BAT, especialmente cuando se trata de &quot;Oportunidades abiertas e ingresos de canalización&quot; vs. &#39;Ofertas e ingresos ganados cerrados&#39;. Esto se realiza generalmente mediante un filtro de &quot;Etapa de oportunidad&quot; (el filtro &quot;Oportunidad ganada&quot; = true/false&quot; también puede ser muy útil aquí).

**5. ROI ([!DNL Marketo Measure] Solo Discover)**

La variable [!DNL Marketo Measure] Los tableros de Discover ofrecen una vista de alto nivel del rendimiento de marketing mediante [!DNL Marketo Measure] datos de atribución. Estos tableros agregados proporcionan datos clave sobre gastos de marketing y ROI que no están disponibles en los informes de CRM. Este entorno pregenerado le permite ver su rendimiento de marketing en armonía con sus datos de ROI, lo que le permite tomar decisiones útiles con respecto a su marketing.

>[!TIP]
>
>Siempre que tenga alguna pregunta relacionada con el ROI, los gastos o los costes, [!DNL Marketo Measure] ¡Discover será el mejor lugar para realizar informes!

La variable [!DNL Marketo Measure] Los paneles de Discover están formados por datos de puntos de contacto de atribución de comprador y punto de contacto de comprador, así como por datos CRM clave. La diferencia principal entre los informes de CRM y los informes en [!DNL Marketo Measure] Discover es el hecho de que los datos de puntos de contacto en Discover se presentan de manera más &quot;agregada&quot; y se resumen por dimensión (Canal de marketing, Campaña, etc.) a diferencia de los registros de puntos de contacto individuales que se pueden resumir. [!DNL Marketo Measure] Discover se utiliza para comprender a un alto nivel qué esfuerzos están teniendo el impacto bueno sobre posibles clientes, ofertas y cuánto ingreso se les debe atribuir. Una vez calculados los ingresos atribuidos mediante los distintos modelos de atribución (se recomienda Ruta completa para atribuir ingresos/reservas ganados cerrados), podemos medirlos en relación con la cantidad gastada en la misma dimensión (Canal de marketing, Subcanal o Campaña). Esto nos da el **ROI**.

>[!TIP]
>
>Una de las cosas más importantes que hay que recordar al realizar informes en Discover es el tipo de datos que se usa para filtrar. Tipo de fecha dictará qué conjunto de datos [!DNL Marketo Measure] se utiliza en los distintos mosaicos.

* **Fecha de Touchpoint**: Muestra los datos relacionados que tenían una &quot;Fecha de punto de contacto&quot; en el periodo especificado
* **Fecha de creación**: Muestra los datos relacionados que tenían una &quot;Fecha de creación&quot; en el intervalo de tiempo especificado
* **Fecha de cierre**: Muestra los datos relacionados que tenían una &quot;Fecha de cierre&quot; en el intervalo de tiempo especificado

Al informar sobre el ROI en [!DNL Marketo Measure] Discover, se recomienda utilizar un &quot;Tipo de fecha&quot; = &quot;Fecha de punto de contacto&quot;. Para determinar el rendimiento de cada dólar invertido, debemos asegurarnos de que los ingresos se atribuyan a la fecha en que se realizó la inversión. &#39;Tipo de fecha&#39; = &quot;Fecha de punto de contacto&quot; garantiza que los informes se estructuren de esta manera en lugar de cuando se creó la oportunidad (Crear fecha) o se cerró (Fecha de cierre). Echemos un vistazo más de cerca:

Los filtros resaltados a continuación son cruciales para un informe centrado en el retorno de la inversión en [!DNL Marketo Measure] (lo más probable es que esté configurando estos filtros en las placas &quot;Información general&quot;, &quot;CMO&quot; o &quot;ROI&quot;):

**5.1 | ROI en la placa &quot;Información general&quot;**

![](assets/bizible-reporting-guide-4.png)

El intervalo &quot;Fecha&quot; no solo establece la cohorte de puntos de contacto (por fecha de punto de contacto) que reciben la atribución, sino que también define el rango que representan el mosaico o las columnas &quot;Gasto&quot;.
[!DNL Marketo Measure] simplemente observe el intervalo &quot;Fecha&quot; para determinar cuánto se gastó, ya sea en total o en los niveles Canal de marketing, Subcanal o Campaña Consulte a continuación:

![](assets/bizible-reporting-guide-5.png)

La captura de pantalla de arriba muestra los datos del gasto en marketing durante los últimos 3 meses completos. En este ejemplo, se gastaron 12.970 dólares en todos los canales. Este número se compone de los datos de gasto de marketing [!DNL Marketo Measure] desde integraciones con cualquiera de sus cuentas de anuncios conectados (Google AdWords, Bing Ads, Facebook Ads, LinkedIn, DoubleClick) y cualquier gasto de marketing adicional que se haya cargado en su cuenta, o que se haya extraído automáticamente de un registro de campaña en su CRM. El ejemplo también muestra cuánto se pueden atribuir los &quot;Ingresos&quot; cerrados a puntos de contacto que se produjeron durante el mismo intervalo de fechas (cuadros verdes). Así es como se calcula el ROI: ingresos atribuidos a puntos de contacto procedentes de inversiones en el mismo intervalo de fechas:

![](assets/bizible-reporting-guide-6.png)

**RECORDATORIO**: [!DNL Marketo Measure] define &quot;Ingresos&quot; como ingresos ganados cerrados o reservas y define &quot;Ingresos de canalización&quot; como _abrir/obtener posibles ingresos de las oportunidades abiertas_.

Otro aspecto importante del informe de ROI anterior es la representación de &quot;Ingresos de canalización&quot; dentro del cuadro rojo. Esto significa que de los $12,970 dólares invertidos en los últimos 3 meses completos, actualmente estamos atribuyendo $705,199 de &#39;Ingresos&#39; cerrados, pero también estamos atribuyendo $6,905,532 de ingresos abiertos, potenciales (&#39;Ingresos de canalización) a puntos de contacto creados a partir de la misma inversión! Lo que esperaríamos ver es una parte de los &quot;Ingresos de la canalización&quot; que se cierran con el tiempo, lo que alimenta el número de &quot;Ingresos&quot; y, por lo tanto, el número de ROI aumentaría con el tiempo. El número &quot;Gasto&quot; es fijo porque no podemos volver a pasar más tiempo en los últimos 3 meses completos. Esta es la importancia de usar un &quot;Tipo de fecha&quot; de &quot;Fecha de punto de contacto&quot; en cualquier informe de ROI: Define la cantidad (**I**)anidada y garantiza la cantidad de (**R**)Los ingresos atribuidos se atribuyen a los mismos puntos de contacto que se obtuvieron de la inversión (por cada dólar gastado, ¿cuánto se hizo?).

>[!TIP]
>
>Filtre en Canales de marketing, Subcanales o Campañas en las que sepa que los datos de gasto de marketing son completos y precisos. El ejemplo anterior es para todos los canales de marketing, pero si algunos canales no tienen cargados los datos relacionados con el gasto de marketing, el informe de ROI podría ser inexacto. Consulte el ejemplo siguiente, esta vez en el panel &quot;ROI&quot; que se centra en las campañas dentro del canal de marketing de &quot;Búsqueda paga&quot;, un canal con datos muy granulares del gasto de marketing a través de las integraciones.

![](assets/bizible-reporting-guide-7.png)
