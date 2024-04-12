---
unique-page-id: 18874777
description: 'Configuración de modelo personalizado: Habilitar el seguimiento del historial de campos de  [!DNL Marketo Measure]'
title: 'Configuración de modelo personalizado: Habilitar el seguimiento del historial de campos'
exl-id: 70328e67-051b-4864-891b-b251e49859c2
feature: Custom Models
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: ht
source-wordcount: '312'
ht-degree: 100%

---

# Configuración de modelo personalizado: Habilitar el seguimiento del historial de campos {#custom-model-setup-enable-field-history-tracking}

## Por qué y cuándo habilitar el seguimiento del historial de campos {#why-and-when-to-enable-field-history-tracking}

Si decide incluir un campo personalizado como una fase en el modelo de atribución personalizado, el seguimiento del historial de campos **debe estar habilitado** para este campo. Si habilita el seguimiento del historial de campos, permitirá que [!DNL Salesforce] realice un seguimiento de cada vez que se edita el campo personalizado, y crea un registro en la tabla Historial de seguimiento. [!DNL Marketo Measure] puede descargar esa tabla y utilizar esta información para medir la hora y el día en que se produjo una “transición”. Sin el seguimiento del historial de campos, [!DNL Marketo Measure] no puede realizar un seguimiento de los cambios relacionados con este campo.

Si solo se utilizan las Fases de oportunidad o el [!UICONTROL Estado del posible cliente] en el modelo personalizado, no es necesario activar el seguimiento del historial de campos porque se rastreará automáticamente como una transición de fase.

Para habilitar el seguimiento del historial de campos, siga las instrucciones a continuación.

## Activar seguimiento del historial de campos {#enable-field-history-tracking}

>[!NOTE]
>
>Deberá ser administrador del sistema para realizar estos cambios en los campos del objeto de posible cliente/contacto/oportunidad.

1. Vaya al objeto donde se encuentra el campo personalizado y haga clic en el botón **[!UICONTROL Definir seguimiento de historial]**.

   ![](assets/1.png)

1. Seleccione los campos en los que desea rastrear los cambios.

   ![](assets/2.png)

[!DNL Marketo Measure] solo puede volver a importar un registro si observa que el registro se ha modificado recientemente. Técnicamente, los campos de fórmula no modifican un registro cuando cambia, ya que realizan el cálculo en segundo plano. Hemos visto problemas en los que se omite una regla porque [!DNL Marketo Measure] no vio el cambio de registro, por lo que se recomienda **no utilizar campos de fórmula en definiciones de reglas**. La solución consiste en crear un campo de texto y utilizar un flujo de trabajo para rellenar ese campo con el valor o el cálculo adecuados cada vez que se edita el registro o se ajusta a los criterios. Esto requiere que todos los registros se editen para que el flujo de trabajo pueda funcionar de forma retroactiva en registros antiguos.
