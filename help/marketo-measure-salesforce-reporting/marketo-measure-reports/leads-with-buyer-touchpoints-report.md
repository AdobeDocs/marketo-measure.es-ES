---
unique-page-id: 18874614
description: Informe de posibles clientes con puntos de contacto del comprador - [!DNL Marketo Measure]
title: Informe de posibles clientes con puntos de contacto del comprador
exl-id: 0376abb0-5eed-41bb-ab4f-3c204ab437df
feature: Touchpoints, Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 8%

---

# Informe de posibles clientes con puntos de contacto del comprador {#leads-with-buyer-touchpoints-report}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en la documentación, pero sigue viendo &quot;[!DNL Bizible]&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

De serie, tiene muchas funciones de creación de informes al alcance de su mano en lo que respecta a [!DNL Marketo Measure], pero hay algunos tipos de informes adicionales que recomendamos crear. Obtenga información sobre la creación de posibles clientes inclusivos con puntos de contacto del comprador, escriba a continuación.

1. Vaya a la opción de configuración en [!DNL Salesforce]. Desde allí, expanda la agrupación &quot;Crear&quot; y seleccione **[!UICONTROL Tipos de informes]**.

   ![](assets/1.jpg)

1. Seleccionar **[!UICONTROL Nuevo tipo de informe personalizado]**.

   ![](assets/2.jpg)

1. Establece el objeto principal como &quot;Posibles clientes&quot; y dentro de la entrada &quot;Etiqueta de tipo de informe&quot;, introduce &quot;Posibles clientes con puntos de contacto de comprador - Incluido&quot;. Almacene el informe en la categoría &quot;Posibles clientes&quot; y cambie el estado de implementación a **[!UICONTROL Implementado]**. A continuación seleccione **[!UICONTROL Siguiente]**.

   ![](assets/3.jpg)

1. Para las relaciones de objeto, seleccione la **[!DNL Marketo Measure]Personas** como objeto secundario. Seleccione la relación A a B como: &quot;Cada registro &#39;A&#39; debe tener al menos un registro &#39;B&#39; relacionado&quot;. A partir de ahí, relacionará el objeto &quot;Punto de contacto del comprador&quot; y seleccionará la misma relación entre los objetos B y C.

   ![](assets/4.jpg)

1. Guarde y empiece a crear algunos informes.
