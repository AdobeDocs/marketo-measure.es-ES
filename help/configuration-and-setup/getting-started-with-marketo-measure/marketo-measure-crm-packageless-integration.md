---
unique-page-id: 37356027
description: "[!DNL Marketo Measure] Integración sin paquetes CRM - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Integración sin paquetes CRM"
exl-id: a4f31d82-63ec-4bb2-bc8b-d3495e61af4f
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---

# [!DNL Marketo Measure] Integración sin paquetes CRM {#marketo-measure-crm-packageless-integration}

Entendemos que no todos los equipos de marketing desean (o tienen acceso) ejecutar informes de marketing desde CRM, ya sea por el acceso limitado, la propiedad de CRM, el tiempo de respuesta al valor más largo o las implicaciones legales. Bajar por el camino de [!DNL Marketo Measure] El inicio rápido le permite implementar y ejecutar de forma eficaz [!DNL Marketo Measure] con la menor dependencia posible de CRM.

## Estándar [!DNL Marketo Measure] Instalación {#standard-marketo-measure-installation}

A través del estándar [!DNL Marketo Measure] instalación, debe instalar un [!DNL Salesforce] Paquete o [!DNL Microsoft Dynamics] Solución administrada. La instalación incluye objetos/entidades personalizados y campos personalizados que se agregan al CRM que [!DNL Marketo Measure] a continuación, puede escribir datos en .

Una integración sin paquete con [!DNL Marketo Measure] es para clientes que no desean crear objetos/entidades personalizados o campos personalizados en su CRM. También es una buena opción para los clientes que utilizan un almacén de datos externo.

## Permisos {#permissions}

A [!DNL Marketo Measure] La integración sin paquetes CRM aún requiere acceso a objetos CRM estándar como posibles clientes y contactos. Recomendamos encarecidamente que un usuario dedicado actúe como usuario conectado, ya que tendrá los privilegios de acceso a los datos adecuados.

Para garantizar que todos los datos se extraigan correctamente de su CRM, necesitamos la siguiente configuración de seguridad y accesibilidad: Ver todos los datos para el perfil del usuario dedicado. Este conjunto de permisos proporciona [!DNL Marketo Measure] el acceso necesario para descargar datos de objetos estándar. Este conjunto de permisos se encuentra en el nivel de perfil.

## Configuración del proveedor de identidad y las conexiones de datos {#setup-your-identity-provider-and-data-connections}

En las guías siguientes, omita los pasos para instalar el [!DNL Salesforce] paquete o [!DNL Microsoft Dynamics] Solución administrada y siga solo los permisos y las instrucciones de integración.

[!DNL Salesforce] clientes, haga clic en [here](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md).

[!DNL Microsoft Dynamics] clientes, haga clic en [here](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

Una vez que complete todos los pasos anteriores, estará listo. Si tiene algún problema en el camino, no dude en ponerse en contacto con su [!DNL Marketo Measure] representante o [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}.

>[!NOTE]
>
>Si comienza con la variable [!DNL Marketo Measure] Integración sin paquetes CRM, podrá instalar más tarde el paquete de Salesforce o la solución administrada de Microsoft Dynamics.
