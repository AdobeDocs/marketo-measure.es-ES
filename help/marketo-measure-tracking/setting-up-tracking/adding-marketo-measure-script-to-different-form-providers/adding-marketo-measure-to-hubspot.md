---
unique-page-id: 18874759
description: Adición [!DNL Marketo Measure] a [!DNL Hubspot] - [!DNL Marketo Measure] - Documentación del producto
title: Adición [!DNL Marketo Measure] a [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Adición [!DNL Marketo Measure] a [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

Obtenga información sobre cómo añadir la variable [!DNL Marketo Measure] JavaScript para realizar un seguimiento de su [!DNL Hubspot] páginas de aterrizaje y envíos de formularios.

Hubspot es un poco diferente de otros sistemas de automatización de marketing, ya que puede alojar sus páginas de aterrizaje/formularios Y su sitio web. Es importante tener en cuenta que las siguientes instrucciones son para tener [!DNL Marketo Measure] rastrear actividad en [!DNL Hubspot]páginas alojadas en . Si enciende su sitio web con un CMS que no sea [!DNL Hubspot] (por ejemplo, Wordpress), tendrá que agregar la variable [!DNL Marketo Measure] JavaScript también para ese CMS.

>[!NOTE]
>
>Si va a implementar JavaScript a través de un proveedor de administración de etiquetas como [!DNL Google Tag Manager], no es necesario que incruste manualmente el código de [!DNL Marketo Measure] JavaScript en el sitio web.

## Introducción {#getting-started}

Una vez que haya iniciado sesión en su [!DNL Hubspot] siga estos pasos.

1. Vaya a Contenido.

1. Haga clic en **[!UICONTROL Configuración de contenido]**.

1. Within [!UICONTROL Configuración de contenido], haga clic en el HTML Encabezado del sitio (consulte la imagen a continuación).

1. Añada la siguiente secuencia de comandos dentro de su `<header>`:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   Debería tener este aspecto:

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>Puede que ya haya otros fragmentos de código de seguimiento en esta área, como el código de Google Analytics. Asegúrese de separarlos por punto y coma `;` y un solo espacio, como este:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
