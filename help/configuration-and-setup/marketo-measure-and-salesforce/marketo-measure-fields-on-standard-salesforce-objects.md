---
unique-page-id: 18874574
description: "[!DNL Marketo Measure] Campos en Estándar [!DNL Salesforce] Objetos - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Campos en Estándar [!DNL Salesforce] Objetos"
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 0%

---

# [!DNL Marketo Measure] Campos en Estándar [!DNL Salesforce] Objetos {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero aún así ver &quot;Bizible&quot; en su CRM. Estamos trabajando para que esto se actualice y el cambio de marca se reflejará pronto en su CRM.

Obtenga información sobre las distintas [!DNL Marketo Measure] campos que se agregan a [!DNL Salesforce] objetos estándar.

## Cuenta {#account}

Puntuación de participación predictiva: Este campo se utiliza con nuestra función ABM para proporcionar una puntuación relacionada con la participación de la cuenta y tiene en cuenta muchos factores, como la actualización de las vistas de página, cuántos contactos están asociados a la cuenta, si hay una opción cerrada, etc.

## Caso {#case}

Añadimos campos al objeto Case relacionados con los hitos de contacto Primer toque y Creación de posibles clientes . Esto es para clientes que utilizan el objeto Case en lugar del posible cliente o contacto y también sirve para el propósito de otra forma de ver los datos en caso de que un cliente no quisiera que creáramos registros de Touchpoint.

Origen de punto de contacto (FT): Esta es la fuente de la interacción de primer contacto.

Fuente de Touchpoint (LC): Esta es la fuente de la interacción táctil de creación de posibles clientes.

Canal de marketing (FT): Este es el canal de marketing de la interacción de primer contacto.

Canal de marketing (LC): Este es el canal de marketing de la interacción de contacto con la creación de posibles clientes.

Nombre de campaña de publicidad (FT): Esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o [!DNL Salesforce] Campaña de la interacción de primer contacto.

Nombre de campaña de publicidad (LC): Esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o [!DNL Salesforce] Campaña de [!UICONTROL creación de posibles clientes] interacción táctil.

Página de aterrizaje (FT): Esta es la página de aterrizaje de la interacción de primer contacto.

Página de aterrizaje (LC): Esta es la página de aterrizaje del [!UICONTROL creación de posibles clientes] interacción táctil.

Fecha de punto de contacto (FT): Esta es la fecha de la interacción de primer contacto.

Fecha Touchpoint (LC): Esta es la fecha de la interacción con el contacto de creación de posibles clientes.

## Campaña {#campaign}

Solo se han añadido 4 campos, 1 botón y 1 regla de validación.

UniqueID: Este campo se utiliza internamente para rastrear las diferentes campañas sincronizadas con [!DNL Marketo Measure].

Habilitar puntos de contacto del comprador: Este campo es para la sincronización real de Campañas para la inclusión de atribución sin conexión y los datos históricos.

Fecha inicial de Touchpoint: Este campo se utiliza para establecer una fecha de inicio para la aplicación de puntos de contacto a campañas históricas.

Fecha de finalización del punto de contacto: Este campo se utiliza para establecer una fecha de finalización para aplicar puntos de contacto a campañas históricas. Un ejemplo común sería la inclusión de campañas digitales antes de[!DNL Marketo Measure] y luego estableciendo la fecha de finalización como el día en que se aplicó la secuencia de comandos.

Fecha del punto de contacto de actualización masiva (botón): Este botón se utiliza para administrar la fecha del punto de contacto de los miembros de la campaña cuando esta se sincroniza, ya que de forma predeterminada hacemos referencia a la fecha de pertenencia a la campaña o a la primera fecha de respuesta. En el caso de que esos campos de fecha no sean una representación precisa de la fecha del punto de contacto real, utilizaríamos este botón para establecer la fecha del punto de contacto.

Actualizar [!DNL Marketo Measure] Atribución (regla de validación): Esta regla está en desuso después de la versión 6.0 del paquete.

## Membresía de la campaña {#campaign-member}

Hay 5 campos y 1 Déclencheur Apex añadido con el paquete.

Estado del punto de contacto (posible cliente): Se trata de un campo de diagnóstico relacionado con una función que no está activada de forma predeterminada. Utilizamos esto para comprender si se creó un Touchpoint con el registro de posible cliente relacionado o, en caso contrario, por qué.

Estado de Touchpoint (Contacto): Se trata de un campo de diagnóstico relacionado con una función que no está activada de forma predeterminada. Utilizamos esto para comprender si se creó un Touchpoint con el registro de contacto relacionado o, en caso contrario, por qué.

Estado del punto de contacto (oportunidad): Se trata de un campo de diagnóstico relacionado con una función que no está activada de forma predeterminada. Utilizamos esto para comprender si se creó un Touchpoint con el registro de oportunidad relacionado o, si no, por qué.

Fecha de estado de Touchpoint: Esta es la fecha en la que se rellenaron los campos de diagnóstico.

Fecha del punto de contacto del comprador: Esto está relacionado con el [!UICONTROL Fecha del punto de contacto de actualización masiva] del objeto Campaign. Cuando se usa, aplicamos la fecha de Touchpoint definida al miembro de la campaña.

OnCampaignMemberDelete: Fuera de la caja, [!DNL Salesforce] no aparece cuando se eliminan miembros de Campaign, lo que puede causar problemas con los informes de atribución precisos. Cuando se elimina un miembro de campaña, se activa para informar [!DNL Marketo Measure] para eliminar los touchpoints relacionados con ese miembro inexistente de Campaign.

## Contacto {#contact}

Añadimos campos al objeto Contact relacionados con los hitos de contacto Primer toque y Creación de posibles clientes . Esto es para clientes que prefieren que la atribución se informe directamente en los campos en lugar de crear registros de Touchpoint. La mayoría de nuestros clientes van con la ruta de registro Touchpoint, pero también utilizan estos campos dentro de su plataforma de automatización.

Origen de punto de contacto (FT): Esta es la fuente de la interacción de primer contacto.

Fuente de Touchpoint (LC): Esta es la fuente de la interacción táctil de creación de posibles clientes.

Canal de marketing (FT): Este es el canal de marketing de la interacción de primer contacto.

Canal de marketing (LC): Este es el canal de marketing de la interacción de contacto con la creación de posibles clientes.

Nombre de campaña de publicidad (FT): Esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o [!DNL Salesforce] Campaña de la interacción de primer contacto.

Nombre de campaña de publicidad (LC): Esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o [!DNL Salesforce] Campaña de [!UICONTROL creación de posibles clientes] interacción táctil.

Página de aterrizaje (FT): Esta es la página de aterrizaje de la interacción de primer contacto.

Página de aterrizaje (LC): Esta es la página de aterrizaje del [!UICONTROL creación de posibles clientes] interacción táctil.

Fecha de punto de contacto (FT): Esta es la fecha de la interacción de primer contacto.

Fecha Touchpoint (LC): Esta es la fecha de la interacción con el contacto de creación de posibles clientes.

BizibleID: Se utiliza en relación con la integración de las métricas de atribución de actividades y seguimiento de llamadas para la asociación de contacto con el punto de contacto.

## Cliente potencial {#lead}

Añadimos campos al objeto Lead relacionados con los hitos de contacto Primer toque y Creación de posibles clientes . Esto es para clientes que prefieren que la atribución se informe directamente en los campos en lugar de crear registros de Touchpoint. La mayoría de nuestros clientes van con la ruta de registro Touchpoint, pero también utilizan estos campos dentro de su plataforma de automatización.

Origen de punto de contacto (FT): Esta es la fuente de la interacción de primer contacto.

Fuente de Touchpoint (LC): Esta es la fuente de la interacción táctil de creación de posibles clientes.

Canal de marketing (FT): Este es el canal de marketing de la interacción de primer contacto.

Canal de marketing (LC): Este es el canal de marketing de la interacción de contacto con la creación de posibles clientes.

Nombre de campaña de publicidad (FT): Esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o [!DNL Salesforce] Campaña de la interacción de primer contacto.

Nombre de campaña de publicidad (LC): Esta es la campaña de UTM, la campaña de publicidad de las redes de publicidad o [!DNL Salesforce] Campaña de la interacción táctil de creación de posibles clientes.

Página de aterrizaje (FT): Esta es la página de aterrizaje de la interacción de primer contacto.

Página de aterrizaje (LC): Esta es la página de aterrizaje de la interacción táctil de creación de posibles clientes.

Fecha de punto de contacto (FT): Esta es la fecha de la interacción de primer contacto.

Fecha Touchpoint (LC): Esta es la fecha de la interacción con el contacto de creación de posibles clientes.

BizibleID: Se utiliza en relación con la integración de las métricas de atribución de actividades y seguimiento de llamadas para la asociación de posibles clientes con el punto de contacto.

## Cuenta {#account-1}

Esto se utiliza para nuestra asignación de posibles clientes a cuentas para nuestra función ABM. Rellenamos este campo para crear la relación de búsqueda entre los dos objetos.

## Oportunidad {#opportunity}

[!DNL Marketo Measure] Cantidad de oportunidad: Este campo se utiliza en el escenario en el que se aprovecha un campo de cantidad personalizada en la oportunidad. Asignamos ese valor de campo personalizado a [!DNL Marketo Measure] Cantidad de oportunidad mediante un flujo de trabajo y, a continuación, lea este campo para nuestros campos de atribución de ingresos en el objeto Touchpoint de atribución de comprador.

## Actividad {#activity}

BizibleID: Esto es para nosotros para relacionar un punto de contacto con actividades para nuestra integración de métricas de atribución de actividad y seguimiento de llamadas.

Fecha del punto de contacto del comprador: Se trata de un campo que se puede rellenar mediante un flujo de trabajo para utilizarlo como fecha para la atribución de actividades y se rellenará para que nuestra integración de métricas de seguimiento de llamadas sepa cuándo se produjo la interacción.
