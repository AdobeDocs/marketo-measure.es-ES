---
unique-page-id: 18874574
description: "[!DNL Marketo Measure] Campos en Standard [!DNL Salesforce] Objetos - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Campos en Standard [!DNL Salesforce] Objetos"
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 1%

---

# Campos de [!DNL Marketo Measure] en objetos estándar de [!DNL Salesforce] {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero sigue viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

Obtenga información sobre los distintos [!DNL Marketo Measure] campos que se añaden a [!DNL Salesforce] objetos estándar.

## Cuenta {#account}

Puntuación de participación predictiva: este campo se utiliza con nuestra función ABM para proporcionar una puntuación relacionada con la participación de la cuenta y tiene en cuenta muchos factores, como la actualización de las vistas de página, cuántos contactos están asociados a la cuenta, si hay una operación cerrada, etc.

## Caso {#case}

Añadimos campos al objeto Case relacionados con los hitos de contacto Primer contacto y Creación de posibles clientes. Esto es para clientes que utilizan el objeto Case en lugar del posible cliente o contacto y también sirve para el propósito de otra manera de ver los datos en caso de que un cliente no quisiera que creáramos registros de Touchpoint.

Fuente de punto de contacto (FT): esta es la fuente de la interacción de primer contacto.

Origen del punto de contacto (LC): Esta es la fuente de la interacción táctil de la creación de posibles clientes.

Canal de marketing (FT): Este es el canal de marketing de la interacción de primer contacto.

Canal de marketing (LC): Este es el canal de marketing de la interacción táctil de creación de posibles clientes.

Nombre de la campaña de publicidad (FT): Esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o [!DNL Salesforce] Campaña de interacción de primer contacto.

Nombre de la campaña de publicidad (LC): Esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o [!DNL Salesforce] Campaña de la [!UICONTROL creación de clientes potenciales] interacción táctil.

Página de aterrizaje (FT): esta es la página de aterrizaje de la interacción de primer contacto.

Página de aterrizaje (LC): Esta es la página de aterrizaje de [!UICONTROL creación de clientes potenciales] interacción táctil.

Fecha del punto de contacto (FT): Es la fecha de la primera interacción de contacto.

Fecha de punto de contacto (LC): es la fecha de la interacción táctil de creación de posibles clientes.

## Campaña {#campaign}

Solo se han añadido 4 campos, 1 botón y 1 regla de validación.

ID único: este campo se utiliza internamente para realizar un seguimiento de las diferentes campañas sincronizadas con [!DNL Marketo Measure].

Habilitar puntos de contacto del comprador: este campo es para la sincronización real de campañas para la inclusión de atribuciones sin conexión y datos históricos.

Fecha de inicio del punto de contacto: este campo se utiliza para establecer una fecha de inicio de la aplicación de puntos de contacto a campañas históricas.

Fecha de finalización del punto de contacto: este campo se utiliza para establecer una fecha de finalización para aplicar puntos de contacto a campañas históricas. Un ejemplo común sería la inclusión de campañas digitales previas a la[!DNL Marketo Measure] y, a continuación, estableciendo la fecha final como el día en que se aplicó la secuencia de comandos.

Fecha del punto de contacto de actualización masiva (botón): este botón se utiliza para administrar la fecha del punto de contacto de los miembros de la campaña cuando se sincroniza la campaña, ya que haremos referencia a la fecha de pertenencia a la campaña o a la primera fecha de respuesta predeterminada. En caso de que esos campos de fecha no sean una representación precisa de la fecha del punto de contacto real, utilizaríamos este botón para establecer la fecha del punto de contacto.

Actualizar [!DNL Marketo Measure] Atribución (regla de validación): esta regla está en desuso después de la versión 6.0 del paquete.

## Membresía de la campaña {#campaign-member}

Se han añadido 5 campos y 1 Déclencheur Apex con el paquete.

Estado del punto de contacto (posible cliente): este es un campo de diagnóstico relacionado con una función que no está activada de forma predeterminada. Utilizamos esto para comprender si se creó un punto de contacto con el registro de posible cliente relacionado o, si no es así, por qué.

Estado del punto de contacto (contacto): este es un campo de diagnóstico relacionado con una función que no está activada de forma predeterminada. Utilizamos esto para comprender si se creó un punto de contacto con el registro de contacto relacionado o, si no es así, por qué.

Estado del punto de contacto (oportunidad): este es un campo de diagnóstico relacionado con una función que no está activada de forma predeterminada. Utilizamos esto para comprender si se creó un punto de contacto con el registro de oportunidad relacionado o, si no es así, por qué.

Fecha de estado del punto de contacto: es la fecha en la que se rellenaron los campos de diagnóstico.

Fecha del punto de contacto del comprador: esto está relacionado con la [!UICONTROL Actualización masiva de fecha de Touchpoint] del objeto Campaign. Cuando se utiliza, se aplica la fecha de punto de contacto definida al miembro de la campaña.

OnCampaignMemberDelete: de forma predeterminada, [!DNL Salesforce] no aparece cuando se eliminan miembros de Campaign, lo que puede causar problemas con los informes de atribución precisos. Cuando se elimina un miembro de la campaña, esto se activa para informar a [!DNL Marketo Measure] para eliminar los puntos de contacto relacionados con ese miembro de campaña inexistente.

## Contacto {#contact}

Añadimos campos al objeto Contacto relacionados con los hitos de contacto Primer contacto y Creación de posibles clientes. Esto es para clientes que prefieren tener la atribución registrada directamente en los campos en lugar de crear registros de Touchpoint. La mayoría de nuestros clientes siguen la ruta de registro de Touchpoint, pero también utilizan estos campos dentro de su plataforma de automatización.

Fuente de punto de contacto (FT): esta es la fuente de la interacción de primer contacto.

Origen del punto de contacto (LC): Esta es la fuente de la interacción táctil de la creación de posibles clientes.

Canal de marketing (FT): Este es el canal de marketing de la interacción de primer contacto.

Canal de marketing (LC): Este es el canal de marketing de la interacción táctil de creación de posibles clientes.

Nombre de la campaña de publicidad (FT): Esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o [!DNL Salesforce] Campaña de interacción de primer contacto.

Nombre de la campaña de publicidad (LC): Esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o [!DNL Salesforce] Campaña de la [!UICONTROL creación de clientes potenciales] interacción táctil.

Página de aterrizaje (FT): esta es la página de aterrizaje de la interacción de primer contacto.

Página de aterrizaje (LC): Esta es la página de aterrizaje de [!UICONTROL creación de clientes potenciales] interacción táctil.

Fecha del punto de contacto (FT): Es la fecha de la primera interacción de contacto.

Fecha de punto de contacto (LC): es la fecha de la interacción táctil de creación de posibles clientes.

BizibleID: Se utiliza en relación con la atribución de actividades y la integración de métricas de seguimiento de llamadas para la asociación de contactos al punto de contacto.

## Cliente potencial {#lead}

Añadimos campos al objeto de posible cliente relacionado con los hitos de contacto Primer contacto y Creación de posibles clientes. Esto es para clientes que prefieren tener la atribución registrada directamente en los campos en lugar de crear registros de Touchpoint. La mayoría de nuestros clientes siguen la ruta de registro de Touchpoint, pero también utilizan estos campos dentro de su plataforma de automatización.

Fuente de punto de contacto (FT): esta es la fuente de la interacción de primer contacto.

Origen del punto de contacto (LC): Esta es la fuente de la interacción táctil de la creación de posibles clientes.

Canal de marketing (FT): Este es el canal de marketing de la interacción de primer contacto.

Canal de marketing (LC): Este es el canal de marketing de la interacción táctil de creación de posibles clientes.

Nombre de la campaña de publicidad (FT): Esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o [!DNL Salesforce] Campaña de interacción de primer contacto.

Nombre de la campaña de publicidad (LC): Esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o [!DNL Salesforce] Campaña de la interacción táctil de la creación del posible cliente.

Página de aterrizaje (FT): esta es la página de aterrizaje de la interacción de primer contacto.

Página de aterrizaje (LC): esta es la página de aterrizaje de la interacción táctil de creación de posibles clientes.

Fecha del punto de contacto (FT): Es la fecha de la primera interacción de contacto.

Fecha de punto de contacto (LC): es la fecha de la interacción táctil de creación de posibles clientes.

BizsibleID: se utiliza en relación con la atribución de actividades y la integración de métricas de seguimiento de llamadas para la asociación de posibles clientes con el punto de contacto.

## Cuenta {#account-1}

Se utiliza para nuestra asignación de cliente potencial a cuenta para nuestra función ABM. Rellenamos este campo para crear la relación de búsqueda entre los dos objetos.

## Oportunidad {#opportunity}

[!DNL Marketo Measure] Importe de oportunidad: este campo se utiliza en el escenario en el que se aprovecha un campo de importe personalizado en la oportunidad. Asignamos ese valor de campo personalizado a [!DNL Marketo Measure] Importe de oportunidad mediante un flujo de trabajo y, a continuación, lea este campo para nuestros campos de atribución de ingresos en el objeto de punto de contacto de atribución del comprador.

## Actividad {#activity}

BizibleID: Esto es para que relacionemos un punto de contacto con actividades para la atribución de actividades y la integración de métricas de seguimiento de llamadas.

Fecha del punto de contacto del comprador: este campo se puede rellenar mediante un flujo de trabajo para utilizarlo como fecha de atribución de actividades y se rellenará para nuestra integración de métricas de seguimiento de llamadas para saber cuándo se produjo la interacción.
