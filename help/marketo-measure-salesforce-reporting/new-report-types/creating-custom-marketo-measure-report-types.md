---
unique-page-id: 18874539
description: Crear personalizado [!DNL Marketo Measure] Tipos de informes - [!DNL Marketo Measure] - Documentación del producto
title: Crear personalizado [!DNL Marketo Measure] Tipos de informes
exl-id: 1d72a04f-6a2d-4607-ad09-3b025125156a
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Crear personalizado [!DNL Marketo Measure] Tipos de informes {#creating-custom-marketo-measure-report-types}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero aún así ver &quot;[!DNL Bizible]&quot; en su CRM. Estamos trabajando para que esto se actualice y el cambio de marca se reflejará pronto en su CRM.

Obtenga información sobre cómo crear [!DNL Marketo Measure] [!DNL Salesforce] tipos de informes. Existen tres tipos de informes diferentes que se recomienda crear: Posibles clientes con puntos de contacto del comprador (personalizado), [!DNL Marketo Measure] Persona con puntos de contacto de comprador (personalizado), oportunidades con punto de contacto de atribución de comprador (personalizado).

## Posibles clientes con puntos de contacto del comprador (personalizado) {#leads-with-buyer-touchpoints-custom}

1. Vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Generar]** > **[!UICONTROL Tipos de informes]** > **[!UICONTROL Nuevos tipos de informes personalizados]**.

   ![](assets/1.png)

1. Defina el tipo de informe personalizado.

   * [!UICONTROL Enfoque del tipo de informe] > [!UICONTROL [!UICONTROL Objeto principal]]: Posible cliente
   * Identificación > [!UICONTROL Etiqueta de tipo de informe]: Posibles clientes con puntos de contacto del comprador (personalizado)
   * [!UICONTROL Almacenar en categoría]: Otros informes
   * [!UICONTROL Implementación] > [!UICONTROL Estado de implementación]: Implementado

   ![](assets/2.png)

1. Defina las relaciones de objeto.

   * Relacione el objeto Lead (A) con el [!DNL Marketo Measure] Objeto de persona (B) y, a continuación, al objeto de punto de contacto del comprador (C)
   * Asegúrese de que &quot;[!UICONTROL Cada registro A/B debe tener al menos un]&quot; registro seleccionado
   * [!UICONTROL Guardar]

   ![](assets/3.png)

## [!DNL Marketo Measure] Persona con puntos de contacto del comprador (personalizado) {#marketo-measure-person-with-buyer-touchpoints-custom}

1. Vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Generar]** > **[!UICONTROL Tipos de informes]** > **[!UICONTROL Nuevos tipos de informes personalizados]**.

   ![](assets/4.png)

1. Defina el tipo de informe personalizado.

   * [!UICONTROL Enfoque del tipo de informe] > [!UICONTROL Objeto principal]: [!DNL Marketo Measure] Personas
   * [!UICONTROL Identificación] > [!UICONTROL Etiqueta de tipo de informe]: [!DNL Marketo Measure] Persona con puntos de contacto del comprador (personalizado)
   * [!UICONTROL Almacenar en categoría]: Otros informes
   * [!UICONTROL Implementación] > [!UICONTROL Estado de implementación]: Implementado

   ![](assets/5.png)

1. Defina las relaciones de objeto.

   * Relacione la variable [!DNL Marketo Measure] Objeto de persona (A) al objeto de punto de contacto del comprador (B)
   * Asegúrese de que &quot;[!UICONTROL Cada registro A debe tener al menos una]&quot; registro seleccionado
   * [!UICONTROL Guardar]

   ![](assets/6.png)

## Oportunidades con punto de contacto de atribución del comprador (personalizado) {#opportunities-with-buyer-attribution-touchpoint-custom}

1. Vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Generar]** > **[!UICONTROL Tipos de informes]** > **[!UICONTROL Nuevos tipos de informes personalizados]**.

   ![](assets/7.png)

1. Defina el tipo de informe personalizado.

   * [!UICONTROL Enfoque del tipo de informe] > [!UICONTROL Objeto principal]: Oportunidades
   * [!UICONTROL Identificación] > [!UICONTROL Etiqueta de tipo de informe]: Oportunidades con punto de contacto de atribución del comprador (personalizado)
   * [!UICONTROL Almacenar en categoría]: Otros informes
   * [!UICONTROL Implementación] > [!UICONTROL Estado de implementación]: Implementado

   ![](assets/8.png)

1. Defina las relaciones de objeto.

   * Relacione el objeto Oportunidades (A) con el objeto Touchpoint de atribución de Comprador (B)
   * Asegúrese de que &quot;[!UICONTROL Cada registro A debe tener al menos una]&quot; registro seleccionado
   * [!UICONTROL Guardar]

   ![](assets/9.png)

## Adición de campos personalizados a tipos de informes personalizados {#adding-custom-fields-to-custom-report-types}

1. Una vez creados los informes, se le redirigirá a una descripción general del tipo de informe. Haga clic en **[!UICONTROL Editar diseño]**.

   ![](assets/10.png)

1. Asegúrese de que los campos personalizados que desea agregar al informe aparecen en la sección Propiedades del diseño de campo . Si hay otros campos que desee agregar, utilice la opción[!UICONTROL Adición de campos relacionados mediante búsqueda]&quot;.

   ![](assets/11.png)
