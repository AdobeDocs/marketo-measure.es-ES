---
unique-page-id: 37356132
description: "[!DNL Marketo Measure] Flujos de trabajo de ingresos para Dynamics - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Flujos de trabajo de ingresos para Dynamics"
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 0%

---

# [!DNL Marketo Measure] Flujos de trabajo de ingresos para Dynamics {#marketo-measure-revenue-workflows-for-dynamics}

## Parte 1: Ingresos estimados vs. Ingresos reales {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] apunta a un campo de ingresos estándar predeterminado (ingresos reales) pero Dynamics tiene dos campos de ingresos estándar: Ingresos reales e ingresos estimados. Para que los ingresos de la canalización estén disponibles en el panel de Discover, se necesita un campo personalizado y un flujo de trabajo para capturar la cantidad correcta desde el campo Ingresos estimados o el campo Ingresos reales, dependiendo de si la oportunidad está abierta o cerrada (si ganó).

Paso 1: Crear campo de cantidad de oportunidad personalizado en Dynamics

>[!NOTE]
>
>Todos los campos de ingresos de Dynamics tienen un campo base y un campo normal. Ignore el campo base.

Paso 2: Cree un flujo de trabajo que actualice el campo cantidad de oportunidad personalizada creado en el paso 1 y la variable [!DNL Marketo Measure] Campo Cantidad de oportunidad.

>[!NOTE]
>
>No podemos señalar a la [!DNL Marketo Measure] Campo Cantidad de oportunidad (bizible2_bizible_oportunidad_cantidad) en Discover con cuentas de Dynamics. Los clientes de Dynamics deben crear un campo personalizado de cantidad de oportunidad para [!DNL Marketo Measure] a en Discover. Una vez finalizado, el cliente debe crear un flujo de trabajo que se actualice **both** el [!DNL Marketo Measure] Cantidad de oportunidad (bizible2_bizible_oportunidad_cantidad) **y** el campo cantidad de oportunidad personalizada. La variable [!DNL Marketo Measure] El campo Cantidad de oportunidad viene con el paquete, pero se debe crear un campo personalizado.

Instrucciones del flujo de trabajo de cantidad:

**FLUJO DE TRABAJO 1**: Oportunidad: Actualización [!DNL Marketo Measure] Campo Importe de Oportunidad y Campo personalizado = Ingresos estimados

Este flujo de trabajo se ejecuta en oportunidades abiertas cada vez que cambie el Ingreso estimado y actualizará el [!DNL Marketo Measure] El campo Importe de oportunidad y el campo personalizado coinciden con el campo Ingresos estimados . El flujo de trabajo debe configurarse para ejecutar &quot;Tiempo real&quot;, pero también puede ejecutarse &quot;bajo demanda&quot; para actualizar las oportunidades abiertas.

Proporcione su [!DNL Marketo Measure] punto de contacto con el nombre del campo de cantidad de oportunidad personalizada. Actualizarán la variable [!DNL Marketo Measure] Configuración de oportunidad de aplicación para incluir el nombre del campo de cantidad de oportunidad personalizada. Esto indicará a Discover qué campo utilizar en los informes.

**FLUJO DE TRABAJO 2**: Oportunidad: Actualización [!DNL Marketo Measure] Campo Importe de Oportunidad y Campo personalizado = Ingresos reales

Este flujo de trabajo se ejecuta en tiempo real. Se inicia cuando un usuario cierra una oportunidad y actualiza la [!DNL Marketo Measure] El campo Cantidad de oportunidad y el campo personalizado con los ingresos reales agregados al formulario Cierre de oportunidad antes de que la oportunidad se bloquee como cerrada.

## Parte 2: Fecha de cierre estimada vs. Fecha de cierre real {#part-estimated-close-date-vs-actual-close-date}

De forma predeterminada, los datos de ingresos de la canalización no estarán disponibles en el panel porque, de forma predeterminada, Dynamics tiene dos campos de fecha de cierre de existencias: Fecha de cierre estimada y Fecha de cierre real. [!DNL Marketo Measure] solo puede apuntar a un campo de fecha de cierre en el panel y actualmente señalamos a la Fecha de cierre real.

Si las oportunidades abiertas no tienen datos en el campo Fecha de cierre real , no se ve ningún dato en el panel para las oportunidades de apertura. Dicho esto, se necesita un flujo de trabajo basado en la fase de oportunidad para admitir ambos campos de fecha.

1. Crear un campo de fecha de cierre personalizado en el objeto de oportunidad (p. ej. [!DNL Marketo Measure] Fecha de cierre personalizada).
1. Crear un flujo de trabajo para actualizar el [!DNL Marketo Measure] Fecha de cierre personalizada con la fecha de la Fecha de cierre estimada o la Fecha de cierre real, dependiendo de si la oportunidad está abierta o cerrada (el flujo de trabajo debe guardarse para ejecutarse en tiempo real, pero deberá ejecutarse &quot;bajo demanda&quot; al menos una vez para actualizar todas las operaciones abiertas actuales).
1. Pruebe el flujo de trabajo y confirme que funciona.
1. El cliente debe proporcionar el nombre de la API de fecha de cierre personalizada a [!DNL Marketo Measure].
1. [!DNL Marketo Measure] para actualizar el [!DNL Marketo Measure] configuración de la aplicación para que apunte a la variable [!DNL Marketo Measure] Fecha de cierre personalizada en el panel.

   Una vez completados los pasos anteriores, tendremos que ejecutar flujos de trabajo para actualizar los [!DNL Marketo Measure] Importe de la opción y la variable [!DNL Marketo Measure] Campo Fecha de cierre personalizada en sus oportunidades históricas para reflejar los datos correctos. Es probable que esto cambie los campos modificados on/by , por lo que querrá consultar a su equipo si esto presenta algún problema.

Para actualizar las oportunidades cerradas...

1. Aísle las oportunidades que se han cerrado desde su [!DNL Marketo Measure] fecha de inicio hasta que el flujo de trabajo esté activo. Este es el grupo de oportunidades históricas que deberá actualizar mediante el flujo de trabajo.
1. Exportar todos los registros a Excel.
1. Abra el archivo de Excel y habilite el contenido.
1. Copiar datos de fecha de cierre real a [!DNL Marketo Measure] Fecha de cierre personalizada.
1. Copiar datos de ingresos reales a [!DNL Marketo Measure] Cantidad de oportunidad personalizada **y** [!DNL Marketo Measure] Cantidad de oportunidad (hay dos campos).
1. Guarde el archivo.
1. Importar archivo. Dynamics lo reconocerá como un archivo con registros existentes que actualizar.
1. Compruebe si hay errores en el archivo de importación.

>[!NOTE]
>
>Los flujos de trabajo descritos en este documento son solo una forma de actualizar los campos para que [!DNL Marketo Measure] puede mostrar los datos correctos en Discover. Si tiene otra forma de realizar la misma tarea, puede ir por ella. Básicamente lo que necesitamos de ellos es algún tipo de flujo de trabajo que logre lo siguiente:
>
> * Si Opp = Abrir, actualice el campo de fecha de cierre personalizado, el campo de cantidad de opp personalizada y [!DNL Marketo Measure] el campo cantidad de opp es igual a Fecha de cierre estimada e Ingresos estimados, respectivamente.
> * Si Opp = Ganó cerrado, actualice el campo de fecha de cierre personalizado, el campo de cantidad de opp personalizada y [!DNL Marketo Measure] opp amount para igualar Fecha de cierre real e Ingresos reales, respectivamente.

