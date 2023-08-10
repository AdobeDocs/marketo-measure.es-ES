---
unique-page-id: 18874539
description: Crear Personalizado [!DNL Marketo Measure] Tipos de informes - [!DNL Marketo Measure] - Documentación del producto
title: Creación de tipos de informes personalizados de  [!DNL Marketo Measure]
exl-id: 1d72a04f-6a2d-4607-ad09-3b025125156a
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 2%

---

# Creación de tipos de informes personalizados de [!DNL Marketo Measure] {#creating-custom-marketo-measure-report-types}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero sigue viendo &quot;[!DNL Bizible]&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

Aprenda a crear formularios personalizados [!DNL Marketo Measure] [!DNL Salesforce] tipos de informes. Existen tres tipos de informes diferentes que recomendamos crear: Posibles clientes con puntos de contacto del comprador (personalizado), [!DNL Marketo Measure] Persona con puntos de contacto de comprador (personalizado), oportunidades con punto de contacto de atribución de comprador (personalizado).

## Posibles clientes con puntos de contacto del comprador (personalizado) {#leads-with-buyer-touchpoints-custom}

1. Ir a **[!UICONTROL Configurar]** > **[!UICONTROL Generar]** > **[!UICONTROL Tipos de informes]** > **[!UICONTROL Nuevos tipos de informes personalizados]**.

   ![](assets/1.png)

1. Defina el Tipo de informe personalizado.

   * [!UICONTROL Enfoque de tipo de informe] > [!UICONTROL [!UICONTROL Objeto principal]]: posible cliente
   * Identificación > [!UICONTROL Etiqueta de tipo de informe]: posibles clientes con puntos de contacto del comprador (personalizado)
   * [!UICONTROL Almacenar en categoría]: Otros informes
   * [!UICONTROL Implementación] > [!UICONTROL Estado de implementación]: implementado

   ![](assets/2.png)

1. Definir las relaciones de objetos.

   * Relacione el objeto del posible cliente (A) con el [!DNL Marketo Measure] Objeto Persona (B) y, a continuación, al objeto Touchpoint del comprador (C)
   * Asegúrese de que &quot;[!UICONTROL Cada registro A/B debe tener al menos un registro B/C]&quot; el registro está seleccionado
   * [!UICONTROL Guardar]

   ![](assets/3.png)

## [!DNL Marketo Measure] Persona con puntos de contacto de comprador (personalizado) {#marketo-measure-person-with-buyer-touchpoints-custom}

1. Ir a **[!UICONTROL Configurar]** > **[!UICONTROL Generar]** > **[!UICONTROL Tipos de informes]** > **[!UICONTROL Nuevos tipos de informes personalizados]**.

   ![](assets/4.png)

1. Defina el Tipo de informe personalizado.

   * [!UICONTROL Enfoque de tipo de informe] > [!UICONTROL Objeto principal]: [!DNL Marketo Measure] Personas
   * [!UICONTROL Identificación] > [!UICONTROL Etiqueta de tipo de informe]: [!DNL Marketo Measure] Persona con puntos de contacto de comprador (personalizado)
   * [!UICONTROL Almacenar en categoría]: Otros informes
   * [!UICONTROL Implementación] > [!UICONTROL Estado de implementación]: implementado

   ![](assets/5.png)

1. Definir las relaciones de objetos.

   * Relacione el [!DNL Marketo Measure] Objeto de persona (A) al objeto Touchpoint del comprador (B)
   * Asegúrese de que &quot;[!UICONTROL Cada registro A debe tener al menos uno B]&quot; el registro está seleccionado
   * [!UICONTROL Guardar]

   ![](assets/6.png)

## Oportunidades con el punto de contacto de atribución del comprador (personalizado) {#opportunities-with-buyer-attribution-touchpoint-custom}

1. Ir a **[!UICONTROL Configurar]** > **[!UICONTROL Generar]** > **[!UICONTROL Tipos de informes]** > **[!UICONTROL Nuevos tipos de informes personalizados]**.

   ![](assets/7.png)

1. Defina el Tipo de informe personalizado.

   * [!UICONTROL Enfoque de tipo de informe] > [!UICONTROL Objeto principal]: Oportunidades
   * [!UICONTROL Identificación] > [!UICONTROL Etiqueta de tipo de informe]: Oportunidades con el punto de contacto de atribución del comprador (personalizado)
   * [!UICONTROL Almacenar en categoría]: Otros informes
   * [!UICONTROL Implementación] > [!UICONTROL Estado de implementación]: implementado

   ![](assets/8.png)

1. Definir las relaciones de objetos.

   * Relacione el objeto de oportunidades (A) con el objeto de punto de contacto de atribución del comprador (B)
   * Asegúrese de que &quot;[!UICONTROL Cada registro A debe tener al menos uno B]&quot; el registro está seleccionado
   * [!UICONTROL Guardar]

   ![](assets/9.png)

## Adición de campos personalizados a tipos de informes personalizados {#adding-custom-fields-to-custom-report-types}

1. Una vez creados los informes, se le redirigirá a una descripción general del tipo de informe. Clic **[!UICONTROL Editar diseño]**.

   ![](assets/10.png)

1. Asegúrese de que los campos personalizados que desee agregar al informe aparezcan en la sección Propiedades de diseño de campo. Si desea añadir otros campos, utilice el campo &quot;[!UICONTROL Añadir campos relacionados mediante la búsqueda]Opción &quot;.

   ![](assets/11.png)
