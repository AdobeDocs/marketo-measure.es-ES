---
description: Prácticas recomendadas para [!DNL Marketo Measure] Paquete CRM - [!DNL Marketo Measure] - Documentación del producto
title: Prácticas recomendadas para el paquete CRM de  [!DNL Marketo Measure]
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 6%

---

# Prácticas recomendadas para el paquete CRM de [!DNL Marketo Measure] {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero sigue viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

## Información general {#overview}

[!DNL Marketo Measure] se integra con ambos [!DNL Salesforce] y [!DNL Microsoft Dynamics], este documento se centrará en [!DNL Marketo Measure] prácticas recomendadas para los paquetes CRM diseñados para [!DNL Salesforce].

Durante la implementación, se habrían instalado los dos paquetes siguientes en su [!DNL Salesforce] ejemplo.

Paquete base: Este es nuestro paquete base que incluye nuestros objetos y campos personalizados. Se recomienda instalar en producción para todos los usuarios.
Paquete de extensión de panel: este es nuestro paquete de extensión de panel, que contiene 3 paneles creados previamente. Se recomienda instalar en producción para todos los usuarios. Es opcional, pero se recomienda a los clientes que instalen.

Estos paquetes permiten que su [!DNL Marketo Measure] para acceder fácilmente a los datos de puntos de contacto a través de su [!DNL Salesforce] ejemplo. La confirmación de que estos paquetes están correctamente configurados será fundamental para verificar que los diseños de página, los conjuntos de permisos, los informes y los paneles se presentan a su [!DNL Marketo Measure] usuarios según lo esperado.

## Práctica recomendada {#best-practice}

Cuando se trata de implementar y administrar su [!DNL Marketo Measure] [!DNL Salesforce] Paquete, tenga en cuenta las siguientes prácticas recomendadas.

* Confirme que todos los integrantes del equipo necesarios tengan acceso a. [!DNL Marketo Measure] carpetas de informes. Debe haber una resistencia de 1-3 [!DNL Marketo Measure] carpetas (se explican a continuación). Para abrir el acceso, la persona que instaló los paquetes debe compartir las carpetas del informe con los usuarios o las funciones correspondientes.
   * **Informes Touchpoint del comprador** - disponible para todo el mundo
   * **[!DNL Marketo Measure]Informes de marketing basado en cuentas** : los informes solo se rellenarán para clientes de nivel 2 o superior
   * **Paneles de Touchpoint del comprador** - disponible para todos, aunque este paquete es opcional.

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Aunque la configuración del paquete CRM se cubre durante la implementación inicial, le recomendamos que revise la configuración de su paquete CRM una vez al año. Esta revisión confirmará que todos los diseños de página están correctamente configurados y que todos los integrantes del equipo correspondientes tienen acceso a [!DNL Marketo Measure] informes y paneles.

Otras razones que podrían déclencheur una revisión...

* Adición de nuevos integrantes del equipo
* Actualizaciones para usted [!DNL Salesforce] diseños de página
* Migración para [!DNL Salesforce] Clásico a Iluminación
* Actualizaciones en su [!DNL Marketo Measure] contraer
* Comprueba que tienes instalada la última versión de nuestro Paquete de puntos de contacto para compradores en [!DNL Salesforce]

>[!NOTE]
>
>Cuando deshabilita la exportación de datos de Marketo Measure a Salesforce, no se eliminan los datos existentes. Para eliminarlo, siga los pasos que se detallan en [este artículo de ayuda de Salesforce](https://help.salesforce.com/s/articleView?id=sf.c360_a_delete_data_stream_records.htm&amp;type=5){target="_blank"}.

>[!MORELIKETHIS]
>
>* [Actualizar el paquete Touchpoint del comprador](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* Conjuntos de permisos de [[!DNL Marketo Measure] ](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [Compartir la carpeta de informes y paneles](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0)
>* [Conectar Marketo Measure a Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)
