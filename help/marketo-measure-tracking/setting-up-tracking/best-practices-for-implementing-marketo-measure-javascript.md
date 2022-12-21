---
description: Prácticas recomendadas para implementar [!DNL Marketo Measure] JavaScript - [!DNL Marketo Measure] - Documentación del producto
title: Prácticas recomendadas para implementar [!DNL Marketo Measure] JavaScript
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
source-git-commit: cf144eb4bc9282ae6a260acd3735f24644292a19
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---

# Prácticas recomendadas para implementar [!DNL Marketo Measure] JavaScript {#best-practices-for-implementing-marketo-measure-javascript}

## Resumen {#overview}

La variable [!DNL Marketo Measure] JavaScript realiza un seguimiento de las interacciones de marketing digital de los visitantes web y es clave para la variable [!DNL Marketo Measure] capacidad para crear datos de Touchpoint en línea. Tener [!DNL Marketo Measure] JavaScript implementado correcta y exhaustivamente en todos los sitios se asegurará de que los datos de sesión recopilados produzcan datos precisos sobre los puntos de contacto.

Incoherencias en la implementación de la variable [!DNL Marketo Measure] JavaScript provocará saltos en los datos de la sesión que pueden resultar en lo siguiente:

* Atribución de canal/subcanal incorrecta
* Pérdida de datos de origen
* Alto nivel de tráfico directo erróneo
* Informes incoherentes

[!DNL Marketo Measure] JavaScript es una parte fundamental de su [!DNL Marketo Measure] cuenta y clave para su éxito!

## Práctica recomendada {#best-practice}

A la hora de implementar y administrar su [!DNL Marketo Measure] JavaScript, tenga en cuenta las siguientes prácticas recomendadas.

* Confirme que todos los dominios están enumerados en su [!DNL Marketo Measure] account
   * Si tiene dudas con respecto a sus dominios, póngase en contacto con el servicio de asistencia
* Implementar JavaScript en TODAS las páginas.
   * Si coloca JavaScript solo en determinadas páginas, se romperán los datos de la sesión, lo que provocará errores [!DNL Marketo Measure] data
* Para un formulario del sitio desde el que no desee crear puntos de contacto, asegúrese de agregar la variable [!DNL Marketo Measure] Excluir script
   * Esta secuencia de comandos de exclusiones garantizará que la variable [!DNL Marketo Measure] los datos de la sesión no se interrumpirán y los datos de origen permanecerán en su lugar
      * Algunos ejemplos de formularios comunes que se deben suprimir son:
         * Inicio de sesión del cliente
         * Formularios de contraseña olvidada
         * Cancelar la suscripción de formularios
         * Formularios de aplicación de carrera
* Revise las secciones &quot;Consideraciones adicionales&quot; y &quot;Forms para prestar más atención a&quot; de la sección [!DNL Marketo Measure] Recurso de secuencia de comandos enumerado a continuación para comprobar si hay escenarios que puedan necesitar un control especial

## Práctica recomendada para mantenimiento {#best-practice-for-maintenance}

Mientras se configura la variable [!DNL Marketo Measure] JavaScript se cubre durante la implementación inicial, los cambios en el sitio o el equipo que lo administra pueden provocar interrupciones en [!DNL Marketo Measure] seguimiento. Le recomendamos que confirme el [!DNL Marketo Measure] JavaScript se implementa de manera correcta y completa una vez al año. Además, si su organización tiene algún tipo de documentación del protocolo de cambio para el sitio web, asegúrese de que haya una parte que explique que [!DNL Marketo Measure] JavaScript debe conservarse o agregarse a todas las páginas nuevas.

Otras razones para que esto pueda déclencheur una revisión de la configuración de JavaScript son:

* Volumen de negocio en su equipo de marketing
* Cambios y actualizaciones en la estructura del sitio
* Migraciones del sitio
* Cambios en el dominio
* Adquisiciones de otras empresas y sus propiedades web
