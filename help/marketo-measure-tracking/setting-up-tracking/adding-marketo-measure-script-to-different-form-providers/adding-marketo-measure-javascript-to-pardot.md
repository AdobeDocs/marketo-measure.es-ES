---
unique-page-id: 18874757
description: Agregando [!DNL Marketo Measure] JavaScript a [!DNL Pardot] - [!DNL Marketo Measure]
title: Agregando [!DNL Marketo Measure] JavaScript a [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%

---

# Agregando [!DNL Marketo Measure] JavaScript a [!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot] los formularios requieren un control adicional dentro de la plantilla de formulario, aparte de colocar secuencias de comandos en el sitio para [!DNL Marketo Measure] para reconocer los envíos de formularios. El proceso es sencillo; solo es necesario colocar el [!DNL Marketo Measure] script de seguimiento en [!DNL Pardot] plantilla de formulario.

## Instrucciones paso a paso {#step-by-step-instructions}

Una vez que haya iniciado sesión en [!DNL Pardot] cuenta de, siga los pasos a continuación.

1. Vaya a **[!UICONTROL Marketing]**.

1. Clic **[!UICONTROL Páginas de aterrizaje]**.

1. Seleccionar **[!UICONTROL Plantilla de diseño]**.

   ![](assets/1-3.png)

1. Determine la plantilla de diseño adecuada y haga clic en **[!UICONTROL Editar]** a la derecha.

   ![](assets/2-1.png)

1. Copie y pegue [!DNL Marketo Measure] Código JavaScript justo antes de la etiqueta de encabezado close en la página del HTML.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Siga estos pasos para todas las plantillas de diseño de página de aterrizaje aplicables.

1. Asegúrese de que la [!DNL Marketo Measure] JavaScript también se encuentra en la página del sitio general.

   Dentro de [!DNL Pardot] Plantilla de diseño, el código tiene este aspecto:

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## Notas adicionales {#additional-notes}

Si la variable [!DNL Pardot] IFrame tiene la siguiente etiqueta de HTML:

`<base href="http://go.pardot.com">`

_Y_ el IFrame en sí es en realidad una página segura (HTTPS) en lugar de no segura (HTTP) al cargar el script en [!DNL Pardot] IFrame, el explorador intenta cargar una versión HTTP del script en una página HTTPS, lo que producirá un error y romperá el seguimiento. La solución consiste en actualizar la secuencia de comandos en la [!DNL Pardot] IFrame para cargar la versión segura del script:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Puede que ya haya otros fragmentos de código de seguimiento en esta área, como [!DNL Google Analytics] código. Asegúrese de separarlos con un punto y coma `;` y un solo espacio, como se muestra en este ejemplo:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
