---
unique-page-id: 18874755
description: 'Agregando [!DNL Marketo Measure] hasta [!DNL Marketo] Páginas de aterrizaje: [!DNL Marketo Measure]'
title: Adición de  [!DNL Marketo Measure]  a las páginas de destino de Marketo
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Agregando [!DNL Marketo Measure] a las páginas de aterrizaje de Marketo {#adding-marketo-measure-to-marketo-landing-pages}

Aprenda a añadir el seguimiento a [!DNL Marketo Engage] Páginas de aterrizaje, ya que requieren una administración adicional. [!DNL Marketo Measure] JavaScript debe estar configurado tanto en la página de aterrizaje como en la [!DNL Marketo Engage] forma en sí misma. Para ello, debe cargar el archivo [!DNL Marketo Measure] JavaScript en [!DNL Marketo Engage] como se explica en las siguientes direcciones.

>[!NOTE]
>
>Si va a implementar JavaScript a través de un proveedor de administración de etiquetas como [!DNL Google Tag Manager], no es necesario que añada manualmente [!DNL Marketo Measure] JS a [!DNL Marketo Engage].

## Cómo agregar [!DNL Marketo Measure] Script a [!DNL Marketo Engage] Páginas de aterrizaje {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. Inicie sesión en su [!DNL Marketo Engage] cuenta.
1. Seleccione la página de aterrizaje y haga clic en **[!UICONTROL Editar borrador]**.
1. Arrastre en el elemento HTML.
1. Introduzca el [!DNL Marketo Measure] JavaScript en la [!UICONTROL dirigir] sección:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Ejemplo en la captura de pantalla siguiente

1. Haga clic en **[!UICONTROL Guardar]**.

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## Notas adicionales {#additional-notes}

* Es posible que ya tenga otros fragmentos de código de seguimiento, como un [!DNL Google Analytics] código. No hay problema con esto, solo asegúrese de separarlos con un punto y coma `;` y un solo espacio. Un ejemplo de cómo se vería esto es:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* Es probable que tenga varias plantillas de página de aterrizaje en uso. Asegúrese de agregar el código a todas las plantillas que tengan formularios.

* A veces, cuando edita la plantilla para páginas de aterrizaje, debe volver a aprobar las páginas en las que utiliza la página de aterrizaje. Este artículo explica [cómo realizar la aprobación masiva](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html){target="_blank"}.
