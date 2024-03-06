---
unique-page-id: 18874519
description: Agregando [!DNL Marketo Measure] Script para Lightbox Forms - [!DNL Marketo Measure]
title: Adición del script de  [!DNL Marketo Measure]  a formularios de Lightbox
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 2%

---

# Agregando [!DNL Marketo Measure] Script para Lightbox Forms {#adding-marketo-measure-script-to-lightbox-forms}

Aprenda a añadir correctamente la variable [!DNL Marketo Measure] JavaScript a un formulario dentro de una caja de luz.

Un lightbox abre un formulario delante del contenido cuando el visitante realiza una acción específica (es decir, hacer clic en una parte concreta de la página, pasar un tiempo determinado en la página, etc.). Por lo general, solicitamos que se le [!DNL Marketo Measure] JavaScript se coloca en el encabezado de la página de aterrizaje, pero para los formularios dentro de una light box se necesita un paso adicional.

Dado que un formulario dentro de una light box es básicamente un formulario dentro de un iFrame, el script se coloca dentro de ese iFrame.

En primer lugar, busque el iFrame en [!UICONTROL lightbox] form vive en.

![](assets/1.png)

A continuación, coloque el [!DNL Marketo Measure] JavaScript dentro del iFrame.

![](assets/2.png)

Finalmente, cuando se agrega el JavaScript, el seguimiento de los envíos de formularios de validación se realiza siguiendo estas instrucciones:

1. Copie la dirección URL de la página de aterrizaje que contiene [!UICONTROL lightbox] formulario.
1. Abra un explorador de Incógnito y pegue la dirección URL.
1. Envíe el formulario con una dirección de correo electrónico única.
1. Confirme que la prueba se rastreó comprobando su CRM para la dirección de correo electrónico única utilizada, asegúrese de que los datos de Touchpoint se estén rellenando.
