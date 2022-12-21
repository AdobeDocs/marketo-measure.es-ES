---
description: Acceso a Data Warehouse - Cuenta de Reader - Documentación del producto
title: 'Acceso a Data Warehouse: Cuenta de Reader'
exl-id: 2aa73c41-47ab-4f11-96d8-dafb642308fc
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%

---

# Acceso a Data Warehouse: Cuenta de Reader {#data-warehouse-access-reader-account}

## Vínculo de acceso del Snowflake {#snowflake-access-link}

Para acceder al almacén de datos del Snowflake, deberá navegar a la dirección URL específica de la cuenta del Snowflake. Puede encontrar este vínculo de acceso iniciando sesión en [!DNL Marketo Measure] y siguiendo los pasos a continuación para ir a la página de información de Data Warehouse.

1. En [!DNL Marketo Measure], en la parte superior de la página, haga clic en **[!UICONTROL Mi cuenta]** > **[!UICONTROL Configuración]**.

   ![](assets/data-warehouse-access-reader-account-1.png)

1. En el menú de la izquierda, en Seguridad, haga clic en **[!UICONTROL Data Warehouse]**.

   ![](assets/data-warehouse-access-reader-account-2.png)

1. En esta página, encontrará el vínculo a su almacén de datos del Snowflake y a su nombre de usuario.

   ![](assets/data-warehouse-access-reader-account-3.png)

   >[!NOTE]
   >
   >Se trata de una cuenta de solo lectura disponible para su organización, no solo para un usuario individual. Cualquier usuario de su organización que tenga acceso a [!DNL Marketo Measure] Puede utilizar esta cuenta para iniciar sesión en la cuenta del lector de Datas Warehouse de Snowflake.

1. Haga clic en el vínculo proporcionado en la dirección URL del Snowflake. Esto le llevará a la página de inicio de sesión del Snowflake donde debe introducir su nombre de usuario y contraseña. _Si no dispone de la contraseña, consulte los pasos siguientes para restablecerla_.

   ![](assets/data-warehouse-access-reader-account-4.png)

1. Una vez que haya iniciado sesión, haga clic en **[!UICONTROL Hojas de cálculo]** en la parte superior de la página.

   ![](assets/data-warehouse-access-reader-account-5.png)

1. Los objetos de base de datos BIZIBLE_ROI_V3 están en el lado izquierdo de la pantalla. Introduzca Warehouse, Database y Schema en las opciones desplegables de la parte superior de la ventana de consulta. Solo debería haber una opción para cada uno. Ahora está listo para ejecutar consultas dentro del editor de consultas de Snowflake.

   ![](assets/data-warehouse-access-reader-account-6.png)

## Restaurar la contraseña {#reset-your-password}

[!DNL Marketo Measure] no tiene acceso a la contraseña de inicio de sesión del Snowflake. Si necesita restablecer la contraseña, haga clic en el botón [!UICONTROL Restablecer contraseña] en la página de información de la Data Warehouse y siga las instrucciones. Una contraseña temporal se mostrará inmediatamente en la interfaz de usuario. Se le pedirá que cree su propia contraseña en el próximo inicio de sesión del almacén de datos.

>[!NOTE]
>
>* Restablecer la contraseña la restablece para todos [!DNL Marketo Measure] usuarios de su organización, no solo el usuario que ha iniciado sesión en ese momento.
>* Solo se muestra la contraseña temporal en la interfaz de usuario. No se envía un correo electrónico.


![](assets/data-warehouse-access-reader-account-7.png)

![](assets/data-warehouse-access-reader-account-8.png)

## Conexión al Snowflake mediante herramientas de terceros {#connecting-to-snowflake-via-third-party-tools}

Deberá introducir algunos datos para conectar el almacén de datos del Snowflake a una herramienta de terceros.

>[!NOTE]
>
>Cada herramienta tiene diferentes requisitos de conexión; se recomienda consultar la documentación de la herramienta específica que está intentando conectar.

* **URI** (siempre obligatorio)
   * Es el nombre de dominio de la cuenta de Snowflake.  Está contenido en una parte del vínculo de inicio de sesión del Snowflake.
* **Nombre de usuario** (siempre obligatorio)
   * El nombre de usuario aparece en la página de información de Data Warehouse de [!DNL Marketo Measure].
* **Contraseña** (siempre obligatorio)
   * Esta es la contraseña que definió la primera vez que inició sesión en su cuenta de Snowflake.  Para restablecer la contraseña, consulte los pasos descritos anteriormente.
* **Nombre de la base de datos** (no siempre obligatorio)
   * La base de datos es la que almacena los datos en Snowflake. Es el recurso de almacenamiento. El nombre de la base de datos aparece enumerado en la página de información de Data Warehouse de [!DNL Marketo Measure].
* **Nombre del almacén** (no siempre obligatorio)
   * El almacén es lo que ejecuta las consultas en Snowflake. Es el recurso de cálculo.  El nombre del almacén aparece en la página de información de Data Warehouse de [!DNL Marketo Measure].
   ![](assets/data-warehouse-access-reader-account-9.png)
