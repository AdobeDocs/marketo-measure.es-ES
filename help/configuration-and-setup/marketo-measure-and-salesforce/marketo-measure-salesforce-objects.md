---
unique-page-id: 18874582
description: "[!DNL Marketo Measure] Objetos de Salesforce: [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Objetos de Salesforce"
exl-id: d5d6f334-6531-40fa-b043-75b49d8f43d5
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 1%

---

# Objetos de Salesforce de [!DNL Marketo Measure]  {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero sigue viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

Cuándo [!DNL Marketo Measure] está instalado en [!DNL Salesforce] (SFDC), varios [!DNL Marketo Measure] Se añaden objetos. Este artículo proporciona una explicación de varios de estos usos [!DNL Marketo Measure] Objetos. Algunos objetos que [!DNL Marketo Measure] agrega a [!DNL Salesforce] son:

* [Punto de contacto del comprador](#touchpoint)
* [Punto de contacto de atribución del comprador](#attribution)
* [[!DNL Marketo Measure] Persona](#person)
* [[!DNL Marketo Measure] Pruebas A/B](#ab)
* [[!DNL Marketo Measure] Eventos](#events)

Los puntos de contacto capturados por las cosas que desea rastrear escribirán en los objetos personalizados creados por la instalación del [!DNL Bizible Salesforce] paquete.

[!DNL Marketo Measure] Los objetos están relacionados con un estándar específico [!DNL Salesforce] Objetos. Esto le permite informar sobre [!DNL Marketo Measure] y [!DNL Salesforce] Objetos juntos. La tabla siguiente muestra qué [!DNL Salesforce] Objetar el [!DNL Marketo Measure] El objeto está relacionado con.

![](assets/1-1.png)

## Punto de contacto del comprador {#buyer-touchpoint}

El [!UICONTROL Buyer Touchpoint] (BT) El objeto cuenta la historia de marketing de un individuo. Almacena todos los datos relacionados con los puntos de contacto de marketing generados por los posibles clientes y contactos. El BT muestra información como el canal de marketing del que provino el punto de contacto o qué campaña de publicidad trajo ese posible cliente/contacto en particular a su sitio web.

El objeto BT es visible en las páginas de posibles clientes y contactos como **Lista relacionada** (véase la imagen siguiente).

![](assets/2-1.png)

La lista relacionada con BT muestra todos los puntos de contacto que pertenecen al posible cliente o contacto. Dentro de la lista están los [!DNL Marketo Measure] Campos que proporcionan más detalles sobre cada punto de contacto. Al hacer clic en el número de ID del punto de contacto del comprador, accederá a la página Detalles del punto de contacto del comprador, que proporciona aún más detalles sobre el punto de contacto, como la primera página web que visitó el posible cliente/contacto durante esa sesión web (**página de aterrizaje**).

## Punto de contacto de atribución del comprador {#buyer-attribution-touchpoint}

El [!UICONTROL Punto de contacto de atribución del comprador] El objeto cuenta la historia de las interacciones de marketing de sus contactos relacionadas con una oportunidad. Muestra el *atribución* datos relacionados con los puntos de contacto de marketing. Este objeto le permite ver cuánto crédito de ingresos se atribuye a cada punto de contacto de marketing. El tipo de modelo de atribución que utiliza determinará el porcentaje de ingresos atribuidos a los puntos de contacto.

Los puntos de contacto de atribución del comprador (BAT) solo se crean una vez que se crea una oportunidad relacionada con contactos que tienen datos de punto de contacto del comprador (BT). Las MTD no se crean sin una oportunidad. Una vez creada la oportunidad, el objeto BAT utilizará el [!DNL Salesforce] *Cantidad* sobre la oportunidad para comprender cuántos ingresos atribuir a los puntos de contacto.

A **workflow** debe crearse si utiliza un [Campo de cantidad personalizado](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md) para mostrar los ingresos del objeto de oportunidad. [!DNL Marketo Measure] no puede leer la información que aparece en los campos de importe personalizados y, por lo tanto, no puede rellenar los datos de atribución de ingresos en los puntos de contacto. Este flujo de trabajo utilizará **[!DNL Marketo Measure]Importe de oportunidad** Field, uno de los [!DNL Marketo Measure] campos personalizados, para asignar el valor de ingresos del campo Importe personalizado al campo Importe de oportunidad.

![](assets/3-1.png)

El objeto BAT es visible en la [!UICONTROL Oportunidad], [!UICONTROL Contacto], y [!UICONTROL Cuenta] Objeto como lista relacionada. Esta lista muestra todos los puntos de contacto con los datos de atribución que pertenecen a una oportunidad. Si pulsas el ID de punto de contacto de atribución de comprador, accederás a la página Detalle del punto de contacto de atribución de comprador. Aquí podrá ver datos de atribución más específicos e información sobre la procedencia del punto de contacto (similar a lo que se proporciona desde el objeto Touchpoint del comprador).

## [!DNL Marketo Measure] Persona {#marketo-measure-person}

El [!DNL Marketo Measure] El objeto Person relaciona los objetos Lead y Contact. De forma predeterminada, Salesforce no proporciona la opción de crear informes utilizando el objeto de posible cliente y contacto en el mismo informe. Al relacionar con el cliente potencial y el objeto de contacto, la variable [!DNL Marketo Measure] Persona permite crear informes sobre ambos objetos dentro del mismo informe. Esto resulta especialmente útil cuando un posible cliente se ha convertido en un contacto. En un [!DNL Marketo Measure] Registro de persona: verá una búsqueda del registro de contacto o posible cliente correspondiente, una lista relacionada de los puntos de contacto vinculados a la persona y el ID de persona (que siempre es la dirección de correo electrónico del contacto o posible cliente). Dado que la variable [!DNL Marketo Measure] La persona se relaciona con el cliente potencial y el objeto de contacto. Nunca habrá un [!DNL Marketo Measure] Registro de persona vinculado a un punto de contacto de atribución de comprador. A continuación se muestra un ejemplo de [!DNL Marketo Measure] Registro de persona en Salesforce:

![](assets/4.png)

## [!DNL Marketo Measure] Prueba A/B {#marketo-measure-a-b-test}

Si está ejecutando pruebas A/B mediante [!DNL Optimizely] Para VWO (Visual Web Optimizer), puede conectar esas cuentas a su [!DNL Marketo Measure] para ver datos de prueba A/B en Salesforce. El [!DNL Marketo Measure] El objeto de prueba A/B esencialmente le permite tomar datos de prueba A/B de Optimizely/VWO y vincularlos a posibles clientes y contactos.

![](assets/5.png)

El [!DNL Marketo Measure] El objeto de prueba A/B se muestra como una lista relacionada en [!UICONTROL Posibles clientes], [!UICONTROL Contactos] y [!UICONTROL Oportunidad] páginas. La lista muestra todos los experimentos y variaciones que está ejecutando a través de Optimizely o VWO, y le permite ver los experimentos/variaciones en relación con posibles clientes y contactos específicos.

## [!DNL Marketo Measure] Eventos {#marketo-measure-events}

El [!DNL Marketo Measure] El objeto Events le permite realizar un seguimiento de eventos específicos que se producen en el sitio web. Para realizar un seguimiento de eventos específicos que se producen en el sitio web, se debe agregar código personalizado a las páginas, además del [!DNL Marketo Measure] Javascript. La información capturada se mostrará dentro de la variable [!DNL Marketo Measure] Lista relacionada con objetos, que se puede encontrar en la [!UICONTROL Posibles clientes], [!UICONTROL Contactos] y [!UICONTROL Oportunidad] páginas. El [!DNL Marketo Measure] Objeto Events *no tiene* vínculo a los datos de atribución. El propósito de este objeto es ver si las personas están realizando acciones específicas en el sitio web.

## [!DNL Marketo Measure] Campos {#marketo-measure-fields}

Datos capturados por el [!DNL Marketo Measure] Javascript se insertará en el [!DNL Marketo Measure] Campos dentro de nuestro [!DNL Marketo Measure] Objetos. Algunos campos solo están presentes en ciertos objetos. Para ver un glosario de todos los [!DNL Marketo Measure] campos, por favor [haga clic aquí](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md). Para una visualización de la cual [!DNL Marketo Measure] Objeto cada [!DNL Marketo Measure] El campo está relacionado con, por favor [haga clic aquí](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

## [!DNL Marketo Measure] Informes y paneles {#marketo-measure-reports-and-dashboards}

El [!DNL Marketo Measure] Informes y paneles que se añaden a su [!DNL Salesforce] le ofrece funciones de creación de informes y visualización de datos listas para usar. Estos son básicos [!DNL Marketo Measure] informes de para permitirle organizar, analizar y comprender rápidamente los datos de puntos de contacto.
