---
unique-page-id: 18874771
description: Uso del cargador de datos para actualizar [!DNL Marketo Measure] Campo de importe personalizado - [!DNL Marketo Measure]
title: Uso del cargador de datos para actualizar el campo de cantidad personalizada de Marketo Measure
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
feature: Custom Revenue Amount
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 1%

---

# Uso del cargador de datos para actualizar [!DNL Marketo Measure] Campo de importe personalizado {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure] recomienda utilizar el cargador de datos como una opción conveniente para actualizar los valores de oportunidad al utilizar un campo de ingresos personalizado (utilizamos el campo Importe de forma predeterminada) en [!DNL Marketo Measure]. Se prefiere el cargador de datos en lugar de usar el [!DNL Marketo Measure] actualizar script, ya que el script requiere que los usuarios deshabiliten todas las reglas de validación de Salesforce mientras que la variable [!DNL Marketo Measure] se ejecuta el script.

## Uso del cargador de datos para actualizar [!DNL Marketo Measure] Campo de importe personalizado{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. Cree una hoja de Excel con:

   * ID de oportunidad
   * Campo Importe de oportunidad personalizada (su campo de ingresos preferido)
   * [!DNL Marketo Measure] Campo Importe de oportunidad

1. Copie y pegue los valores del campo de ingresos preferido en [!UICONTROL [!DNL Marketo Measure] Importe de oportunidad] field. A continuación, actualice estas opciones utilizando el archivo .csv.

**_También puede entrar en Salesforce y utilizar una vista de lista personalizada para editar en masa todas las oportunidades..._**

1. Cree una vista de lista personalizada para todas las oportunidades.
1. El campo Añadir un filtro para ingresos preferidos no está en blanco _y_ [!UICONTROL Marketo] El campo Importe de oportunidad de medida está en blanco.
1. Clic **[!UICONTROL Edición masiva]**, pero no cambies nada en realidad.
1. Haga clic en **[!UICONTROL Guardar]**. Esto almacenará en déclencheur el flujo de trabajo para rellenar la variable [!DNL Marketo Measure] Importe de oportunidad con el campo Ingresos de software.
