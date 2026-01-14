---
description: Agregando  [!DNL Marketo Measure] Script a la guía de Lightbox Forms para usuarios de Marketo Measure
title: Adición del script de  [!DNL Marketo Measure]  a formularios de Lightbox
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
feature: Tracking
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---

# Agregando script [!DNL Marketo Measure] a Lightbox Forms {#adding-marketo-measure-script-to-lightbox-forms}

Aprenda a agregar correctamente el JavaScript [!DNL Marketo Measure] a un formulario dentro de una light box.

Un lightbox abre un formulario delante del contenido cuando el visitante realiza una acción específica (es decir, hacer clic en una parte concreta de la página, pasar un tiempo determinado en la página, etc.). Normalmente, pedimos que la JavaScript [!DNL Marketo Measure] se coloque en el encabezado de la página de aterrizaje, pero para los formularios dentro de una light box se necesita un paso adicional.

Dado que un formulario dentro de una light box es básicamente un formulario dentro de un iFrame, el script se coloca dentro de ese iFrame.

Primero, busque el iFrame en el que se encuentra el formulario [!UICONTROL lightbox].

![Primero, busque el iFrame en el que se encuentra el formulario Lightbox.](assets/adding-providers-8.png)

A continuación, coloque el JavaScript [!DNL Marketo Measure] dentro del iFrame.

![A continuación, coloque el Marketo Measure JavaScript dentro del iFrame.](assets/adding-providers-5.png)

Por último, cuando se agrega la JavaScript, el seguimiento de los envíos de los formularios de validación se realiza siguiendo estas instrucciones:

1. Copie la dirección URL de la página de aterrizaje que contiene el formulario [!UICONTROL lightbox].
1. Abra un explorador de Incógnito y pegue la dirección URL.
1. Envíe el formulario con una dirección de correo electrónico única.
1. Confirme que la prueba se rastreó comprobando su CRM para la dirección de correo electrónico única utilizada, asegúrese de que los datos de Touchpoint se estén rellenando.
