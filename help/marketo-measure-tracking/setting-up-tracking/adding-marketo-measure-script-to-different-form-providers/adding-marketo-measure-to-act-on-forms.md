---
unique-page-id: 18874753
description: Agregando [!DNL Marketo Measure] para actuar en Forms - [!DNL Marketo Measure]
title: Adición de  [!DNL Marketo Measure]  a formularios Act-On
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 6%

---

# Agregando [!DNL Marketo Measure] para actuar en Forms {#adding-marketo-measure-to-act-on-forms}

## Direcciones {#directions}

1. En el formulario que está editando, seleccione **[!UICONTROL Configuración]** en la esquina derecha.
1. Busque un área etiquetada como [!UICONTROL &quot;Análisis web externo&quot;.] Aquí será donde suelte el [!DNL Marketo Measure] fragmento de código de seguimiento.

## JavaScript de [!DNL Marketo Measure] {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>Puede que ya haya otros fragmentos de código de seguimiento en esta área, como [!DNL Google Analytics] código. Asegúrese de separarlos con un punto y coma `;` y un solo espacio, así:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
