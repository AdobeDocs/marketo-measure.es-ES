---
description: Documentación del producto  [!DNL Marketo Measure] , notas de la versión actual
title: Notas de la versión actual
exl-id: 64b8fce8-af7d-4991-b01e-3fcf375d14e7
feature: Release Notes
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 100%

---

# Notas de la versión: 2023 {#release-notes-2023}

A continuación, encontrará todas las funciones nuevas y actualizadas de nuestras versiones de 2023.

## Versión del segundo trimestre {#q2-release}

<p>

**Consolidación de paquetes de Salesforce**

* Estamos combinando todos los paquetes de Salesforce en un único paquete completo para mejorar la experiencia del usuario y simplificar el uso. Los paquetes V1, V2_EXT y de creación de informes se retirarán el próximo trimestre. El nuevo paquete combina todas las funciones anteriores, lo que permite un seguimiento más eficiente y datos del cliente más detallados.
* Los clientes que ya tengan instalado la versión 2 del paquete deben actualizarlo a la nueva versión consolidada.
* Se han añadido dos campos nuevos para mejorar las funciones de creación de informes:
   * form_name: ahora disponible en objetos BT/BAT, este campo permite a los usuarios crear informes basados en nombres de formulario.
   * user_touchpoint_id: este campo permite a los usuarios crear informes con recuentos de puntos de contacto de usuario único.
* [Este artículo](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} incluye guías sobre cómo volver a crear informes y paneles a partir de los paquetes de informes heredados.

**Actualizaciones de versiones de API de Salesforce**

* Todas las versiones de la API de Salesforce de las clases Apex, incluida la clase UserActivityContext, se actualizan a versiones compatibles. (de 31.0 a 57.0)

**Instalación del nuevo paquete**

* El nuevo vínculo de instalación del paquete consolidado [se puede encontrar aquí](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### ¿Qué nos espera? {#whats-coming}

<p>

**Cambios en el almacenamiento de direcciones IP**

* Ya no almacenaremos direcciones IP en nuestro sistema por motivos de privacidad. Seguiremos identificando y almacenando la geolocalización de la dirección IP, pero el formato cambiará (por ejemplo, de “Estados Unidos” a “US”).
