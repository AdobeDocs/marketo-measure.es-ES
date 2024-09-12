---
description: Obtenga información acerca del proceso de migración al pasar de la  [!DNL Marketo Measure] suscripción por niveles a [!DNL Marketo Measure] Ultimate.
hide: true
hidefromtoc: true
title: Migración de nivel a  [!DNL Marketo Measure] Ultimate
feature: Integration, Tracking, Attribution
source-git-commit: 0c94276bec390bb67dafe5dd679c1a0378a05c85
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 1%

---

# Migración de nivel 1-2 a [!DNL Marketo Measure] Ultimate {#migration-from-tier-to-marketo-measure-ultimate}

Este artículo describe el proceso de migración para los usuarios que pasan de la suscripción de nivel 1 o 2 a Marketo Measure Ultimate.

>[!IMPORTANT]
>
>Recuerde conservar la instancia de nivel existente hasta que se complete la migración.

## Recopilación de datos {#data-collection}

### Datos de tráfico web {#web-traffic-data}

* No se requieren cambios para la implementación de JavaScript.

* Habilite los dominios en la nueva instancia de Ultimate.

* Si es necesario, envíe un ticket para migrar y volver a procesar los datos web históricos.

* Las integraciones de publicidad permanecen inalteradas, pero recuerde volver a conectarlas en Ultimate. Antes de hacerlo, asegúrese de desconectar sus cuentas de publicidad en el inquilino de nivel.

>[!NOTE]
>
>Los datos históricos de costes de publicidad no se importarán. Solo importaremos los datos de costes de publicidad a partir de ese momento una vez que las cuentas de publicidad se hayan reconectado.

### Conexión de datos empresariales {#enterprise-data-connection}

Vuelva a implementar todas las conexiones de datos de origen en AEP, incluidas las conexiones CRM y de Marketo Engage.

## Transformación de datos {#data-transformation}

* Las funciones de Account-Based Marketing, incluida la coincidencia de cliente potencial con cuenta y las puntuaciones de participación predictiva, no están disponibles en Ultimate.

   * Sin embargo, puede importar los resultados coincidentes de cliente potencial con cuenta a través de AEP y utilizarlos dentro de la plataforma.

* En Ultimate, las transiciones de fase históricas de CRM se deducen en lugar de leerse directamente, ya que no hay conexión directa de CRM.

   * Leemos registros de oportunidades y marcas de tiempo y vemos la etapa actual, luego deducimos las etapas históricas.

## Creación de informes {#reporting}

* Ultimate no devuelve los datos a los CRM.

   * Si desea volver a insertar datos en el CRM, se requiere una canalización de ETL personalizada para extraer datos del Snowflake de Marketo Measure al CRM. Debe configurar un modelo de datos personalizado en su CRM.

* Todos los paneles de Discover son los mismos que los de la solución por niveles, con la adición de paneles de Attribution AI.
