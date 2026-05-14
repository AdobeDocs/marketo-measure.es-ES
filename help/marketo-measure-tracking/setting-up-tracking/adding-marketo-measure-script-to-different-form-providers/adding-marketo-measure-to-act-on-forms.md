---
unique-page-id: 18874753
description: Agregando  [!DNL Marketo Measure] a Forms de inicio de sesión - [!DNL Marketo Measure]
title: Adición de  [!DNL Marketo Measure]  a formularios Act-On
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
TQID: https://experienceleague.adobe.com/BUdHiCxfaG7a8Tays-Oqg9ZJQjSZJMM4-ChPHuF0RCg
product_v2: id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 77
ht-degree: 6%

---

# Agregando [!DNL Marketo Measure] a Act-On Forms {#adding-marketo-measure-to-act-on-forms}

## Direcciones {#directions}

1. En el formulario que está editando, seleccione la opción **[!UICONTROL Configuración]** en la esquina derecha.
1. Busque un área denominada [!UICONTROL &quot;Análisis de Web externo&quot;.] Aquí es donde suelta el fragmento de código de seguimiento [!DNL Marketo Measure].

## JavaScript de [!DNL Marketo Measure] {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>Puede que ya haya otros fragmentos de código de seguimiento en esta área, como un código [!DNL Google Analytics]. Asegúrese de separarlos con un punto y coma `;` y un solo espacio, de este modo:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
