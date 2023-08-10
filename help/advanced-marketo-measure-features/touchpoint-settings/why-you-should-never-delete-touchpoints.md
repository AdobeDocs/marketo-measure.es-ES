---
unique-page-id: 18874560
description: 'Por qué nunca debe eliminar los puntos de contacto: [!DNL Marketo Measure] - Documentación del producto'
title: Por qué nunca se deben eliminar los puntos de contacto
exl-id: e74c14ff-0399-4ee9-b732-6686823ff5c7
feature: Touchpoints
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 5%

---

# Por qué nunca se deben eliminar los puntos de contacto {#why-you-should-never-delete-touchpoints}

Si descubre que hay un punto de contacto en una oportunidad a la que se le está asignando crédito de atribución incorrectamente, póngase en contacto con su administrador de cuentas para determinar los pasos siguientes. En estas situaciones, recomendamos utilizar la función de supresión de puntos de contacto del comprador para eliminar el punto de contacto de SFDC y el panel de ROI. El administrador de cuentas puede ayudar a crear estas reglas. No elimine manualmente estos puntos de contacto.

El [!DNL Marketo Measure] El sistema de procesamiento no registrará la eliminación manual de un punto de contacto de SFDC. A partir de hoy, no hay ningún déclencheur que indique a nuestro sistema que ajuste los datos. [!DNL Marketo Measure] no insertará automáticamente otro punto de contacto para reemplazar el que se eliminó, ni reasignará la posición del punto de contacto o atribución al punto de contacto posterior.

Cuando se elimina un punto de contacto, se crea un agujero en los datos de atribución. Normalmente, esto se manifiesta en los puntos de contacto de atribución de una oportunidad. En la siguiente imagen, se ha eliminado el punto de contacto que habría recibido el contacto de Creación de oportunidad. Como resultado, a esta oportunidad le falta el punto de contacto OC y el porcentaje de atribución para esta Opp no sumará el 100%.

![](assets/1.png)

Si se han eliminado puntos de contacto de su SFDC, póngase en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} para solicitar una reimportación de sus datos.
