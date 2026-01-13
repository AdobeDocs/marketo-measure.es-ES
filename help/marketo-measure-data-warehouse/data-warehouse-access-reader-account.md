---
description: 'Acceso a Data Warehouse: Cuenta de Reader'
title: 'Acceso a Data Warehouse: Cuenta de Reader'
exl-id: 2aa73c41-47ab-4f11-96d8-dafb642308fc
feature: Data Warehouse
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 3%

---


# Acceso a Data Warehouse: Cuenta de Reader {#data-warehouse-access-reader-account}

## Vínculo de acceso de Snowflake {#snowflake-access-link}

Para acceder a su Snowflake Data Warehouse, debe ir a la URL específica de su cuenta de Snowflake. Para encontrar este vínculo de acceso, inicie sesión en [!DNL Marketo Measure] y siga los pasos a continuación para navegar a la página de información de Data Warehouse.

1. En [!DNL Marketo Measure], en la parte superior de la página, haga clic en **[!UICONTROL Mi cuenta]** > **[!UICONTROL Configuración]**.

   ![Menú de navegación de Marketo Measure con las opciones Mi cuenta y Configuración](assets/data-warehouse-access-reader-account-1.png)

1. En el menú del lado izquierdo, debajo de Seguridad, haga clic en **[!UICONTROL Data Warehouse]**.

   ![Barra lateral de configuración con la opción Data Warehouse en la sección Seguridad](assets/data-warehouse-access-reader-account-2.png)

1. Esta página incluye el enlace a su almacén de datos de Snowflake y su nombre de usuario.

   ![Página de información de Data Warehouse que muestra la URL de Snowflake y el nombre de usuario](assets/data-warehouse-access-reader-account-3.png)

   >[!NOTE]
   >Se trata de una cuenta de solo lectura disponible para su organización, no solo para un usuario individual. Cualquier usuario de su organización que tenga acceso a [!DNL Marketo Measure] puede utilizar esta cuenta para iniciar sesión en la cuenta de Snowflake Data Warehouse Reader.

1. Haga clic en el vínculo proporcionado en la URL de Snowflake, que le lleva a la página de inicio de sesión de Snowflake donde introduce su nombre de usuario y contraseña. _Si no tienes tu contraseña, consulta los pasos a continuación para restablecerla_.

   ![Página de inicio de sesión de Snowflake con campos de nombre de usuario y contraseña](assets/data-warehouse-access-reader-account-4.png)

1. Cuando haya iniciado sesión, haga clic en **[!UICONTROL Hojas de cálculo]** en la parte superior de la página.

   ![Interfaz de Snowflake con opción de navegación de hojas de cálculo](assets/data-warehouse-access-reader-account-5.png)

1. Los objetos de base de datos BIZIBLE_ROI_V3 se encuentran en el lado izquierdo de la pantalla. Introduzca el almacén, la base de datos y el esquema en las opciones desplegables de la parte superior de la ventana de consulta. Solo debe haber una opción para cada uno. Ahora está listo para ejecutar consultas dentro del editor de consultas de Snowflake.

   ![Editor de consultas de Snowflake con selectores desplegables y base de datos BIZIBLE_ROI_V3](assets/data-warehouse-access-reader-account-6.png)

## Restablezca su contraseña {#reset-your-password}

[!DNL Marketo Measure] no tiene acceso a su contraseña de inicio de sesión de Snowflake. Si debe restablecer la contraseña, haga clic en el botón [!UICONTROL Restablecer contraseña] de la página de información de Data Warehouse y siga las instrucciones. En la interfaz de usuario se muestra inmediatamente una contraseña temporal. Se le pedirá que cree su propia contraseña en el próximo inicio de sesión de Data Warehouse.

>[!NOTE]
> Restablecer la contraseña la restablece para todos los usuarios de [!DNL Marketo Measure] de su organización, no solo para el usuario que ha iniciado sesión actualmente.
> Solo se muestra la contraseña temporal en la interfaz de usuario. No se enviará un correo electrónico.

![Página de Data Warehouse con botón Restablecer contraseña](assets/data-warehouse-access-reader-account-7.png)

![Visualización de contraseña temporal tras restablecer la contraseña](assets/data-warehouse-access-reader-account-8.png)

## Conexión a Snowflake mediante herramientas de terceros {#connecting-to-snowflake-via-third-party-tools}

Debe introducir algunos datos para conectar el almacén de datos de Snowflake a una herramienta de terceros.

>[!NOTE]
>
>Cada herramienta tiene diferentes requisitos de conexión; se recomienda que consulte la documentación de la herramienta específica que está intentando conectar.

* **URI** (siempre obligatorio)
   * Es el nombre de dominio de la cuenta de Snowflake. Se encuentra dentro de una parte del vínculo de inicio de sesión de Snowflake.
* **Nombre de usuario** (siempre obligatorio)
   * El nombre de usuario aparece en la página de información de Data Warehouse en [!DNL Marketo Measure].
* **Contraseña** (siempre requerida)
   * Esta es la contraseña que configuró la primera vez que inició sesión en su cuenta de Snowflake. Para restablecer la contraseña, consulte los pasos descritos anteriormente.
* **Nombre de base de datos** (no siempre es obligatorio)
   * La base de datos es la que almacena los datos en Snowflake. Es el recurso de almacenamiento. El nombre de la base de datos aparece en la página de información de Data Warehouse en [!DNL Marketo Measure].
* **Nombre de almacén** (no siempre es obligatorio)
   * El almacén es lo que ejecuta consultas en Snowflake. Es el recurso calculado. El nombre del almacén aparece en la página de información de Data Warehouse en [!DNL Marketo Measure].

  ![Página de información de Data Warehouse que muestra detalles de base de datos y nombre de almacén](assets/data-warehouse-access-reader-account-9.png)
