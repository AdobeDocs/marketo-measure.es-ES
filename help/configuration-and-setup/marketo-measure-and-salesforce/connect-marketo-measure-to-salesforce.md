---
description: Directrices de Connect Marketo Measure to Salesforce para usuarios de Marketo Measure
title: Conectar Marketo Measure a Salesforce
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
feature: Salesforce
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 1%

---

# Conectar Marketo Measure a Salesforce {#connect-marketo-measure-to-salesforce}

Este artículo proporciona información general sobre cómo conectar la cuenta de [!DNL Salesforce] a la cuenta de [!DNL Marketo Measure].

## Conectando [!DNL Marketo Measure] con [!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. Use un explorador de incógnito para iniciar sesión en [!DNL Marketo Measure].

1. En la barra de menús de la parte superior de la pantalla, ve a **[!UICONTROL Mi cuenta]** y haz clic en la opción **[!UICONTROL Configuración]**.

1. En la columna de opciones de configuración de la izquierda, haga clic en **[!UICONTROL Conexiones]** ubicadas en la sección [!UICONTROL Integraciones].

   ![](assets/bizible-full-1.png)

1. En la sección CRM de Conexiones, haga clic en **[!UICONTROL Configurar nueva conexión CRM]**.

   ![](assets/bizible-taxonomy-1.png)

1. Aparece una ventana emergente que le pide que seleccione una conexión CRM. Haga clic en **[!UICONTROL Conectar]** junto al logotipo de [!DNL Salesforce].

   ![](assets/connect-salesforce-1.png)

1. Aparece una última ventana emergente que le pide sus credenciales de [!DNL Salesforce], su zona protegida o su producción. Escriba su información y haga clic en **[!UICONTROL Autorizar]** para conectar la cuenta a [!DNL Marketo Measure].

>[!NOTE]
>
>[!DNL Marketo Measure] solo se puede conectar a una instancia de [!DNL Salesforce] a la vez.
>
>* Se puede conectar una instancia de [!DNL Marketo Measure] a una instancia de zona protegida de SFDC para probar la integración antes de cambiar la conexión a la instancia de producción de SFDC.
>* Si realiza la prueba primero con una zona protegida de SFDC, le recomendamos encarecidamente que realice la prueba con una que sea una réplica exacta de la instancia de producción de SFDC en términos de campos de los objetos Posible cliente, Contacto, Cuenta, Oportunidad, Campaña y Caso. Si tiene déclencheur APEX activos en producción que se activan al actualizar los objetos de posible cliente, contacto, cuenta, oportunidad, campaña y caso, debe intentar tenerlos activos en su zona protegida.
>* Una vez que haya terminado la prueba, actualice su cuenta de [!DNL Marketo Measure] para que apunte a su [!DNL Salesforce] de producción (en lugar de a la zona protegida [!DNL Salesforce]). Debido a la forma en que se creó la integración, una vez que una cuenta de [!DNL Marketo Measure] esté conectada a la producción [!DNL Salesforce], no podrá retroceder y conectarse a una organización de espacio aislado [!DNL Salesforce].

## Uso de créditos de API {#api-credits-usage}

Marketo Measure emplea una tarea de integración de CRM para interactuar con el Salesforce de un cliente a través de un usuario integrado. Todos los intercambios de datos a través de este usuario utilizan créditos de la API de Salesforce. Tiene la capacidad de asignar una cuota de crédito a un usuario de integración, lo que sirve para regular llamadas de API excesivas. Esta cuota o límite se restablece cada 24 horas.

Puede acceder a este límite en Marketo Measure a través de: **Mi cuenta** > **Configuración** > **CRM** > **General** > **Límite diario de API de CRM**, y puede configurarlo para sus inquilinos.

![](assets/connect-salesforce-2.png)

### Configuración de un límite para créditos de API {#setting-a-limit-for-api-credits}

1. Vaya a **Mi cuenta** > **Configuración**.

1. En CRM, haga clic en **General**. Verá la opción **Límite diario de API de CRM**.

1. Haga clic en el icono Bloquear para editarlo.

   ![](assets/connect-salesforce-3.png)

1. Introduzca un límite deseado igual o superior a 100 000. Haga clic en **Guardar** cuando termine.

   ![](assets/connect-salesforce-1.png)

>[!NOTE]
>
>Para aumentar los créditos de la API de Salesforce disponibles para su solución conectada, póngase en contacto con su administrador de Salesforce y haga referencia a [este documento de Salesforce](https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm?lang=es){target="_blank"}.

>[!MORELIKETHIS]
>
>[Notificaciones de errores](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
