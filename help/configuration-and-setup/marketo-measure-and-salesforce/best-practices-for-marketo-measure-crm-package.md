---
description: 'Prácticas recomendadas para [!DNL Marketo Measure] Paquete CRM: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para [!DNL Marketo Measure] Paquete CRM
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
source-git-commit: 00268f49ff6e5dfc105fa7ea21837375eae49647
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Prácticas recomendadas para [!DNL Marketo Measure] Paquete CRM {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero aún así ver &quot;Bizible&quot; en su CRM. Estamos trabajando para que esto se actualice y el cambio de marca se reflejará pronto en su CRM.

## Resumen {#overview}

[!DNL Marketo Measure] se integra con ambos [!DNL Salesforce] y [!DNL Microsoft Dynamics], este documento se centrará en la variable [!DNL Marketo Measure] prácticas recomendadas para los paquetes CRM diseñados para [!DNL Salesforce].

Durante la implementación, los dos paquetes siguientes se habrían instalado en su [!DNL Salesforce] instancia.

Paquete base: Este es nuestro paquete base que incluye nuestros objetos y campos personalizados. Se recomienda instalar en Producción para todos los usuarios.
Paquete de extensión del panel: Este es nuestro paquete de extensión de tablero, que contiene 3 tableros pregenerados. Se recomienda instalar en Producción para todos los usuarios. Esto es opcional, pero recomendamos a los clientes que lo instalen.

Estos paquetes habilitan su [!DNL Marketo Measure] usuarios para acceder fácilmente a los datos de touchpoint en todas sus [!DNL Salesforce] instancia. Confirmación de que estos paquetes están correctamente configurados será clave para verificar que los diseños de página, los conjuntos de permisos y los informes y tableros se presenten a su [!DNL Marketo Measure] usuarios como se esperaba.

## Práctica recomendada {#best-practice}

A la hora de implementar y administrar su [!DNL Marketo Measure] [!DNL Salesforce] Paquete, tenga en cuenta las siguientes prácticas recomendadas.

* Confirme que todos los miembros del equipo necesarios tienen acceso a la variable [!DNL Marketo Measure] carpetas de informes. Debe haber 1-3 [!DNL Marketo Measure] carpetas (se explican a continuación). Para abrir el acceso, la persona que instaló los paquetes debe compartir las carpetas de informes con los usuarios o las funciones correspondientes.
   * **Informes de puntos de contacto del comprador** - disponible para todos
   * **[!DNL Marketo Measure]Informes de marketing basados en cuentas** - los informes solo se rellenarán a los clientes de nivel 2 y superior
   * **Tableros de puntos de contacto del comprador** - disponible para todos, aunque este paquete es opcional.

## Práctica recomendada para mantenimiento {#best-practice-for-maintenance}

Aunque la configuración de su paquete CRM se cubre durante la implementación inicial, le recomendamos que revise la configuración de su paquete CRM una vez al año. Esta revisión confirmará que todos los diseños de página están correctamente configurados y que todos los integrantes del equipo adecuado tienen acceso a [!DNL Marketo Measure] informes y tableros.

Otras razones para ello podrían déclencheur una revisión...

* Adición de nuevos integrantes del equipo
* Actualizaciones [!DNL Salesforce] diseños de página
* Migración para [!DNL Salesforce] Classic a Lighing
* Actualizaciones a su [!DNL Marketo Measure] contrato
* Compruebe que tiene instalada la versión más reciente de nuestro Paquete de puntos de contacto de comprador en [!DNL Salesforce]

>[!NOTE]
>
>Al desactivar la exportación de datos de Marketo Measure a Salesforce, no se elimina ningún dato existente. Para eliminarlo, siga los pasos indicados en [este artículo de ayuda de Salesforce](https://help.salesforce.com/s/articleView?id=sf.c360_a_delete_data_stream_records.htm&amp;type=5){target="_blank"}.

>[!MORELIKETHIS]
>
>* [Actualizar paquete de puntos de contacto del comprador](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure] Conjuntos de permisos](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [Uso compartido de informes y tableros](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0)
>* [Conectar Marketo Measure a Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)

