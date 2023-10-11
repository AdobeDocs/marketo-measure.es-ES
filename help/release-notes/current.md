---
description: Documentación del producto  [!DNL Marketo Measure] , notas de la versión actual
title: Notas de la versión actual
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: dc4fda07004398207fb5067eb42ecd9e8ffe8624
workflow-type: ht
source-wordcount: '536'
ht-degree: 100%

---

# Notas de la versión: 2023 {#release-notes-2023}

A continuación, encontrará todas las funciones nuevas y actualizadas de nuestras versiones de 2023.

## Versión del cuarto trimestre {#q4-release}

<p>

**Descubrir el rediseño de paneles**

Todos los usuarios de Marketo Measure experimentarán nuestros paneles en la aplicación rediseñados que combinan una mayor facilidad de uso con un valor añadido. También estamos introduciendo nuevas métricas, como &quot;ROI realizado&quot;, que tiene en cuenta el retraso típico entre las inversiones de marketing y las compras en los mercados de lanzamiento B2B.

Está previsto que el nuevo conjunto de paneles generados previamente se introduzca por olas, a partir de la primera semana de octubre hasta finales de año. Estos nuevos paneles aparecerán automáticamente en las instancias, junto con información interna del producto y vínculos a la documentación.

* [Nueva guía del panel Discover](/help/marketo-measure-discover-ui/dashboards/new-discover-dashboard-guide.md){target="_blank"}
* [Descubra los conceptos básicos del panel](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
* [Panel de información general sobre ingresos](/help/marketo-measure-discover-ui/dashboards/revenue-overview-dashboard.md){target="_blank"}
* [Panel de ingresos atribuidos](/help/marketo-measure-discover-ui/dashboards/attributed-revenue-dashboard.md){target="_blank"}
* [Panel de ROI ](/help/marketo-measure-discover-ui/dashboards/roi-dashboard.md){target="_blank"}
* [Panel de Passport](/help/marketo-measure-discover-ui/dashboards/passport-dashboard.md){target="_blank"}

>[!NOTE]
>
>Aunque los paneles actuales quedarán obsoletos a mediados de enero de 2024, puede utilizar ambas versiones hasta entonces, lo que garantiza una transición sin problemas.

### En desuso {#deprecations}

<p>

* **Campo &quot;custom_properties&quot;**

En nuestro almacén de datos, el campo &quot;custom_properties&quot; ha servido como almacenamiento para puntos de datos adicionales que no están cubiertos por nuestro esquema fijo. Almacenado en formato JSON, el uso de este campo es limitado y su integración con consultas SQL puede ser complicada, lo que afecta al rendimiento. Dados estos factores, hemos decidido dejar este campo sin efecto. Este cambio afectará principalmente a la capa de procesamiento de datos dentro de nuestro almacenamiento de tablas de Azure y a los datos exportados a nuestro almacén de datos.

* **Paquete de Dynamics relacionado**

   * Para mantenerse conectado a Dynamics, instale la última versión del paquete, 6.12. Versiones antiguas `(<v6.12)` ya no serán compatibles. Esta actualización optimiza la creación de registros históricos para reducir el uso del almacenamiento.

   * El método obsoleto de OAuth con un RefreshToken quedará obsoleto. Consulte [esta guía](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md){target="_blank"} para actualizar sus credenciales de modo que se ajusten a las prácticas recomendadas de Microsoft para utilizar ClientSecret.

### ¿Qué nos espera? {#q4-whats-coming}

<p>

**Creación de informes personalizados en la aplicación**

Los clientes de Marketo Measure, por primera vez, podrán crear y guardar sus propios informes directamente en la aplicación. Esto seguirá a la publicación de los paneles generados previamente a principios de 2024.

<br>

## Versión del segundo trimestre {#q2-release}

<p>

* **Consolidación de paquetes de Salesforce**

Estamos combinando todos los paquetes de Salesforce en un único paquete completo para mejorar la experiencia del usuario y simplificar el uso. Los paquetes V1, V2_EXT y de creación de informes se retirarán el próximo trimestre. El nuevo paquete combina todas las funciones anteriores, lo que permite un seguimiento más eficiente y datos del cliente más detallados.

Los clientes que ya tengan instalado la versión 2 del paquete deben actualizarlo a la nueva versión consolidada.

Se han añadido dos campos nuevos para mejorar las funciones de creación de informes:

* form_name: ahora disponible en objetos BT/BAT, este campo permite a los usuarios crear informes basados en nombres de formulario.
* user_touchpoint_id: este campo permite a los usuarios crear informes con recuentos de puntos de contacto de usuario único.

[Este artículo](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} incluye guías sobre cómo volver a crear informes y paneles a partir de los paquetes de informes heredados.

* **Actualizaciones de versiones de API de Salesforce**

Todas las versiones de la API de Salesforce de las clases Apex, incluida la clase UserActivityContext, se actualizan a versiones compatibles. (de 31.0 a 57.0)

* **Instalación del nuevo paquete**

El nuevo vínculo de instalación del paquete consolidado [se puede encontrar aquí](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### ¿Qué nos espera? {#q2-whats-coming}

<p>

**Cambios en el almacenamiento de direcciones IP**

Ya no almacenaremos direcciones IP en nuestro sistema por motivos de privacidad. Seguiremos identificando y almacenando la geolocalización de la dirección IP, pero el formato cambiará (por ejemplo, de “Estados Unidos” a “US”).
