---
description: Prácticas recomendadas para utilizar una cantidad de ingresos personalizada - [!DNL Marketo Measure]
title: Prácticas recomendadas para utilizar un importe de ingresos personalizado
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
feature: Custom Revenue Amount
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 7%

---

# Prácticas recomendadas para utilizar un importe de ingresos personalizado {#best-practices-for-utilizing-a-custom-revenue-amount}

## Información general {#overview}

La funcionalidad principal de [!DNL Marketo Measure] es la capacidad de asignar crédito de ingresos a puntos de contacto de marketing durante todo el recorrido del comprador. La clave para una atribución de ingresos precisa es la capacidad de [!DNL Marketo Measure] para hacer referencia a la cantidad de ingresos correcta en una oportunidad, que a su vez se distribuye entre los puntos de contacto de marketing a través de los distintos modelos de atribución.

A menos que se especifique lo contrario durante la implementación, su [!DNL Marketo Measure] se establecerá para hacer referencia al importe de oportunidad estándar (valor predeterminado de SFDC) para la atribución de ingresos. Sin embargo, para muchos [!DNL Marketo Measure] Cuentas de, este campo no refleja la cantidad de ingresos exacta para Oportunidades. En estos casos, [!DNL Marketo Measure] ofrece la posibilidad de configurar un importe de ingresos personalizado para [!DNL Marketo Measure] para hacer referencia a los puntos de contacto de atribución (MTD) y distribuirlos.

## Práctica recomendada {#best-practice}

Al configurar un importe de ingresos personalizados, tenga en cuenta las siguientes prácticas recomendadas para garantizar que [!DNL Marketo Measure] los datos de atribución son precisos y coherentes.

Cosas que hay que tener en cuenta:

* Seleccione el campo de ingresos que sea preciso y se utilice para todas las oportunidades
   * ARR o valor total del contrato recomendado
* No utilice un campo de fórmula
* Si utiliza un importe de ingresos personalizado para las conversiones de moneda, la variable [!UICONTROL Varias monedas de Marketo Measure] en su lugar, es el método preferido.
   * El [!DNL Marketo Measure] La funcionalidad Varias monedas hace referencia a las tasas de conversión establecidas en [!DNL Salesforce] para garantizar mejor la alineación entre las conversiones de moneda. Esto le permite seguir utilizando el &quot;Importe&quot; estándar (valor predeterminado de SFDC) o cualquier otro campo de importe personalizado relacionado con la variable [!DNL Salesforce] tasas de conversión.
* Si actualiza el campo Cantidad, debe hacer lo siguiente [!DNL Marketo Measure] como referencia, utilice el cargador de datos para actualizar las oportunidades anteriores y garantizar que los datos de ingresos sean coherentes y que el campo adecuado se rellene a través del flujo de trabajo

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Revisar la configuración anual de la cantidad de ingresos garantizará que los datos de atribución sean precisos y estén alineados con el resto de los informes de ingresos de la organización.

Si utiliza un importe de ingresos personalizado, compruebe la configuración de ingresos de la siguiente manera.

* En su [!DNL Marketo Measure] cuenta, vaya a &#39;[!UICONTROL Oportunidades]&#39; en CRM
* Identificar el [!UICONTROL Importe de oportunidad personalizada] Field, aquí su [!UICONTROL API de importe de ingresos personalizados] el campo debe aparecer en la lista
* Confirme que sigue siendo el campo correcto.
* También tiene su [!DNL Salesforce] El administrador confirma que el flujo de trabajo Importe de ingresos personalizados en [!DNL Salesforce] sigue en ejecución

Además de una revisión anual, ciertos cambios organizativos pueden indicar la necesidad de revisar la configuración de la cantidad de ingresos...

* Rotación en su equipo de marketing
* Cambios en el campo Ingresos personalizados
* Cambios de organización en la forma en que se generan los informes de ingresos

>[!MORELIKETHIS]
>
>* [Uso de un campo de importe de ingresos personalizado](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [Uso del cargador de datos para actualizar el campo de cantidad personalizado](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [Información general sobre Multi-Currency](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [Configuración de varias monedas](/help/advanced-marketo-measure-features/multi-currency/settings.md)
