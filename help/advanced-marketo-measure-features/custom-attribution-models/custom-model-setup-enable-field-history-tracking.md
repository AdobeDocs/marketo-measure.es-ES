---
unique-page-id: 18874777
description: 'Configuración del modelo personalizado: habilitar el seguimiento del historial de campos [!DNL Marketo Measure] - Documentación del producto'
title: 'Configuración del modelo personalizado: habilitar el seguimiento del historial de campos'
exl-id: 70328e67-051b-4864-891b-b251e49859c2
feature: Custom Models
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---

# Configuración de modelo personalizado: Habilitar el seguimiento del historial de campos {#custom-model-setup-enable-field-history-tracking}

## Por qué y cuándo habilitar el seguimiento del historial de campos {#why-and-when-to-enable-field-history-tracking}

Si decide incluir un campo personalizado como escenario en el modelo de atribución personalizado, el seguimiento del historial de campos **debe estar habilitado** para este campo. Si habilita el seguimiento del historial de campos, permitirá [!DNL Salesforce] para realizar un seguimiento de cada vez que se edita el campo personalizado creando un registro en la tabla Historial de seguimiento. [!DNL Marketo Measure] Puede descargar esa tabla y utilizar esta información para medir la hora y el día en que se produjo una &quot;transición&quot;. Sin seguimiento del historial de campos, [!DNL Marketo Measure] no puede realizar un seguimiento de los cambios relacionados con este campo.

If only [!UICONTROL Estado del posible cliente] Para que las fases de oportunidad se utilicen en el modelo personalizado, no es necesario activar el seguimiento del historial de campos porque se rastreará automáticamente como una transición de fase.

Para habilitar el seguimiento del historial de campos, siga las instrucciones a continuación.

## Activar seguimiento de historial de campos {#enable-field-history-tracking}

>[!NOTE]
>
>Deberá ser administrador del sistema para realizar estos cambios en los campos del objeto de posible cliente/contacto/oportunidad.

1. Vaya al objeto donde se encuentra el campo personalizado y haga clic en **[!UICONTROL Definir seguimiento de historial]** botón.

   ![](assets/1.png)

1. Seleccione los campos en los que desea rastrear los cambios.

   ![](assets/2.png)

[!DNL Marketo Measure] sólo puede volver a importar un registro si observa que el registro se ha modificado recientemente. Técnicamente, los campos de fórmula no modifican un registro cuando cambia, ya que realizan el cálculo en segundo plano. Hemos visto problemas en los que se omite una regla porque [!DNL Marketo Measure] no vio el cambio de registro, por lo que se recomienda **no utilizar campos de fórmula en definiciones de reglas**. La solución consiste en crear un campo de texto y utilizar un flujo de trabajo para rellenar ese campo con el valor o el cálculo adecuados cada vez que se edita el registro o se ajusta a los criterios. Esto requiere que todos los registros se editen para que el flujo de trabajo pueda funcionar de forma retroactiva en registros antiguos.
