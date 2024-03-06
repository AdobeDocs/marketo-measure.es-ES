---
unique-page-id: 18874759
description: Agregando [!DNL Marketo Measure] hasta [!DNL Hubspot] - [!DNL Marketo Measure]
title: Agregando [!DNL Marketo Measure] hasta [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 1%

---

# Agregando [!DNL Marketo Measure] hasta [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

Obtenga información sobre cómo añadir el [!DNL Marketo Measure] JavaScript para realizar un seguimiento de [!DNL Hubspot] páginas de aterrizaje y envíos de formularios.

Hubspot es un poco diferente de otros sistemas de automatización de marketing en que puede alojar sus páginas de aterrizaje / formularios y su sitio web. Es importante tener en cuenta que las siguientes instrucciones son para tener [!DNL Marketo Measure] seguimiento de actividad en [!DNL Hubspot]Páginas alojadas por. Si alimenta su sitio web con un CMS que no sea [!DNL Hubspot] (por ejemplo, Wordpress), debe agregar la variable [!DNL Marketo Measure] JavaScript también a ese CMS.

>[!NOTE]
>
>Si va a implementar JavaScript a través de un proveedor de administración de etiquetas como [!DNL Google Tag Manager], no es necesario codificar manualmente el [!DNL Marketo Measure] JavaScript en el sitio web.

## Introducción {#getting-started}

Una vez que haya iniciado sesión en [!DNL Hubspot] cuenta de, siga estos pasos.

1. Vaya al contenido.

1. Clic **[!UICONTROL Configuración de contenido]**.

1. En [!UICONTROL Configuración de contenido], haga clic en el HTML Encabezado del sitio (consulte la imagen siguiente).

1. Añada la siguiente secuencia de comandos dentro de su `<header>`:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   Debería tener un aspecto similar al siguiente:

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>Puede que ya haya otros fragmentos de código de seguimiento en esta área, como un código de Google Analytics. Asegúrese de separarlos con un punto y coma `;` y un solo espacio, así:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
