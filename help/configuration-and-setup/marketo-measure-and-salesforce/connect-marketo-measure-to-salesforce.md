---
unique-page-id: 18874580
description: Conectar Marketo Measure a Salesforce - [!DNL Marketo Measure] - Documentación del producto
title: Conectar Marketo Measure a Salesforce
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# Conectar Marketo Measure a Salesforce {#connect-marketo-measure-to-salesforce}

Este artículo proporciona información general sobre cómo conectar su [!DNL Salesforce] a su [!DNL Marketo Measure] cuenta.

## Conexión [!DNL Marketo Measure] con [!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. Utilice un navegador incógnito para iniciar sesión en [!DNL Marketo Measure].

1. En la barra de menús de la parte superior de la pantalla, vaya a **[!UICONTROL Mi cuenta]** y haga clic en el botón [!UICONTROL Configuración] .

1. En la columna de configuración de la izquierda, haga clic en [!UICONTROL Conexiones] ubicado bajo el [!UICONTROL Integraciones] para obtener más información.

   ![](assets/1.png)

1. En la sección CRM de Conexiones, haga clic en **[!UICONTROL Configurar nueva conexión CRM]**.

   ![](assets/2.png)

1. Aparecerá una ventana emergente pidiéndole que seleccione la conexión CRM. Haga clic en el [!UICONTROL Connect] junto al botón [!DNL Salesforce] logotipo.

   ![](assets/3.png)

1. Aparecerá una ventana emergente final en la que se le pedirá que especifique su [!DNL Salesforce] credenciales, simulación de pruebas o producción. Introduzca la información y haga clic en **[!UICONTROL Autorizar]** para conectar la cuenta a [!DNL Marketo Measure].

>[!NOTE]
>
>[!DNL Marketo Measure] solo se puede conectar a uno [!DNL Salesforce] a la vez.
>
>* A [!DNL Marketo Measure] La instancia de se puede conectar a una instancia de Sandbox de SFDC para probar la integración antes de cambiar la conexión a la instancia de producción de SFDC.
>* Si realiza la prueba primero con un Simulador para pruebas SFDC, le recomendamos encarecidamente que realice una prueba con una que sea una réplica exacta de su instancia de producción SFDC en términos de campos en los objetos Posibles clientes, Contacto, Cuenta, Oportunidad, Campaña y Caso. Si tiene déclencheur de APEX activos en producción que se activen al actualizar los objetos Posible cliente, Contacto, Cuenta, Oportunidad, Campaña y Caso, debe intentar activarlos en el simulador de pruebas.
>* Una vez que haya terminado con las pruebas, actualizará su [!DNL Marketo Measure] para señalar la producción [!DNL Salesforce] (en lugar de Sandbox [!DNL Salesforce]). Debido a la forma en que se creó la integración, una vez [!DNL Marketo Measure] La cuenta está conectada a Producción [!DNL Salesforce], no puede ir &quot;atrás&quot; y conectarse a un Simulador para pruebas [!DNL Salesforce] org.


