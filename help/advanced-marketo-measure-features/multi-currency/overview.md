---
unique-page-id: 27656735
description: 'Información general: [!DNL Marketo Measure] - Documentación del producto'
title: Resumen
exl-id: 2076521c-b579-457c-ab1c-263b1da4dd89
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# Resumen {#overview}

Hoy, la variable [!DNL Marketo Measure] La aplicación solo admite una moneda única (se supone que es USD), mientras que sabemos y somos conscientes de que tenemos clientes en todo el mundo que necesitan informar sobre sus propias monedas corporativas y de usuario. Esta función desarrolla la capacidad de los usuarios de cambiar entre distintas monedas cuando están viendo los ingresos de gastos o ventas notificados.

## Disponibilidad {#availability}

Nivel 2 y superior.

## Requisitos {#requirements}

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
