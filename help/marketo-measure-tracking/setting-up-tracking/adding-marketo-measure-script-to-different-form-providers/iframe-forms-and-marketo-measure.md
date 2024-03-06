---
unique-page-id: 18874741
description: IFrame Forms y [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: Formularios IFrame y  [!DNL Marketo Measure]
exl-id: fe8d7403-27be-4702-a1b6-d574e1243c0a
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 20%

---

# Formularios IFrame y [!DNL Marketo Measure] {#iframe-forms-and-marketo-measure}

Con [!DNL Marketo Measure] una de las funcionalidades principales es el seguimiento de los esfuerzos de marketing digital a través de sesiones en el sitio y envíos de formularios. Por lo general, cuando se coloca Marketo JavaScript en el sitio, se adjunta automáticamente a todos los formularios del sitio. Sin embargo, esta funcionalidad tiene limitaciones si el formulario está contenido en un IFrame.

Piense en un IFrame como una página dentro de una página, por lo que, al igual que solicitamos que el script se agregue a todas las páginas del sitio, necesitaríamos el script colocado dentro del IFrame para asegurarnos de realizar el seguimiento.

En muchos casos, vemos que IFrame se administra a través de un proveedor de automatización de marketing, por lo que deberá configurarlo dentro de esa plataforma o a través de su proveedor de formularios.

Se recomienda colocar el JavaScript dentro del encabezado del IFrame y desde allí se adjuntará automáticamente a los formularios dentro de ese marco.

![](assets/1-1.png)

Si tiene alguna pregunta sobre la adición de JavaScript a los formularios de IFrame, póngase en contacto con el equipo de cuenta de Adobe (su administrador de cuentas) o [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
