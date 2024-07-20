---
description: Prácticas recomendadas para utilizar una cantidad de ingresos personalizada - [!DNL Marketo Measure]
title: Prácticas recomendadas para utilizar un importe de ingresos personalizado
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
feature: Custom Revenue Amount
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 7%

---

# Prácticas recomendadas para utilizar un importe de ingresos personalizado {#best-practices-for-utilizing-a-custom-revenue-amount}

## Información general {#overview}

La funcionalidad principal de [!DNL Marketo Measure] es la capacidad de asignar crédito de ingresos a puntos de contacto de marketing a lo largo del recorrido del comprador. La clave para la atribución de ingresos precisa es la capacidad de [!DNL Marketo Measure] de hacer referencia a la cantidad de ingresos correcta en una oportunidad, la cual, a su vez, se distribuye entre los puntos de contacto de marketing a través de los distintos modelos de atribución.

A menos que se especifique lo contrario durante la implementación, la instancia de [!DNL Marketo Measure] se configurará para hacer referencia al importe de oportunidad estándar (valor predeterminado de SFDC) para la atribución de ingresos. Sin embargo, para muchas cuentas de [!DNL Marketo Measure], este campo no refleja la cantidad exacta de ingresos para Oportunidades. BAT En estos casos, [!DNL Marketo Measure] ofrece la capacidad de configurar una cantidad de ingresos personalizados para [!DNL Marketo Measure] a fin de que se haga referencia a los puntos de contacto de atribución (puntos de contacto) y se distribuyan entre ellos (puntos de contacto de atribución) (o puntos de contacto de atribución).

## Práctica recomendada {#best-practice}

Al configurar una cantidad de ingresos personalizados, tenga en cuenta las siguientes prácticas recomendadas para asegurarse de que los datos de atribución de [!DNL Marketo Measure] sean precisos y coherentes.

Cosas que hay que tener en cuenta:

* Seleccione el campo de ingresos que sea preciso y se utilice para todas las oportunidades
   * ARR o valor total del contrato recomendado
* No utilice un campo de fórmula
* Si está usando un importe de ingresos personalizado para las conversiones monetarias, la funcionalidad [!UICONTROL Marketo Measure en varias monedas] es el método preferido en su lugar.
   * La funcionalidad [!DNL Marketo Measure] múltiples monedas hace referencia a las tasas de conversión establecidas en [!DNL Salesforce] para garantizar mejor la alineación entre las conversiones de moneda. Esto le permite seguir utilizando el campo &quot;Importe&quot; estándar (valor predeterminado de SFDC) o cualquier otro campo de importe personalizado que esté relacionado con las tasas de conversión de [!DNL Salesforce].
* Si actualiza el campo Importe al que desea que [!DNL Marketo Measure] haga referencia, utilice el cargador de datos para actualizar las oportunidades anteriores a fin de garantizar que los datos de ingresos sean coherentes y que el campo adecuado se rellene mediante el flujo de trabajo

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Revisar la configuración anual de la cantidad de ingresos garantizará que los datos de atribución sean precisos y estén alineados con el resto de los informes de ingresos de la organización.

Si utiliza un importe de ingresos personalizado, compruebe la configuración de ingresos de la siguiente manera.

* En su cuenta de [!DNL Marketo Measure], vaya a la sección &#39;[!UICONTROL Oportunidades]&#39; en CRM
* Identifique el campo [!UICONTROL Importe de oportunidad personalizado], donde debería aparecer el campo [!UICONTROL API de importe de ingresos personalizados]
* Confirme que sigue siendo el campo correcto.
* Además, haga que su administrador [!DNL Salesforce] confirme que el flujo de trabajo Cantidad de ingresos personalizados en [!DNL Salesforce] aún se está ejecutando

Además de una revisión anual, ciertos cambios organizativos pueden indicar la necesidad de revisar la configuración de la cantidad de ingresos...

* Rotación en su equipo de marketing
* Cambios en el campo Ingresos personalizados
* Cambios de organización en la forma en que se generan los informes de ingresos

>[!MORELIKETHIS]
>
>* [Uso de un campo de monto de ingresos personalizado](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [Uso del cargador de datos para actualizar el campo de importe personalizado](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [Información general sobre Multi-Currency](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [Configuración de múltiples monedas](/help/advanced-marketo-measure-features/multi-currency/settings.md)
