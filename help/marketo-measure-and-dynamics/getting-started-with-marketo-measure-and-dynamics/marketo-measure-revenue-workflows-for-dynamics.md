---
unique-page-id: 37356132
description: "[!DNL Marketo Measure] Flujos de trabajo de ingresos para Dynamics - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Flujos de trabajo de ingresos para Dynamics"
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
feature: Microsoft Dynamics
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 0%

---

# [!DNL Marketo Measure] Flujos de trabajo de ingresos para Dynamics {#marketo-measure-revenue-workflows-for-dynamics}

## Parte 1: Ingresos estimados vs. ingresos reales {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] apunta a un campo de ingresos estándar predeterminado (Ingresos reales), pero Dynamics tiene dos campos de ingresos estándar: Ingresos reales e Ingresos estimados. Para que los ingresos de canalización estén disponibles en el panel de detección, se necesita un campo personalizado y un flujo de trabajo para capturar la cantidad correcta del campo Ingresos estimados o Ingresos reales en función de si la oportunidad está abierta o cerrada (ganada).

Paso 1: Crear un campo de cantidad de oportunidad personalizado en Dynamics

>[!NOTE]
>
>Todos los campos de ingresos de Dynamics tienen un campo base y un campo regular. Ignore el campo base.

Paso 2: Cree un flujo de trabajo que actualice el campo de cantidad de oportunidad personalizada creado en el paso 1 y el [!DNL Marketo Measure] Campo Importe de oportunidad.

>[!NOTE]
>
>No podemos señalar a la [!DNL Marketo Measure] Campo Importe de oportunidad (bizible2_bizible_Opportunity_amount) en Discover con cuentas de Dynamics. Los clientes de Dynamics deben crear un campo de cantidad de oportunidad personalizado para [!DNL Marketo Measure] para apuntar a en Discover. Una vez finalizado, el cliente debe crear un flujo de trabajo que actualice **ambos** el [!DNL Marketo Measure] Importe de oportunidad (bizible2_bizible_Opportunity_amount) **y** el campo cantidad de oportunidad personalizada. El [!DNL Marketo Measure] El campo Cantidad de oportunidad viene con el paquete, pero se debe crear un campo personalizado.

Cantidad de instrucciones de flujo de trabajo:

**#1 DE FLUJO DE TRABAJO**: oportunidad, actualización [!DNL Marketo Measure] Campo de importe de oportunidad y campo personalizado = Ingresos estimados

Este flujo de trabajo se ejecuta con oportunidades abiertas cada vez que los ingresos estimados cambian y actualizan el [!DNL Marketo Measure] Importe de la oportunidad y el campo personalizado para que sea igual al campo Ingresos estimados. El flujo de trabajo debe configurarse para ejecutarse en tiempo real, pero también puede ejecutarse bajo demanda para actualizar las oportunidades abiertas.

Proporcione su [!DNL Marketo Measure] punto de contacto con el nombre del campo de cantidad de oportunidad personalizada. Actualizan el [!DNL Marketo Measure] Configuración de oportunidad de la aplicación para incluir el nombre del campo de cantidad de oportunidad personalizada. Esto indica a Discover qué campo utilizar en el sistema de informes.

**#2 DE FLUJO DE TRABAJO**: oportunidad, actualización [!DNL Marketo Measure] Campo de importe de oportunidad y campo personalizado = Ingresos reales

Este flujo de trabajo se inicia cuando un usuario cierra una oportunidad y actualiza la [!DNL Marketo Measure] Importe de oportunidad y el campo personalizado con los ingresos reales agregados al formulario Cierre de oportunidad antes de que la oportunidad se bloquee como cerrada.

## Parte 2: Fecha de cierre estimada frente a fecha de cierre real {#part-estimated-close-date-vs-actual-close-date}

De forma predeterminada, los datos de ingresos de la canalización no están disponibles en el panel porque, de forma predeterminada, Dynamics tiene dos campos de fecha de cierre de existencias: Fecha de cierre estimada y Fecha de cierre real. [!DNL Marketo Measure] solo puede señalar a un campo de fecha de cierre del panel y señala a la fecha de cierre real.

Si las oportunidades abiertas no tienen datos en el campo Fecha de cierre real, no hay datos en el panel para las oportunidades abiertas. Dicho esto, se necesita un flujo de trabajo basado en la fase de oportunidad para admitir ambos campos de fecha.

1. Crear campo de fecha de cierre personalizado en el objeto de oportunidad ([!DNL Marketo Measure] Fecha de cierre personalizada).
1. Cree un flujo de trabajo para actualizar [!DNL Marketo Measure] Campo Fecha de cierre personalizada con la fecha desde la fecha de cierre estimada o la fecha de cierre real, dependiendo de si la oportunidad está abierta o cerrada (el flujo de trabajo debe guardarse para ejecutarse en tiempo real, pero debe ejecutarse &quot;bajo demanda&quot; al menos una vez para actualizar todas las operaciones abiertas actuales).
1. Pruebe el flujo de trabajo y confirme que funciona.
1. El cliente debe proporcionar el nombre personalizado de la API de fecha de cierre a [!DNL Marketo Measure].
1. [!DNL Marketo Measure] para actualizar el [!DNL Marketo Measure] configuración de la aplicación para que apunte a [!DNL Marketo Measure] Campo Fecha de cierre personalizado en el panel.

   Una vez completados los pasos anteriores, ejecute los flujos de trabajo para actualizar tanto el personalizado [!DNL Marketo Measure] Importe de operación y el campo [!DNL Marketo Measure] Campo Fecha de cierre personalizada en las oportunidades históricas para reflejar los datos correctos. Es probable que esto cambie los campos modificados en/por, por lo que debe consultar con su equipo para ver si esto presenta algún problema.

Para actualizar las oportunidades cerradas...

1. Aísle las oportunidades que se han cerrado desde la [!DNL Marketo Measure] la fecha de inicio hasta que el flujo de trabajo esté activo. Este es el grupo de oportunidades históricas que debe actualizar mediante un flujo de trabajo.
1. Exportar todos los registros a Excel.
1. Abra el archivo de Excel y habilite el contenido.
1. Copiar datos de fecha de cierre real en [!DNL Marketo Measure] Fecha de cierre personalizada.
1. Copiar los datos de ingresos reales en [!DNL Marketo Measure] Importe de oportunidad personalizada **y** [!DNL Marketo Measure] Importe de oportunidad (hay dos campos).
1. Guarde el archivo.
1. Importar archivo. Dynamics lo reconocerá como un archivo con registros existentes para actualizar.
1. Compruebe si se han producido errores al importar el archivo.

>[!NOTE]
>
>Los flujos de trabajo descritos en este documento son solo una forma de actualizar los campos de forma que [!DNL Marketo Measure] Puede mostrar los datos correctos en Discover. Si tienes otra forma de lograr la misma tarea, puedes ir por ella. Básicamente, lo que necesitamos de ellos es algún tipo de flujo de trabajo que logre lo siguiente:
>
> * Si Opp = Abrir, actualice el campo de fecha de cierre personalizado, el campo de cantidad de opp personalizado y [!DNL Marketo Measure] opp para igualar la Fecha de cierre estimada y los Ingresos estimados, respectivamente.
> * Si Opp = Ganado cerrado, actualice el campo de fecha de cierre personalizado, el campo de cantidad de opp personalizado y [!DNL Marketo Measure] Campo de importe de operación para que sea igual a Fecha de cierre real e Ingresos reales, respectivamente.
