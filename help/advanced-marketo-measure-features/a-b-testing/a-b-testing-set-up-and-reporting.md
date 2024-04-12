---
unique-page-id: 18874773
description: Configuración y creación de informes de pruebas A/B [!DNL Marketo Measure]
title: Configuración e informes de pruebas A/B
exl-id: 9a3f0731-5909-4fbf-a35a-9608ff561061
feature: A/B Testing
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: ht
source-wordcount: '415'
ht-degree: 100%

---

# Configuración e informes de pruebas A/B {#a-b-testing-set-up-and-reporting}

La integración de pruebas A/B de [!DNL Marketo Measure] le permite hacer un seguimiento del impacto de sus ingresos de [Optimizely](https://www.optimizely.com/){target="_blank"} y experimentos en el sitio de VWO. Este artículo contiene instrucciones sobre cómo añadir Secciones de prueba A/B de [!DNL Marketo Measure] a los diseños de páginas de Cliente potencial, [!UICONTROL Contacto], Caso y [!UICONTROL Oportunidad]. También se tratan las prácticas generales de creación de informes y recomendaciones para la ejecución de Tipos de informes A/B de [!DNL Marketo Measure].

## Configuración {#set-up}

Añada las Secciones de prueba A/B de [!DNL Marketo Measure] sobre cliente potencial, contacto, caso y oportunidad. La integración de pruebas A/B de [!DNL Marketo Measure] le permite hacer un seguimiento del impacto de sus ingresos de [Optimizely](https://www.optimizely.com/){target="_blank"} and [VWO](https://vwo.com/){target="_blank"} experimentos en el sitio.

1. Compruebe que está utilizando el paquete [!DNL Marketo Measure] v3.9 o posterior. Para ello, vaya a [!UICONTROL Salesforce] >[!UICONTROL Configurar] > [!UICONTROL Paquetes instalados].
1. Edite el diseño de la página de posible cliente y añada la lista relacionada de **[!DNL Marketo Measure]pruebas A/B** a la página.

   ![](assets/1.png)

1. Haga clic en el botón [!UICONTROL Llave inglesa]. Elimine el campo &quot;Id&quot; de stock de la lista de Campos seleccionados. Añada los campos **[!UICONTROL Experimento]**, **[!UICONTROL Variación]**, y **[!UICONTROL DateReported]**. Cambie de “[!UICONTROL ordenar por]” a **[!UICONTROL fecha del informe]** y seleccione **[!UICONTROL Descendente]** en la lista desplegable.

   ![](assets/2.png)

1. En [!UICONTROL Botones], desmarque **[!UICONTROL Nuevo]**.

   ![](assets/3.png)

1. Póngase en contacto con su representante de [!DNL Marketo Measure] o [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} para activar la función.

## Creación de informes {#reporting}

Los clientes tienen acceso a un par de Tipos de informes A/B de [!DNL Marketo Measure]que le permiten crear informes sobre pruebas A/B en relación con clientes potenciales, contactos y oportunidades:

* Pruebas A/B de [!DNL Marketo Measure]
* [!DNL Marketo Measure] Pruebas A/B con contacto
* Pruebas A/B de [!DNL Marketo Measure] con cliente potencial
* Pruebas A/B de [!DNL Marketo Measure] con oportunidad

![](assets/4.png)

Los tipos de informes A/B se utilizan para informar sobre qué cliente potencial, contacto u oportunidad se ha expuesto a una prueba A/B. Estos informes también muestran la cantidad de ingresos vinculados a una oportunidad expuesta a una prueba A/B.

Es importante tener en cuenta que Optimizely/VWO es una plataforma de variación de contenido y no un canal de marketing. Por lo tanto, estos tipos de informes A/B de [!DNL Marketo Measure] se usan de forma diferente a los informes de Buyer Touchpoint. Los tipos de informes de Buyer touchpoint se utilizan para comprender qué canal de marketing (publicidad de pago, web directa, social) condujo a un cliente potencial o contacto a una página específica. Sin embargo, los tipos de informes A/B de [!DNL Marketo Measure] no se pueden usar para informar sobre cómo una variación influyó en un cliente potencial o una oportunidad. Dado que una variación de prueba A/B no es un canal, los detalles de la variación no aparecen en el Buyer touchpoint.

Estos son algunos campos recomendados para usar en la creación de informes de una prueba A/B, con el fin de aumentar la claridad y la perspectiva:

* Cliente potencial convertido
* Experimento
* ID de experimento
* Variación
* ID de variación
* Fecha del informe

## Informes de ejemplo de [!DNL Salesforce] {#salesforce-example-reports}

Prueba A/B de **[!DNL Marketo Measure]con cliente potencial**

![](assets/5.png)

Prueba A/B de **[!DNL Marketo Measure]con oportunidad**

![](assets/6.png)
