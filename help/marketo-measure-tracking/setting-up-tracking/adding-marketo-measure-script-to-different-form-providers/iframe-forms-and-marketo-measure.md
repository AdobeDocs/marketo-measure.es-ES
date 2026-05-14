---
unique-page-id: 18874741
description: Formularios iframe y  [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: Formularios IFrame y  [!DNL Marketo Measure]
exl-id: fe8d7403-27be-4702-a1b6-d574e1243c0a
feature: Tracking
TQID: https://experienceleague.adobe.com/qR5a7F-h839nvcMRlQ6x6qjkQK3plhZO30aEzqxD00s
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 191
ht-degree: 86%

---

# Formularios IFrame y [!DNL Marketo Measure] {#iframe-forms-and-marketo-measure}

Una de las funcionalidades principales de [!DNL Marketo Measure] es el seguimiento de sus esfuerzos de marketing digital a través de sesiones en su sitio y envíos de formularios. Por lo general, cuando Marketo JavaScript se coloca en el sitio, se adjunta automáticamente a todos los formularios del sitio. Sin embargo, existen limitaciones de esta funcionalidad si el formulario está contenido en un iframe.

Puede considerar un iframe como una página dentro de una página, por lo que, al igual que se solicita que el script se añada a todas las páginas del sitio, es necesario colocar el script dentro del iframe para realizar el seguimiento.

En muchos casos, vemos que iframe se administra a través de un proveedor de automatización de marketing, por lo que deberá configurarlo dentro de esa plataforma o a través de su proveedor de formularios.

Se recomienda colocar el JavaScript dentro del encabezado del iframe y, a partir de ahí, se adjunta automáticamente a los formularios dentro de dicho marco.

![](assets/1-1.png)

Si tiene alguna pregunta sobre cómo agregar JavaScript a los formularios de IFrame, póngase en contacto con el equipo de cuenta de Adobe (su administrador de cuentas) o con el [equipo de asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
