---
unique-page-id: 18874753
description: Adición [!DNL Marketo Measure] a Act-On Forms - [!DNL Marketo Measure] - Documentación del producto
title: Adición [!DNL Marketo Measure] a Act-On Forms
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 0%

---

# Adición [!DNL Marketo Measure] a Act-On Forms {#adding-marketo-measure-to-act-on-forms}

## Instrucciones {#directions}

1. En el formulario que esté editando, seleccione la opción **[!UICONTROL Configuración]** en la esquina derecha.
1. Buscar un área etiquetada [!UICONTROL &quot;Análisis web externo&quot;.] Aquí es donde suelta el [!DNL Marketo Measure] fragmento de código de seguimiento.

## [!DNL Marketo Measure] JavaScript {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>Puede que ya haya otros fragmentos de código de seguimiento en esta área, como un [!DNL Google Analytics] código. Asegúrese de separarlos con un punto y coma `;` y un solo espacio, como este:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
