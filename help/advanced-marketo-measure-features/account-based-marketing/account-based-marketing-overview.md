---
unique-page-id: 18874730
description: Obtenga información acerca de Account-Based Marketing (ABM) y cómo Adobe Marketo Measure ayuda a los equipos de marketing y ventas a ejecutar estrategias ABM exitosas.
title: Información general sobre el marketing basado en cuentas
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
feature: Account-based Marketing
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 53%

---

# Información general sobre el marketing basado en cuentas {#account-based-marketing-overview}

En las siguientes secciones se ofrece una breve descripción de ABM, los componentes de la [!DNL Marketo Measure] Función ABM y cómo añadirla a su [!DNL Salesforce] diseño de página. Para obtener más información sobre ABM, consulte Adobe [ABM blog](https://business.adobe.com/blog/basics/account-based-marketing){target="_blank"}.

Para obtener instrucciones detalladas sobre la configuración de ABM dentro de su [!DNL Salesforce] Por ejemplo, vaya a [Configuración del diseño de página ABM en Salesforce](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}.

## Qué es ABM {#what-is-abm}

El marketing basado en cuentas (ABM) es una estrategia de marketing en la que se segmenta y se vende a empresas y cuentas en su conjunto, no solo como individuos. [!DNL Marketo Measure] ayuda a los equipos de marketing y ventas a ejecutar estrategias de ABM exitosas con su funcionalidad de asignación de clientes potenciales a cuentas y su puntuación de participación predictiva.

Para que nuestro modelo de marketing basado en cuentas empiece a rellenarse en su CRM, [!DNL Marketo Measure] necesita que se cumplan los siguientes criterios:

* Su CRM necesita al menos 25 cuentas que tengan al menos una oportunidad ganada cerrada en ellas, para evaluar mejor las características comunes de una cuenta/oportunidad &quot;exitosa&quot; para su negocio.
* En la otra cara de la moneda, su CRM necesita al menos 25 cuentas sin ninguna oportunidad ganada cerrada (todas las opps deben estar en una categoría de etapa &quot;abierta&quot; o en una categoría &quot;perdida cerrada&quot;) - esto nos ayuda a medir lo que hace una cuenta de menor grado en su organización.

>[!NOTE]
>
>Las cuentas &quot;malas&quot; anteriores deben estar abiertas durante al menos 12 meses sin acumular una Opp Cerrada Ganada; esa es la guía básica para determinar si una Opp se ha quedado obsoleta para los fines del modelo.

## Asignación de cliente potencial a cuenta {#lead-to-account-mapping}

La asignación de cliente potencial a cuenta es una parte crucial de un enfoque eficaz de ABM. Con la asignación de cliente potencial a cuenta, los posibles clientes o clientes potenciales se agrupan en la misma cuenta de compañía a medida que interactúan con la marca. Esto le permite segmentar y vender a particulares de la misma compañía de forma coherente. No hay más [!DNL Salesforce] necesaria para comenzar a beneficiarse de esta función. La Asignación de clientes potenciales a cuentas de [!DNL Marketo Measure] dispone de cinco métodos de coincidencia diferentes:

* Sitio web principal del cliente potencial a sitio web de la cuenta
* Dominio de correo electrónico del posible cliente al dominio del sitio web de la cuenta
* Nombre de la compañía del posible cliente al nombre de la cuenta
* Compañía del cliente potencial al dominio del sitio web de la cuenta
* Hacer coincidir el dominio de la dirección de correo electrónico del cliente potencial con la cuenta a través de la dirección de correo electrónico del contacto

>[!NOTE]
>
>Cada posible cliente intenta ser emparejado con una Cuenta en el orden preferencial de los métodos anteriores. Una vez que se establece una coincidencia, se establece inmediatamente el AccountId en el cliente potencial y no se establecerá una coincidencia con otro método. Si el cliente potencial ya tiene un AccountId válido, se omite el cliente potencial.

## Puntuación de participación predictiva {#predictive-engagement-score}

La Puntuación de participación predictiva de [!DNL Marketo Measure] (PES) es un valor dinámico que ilustra el compromiso de una cuenta en particular con sus esfuerzos de marketing. Esta puntuación es útil para segmentar las cuentas destino. Es una herramienta valiosa para identificar cuentas a las que dirigirse de forma más eficaz y eficiente.

Hay muchos componentes que entran en el algoritmo que calcula la PES. La actualización y la edad tienen una gran influencia en los cambios de puntuación, junto con la actividad del último punto de contacto o las vistas de página. Añadir nuevos contactos a una cuenta también afecta a la PES. A continuación se muestra una lista de algunas entradas de PES:

* Número total de vistas de página desde la cuenta
* Número promedio de vistas de la página
* Número promedio de personas en la cuenta
* Antigüedad de la última vista de la página
* Antigüedad promedio de las vistas de la página
* Número de personas en la cuenta
* Páginas importantes específicas y si ha habido una visita en los últimos 30/60/90 días
* Si la cuenta tiene una operación perdida/ganada cerrada
* Qué probabilidades hay de que se cierre perdido/ganado

>[!NOTE]
>
>Puede observar una calificación “N/A” o “-” (el símbolo del guion) en su Puntuación de participación predictiva para algunas cuentas.

_Una calificación de &quot;N/A&quot; simplemente significa que no hay datos suficientes en esa cuenta para que el modelo genere una calificación verdadera - con más datos, una calificación se da eventualmente._
_Un grado de &quot;-&quot; (símbolo de guión) significa que esta cuenta aún no ha sido procesada por el proceso ABM, debido a limitaciones de tiempo, procesos ocasionalmente incumplidos, etc. Si cree que una cuenta debe tener una calificación, basada en otras cuentas o marcos de tiempo similares, póngase en contacto con y deje que [!DNL Marketo Measure] Lo sé._

## Configuración del diseño de página de ABM en [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

Para empezar a utilizar PES, debe agregar el campo PES y la lista relacionada a los diseños de página adecuados en [!DNL Salesforce].

1. Vaya a **[!UICONTROL Configurar]** > **[!UICONTROL Personalizar]** > **[!UICONTROL Cuentas]** > **[!UICONTROL Diseño de página]**. A continuación, seleccione el diseño de página que desee editar.
1. Vaya a [!UICONTROL Campos] y mueva el campo “Puntuación de participación predictiva” a la sección Información de la cuenta.

   ![](assets/1.png)

1. Finalmente, vaya a [!UICONTROL Listas relacionadas] y mueva la Lista relacionada “Clientes potenciales” a su diseño de página.

   ![](assets/2.png)

1. A continuación, vaya a **[!UICONTROL Configurar]** > **[!UICONTROL Personalizar]** > **[!UICONTROL Clientes potenciales]** > **[!UICONTROL Diseño de página]** y seleccione los diseños de página adecuados que desee editar.
1. Haga clic en **[!UICONTROL Campos]** y añada el campo [!UICONTROL Cuenta] donde crea conveniente en la página.

   ![](assets/3.png)

Ya está todo listo.

