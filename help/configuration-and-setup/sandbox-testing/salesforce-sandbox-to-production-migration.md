---
unique-page-id: 18874694
description: 'Migración del Simulador para pruebas de Salesforce a la producción: [!DNL Marketo Measure] - Documentación del producto'
title: Salesforce Sandbox to Production Migration
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Salesforce Sandbox to Production Migration {#salesforce-sandbox-to-production-migration}

Si elige probar [!DNL Marketo Measure] en un [!DNL Salesforce] Entorno de espacio aislado, siga estas instrucciones para migrar a Producción una vez que esté listo. Las siguientes instrucciones suponen que ya ha descargado el [!DNL Marketo Measure] en su organización de Sandbox, realizó las pruebas necesarias y está listo para insertar [!DNL Marketo Measure] a Producción.

## Paso 1: Instalar [!DNL Marketo Measure] Paquetes en la producción [!DNL Salesforce] Instancia {#install-marketo-measure-packages-into-your-production-salesforce-instance}

* Instale los dos [!DNL Marketo Measure] en Producción con el[!UICONTROL Todos los usuarios]&quot;

   * [Paquete base](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target=&quot;_blank&quot;}
   * [Paquete de extensión del panel](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t610000001jI6){target=&quot;_blank&quot;}

* Para obtener más información sobre la variable [!DNL Marketo Measure] relación con [!DNL Salesforce], eche un vistazo a [este artículo](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)
* Un poco de [!DNL Salesforce] es necesaria. Los elementos de acción específicos se describen a continuación en [Paso 4 a continuación](#salesforce-configuration)

## Paso 2: Eliminar la conexión actual de Sandbox CRM en [!DNL Marketo Measure] Aplicación {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* Inicie sesión en la [!DNL Marketo Measure] aplicación en experience.adobe.com/marketo-measure
* Vaya a Mi cuenta >[!UICONTROL Configuración] >[!UICONTROL Conexiones]
* Haga clic en el icono de papelera situado junto a la conexión SFDC para eliminar
* Se le pedirá que confirme la eliminación. Asegúrese de leer detenidamente y comprender las consecuencias de la eliminación

   ![](assets/salesforce-sandbox-to-production-migration-1.png)

   * Escriba el nombre de la empresa tal como se indica en el modelo de confirmación y haga clic en &quot;Entiendo las consecuencias, elimine esta conexión&quot;.
* Esto déclencheur el proceso de eliminación y tardará algún tiempo en completarse

## Paso 3: Conecte la instancia de Production CRM en [!DNL Marketo Measure] Aplicación {#connect-the-production-crm-instance-in-marketo-measure-app}

* Inicie sesión en la [!DNL Marketo Measure] aplicación en experience.adobe.com/marketo-measure
* Vaya a [!UICONTROL Mi cuenta] >[!UICONTROL Configuración] > [!UICONTROL Conexiones]
* Una vez que la eliminación de la conexión de espacio aislado se haya eliminado correctamente, la conexión desaparecerá de la página; de lo contrario, la conexión seguirá presente con el estado &quot;Eliminación en curso&quot;
* Haga clic en &quot;[!UICONTROL Configurar nueva conexión CRM]&quot;
* En el[!UICONTROL Seleccionar conexión CRM]&quot; modal , haga clic en el &quot;[!UICONTROL Connect]&quot; Acción junto al [!DNL Salesforce] Plataforma, seleccione la opción[!UICONTROL Producción]&quot;, opción
* Se le solicitarán sus credenciales, asegúrese de introducir los detalles de inicio de sesión de producción

## Paso 4: Configuración de Salesforce {#salesforce-configuration}

[Diseños de página](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[Conjuntos de permisos](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[Uso compartido de informes](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0){target=&quot;_blank&quot;}

[Ocultar tipos de informes innecesarios](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[Flujo de trabajo personalizado, si corresponde](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
