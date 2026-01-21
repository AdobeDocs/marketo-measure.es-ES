---
description: '[!DNL Marketo Measure] 101 Información general de informes - [!DNL Marketo Measure]'
title: Información general sobre los informes 101 de [!DNL Marketo Measure]
exl-id: 83977b81-8055-47fd-8a6b-5ef32d280269
feature: Reporting
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 5%

---

# Información general sobre los informes 101 de [!DNL Marketo Measure] {#marketo-measure-101-reports-overview}

>[!NOTE]
>
>Puede que vea instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero seguirá viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

Todos los clientes de [!DNL Marketo Measure] que usan [!DNL Marketo Measure] y [!DNL Salesforce] tienen acceso a la carpeta &quot;Informes de puntos de contacto del comprador&quot; en su instancia de SFDC. Esta carpeta contiene varios informes creados previamente que pueden ayudarle a empezar a crear informes con datos de Buyer Touchpoint.

![](assets/bizible-101-reports-overview-1.png)

Aunque muchos de estos informes ya tienen establecidos objetivos específicos de generación de informes, existen seis &quot;_[!DNL Marketo Measure]101..._&quot; representados por tres tipos de informes clave que cubren la mayoría de las necesidades de generación de informes.

* Posibles clientes con puntos de contacto del comprador
* [!DNL Marketo Measure] personas con puntos de contacto de comprador
* Puntos de contacto de atribución de comprador con oportunidades

![](assets/bizible-101-reports-overview-2.png)

Estos informes le proporcionan los campos básicos y la infraestructura necesaria para cualquier informe relacionado con [!DNL Marketo Measure] que desee crear. Recomendamos a todos los clientes, tanto nuevos como antiguos, que empiecen con estos informes cuando exploren las preguntas de atribución de marketing. A continuación encontrará una explicación de cada uno de los seis informes &quot;_[!DNL Marketo Measure]101..._&quot;.

_Si no encuentra la carpeta Informe de puntos de contacto del comprador o los seis informes &quot;_[!DNL Marketo Measure] 101..._&quot; que contiene esa carpeta, póngase en contacto con el servicio de asistencia para obtener ayuda._

**Posibles clientes con puntos de contacto del comprador** | Las dos variaciones siguientes informan sobre los posibles clientes y sus puntos de contacto del comprador. Aunque utilizan el mismo tipo de informe base, se agrupan por distintas métricas, ID de posible cliente o canal de marketing, para proporcionar dos vistas clave de los datos. Este tipo de informe está diseñado para los informes principales de funnel y es ideal cuando desea explorar cómo los posibles clientes interactúan con los esfuerzos de marketing. Antes de cualquier personalización, los dos informes siguientes muestran lo siguiente:

**[!DNL Marketo Measure]101: Posibles clientes por canal** | Una vista de alto nivel de cómo los canales de marketing influyen en la creación de posibles clientes y en sus participaciones adicionales.
**[!DNL Marketo Measure]101: posibles clientes por id.** | Muestra la historia de posibles clientes y es un informe mucho más granular que muestra cada posible cliente individual y los puntos de contacto del comprador relacionados.

**Posibles clientes/contactos con puntos de contacto del comprador** | Estos informes se denominan comúnmente informes de [!DNL Marketo Measure] personas. Utilizan el objeto personalizado [!DNL Marketo Measure] _[!DNL Marketo Measure]persona_ en lugar del objeto de posible cliente de los informes mencionados anteriormente.

El Objeto Persona de [!DNL Marketo Measure] relaciona los objetos Posible cliente y Contacto. De serie, [!DNL Salesforce] no proporciona la opción de crear informes utilizando el objeto de posible cliente y contacto en el mismo informe. Al relacionar el cliente potencial y el objeto de contacto mediante el identificador único de una persona, su correo electrónico, la persona [!DNL Marketo Measure] puede generar informes sobre los puntos de contacto del comprador relacionados con el cliente potencial y el contacto dentro del mismo informe. Este tipo de informe es ideal cuando desea validar cualquiera de los ajustes de cuenta de [!DNL Marketo Measure], ya que es el nivel más inclusivo de creación de informes de puntos de contacto.

Las dos variaciones de informes siguientes utilizan el mismo tipo de informe, pero se agrupan por distintas métricas, ID de persona (correo electrónico) frente a canal de marketing. Estos son los informes principales/secundarios de funnel de funnel que son ideales para explorar cómo los posibles clientes y contactos se relacionan con los esfuerzos de marketing. Antes de cualquier personalización, los dos informes siguientes muestran lo siguiente:

**[!DNL Marketo Measure]101: posible cliente/contactos por canal** | Una vista de alto nivel de cómo los canales de marketing influyen en la creación de posibles clientes o contactos y en sus participaciones adicionales. Este informe es ideal para comprender la participación total en los canales de marketing y en los canales de marketing que están generando nuevos nombres en la instancia de Salesforce.
**[!DNL Marketo Measure]101: posible cliente/contactos por id.** | Esto muestra la historia de cada persona [!DNL Marketo Measure] y es un informe mucho más granular que muestra a cada individuo y sus puntos de contacto de comprador, independientemente de si el punto de contacto se produjo cuando era un posible cliente o como contacto.

**Oportunidades con puntos de contacto de atribución de comprador** | Los dos últimos informes &quot;_[!DNL Marketo Measure]101..._&quot; se encuentran en la parte inferior de los informes de funnel que muestran los datos de Buyer Attribution Touchpoint relacionados con las oportunidades. El principal elemento diferenciador de estos informes es que se basan en _Puntos de contacto de atribución del comprador_ que están relacionados con los datos de nivel de oportunidad y oportunidad, como los ingresos. Siempre que busque informar sobre Oportunidades o ingresos atribuidos, se debe utilizar este tipo de informe. Los dos informes siguientes utilizan el mismo tipo de informe; sin embargo, se agrupan por distintas métricas, ID de oportunidad o canal de marketing. Antes de cualquier personalización, los dos informes siguientes muestran lo siguiente:

**[!DNL Marketo Measure]101: Oportunidades por canal** | Una vista de alto nivel de cómo los canales de marketing influyen en los ingresos atribuidos a través de las oportunidades y los impulsan.
**[!DNL Marketo Measure]101: Oportunidades por identificador** | Esta versión pormenorizada del informe muestra el recorrido completo de las oportunidades. En este informe puede ver todas las Buyer Attribution Touchpoint asociadas a una oportunidad y sus ingresos atribuidos a través de los distintos modelos de atribución.

Se considera una práctica recomendada tratar los informes &quot;_[!DNL Marketo Measure]101..._&quot; como plantillas para sus necesidades de creación de informes. Comenzar con uno de los informes anteriores le ahorrará tiempo y le garantizará que está trabajando con los campos correctos relacionados con los datos de [!DNL Marketo Measure]. Asegúrese siempre de &quot;Guardar como&quot; siempre que realice personalizaciones en las plantillas &quot;_[!DNL Marketo Measure]101..._&quot; para conservar la variación original del informe.

La carpeta &quot;Informes de Buyer Touchpoint&quot; está diseñada para ayudarle a empezar con sus informes de [!DNL Marketo Measure]; en el caso de los informes procesables, deberá personalizar dichos informes de modo que se adapten a sus necesidades. deberá añadir los filtros necesarios para garantizar que los registros del informe (y sus puntos de contacto relacionados) estén alineados con el objetivo de la creación de informes.

Si está familiarizado con los informes &quot;_[!DNL Marketo Measure]101..._&quot;, quizá desee volver a crearlos a partir de los tipos de informes personalizados para satisfacer sus necesidades de creación de informes más personalizadas. Crear los [[!DNL Marketo Measure] tipos de informes personalizados](/help/marketo-measure-salesforce-reporting/new-report-types/creating-custom-marketo-measure-report-types.md) le permitirá extraer campos personalizados que podría usar comúnmente en otros informes de CRM. Esto le ayudará a llevar los informes de [!DNL Marketo Measure] al siguiente nivel.
