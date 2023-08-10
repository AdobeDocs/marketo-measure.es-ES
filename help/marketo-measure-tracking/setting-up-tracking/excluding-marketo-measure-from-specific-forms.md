---
unique-page-id: 18874783
description: 'Exclusión [!DNL Marketo Measure] de Forms específico: [!DNL Marketo Measure] - Documentación del producto'
title: Exclusión de  [!DNL Marketo Measure]  de formularios específicos
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 8%

---

# Exclusión de [!DNL Marketo Measure] de formularios específicos {#excluding-marketo-measure-from-specific-forms}

De forma predeterminada, [!DNL Marketo Measure] se adjunta a todos los formularios del sitio. Sin embargo, no todos los envíos de formularios deben rastrearse ni incluirse necesariamente en un modelo de atribución. Esto se debe a que no todos los rellenos de formulario se consideran &quot;buenos&quot;. Un ejemplo de esto es una página o formulario para cancelar la suscripción. Además, los formularios de inicio de sesión generalmente no se rastrean, ya que diluirían el modelo de atribución.

## Cómo agregar [!DNL Marketo Measure]-excluir código:  {#how-to-add-marketo-measure-exclude-code}

Para evitar [!DNL Marketo Measure] para rastrear formularios específicos, simplemente añada &quot;[!DNL Bizible-Exclude]&quot; como una &quot;clase&quot; en el formulario. El código es el siguiente:

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
