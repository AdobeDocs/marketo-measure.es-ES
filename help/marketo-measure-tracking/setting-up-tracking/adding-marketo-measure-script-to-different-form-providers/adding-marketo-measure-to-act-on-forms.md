---
unique-page-id: 18874753
description: Agregando [!DNL Marketo Measure] para actuar en Forms - [!DNL Marketo Measure] - Documentación del producto
title: Adición de  [!DNL Marketo Measure]  a formularios Act-On
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 10%

---

# Adición de [!DNL Marketo Measure] a formularios Act-On {#adding-marketo-measure-to-act-on-forms}

## Direcciones {#directions}

1. En el formulario que está editando, seleccione **[!UICONTROL Configuración]** en la esquina derecha.
1. Busque un área etiquetada como [!UICONTROL &quot;Análisis web externo&quot;.] Aquí será donde suelte el [!DNL Marketo Measure] fragmento de código de seguimiento.

## [!DNL Marketo Measure] JavaScript {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>Puede que ya haya otros fragmentos de código de seguimiento en esta área, como [!DNL Google Analytics] código. Asegúrese de separarlos con un punto y coma `;` y un solo espacio, así:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
