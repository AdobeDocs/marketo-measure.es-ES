---
unique-page-id: 37356027
description: "[!DNL Marketo Measure] Integración sin paquetes CRM - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Integración sin paquetes CRM"
exl-id: a4f31d82-63ec-4bb2-bc8b-d3495e61af4f
feature: Integration
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 1%

---

# Integración sin paquetes CRM de [!DNL Marketo Measure] {#marketo-measure-crm-packageless-integration}

No todos los equipos de marketing desean (o tienen acceso) ejecutar informes de marketing desde CRM, ya sea debido a un acceso limitado, a la propiedad de CRM, a un tiempo de respuesta más largo o a implicaciones legales. Siguiendo el camino de [!DNL Marketo Measure] Inicio rápido le permite implementar y ejecutar de forma eficaz [!DNL Marketo Measure] con la menor dependencia posible del CRM.

## Standard [!DNL Marketo Measure] Instalación {#standard-marketo-measure-installation}

A través de la norma [!DNL Marketo Measure] instalación, es necesario que instale un [!DNL Salesforce] Paquete o un [!DNL Microsoft Dynamics] Solución administrada. La instalación incluye objetos/entidades personalizados y campos personalizados que se añaden al CRM [!DNL Marketo Measure] a continuación, puede escribir datos en.

Una integración sin paquetes con [!DNL Marketo Measure] es para clientes que no desean crear objetos/entidades personalizados o campos personalizados en su CRM. También es una buena opción para los clientes que utilizan una Data Warehouse externa.

## Permisos {#permissions}

A [!DNL Marketo Measure] La integración sin paquetes de CRM aún requiere acceso a objetos CRM estándar, como posibles clientes y contactos. Se recomienda que un usuario dedicado actúe como el usuario conectado, ya que dispone de los privilegios adecuados de acceso a los datos.

Para garantizar que todos los datos se extraen correctamente de su CRM, se requiere la siguiente configuración de seguridad y accesibilidad: Ver todos los datos del perfil del usuario dedicado. Este conjunto de permisos proporciona [!DNL Marketo Measure] el acceso necesario para descargar datos de objetos estándar. Este conjunto de permisos se encuentra en el nivel de perfil.

## Configuración del proveedor de identidad y las conexiones de datos {#setup-your-identity-provider-and-data-connections}

En las guías siguientes, omita los pasos para instalar el [!DNL Salesforce] paquete o [!DNL Microsoft Dynamics] Solución administrada y siga solo las instrucciones de permisos e integración.

[!DNL Salesforce] clientes hacen clic en [aquí](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md).

[!DNL Microsoft Dynamics] clientes hacen clic en [aquí](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

Después de completar estos pasos, la integración debería estar operativa. Si tiene algún problema, póngase en contacto con su [!DNL Marketo Measure] representante o [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!NOTE]
>
>Si comienza con la variable [!DNL Marketo Measure] Integración sin paquetes de CRM: puede instalar el paquete de Salesforce o la solución administrada de Microsoft Dynamics más adelante.
