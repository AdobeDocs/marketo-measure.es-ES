---
unique-page-id: 18874560
description: 'Por qué nunca se deben eliminar los puntos de contacto: [!DNL Marketo Measure] - Documentación del producto'
title: Por qué nunca se deben eliminar los puntos de contacto
exl-id: e74c14ff-0399-4ee9-b732-6686823ff5c7
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# Por qué nunca se deben eliminar los puntos de contacto {#why-you-should-never-delete-touchpoints}

Si encuentra que hay un punto de contacto en una oportunidad a la que se asigna crédito de atribución incorrectamente, póngase en contacto con su administrador de cuentas para determinar los pasos siguientes. En estas situaciones, recomendamos utilizar la función de supresión de puntos de contacto del Comprador para eliminar el punto de contacto de SFDC y el panel de ROI. El administrador de cuentas puede ayudarle a crear estas reglas. No elimine manualmente estos puntos de contacto usted mismo.

La variable [!DNL Marketo Measure] el sistema de procesamiento no registrará que un punto de contacto se haya eliminado manualmente de SFDC. A partir de hoy, no hay ningún déclencheur que indique a nuestro sistema que ajuste los datos. [!DNL Marketo Measure] no insertará automáticamente otro punto de contacto para reemplazar el que se eliminó, ni reasignará la posición o atribución del punto de contacto al siguiente punto de contacto.

Cuando se elimina un punto de contacto, se crea un agujero en los datos de atribución. Normalmente, esto se manifestará en los puntos de contacto de atribución de una oportunidad. En la imagen siguiente, se había eliminado el punto de contacto que hubiera recibido el toque de creación de oportunidades. Como resultado, a esta oportunidad le falta el punto de contacto OC y el porcentaje de atribución para esta Opp no sumará hasta el 100%.

![](assets/1.png)

Si se han eliminado puntos de contacto de su SFDC, póngase en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;} para solicitar una reimportación de sus datos.
