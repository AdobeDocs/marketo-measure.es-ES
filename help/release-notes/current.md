---
description: Notas de la versión actual de  [!DNL Marketo Measure]
title: Notas de la versión actual
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 9ea72d0e1cf0f754cc8fe844944b93705fb2b12f
workflow-type: tm+mt
source-wordcount: '1375'
ht-degree: 94%

---

# Notas de la versión: 2024 {#release-notes-2024}

A continuación, encontrará todas las funciones nuevas y actualizadas de nuestras versiones de 2024.

## Versión del cuarto trimestre {#q4-release}

### Comportamiento de transferencia de canal de nueva sesión

El canal de la sesión anterior ahora se transferirá si una nueva sesión se inicia dentro de los siete días posteriores a 30 minutos de inactividad, aplicándose solo a las visitas directas (sin referente ni referentes internos). Después de siete días de inactividad, la sesión será Directa/Otros de forma predeterminada. Los datos de sesiones anteriores no anularán los canales no directos.

Además, las sesiones que utilizan el inicio de sesión social (Google, Microsoft o Apple) ahora se combinan en una sesión continua, lo que garantiza una experiencia más fluida. Sin esta opción de transferencia, los inicios de sesión sociales podrían crear sesiones independientes debido a diferencias de referentes externos.

Para los clientes nuevos, la transferencia del canal de sesión es ahora el comportamiento predeterminado. Los clientes existentes pueden habilitarlo activando la opción Transferencia de canal de sesión en Configuración > Atribución Everytouch. Una vez activada, esta configuración no se puede deshacer.

Documentación: [Definición de sesiones web de Marketo Measure](https://experienceleague.adobe.com/es/docs/marketo-measure/using/marketo-measure-tracking/setting-up-tracking/definition-of-marketo-measure-web-sessions){target="_blank"}

### Panel de control del retorno de la inversión de palabra clave

El nuevo tablero de ROI de palabras clave ofrece una perspectiva detallada del rendimiento de las campañas de búsqueda de pago, y proporciona una vista completa de los costes a nivel de palabra clave, los ingresos atribuidos, y los posibles clientes y las oportunidades generadas. Este tablero le ayuda a evaluar el ROI de cada palabra clave en Google AdWords, LinkedIn y Bing Ads, etc.

Documentación: [Panel de control del retorno de la inversión de palabra clave](https://experienceleague.adobe.com/es/docs/marketo-measure/using/marketo-measure-discover-ui/dashboards/keyword-roi-dashboard){target="_blank"}

### Reglas de segmentos mejoradas

Ahora puede crear segmentos utilizando los campos Campaña y Miembro de campaña, además de los campos Touchpoint y Contacto. Esta mejora le permite analizar y diseccionar los datos de forma más eficaz en Discover.

![Reglas de segmentos mejoradas](assets/mm-q4-release-1.png)

### Actualización: configuración de control de errores para exportaciones de CRM

Hemos escuchado sus comentarios sobre el método de detener el trabajo y estamos introduciendo una nueva función en la interfaz de usuario. A partir de hoy, puede elegir si los trabajos de exportación deben pausarse cuando se producen errores. Use la nueva opción en **Mi cuenta** > **Configuración** > **CRM** > **General**. Este conmutador está activado de forma predeterminada para mejorar la integridad y visibilidad de los datos. Sin embargo, si prefiere no utilizar esta función, puede desactivarla en la interfaz de usuario y se reanudarán los trabajos de exportación. Esta actualización está diseñada para mejorar la fiabilidad de los procesos de administración de datos y, al mismo tiempo, ofrecerle un mayor control.

#### Fechas clave y despliegue gradual

1. **Disponibilidad de alternancia inmediata:** el conmutador ya está incluido en la interfaz de usuario y está habilitado de forma predeterminada para evitar que los datos se omitan durante los trabajos de exportación. Si prefiere que los trabajos de exportación sigan ejecutándose a pesar de que se encuentren errores, deshabilite la opción.

1. **Activación de pausa de trabajos el 1 de octubre:** a partir del 1 de octubre de 2024, si el conmutador está activado y se encuentra un error de nivel de registro durante un trabajo de exportación, el trabajo se pausa para garantizar que no se pierdan datos. Estos errores suelen deberse a la falta de permisos, a reglas de validación personalizadas aplicadas incorrectamente o a problemas en flujos de trabajo/activadores. Recibirá notificaciones sobre el problema y, una vez corregido, el trabajo de exportación se reanudará desde el punto de interrupción. Si decide excluirse de la pausa del trabajo, seguirá recibiendo notificaciones de problemas y, cuando se hayan corregido, los registros omitidos se vuelven a exportar automáticamente.

#### Por qué es importante

* **Mejor integridad de los datos e integración a prueba de futuro:** deteniendo el trabajo a la primera señal de que haya problemas para evitar la pérdida de datos y garantizar la precisión. Esto permite una rápida resolución de errores, lo que mejora la calidad de la exportación de datos y la fiabilidad general del sistema.

* **Visibilidad inmediata:** mediante las notificaciones de pulso, recibirá alertas oportunas por errores de permisos, lo que permitirá respuestas rápidas y minimizará los posibles impactos en sus operaciones.

#### Apoyo a la transición

Para ayudarle a adaptarse a este cambio, hemos creado una documentación sobre la nueva función con descripciones claras de los errores y pasos exhaustivos para la resolución de problemas.

* Nueva documentación: [Configuración de control de errores para exportaciones de CRM](/help/configuration-and-setup/marketo-measure-and-salesforce/crm-error-handling.md)
* [Notificaciones de errores](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md)

## Versión del tercer trimestre {#q3-release}

<p>

### Recordatorio: Degradaciones en el campo de Salesforce, 14 de junio

Como se anunció el año pasado, [eliminaremos gradualmente nuestros trabajos de exportación a objetos de contacto/posible cliente](https://nation.marketo.com/t5/employee-blogs/marketo-measure-salesforce-lead-and-contact-field-deprecation-06/ba-p/350179){target="_blank"} para simplificar nuestra integración y eliminar la necesidad de exportar a objetos estándar de Salesforce. Puede obtener los mismos datos de los objetos Touchpoint siguiendo los pasos [documentados aquí](/help/release-notes/previous-releases/2023.md#deprecations){target="_blank"}. También se compartirá documentación sobre la creación de flujos de trabajo para añadir estos datos al objeto de posible cliente/contacto. La obsolescencia entrará en vigor el 14 de junio de 2024.

Este cambio traerá dos ventajas clave:

* **Costes reducidos de API de Salesforce**: los clientes pueden esperar ver reducidos sus costes de API de Salesforce en aproximadamente un 10 %.
* **Integración optimizada**: el mayor número de errores en nuestros trabajos de exportación está relacionado con estos procesos. Su eliminación agilizará considerablemente nuestra integración.

### Panel de oportunidades atribuidas

Estamos encantados de presentar el nuevo [Panel de oportunidades atribuidas](/help/marketo-measure-discover-ui/dashboards/attributed-opportunity-dashboard.md){target="_blank"}, diseñado para proporcionarle una visión completa de cómo sus esfuerzos de marketing contribuyen a las oportunidades de canalización incipientes y maduras. Este panel le permite profundizar en los detalles de cada oportunidad abierta y cerrada atribuible a sus estrategias, con la flexibilidad de filtrar por etapa de oportunidad. Proporciona información sobre los canales, subcanales o campañas que ocupan los primeros puestos en términos de la cantidad de oportunidades atribuidas y muestra la cantidad total de oportunidades atribuidas junto con el recuento de oportunidades atribuidas abiertas y cerradas.

### Sincronización de cookies de Marketo Engage para Marketo Measure Ultimate

La sincronización de cookies de Marketo Engage ya está disponible para Marketo Measure Ultimate. Para utilizar esta función:

1. En la página Esquemas de AEP, edite el esquema Persona B2B y añada el grupo de campos “Detalles de persona del Marketo Engage”.
1. Al ingerir los datos en MMU, asigne el campo ID de cookie del grupo de campos al campo Cookies de Marketo Engage.

### Fases de boomerang habilitadas para clientes de nivel 2

Anteriormente, solo disponible para clientes de nivel 3, la función Fase de Boomerang también estará disponible para todos los clientes de nivel 2 a partir del 13 de junio de 2024. Para obtener información más detallada sobre esta funcionalidad, consulte la documentación siguiente.

* [Fases y puntos de contacto de Boomerang](/help/advanced-marketo-measure-features/boomerang/boomerang-stages-and-touchpoints.md){target="_blank"}
* [Configuración de fases de Boomerang](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md){target="_blank"}
* [Escenarios de fases de Boomerang](/help/advanced-marketo-measure-features/boomerang/boomerang-stage-scenarios.md){target="_blank"}

<p>

## Versión del segundo trimestre {#q2-release}

<p>

### Obsolescencia de las funciones de Marketo Measure en respuesta a la eliminación gradual de las cookies de terceros

En respuesta a la creciente preocupación por la privacidad, las cookies de terceros se están eliminando gradualmente, y la fecha límite del tercer trimestre de 2024 de Google Chrome señala su fin. Marketo Measure dejará de utilizar determinadas funciones que dependen de cookies de terceros, específicamente el seguimiento entre dominios y la atribución de visualizaciones, que dependen de la cookie de impresión Google/DoubleClick. Este cambio no afectará a otras funcionalidades de Marketo Measure ni al uso de cookies de terceros. Siguiendo la cronología de Google, se espera que estas funcionalidades estén en desuso el 1 de junio, aunque los datos recopilados antes de esta fecha seguirán siendo accesibles para los clientes.

* [Adaptación al desuso de las cookies de terceros en Marketo Measure](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Cookies de Marketo Measure](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

### Despliegue gradual de nuestra gestión de errores mejorada

Presentamos un despliegue por fases de la gestión de errores mejorada para los trabajos de exportación, comenzando con las notificaciones inmediatas en la aplicación para los errores de permisos y la transición a un nuevo enfoque en el que los trabajos de exportación se detendrán en el punto del error. Este cambio tiene como objetivo mejorar la integridad y visibilidad de los datos, lo que garantiza procesos de administración de datos más fluidos y fiables para nuestros usuarios. Para garantizar una transición sin problemas y una interrupción mínima de sus operaciones, estamos implementando estos cambios en dos fases:

* Disponibilidad inmediata de las notificaciones pulse: recibirá notificaciones pulse en la aplicación para detectar errores de permisos durante los trabajos de exportación. Esto no interrumpirá sus exportaciones, pero le ayudará a conocer los errores sin que ello afecte a sus trabajos actuales.
* Implementación de la pausa de trabajos el 25 de abril: **POSPUESTA**: después de tener en cuenta los comentarios de los usuarios de Marketo Measure, hemos decidido posponer la implementación de la pausa de los trabajos de exportación en el punto de error, programado originalmente para el 25 de abril. Reconocemos que detener los trabajos tal vez no sea el planteamiento más eficaz. Nos comprometemos a encontrar una mejor solución que mantenga la integridad de los datos y minimice las interrupciones. Nos realizaremos ningún cambio en nuestro sistema actual hasta que podamos garantizar una solución que se ajuste más a las necesidades de nuestros usuarios.

_Por qué es importante_

Mejor integridad de los datos e integración a prueba de futuro: detenemos el trabajo a la primera señal de que haya problemas para evitar la pérdida de datos y garantizar la precisión. Esto permite una rápida resolución de problemas, mejorando la calidad de la exportación de datos y la fiabilidad del sistema.

Visibilidad inmediata: la introducción de las notificaciones pulse permite una respuesta rápida a los errores de permisos, lo que evita posibles impactos en las operaciones.

_Apoyo a la transición_

Para ayudarle a adaptarse a este cambio, [hemos creado una documentación](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"} con descripciones claras de los errores y pasos exhaustivos para la resolución de problemas.

<br>

### Acción necesaria para la integración de LinkedIn

LinkedIn ha lanzado recientemente una versión actualizada de su API de sincronización de posibles clientes. Vuelva a autenticar la conexión de LinkedIn en su instancia de Marketo Measure antes del 20 de mayo para evitar interrupciones.
