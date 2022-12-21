---
unique-page-id: 18874582
description: "[!DNL Marketo Measure] Objetos de Salesforce - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Objetos de Salesforce"
exl-id: d5d6f334-6531-40fa-b043-75b49d8f43d5
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 1%

---

# [!DNL Marketo Measure] Objetos de Salesforce {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero aún así ver &quot;Bizible&quot; en su CRM. Estamos trabajando para que esto se actualice y el cambio de marca se reflejará pronto en su CRM.

When [!DNL Marketo Measure] está instalado en [!DNL Salesforce] (SFDC), varias [!DNL Marketo Measure] Se agregan objetos. Este artículo proporciona una explicación de varias de estas [!DNL Marketo Measure] Objetos. Algunos objetos que [!DNL Marketo Measure] agrega a [!DNL Salesforce] son:

* [Punto de contacto del comprador](#touchpoint)
* [Punto de contacto de atribución del comprador](#attribution)
* [[!DNL Marketo Measure] Persona](#person)
* [[!DNL Marketo Measure] Prueba A/B](#ab)
* [[!DNL Marketo Measure] Eventos](#events)

Los puntos de contacto capturados por los elementos que desea rastrear se escribirán en los objetos personalizados creados mediante la instalación del [!DNL Bizible Salesforce] paquete.

[!DNL Marketo Measure] Los objetos están relacionados con normas específicas [!DNL Salesforce] Objetos. Esto le permite informar sobre [!DNL Marketo Measure] y [!DNL Salesforce] Objetos juntos. La tabla siguiente muestra cuál [!DNL Salesforce] Objeto [!DNL Marketo Measure] El objeto está relacionado con.

![](assets/1-1.png)

## Punto de contacto del comprador {#buyer-touchpoint}

La variable [!UICONTROL Punto de contacto del comprador] (BT) El objeto cuenta la historia de marketing de un individuo. Contiene todos los datos relacionados con los puntos de contacto de marketing generados por los posibles clientes y los contactos. El BT muestra información como el canal de marketing del que provino el punto de contacto o qué campaña de publicidad trajo ese posible posible cliente o contacto a su sitio web.

El objeto BT es visible en las páginas posibles clientes y contactos como un **Lista relacionada** (ver imagen más abajo).

![](assets/2-1.png)

La lista relacionada con BT muestra todos los puntos de contacto que pertenecen al posible cliente o contacto. Dentro de la lista están personalizados [!DNL Marketo Measure] Campos que proporcionan más detalles sobre cada punto de contacto. Al hacer clic en el número de ID de punto de contacto del comprador, se le dirigirá a la página Detalle de punto de contacto del comprador, que proporciona aún más detalles sobre el punto de contacto, como la primera página web que visitó el posible cliente o contacto durante esa sesión web (**página de aterrizaje**).

## Punto de contacto de atribución del comprador {#buyer-attribution-touchpoint}

La variable [!UICONTROL Punto de contacto de atribución del comprador] El objeto cuenta la historia de las interacciones de marketing de los contactos relacionadas con una oportunidad. Muestra el *atribución* datos relacionados con los puntos de contacto de marketing. Este objeto permite ver cuánto crédito por ingresos se atribuye a cada punto de contacto de marketing. El tipo de modelo de atribución que utilice determinará el porcentaje de ingresos atribuido a los puntos de contacto.

Los puntos de contacto de atribución de comprador (BAT) solo se crean una vez que se crea una oportunidad relacionada con contactos que tienen datos de punto de contacto de comprador (BT). Las MTD no se crearán sin una oportunidad. Una vez creada la oportunidad, el objeto BAT utilizará la variable [!DNL Salesforce] *Importe* en el campo Oportunidad para comprender cuántos ingresos se atribuyen a los puntos de contacto.

A **flujo de trabajo** debe crearse si utiliza un [campo Cantidad personalizada](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md) para mostrar los ingresos en el objeto de oportunidad. [!DNL Marketo Measure] no puede leer la información que aparece en los campos Cantidad personalizada y, por lo tanto, no puede rellenar los datos de atribución de ingresos en los puntos de contacto. Este flujo de trabajo utilizará la variable **[!DNL Marketo Measure]Cantidad de oportunidad** Campo, uno de los [!DNL Marketo Measure] campos personalizados, para asignar el valor de ingresos del campo Cantidad personalizada al campo Cantidad de oportunidad.

![](assets/3-1.png)

El objeto BAT es visible en la variable [!UICONTROL Oportunidad], [!UICONTROL Contacto]y [!UICONTROL Cuenta] Objeto como lista relacionada. Esta lista muestra todos los puntos de contacto con los datos de atribución pertenecientes a una oportunidad. Si hace clic en el ID de punto de contacto de atribución de comprador, se le dirigirá a la página Detalle de punto de contacto de atribución de comprador . Aquí podrá ver datos de atribución más específicos e información sobre la procedencia del punto de contacto (similar a lo que proporciona el objeto Touchpoint de Comprador).

## [!DNL Marketo Measure] Persona {#marketo-measure-person}

La variable [!DNL Marketo Measure] El objeto Persona relaciona los objetos Posible cliente y Contacto. De forma predeterminada, Salesforce no proporciona la opción de crear informes utilizando el objeto posible cliente y contacto en el mismo informe. Al relacionar el posible cliente y el objeto de contacto, la variable [!DNL Marketo Measure] Persona le permite informar sobre ambos objetos dentro del mismo informe. Esto resulta especialmente útil cuando un posible cliente se ha convertido en un contacto. En un [!DNL Marketo Measure] Registro de persona verá una búsqueda del registro de posible cliente o contacto correspondiente, una lista relacionada de los puntos de contacto asociados a la persona y el ID de persona (que siempre es la dirección de correo electrónico del posible cliente o contacto). Dado que la variable [!DNL Marketo Measure] Persona relacionada con el objeto Posible cliente y contacto, nunca habrá un [!DNL Marketo Measure] Registro de persona vinculado a un punto de contacto de atribución de comprador. A continuación se muestra un ejemplo de [!DNL Marketo Measure] Registro de persona en Salesforce:

![](assets/4.png)

## [!DNL Marketo Measure] Prueba A/B {#marketo-measure-a-b-test}

Si está ejecutando pruebas A/B a través de [!DNL Optimizely] o VWO (Visual Web Optimizer), puede conectar esas cuentas a su [!DNL Marketo Measure] para ver los datos de prueba A/B en Salesforce. La variable [!DNL Marketo Measure] El objeto de prueba A/B básicamente le permite tomar datos de prueba A/B de Optimizely/VWO y enlazar los datos a posibles clientes y contactos.

![](assets/5.png)

La variable [!DNL Marketo Measure] El objeto de prueba A/B se muestra como una lista relacionada en [!UICONTROL Posibles clientes], [!UICONTROL Contactos] y [!UICONTROL Oportunidad] páginas. La lista muestra todos los experimentos y variaciones que está realizando mediante Optimizely o VWO, y le permite ver los experimentos/variaciones en relación con posibles clientes y contactos específicos.

## [!DNL Marketo Measure] Eventos {#marketo-measure-events}

La variable [!DNL Marketo Measure] El objeto Eventos permite rastrear eventos específicos que se producen en el sitio web. Para rastrear eventos específicos que suceden en el sitio web, se debe agregar código personalizado a las páginas además del [!DNL Marketo Measure] Javascript. La información capturada se muestra dentro de la variable [!DNL Marketo Measure] Lista relacionada con objetos, que se puede encontrar en la [!UICONTROL Posibles clientes], [!UICONTROL Contactos] y [!UICONTROL Oportunidad] páginas. La variable [!DNL Marketo Measure] Objeto Events *no* se vincula a los datos de atribución. El propósito de este objeto es ver si las personas están realizando acciones específicas en el sitio web.

## [!DNL Marketo Measure] Campos {#marketo-measure-fields}

Los datos que captura el [!DNL Marketo Measure] Javascript se insertará en la variable [!DNL Marketo Measure] Los campos dentro de nuestra [!DNL Marketo Measure] Objetos. Determinados campos solo están presentes en determinados objetos. Para un glosario de todas las variables [!DNL Marketo Measure] campos, por favor [haga clic aquí](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md). Para una visualización de cuál [!DNL Marketo Measure] Objeto each [!DNL Marketo Measure] Las actividades sobre el terreno se refieren a [haga clic aquí](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

## [!DNL Marketo Measure] Informes y tableros {#marketo-measure-reports-and-dashboards}

La variable [!DNL Marketo Measure] Informes y tableros que se agregaron al [!DNL Salesforce] proporciona funciones de creación de informes y visualización de datos integradas. Estos son básicos [!DNL Marketo Measure] informes para que pueda organizar, analizar y comprender rápidamente los datos de puntos de contacto.
