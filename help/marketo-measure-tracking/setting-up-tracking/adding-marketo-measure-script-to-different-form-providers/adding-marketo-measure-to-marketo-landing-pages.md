---
unique-page-id: 18874755
description: 'Adición [!DNL Marketo Measure] a [!DNL Marketo] Páginas de aterrizaje: [!DNL Marketo Measure] - Documentación del producto'
title: Adición [!DNL Marketo Measure] a las páginas de aterrizaje de Marketo
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# Adición [!DNL Marketo Measure] a las páginas de aterrizaje de Marketo {#adding-marketo-measure-to-marketo-landing-pages}

Obtenga información sobre cómo añadir el seguimiento a [!DNL Marketo Engage] Páginas de aterrizaje, ya que requieren un tratamiento adicional. [!DNL Marketo Measure] JavaScript debe estar en su lugar tanto en la página de aterrizaje como en la [!DNL Marketo Engage] forma. Para ello, deberá cargar la variable [!DNL Marketo Measure] JavaScript en [!DNL Marketo Engage] como se explica en las siguientes direcciones.

>[!NOTE]
>
>Si va a implementar JavaScript a través de un proveedor de administración de etiquetas como [!DNL Google Tag Manager], no es necesario agregar manualmente [!DNL Marketo Measure] JS a [!DNL Marketo Engage].

## Cómo añadir [!DNL Marketo Measure] Secuencia de comandos para [!DNL Marketo Engage] Páginas de aterrizaje {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. Inicie sesión en su [!DNL Marketo Engage] cuenta.
1. Seleccione la página de aterrizaje y haga clic en **[!UICONTROL Editar borrador]**.
1. Arrastre el elemento HTML .
1. Introduzca la variable [!DNL Marketo Measure] JavaScript en [!UICONTROL head] sección:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Ejemplo en la captura de pantalla siguiente

1. Haga clic en **[!UICONTROL Guardar]**.

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## Notas adicionales {#additional-notes}

* Es posible que ya tenga otros fragmentos de código de seguimiento implementados, como un [!DNL Google Analytics] código. No hay problema con esto, solo asegúrese de separarlos con un punto y coma `;` y un espacio único. Un ejemplo de cómo sería esto es:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* Es probable que tenga varias plantillas de página de aterrizaje en uso, asegúrese de agregar el código a todas las plantillas que tengan formularios en ellas.

* A veces, al editar la plantilla para páginas de aterrizaje, debe volver a aprobar las páginas en las que se utiliza la página de aterrizaje. Este artículo explica [aprobación masiva](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html){target=&quot;_blank&quot;}.
