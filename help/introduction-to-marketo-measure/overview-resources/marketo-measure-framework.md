---
unique-page-id: 18874570
description: Marco de trabajo de Marketo Measure - Marketo Measure - Documentación del producto
title: Marco de trabajo de Marketo Measure
exl-id: fa6de27c-cdd2-4fd9-ac35-7286fe2752d8
feature: Fundamentals
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 62%

---

# Marco de trabajo de Marketo Measure {#marketo-measure-framework}

Obtenga más información sobre los cuatro componentes principales que conforman el marco de trabajo de Marketo Measure. Marketo Measure utiliza estas aplicaciones para rastrear, organizar y alojar datos, así como para proporcionar capacidades de generación de informes. Los cuatro componentes que componen el marco de trabajo de Marketo Measure son:

* JavaScript de Marketo Measure
* Integraciones de CRM
* Aplicaciones/sistemas de terceros
* Aplicación Marketo Measure

## JavaScript de Marketo Measure {#marketo-measure-javascript}

El JavaScript de Marketo Measure rastrea todas las interacciones de marketing en línea, también denominadas puntos de contacto, que los clientes potenciales o posibles clientes tienen con su organización. Se trata de un script personalizado que se agrega antes de la etiqueta de cierre (`</head>`) en todas las páginas del sitio web.

`<script type="text/javascript" src="//[cdn.bizible.com/scripts/bizible.js](http://cdn.bizible.com/scripts/bizible.js)" async=""></script>`

>[!NOTE]
>
>Para obtener instrucciones sobre cómo añadir el JS de Marketo Measure, [haga clic aquí](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md).

El JS de Marketo Measure captura datos de las visitas web (incluidas las visitas web anónimas), el tráfico general/navegación por páginas, las descargas de contenido y los envíos de formularios. Estos datos se insertan en su CRM y cada interacción de marketing se muestra como un punto de contacto.

## Integraciones de CRM {#crm-integrations}

Marketo Measure se integra con CRM para alojar y organizar todos los datos capturados por el JS de Marketo Measure. Actualmente, Marketo Measure tiene integraciones de API con dos CRM:

![](assets/1-2.png)

Al mostrar datos de Marketo Measure en su CRM, puede ver la información granular relacionada con cada punto de contacto y generar informes para comprender el rendimiento de sus canales.

## Aplicaciones de terceros {#third-party-applications}

La mayoría de los expertos en marketing utilizan distintas aplicaciones para ejecutar sus esfuerzos de marketing. Además de Salesforce y MS Dynamics, Marketo Measure está integrado con 13 aplicaciones de terceros (enumeradas a continuación).

![](assets/2-1.png)

Si está ejecutando cualquier esfuerzo de marketing mediante las aplicaciones anteriores, puede vincular esas cuentas a su cuenta de Marketo Measure. Esto permite realizar un seguimiento y transferir fácilmente los datos a su cuenta de Marketo Measure.

## Aplicación Marketo Measure {#marketo-measure-application}

La aplicación Marketo Measure se utiliza para ver los datos de atribución y elaborar informes al respecto, configurar los ajustes de la cuenta y actualizar la información de la cuenta. Entre los elementos de menú principales de la aplicación Marketo Measure se incluyen:

**Configuración de la cuenta**

Aquí puede actualizar la información general de su empresa y acceder a Javascript de Marketo Measure.

**Configuración**

Este elemento de menú le permite configurar los ajustes de atribución y asignación de canales, administrar las integraciones con CRM y aplicaciones de terceros, ver/agregar usuarios de cuenta de Marketo Measure y actualizar la información de facturación.

**Tablero de ROI de marketing**

El elemento de menú del panel ROI de marketing es donde puede visualizar los datos en términos de rendimiento de canal, actividad y coste.
