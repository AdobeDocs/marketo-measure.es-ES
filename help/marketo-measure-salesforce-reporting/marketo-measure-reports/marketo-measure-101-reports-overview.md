---
description: "[!DNL Marketo Measure] 101 Información general sobre los informes [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] 101 Información general sobre los informes"
exl-id: 83977b81-8055-47fd-8a6b-5ef32d280269
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 0%

---

# [!DNL Marketo Measure] Información general sobre los informes 101 {#marketo-measure-101-reports-overview}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero aún así ver &quot;Bizible&quot; en su CRM. Estamos trabajando para que esto se actualice y el cambio de marca se reflejará pronto en su CRM.

Todo [!DNL Marketo Measure] clientes que utilizan [!DNL Marketo Measure] y [!DNL Salesforce] tienen acceso a la carpeta &quot;Informes de puntos de contacto del comprador&quot; dentro de su instancia de SFDC. Esta carpeta contiene varios informes pregenerados que pueden ayudarle a empezar a crear informes con los datos de punto de contacto del comprador.

![](assets/bizible-101-reports-overview-1.png)

Si bien muchos de estos informes ya tienen metas específicas de presentación de informes establecidas, hay seis._[!DNL Marketo Measure]101..._&quot; representado por tres tipos de informes clave que cubren la mayoría de las necesidades de informes.

* Posibles clientes con puntos de contacto del comprador
* [!DNL Marketo Measure] Personas con puntos de contacto de comprador
* Puntos de contacto de atribución de comprador con oportunidades

![](assets/bizible-101-reports-overview-2.png)

Estos informes le proporcionan los campos básicos y la infraestructura necesaria para cualquier [!DNL Marketo Measure] informe relacionado que desea crear. Recomendamos a todos los clientes, tanto nuevos como antiguos, que empiecen con estos informes al explorar las preguntas de atribución de marketing. A continuación encontrará una explicación de cada uno de los seis &quot;_[!DNL Marketo Measure]101..._&quot;.

_Si no encuentra la carpeta Informe de puntos de contacto del comprador o los seis_[!DNL Marketo Measure] 101..._&quot; dentro de esa carpeta, póngase en contacto con el servicio de soporte técnico para obtener ayuda._

**Posibles clientes con puntos de contacto del comprador** | Las dos variaciones siguientes, informan sobre posibles clientes y sus puntos de contacto de compradores. Aunque utilizan el mismo tipo de informe base, se agrupan por métricas diferentes, ID de posible cliente o Canal de marketing, para proporcionar dos vistas clave de los datos. Este tipo de informe está diseñado para los informes de canal superior y es ideal cuando desea explorar cómo sus posibles clientes están interactuando con sus esfuerzos de marketing. Antes de cualquier personalización, los dos informes siguientes muestran lo siguiente:

**[!DNL Marketo Measure]101: Posibles clientes por canal** | Una vista de alto nivel de cómo sus canales de marketing están influyendo en la creación de posibles clientes y sus compromisos adicionales.
**[!DNL Marketo Measure]101: Posibles clientes por ID** | Muestra el artículo Posibles clientes y es un informe mucho más granular que muestra cada posible cliente y sus puntos de contacto de compradores relacionados.

**Posibles clientes/contactos con puntos de contacto del comprador** | Estos informes suelen denominarse [!DNL Marketo Measure] Informes de personas. Utilizan el [!DNL Marketo Measure] objeto personalizado _[!DNL Marketo Measure]Persona_ a diferencia del objeto Lead en los informes mencionados anteriormente.

La variable [!DNL Marketo Measure] El objeto Persona relaciona los objetos Posible cliente y Contacto. Fuera de la caja, [!DNL Salesforce] no proporciona la opción de crear informes utilizando el objeto posible cliente y contacto en el mismo informe. Al relacionar el posible cliente y el objeto de contacto con el identificador único de una persona, su correo electrónico, la variable [!DNL Marketo Measure] Las personas pueden informar sobre los puntos de contacto del cliente potencial y del comprador relacionado con el contacto dentro del mismo informe. Este tipo de informe es ideal cuando se busca validar cualquiera de los [!DNL Marketo Measure] Configuración de la cuenta, ya que es el nivel más inclusivo de informes de puntos de contacto.

Las dos variaciones de informe siguientes utilizan el mismo tipo de informe, pero se agrupan por métricas diferentes, ID de persona (correo electrónico) y Canal de marketing. Estos son los principales informes de canal/medio de canal que son buenos cuando desea explorar cómo sus posibles clientes y contactos están interactuando con sus esfuerzos de marketing. Antes de cualquier personalización, los dos informes siguientes muestran lo siguiente:

**[!DNL Marketo Measure]101: Posibles clientes/contactos por canal** | Una vista de alto nivel de cómo sus canales de marketing están influyendo en la creación de posibles clientes o contactos y sus compromisos adicionales. Este informe es ideal para comprender la participación total en los canales de marketing y qué canales de marketing están generando nuevos nombres dentro de la instancia de Salesforce.
**[!DNL Marketo Measure]101: Posibles clientes/contactos por ID** | Muestra cada [!DNL Marketo Measure] El artículo de la persona y es un informe mucho más granular, que muestra a cada individuo y sus puntos de contacto de comprador, independientemente de si el punto de contacto se produjo cuando eran un posible cliente o como un contacto.

**Oportunidades con puntos de contacto de atribución del comprador** | Los dos últimos &quot;_[!DNL Marketo Measure]101..._&quot; son los informes de canal que muestran los datos de Touchpoint de atribución de Comprador relacionados con Oportunidades. El diferenciador clave para estos informes es que están construidos a partir de _Puntos de contacto de atribución del comprador_ que están relacionadas con los datos de nivel de oportunidad y oportunidad, como los ingresos. Siempre que desee informar sobre Oportunidades o ingresos atribuidos, debe utilizar este tipo de informe. Los dos informes siguientes utilizan el mismo tipo de informe; sin embargo, se agrupan por métricas diferentes, ID de oportunidad o Canal de marketing. Antes de cualquier personalización, los dos informes siguientes muestran lo siguiente:

**[!DNL Marketo Measure]101: Oportunidades por canal** | Una vista de alto nivel de cómo sus canales de marketing están influyendo e impulsando los ingresos atribuidos en sus oportunidades.
**[!DNL Marketo Measure]101: Oportunidades por ID** | Esta versión granular del informe muestra el recorrido completo de sus Oportunidades. En este informe puede ver cada punto de contacto de atribución de comprador asociado a una oportunidad y sus ingresos atribuidos a través de los distintos modelos de atribución.

Se considera una práctica recomendada tratar el &quot;_[!DNL Marketo Measure]101..._&quot; como plantillas para sus necesidades de creación de informes. Comenzando con uno de los informes anteriores, ahorrará tiempo y se asegurará de que está trabajando con los campos correctos relacionados con [!DNL Marketo Measure] datos. Asegúrese siempre de &quot;Guardar como&quot; cada vez que realice personalizaciones de &quot;_[!DNL Marketo Measure]101..._&quot; para conservar la variación original del informe.

La carpeta &quot;Informes de puntos de contacto del comprador&quot; está diseñada para ayudarle a empezar con su [!DNL Marketo Measure] informes, para los informes procesables deberá personalizar dichos informes de modo que se adapten a sus necesidades. Deberá agregar los filtros necesarios para garantizar que los registros del informe (y sus puntos de contacto relacionados) estén alineados con el objetivo de informes.

Una vez que esté familiarizado con el &quot;_[!DNL Marketo Measure]101..._&quot;, es posible que desee volver a crearlos a partir de tipos de informes personalizados para satisfacer sus necesidades. Creación de la variable [[!DNL Marketo Measure] Tipos de informes personalizados](/help/marketo-measure-salesforce-reporting/new-report-types/creating-custom-marketo-measure-report-types.md) le permitirá extraer campos personalizados que podría utilizar con frecuencia en otros informes de CRM. Esto le ayudará a llevar [!DNL Marketo Measure] informe al siguiente nivel!
