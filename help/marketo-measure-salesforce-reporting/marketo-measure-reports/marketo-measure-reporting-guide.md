---
description: "[!DNL Marketo Measure] Guía de informes - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Guía de informes"
exl-id: 9b991f9e-c187-4b43-b0a8-8ed3e9a6056b
feature: Reporting
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '6437'
ht-degree: 1%

---

# Guía de informes de [!DNL Marketo Measure] {#marketo-measure-reporting-guide}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en la documentación, pero sigue viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

Antes de crear un [!DNL Marketo Measure] informe, es fundamental que confirme su [!DNL Marketo Measure] Se ha revisado y configurado la configuración de la cuenta para garantizar que los datos de los informes sean precisos y reflejen las características específicas de su empresa. Además, los proyectos de creación de informes funcionan mejor cuando siguen un proceso estructurado. Justin Norris, un [!DNL Marketo Measure] usuario avanzado, defensor y socio de [Perkuto](https://perkuto.com/) resumido por expertos [cómo abordar la creación de informes en [!DNL Marketo Measure]](https://perkuto.com/blog/turning-attribution-data-into-actionable-insights/):

**Establecer metas**: &quot;La primera pregunta es &#39;¿por qué medimos?&#39; Lori Wizdo de [Forrester Research](https://go.forrester.com/) lo resumió muy bien en un [Seminario web de Marketo](https://www.marketo.com/webinars/beyond-revenue-performance-real-kpis-of-b2b-marketing/). Según ella, &quot;medimos para probar o validar una decisión o el valor del marketing o para mejorar (mejora de procesos)&quot;. Añadimos que las perspectivas de una buena medición también proporcionan insumos y orientación para el proceso de planificación de marketing.

Así que antes de empezar, es esencial ser muy claro en sus objetivos, las preguntas que está tratando de responder, o los problemas que está tratando de resolver. ¿Qué historia quieres contar? ¿Qué decisiones se tomarán como resultado? Con demasiada frecuencia estos fundamentos no están bien pensados, lo que lleva a la frustración de todos los involucrados&quot;.

**Diseño del informe**: &quot;A continuación, debe diseñar el informe y determinar las dimensiones, métricas y conjuntos de datos específicos que contendrá. Una experiencia común es proporcionar a un usuario empresarial exactamente lo que solicita, solo para que siga sintiendo que sus necesidades no se satisfacen. Esto se debe a que la perspectiva que un usuario empresarial está buscando no siempre aparece en el informe que solicita. Un buen analista (o una persona de MOPS con un sombrero de analista) hará preguntas aclaratorias, establecerá definiciones comunes (&quot;¿qué quieres decir con plomo?&quot;), e incluso esbozará una imagen visual del informe final para asegurarse de que haya alineación. Solo entonces genera el informe sabiendo que tiene un conjunto sólido de requisitos&quot;.

**Report Build**: &quot;Una vez que vas a construir, no es raro encontrar obstáculos o callejones sin salida. Por ejemplo, es posible que descubra que le falta un punto de datos esencial o que los objetos no se vinculan de la manera que necesita. Para resolver estos problemas, también creo que es fundamental entender lo que está pasando &quot;bajo el capó&quot; en su &quot;máquina&quot; de creación de informes. Esta fluidez le permitirá dimensionar rápidamente una solicitud de creación de informes y evaluar si es alcanzable (y diseñar soluciones creativas más fácilmente cuando no lo es)&quot;.

Echemos un vistazo &quot;bajo el capó&quot; para entender mejor qué hace que la [!DNL Marketo Measure] ejecución del equipo de informes de atribución.

## Objetos Touchpoint del comprador (CRM) {#buyer-touchpoint-objects-crm}

En el nivel más alto existen dos categorías de informes basadas en los dos objetos de punto de contacto del comprador diferentes: estas categorías determinan qué tipo de [!DNL Marketo Measure] datos sobre los que desea informar: datos relacionados con un _particular_ o datos relacionados con un _oportunidad_.

1. **Puntos de contacto del comprador** (BT) / Particulares / Participación total

   * Se utiliza comúnmente para métricas de &quot;parte superior del canal&quot; (TOFU) e informes relacionados con _personas_ (Posibles clientes, contactos, [!DNL Marketo Measure] Personas)
   * Los BT se utilizan para comprender todas las interacciones de marketing relacionadas con **personas**, ya que contienen el historial completo de puntos de contacto de cada persona. Como recordatorio, estos puntos de contacto se crean en CRM para el primer contacto anónimo, el contacto de creación de posibles clientes y cualquier envío de formulario o punto de contacto posterior que elija sincronizar desde una campaña o actividad sin conexión.

1. **Puntos de contacto de atribución del comprador** (MTD) / Oportunidad / Nivel de cuenta / Ingresos

   * Se utiliza comúnmente para las métricas &quot;centro y/o final del canal&quot; (MOFU y BOFU) y los informes relacionados con _Oportunidades_.
   * Las MTD representan los puntos de contacto relevantes de todas las personas conectadas a la **oportunidad** (a través de las funciones de contacto de oportunidad o a través de un ID de cuenta compartida, según la configuración). A diferencia de las MTD que solo se refieren a personas, las MTD también pueden asociarse con **ingresos**. Como tal, utilizará las MTD para responder a preguntas relacionadas con las oportunidades, incluidas cuántas oportunidades se abrieron o cerraron, o el valor de la canalización y los ingresos obtenidos.

>[!NOTE]
>
>Las MTD se crean a partir de MTD. Básicamente, el seguimiento comienza a nivel individual a través de los BT. Una vez que se crea una oportunidad en una cuenta, se hace referencia a todos los BT de contactos de la misma cuenta y son aptos para crear MTD relacionados con la oportunidad, por lo que querrá utilizar una o la otra según las preguntas que esté intentando responder: preguntas relacionadas con las métricas de Personas (informes MTD) o preguntas relacionadas con las métricas de Oportunidad (informes MTD)

Artículo de soporte: [Diferencia entre los puntos de contacto del comprador y los de atribución del comprador](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md#configuration-and-setup)

## Punto de contacto de comprador (BT) {#buyer-touchpoint-bt}

El punto de contacto del comprador (BT) es el objeto utilizado para rastrear cada interacción de marketing que alguien tiene con sus materiales de marketing. De cada individuo (cliente potencial/contacto/[!DNL Marketo Measure] Persona) El recorrido estaría representado por sus BT relacionados. Entrada [!DNL Marketo Measure], el recorrido de un individuo consiste en:

1. ¿Cómo interactuó esta persona por primera vez con nuestra marca? (Primer contacto o _FT_)
1. ¿Cómo esta persona se convirtió / se hizo conocida / se convirtió en un posible cliente? (Creación de posibles clientes o _LC_)
1. ¿De qué otra manera ha interactuado esta persona con nuestra marca y materiales de marketing desde que se convirtió en líder? (_PostLC_)

Los puntos de contacto del comprador se utilizan para responder a preguntas relacionadas con _personas_ (&quot;personas&quot; están representadas por posibles clientes o contactos dentro de un CRM), como las métricas de generación de posibles clientes/contactos o de adquisición, en lugar de las métricas relacionadas con oportunidades. Por ejemplo:

* ¿Qué canales ofrecen la mayor cantidad de posibles clientes?
* ¿Qué canales son más o menos costosos para crear un nuevo posible cliente?
* ¿Con qué contenido están interactuando mis posibles clientes/contactos?
* ¿Cuál es la historia de marketing de títulos, roles y personalidades particulares?
* ¿Qué canales generan MQL u otros estados de cliente potencial/contacto?

Principalmente, las empresas deben saber: &quot;¿de dónde provienen mis posibles clientes o contactos?&quot;. Históricamente, se respondió con un solo valor unidimensional (por ejemplo, el origen del posible cliente). Sin embargo, como se describe en #1 y #2 anteriores, sabemos que los posibles clientes pueden tener varios puntos de contacto durante su recorrido de convertirse en posibles clientes. El punto de contacto del comprador nos permite obtener información sobre las dos interacciones más cruciales que representan cómo se generó un posible cliente: su primer contacto y su contacto de creación de posibles clientes. Los puntos de contacto del comprador también son _multidimensional_ Esto significa que transportan muchos datos de marketing, principalmente de dónde proviene la persona (canal de marketing) y con qué se involucra la persona (contenido).

El [modelos de atribución](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md) para obtener la mejor perspectiva de las métricas basadas en personas, consulte:

* **Primer contacto** - 100% de crédito de atribución al primer contacto del posible cliente (FT)
* **Creación de posibles clientes** - 100% de crédito de atribución al Lead Creation Touch (LC)
* **Forma de U** - enfoque multitáctil, con un 40% de crédito a la FT, un 40% de crédito a la LC

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-1.png"></td> 
   <td>El modelo en forma de U está diseñado para dar crédito a cualquier punto de contacto del comprador que resuma cómo un posible cliente se convirtió en un posible cliente. Aunque también se puede informar de que los puntos de contacto subsiguientes de estos posibles clientes entienden la participación adicional (posterior a la LC), no forman parte de la <strong>Recorrido de creación de posibles clientes</strong> por lo que no obtienen ningún crédito de atribución en los modelos FT, LC o en forma de U.<p>

&#42;Normalmente, la atribución en forma de U refleja una división incluso 50/50 entre FT y LC. Si el posible cliente se convierte en la misma sesión que el primer contacto, un solo punto de contacto representaría las posiciones de punto de contacto FT y LC. Por lo tanto, el 100 % de la atribución se daría a un solo punto de contacto.</td>
</tr>
 </tbody>
</table>

Estos modelos hacen mucho hincapié en las interacciones en las primeras etapas y en la parte superior de la participación del canal. La atribución de Forma de U es el modelo recomendado, ya que influye en los puntos de contacto de FT y LC y garantiza que se dé crédito a cualquier contacto que haya influido en la creación del posible cliente. Sin embargo, se puede obtener una perspectiva adicional de los modelos de primer contacto y contacto de creación de clientes potenciales si desea comprender esas partes específicas del recorrido de clientes potenciales con más detalle.

## Informes recomendados que utilizan el punto de contacto del comprador (BT) {#recommended-reports-using-the-buyer-touchpoint-bt}

1. **POSIBLES CLIENTES con PUNTOS DE CONTACTO DEL COMPRADOR**

**1,1 | Nuevos posibles clientes por canal de marketing**

Resumiendo los datos del punto de contacto del comprador del posible cliente por el campo &quot;Canal de marketing&quot;, se encuentra la vista de nivel superior que representa qué canales/tácticas influyen en la creación de nuevos posibles clientes. Estructurar este informe en torno a un &quot;Tipo de fecha&quot; = &quot;Fecha de creación&quot; garantiza que se establezca en el informe una cohorte de &quot;nuevos posibles clientes netos&quot; (cuando el posible cliente se creó en su CRM).

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>¿Qué canales de marketing influyen en la creación de posibles clientes?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Puntos de contacto de clientes potenciales y compradores (CRM)<br>
   Métrica: posibles clientes ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Campo de fecha/tipo de fecha</td> 
   <td>Fecha de creación del posible cliente (CRM) / Fecha de creación (Discover)</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccione el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Canal de marketing</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Primer contacto, creación de posibles clientes, <strong>Forma de U</strong><br>
   *SUMA de los campos "Recuento" en los informes de CRM (Recuento - Primer toque, Recuento - Creación de posibles clientes, Recuento - Forma de U)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Para cualquier tipo de informe &quot;Posibles clientes con puntos de contacto del comprador&quot;, comience personalizando el informe creado previamente llamado &quot;[!DNL Marketo Measure] 101 | Posibles clientes por canal&quot;. Este informe está disponible de forma predeterminada y es una excelente zona protegida prediseñada tal como se describe en la tabla anterior, y se puede personalizar rápidamente para satisfacer necesidades de creación de informes más específicas.

**1,2 | Nuevos posibles clientes por campaña (o perspectivas más detalladas)**

Para obtener una perspectiva más granular de los datos resumidos en el informe &quot;Nuevos posibles clientes por canal de marketing&quot; (1.1), añada un resumen adicional en el nivel de campaña. Esto le permitirá no solo comprender qué &quot;Canales de marketing&quot; están impulsando la creación de nuevos posibles clientes, sino también, más específicamente, qué campañas dentro de esos canales tienen el mejor rendimiento:

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué <i>campañas</i> ¿Está influyendo en los posibles clientes en la creación?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Puntos de contacto de clientes potenciales y compradores (CRM)<br>
   Métrica: posibles clientes ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Campo de fecha/tipo de fecha</td> 
   <td>Fecha de creación del posible cliente (CRM) / Fecha de creación (Discover)</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccione el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Nombre de la campaña de publicidad (CRM)</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Primer contacto, creación de posibles clientes, <strong>Forma de U</strong><br>
   *SUMA de los campos "Recuento" en los informes de CRM (Recuento - Primer toque, Recuento - Creación de posibles clientes, Recuento - Forma de U)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Obtenga una perspectiva aún más granular resumiendo el informe con otros campos disponibles del objeto Touchpoint del comprador. Para ello, configure agrupaciones (CRM) o dimensiones adicionales (Discover). Según el canal (que puede ser representativo de su función), puede haber detalles adicionales más allá del nivel de campaña en el que desee obtener información. Vamos a explorar en profundidad &quot;Búsqueda de pago&quot;, por ejemplo, en la siguiente tabla...

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué <i>palabras clave</i> ¿Está influyendo en los posibles clientes en la creación?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Puntos de contacto de clientes potenciales y compradores (CRM)<br>
   Métrica: posibles clientes ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td>Canal de marketing = Búsqueda de pago</td> 
  </tr>
  <tr>
   <td>Campo de fecha/tipo de fecha</td> 
   <td>Fecha de creación del posible cliente (CRM) / Fecha de creación (Discover)</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccione el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Texto de palabra clave (CRM) / Palabra clave (Discover)</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Primer contacto, creación de posibles clientes, <strong>Forma de U</strong><br>
   *SUMA de los campos "Recuento" en los informes de CRM (Recuento - Primer toque, Recuento - Creación de posibles clientes, Recuento - Forma de U)</td> 
  </tr>
 </tbody>
</table>

El nivel de granularidad puede variar según el canal. El enfoque recomendado sería preguntarse, &quot;¿qué hay del &#39;canal X&#39; que estoy buscando entender con más detalle?&quot;. Los administradores de búsqueda de pago también pueden estar interesados en dimensiones adicionales como:

* Nombre de campaña de anuncios
* Contenido de anuncios
* Grupo de anuncio

Sin embargo, los administradores de eventos pueden estar más interesados en qué eventos específicos o en qué tipos de eventos influyeron en la creación de la mayoría de los posibles clientes:

* Nombre de la campaña de publicidad/Campaña de Salesforce = evento específico
* Medio = &quot;Tipo&quot; de campaña

**AVISO**: Es posible que sea necesario añadir filtros adicionales a cualquiera de las variaciones de informes descritas anteriormente o siguientes. Estos filtros serían específicos de su organización y los equipos de operaciones de marketing u operaciones de ventas podrían ayudarle a aconsejarlos. No es raro que una organización ejecute los mismos filtros en todos los informes para asegurarse de que el informe sea lo más limpio y preciso posible. Algunos ejemplos comunes son:

* Filtrado de registros internos de pruebas, normalmente por dirección de correo electrónico
* Filtrado basado en ciertos &quot;tipos de registro&quot; que pueden ser específicos de su unidad comercial

**1,3 | Nuevos posibles clientes por contenido (solo informes CRM)**

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué <i>content</i> ¿Está influyendo en los posibles clientes en la creación?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Puntos de contacto de clientes potenciales y compradores (CRM)</td> 
  </tr>
  <tr>
   <td>Campo de fecha</td> 
   <td>Fecha de creación de cliente potencial</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccione el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Página de aterrizaje<br> 
   URL del formulario</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Primer contacto, creación de posibles clientes, <strong>Forma de U</strong><br></td> 
  </tr>
 </tbody>
</table>

**AVISO**: los dos campos principales para informar sobre contenido o recursos digitales son &quot;Página de aterrizaje&quot; y &quot;URL del formulario&quot;. Estos dos valores pueden ser iguales si el posible cliente convierte (envía un formulario) en la misma página en la que &quot;aterrizó&quot; (página de aterrizaje), _sin embargo_ Sin embargo, a veces estos valores son diferentes. Por ejemplo, el posible cliente puede hacer clic en un vínculo de Facebook que le lleva a una página del sitio web (el valor sería &quot;Página de aterrizaje&quot;). El posible cliente puede entonces salir de esa página, continuar con su sesión en el sitio y terminar enviando un formulario en otra página (URL del formulario). Esto se resumiría en un único punto de contacto que representa de dónde proviene el posible cliente (canal de marketing), qué contenido le llevó al sitio (página de aterrizaje) y qué contenido terminó descargando (URL del formulario). &quot;URL del formulario&quot; es también el campo de referencia para informes en otros formularios no asociados con contenido descargable, como los formularios &quot;Contáctenos&quot; o &quot;Solicitud de demostración&quot;.

>[!TIP]
>
>Obtenga información sobre &quot;contenido&quot; específico con filtros adicionales
>
>* Filtrar por: &#39;Página de aterrizaje&#39; CONTIENE (por ejemplo):
>   * /blog
>   * /ebook
>   * /seminario web
>
>* OR: &quot;URL del formulario&quot; CONTIENE (por ejemplo)
>   * /contact
>   * /demo

Los informes basados en &quot;Contenido&quot; proporcionan un gran valor al generar informes sobre cualquier parte del canal; sin embargo, se utilizan normalmente en la parte superior del canal para proporcionar una perspectiva adicional de la participación inicial de los posibles clientes. Teniendo en cuenta que la &quot;Búsqueda orgánica&quot; tiende a ser el canal más sólido para impulsar la participación inicial (FT), no hay tantos datos de nivel de &quot;Campaña&quot;.

Los informes basados en &quot;Contenido&quot; son ideales para obtener información sobre los posibles clientes, más específicamente dentro del canal de marketing de nivel superior, en este caso la &quot;Búsqueda orgánica&quot;.

**1,4 | Participación total del posible cliente en un intervalo de fechas determinado**

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué canales de marketing han tenido la mayor cantidad <i>participación total del posible cliente</i> en el pasado (semana/mes/trimestre)?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Puntos de contacto de clientes potenciales y compradores (CRM)<br> 
   Métrica: posibles clientes ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Campo de fecha/tipo de fecha</td> 
   <td>Fecha de Touchpoint</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccione el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Canal de marketing (o más granular)</td> 
  </tr>
  <tr>
   <td>Modelos óptimos*</td> 
   <td>*Este informe trata menos de medir la procedencia de los posibles clientes con un modelo de atribución, pero más sobre la variable <i>número total de puntos de contacto (cantidad de participación)</i>, incluidos los que se encuentran después del toque de creación de posibles clientes. El recuento total de puntos de contacto de registro reflejaría qué canales han visto la mayor participación de posibles clientes.</td> 
  </tr>
 </tbody>
</table>

**AVISO**: Basar los informes en torno a &quot;Fecha de punto de contacto&quot; es la forma más reflexiva de comprender el rendimiento de marketing durante un intervalo de fechas determinado. &quot;Fecha de punto de contacto&quot; estructura el informe de forma que la atribución no solo está relacionada con el canal, la campaña o el contenido, sino que también muestra cuándo se produjo el punto de contacto. Esta es la forma más eficaz de comprender qué participación de marketing se produjo en un momento determinado y también la forma recomendada de medir el impacto del marketing en comparación con el gasto de marketing invertido durante el mismo tiempo. Se recomienda cuando se realiza cualquier análisis de gasto o ROI de marketing (consulte 5.1).

**2. POSIBLES CLIENTES CUALIFICADOS DE MARKETING con PUNTOS DE CONTACTO DEL COMPRADOR**

Uno de los informes más comunes se centra no solo en nuevos posibles clientes o en la participación de nivel de posible cliente, sino más específicamente en los &quot;posibles clientes cualificados de marketing&quot; (MQL). Hay un par de enfoques diferentes en cuanto a la creación de informes sobre MQL, según lo que [!DNL Marketo Measure] funciones y funcionalidades a las que tiene acceso.

**2,1 | Posibles clientes cualificados de marketing por canal (multitáctil)**

Este enfoque para medir el impacto del marketing en la influencia de los MQL es esencialmente una continuación del informe &quot;Nuevos posibles clientes por canal de marketing&quot; (1.1), pero con los criterios adicionales de que los posibles clientes que se miden son más específicamente MQL. El modelo de atribución en forma de U aún se recomienda aquí para identificar qué canales y contenido de marketing están generando posibles clientes que luego generarán _probable_ para convertirse en un MQL:

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué canales de marketing son los mejores para generar nuevos posibles clientes que se convierten en <i>MQL</i>?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Puntos de contacto de clientes potenciales y compradores (CRM)<br> 
   Métrica: posibles clientes ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td>MQL = true*<br>
   *<i>Los MQL pueden definirse de forma diferente por organización. Asegúrese de que [!DNL Marketo Measure] El informe se filtra para MQL usando los mismos campos que otros informes basados en MQL. Sería necesario crear un filtro de segmentos del mismo modo para los informes sobre MQL en [!DNL Marketo Measure] Descubrir.</i></td> 
  </tr>
  <tr>
   <td>Campo de fecha/tipo de fecha</td> 
   <td>Fecha de MQL (o equivalente) / Fecha de creación ([!DNL Marketo Measure] Discover)<br> <i>La fecha de creación del posible cliente también se puede utilizar en los informes de CRM si "Fecha de MQL" no es una opción en su CRM. Es importante tener en cuenta qué campo de fecha está utilizando para definir el conjunto de datos cohorte.</i></td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccione el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Canal de marketing</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Primer contacto, creación de posibles clientes, <strong>Forma de U</strong><br> 
   SUME los campos "Recuento" en los informes de CRM (Recuento - Primer toque, Recuento - Creación de posibles clientes, Recuento - Forma de U)</td> 
  </tr>
 </tbody>
</table>

**2,2 | Posibles clientes cualificados de marketing por canal (un solo contacto, solo CRM)**

Este enfoque para medir el impacto del marketing en la influencia de los MQL se centra más en identificar cuáles _punto de contacto único_ fue el último contacto antes de que el posible cliente llegara a MQL.

>[!NOTE]
>
>Para ejecutar este informe, se requiere un valor de &quot;Estado del posible cliente&quot; de &quot;MQL&quot; para definir la fase MQL con fines de seguimiento (fase de canal). Si los MQL no se rastrean mediante el campo &quot;Estado del posible cliente&quot;, el modelo de atribución personalizado con la función de fases personalizadas es necesario para crear una fase &quot;MQL&quot; personalizada en el [!DNL Marketo Measure] Configuración de cuenta.

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>¿Qué canales de marketing son más sólidos para impulsar a los posibles clientes a alcanzar el estado MQL?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Puntos de contacto de clientes potenciales y compradores (CRM)<br>
   <i>este informe solo es posible dentro de los informes de CRM. No es posible filtrar ciertos valores de "Posición del punto de contacto" en [!DNL Marketo Measure] Discover</i></td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td><strong>La posición del punto de contacto CONTIENE "MQL"</strong></td> 
  </tr>
  <tr>
   <td>Campo de fecha/tipo de fecha</td> 
   <td>Fecha de MQL (o equivalente)</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccione el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Canal de marketing</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td><i>Dado que este informe se filtra en un solo punto de contacto, los modelos de atribución de nivel de posible cliente no son tan relevantes. Al igual que el "Informe de participación del posible cliente" (1.4), el número de registros de punto de contacto se utilizaría aquí para comprender qué canales son los más sólidos (cada posible cliente solo tendría un punto de contacto MQL).</i></td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Explore otras agrupaciones o dimensiones para obtener más información sobre los MQL. Como se mencionó en los otros informes &quot;Posibles clientes con puntos de contacto del comprador&quot;, el punto de contacto del comprador ofrece mucha más granularidad que solo el canal de marketing. Un informe basado en &quot;Contenido&quot; también se podría combinar con cualquiera de los informes de MQL anteriores para comprender mejor qué contenido influye mejor en los MQL.

**3. [!DNL MARKETO MEASURE] PERSONAS con PUNTOS DE CONTACTO DEL COMPRADOR**

Hay una tercera costumbre [!DNL Marketo Measure] objeto en Salesforce que puede ser muy útil al informar sobre métricas relacionadas con personas: **el [!DNL Marketo Measure] Persona (BP)**. La BP soluciona el antiguo problema de cómo representar la información de contactos y posibles clientes en el mismo informe. Une todos los BT relacionados con una &quot;persona&quot; (a [!DNL Marketo Measure] ID de la persona (es su dirección de correo electrónico). Tanto si existen como clientes potenciales o de contacto, la BP actúa como objeto puente para ayudar a los informes a abarcar a ambos, y es muy útil para producir informes más sofisticados sobre las personas.

El [!DNL Marketo Measure] La persona solo está relacionada con uno de los objetos de punto de contacto, el punto de contacto del comprador (BT). Esto significa que no se puede utilizar para métricas relacionadas con oportunidades o ingresos. A &#39;[!DNL Marketo Measure] El tipo de informe Puntos de contacto de persona y comprador es muy comprensible _participación total_ ya que muestra todos los BT si el BT se relaciona con un posible cliente o contacto más específicamente. Por ejemplo: si utiliza una campaña de Salesforce para rastrear un evento, puede tener miembros de la campaña dentro de la campaña de CRM que existan como posibles clientes O como contactos. [!DNL Marketo Measure] creará puntos de contacto para los miembros de la campaña independientemente, pero sin la variable [!DNL Marketo Measure] Persona, los informes estándar de Salesforce requerirían dos informes separados para comprender cuántas _total_ puntos de contacto que tiene del evento: uno que es &quot;Posibles clientes con puntos de contacto del comprador&quot; y otro que es &quot;Contactos con puntos de contacto del comprador&quot;. Unos pocos más [!DNL Marketo Measure] A continuación se enumeran los casos de uso de informes basados en personas:

**3,1 [!DNL Marketo Measure] Personas que han descargado &quot;libros electrónicos&quot; o &quot;documentos técnicos&quot; (descargas totales)**

Este informe sería igual que un informe basado en &quot;Contenido&quot; a nivel de posible cliente. Sin embargo, en lugar de buscar medir el número de posibles clientes atribuibles a cada parte de contenido, utilice un [!DNL Marketo Measure] El informe de personas será útil para comprender el total _número de descargas_ si el recurso está bloqueado (el número total de puntos de contacto representaría el número total de descargas/envíos del formulario).

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>¿Cuántas personas han descargado un recurso en particular?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>[!DNL Marketo Measure] Puntos de contacto de personas y compradores (CRM)</td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td>"URL del formulario" CONTIENE (por ejemplo)<br>
   <li>/ebook</li>
   <li>/documento técnico</li>
   <i>Los valores de filtro anteriores solo son ejemplos. El valor real se basará en la estructura URL de cada organización.</i></td> 
  </tr>
  <tr>
   <td>Campo de fecha/tipo de fecha</td> 
   <td>Fecha de Touchpoint <i>(cuándo se descargó el recurso)</i></td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccione el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Formulario/URL</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Este informe no trata tanto de medir la procedencia de los posibles clientes o contactos con un modelo de atribución, sino más bien del <i>número total de puntos de contacto (cantidad de participación)</i>, incluidos los que se encuentran después del toque de creación de posibles clientes. Con este informe buscamos entender el proceso de <i>cantidad de participación total</i>. El recuento total de registros de puntos de contacto reflejaría qué recursos se han descargado más.</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Para cualquier posible cliente con [!DNL Marketo Measure] Tipo de informe de personas, comience personalizando el informe generado previamente llamado &#39;**[!DNL Marketo Measure]101 | Posibles clientes/contactos por canal**&#39;. Este informe está disponible de forma predeterminada y es un excelente [!DNL Marketo Measure] Zona protegida basada en personas. Está generado previamente y se puede personalizar rápidamente para satisfacer necesidades de creación de informes más específicas.

>[!TIP]
>
>Puede utilizar este informe para obtener información sobre la participación total de cualquier dimensión de marketing desde el objeto de punto de contacto del comprador, no solo sobre las descargas de contenido como se muestra en el ejemplo. En su lugar, el informe se puede agrupar o filtrar en dimensiones como &quot;Canal de marketing&quot; o &quot;Nombre de la campaña de publicidad&quot; para comprender mejor la participación total de posibles clientes y contactos en la base de datos. Cambie los filtros o agrupaciones dentro del informe a cero en en otras dimensiones representadas por otros campos desde el objeto touchpoint.

**3,2 [!DNL Marketo Measure] Personas que se han registrado para un evento (solo CRM)**

_Este informe solo es aplicable si los formularios de registro están alojados en sus sitios web que [!DNL Marketo Measure] es capaz de realizar un seguimiento digital._

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>¿Qué canales de marketing dirigen mis registros de eventos?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>[!DNL Marketo Measure] Puntos de contacto de personas y compradores (CRM)</td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td>"URL del formulario" CONTIENE (por ejemplo)<br>
   <li>/event</li>
   <i>El valor de filtro anterior solo son ejemplos. El valor real se basará en la estructura URL de cada organización.</i></td> 
  </tr>
  <tr>
   <td>Campo de fecha/tipo de fecha</td> 
   <td>Fecha de Touchpoint <i>(cuando se envió el formulario de registro)</i></td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccione el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>URL del formulario<br>
   Canal de marketing</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td>Este informe no trata tanto de medir la procedencia de los posibles clientes o contactos con un modelo de atribución, sino más bien del <i>número total de puntos de contacto (número de registros)</i>, incluidos los que se encuentran después del toque de creación de posibles clientes. Con este informe buscamos obtener una perspectiva de lo que impulsa los registros de eventos. El recuento total de puntos de contacto por "canal de marketing" reflejará qué canales fueron los que generaron la mayor cantidad de registros.</td> 
  </tr>
 </tbody>
</table>

La clave de este informe es que los datos del punto de contacto del comprador también proporcionarán datos del canal de marketing. Aunque es posible que ya tenga conocimiento sobre la cantidad de personas que se han registrado en sus eventos, este informe también proporcionará conocimiento sobre qué canales de marketing digital, fuentes o campañas están trayendo personas a su sitio web para luego registrarse en el evento.

>[!TIP]
>
>Este mismo enfoque se puede adoptar cuando se busca obtener información sobre los registros de seminarios web o quizás sobre las descargas de seminarios web bajo demanda (si son un recurso cerrado). La única diferencia sería el valor de filtro en la &quot;URL del formulario&quot; si esos formularios están alojados en páginas únicas del sitio web. Sin embargo, el objetivo es el mismo. Responde a las preguntas &quot;cuáles de mis canales de marketing son los que más descargas de seminarios web bajo demanda/de registros están impulsando.

**3,3 [!DNL Marketo Measure] Personas con puntos de contacto de comprador (validación de punto de contacto)**

Teniendo en cuenta [!DNL Marketo Measure] La persona nos permite informar sobre todos los puntos de contacto en un solo informe, es el tipo de informe ideal para utilizar cuando busque validar sus datos. Queremos asegurarnos de no pasar por alto ningún punto de contacto que pueda revelar, por ejemplo, dónde hay un problema en la configuración de sus &quot;Canales de marketing&quot; (consulte los artículos de asistencia vinculados a continuación para obtener más información sobre la configuración de sus &quot;Canales de marketing&quot;).

* [Configuración de canales personalizados en línea](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
* [Configuración de canales personalizados sin conexión](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)

Básicamente, los datos de punto de contacto reflejarán lo que se ha rastreado mediante [!DNL Marketo Measure] y se pueden auditar para garantizar que la configuración coincida con las entradas en función de elementos como valores de parámetro de UTM, páginas de referencia o tipos de campaña. Si los datos del punto de contacto no coinciden con la configuración, es muy probable que haya que ajustar algo. Más allá de la configuración de &quot;Canal de marketing&quot;, puede ver los datos de puntos de contacto para determinar qué puntos de contacto pueden necesitar ser [suprimido](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md) o [segmentado](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md). Se recomienda auditar los datos de su punto de contacto dentro de un &#39;[!DNL Marketo Measure] Informe de personas y puntos de contacto del comprador al final de cada mes o trimestre, si es posible. Esto garantizará que su atribución sea lo más precisa posible. El &#39;[!DNL Marketo Measure] 101 | El informe &quot;Posibles clientes/contactos por canal&quot; disponible de forma predeterminada es un buen punto de partida. Incluya los siguientes campos si aún no se han incluido para revisar algunos de los elementos de configuración más cruciales:

* **Canal de marketing** - Ruta = Canal de marketing.Subcanal (valores establecidos en [!DNL Marketo Measure])
* **Touchpoint Source** = utm_source
* **Mediana** = utm_medium (puntos de contacto en línea) O Tipo de campaña de CRM (puntos de contacto sin conexión)
* **Página de referente** (se utilizó la configuración &quot;Canales en línea&quot;)
* **Página de aterrizaje: sin procesar** (utilizado la configuración &quot;Canales en línea&quot;) también una entrada común para la supresión de puntos de contacto en la pestaña &quot;Configuración de punto de contacto&quot; de su Configuración)
* **URL del formulario** (una entrada común para la supresión de puntos de contacto en la pestaña &quot;Configuración de punto de contacto&quot; de Configuración)

**PUNTO DE CONTACTO DE ATRIBUCIÓN DEL COMPRADOR (BAT)**

Los puntos de contacto de atribución del comprador (BAT) representan los puntos de contacto relevantes de todos los contactos conectados a la oportunidad (a través de las funciones de contacto de la oportunidad o a través de un ID de cuenta compartido, según la configuración). A diferencia de los MTD (que están principalmente conectados a personas), los MTD pueden asociarse con ingresos. Como tal, utilizará las MTD para responder a preguntas relacionadas con oportunidades, principalmente abiertas _Oportunidades/Ingresos de canalización_ y cerrado ganado _Oportunidades/Ofertas/Ingresos_. Una MTD se crea a través de los registros BT de un contacto en cuanto se crea una oportunidad en la misma cuenta que el contacto (la MTD no se convierte en una MTD. Se hace referencia a los datos BT simplemente para crear un registro adicional (la MTD que luego se relaciona con la oportunidad).

El punto de contacto de atribución del comprador nos permite medir el impacto del marketing a mayor profundidad en el canal. _La profundidad del canal en el que desea medir puede representarse mediante los distintos modelos de atribución multitáctil_.

Teniendo en cuenta que la relación principal de las MTD es con la oportunidad, se utilizan para responder preguntas como las siguientes:

* ¿Cuáles de mis esfuerzos de marketing han influido en la mayor cantidad de oportunidades?
* ¿Cuántos ingresos de canalización nuevos puedo atribuir a cada uno de mis canales de marketing?
* ¿Cuál de mis campañas obtuvo el retorno de la inversión más alto el trimestre pasado?

El [modelos de atribución](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md) para obtener la mejor perspectiva de las métricas basadas en oportunidades, consulte:

**Forma de W** - El &#39;_Modelo de canalización_&#39;. El modelo en forma de W incluye tres puntos de contacto de hitos. En este modelo, los puntos de contacto FT, LC y OC se atribuyen cada uno el 30 % del crédito de atribución. El 10 % restante se atribuye por igual a cualquier punto de contacto intermedio que se produzca entre los tres puntos de contacto de hito.

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-2.png"></td> 
   <td>Este modelo resume esencialmente el recorrido de una nueva oportunidad que suele ser sinónimo de generación de nuevos ingresos de canalización.<p>
   <p>
   Cuando se busca medir el impacto del marketing en nuevas oportunidades o en la nueva canalización generada, se recomienda el modelo con forma de W.</td> 
  </tr>
 </tbody>
</table>

**Ruta completa** - El &#39;_Modelo obtenido cerrado_&#39;. Este modelo incluye los cuatro puntos de contacto de hitos: FT, LC, OC y Cerrado. A cada uno se le otorga el 22,5% del crédito de Oportunidad, y el 10% restante se distribuye equitativamente entre los toques intermediarios.

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-3.png"></td> 
   <td>Este modelo resume esencialmente el recorrido de una operación ganada cerrada que suele ser sinónimo de ingresos/reservas ganados cerrados.<p>
   <p>
   Cuando se busca medir el impacto del marketing en las ofertas ganadas cerradas o en los ingresos ganados cerrados, se recomienda el modelo de ruta completa.</td> 
  </tr>
 </tbody>
</table>

Este modelo resume esencialmente el recorrido de una operación ganada cerrada que suele ser sinónimo de ingresos/reservas ganados cerrados.

Cuando se busca medir el impacto del marketing en las ofertas ganadas cerradas o en los ingresos ganados cerrados, se recomienda el modelo de ruta completa.

**Personalizado** - [!DNL Marketo Measure] también ofrece un modelo de atribución personalizado que permite a los usuarios elegir qué puntos de contacto o etapas personalizadas incluir en su modelo. Además, los usuarios pueden controlar el porcentaje de crédito de atribución atribuido a estos puntos de contacto y fases. Según la configuración del modelo personalizado, se puede utilizar de la manera más adecuada para medir las oportunidades y la canalización O, las ofertas y los ingresos ganados cerrados. Tenga esto en cuenta al utilizarlo en los informes.

>[!NOTE]
>
>El modelo de atribución personalizado es una función adicional que no está disponible para todos los clientes. Póngase en contacto con el equipo de cuenta de Adobe (su administrador de cuentas) para obtener más información sobre cómo agregar esta función a su cuenta.

Normalmente, los especialistas en marketing necesitan saber: &quot;¿de dónde vienen mis oportunidades?&quot;. De forma similar a la creación de informes a nivel de posibles clientes, históricamente esta pregunta se respondió con un valor único y unidimensional (por ejemplo, la fuente de la campaña principal). Sin embargo, sabemos que se invierte mucho más en el desarrollo de una oportunidad que en un único punto de contacto de un único contacto. Normalmente, hay varios puntos de contacto de varios canales y de varias partes interesadas que influyen en una oportunidad en la creación. Con [!DNL Marketo Measure], podemos mostrar todos los puntos de contacto de una cuenta para comprender mejor de dónde proviene una oportunidad. Sin embargo, más allá de eso, podemos seguir apareciendo cualquier punto de contacto que se haya producido después de crear la oportunidad y hasta el punto en que se cierre la oportunidad. Esto nos permite no solo tomar un enfoque de múltiples contactos para entender de dónde vino una oportunidad, sino también lo que influyó para que se cerrara y, en última instancia, para representar ingresos ganados cerrados. Esto permite conocer diferentes preguntas, como &quot;¿cuál es el impacto del marketing en la influencia para que las ofertas cierren?&quot;, &quot;¿qué marketing está impulsando el cierre de los ingresos ganados?&quot; y, en última instancia, &quot;¿cuál de mis esfuerzos de marketing obtiene el mayor ROI?&quot;

## INFORMES RECOMENDADOS CON EL PUNTO DE CONTACTO DE ATRIBUCIÓN DEL COMPRADOR (BAT) {#recommended-reports-using-the-buyer-attribution-touchpoint}

**4,1 | Nuevas oportunidades por canal de marketing**

Resumir los datos del punto de contacto de atribución de comprador de Oportunidades por el campo &quot;Canal de marketing&quot; es la vista de nivel superior que representa qué canales/tácticas influyen en las nuevas oportunidades en la creación. Estructurar este informe en torno a un &quot;Tipo de fecha&quot; = &quot;Fecha de creación de la oportunidad&quot; garantiza que también se esté resumiendo el informe en función de cuándo se creó la oportunidad en su CRM. Es posible que los puntos de contacto hayan sido anteriores, pero seguirán estando relacionados con las oportunidades que se hayan creado dentro del intervalo de fechas definido y, por lo tanto, recibirán crédito de atribución a medida que se reconozca que influyen en la oportunidad.

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué <i>canales de marketing</i> ¿Está influyendo en la creación de Oportunidades?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Puntos de contacto de atribución de comprador con oportunidades (CRM)<br> 
   Métrica: Oportunidades ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td>
   <li>Fase de oportunidad* <i>(opcional) según las oportunidades específicas que desee limitar al informe. Es posible que solo desee informar sobre las MTD que siguen asociadas únicamente a Oportunidades "Abiertas" (por ejemplo)</i></li>
   <li>Tipo de oportunidad (es común filtrar ciertas oportunidades, es decir, "Nuevo negocio" en lugar de <i>todo</i> Oportunidades)</li><br>
   *Se debe usar un filtro de segmento para 'Tipo de oportunidad' en [!DNL Marketo Measure] Discover</td> 
  </tr>
  <tr>
   <td>Campo de fecha/tipo de fecha</td> 
   <td>Fecha de creación de la oportunidad (CRM) / Fecha de creación (Discover)</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccione el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Canal de marketing</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td><strong>Forma de W</strong><br>
   SUME los campos "Forma de W" en los informes de CRM (Recuento: Forma de W, Ingresos: Forma de W)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Para cualquier tipo de informe &quot;Puntos de contacto de atribución del comprador con oportunidades&quot;, comience personalizando el informe creado previamente y titulado &quot;[!DNL Marketo Measure] 101 | Oportunidades por canal&#39;. Este informe está disponible de forma predeterminada y es una buena zona protegida prediseñada tal como se describe en la tabla anterior y se puede personalizar rápidamente para necesidades de creación de informes más específicas (el informe utiliza un modelo de ruta completa de forma predeterminada, por lo que asegúrese de personalizar el informe para incluir cualquier otro modelo de atribución, en este caso, el modelo con forma de W).

>[!TIP]
>
>El informe descrito anteriormente también se utilizaría para comprender la cantidad de moneda que también debería atribuirse. Al realizar informes en el nivel de oportunidad mediante MTD, hay dos métricas clave que se pueden resumir: moneda (la cantidad de la oportunidad) y el propio registro de oportunidad. En el ejemplo anterior, estamos midiendo más específicamente las oportunidades abiertas y los nuevos ingresos de la canalización.

>[!TIP]
>
>Obtenga una perspectiva aún más granular resumiendo el informe con otros campos disponibles del objeto Buyer Attribution Touchpoint. Esto se hace del mismo modo que en el nivel de posible cliente con puntos de contacto del comprador (1.2). Para ello, agregue agrupaciones (CRM) o dimensiones adicionales (Discover). Según el canal (que puede ser representativo de su función), puede haber detalles adicionales más allá del nivel de campaña en el que desea obtener más información. Vamos a explorar en &quot;Búsqueda de pago&quot; a continuación:

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Que <i>palabras clave</i> de mis anuncios de búsqueda de pago están generando la mayor cantidad de ingresos de la canalización?
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
   <li>Canal de marketing = Búsqueda de pago</li>
   <li>Fase de oportunidad* <i>(opcional) según las oportunidades específicas que desee limitar al informe. Este ejemplo se basa en los ingresos de canalización definidos en [!DNL Marketo Measure] por "Abrir" (oportunidades que representan ingresos potenciales/canalización abierta)</i></li>
   <li>Tipo de oportunidad (es común filtrar ciertas oportunidades, es decir, "Nuevo negocio" en lugar de <i>todo</i> Oportunidades)</li><br>
   *Se debe usar un filtro de segmento para 'Tipo de oportunidad' en [!DNL Marketo Measure] Discover</td> 
  </tr>
  <tr>
   <td>Campo de fecha/tipo de fecha</td> 
   <td>Fecha de creación de la oportunidad</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccione el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Texto de palabra clave (CRM)<br> 
   Palabra clave (Discover)</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td><strong>Forma de W</strong><br>
   SUME los campos "Forma de W" en los informes de CRM (Recuento: Forma de W, Ingresos: Forma de W)</td> 
  </tr>
 </tbody>
</table>

**4,2 | Ofertas por canal de marketing**

Este informe sería esencialmente el mismo que el primer ejemplo de punto de contacto de atribución de comprador (4.1), excepto que la métrica ahora ha cambiado de Oportunidades abiertas a Ofertas ganadas cerradas. La métrica siempre debe ser lo que indica qué modelo de atribución utilizar. Teniendo en cuenta que ahora estamos viendo las ofertas ganadas cerradas y sus MTD relacionadas, deberíamos utilizar un modelo que represente todo el recorrido del comprador (acuerdo). Esto garantiza que cualquier seguimiento de contacto de marketing durante el recorrido del comprador reciba crédito de atribución:

<table> 
 <tbody>
  <tr>
   <td>Pregunta</td> 
   <td>Qué <i>canales de marketing</i> ¿Está influyendo en los acuerdos para cerrar?</td> 
  </tr>
  <tr>
   <td>Tipo de informe</td> 
   <td>Puntos de contacto de atribución de comprador con oportunidades (CRM)<br> 
   Métrica: Ofertas ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filtros</td> 
   <td>
   <li>Fase de oportunidad (<i>solo las oportunidades ganadas cerradas deben aparecer en el informe</i>) O,</li>
   <li>Oportunidad ganada = verdadero</li>
   <li>Tipo de oportunidad (es común filtrar ciertas oportunidades, es decir, "nuevos negocios" en lugar de todas las oportunidades)<br>
   </td> 
  </tr>
  <tr>
   <td>Campo de fecha/tipo de fecha</td> 
   <td>Fecha de cierre de oportunidad</td> 
  </tr>
  <tr>
   <td>Intervalo de fechas</td> 
   <td><i>seleccione el intervalo de fechas deseado</i></td> 
  </tr>
  <tr>
   <td>Grupo/Dimension</td> 
   <td>Canal de marketing</td> 
  </tr>
  <tr>
   <td>Modelos óptimos</td> 
   <td><strong>Ruta completa</strong><br>
   SUME los campos "Ruta completa" en los informes de CRM (Recuento - Ruta completa, Ingresos - Ruta completa)</td> 
  </tr>
 </tbody>
</table>

**AVISO**: Es crucial recordar filtrar por las oportunidades específicas que desea incluir en los informes basados en MTD, especialmente cuando se trata de &quot;Oportunidades abiertas e ingresos de canalización&quot; frente a &quot;Acuerdos e ingresos ganados cerrados&quot;. Esto se suele hacer mediante un filtro &quot;Fase de oportunidad&quot; (el filtro &quot;Oportunidad ganada&quot; = true/false también puede ser muy útil aquí).

**5. ROI ([!DNL Marketo Measure] Solo Discover)**

El [!DNL Marketo Measure] Descubra cómo los paneles proporcionan una vista de alto nivel del rendimiento de marketing mediante [!DNL Marketo Measure] datos de atribución. Estos paneles agregados proporcionan datos clave sobre el gasto en marketing y el retorno de la inversión que no están disponibles en los informes de CRM. Este entorno creado previamente le permite ver el rendimiento de marketing en consonancia con los datos de ROI, lo que le permite tomar decisiones procesables en relación con el marketing.

>[!TIP]
>
>Siempre que tenga una pregunta relacionada con el retorno de la inversión, el gasto o el coste, [!DNL Marketo Measure] ¡Discover será el mejor lugar para informar!

El [!DNL Marketo Measure] Los paneles de Discover constan de datos de puntos de contacto de Attribution Touchpoint del comprador y de puntos de contacto de la atribución del comprador, así como datos clave de CRM. La principal diferencia entre los informes de CRM y los de [!DNL Marketo Measure] Discover indica que los datos de puntos de contacto en Discover se presentan de forma más &quot;agregada&quot; y se resumen por dimensión (canal de marketing, campaña, etc.) a diferencia de los registros de puntos de contacto individuales, que se pueden resumir a continuación. [!DNL Marketo Measure] Discover se utiliza para comprender a alto nivel cuál de sus esfuerzos está teniendo el mayor impacto en los posibles clientes, las oportunidades de negocio, las ofertas y cuántos ingresos deben atribuirse a ellos. Una vez que hayamos calculado los ingresos atribuidos a través de los distintos modelos de atribución (se recomienda Ruta completa para atribuir ingresos/reservas ganados cerrados), podemos medirlos con respecto a cuánto se gastó en la misma dimensión (Canal de marketing, Subcanal o Campaña). Esto nos da el **ROI**.

>[!TIP]
>
>Una de las cosas más importantes que debe recordar al realizar informes en Discover es qué tipo de datos está utilizando para filtrar. Tipo de fecha dictará qué conjunto de datos [!DNL Marketo Measure] se utiliza en los distintos mosaicos.

* **Fecha de Touchpoint**: Muestra los datos relacionados que tenían una &quot;Fecha de punto de contacto&quot; en el periodo de tiempo especificado
* **Fecha de creación**: Muestra los datos relacionados que tenían una &quot;Fecha de creación&quot; en el periodo de tiempo especificado
* **Fecha de cierre**: Muestra los datos relacionados que tenían una &quot;Fecha de cierre&quot; en el periodo de tiempo especificado

Al informar sobre el ROI en [!DNL Marketo Measure] Descubra, se recomienda utilizar un &#39;Tipo de fecha&#39; = &quot;Fecha de punto de contacto&quot;. Para determinar el retorno de cada dólar invertido, debemos asegurarnos de que los ingresos se atribuyan de nuevo a la fecha en que se hizo la inversión. &quot;Tipo de fecha&quot; = &quot;Fecha de punto de contacto&quot; garantiza que los informes estén estructurados de esta manera, en lugar de cuando se creó la oportunidad (fecha de creación) o se cerró (fecha de cierre). Echemos un vistazo más de cerca:

Los filtros que se indican a continuación son cruciales para un informe centrado en el retorno de la inversión en [!DNL Marketo Measure] (lo más probable es que configure estos filtros en los tableros &quot;Información general&quot;, &quot;CMO&quot; o &quot;ROI&quot;):

**5,1 | ROI en el tablero &quot;Información general&quot;**

![](assets/bizible-reporting-guide-4.png)

El intervalo &quot;Fecha&quot; no solo establece la cohorte de puntos de contacto (por fecha de punto de contacto) que reciben atribución, sino que también define el intervalo que representan el mosaico o las columnas &quot;Gastar&quot;.
[!DNL Marketo Measure] simplemente consulta el intervalo &quot;Fecha&quot; para determinar cuánto se gastó en total o en los niveles de canal de marketing, subcanal o campaña. Consulte lo siguiente:

![](assets/bizible-reporting-guide-5.png)

La captura de pantalla anterior muestra los datos de gasto en marketing de los últimos 3 meses completos. En este ejemplo, se gastaron 12 970 $ en todos los canales. Este número está formado por los datos de gasto de marketing [!DNL Marketo Measure] tiene de integraciones con cualquiera de sus cuentas de anuncios conectadas (Google AdWords, Bing Ads, Facebook Ads, LinkedIn, DoubleClick) y cualquier gasto de marketing adicional que se haya cargado en su cuenta o extraído automáticamente de un registro de Campaign en su CRM. El ejemplo también muestra cuánto won cerrados &#39;Ingresos&#39; también pueden atribuirse a puntos de contacto que se produjeron durante el mismo intervalo de fechas (cuadros verdes). Así es como se calcula el retorno de la inversión: ingresos atribuidos a puntos de contacto procedentes de la inversión en el mismo intervalo de fechas:

![](assets/bizible-reporting-guide-6.png)

**AVISO**: [!DNL Marketo Measure] define &quot;Ingresos&quot; como ingresos ganados cerrados o reservas y define &quot;Ingresos de canalización&quot; como _ingresos abiertos/potenciales procedentes de oportunidades abiertas_.

Otra conclusión importante del informe de ROI anterior es que los &quot;ingresos de la canalización&quot; se representan dentro del cuadro rojo. Esto significa que de los 12.970 dólares invertidos en los últimos 3 meses completos, actualmente estamos atribuyendo 705.199 dólares de &quot;Ingresos&quot; ganados cerrados, pero también estamos atribuyendo 6.905.532 dólares de ingresos potenciales abiertos (&quot;Ingresos de tubería&quot;) a puntos de contacto creados a partir de la misma inversión. Lo que esperaríamos ver es que una parte de los &quot;ingresos de la canalización&quot; se cierre con el tiempo, alimentando el número &quot;ingresos&quot;, y por lo tanto, el número de ROI aumentaría con el tiempo. El número &quot;Gastar&quot; está fijo porque no podemos retroceder en el tiempo para gastar más en los últimos 3 meses completos. Esta es la importancia de utilizar un &quot;Tipo de fecha&quot; de &quot;Fecha de punto de contacto&quot; en cualquier informe de ROI: Define la cantidad (**I**)invertida y garantiza la cantidad de (**R**)los ingresos atribuidos se atribuyen de nuevo a los mismos puntos de contacto que se obtuvieron de la inversión (por cada dólar gastado, ¿cuánto se hizo?).

>[!TIP]
>
>Filtre en Canales de marketing, Subcanales o Campañas en los que sepa que los datos de gasto en marketing son completos y precisos. El ejemplo anterior es para todos los canales de marketing, pero si algunos canales no tienen cargados los datos de gasto en marketing relacionados, los informes de ROI podrían ser inexactos. Consulte el ejemplo siguiente, esta vez en el panel ROI, que se centra en las campañas dentro del canal de marketing de Búsqueda de pago, un canal con datos de gasto en marketing muy granulares a través de las integraciones.

![](assets/bizible-reporting-guide-7.png)
