---
unique-page-id: 18874783
description: Excluyendo  [!DNL Marketo Measure] de Forms específico - [!DNL Marketo Measure]
title: Exclusión de  [!DNL Marketo Measure]  de formularios específicos
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 4%

---

# Excluyendo [!DNL Marketo Measure] de Forms específico {#excluding-marketo-measure-from-specific-forms}

De manera predeterminada, [!DNL Marketo Measure] se adjunta a todos los formularios del sitio. Sin embargo, no todos los envíos de formularios deben necesariamente rastrearse o incluirse en un modelo de atribución. Esto se debe a que no todos los rellenos de formulario se consideran &quot;buenos&quot;. Un ejemplo de esto es una página o formulario para cancelar la suscripción. Además, los formularios de inicio de sesión no suelen rastrearse, ya que diluirían el modelo de atribución.

## Cómo agregar el código de exclusión de [!DNL Marketo Measure]:  {#how-to-add-marketo-measure-exclude-code}

Para evitar que [!DNL Marketo Measure] realice el seguimiento de formularios específicos, simplemente agregue &quot;[!DNL Bizible-Exclude]&quot; como una &quot;clase&quot; en el formulario. El código es el siguiente:

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
