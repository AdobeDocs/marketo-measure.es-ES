---
unique-page-id: 18874783
description: 'Exclusión [!DNL Marketo Measure] de Forms específico: [!DNL Marketo Measure] - Documentación del producto'
title: Exclusión [!DNL Marketo Measure] de Forms específico
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 0%

---

# Exclusión [!DNL Marketo Measure] de Forms específico {#excluding-marketo-measure-from-specific-forms}

De forma predeterminada, [!DNL Marketo Measure] se adjunta a todos los formularios del sitio. Sin embargo, no todos los envíos de formularios deben seguirse o incluirse necesariamente en un modelo de atribución. Esto se debe a que no todos los rellenos de formulario se consideran &quot;buenos&quot;. Un ejemplo de esto es una página o formulario de cancelación de suscripción. Además, los formularios de inicio de sesión normalmente no se rastrean, ya que diluirían el modelo de atribución.

## Cómo añadir [!DNL Marketo Measure]-exclude Código:  {#how-to-add-marketo-measure-exclude-code}

Para evitar [!DNL Marketo Measure] desde el seguimiento de formularios específicos, simplemente agregue &quot;[!DNL Bizible-Exclude]&quot; como una &quot;clase&quot; en el formulario. El código es el siguiente:

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
