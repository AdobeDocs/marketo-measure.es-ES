---
description: Agregando  [!DNL Marketo Measure] JavaScript a [!DNL Pardot] - [!DNL Marketo Measure]
title: Agregando [!DNL Marketo Measure] JavaScript a [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 0%

---


# Agregando [!DNL Marketo Measure] JavaScript a [!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

Los formularios de [!DNL Pardot] requieren un control adicional dentro de la plantilla de formulario, además de colocar el script en el sitio para que [!DNL Marketo Measure] reconozca los envíos de formularios. El proceso es sencillo; solo es necesario colocar el script de seguimiento [!DNL Marketo Measure] en la plantilla de formulario [!DNL Pardot].

## Instrucciones paso a paso {#step-by-step-instructions}

Una vez que haya iniciado sesión en su cuenta de [!DNL Pardot], siga los pasos a continuación.

1. Vaya a **[!UICONTROL Marketing]**.

1. Haga clic en **[!UICONTROL Páginas de aterrizaje]**.

1. Seleccione **[!UICONTROL Plantilla de diseño]**.

   ![ 3](assets/1-3.png)

1. Determine la plantilla de diseño adecuada y haga clic en **[!UICONTROL Editar]** a la derecha.

   ![ 1](assets/2-1.png)

1. Copie y pegue el código de JavaScript [!DNL Marketo Measure] justo antes de la etiqueta de encabezado de cierre de la página de HTML.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Siga estos pasos para todas las plantillas de diseño de página de aterrizaje aplicables.

1. Asegúrese de que [!DNL Marketo Measure] JavaScript también se encuentra en la página del sitio general.

   En la plantilla de diseño [!DNL Pardot], el código tiene este aspecto:

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## Notas adicionales {#additional-notes}

Si [!DNL Pardot] IFrame tiene la siguiente etiqueta HTML:

`<base href="http://go.pardot.com">`

_Y_ el IFrame en sí es en realidad una página segura (HTTPS) en lugar de no segura (HTTP), al cargar el script en el IFrame [!DNL Pardot], el explorador intenta cargar una versión HTTP del script en una página HTTPS, lo que producirá un error y romperá el seguimiento. La solución consiste en actualizar el script en el IFrame [!DNL Pardot] para cargar la versión segura del script:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Puede que ya haya otros fragmentos de código de seguimiento en esta área, como un código [!DNL Google Analytics]. Asegúrese de separarlos con un punto y coma `;` y un espacio, como se muestra en este ejemplo:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
