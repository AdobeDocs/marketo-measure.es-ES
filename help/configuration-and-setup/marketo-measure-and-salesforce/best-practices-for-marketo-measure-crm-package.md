---
description: Prácticas recomendadas para  [!DNL Marketo Measure] Paquete CRM - [!DNL Marketo Measure]
title: Prácticas recomendadas para el paquete CRM de  [!DNL Marketo Measure]
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 7%

---

# Prácticas recomendadas para el paquete CRM [!DNL Marketo Measure] {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>Puede que vea instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero seguirá viendo &quot;Bizible&quot; en su CRM. Se ha actualizado y el cambio de marca se reflejará próximamente en su CRM.

## Información general {#overview}

[!DNL Marketo Measure] se integra con [!DNL Salesforce] y [!DNL Microsoft Dynamics], este documento se centra en las prácticas recomendadas de [!DNL Marketo Measure] para los paquetes CRM diseñados para [!DNL Salesforce].

Durante la implementación, los dos paquetes siguientes se habrían instalado en la instancia de [!DNL Salesforce].

Paquete base: Este es el paquete base que incluye objetos y campos personalizados. Se recomienda instalar dentro de Producción para todos los usuarios.
Paquete de extensión de panel: este es nuestro paquete de extensión de panel, que contiene tres paneles creados previamente. Se recomienda instalar en el entorno de producción para todos los usuarios. Es opcional, pero se recomienda a los clientes que instalen.

Estos paquetes permiten a los usuarios de [!DNL Marketo Measure] acceder fácilmente a los datos de puntos de contacto a través de su instancia de [!DNL Salesforce]. Confirmar que estos paquetes están correctamente configurados es clave para comprobar que los diseños de página, los conjuntos de permisos, los informes y los paneles se presentan a los usuarios de [!DNL Marketo Measure] según lo esperado.

## Práctica recomendada {#best-practice}

Al implementar y administrar el paquete [!DNL Marketo Measure] [!DNL Salesforce], tenga en cuenta las siguientes prácticas recomendadas.

* Confirme que todos los integrantes del equipo necesarios tengan acceso a las carpetas de informes [!DNL Marketo Measure]. Debe haber entre 1 y 3 carpetas [!DNL Marketo Measure] (explicadas a continuación). Para abrir el acceso, la persona que instaló los paquetes debe compartir las carpetas de informes con los usuarios o roles correspondientes.
   * **Informes de Buyer Touchpoint** - disponibles para todos
   * **[!DNL Marketo Measure]informes de marketing basado en cuentas**: los informes solo se rellenarán para los clientes de nivel 2 o superior
   * **Paneles de Buyer Touchpoint**: disponible para todos, aunque este paquete es opcional.

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Aunque la configuración del paquete CRM se cubre durante la implementación inicial, se recomienda revisar la configuración del paquete CRM una vez al año. Esta revisión confirma que todos los diseños de página se han configurado correctamente y que todos los integrantes del equipo correspondiente tienen acceso a [!DNL Marketo Measure] informes y paneles.

Otras razones que podrían déclencheur una revisión...

* Adición de nuevos integrantes del equipo
* Actualizaciones en los diseños de página de [!DNL Salesforce]
* Migración de [!DNL Salesforce] Classic a Lighening
* Actualizaciones a su contrato de [!DNL Marketo Measure]
* Compruebe que tiene instalada la versión más reciente del paquete de puntos de contacto del comprador en [!DNL Salesforce]

>[!NOTE]
>
>Cuando deshabilita la exportación de datos de Marketo Measure a Salesforce, no se eliminará ningún dato existente. Para quitarlo, siga los pasos de [este artículo de ayuda de Salesforce](https://help.salesforce.com/s/articleView?language=en_US&id=sf.c360_a_delete_data_stream_records.htm&type=5){target="_blank"}.

>[!MORELIKETHIS]
>
>* [Actualizar paquete de Buyer Touchpoint](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure] Conjuntos de permisos](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [Carpeta para compartir informes y paneles](https://help.salesforce.com/s/articleView?language=en_US&id=analytics_share_folder.htm&type=0)
>* [Conectar Marketo Measure a Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)
