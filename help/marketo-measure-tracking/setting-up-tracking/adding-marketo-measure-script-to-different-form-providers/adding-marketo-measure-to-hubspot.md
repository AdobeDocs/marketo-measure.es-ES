---
unique-page-id: 18874759
description: Agregando [!DNL Marketo Measure] a [!DNL Hubspot] - [!DNL Marketo Measure]
title: Agregando [!DNL Marketo Measure] a [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 1%

---

# Agregando [!DNL Marketo Measure] a [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

Aprenda a agregar el JavaScript [!DNL Marketo Measure] para rastrear sus [!DNL Hubspot] páginas de aterrizaje y envíos de formularios.

Hubspot es un poco diferente de otros sistemas de automatización de marketing en que puede alojar sus páginas de aterrizaje / formularios y su sitio web. Es importante tener en cuenta que las siguientes instrucciones son para que [!DNL Marketo Measure] realice un seguimiento de la actividad en [!DNL Hubspot] páginas hospedadas. Si enciende su sitio web con un CMS que no sea [!DNL Hubspot] (por ejemplo, Wordpress), también deberá agregar el JavaScript [!DNL Marketo Measure] a ese CMS.

>[!NOTE]
>
>Si está implementando JavaScript a través de un proveedor de administración de etiquetas como [!DNL Google Tag Manager], no necesita codificar manualmente el JavaScript [!DNL Marketo Measure] en su sitio web.

## Introducción {#getting-started}

Una vez que haya iniciado sesión en su cuenta de [!DNL Hubspot], siga estos pasos.

1. Vaya al contenido.

1. Haga clic en **[!UICONTROL Configuración de contenido]**.

1. En [!UICONTROL Configuración de contenido], haga clic en el HTML Encabezado del sitio (vea la imagen siguiente).

1. Agregue el siguiente script dentro de su `<header>`:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   Debería tener un aspecto similar al siguiente:

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>Puede que ya haya otros fragmentos de código de seguimiento en esta área, como un código de Google Analytics. Asegúrese de separarlos con un punto y coma `;` y un espacio, de esta manera:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
