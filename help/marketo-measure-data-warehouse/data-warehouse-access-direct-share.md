---
description: Acceso a la Data Warehouse - Uso compartido directo - Documentación del producto
title: 'Acceso a Data Warehouse: Uso compartido directo'
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
feature: Data Warehouse
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 3%

---

# Acceso a Data Warehouse: Uso compartido directo {#data-warehouse-access-direct-share}

## Requisitos {#requirements}

Para que [!DNL Marketo Measure] para configurar un recurso compartido directo en el data warehouse, debe cumplir los siguientes requisitos.

* Tiene su propia instancia de Snowflake.
* La instancia de Snowflake se encuentra en la región de Snowflake de Azure East US 2.
* Usted proporciona [!DNL Marketo Measure] con su id de cuenta de Snowflake.

## Limitaciones {#limitations}

[!DNL Marketo Measure] solo podrá configurar acciones directas de Snowflake con cuentas ubicadas en Azure East US 2 debido a las limitaciones actuales de Snowflake Direct Share. Si necesita que los datos estén disponibles en otras regiones de Snowflake, le recomendamos que realice una copia de los datos en una cuenta de Snowflake ubicada en Azure East US 2 y que aproveche la [Replicación de base de datos de Snowflake](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target="_blank"} para copiar los datos en la región o cuenta de Snowflake que elija.

## Introducir ID de cuenta de Snowflake {#enter-snowflake-account-id}

Abra el **Configuración** en la aplicación de Marketo Measure y vaya a la sección **Data Warehouse** página. En el **Uso compartido directo** , introduzca su [id de cuenta de Snowflake](https://docs.snowflake.com/en/user-guide/admin-account-identifier.html){target="_blank"} en el cuadro proporcionado y haga clic en **Connect**.

![](assets/data-warehouse-access-direct-share-1.png)

## Acceso al recurso compartido {#accessing-the-share}

Una vez creado el recurso compartido para el ID de cuenta proporcionado, debe completar el [pasos de configuración](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"} en la instancia de Snowflake para acceder a los datos.

>[!NOTE]
>
>Puede elegir cualquier nombre de base de datos que desee. Puede asignar los privilegios a cualquier función que elija, siempre que exista en la instancia de Snowflake.

* Usar la función Administrador de cuentas

```
USE ROLE ACCOUNTADMIN
```

* Ver los recursos compartidos disponibles (se mostrará el nombre del recurso compartido concedido)

```
SHOW SHARES
```

* Crear una base de datos para el recurso compartido

```
CREATE DATABASE <database_name> FROM SHARE <provider_account>.<share_name>
```

* Conceder privilegios en la base de datos compartida

```
GRANT IMPORTED PRIVILEGES ON DATABASE <database_name> TO ROLE <role_name>
GRANT IMPORTED PRIVILEGES ON ALL SCHEMAS IN DATABASE <database_name> TO ROLE <role_name>
```

Para obtener instrucciones y pasos más detallados para realizar estos pasos desde la interfaz de usuario de Snowflake, consulte [Documentación del Snowflake directamente](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}.
