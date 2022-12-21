---
unique-page-id: 18874771
description: Uso del cargador de datos para actualizar [!DNL Marketo Measure] Campo Importe personalizado - [!DNL Marketo Measure] - Documentación del producto
title: Uso del cargador de datos para actualizar el campo Cantidad personalizada de medida de Marketo
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Uso del cargador de datos para actualizar [!DNL Marketo Measure] Campo Importe personalizado {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure] recomienda utilizar el cargador de datos como una opción conveniente para actualizar los valores de oportunidad al utilizar un campo de ingresos personalizado (utilizamos el campo Importe fuera de la caja) en [!DNL Marketo Measure]. Se prefiere el cargador de datos en lugar de usar la variable [!DNL Marketo Measure] actualice la secuencia de comandos, ya que la secuencia de comandos requiere que los usuarios deshabiliten todas las reglas de validación de Salesforce mientras que la variable [!DNL Marketo Measure] se ejecuta la secuencia de comandos.

## Uso del cargador de datos para actualizar [!DNL Marketo Measure] Campo Importe personalizado{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. Cree una hoja de Excel con:

   * Id De Oportunidad
   * Campo Cantidad de oportunidad personalizada (campo de ingresos preferido)
   * [!DNL Marketo Measure] Campo Cantidad de oportunidad

1. Copie y pegue los valores del campo de ingresos preferido en el [!UICONTROL [!DNL Marketo Measure] Cantidad de oportunidad] campo . A continuación, actualice estas Opps usando el archivo .csv .

**_Como alternativa, puede entrar en Salesforce y utilizar una vista de lista personalizada para editar en masa todas las oportunidades..._**

1. Cree una vista Lista personalizada para todas las oportunidades.
1. Añadir un filtro para el campo de ingresos preferidos no está en blanco _y_ [!UICONTROL Marketo] El campo Medir cantidad de oportunidad está en blanco.
1. Haga clic en **[!UICONTROL Edición masiva]**, pero no cambies nada.
1. Haga clic en **[!UICONTROL Guardar]**. Esto déclencheur el flujo de trabajo para rellenar la variable [!DNL Marketo Measure] Campos Cantidad de oportunidad con el campo Ingresos de software .
