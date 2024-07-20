---
unique-page-id: 18874562
description: 'Puntos de contacto PostLC y participación del posible cliente: Marketo Measure, documentación del producto'
title: Puntos de contacto de PostLC y participación de posibles clientes
exl-id: 3ee5c571-195e-46c7-b150-fedcbc3614cb
feature: Touchpoints
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 3%

---

# Puntos de contacto de PostLC y participación de posibles clientes {#postlc-touchpoints-and-lead-engagement}

Los puntos de contacto de creación posterior al posible cliente (PostLC) de [!DNL Marketo Measure] están disponibles para los clientes que utilizan modelos de atribución multitáctil (W-Shape y posteriores). Cuando un posible cliente o contacto vuelve a su sitio web y continúa rellenando formularios, estos envíos de formularios se registran como puntos de contacto de PostLC. Estos puntos de contacto le permiten ver qué contenido está impulsando a los posibles clientes a seguir interactuando con el sitio mucho después de su primera conversión. Los puntos de contacto de PostLC comparten el crédito de atribución con todos los puntos de contacto intermedios dentro de una oportunidad; el 10 % del crédito de atribución se asigna a los puntos de contacto intermedios y se distribuye equitativamente entre todos los toques.

![](assets/1.png)

Puede ajustar el número de puntos de contacto PostLC que se muestran en [!DNL SFDC]. Normalmente, recomendamos insertar hasta cinco puntos de contacto PostLC; cada punto de contacto ocupa 1 KB en [!DNL SFDC].

>[!NOTE]
>
>Las instrucciones para ajustar la configuración del punto de contacto PostLC se encuentran al final de este artículo.

Los puntos de contacto de PostLC son dinámicos. A medida que un posible cliente o contacto continúa enviando formularios PostLC, [!DNL Marketo Measure] actualiza los puntos de contacto PostLC en su CRM para mostrarle los envíos de formularios más recientes. En concreto, si ha establecido un límite de 5 puntos de contacto PostLC, [!DNL Marketo Measure] siempre inserta los cinco puntos de contacto _más recientes_ en su CRM.  En este ejemplo, esta cuenta ha establecido su límite de PostLC en cuatro puntos de contacto. Este posible cliente ya ha alcanzado el número máximo de puntos de contacto PostLC que puede tener en su CRM. El último contacto con PostLC fue el 6/2/2018. Si esta persona rellenara otro formulario al día siguiente, [!DNL Marketo Measure] quitará el primer punto de contacto de PostLC a partir del 9/11/2017 para agregar el último punto de contacto a partir del 7/2/2018.

![](assets/2.png)

>[!NOTE]
>
>[!DNL Marketo Measure] solo actualiza los puntos de contacto PostLC en el posible cliente o contacto, y no actualiza los puntos de contacto de atribución PostLC en una oportunidad. Todos los puntos de contacto PostLC relevantes en un contacto se incluyen en la oportunidad.

## Cómo cambiar la configuración de PostLC Touchpoint {#how-to-change-postlc-touchpoint-settings}

Para ajustar la configuración del punto de contacto PostLC para sus posibles clientes o contactos, siga las instrucciones a continuación.

**Posibles clientes**

1. Inicia sesión en tu cuenta de [!DNL Marketo Measure] en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} y ve a [!UICONTROL Configuración].

1. En CRM, Seleccione **[!UICONTROL Posibles clientes]**.

1. Introduzca el número de puntos de contacto postLC que desee insertar en sus posibles clientes y haga clic en **[!UICONTROL Guardar]**.

   ![](assets/3.png)

**Contactos**

1. Inicia sesión en tu cuenta de [!DNL Marketo Measure] en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} y ve a [!UICONTROL Configuración].

1. En CRM, Seleccione **[!UICONTROL Contactos]**.

1. Escriba el número de puntos de contacto postLC que desee insertar en Contactos y haga clic en **[!UICONTROL Guardar]**.

   ![](assets/4.png)
