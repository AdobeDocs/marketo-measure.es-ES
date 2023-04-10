---
unique-page-id: 27656735
description: 'Información general: [!DNL Marketo Measure] - Documentación del producto'
title: Información general
exl-id: 2076521c-b579-457c-ab1c-263b1da4dd89
source-git-commit: bf047695c4ea82c4fbf1e9079b7443a5c9821e42
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Información general {#overview}

Hoy, la variable [!DNL Marketo Measure] La aplicación solo admite una moneda única (se supone que es USD), mientras que sabemos y somos conscientes de que tenemos clientes en todo el mundo que necesitan informar sobre sus propias monedas corporativas y de usuario. Esta función permite a los usuarios cambiar entre las mismas monedas utilizadas en su CRM al ver los ingresos de gastos o ventas registrados en [!DNL Marketo Measure].

## Disponibilidad {#availability}

Nivel 2 y superior.

## Requisitos {#requirements}

[!DNL Marketo Measure] extraerá automáticamente la configuración de moneda del CRM del cliente. Configuración manual en [!DNL Marketo Measure] para que coincida con CRM ya no es necesario. La configuración de moneda se encuentra en la página &quot;General&quot; en &quot;CRM&quot;.

En [!DNL Salesforce], el cliente debe tener habilitado &quot;Activar varias monedas&quot;. De forma opcional, el cliente también puede seleccionar &quot;Sí, deseo habilitar la Gestión Avanzada de Divisas&quot;.

En Dynamics, el cliente puede establecer tipos de cambio estáticos en su Configuración para varias monedas. No existe el concepto de &quot;administración avanzada de divisas&quot; en Dynamics.

## Términos {#terms}

| **Término** | Descripción |
|---|---|
| **Moneda avanzada** | El cliente tiene habilitados Advanced Currency Management y Multiple Currency, lo que significa que puede tener diferentes tasas de conversión para diferentes períodos de tiempo. |
| **Moneda corporativa** | Estas son las distintas monedas que una organización en CRM enumera y declara, todas con tasas de conversión. [!DNL Marketo Measure] importará estos valores y pondrá estas monedas a disposición de los usuarios de nuestro producto. |
| **Configuración regional de moneda** | La moneda única que se utiliza para una organización, se establece en la página Información de la empresa . |
| **Moneda local (o Moneda de usuario)** | La moneda establecida para un único usuario en el perfil de usuario, para que pueda ver cualquier cantidad en su propia moneda local. La organización deberá declarar y configurar la moneda antes de que el usuario pueda seleccionar la moneda local. |
| **Moneda única** | Se utiliza para clientes que no utilizan Monedas Múltiples en CRM, pero su organización se ejecuta en una moneda diferente, por lo que tienen una &quot;Configuración regional de moneda&quot;. Se trata de una moneda única para la organización, pero sin ninguna conversión. |
| **Moneda simple** | El cliente tiene activada la opción Varias monedas, pero tiene una tasa de conversión estática por moneda. |
