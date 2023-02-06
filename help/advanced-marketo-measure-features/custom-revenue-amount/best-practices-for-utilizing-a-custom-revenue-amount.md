---
description: 'Prácticas recomendadas para utilizar una cantidad de ingresos personalizada: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para utilizar una cantidad de ingresos personalizada
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 0%

---

# Prácticas recomendadas para utilizar una cantidad de ingresos personalizada {#best-practices-for-utilizing-a-custom-revenue-amount}

## Resumen {#overview}

La funcionalidad principal de [!DNL Marketo Measure] es la capacidad de asignar crédito por ingresos a los puntos de contacto de marketing a través del recorrido del comprador. La clave para una atribución de ingresos precisa es la capacidad de [!DNL Marketo Measure] para hacer referencia a la cantidad de ingresos correcta en una oportunidad, que a su vez se distribuye entre los puntos de contacto de marketing a través de los distintos modelos de atribución.

A menos que se especifique lo contrario durante la implementación, su [!DNL Marketo Measure] se establecerá para hacer referencia a la cantidad de oportunidad estándar (predeterminada de SFDC) para la atribución de ingresos. Sin embargo, para muchos [!DNL Marketo Measure] cuentas, este campo no refleja la cantidad exacta de ingresos para Oportunidades. En estos casos, [!DNL Marketo Measure] ofrece la capacidad de configurar un importe de ingresos personalizado para [!DNL Marketo Measure] para hacer referencia a los puntos de contacto de atribución (MTD) y distribuirlos entre ellos.

## Práctica recomendada {#best-practice}

Al configurar un importe de ingresos personalizado, tenga en cuenta las siguientes prácticas recomendadas para garantizar que su [!DNL Marketo Measure] los datos de atribución son precisos y coherentes.

Cosas que hay que tener en cuenta:

* Seleccione el campo de ingresos que sea preciso y utilizado para todas las oportunidades
   * ARR o valor total del contrato que se recomienda
* No utilizar un campo de fórmula
* Si utiliza un importe de ingresos personalizado para conversiones de moneda, la variable [!UICONTROL Múltiples monedas de Marketo Measure] en su lugar, la funcionalidad es el método preferido.
   * La variable [!DNL Marketo Measure] La funcionalidad Monedas múltiples hace referencia a las tasas de conversión establecidas en [!DNL Salesforce] para garantizar de la mejor manera la alineación entre las conversiones de moneda. Esto le permite seguir utilizando la cantidad estándar (predeterminada de SFDC) o cualquier otro campo de cantidad personalizado relacionado con la variable [!DNL Salesforce] tasas de conversión.
* Si actualiza el campo Importe que desea [!DNL Marketo Measure] para hacer referencia a , utilice el cargador de datos para actualizar las oportunidades anteriores y garantizar que los datos de ingresos sean coherentes y que el campo adecuado se rellene mediante el flujo de trabajo

## Práctica recomendada para mantenimiento {#best-practice-for-maintenance}

Al revisar la configuración anual de la cantidad de ingresos, se asegurará de que los datos de atribución sean precisos y estén alineados con el resto de los informes de ingresos de la organización.

Si utiliza un importe de ingresos personalizado, compruebe la configuración de ingresos de la siguiente manera.

* En [!DNL Marketo Measure] , vaya a[!UICONTROL Oportunidades]&#39; sección bajo CRM
* Identifique el [!UICONTROL Cantidad de oportunidad personalizada] Campo, aquí su [!UICONTROL API de importe de ingresos personalizados] el campo debe aparecer en la lista
* Confirme que este sigue siendo el campo correcto
* También tenga su [!DNL Salesforce] El administrador confirma que el flujo de trabajo de la cantidad de ingresos personalizada en [!DNL Salesforce] sigue en ejecución

Además de una revisión anual, algunos cambios en la organización pueden indicar la necesidad de revisar la configuración de la cantidad de ingresos...

* Volumen de negocio en su equipo de marketing
* Cambios en el campo Ingresos personalizados
* Cambios en la organización en la forma de informar de los ingresos

>[!MORELIKETHIS]
>
>* [Uso de un campo de importe de ingresos personalizado](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [Uso del cargador de datos para actualizar el campo Cantidad personalizada](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [Información general sobre monedas múltiples](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [Configuración de varias monedas](/help/advanced-marketo-measure-features/multi-currency/settings.md)

