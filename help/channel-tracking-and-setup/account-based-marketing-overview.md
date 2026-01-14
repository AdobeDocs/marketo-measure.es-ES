---
description: Obtenga información acerca de Account-Based Marketing (ABM) y cómo Adobe Marketo Measure ayuda a los equipos de marketing y ventas a ejecutar estrategias ABM exitosas.
title: Información general sobre el marketing basado en cuentas
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
feature: Account-based Marketing
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 95%

---

# Información general sobre el marketing basado en cuentas {#account-based-marketing-overview}

Las siguientes secciones ofrecen información general breve sobre ABM, los componentes de la función ABM de [!DNL Marketo Measure] y cómo añadirla a su diseño de página de [!DNL Salesforce]. Para leer más sobre ABM, revisa el [blog ABM](https://business.adobe.com/blog/basics/account-based-marketing){target="_blank"} de Adobe.

Para obtener instrucciones detalladas sobre la configuración de ABM dentro de su instancia de [!DNL Salesforce] vaya a [Configuración del diseño de página ABM en Salesforce](/help/channel-tracking-and-setup/account-based-marketing-overview.md){target="_blank"}.

## Qué es ABM {#what-is-abm}

El marketing basado en cuentas (ABM) es una estrategia de marketing en la que se segmenta y se vende a empresas y cuentas en su conjunto, no solo como individuos. [!DNL Marketo Measure] ayuda a los equipos de marketing y ventas a ejecutar estrategias de ABM exitosas con su funcionalidad de asignación de clientes potenciales a cuentas y su puntuación de participación predictiva.

Para que nuestro modelo de marketing basado en cuentas empiece a rellenarse en su CRM, [!DNL Marketo Measure] necesita que se cumplan los siguientes criterios:

* Su CRM necesita al menos 25 cuentas que tengan una oportunidad ganada cerrada, para evaluar mejor los aspectos comunes de una cuenta/oportunidad “exitosa” para su negocio.
* En la otra cara de la moneda, su CRM necesita al menos 25 cuentas sin ninguna oportunidad ganada cerrada (todas las oportunidades deben estar en nuestra categoría de etapa “abierta” o en una categoría “perdida cerrada”). Esto nos ayuda a medir lo que hace una cuenta de menor grado en su organización.

>[!NOTE]
>
>Las cuentas “malas” anteriores deben estar abiertas durante al menos 12 meses sin acumular una oportunidad Cerrada ganada; esa es la guía básica para saber si una oportunidad se ha quedado obsoleta para los fines del modelo.

## Asignación de cliente potencial a cuenta {#lead-to-account-mapping}

La asignación de cliente potencial a cuenta es una parte crucial de un enfoque eficaz de ABM. Con la asignación de cliente potencial a cuenta, los posibles clientes o clientes potenciales se agrupan en la misma cuenta de compañía a medida que interactúan con la marca. Esto le permite segmentar y vender a particulares de la misma compañía de forma coherente. No es necesario una configuración de [!DNL Salesforce] adicional para comenzar a beneficiarse de esta función. La asignación de posibles clientes a cuentas de [!DNL Marketo Measure] dispone de métodos de coincidencia diferentes:

* Sitio web principal del cliente potencial a sitio web de la cuenta
* Dominio de correo electrónico del posible cliente al dominio del sitio web de la cuenta
* Nombre de la compañía del posible cliente al nombre de la cuenta
* Compañía del cliente potencial al dominio del sitio web de la cuenta
* Sitio web del posible cliente al dominio del correo electrónico de los contactos de la cuenta
* Dominio de correo electrónico del posible cliente al dominio del correo electrónico de los contactos de la cuenta
* Sitio web del posible cliente al dominio del correo electrónico de los posibles clientes de la cuenta
* Dominio del correo electrónico del posible cliente al dominio del correo electrónico de los posibles clientes de la cuenta

Los posibles clientes/contactos de las cuentas se validan mediante los dominios de correo electrónico/sitio web y se comparan con el dominio o subdominio del correo electrónico/sitio web del posible cliente. Se utiliza la cuenta con la mayor cantidad de coincidencias.

>[!NOTE]
>
>Se intenta hacer coincidir cada posible cliente con una cuenta en el orden preferencial de métodos anterior. Una vez que se establece una coincidencia, se establece inmediatamente el AccountId en el posible cliente y no se establecerá una coincidencia con otro método.

## Puntuación de participación predictiva {#predictive-engagement-score}

La Puntuación de participación predictiva de [!DNL Marketo Measure] (PES) es un valor dinámico que ilustra el compromiso de una cuenta en particular con sus esfuerzos de marketing. Esta puntuación es útil para segmentar las cuentas destino. Es una herramienta valiosa para identificar cuentas a las que dirigirse de forma más eficaz y eficiente.

Hay muchos componentes que entran en el algoritmo que calcula la PES. La actualización y la edad influyen en gran medida en los cambios de puntuación, junto con la actividad del último punto de contacto o las vistas de la página. Añadir nuevos contactos a una cuenta también afecta a la PES. A continuación se muestra una lista de algunas entradas de PES:

* Número total de vistas de página desde la cuenta
* Número promedio de vistas de la página
* Número promedio de personas en la cuenta
* Antigüedad de la última vista de la página
* Antigüedad promedio de las vistas de la página
* Número de personas en la cuenta
* Páginas importantes específicas y si ha habido una visita en los últimos 30/60/90 días
* Si la cuenta tiene una operación perdida/ganada cerrada
* Probabilidades de que se cierre perdida/ganada

>[!NOTE]
>
>Puede observar una calificación “N/A” o “-” (el símbolo del guion) en su Puntuación de participación predictiva para algunas cuentas.

_Una calificación de “N/A” simplemente significa que no hay datos suficientes aún en esa cuenta para que el modelo genere una calificación verdadera; con más datos, se asignará una calificación._
_Un grado de “-” (el símbolo de guion) significa que esta cuenta aún no ha sido procesada por el proceso de ABM, debido a limitaciones de tiempo, procesos ocasionalmente incumplidos, etc. Si cree que una cuenta debe tener una calificación basada en otras cuentas o marcos de tiempo similares, póngase en contacto e informe a [!DNL Marketo Measure]._

## Configuración del diseño de página de ABM en [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

Para empezar a utilizar la PES, debe añadir el campo PES y la lista relacionada con los diseños de página adecuados en [!DNL Salesforce].

1. Vaya a **[!UICONTROL Configurar]** > **[!UICONTROL Personalizar]** > **[!UICONTROL Cuentas]** > **[!UICONTROL Diseño de página]**. A continuación, seleccione el diseño de página que desee editar.
1. Vaya a [!UICONTROL Campos] y mueva el campo “Puntuación de participación predictiva” a la sección Información de la cuenta.

   ![1. Vaya a Campos y mueva el campo &quot;Puntuación de participación predictiva&quot;](assets/account-marketing-3.png)

1. Finalmente, vaya a [!UICONTROL Listas relacionadas] y mueva la Lista relacionada “Clientes potenciales” a su diseño de página.

   ![1. Finalmente, vaya a Listas relacionadas y mueva los &quot;Posibles clientes&quot; relacionados](assets/account-marketing-4.jpg)

1. A continuación, vaya a **[!UICONTROL Configurar]** > **[!UICONTROL Personalizar]** > **[!UICONTROL Clientes potenciales]** > **[!UICONTROL Diseño de página]** y seleccione los diseños de página adecuados que desee editar.
1. Haga clic en **[!UICONTROL Campos]** y añada el campo [!UICONTROL Cuenta] donde crea conveniente en la página.

   ![1. Haga clic en Campos y agregue el campo Cuenta donde ](assets/account-marketing-5.png)

Ya está todo listo.

