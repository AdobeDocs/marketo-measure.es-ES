---
unique-page-id: 18874741
description: IFrame Forms y [!DNL Marketo Measure] - [!DNL Marketo Measure] - Documentación del producto
title: IFrame Forms y [!DNL Marketo Measure]
exl-id: fe8d7403-27be-4702-a1b6-d574e1243c0a
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 0%

---

# IFrame Forms y [!DNL Marketo Measure] {#iframe-forms-and-marketo-measure}

con [!DNL Marketo Measure] una de nuestras funcionalidades principales es el seguimiento de sus esfuerzos de marketing digital a través de sesiones en su sitio y envíos de formularios. Por lo general, cuando nuestro JavaScript se coloca en el sitio, se adjunta automáticamente a todos los formularios del sitio. Sin embargo, tenemos limitaciones de esta funcionalidad si el formulario está contenido en un IFrame.

Puede considerar un IFrame como una página dentro de una página, de modo que, al solicitar que se añada nuestro script a todas las páginas de su sitio, necesitaríamos el script colocado dentro del IFrame para asegurarnos de que estamos realizando el seguimiento.

En muchos casos, vemos que IFrame se administra a través de un proveedor de automatización de marketing, por lo que tendrá que configurarlo dentro de esa plataforma o a través de su proveedor de formularios.

Se recomienda colocar el JavaScript dentro del encabezado del IFrame y desde allí se adjuntarán automáticamente a los formularios dentro de ese marco.

![](assets/1-1.png)

Si tiene alguna duda sobre cómo agregar nuestro JavaScript a los formularios IFrame, póngase en contacto con su gestor de éxito de clientes o [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}.
