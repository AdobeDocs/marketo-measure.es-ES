---
description: Notas de la versión actual - [!DNL Marketo Measure] - Documentación del producto
title: Notas de la versión actual
source-git-commit: 8e8ddd80d69102455fa678a32f31a9fe8319822c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Notas de la versión: 2023 {#release-notes-2023}

A continuación encontrará todas las funciones nuevas y actualizadas de nuestras versiones de 2023.

## Versión del segundo trimestre {#q2-release}

<p>

**Consolidación de paquetes de Salesforce**

* Estamos combinando todos los paquetes de Salesforce en un único paquete completo para mejorar la experiencia del usuario y simplificar el uso. Los paquetes V1, V2_EXT y Reporting se retirarán el próximo trimestre. El nuevo paquete combina todas las funciones anteriores, lo que permite un seguimiento más eficaz y perspectivas más profundas para los clientes.
* Los clientes que ya tengan instalado el paquete V2 deben actualizarlo a la nueva versión consolidada.
* Hemos agregado dos campos nuevos para mejorar sus capacidades de creación de informes:
   * form_name: Ahora disponible en objetos BT/BAT, este campo permite a los usuarios crear informes basados en nombres de formulario.
   * user_touchpoint_id: Este campo permite a los usuarios crear informes con recuentos de puntos de contacto de usuario únicos.
* [Este artículo](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} incluye guías para recrear informes y tableros de los paquetes de informes heredados.

**Actualizaciones de la versión de la API de Salesforce**

* Todas las versiones de API de Salesforce de las clases Apex, incluida la clase UserActivityContext, se actualizan a versiones compatibles. (31.0 a 57.0)

**Nueva instalación del paquete**

* El nuevo enlace de instalación del paquete consolidado [se puede encontrar aquí](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### ¿Qué viene? {#whats-coming}

<p>

**Cambios en el almacenamiento de direcciones IP**

* Ya no almacenaremos direcciones IP en nuestro sistema por consideraciones de privacidad. Seguiremos identificando y almacenando la ubicación geográfica de la dirección IP, pero el formato cambiará (por ejemplo, &quot;Estados Unidos&quot; a &quot;EE.UU.&quot;).
