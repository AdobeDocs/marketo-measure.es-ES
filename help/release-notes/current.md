---
description: Documentación del producto  [!DNL Marketo Measure] , notas de la versión actual
title: Notas de la versión actual
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 40cd00c8edeb04c1939db9402d537d4c0e7a3406
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 61%

---

# Notas de la versión: 2023 {#release-notes-2023}

A continuación, encontrará todas las funciones nuevas y actualizadas de nuestras versiones de 2023.

## Versión del cuarto trimestre {#q4-release}

<p>

**Tablero de tráfico web**

El recién rediseñado [Panel de tráfico web](/help/marketo-measure-discover-ui/dashboards/web-traffic-dashboard.md){target="_blank"} ahora es accesible para todos los clientes. Este tablero ofrece una descripción general completa de las interacciones del visitante del sitio web. Puede analizar métricas como los recuentos de visitantes únicos por URL, las visitas generales, las vistas de página y los envíos de formularios desde direcciones URL de formularios o páginas de aterrizaje específicos. También puede realizar un seguimiento de las tendencias de tráfico mensuales e identificar medios de pago de alto rendimiento, lo que le ayudará a refinar sus estrategias para una óptima generación de ingresos.

Está previsto que el nuevo conjunto de paneles pregenerados se introduzca en olas y finalice antes de finales de año.

>[!NOTE]
>
>Aunque los paneles actuales quedarán obsoletos a mediados de enero de 2024, puede utilizar ambas versiones hasta entonces, lo que garantiza una transición sin problemas.

**Eliminación de datos de direcciones IP**

Estamos eliminando los datos de direcciones IP de nuestro almacenamiento a largo plazo para garantizar el cumplimiento de la privacidad de datos. Actualmente, las siguientes tablas y vistas de Snowflake contienen direcciones IP, y tenemos previsto eliminar estos datos y añadir nueva información de geolocalización:

<table style="width:400px">
<thead>
  <tr>
    <th style="width:50%">Tablas</th>
    <th>Vistas</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>CUSTOMER_AB_TESTS</td>
    <td>BIZ_CUSTOMER_AB_TESTS</td>
  </tr>
  <tr>
    <td>CUSTOMER_EVENTS</td>
    <td>BIZ_CUSTOMER_EVENTS</td>
  </tr>
  <tr>
    <td>FORM_SUBMITS</td>
    <td>BIZ_FORM_SUBMITS</td>
  </tr>
  <tr>
    <td>IMPRESSIONS</td>
    <td>BIZ_IMPRESSIONS</td>
  </tr>
  <tr>
    <td>PAGE_VIEWS</td>
    <td>BIZ_PAGE_VIEWS</td>
  </tr>
  <tr>
    <td>SESIONES</td>
    <td>BIZ_SESSIONS</td>
  </tr>
  <tr>
    <td>ASIGNACIONES_HOST_WEB</td>
    <td>BIZ_WEB_HOST_MAPPINGS</td>
  </tr>
</tbody>
</table>

* A partir de ahora, descargaremos Código de país, Nombre de ciudad y Código de región en lugar de Nombre de país, Nombre de ciudad y Nombre de región.
* Durante el procesamiento de todas las actividades web históricas, pueden surgir incoherencias en la información de ubicación entre registros. Estas incoherencias pueden incluir la presencia de direcciones IP sin detalles de geolocalización, información de geolocalización actualizada sin direcciones IP o una combinación de nombres y códigos de país o región.
* _**Se espera que este período de datos mixtos se produzca del 04/01/2023 al 29/02/2023.**_

**Datos de título de página en tabla de URL**

La tabla URL en la variable [data warehouse](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target="_blank"} ahora incluye un campo de título de página, además de tablas de datos web.

Tenga en cuenta que el título de página de la tabla URL puede no coincidir siempre con el título de página de otras tablas web. La tabla de URL contiene el título de la página más reciente. Si el título se ha cambiado para la URL después de que se haya realizado la actividad web, no coincidirá con lo que hay en la tabla de URL.

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

* **Degradaciones de campo de Salesforce**

Eliminaremos gradualmente nuestros trabajos de exportación a objetos de contacto/posible cliente para simplificar nuestra integración y eliminar la necesidad de exportar a objetos estándar de Salesforce. Los campos desnormalizados que se enumeran a continuación también quedarán obsoletos, ya que los clientes pueden obtener los mismos datos de sus objetos Touchpoint. _**El plazo para dejar de utilizar es junio de 2024.**_

<table style="width:300px">
<tbody>
  <tr>
    <td>bizible2__Ad_Campaign_Name_FT__c</td>
  </tr>
  <tr>
    <td>bizible2__Ad_Campaign_Name_LC__c</td>
  </tr>
  <tr>
    <td>bizible2__Landing_Page_FT__c</td>
  </tr>
  <tr>
    <td>bizible2__Landing_Page_LC__c</td>
  </tr>
  <tr>
    <td>bizible2__Touchpoint_Date_FT__c</td>
  </tr>
  <tr>
    <td>bizible2__Touchpoint_Date_LC__c</td>
  </tr>
  <tr>
    <td>bizible2__Touchpoint_Source_FT__c</td>
  </tr>
  <tr>
    <td>bizible2__Touchpoint_Source_LC__c</td>
  </tr>
  <tr>
    <td>bizible2__Marketing_Channel_FT__c</td>
  </tr>
  <tr>
    <td>bizible2__Marketing_Channel_LC__c</td>
  </tr>
</tbody>
</table>

* **Paquete de Dynamics relacionado**

   * Para mantenerse conectado a Dynamics, instale la última versión del paquete, 6.12. Versiones antiguas `(<v6.12)` ya no serán compatibles. Esta actualización optimiza la creación de registros históricos para reducir el uso del almacenamiento.

   * El método obsoleto de OAuth con un RefreshToken quedará obsoleto. Consulte [esta guía](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md){target="_blank"} para actualizar sus credenciales de modo que se ajusten a las prácticas recomendadas de Microsoft para utilizar ClientSecret.

* **Campo &quot;custom_properties&quot;**

En nuestro almacén de datos, el campo &quot;custom_properties&quot; ha servido como almacenamiento para puntos de datos adicionales que no están cubiertos por nuestro esquema fijo. Almacenado en formato JSON, el uso de este campo es limitado y su integración con consultas SQL puede ser complicada, lo que afecta al rendimiento. Dados estos factores, hemos decidido dejar este campo sin efecto. Este cambio afectará principalmente a la capa de procesamiento de datos dentro de nuestro almacenamiento de tablas de Azure y a los datos exportados a nuestro almacén de datos.

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
