---
description: '[!DNL Marketo Measure] integración sin paquetes CRM - [!DNL Marketo Measure]'
title: Integración sin paquetes CRM de [!DNL Marketo Measure]
exl-id: a4f31d82-63ec-4bb2-bc8b-d3495e61af4f
feature: Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 2%

---


# Integración sin paquetes CRM de [!DNL Marketo Measure] {#marketo-measure-crm-packageless-integration}

No todos los equipos de marketing desean (o tienen acceso) ejecutar informes de marketing desde CRM, ya sea debido a un acceso limitado, a la propiedad de CRM, a un tiempo de respuesta más largo o a implicaciones legales. Al seguir la ruta de Inicio rápido de [!DNL Marketo Measure], podrá implementar y ejecutar [!DNL Marketo Measure] de forma eficaz con la menor dependencia posible del CRM.

## Instalación estándar de [!DNL Marketo Measure] {#standard-marketo-measure-installation}

Mediante la instalación estándar de [!DNL Marketo Measure], es necesario que instale un paquete de [!DNL Salesforce] o una solución administrada de [!DNL Microsoft Dynamics]. La instalación incluye objetos o entidades personalizados y campos personalizados que se agregan al CRM en el que [!DNL Marketo Measure] puede escribir datos.

Una integración sin paquetes con [!DNL Marketo Measure] es para clientes que no desean crear objetos, entidades o campos personalizados en su CRM. También es una buena opción para los clientes que utilizan un Data Warehouse externo.

## Permisos {#permissions}

Una integración sin paquetes de CRM [!DNL Marketo Measure] todavía requiere acceso a objetos de CRM estándar como posibles clientes y contactos. Se recomienda que un usuario dedicado actúe como el usuario conectado, ya que dispone de los privilegios adecuados de acceso a los datos.

Para garantizar que todos los datos se extraen correctamente de su CRM, se requiere la siguiente configuración de seguridad y accesibilidad: Ver todos los datos del perfil del usuario dedicado. Este conjunto de permisos concede a [!DNL Marketo Measure] el acceso necesario para descargar datos de objetos estándar. Este conjunto de permisos se encuentra en el nivel de perfil.

## Configuración del proveedor de identidad y las conexiones de datos {#setup-your-identity-provider-and-data-connections}

En las guías siguientes, omita los pasos para instalar el paquete [!DNL Salesforce] o la solución administrada [!DNL Microsoft Dynamics] y siga solamente las instrucciones de permisos e integración.

[!DNL Salesforce] clientes hacen clic [aquí](/help/configuration-and-setup/install-set-up.md).

[!DNL Microsoft Dynamics] clientes hacen clic [aquí](/help/microsoft-dynamics-crm-installation-guide.md).

Después de completar estos pasos, la integración debería estar operativa. Si encuentra algún problema, comuníquese con su representante de [!DNL Marketo Measure] o con el [Soporte técnico de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!NOTE]
>Si comienza con la integración sin paquetes de [!DNL Marketo Measure] CRM, podrá instalar el paquete de Salesforce o la solución administrada de Microsoft Dynamics más adelante.
