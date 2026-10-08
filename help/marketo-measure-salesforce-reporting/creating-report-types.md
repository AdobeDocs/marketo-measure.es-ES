---
description: Creando guía de tipos de informes [!DNL Marketo Measure] personalizados para usuarios de Marketo Measure
title: Creando tipos de informe [!DNL Marketo Measure] personalizados
exl-id: 1d72a04f-6a2d-4607-ad09-3b025125156a
feature: Reporting
hidefromtoc: 'yes'
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: d24e0b99-7796-5c7d-831d-d71a1d725f01
    internal-label: Reporting
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 6%
---
# Creando tipos de informe [!DNL Marketo Measure] personalizados {#creating-custom-marketo-measure-report-types}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en la documentación, pero aún así ve &quot;[!DNL Bizible]&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

Aprenda a crear tipos de informes personalizados [!DNL Marketo Measure] [!DNL Salesforce]. Hay tres tipos de informes diferentes que recomendamos crear: Posibles clientes con puntos de contacto del comprador (personalizado), [!DNL Marketo Measure] persona con puntos de contacto del comprador (personalizado), Oportunidades con Buyer Attribution Touchpoint (personalizado).

## Posibles clientes con puntos de contacto del comprador (personalizado) {#leads-with-buyer-touchpoints-custom}

1. Vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Compilación]** > **[!UICONTROL Tipos de informes]** > **[!UICONTROL Nuevos tipos de informes personalizados]**.

   ![1. Ir a Configurar tipos de informes de compilación Nuevo](assets/new-types-1.png)

1. Defina el Tipo de informe personalizado.

   * [!UICONTROL Enfoque de tipo de informe] > [!UICONTROL [!UICONTROL Objeto principal]]: posible cliente
   * Identificación > [!UICONTROL Etiqueta de tipo de informe]: posibles clientes con puntos de contacto del comprador (personalizado)
   * [!UICONTROL Almacenar en categoría]: otros informes
   * [!UICONTROL Implementación] > [!UICONTROL Estado de implementación]: implementado

   ![Estado de implementación: implementado](assets/new-types-10.jpg)

1. Definir las relaciones de objetos.

   * Relacione el objeto de posible cliente (A) con el objeto de persona [!DNL Marketo Measure] (B) y, a continuación, con el objeto de Buyer Touchpoint (C)
   * Asegúrese de que &quot;[!UICONTROL Cada registro A/B debe tener al menos un registro B/C]&quot; seleccionado
   * [!UICONTROL Guardar]

   ![Guardar](assets/new-types-11.png)

## [!DNL Marketo Measure] persona con puntos de contacto de comprador (personalizado) {#marketo-measure-person-with-buyer-touchpoints-custom}

1. Vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Compilación]** > **[!UICONTROL Tipos de informes]** > **[!UICONTROL Nuevos tipos de informes personalizados]**.

   ![1. Ir a Configurar tipos de informes de compilación Nuevo](assets/new-types-12.png)

1. Defina el Tipo de informe personalizado.

   * [!UICONTROL Enfoque de tipo de informe] > [!UICONTROL Objeto principal]: [!DNL Marketo Measure] personas
   * [!UICONTROL Identificación] > [!UICONTROL Etiqueta de tipo de informe]: [!DNL Marketo Measure] persona con puntos de contacto de comprador (personalizada)
   * [!UICONTROL Almacenar en categoría]: otros informes
   * [!UICONTROL Implementación] > [!UICONTROL Estado de implementación]: implementado

   ![Estado de implementación: implementado](assets/new-types-13.jpg)

1. Definir las relaciones de objetos.

   * Relacionar el objeto de persona [!DNL Marketo Measure] (A) con el objeto de Buyer Touchpoint (B)
   * Asegúrese de que &quot;[!UICONTROL Cada registro A debe tener al menos un registro B]&quot; seleccionado
   * [!UICONTROL Guardar]

   ![Guardar](assets/new-types-9.png)

## Oportunidades con Buyer Attribution Touchpoint (personalizado) {#opportunities-with-buyer-attribution-touchpoint-custom}

1. Vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Compilación]** > **[!UICONTROL Tipos de informes]** > **[!UICONTROL Nuevos tipos de informes personalizados]**.

   ![1. Ir a Configurar tipos de informes de compilación Nuevo](assets/new-types-8.png)

1. Defina el Tipo de informe personalizado.

   * [!UICONTROL Enfoque del tipo de informe] > [!UICONTROL Objeto principal]: Oportunidades
   * [!UICONTROL Identificación] > [!UICONTROL Etiqueta de tipo de informe]: oportunidades con Buyer Attribution Touchpoint (personalizado)
   * [!UICONTROL Almacenar en categoría]: otros informes
   * [!UICONTROL Implementación] > [!UICONTROL Estado de implementación]: implementado

   ![Estado de implementación: implementado](assets/new-types-14.jpg)

1. Definir las relaciones de objetos.

   * Relacione el objeto Oportunidades (A) con el objeto Buyer Attribution Touchpoint (B)
   * Asegúrese de que &quot;[!UICONTROL Cada registro A debe tener al menos un registro B]&quot; seleccionado
   * [!UICONTROL Guardar]

   ![Guardar](assets/new-types-15.png)

## Adición de campos personalizados a tipos de informes personalizados {#adding-custom-fields-to-custom-report-types}

1. Una vez creados los informes, se le redirigirá a una descripción general del tipo de informe. Haga clic en **[!UICONTROL Editar diseño]**.

   ![1. Una vez creados los informes, se le redirigirá a ](assets/new-types-2.png)

1. Asegúrese de que los campos personalizados que desee agregar al informe aparezcan en la sección Propiedades de diseño de campo. Si desea agregar otros campos, use la opción &quot;[!UICONTROL Agregar campos relacionados mediante la búsqueda]&quot;.

   ![1. Asegúrese de que los campos personalizados que desea agregar a ](assets/new-types-3.png)
