---
description: Por qué no debe eliminar nunca la guía de puntos de contacto para usuarios de Marketo Measure
title: Por qué nunca se deben eliminar los puntos de contacto
exl-id: e74c14ff-0399-4ee9-b732-6686823ff5c7
feature: Touchpoints
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 5%

---

# Por qué nunca se deben eliminar los puntos de contacto {#why-you-should-never-delete-touchpoints}

Si descubre que hay un punto de contacto en una oportunidad a la que se le está asignando crédito de atribución incorrectamente, póngase en contacto con su administrador de cuentas para determinar los pasos siguientes. En estas situaciones, recomendamos utilizar la función de supresión de puntos de contacto del comprador para eliminar el punto de contacto de SFDC y el panel de ROI. El administrador de cuentas puede ayudar a crear estas reglas. No elimine manualmente estos puntos de contacto.

El sistema de procesamiento [!DNL Marketo Measure] no registrará que un punto de contacto se ha eliminado manualmente de SFDC. A partir de hoy, no hay ningún déclencheur que indique a nuestro sistema que ajuste los datos. [!DNL Marketo Measure] no insertará automáticamente otro punto de contacto para reemplazar el que se eliminó, ni reasignará la posición del punto de contacto o atribución al punto de contacto posterior.

Cuando se elimina un punto de contacto, se crea un agujero en los datos de atribución. Normalmente, esto se manifiesta en los puntos de contacto de atribución de una oportunidad. En la siguiente imagen, se ha eliminado el punto de contacto que habría recibido el contacto de Creación de oportunidad. Como resultado, a esta oportunidad le falta el punto de contacto OC y el porcentaje de atribución para esta Opp no sumará el 100%.

![](assets/touchpoint-settings-10.png)

Si se han eliminado puntos de contacto de tu SFDC, ponte en contacto con el [Soporte técnico de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} para solicitar que se vuelvan a importar tus datos.
