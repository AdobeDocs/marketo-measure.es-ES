---
unique-page-id: 18874694
description: Migración de zona protegida de Salesforce a producción - [!DNL Marketo Measure] - Documentación del producto
title: Migración de zona protegida de Salesforce a producción
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
feature: Salesforce
source-git-commit: ad658a513b01dc7a51299abcb7313ff1877e49f3
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 4%

---

# Migración de zona protegida de Salesforce a producción {#salesforce-sandbox-to-production-migration}

Si eligió realizar la prueba [!DNL Marketo Measure] en un [!DNL Salesforce] Entorno de zona protegida, siga estas instrucciones para migrar al entorno de producción una vez que esté listo. Las siguientes instrucciones suponen que ya ha descargado el [!DNL Marketo Measure] en su organización de espacio aislado, ha realizado las pruebas necesarias y está listo para publicar [!DNL Marketo Measure] en Producción.

## Paso 1: Instalar el [!DNL Marketo Measure] Empaquetar en su producción [!DNL Salesforce] Instancia

* Instale el [!DNL Marketo Measure] paquete en Producción con el complemento &quot;[!UICONTROL Todos los usuarios]&quot; configuración

   * [Paquete base](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"}

* Para obtener más información sobre [!DNL Marketo Measure] relación con [!DNL Salesforce], eche un vistazo a [este artículo](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)
* Un poco de [!DNL Salesforce] es necesaria la configuración de. Los elementos de acción específicos se describen a continuación en [Paso 4 siguiente](#salesforce-configuration)

## Paso 2: Eliminar la conexión CRM de la zona protegida actual en [!DNL Marketo Measure] Aplicación {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* Inicie sesión en [!DNL Marketo Measure] aplicación en experience.adobe.com/marketo-measure
* Vaya a Mi cuenta >[!UICONTROL Configuración] >[!UICONTROL Conexiones]
* Haga clic en el icono de papelera situado junto a la conexión SFDC para eliminarla
* Se le pedirá que confirme la eliminación. Asegúrese de leer el mensaje con cuidado y comprender las consecuencias de la eliminación

  ![](assets/salesforce-sandbox-to-production-migration-1.png)

   * Escriba el nombre de la Empresa como se solicita en el modelo de confirmación y haga clic en &quot;Entiendo las consecuencias, elimine esta conexión&quot;
* Esto almacenará en déclencheur el proceso de eliminación y tardará algún tiempo en finalizar

## Paso 3: Conectar la instancia de Production CRM en [!DNL Marketo Measure] Aplicación {#connect-the-production-crm-instance-in-marketo-measure-app}

* Inicie sesión en [!DNL Marketo Measure] aplicación en experience.adobe.com/marketo-measure
* Vaya a [!UICONTROL Mi cuenta] >[!UICONTROL Configuración] > [!UICONTROL Conexiones]
* Una vez que la eliminación de la conexión de espacio aislado se haya eliminado correctamente, la conexión desaparecerá de la página; de lo contrario, la conexión seguirá presente con el estado &quot;Eliminación en curso&quot;
* Haga clic en &quot;[!UICONTROL Configurar nueva conexión CRM]&quot;
* En el campo &quot;[!UICONTROL Seleccionar conexión CRM]&quot; modal, haga clic en &quot;[!UICONTROL Connect]&quot; Acción junto a [!DNL Salesforce] Platform, seleccione la opción &quot;[!UICONTROL Producción]&quot; opción
* Se le pedirán sus credenciales. Asegúrese de introducir los detalles de inicio de sesión de producción

## Paso 4: Configuración de Salesforce {#salesforce-configuration}

[Diseños de páginas](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[Conjuntos de permisos](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[Uso compartido de informes](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0){target="_blank"}

[Ocultar tipos de informes innecesarios](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[Flujo de trabajo personalizado si corresponde](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
