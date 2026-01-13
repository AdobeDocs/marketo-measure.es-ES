---
description: Migración de zona protegida de Salesforce a producción,  [!DNL Marketo Measure]
title: Migración de zona protegida de Salesforce a producción
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 95%

---


# Migración de zona protegida de Salesforce a producción {#salesforce-sandbox-to-production-migration}

Si eligió realizar la prueba de [!DNL Marketo Measure] en un entorno de zona protegida de [!DNL Salesforce], siga estas instrucciones para migrar a la producción una vez que esté listo. Las siguientes instrucciones suponen que ya ha descargado el paquete de [!DNL Marketo Measure] en su organización de zona protegida, ha realizado las pruebas necesarias y está listo para enviar [!DNL Marketo Measure] a producción.

## Paso 1: Instalar el paquete de [!DNL Marketo Measure] en su instancia de producción de [!DNL Salesforce]

* Instale el paquete de [!DNL Marketo Measure] en producción con la configuración “[!UICONTROL Todos los usuarios]”.

   * [Paquete base](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"}

* Para obtener más información sobre la relación de [!DNL Marketo Measure] con [!DNL Salesforce], consulte [este artículo](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).
* Es necesario configurar [!DNL Salesforce] un poco. Los elementos de acción específicos se describen a continuación en el [Paso 4 siguiente](#salesforce-configuration)

## Paso 2: Eliminar la conexión de CRM de la zona protegida actual en la aplicación de [!DNL Marketo Measure] {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* Inicie sesión en la aplicación de [!DNL Marketo Measure] en experience.adobe.com/marketo-measure
* Vaya a Mi cuenta >[!UICONTROL Configuración] >[!UICONTROL Conexiones].
* Haga clic en el icono de papelera situado junto a la conexión de SFDC para eliminarlo.
* Se le pedirá que confirme la eliminación.  Asegúrese de leer la indicación con cuidado y comprender las consecuencias de la eliminación.

  ![Página de conexiones de Marketo Measure que confirma la eliminación de una zona protegida de Salesforce](assets/salesforce-sandbox-to-production-migration-1.png)

   * Escriba el nombre de la empresa como se le indica en el modelo de confirmación y haga clic en “Entiendo las consecuencias, eliminar esta conexión”.
* Esto desencadena el proceso de eliminación y tardará algún tiempo en finalizar.

## Paso 3: Conectar la instancia de producción de CRM en la aplicación de [!DNL Marketo Measure] {#connect-the-production-crm-instance-in-marketo-measure-app}

* Inicie sesión en la aplicación de [!DNL Marketo Measure] en experience.adobe.com/marketo-measure
* Vaya a [!UICONTROL Mi cuenta] >[!UICONTROL Configuración] > [!UICONTROL Conexiones].
* Una vez que la eliminación de la conexión de zona protegida se haya realizado correctamente, la conexión desaparece de la página; de lo contrario, la conexión seguirá presente con el estado “Eliminación en curso”.
* Haga clic en “[!UICONTROL Establecer nueva conexión de CRM]”
* En el diálogo modal “[!UICONTROL Seleccionar conexión de CRM]”, haga clic en la acción “[!UICONTROL Conectar]” junto a [!DNL Salesforce] Platform y seleccione la opción “[!UICONTROL Producción]”.
* Se le solicitarán sus credenciales. Asegúrese de introducir los detalles de inicio de sesión de producción.

## Paso 4: Configuración de Salesforce {#salesforce-configuration}

[Diseño de páginas](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[Conjuntos de permisos](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[Compartir informes](https://help.salesforce.com/s/articleView?language=en_US&id=analytics_share_folder.htm&type=0){target="_blank"}

[Ocultar tipos de informes innecesarios](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[Flujo de trabajo personalizado si corresponde](/help/advanced-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
