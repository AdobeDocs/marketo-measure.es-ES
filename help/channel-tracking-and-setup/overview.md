---
description: Directrices generales para usuarios de Marketo Measure
title: Información general
exl-id: 2076521c-b579-457c-ab1c-263b1da4dd89
feature: Multi-Currency
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 1%

---

# Información general {#overview}

En la actualidad, la aplicación [!DNL Marketo Measure] solo admite una sola moneda (se supone que es USD), mientras que sabemos y somos conscientes de que tenemos clientes en todo el mundo que necesitan informar sobre sus propias monedas corporativas y de usuario. Esta característica permite a los usuarios cambiar entre las mismas monedas utilizadas en su CRM al ver los gastos o ingresos de ventas registrados en [!DNL Marketo Measure].

## Disponibilidad {#availability}

Nivel 2 y superior.

## Requisitos {#requirements}

[!DNL Marketo Measure] extraerá automáticamente la configuración de moneda del CRM del cliente. Ya no se requiere la configuración manual en [!DNL Marketo Measure] para que coincida con CRM. La configuración de moneda se puede encontrar en la página &quot;General&quot; en &quot;CRM&quot;.

En [!DNL Salesforce], el cliente debe tener habilitada la opción &quot;Activar múltiples monedas&quot;. De forma opcional, el cliente también puede seleccionar &quot;Sí, deseo activar la gestión avanzada de divisas&quot;.

En Dynamics, el cliente puede establecer tasas de cambio estáticas en su Configuración para varias monedas. No existe el concepto de &quot;administración avanzada de monedas&quot; en Dynamics.

## Términos {#terms}

| **Término** | Descripción |
|---|---|
| **Moneda avanzada** | El cliente tiene activada la gestión avanzada de divisas y la opción Varias Divisas, lo que significa que puede tener diferentes tasas de conversión para diferentes períodos de tiempo. |
| **Moneda corporativa** | Son las distintas monedas que enumera y declara una organización en CRM, todas con tasas de conversión. [!DNL Marketo Measure] importará estos valores y pondrá estas monedas a disposición de los usuarios dentro de nuestro producto. |
| **Configuración regional de moneda** | La moneda única que se utiliza para una organización, establecida en la página Información de la compañía. |
| **Moneda local (o Moneda de usuario)** | La moneda establecida para un solo usuario en el perfil de usuario, de modo que pueda ver cualquier cantidad en su propia moneda local. La organización tendrá que declarar y configurar la moneda antes de que un usuario pueda seleccionar su moneda local. |
| **Moneda única** | Se utiliza para los clientes que no utilizan varias monedas en CRM, pero cuya organización se ejecuta en una moneda diferente, por lo que tienen una configuración regional de moneda. Sigue siendo una moneda única para la organización, pero sin ninguna conversión. |
| **Moneda simple** | El cliente tiene habilitada la opción Varias monedas, pero tiene una tasa de conversión estática por moneda. |
