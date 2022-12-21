---
unique-page-id: 18874562
description: Puntos de contacto y participación de posibles clientes PostLC - Medida de Marketo - Documentación del producto
title: Puntos de contacto de PostLC y participación de posible cliente
exl-id: 3ee5c571-195e-46c7-b150-fedcbc3614cb
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---

# Puntos de contacto de PostLC y participación de posible cliente {#postlc-touchpoints-and-lead-engagement}

[!DNL Marketo Measure] Los puntos de contacto posteriores a la creación de posibles clientes (PostLC) están disponibles para los clientes que utilizan modelos de atribución multitáctil (Forma W y superior). Cuando un posible cliente o contacto regresa a su sitio web y continúa rellenando formularios, estos envíos de formularios se registrarán como puntos de contacto de PostLC. Estos puntos de contacto le permiten ver qué contenido está impulsando a los posibles clientes a seguir interactuando con su sitio, mucho después de su primera conversión. Los puntos de contacto de PostLC comparten crédito de atribución con todos los puntos de contacto intermedios dentro de una Oportunidad; El 10% de crédito de atribución se asigna a puntos de contacto intermedios y se distribuye equitativamente entre todos los toques.

![](assets/1.png)

Puede ajustar el número de puntos de contacto de PostLC que se mostrarán en [!DNL SFDC]. Normalmente recomendamos impulsar hasta cinco puntos de contacto PostLC; cada punto de contacto ocupa 1 KB en [!DNL SFDC].

>[!NOTE]
>
>Las instrucciones para ajustar la configuración de los puntos de contacto de PostLC se encuentran al final de este artículo.

Los puntos de contacto PostLC son dinámicos. Como posible cliente o contacto continúa enviando formularios PostLC, [!DNL Marketo Measure] actualizará los puntos de contacto de PostLC en su CRM para mostrarle sus envíos de formularios más recientes. Específicamente, si ha establecido un límite de 5 puntos de contacto PostLC, [!DNL Marketo Measure] pulsar siempre 5 _más reciente_ puntos de contacto con su CRM.  En este ejemplo, esta cuenta ha establecido su límite de PostLC en cuatro puntos de contacto. Este posible cliente ya ha alcanzado el número máximo de puntos de contacto de PostLC que puede tener en su CRM. El último contacto de PostLC fue el 6/2/2018. Si esta persona rellenara otro formulario al día siguiente, [!DNL Marketo Measure] eliminará el primer punto de contacto de PostLC del 9/11/2017 para añadir el último punto de contacto del 7/2/2018.

![](assets/2.png)

>[!NOTE]
>
>[!DNL Marketo Measure] solo actualizará los puntos de contacto de PostLC en el posible cliente o contacto y no actualizará los puntos de contacto de atribución de PostLC en una oportunidad. Todos los puntos de contacto relevantes de PostLC en un Contacto se incluirán en la oportunidad.

## Cómo cambiar la configuración de los puntos de contacto de PostLC {#how-to-change-postlc-touchpoint-settings}

Para ajustar la configuración del punto de contacto de PostLC para sus posibles clientes o contactos, siga las instrucciones que se indican a continuación.

**Leads**

1. Inicie sesión en su [!DNL Marketo Measure] cuenta en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;} y vaya a [!UICONTROL Configuración].

1. En CRM, seleccione **[!UICONTROL Posibles clientes]**.

1. Introduzca el número de puntos de contacto postLC que desea insertar en los posibles clientes y haga clic en **[!UICONTROL Guardar]**.

   ![](assets/3.png)

**Contactos**

1. Inicie sesión en su [!DNL Marketo Measure] cuenta en [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;} y vaya a [!UICONTROL Configuración].

1. En CRM, seleccione **[!UICONTROL Contactos]**.

1. Introduzca el número de puntos de contacto postLC que desea insertar en sus contactos y haga clic en **[!UICONTROL Guardar]**.

   ![](assets/4.png)
