---
unique-page-id: 18874519
description: Agregando [!DNL Marketo Measure] Script para Lightbox Forms - [!DNL Marketo Measure] - Documentación del producto
title: Adición del script de  [!DNL Marketo Measure]  a formularios de Lightbox
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# Adición del script de [!DNL Marketo Measure] a formularios de Lightbox {#adding-marketo-measure-script-to-lightbox-forms}

Aprenda a añadir correctamente la variable [!DNL Marketo Measure] JavaScript a un formulario dentro de una caja de luz.

Un lightbox abre un formulario delante del contenido cuando el visitante realiza una acción específica (es decir, hacer clic en una parte concreta de la página, pasar un periodo determinado en la página, etc.). Típicamente solo pedimos que nos den el [!DNL Marketo Measure] JavaScript se coloca en el encabezado de la página de aterrizaje, pero para los formularios dentro de una light box se necesita un paso adicional.

Dado que un formulario dentro de una light box es básicamente un formulario dentro de un iFrame, necesitaremos que nuestro script se coloque dentro de ese iFrame.

En primer lugar, busque el iFrame en [!UICONTROL lightbox] form vive en.

![](assets/1.png)

A continuación, coloque el [!DNL Marketo Measure] JavaScript dentro del iFrame.

![](assets/2.png)

Por último, cuando se añada el JavaScript, le recomendamos que valide el seguimiento de los envíos de formularios siguiendo estas instrucciones:

1. Copie la dirección URL de la página de aterrizaje que contiene [!UICONTROL lightbox] formulario.
1. Abra un explorador de Incógnito y pegue la dirección URL.
1. Envíe el formulario con una dirección de correo electrónico única.
1. Confirme que la prueba se rastreó comprobando su CRM para la dirección de correo electrónico única utilizada, asegúrese de que los datos de Touchpoint se estén rellenando.
