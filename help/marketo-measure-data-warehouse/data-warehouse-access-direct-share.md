---
description: Acceso a la Data Warehouse - Uso compartido directo - Documentación del producto
title: 'Acceso a Datas Warehouse: uso compartido directo'
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# Acceso a Datas Warehouse: uso compartido directo {#data-warehouse-access-direct-share}

**Requisitos**

Para [!DNL Marketo Measure] para configurar un recurso compartido directo en el almacén de datos, debe cumplir los siguientes requisitos.

* Tiene su propia instancia de Snowflake.
* La instancia de Snowflake se encuentra en la región de Snowflake de Azure East US 2.
* Proporcione [!DNL Marketo Measure] con su id de cuenta de Snowflake.

**Limitaciones**

[!DNL Marketo Measure] solo podrá configurar Snowflake Direct Share con cuentas ubicadas en Azure East US 2 debido a las limitaciones actuales de Direct Share para Snowflake. Si necesita que los datos estén disponibles en otras regiones de Snowflake, le recomendamos que realice una copia de los datos en una cuenta de Snowflake ubicada en Azure East US 2 y que aproveche la variable [Replicación de base de datos de Snowflake](https://docs.snowflake.com/en/user-guide/database-replication-intro.html)función {target=&quot;_blank&quot;} para copiar los datos en la región o cuenta del Snowflake que elija.

**Acceso al recurso compartido**

Una vez creado el recurso compartido para el id de cuenta proporcionado, debe completar la [pasos de configuración](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target=&quot;_blank&quot;} en la instancia de Snowflake para acceder a los datos.

>[!NOTE]
>
>Puede elegir cualquier nombre de base de datos que desee. Puede asignar los privilegios a cualquier regla que elija, siempre que exista en la instancia de Snowflake.

* Uso del rol Administrador de cuentas

```
USE ROLE ACCOUNTADMIN
```

* Ver recursos compartidos disponibles (se mostrará el nombre del recurso compartido concedido)

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

Para obtener instrucciones y pasos más detallados para realizar estos pasos desde la interfaz de usuario del Snowflake, consulte [documentación del Snowflake directamente](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target=&quot;_blank&quot;}.
