---
description: Notas de la versión actual - [!DNL Marketo Measure]
title: Notas de la versión actual
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 4a3b8a1df9d8a675d977b08693b9d7facb64bc02
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 1%

---

# Notas de la versión: 2024 {#release-notes-2024}

Consulte a continuación todas las funciones nuevas y actualizadas de nuestras versiones de 2024.

## Versión del segundo trimestre {#q2-release}

<p>

**Obsolescencia de las funciones de Marketo Measure en respuesta a la eliminación gradual de las cookies de terceros**

En respuesta a las crecientes preocupaciones por la privacidad, las cookies de terceros se están eliminando gradualmente, y el plazo del tercer trimestre de 2024 de Google Chrome indica su fin. Marketo Measure dejará de utilizar determinadas funciones que dependen de cookies de terceros, específicamente el seguimiento entre dominios y la atribución de visualizaciones, que dependen de la cookie de impresión Google/DoubleClick. Este cambio no afectará a otras funcionalidades de Marketo Measure ni al uso de cookies de origen. Siguiendo el cronograma de Google, se espera que estas funcionalidades estén en desuso antes del 1 de junio, aunque los datos recopilados antes de esta fecha seguirán siendo accesibles para los clientes.

* [Adaptación al desuso de cookies de terceros en Marketo Measure](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Cookies de Marketo Measure](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**Despliegue gradual de nuestra gestión de errores mejorada**

Presentamos una implementación por fases de la gestión de errores mejorada para los trabajos de exportación, que comienza con las notificaciones inmediatas de pulso en la aplicación para los errores de permisos y la transición el 25 de abril a un nuevo enfoque en el que los trabajos de exportación se pausarán en el punto de error. Este cambio tiene como objetivo mejorar la integridad y visibilidad de los datos, lo que garantiza procesos de administración de datos más fluidos y fiables para nuestros usuarios. Para garantizar una transición sin problemas y una interrupción mínima de sus operaciones, estamos implementando estos cambios en dos fases:

* Disponibilidad inmediata de notificaciones Pulse: recibirá notificaciones Pulse en la aplicación para detectar errores de permisos durante los trabajos de exportación. Esto no interrumpirá sus exportaciones, pero le ayudará a conocer los errores sin afectar a sus trabajos actuales.
* Implementación de la pausa de trabajos el 25 de abril: a partir del 25 de abril, si el sistema encuentra un error de permisos durante un trabajo de exportación, detendrá el trabajo para asegurarse de que no se omitan datos. Se le notificará cualquier problema y, una vez corregidos los permisos, el trabajo de exportación se reanudará sin problemas desde el lugar en el que se detuvo.

_Por qué esto importa_

Integridad de datos mejorada e integración a prueba de futuro: detenemos el trabajo a la primera señal de problemas para evitar la pérdida de datos y garantizar la precisión. Esto permite una rápida resolución de problemas, mejorando la calidad de la exportación de datos y la fiabilidad del sistema.

Visibilidad inmediata: la introducción de las notificaciones push permite una respuesta rápida a los errores de permisos, lo que evita posibles impactos en las operaciones.

_Apoyo a la transición_

Para ayudarle a adaptarse a este cambio, [hemos creado la documentación](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"} con descripciones claras de los errores y pasos exhaustivos para la resolución de problemas.

**Acción necesaria para la integración de LinkedIn**

LinkedIn ha lanzado recientemente una versión actualizada de su API de sincronización de posibles clientes. Vuelva a autenticar la conexión de LinkedIn en su instancia de Marketo Measure antes del 20 de mayo para evitar interrupciones.
