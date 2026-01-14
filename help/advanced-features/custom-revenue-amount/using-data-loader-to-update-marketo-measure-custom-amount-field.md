---
description: Uso del cargador de datos para actualizar la guía del campo de cantidad personalizada de Marketo Measure para los usuarios de Marketo Measure
title: Uso del cargador de datos para actualizar el campo de cantidad personalizada de Marketo Measure
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
feature: Custom Revenue Amount
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 1%

---

# Usando el cargador de datos para actualizar el campo de cantidad personalizada [!DNL Marketo Measure] {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure] recomienda usar el Cargador de datos como una opción conveniente para actualizar los valores de oportunidad al usar un campo de ingresos personalizado (se usa el campo Importe predeterminado) en [!DNL Marketo Measure]. Se prefiere el cargador de datos en lugar de usar el script de actualización [!DNL Marketo Measure], ya que el script requiere que los usuarios deshabiliten todas las reglas de validación de Salesforce mientras se ejecuta el script [!DNL Marketo Measure].

## Usando el cargador de datos para actualizar el campo de cantidad personalizada [!DNL Marketo Measure]{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. Cree una hoja de Excel con:

   * Identificación de oportunidad
   * Campo Importe de oportunidad personalizada (su campo de ingresos preferido)
   * [!DNL Marketo Measure] campo Cantidad de oportunidad

1. Copie y pegue los valores del campo de ingresos preferido en el campo [!UICONTROL [!DNL Marketo Measure] Importe de oportunidad]. A continuación, actualice estas opciones utilizando el archivo .csv.

**_También puede entrar en Salesforce y usar una vista de lista personalizada para editar en masa todas las oportunidades..._**

1. Cree una vista de lista personalizada para todas las oportunidades.
1. Agregar un filtro para el campo de ingresos preferidos no está en blanco _y_ [!UICONTROL El campo Importe de oportunidad de medida de Marketo] está en blanco.
1. Haga clic en **[!UICONTROL Edición masiva]**, pero no cambie nada.
1. Haga clic en **[!UICONTROL Guardar]**. Esto almacenará en déclencheur el flujo de trabajo para rellenar los campos de cantidad de oportunidad [!DNL Marketo Measure] con el campo de ingresos de software.
