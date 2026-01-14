---
description: Agregando  [!DNL Marketo Measure] a las directrices de Forms para actuar en consecuencia para los usuarios de Marketo Measure
title: Adición de  [!DNL Marketo Measure]  a formularios Act-On
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 6%

---

# Agregando [!DNL Marketo Measure] a Act-On Forms {#adding-marketo-measure-to-act-on-forms}

## Direcciones {#directions}

1. En el formulario que está editando, seleccione la opción **[!UICONTROL Configuración]** en la esquina derecha.
1. Busque un área etiquetada [!UICONTROL  como &quot;Análisis de web externo&quot;.] Aquí es donde suelta el fragmento de código de seguimiento [!DNL Marketo Measure].

## JavaScript de [!DNL Marketo Measure] {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>Puede que ya haya otros fragmentos de código de seguimiento en esta área, como un código [!DNL Google Analytics]. Asegúrese de separarlos con un punto y coma `;` y un solo espacio, de este modo:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
