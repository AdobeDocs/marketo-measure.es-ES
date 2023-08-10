---
unique-page-id: 18874741
description: IFrame Forms y [!DNL Marketo Measure] - [!DNL Marketo Measure] - Documentación del producto
title: Formularios IFrame y  [!DNL Marketo Measure]
exl-id: fe8d7403-27be-4702-a1b6-d574e1243c0a
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 3%

---

# Formularios IFrame y [!DNL Marketo Measure] {#iframe-forms-and-marketo-measure}

Con [!DNL Marketo Measure] una de nuestras funcionalidades principales es el seguimiento de sus esfuerzos de marketing digital a través de sesiones en su sitio y envíos de formularios. Por lo general, cuando nuestro JavaScript se coloca en el sitio, se adjunta automáticamente a todos los formularios del sitio. Sin embargo, existen limitaciones de esta funcionalidad si el formulario está contenido en un IFrame.

Puede considerar un IFrame como una página dentro de una página, por lo que, al igual que solicitamos que el script se agregue a todas las páginas del sitio, necesitaríamos el script colocado dentro del IFrame para asegurarnos de realizar el seguimiento.

En muchos casos, vemos que IFrame se administra a través de un proveedor de automatización de marketing, por lo que deberá configurarlo dentro de esa plataforma o a través de su proveedor de formularios.

Se recomienda colocar el JavaScript dentro del encabezado del IFrame y, a partir de ahí, se adjuntará automáticamente a los formularios dentro de ese marco.

![](assets/1-1.png)

Si tiene alguna pregunta sobre la adición de JavaScript a los formularios de IFrame, póngase en contacto con el equipo de cuenta de Adobe (su administrador de cuentas) o [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
