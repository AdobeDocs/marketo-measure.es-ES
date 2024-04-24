---
description: Notas de la versión actual de  [!DNL Marketo Measure]
title: Notas de la versión actual
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: cbb2afd48c0e462768be0a7cfe56007ae285c492
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 71%

---

# Notas de la versión: 2024 {#release-notes-2024}

A continuación, encontrará todas las funciones nuevas y actualizadas de nuestras versiones de 2024.

## Versión del segundo trimestre {#q2-release}

<p>

**Desuso de las funciones de Marketo Measure en respuesta a la eliminación gradual de las cookies de terceros**

En respuesta a la creciente preocupación por la privacidad, las cookies de terceros se están eliminando gradualmente, y la fecha límite del tercer trimestre de 2024 de Google Chrome señala su fin. Marketo Measure dejará de utilizar determinadas funciones que dependen de cookies de terceros, específicamente el seguimiento entre dominios y la atribución de visualizaciones, que dependen de la cookie de impresión Google/DoubleClick. Este cambio no afectará a otras funcionalidades de Marketo Measure ni al uso de cookies de terceros. Siguiendo la cronología de Google, se espera que estas funcionalidades estén en desuso el 1 de junio, aunque los datos recopilados antes de esta fecha seguirán siendo accesibles para los clientes.

* [Adaptación al desuso de las cookies de terceros en Marketo Measure](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Cookies de Marketo Measure](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**Despliegue gradual de nuestra gestión de errores mejorada**

Presentamos una implementación por fases de la gestión de errores mejorada para los trabajos de exportación, que comienza con las notificaciones inmediatas en la aplicación de los errores de permisos y la transición a un nuevo método en el que los trabajos de exportación se pausarán en el punto de error. Este cambio tiene como objetivo mejorar la integridad y visibilidad de los datos, lo que garantiza procesos de administración de datos más fluidos y fiables para nuestros usuarios. Para garantizar una transición sin problemas y una interrupción mínima de sus operaciones, estamos implementando estos cambios en dos fases:

* Disponibilidad inmediata de las notificaciones pulse: recibirá notificaciones pulse en la aplicación para detectar errores de permisos durante los trabajos de exportación. Esto no interrumpirá sus exportaciones, pero le ayudará a conocer los errores sin que ello afecte a sus trabajos actuales.
* Implementación de la pausa de trabajos el 25 de abril: **POSPUESTO** - Después de considerar los comentarios de los usuarios de Marketo Measure, hemos decidido posponer la implementación de la pausa de los trabajos de exportación en el punto de error, originalmente programado para el 25 de abril. Reconocemos que detener los empleos tal vez no sea el enfoque más eficaz. Estamos comprometidos a encontrar una mejor solución que mantenga la integridad de los datos y minimice las interrupciones. Nos mantendremos al margen de cualquier cambio en nuestro sistema actual hasta que podamos garantizar una solución que se ajuste más a las necesidades de nuestros usuarios.

_Por qué es importante_

Mejor integridad de los datos e integración a prueba de futuro: detenemos el trabajo a la primera señal de que haya problemas para evitar la pérdida de datos y garantizar la precisión. Esto permite una rápida resolución de problemas, mejorando la calidad de la exportación de datos y la fiabilidad del sistema.

Visibilidad inmediata: la introducción de las notificaciones pulse permite una respuesta rápida a los errores de permisos, lo que evita posibles impactos en las operaciones.

_Apoyo a la transición_

Para ayudarle a adaptarse a este cambio, [hemos creado una documentación](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"} con descripciones claras de los errores y pasos exhaustivos para la resolución de problemas.

<br>

**Acción necesaria para la integración con LinkedIn**

LinkedIn ha lanzado recientemente una versión actualizada de su API de sincronización de posibles clientes. Vuelva a autenticar la conexión de LinkedIn en su instancia de Marketo Measure antes del 20 de mayo para evitar interrupciones.

