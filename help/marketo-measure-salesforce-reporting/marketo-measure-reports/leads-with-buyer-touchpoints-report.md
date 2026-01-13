---
description: Informe de posibles clientes con puntos de contacto del comprador - [!DNL Marketo Measure]
title: Informe de posibles clientes con puntos de contacto del comprador
exl-id: 0376abb0-5eed-41bb-ab4f-3c204ab437df
feature: Touchpoints, Reporting
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 7%

---


# Informe de posibles clientes con puntos de contacto del comprador {#leads-with-buyer-touchpoints-report}

>[!NOTE]
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en la documentación, pero aún así ve &quot;[!DNL Bizible]&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

De serie, tiene muchas capacidades de creación de informes al alcance de su mano cuando se trata de [!DNL Marketo Measure], pero hay algunos tipos de informes adicionales que recomendamos crear. Obtenga información sobre la creación de posibles clientes inclusivos con puntos de contacto del comprador, escriba a continuación.

1. Vaya a la opción de instalación en [!DNL Salesforce]. Desde allí, expanda la agrupación &quot;Crear&quot; y seleccione **[!UICONTROL Tipos de informes]**.

   ![Página de tipos de informes de Salesforce que muestra los posibles clientes con la configuración de puntos de contacto del comprador](assets/1.jpg)

1. Seleccione **[!UICONTROL Nuevo tipo de informe personalizado]**.

   ![Nuevo asistente de tipo de informe personalizado en Salesforce](assets/2.jpg)

1. Establece el objeto principal como &quot;Posibles clientes&quot; y dentro de la entrada &quot;Etiqueta de tipo de informe&quot;, introduce &quot;Posibles clientes con puntos de contacto de comprador - Incluido&quot;. Almacene el informe dentro de la categoría &quot;Posibles clientes&quot; y cambie el estado de implementación a **[!UICONTROL Implementado]**. Luego selecciona **[!UICONTROL Siguiente]**.

   ![Detalles del tipo de informe con posibles clientes como objeto principal](assets/3.jpg)

1. Para las relaciones de objeto, seleccione el objeto **[!DNL Marketo Measure]Persons** como objeto secundario. Seleccione la relación A a B como: &quot;Cada registro &#39;A&#39; debe tener al menos un registro &#39;B&#39; relacionado&quot;. A partir de ahí, relacionará el objeto &quot;Buyer Touchpoint&quot; y seleccionará la misma relación entre los objetos B y C.

   ![Selección de relación de objetos que incluye puntos de contacto de compradores y personas de Marketo Measure](assets/4.jpg)

1. Guarde y empiece a crear algunos informes.
