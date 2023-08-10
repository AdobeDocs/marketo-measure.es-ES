---
unique-page-id: 18874773
description: Configuración e informes de pruebas A/B - [!DNL Marketo Measure] - Documentación del producto
title: Configuración e informes de pruebas A/B
exl-id: 9a3f0731-5909-4fbf-a35a-9608ff561061
feature: A/B Testing
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 4%

---

# Configuración e informes de pruebas A/B {#a-b-testing-set-up-and-reporting}

El [!DNL Marketo Measure] La integración de pruebas A/B le permite hacer un seguimiento del impacto de sus ingresos [Optimizely](https://optimizely.com/){target="_blank"} y experimentos en el sitio de VWO. En estas guías de artículo se proporcionan instrucciones sobre cómo agregar [!DNL Marketo Measure] Secciones de prueba A/B al posible cliente, [!UICONTROL Contacto], Case y [!UICONTROL Oportunidad] diseños de página. También explicaremos las prácticas generales de creación de informes y las recomendaciones para la ejecución de [!DNL Marketo Measure] Tipos de informes A/B.

## Configurar {#set-up}

Añada el [!DNL Marketo Measure] Secciones de prueba A/B sobre posible cliente, contacto, caso y oportunidad. [!DNL Marketo Measure] La integración de pruebas A/B le permite hacer un seguimiento del impacto de sus ingresos [Optimizely](https://optimizely.com/){target="_blank"} and [VWO](https://vwo.com/){target="_blank"} experimentos en el sitio.

1. Compruebe que está utilizando el paquete [!DNL Marketo Measure] v3.9 o posterior. Para ello, vaya a [!UICONTROL Salesforce] >[!UICONTROL Configurar] > [!UICONTROL Paquetes instalados].
1. Edite el diseño de la página de posible cliente y añada **[!DNL Marketo Measure]Pruebas A/B** Lista relacionada con la página.

   ![](assets/1.png)

1. Haga clic en [!UICONTROL Llave] botón. Elimine el campo &quot;Id&quot; de stock de la lista de Campos seleccionados. Añadir **[!UICONTROL Experimento]**, **[!UICONTROL Variación]**, y **[!UICONTROL DateReported]** campos. Cambiar &quot;[!UICONTROL Ordenar por]&quot; a **[!UICONTROL Fecha del informe]** y seleccione **[!UICONTROL Descendente]** en la lista desplegable.

   ![](assets/2.png)

1. En [!UICONTROL Botones], desmarque **[!UICONTROL Nuevo]**.

   ![](assets/3.png)

1. Póngase en contacto con su [!DNL Marketo Measure] rep o [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} para activar la función.

## Informes {#reporting}

Los clientes tienen acceso a un par de [!DNL Marketo Measure] Tipos de informes A/B que le permiten crear informes sobre pruebas A/B en relación con posibles clientes, contactos y oportunidades:

* [!DNL Marketo Measure] Pruebas A/B
* [!DNL Marketo Measure] Pruebas A/B con contacto
* [!DNL Marketo Measure] Pruebas A/B con posible cliente
* [!DNL Marketo Measure] Pruebas A/B con oportunidad

![](assets/4.png)

Los tipos de informes A/B se utilizan para informar sobre qué posible cliente, contacto u oportunidad se ha expuesto a una prueba A/B. Además, estos informes pueden mostrar la cantidad de ingresos vinculados a una oportunidad expuesta a una prueba A/B.

Es importante tener en cuenta que Optimizely/VWO es una plataforma de variación de contenido y no un canal de marketing. Por lo tanto, [!DNL Marketo Measure] Los tipos de informes A/B se usan de forma diferente a los informes de puntos de contacto del comprador. Los tipos de informes de punto de contacto del comprador se utilizan para comprender qué canal de marketing (por ejemplo, publicidad de pago, web directa, social) llevó a un posible cliente o contacto a una página específica. Sin embargo, [!DNL Marketo Measure] Los tipos de informes A/B no se pueden usar para informar sobre cómo una variación influyó en un posible cliente o una oportunidad. Además, como una variación de prueba A/B no es un canal, los detalles de la variación no aparecerán en el punto de contacto del comprador.

A continuación se indican algunos campos comunes que recomendamos utilizar al realizar informes en pruebas A/B para ayudar a aumentar la claridad y la perspectiva:

* Posible cliente convertido
* Experimento
* ID de experimento
* Variación
* ID de variación
* Fecha del informe

## [!DNL Salesforce] Informes de ejemplo {#salesforce-example-reports}

**[!DNL Marketo Measure]Prueba A/B con posible cliente**

![](assets/5.png)

**[!DNL Marketo Measure]Prueba A/B con oportunidad**

![](assets/6.png)
