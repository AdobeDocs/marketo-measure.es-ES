---
description: Obtenga información acerca del proceso de migración al pasar de la suscripción en niveles [!DNL Marketo Measure] a [!DNL Marketo Measure] Ultimate.
title: Migración de nivel a [!DNL Marketo Measure] Ultimate
feature: Integration, Tracking, Attribution
exl-id: 828c9bba-3835-484a-bd80-84b5a6b67e22
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: 7da342c5-06ee-5869-b3e8-b73d5bf75a9d
    internal-label: Integration
  - id: dcbeff6e-0253-5a4b-9ac2-1b67cc4a6286
    internal-label: Tracking
  - id: d7322935-5b46-52a3-b6ea-21e6aec748b5
    internal-label: Attribution
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 1%
---
# Migración de nivel 1-2 a [!DNL Marketo Measure] Ultimate {#migration-from-tier-to-marketo-measure-ultimate}

Este artículo describe el proceso de migración de los usuarios que pasan de la suscripción de nivel 1 o 2 a [!DNL Marketo Measure] Ultimate.

>[!IMPORTANT]
>
>Recuerde conservar la instancia de nivel existente hasta que se complete la migración.

## Recopilación de datos {#data-collection}

### Datos de tráfico web {#web-traffic-data}

* No se requieren cambios para la implementación de JavaScript.

* Habilitar dominios en la nueva instancia de Ultimate.

* Si es necesario, envíe un ticket para migrar y volver a procesar los datos web históricos.

* Las integraciones de publicidad permanecen inalteradas, pero recuerde volver a conectarlas en Ultimate. Antes de hacerlo, asegúrese de desconectar sus cuentas de publicidad en el inquilino de nivel.

>[!NOTE]
>
>Los datos históricos de costes de publicidad no se importarán. Solo importaremos los datos de costes de publicidad a partir de ese momento una vez que las cuentas de publicidad se hayan reconectado.

### Conexión de datos empresariales {#enterprise-data-connection}

Vuelva a implementar todas las conexiones de datos de origen en AEP, incluidas las conexiones CRM y Marketo Engage.

## Transformación de datos {#data-transformation}

* Las funciones de Account-Based Marketing, incluida la coincidencia de cliente potencial con cuenta y las puntuaciones de participación predictiva, no están disponibles en Ultimate.

  * Sin embargo, puede importar los resultados coincidentes del posible cliente con la cuenta a través de AEP y utilizarlos dentro de la plataforma.

* En Ultimate, las transiciones de fase históricas de CRM se infieren en lugar de leerse directamente, ya que no hay conexión directa de CRM.

  * Leemos registros de oportunidades y marcas de tiempo y vemos la etapa actual, luego deducimos las etapas históricas.

## Sistema de informes {#reporting}

* Ultimate no devuelve los datos a los CRM.

  * Si desea volver a insertar datos en el CRM, se requiere una canalización de ETL personalizada para extraer datos de Marketo Measure Snowflake al CRM. Debe configurar un modelo de datos personalizado en su CRM.

* Todos los paneles de Discover son los mismos que los de la solución por niveles, con la adición de paneles de Attribution AI.
