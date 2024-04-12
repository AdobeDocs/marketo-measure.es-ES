---
unique-page-id: 18874574
description: "Campos de [!DNL Marketo Measure] en objetos de  [!DNL Salesforce] estándar - [!DNL Marketo Measure]"
title: "Campos de [!DNL Marketo Measure] en objetos de  [!DNL Salesforce]  estándar"
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: ht
source-wordcount: '1292'
ht-degree: 100%

---

# Campos de [!DNL Marketo Measure] en objetos de [!DNL Salesforce] estándar {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>
>Puede que vea instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero seguirá viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

Obtenga información sobre los distintos campos de [!DNL Marketo Measure] que se añaden a objetos de [!DNL Salesforce] estándar.

## Cuenta {#account}

Puntuación de participación predictiva: este campo se utiliza con nuestra función ABM para proporcionar una puntuación relacionada con la participación de la cuenta y tiene en cuenta muchos factores, como la actualización de las vistas de página, cuántos contactos están asociados a la cuenta, si hay una operación cerrada, etc.

## Caso {#case}

Añadimos campos al objeto Caso relacionados con los hitos de contacto Primer contacto y Creación del cliente potencial. Esto es para clientes que utilizan el objeto Case en lugar del cliente potencial o contacto y también sirve al efecto de otra manera de ver los datos en caso de que un cliente no quiera que creemos registros de Touchpoint.

Fuente de Touchpoint (FT): esta es la fuente de interacción del primer contacto.

Fuente del Touchpoint (LC): esta es la fuente de la interacción táctil de la creación del cliente potencial.

Canal de marketing (FT): este es el canal de marketing de la interacción de primer contacto.

Canal de marketing (LC): este es el canal de marketing de la interacción táctil de creación de posibles clientes.

Nombre de la campaña de publicidad (FT): esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o [!DNL Salesforce] la Campaña de interacción de primer contacto.

Nombre de la campaña de publicidad (LC): esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o Campaign de [!DNL Salesforce] de la interacción táctil de [!UICONTROL creación del cliente potencial].

Página de aterrizaje (FT): esta es la página de aterrizaje de la interacción de primer contacto.

 Página de aterrizaje (LC): esta es la página de aterrizaje de la interacción táctil de [!UICONTROL creación del cliente potencial].

Fecha de Touchpoint (FT): la fecha de la primera interacción del contacto.

Fecha de Touchpoint (LC): la fecha de la interacción táctil de creación de posibles clientes.

## Campaña {#campaign}

Solo se han añadido 4 campos, 1 botón y 1 regla de validación.

ID único: este campo se utiliza internamente para realizar un seguimiento de las diferentes campañas sincronizadas con [!DNL Marketo Measure].

Habilitar Buyer Touchpoints: este campo es para la sincronización real de campañas para la inclusión de atribuciones sin conexión y datos históricos.

Fecha de inicio de Touchpoint: este campo se utiliza para establecer una fecha de inicio de la aplicación de Touchpoints a campañas históricas.

Fecha de finalización de Touchpoint: este campo se utiliza para establecer una fecha de finalización para aplicar puntos de contacto a campañas históricas. Un ejemplo común sería la inclusión de campañas digitales previas a [!DNL Marketo Measure] y, a continuación, establecer la fecha final como el día en que se aplicó el script.

Fecha de Tourchpoint de actualización masiva (botón): este botón se utiliza para administrar la fecha de Touchpoint de los miembros de la campaña cuando se sincroniza la campaña, ya que se hace referencia a la fecha de abono a la campaña o a la primera fecha de respuesta predeterminada. En caso de que esos campos de fecha no sean una representación precisa de la fecha del punto de contacto real, utilizaríamos este botón para establecer la fecha del punto de contacto.

Actualizar [!DNL Marketo Measure] Atribución (regla de validación): esta regla está en desuso después de la versión 6.0 del paquete.

## Miembro de la campaña {#campaign-member}

Se han añadido 5 campos y 1 activador Apex con el paquete.

Estado del Touchpoint (cliente potencial): este es un campo de diagnóstico relacionado con una función que no está activada de forma predeterminada. Lo utilizamos para comprender si se ha creado un punto de contacto con el registro de cliente potencial relacionado o, si no es así, por qué.

Estado del Touchpoint (contacto): este es un campo de diagnóstico relacionado con una función que no está activada de forma predeterminada. Lo utilizamos para comprender si se ha creado un Touchpoint con el registro de contacto relacionado o, si no es así, por qué.

Estado del Touchpoint (oportunidad): este es un campo de diagnóstico relacionado con una función que no está activada de forma predeterminada. Lo utilizamos para comprender si se ha creado un Touchpoint con el registro de oportunidad relacionado o, si no es así, por qué.

Fecha de estado del Touchpoint: es la fecha en la que se se han rellenado los campos de diagnóstico.

Fecha de Buyer Touchpoint: está relacionada con el botón [!UICONTROL Fecha de Tourchpoint de actualización masiva] del objeto de Campaign. Cuando se utiliza, se aplica la fecha de Touchpoint definida al miembro de la campaña.

OnCampaignMemberDelete: de forma predeterminada, [!DNL Salesforce] no aparece cuando se eliminan miembros de Campaign, lo que puede causar problemas con los informes de atribución precisos. Cuando se elimina un miembro de la campaña, esto se activa para informar a [!DNL Marketo Measure] que elimine los Touchpoints relacionados con ese miembro de campaña inexistente.

## Contacto {#contact}

Añadimos campos al objeto Contacto relacionado con los hitos de contacto Primer contacto y Creación del cliente potencial. Esto es para clientes que prefieren tener la atribución registrada directamente en los campos en lugar de crear registros de Touchpoint. La mayoría de nuestros clientes siguen la ruta de registro de Touchpoint, pero también utilizan estos campos dentro de su plataforma de automatización.

Fuente de Touchpoint (FT): esta es la fuente de interacción del primer contacto.

Fuente del Touchpoint (LC): esta es la fuente de la interacción táctil de la creación del cliente potencial.

Canal de marketing (FT): este es el canal de marketing de la interacción de primer contacto.

Canal de marketing (LC): este es el canal de marketing de la interacción táctil de creación de posibles clientes.

Nombre de la campaña de publicidad (FT): esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o Campaña de [!DNL Salesforce] de interacción de primer contacto.

Nombre de la campaña de publicidad (LC): esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o Campaña de [!DNL Salesforce] de la interacción táctil de la [!UICONTROL creación de clientes potenciales].

Página de aterrizaje (FT): esta es la página de aterrizaje de la interacción de primer contacto.

Página de aterrizaje (LC): esta es la página de aterrizaje de la interacción táctil de la [!UICONTROL creación de clientes potenciales].

Fecha de Touchpoint (FT): la fecha de la primera interacción del contacto.

Fecha de Touchpoint (LC): la fecha de la interacción táctil de creación de posibles clientes.

BizibleID: se utiliza en relación con la atribución de actividades y la integración de métricas de seguimiento de llamadas para la asociación de contactos al touchpoint.

## Posible cliente {#lead}

Se añadieron campos al objeto de posible cliente relacionado con los hitos de contacto Primer contacto y Creación de posibles clientes. Esto es para clientes que prefieren tener la atribución registrada directamente en los campos en lugar de crear registros de Touchpoint. La mayoría de nuestros clientes siguen la ruta de registro de Touchpoint, pero también utilizan estos campos dentro de su plataforma de automatización.

Fuente de Touchpoint (FT): esta es la fuente de interacción del primer contacto.

Fuente del Touchpoint (LC): esta es la fuente de la interacción táctil de la creación del cliente potencial.

Canal de marketing (FT): este es el canal de marketing de la interacción de primer contacto.

Canal de marketing (LC): este es el canal de marketing de la interacción táctil de creación de posibles clientes.

Nombre de la campaña de publicidad (FT): esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o campaña de [!DNL Salesforce] de interacción de primer contacto.

Nombre de la campaña de publicidad (LC): esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o Campaña de [!DNL Salesforce] de la interacción táctil de la creación del posible cliente.

Página de aterrizaje (FT): esta es la página de aterrizaje de la interacción de primer contacto.

Página de aterrizaje (LC): genera la interacción táctil de creación de posibles clientes.

Fecha de Touchpoint (FT): la fecha de la primera interacción del contacto.

Fecha de Touchpoint (LC): la fecha de la interacción táctil de creación de posibles clientes.

BizsibleID: se utiliza en relación con la atribución de actividades y la integración de métricas de seguimiento de llamadas para la asociación de posibles clientes con el Touchpoint.

## Cuenta {#account-1}

Se utiliza para nuestra asignación de cliente potencial a cuenta para nuestra función ABM. Se rellena este campo para crear la relación de búsqueda entre los dos objetos.

## Oportunidad {#opportunity}

Importe de oportunidad de [!DNL Marketo Measure]: este campo se utiliza en el escenario en el que se utiliza un campo de importe personalizado en la Oportunidad. Asignamos ese valor de campo personalizado a Importe de oportunidad de [!DNL Marketo Measure] mediante un flujo de trabajo. A continuación, lea este campo para los campos de atribución de ingresos en el objeto de Touchpoint de atribución del comprador.

## Actividad {#activity}

BizibleID: esto es para que relacionemos un Touchpoint con actividades para la atribución de estas y la integración de métricas de seguimiento de llamadas.

Fecha de Buyer Touchpoint: este campo se puede rellenar mediante un flujo de trabajo para utilizarlo como fecha de atribución de actividades y se rellena para nuestra integración de métricas de seguimiento de llamadas para saber cuándo se produjo la interacción.
