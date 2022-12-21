---
unique-page-id: 18874777
description: Configuración de modelo personalizado - Activar el seguimiento del historial de campos - [!DNL Marketo Measure] - Documentación del producto
title: 'Configuración de modelo personalizado: activar el seguimiento del historial de campos'
exl-id: 70328e67-051b-4864-891b-b251e49859c2
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# Configuración de modelo personalizado: Habilitar el seguimiento del historial de campos {#custom-model-setup-enable-field-history-tracking}

## Por qué y cuándo activar el seguimiento del historial de campos {#why-and-when-to-enable-field-history-tracking}

Si decide incluir un campo personalizado como etapa en el modelo de atribución personalizado, seguimiento del historial de campos **debe estar habilitado** para este campo. Habilitar el seguimiento del historial de campos permitirá [!DNL Salesforce] para realizar un seguimiento de cualquier momento en el que se edita el campo personalizado, cree un registro en la tabla Seguimiento del historial. [!DNL Marketo Measure] puede descargar esa tabla y utilizar esta información para medir la hora y el día en que se produjo una &quot;transición&quot;. Sin seguimiento del historial de campos, [!DNL Marketo Measure] no puede realizar el seguimiento de los cambios relacionados con este campo.

If only [!UICONTROL Estado de posible cliente] Para que los escenarios de oportunidad se utilicen en el modelo personalizado, no es necesario activar el seguimiento del historial de campos porque se rastreará automáticamente como una transición de etapa.

Para habilitar el seguimiento del historial de campos, siga las instrucciones que se indican a continuación.

## Habilitar el seguimiento del historial de campos {#enable-field-history-tracking}

>[!NOTE]
>
>Debe ser administrador del sistema para realizar estos cambios en los campos del objeto posible cliente/contacto/oportunidad.

1. Vaya al objeto en el que se encuentra el campo personalizado y haga clic en el botón **[!UICONTROL Configurar el seguimiento del historial]** botón.

   ![](assets/1.png)

1. Seleccione los campos en los que desea realizar el seguimiento de los cambios.

   ![](assets/2.png)

[!DNL Marketo Measure] solo puede volver a importar un registro si ve que el registro se ha modificado recientemente. Técnicamente, los campos de fórmula no modifican un registro cuando cambia, ya que realiza el cálculo en segundo plano. Hemos visto problemas en los que una regla se salta porque [!DNL Marketo Measure] no ha visto el cambio de registro, por lo que se recomienda que **no utilizar campos de fórmula en definiciones de regla**. La solución es crear un campo de texto y utilizar un flujo de trabajo para rellenar ese campo con el valor o cálculo adecuados cada vez que se edita el registro o se ajusta a los criterios. Esto requiere que todos los registros se editen para que el flujo de trabajo pueda funcionar retroactivamente en registros antiguos.
