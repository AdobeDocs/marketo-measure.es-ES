---
unique-page-id: 18874757
description: Adición [!DNL Marketo Measure] JavaScript a [!DNL Pardot] - [!DNL Marketo Measure] - Documentación del producto
title: Adición [!DNL Marketo Measure] JavaScript a [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Adición [!DNL Marketo Measure] JavaScript a [!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot] los formularios requieren un tratamiento adicional dentro de la plantilla de formulario, más allá de colocar la secuencia de comandos en el sitio para [!DNL Marketo Measure] para reconocer los envíos de formularios. El proceso es sencillo; solo requiere colocar la variable [!DNL Marketo Measure] secuencia de comandos de seguimiento en [!DNL Pardot] plantilla de formulario.

## Instrucciones paso a paso {#step-by-step-instructions}

Una vez que haya iniciado sesión en su [!DNL Pardot] siga los pasos a continuación.

1. Vaya a **[!UICONTROL Marketing]**.

1. Haga clic en **[!UICONTROL Páginas de aterrizaje]**.

1. Select **[!UICONTROL Plantilla de diseño]**.

   ![](assets/1-3.png)

1. Determine la plantilla de diseño adecuada y haga clic en **[!UICONTROL Editar]** a la derecha.

   ![](assets/2-1.png)

1. Copie y pegue el [!DNL Marketo Measure] Código JavaScript justo antes de la etiqueta de cierre del encabezado de la página HTML.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Siga estos pasos para todas las plantillas de diseño de página de aterrizaje aplicables.

1. Asegúrese de que la variable [!DNL Marketo Measure] JavaScript también se encuentra en la página del sitio general.

   Dentro de [!DNL Pardot] Plantilla de diseño, el código tendrá un aspecto similar al siguiente:

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## Notas adicionales {#additional-notes}

Si la variable [!DNL Pardot] IFrame tiene la siguiente etiqueta de HTML:

`<base href="http://go.pardot.com">`

_Y_ el propio IFrame se encuentra realmente en una página segura (HTTPS) en lugar de en una página no segura (HTTP), cuando intentamos cargar nuestro script en el [!DNL Pardot] IFrame, el navegador intentará cargar una versión HTTP de nuestro script en una página HTTPS que fallará y nos impedirá rastrear. La solución es actualizar el script en la variable [!DNL Pardot] IFrame para cargar la versión segura de nuestro script:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Además, es posible que ya haya otros fragmentos de código de seguimiento en esta área, como un [!DNL Google Analytics] código. Asegúrese de separarlos por punto y coma `;` y un espacio único, como se muestra en este ejemplo:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
