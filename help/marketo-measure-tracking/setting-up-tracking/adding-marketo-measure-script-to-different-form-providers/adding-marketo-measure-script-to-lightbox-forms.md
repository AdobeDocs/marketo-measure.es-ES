---
unique-page-id: 18874519
description: Adición [!DNL Marketo Measure] Script a Lightbox Forms - [!DNL Marketo Measure] - Documentación del producto
title: Adición [!DNL Marketo Measure] Script a Lightbox Forms
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---

# Adición [!DNL Marketo Measure] Script a Lightbox Forms {#adding-marketo-measure-script-to-lightbox-forms}

Aprenda a añadir correctamente la variable [!DNL Marketo Measure] JavaScript a un formulario dentro de un lightbox.

Un lightbox abre un formulario delante del contenido cuando el visitante realiza una acción específica (p. ej., hacer clic en una parte concreta de la página, pasar un tiempo determinado en la página, etc.). Normalmente solo pedimos que se use la variable [!DNL Marketo Measure] JavaScript se coloca en el encabezado de la página de aterrizaje, pero para los formularios dentro de un lightbox se necesita un paso adicional.

Como un formulario dentro de Lightbox es básicamente un formulario dentro de un iFrame, necesitaremos que nuestro script se coloque dentro de ese iFrame.

En primer lugar, busque el iFrame en la [!UICONTROL lightbox] form vive en.

![](assets/1.png)

A continuación, coloque la variable [!DNL Marketo Measure] JavaScript dentro del iFrame.

![](assets/2.png)

Por último, cuando se agrega JavaScript, le recomendamos que valide el seguimiento de los envíos de formularios siguiendo estas instrucciones:

1. Copie la dirección URL de la página de aterrizaje que contiene la variable [!UICONTROL lightbox] formulario.
1. Abra un navegador Incognito y pegue la dirección URL.
1. Envíe el formulario con una dirección de correo electrónico única.
1. Confirme que la prueba se ha rastreado comprobando su CRM para la dirección de correo electrónico única utilizada; asegúrese de que los datos de Touchpoint se estén rellenando.
