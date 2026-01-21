---
unique-page-id: 37356132
description: '[!DNL Marketo Measure] flujos de trabajo de ingresos para Dynamics - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] flujos de trabajo de ingresos para Dynamics'
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
feature: Microsoft Dynamics
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 0%

---

# [!DNL Marketo Measure] flujos de trabajo de ingresos para Dynamics {#marketo-measure-revenue-workflows-for-dynamics}

## Parte 1: Ingresos estimados vs. ingresos reales {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] señala a un campo de ingresos estándar de forma predeterminada (Ingresos reales), pero Dynamics tiene dos campos de ingresos estándar: Ingresos reales e Ingresos estimados. Para que los ingresos de canalización estén disponibles en el panel de detección, se necesita un campo personalizado y un flujo de trabajo para capturar la cantidad correcta del campo Ingresos estimados o Ingresos reales en función de si la oportunidad está abierta o cerrada (ganada).

Paso 1: Crear un campo de cantidad de oportunidad personalizado en Dynamics

>[!NOTE]
>
>Todos los campos de ingresos de Dynamics tienen un campo base y un campo regular. Ignore el campo base.

Paso 2: Cree un flujo de trabajo que actualice el campo de cantidad de oportunidad personalizada creado en el paso 1 y el campo de cantidad de oportunidad [!DNL Marketo Measure].

>[!NOTE]
>
>No podemos señalar al campo Importe de oportunidad [!DNL Marketo Measure] (bizible2_bizible_Opportunity_amount) en Discover con cuentas de Dynamics. Los clientes de Dynamics deben crear un campo de cantidad de oportunidad personalizada para que [!DNL Marketo Measure] apunte en Discover. Una vez finalizado, el cliente debe crear un flujo de trabajo que actualice **tanto** la cantidad de oportunidad [!DNL Marketo Measure] (bizible2_bizible_Opportunity_amount) **como** el campo de cantidad de oportunidad personalizada. El campo Cantidad de oportunidad [!DNL Marketo Measure] viene con el paquete, pero se debe crear un campo personalizado.

Cantidad de instrucciones de flujo de trabajo:

**#1 DE FLUJO DE TRABAJO**: Oportunidad - Actualizar [!DNL Marketo Measure] campo Cantidad de oportunidad y campo personalizado = Ingresos estimados

Este flujo de trabajo se ejecuta con oportunidades abiertas cada vez que los ingresos estimados cambian y actualizan el campo Cantidad de oportunidad [!DNL Marketo Measure] y el campo personalizado para que coincida con el campo Ingresos estimados. El flujo de trabajo debe configurarse para ejecutarse en tiempo real, pero también puede ejecutarse bajo demanda para actualizar las oportunidades abiertas.

Proporcione a su punto de contacto [!DNL Marketo Measure] el nombre del campo de monto de oportunidad personalizado. Actualizan la configuración de oportunidad de la aplicación [!DNL Marketo Measure] para incluir el nombre del campo de cantidad de oportunidad personalizada. Esto indica a Discover qué campo utilizar en el sistema de informes.

**#2 DE FLUJO DE TRABAJO**: Oportunidad - Actualizar [!DNL Marketo Measure] campo Cantidad de oportunidad y campo personalizado = Ingresos reales

Este flujo de trabajo se inicia cuando un usuario cierra una oportunidad y actualiza el campo Cantidad de oportunidad [!DNL Marketo Measure] y el campo personalizado con los ingresos reales agregados al formulario Cierre de oportunidad antes de que la oportunidad se bloquee como cerrada.

## Parte 2: Fecha de cierre estimada frente a fecha de cierre real {#part-estimated-close-date-vs-actual-close-date}

De forma predeterminada, los datos de ingresos de la canalización no están disponibles en el panel porque, de forma predeterminada, Dynamics tiene dos campos de fecha de cierre de existencias: Fecha de cierre estimada y Fecha de cierre real. [!DNL Marketo Measure] solo puede señalar a un campo de fecha de cierre en el panel y señala a la fecha de cierre real.

Si las oportunidades abiertas no tienen datos en el campo Fecha de cierre real, no hay datos en el panel para las oportunidades abiertas. Dicho esto, se necesita un flujo de trabajo basado en la fase de oportunidad para admitir ambos campos de fecha.

1. Crear campo de fecha de cierre personalizado en el objeto de oportunidad ([!DNL Marketo Measure] fecha de cierre personalizado).
1. Cree un flujo de trabajo para actualizar el campo Fecha de cierre personalizada [!DNL Marketo Measure] con la fecha desde la Fecha de cierre estimada o la Fecha de cierre real, dependiendo de si la oportunidad está abierta o cerrada (el flujo de trabajo debe guardarse para ejecutarse en tiempo real, pero debe ejecutarse &quot;bajo demanda&quot; al menos una vez para actualizar todas las operaciones abiertas actuales).
1. Pruebe el flujo de trabajo y confirme que funciona.
1. El cliente debe proporcionar el nombre personalizado de la API de fecha de cierre a [!DNL Marketo Measure].
1. [!DNL Marketo Measure] para actualizar la configuración de la aplicación [!DNL Marketo Measure] de modo que apunte al campo Fecha de cierre personalizado de [!DNL Marketo Measure] en el panel.

   Una vez completados los pasos anteriores, ejecute los flujos de trabajo para actualizar el campo Cantidad de Opp [!DNL Marketo Measure] personalizada y el campo Fecha de cierre personalizada [!DNL Marketo Measure] en sus oportunidades históricas para reflejar los datos correctos. Es probable que esto cambie los campos modificados en/por, por lo que debe consultar con su equipo para ver si esto presenta algún problema.

Para actualizar las oportunidades cerradas...

1. Aísle las oportunidades que se han cerrado desde la fecha de inicio de [!DNL Marketo Measure] hasta que el flujo de trabajo esté activo. Este es el grupo de oportunidades históricas que debe actualizar mediante un flujo de trabajo.
1. Exportar todos los registros a Excel.
1. Abra el archivo de Excel y habilite el contenido.
1. Copiar los datos de la fecha de cierre real en la fecha de cierre personalizada [!DNL Marketo Measure].
1. Copie los datos de ingresos reales en [!DNL Marketo Measure] importe de oportunidad personalizado **y** [!DNL Marketo Measure] importe de oportunidad (hay dos campos).
1. Guarde el archivo.
1. Importar archivo. Dynamics lo reconocerá como un archivo con registros existentes para actualizar.
1. Compruebe si se han producido errores al importar el archivo.

>[!NOTE]
>
>Los flujos de trabajo descritos en este documento son solo una forma de actualizar los campos para que [!DNL Marketo Measure] pueda mostrar los datos correctos en Discover. Si tienes otra forma de lograr la misma tarea, puedes ir por ella. Básicamente, lo que necesitamos de ellos es algún tipo de flujo de trabajo que logre lo siguiente:
>
> * Si Opp = Abrir, actualice el campo de fecha de cierre personalizado, el campo de cantidad de opp personalizado y el campo de cantidad de opp [!DNL Marketo Measure] para que sean iguales a Fecha de cierre estimada e Ingresos estimados, respectivamente.
> * Si Opp = Ganado cerrado, actualice el campo de fecha de cierre personalizado, el campo de cantidad de opp personalizado y el campo de cantidad de opp [!DNL Marketo Measure] para que sean iguales a Fecha de cierre real e Ingresos reales, respectivamente.
