---
unique-page-id: 18874730
description: Información general de marketing basado en cuentas [!DNL Marketo Measure] - Documentación del producto
title: Información general sobre marketing basado en cuentas
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 0%

---

# Información general sobre marketing basado en cuentas {#account-based-marketing-overview}

A continuación se presenta una breve descripción de ABM, los componentes de la [!DNL Marketo Measure] función ABM y cómo agregarla a su [!DNL Salesforce] diseño de página. Para leer más sobre ABM, consulte [esta página](https://www.marketo.com/account-based-marketing/){target="_blank"}.

Para navegar directamente a las instrucciones para configurar ABM dentro de su [!DNL Salesforce] instancia, por favor [haga clic aquí](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}.

## ¿Qué es ABM? {#what-is-abm}

El marketing basado en cuentas, ABM, es una estrategia de marketing en la que se dirige y vende a empresas y cuentas en su conjunto, no solo como individuos. [!DNL Marketo Measure] ayuda a los equipos de marketing y ventas a ejecutar estrategias de ABM exitosas con su funcionalidad de asignación de cliente potencial a cuenta y puntuación de participación predictiva.

Para que nuestro modelo de marketing basado en cuentas empiece a rellenarse en su CRM, [!DNL Marketo Measure] necesita cumplir los siguientes criterios:

* Su CRM necesita al menos 25 cuentas que tengan al menos una oportunidad cerrada ganada, de modo que podamos medir mejor las características comunes de una cuenta/oportunidad &quot;exitosa&quot; para su negocio.
* Al otro lado de la moneda, su CRM necesita al menos 25 cuentas sin ninguna oportunidad de ganancias cerradas (todas las opps deben estar en nuestra categoría de escenario &quot;Abierto&quot; o en la categoría &quot;Cerrado Perdido&quot; - esto nos ayuda a medir qué hace una cuenta de bajo grado en su organización.

>[!NOTE]
>
>Las cuentas &quot;malas&quot; mencionadas deben estar abiertas durante al menos 12 meses sin acumular un Closed Won opp; esa es nuestra guía básica para saber si una Opp se ha quedado obsoleta o no para los propósitos del modelo.

## Asignación de posibles clientes a cuentas {#lead-to-account-mapping}

La asignación de cliente potencial a cuenta es una parte crucial de un enfoque ABM efectivo. Con la asignación de cliente potencial a cuenta, los posibles clientes o posibles clientes se agrupan en la misma cuenta de empresa a medida que interactúan con su marca. Esto le permite dirigirse a personas de la misma empresa y venderlas de forma coherente. No hay más [!DNL Salesforce] para comenzar a beneficiarse de esta función. La variable [!DNL Marketo Measure] Asignación de posibles clientes a cuentas: cinco métodos coincidentes diferentes:

* Sitio web de posibles clientes a sitio web de cuentas
* Dominio de correo electrónico de posible cliente para dominio de sitio web de la cuenta
* Nombre de la empresa potencial al nombre de la cuenta
* Dominio de empresa potencial a sitio web de cuenta
* Coincidencia del dominio en la dirección de correo electrónico del posible cliente con la cuenta a través de la dirección de correo electrónico del contacto

## Puntuación de participación predictiva {#predictive-engagement-score}

La variable [!DNL Marketo Measure] La puntuación de participación predictiva, o PES, es un valor dinámico que ilustra la participación de una cuenta en particular en sus esfuerzos de marketing. Esta puntuación es útil para segmentar cuentas a las que se va a dirigir. Es un valioso instrumento para identificar cuentas que se destinen de manera más eficaz y eficiente.

Hay muchos componentes que van al algoritmo que calcula el PES. La actualización y la edad tienen una gran influencia en los cambios de puntuación, junto con la actividad de los últimos puntos de contacto o las vistas de página. Añadir nuevos contactos a una cuenta también afecta al PES. A continuación se muestra una lista de algunas entradas de PES:

* Número total de vistas de página desde la cuenta
* Número promedio de vistas de página
* Número promedio de personas en la cuenta
* Edad de la última vista de página
* Edad promedio de las vistas de página
* Número de personas de la cuenta
* Páginas importantes específicas y si ha habido una visita en los últimos 30/60/90 días
* Si la cuenta tiene una operación cerrada perdida/ganada
* Probabilidad de que se cierre perdido/ganado

>[!NOTE]
>
>Puede observar un grado de &quot;N/A&quot; o &quot;-&quot; (el símbolo de guión) en la puntuación de participación predictiva para algunas cuentas.

_Una calificación de &quot;N/A&quot; simplemente significa que todavía no tenemos datos suficientes para que nuestro modelo genere una verdadera calificación -con más datos, eventualmente se dará una calificación._
_Un grado de &quot;-&quot; (el símbolo de guión) significa que esta cuenta aún no ha sido procesada por nuestro proceso ABM, debido a limitaciones de tiempo, a procesos que a veces se pierden, etc. Si cree que una cuenta debe tener una calificación, basada en otras cuentas o marcos de tiempo similares, póngase en contacto con y permita [!DNL Marketo Measure] ya saben._

## Configuración del diseño de página de ABM en [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

Para empezar a utilizar el PES, simplemente debe añadir el campo PES y la lista relacionada a los diseños de página correspondientes en [!DNL Salesforce].

1. Vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Personalizar]** > **[!UICONTROL Cuentas]** > **[!UICONTROL Diseño de página]**. A continuación, seleccione el diseño de página que desee editar.
1. Vaya a [!UICONTROL Campos] y mueva el campo &quot;Puntuación de participación predictiva&quot; a la sección Información de la cuenta .

   ![](assets/1.png)

1. Finalmente, vaya a [!UICONTROL Listas relacionadas] y mueva la lista relacionada &quot;Posibles clientes&quot; al diseño de la página.

   ![](assets/2.png)

1. A continuación, vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Personalizar]** > **[!UICONTROL Posibles clientes]** > **[!UICONTROL Diseño de página]** y seleccione los diseños de página que desee editar.
1. Haga clic en **[!UICONTROL Campos]** y añada [!UICONTROL Cuenta] campo en el que se ve que cabe en la página.

   ![](assets/3.png)

¡Estás listo!

