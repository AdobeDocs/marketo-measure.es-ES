---
description: Prácticas recomendadas para la implementación [!DNL Marketo Measure] JavaScript - [!DNL Marketo Measure] - Documentación del producto
title: Prácticas recomendadas para implementar el JavaScript de  [!DNL Marketo Measure]
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 2%

---

# Prácticas recomendadas para implementar el JavaScript de [!DNL Marketo Measure] {#best-practices-for-implementing-marketo-measure-javascript}

## Información general {#overview}

El [!DNL Marketo Measure] JavaScript realiza un seguimiento de las interacciones de marketing digital de los visitantes web y es fundamental para el [!DNL Marketo Measure] capacidad para crear datos de Touchpoint en línea. Tener el [!DNL Marketo Measure] JavaScript implementado correctamente y de forma exhaustiva en todo el sitio se asegurará de que los datos de sesión recopilados produzcan datos de punto de contacto precisos.

Incoherencias en la implementación de [!DNL Marketo Measure] JavaScript interrumpirá los datos de la sesión, lo que puede provocar lo siguiente:

* Atribución de canal/subcanal incorrecta
* Pérdida de datos de origen
* Altos niveles de tráfico directo erróneo
* Informes incoherentes

[!DNL Marketo Measure] JavaScript es una parte fundamental de su [!DNL Marketo Measure] cuenta y clave de su éxito.

## Práctica recomendada {#best-practice}

Cuando se trata de implementar y administrar su [!DNL Marketo Measure] JavaScript, tenga en cuenta las siguientes prácticas recomendadas.

* Confirme que todos los dominios se han enumerado en la [!DNL Marketo Measure] account
   * Si tiene dudas con respecto a sus dominios, póngase en contacto con el servicio de asistencia
* Implementar JavaScript en TODAS las páginas.
   * Si coloca JavaScript solo en determinadas páginas, se producirán interrupciones en los datos de la sesión, lo que provocará errores [!DNL Marketo Measure] datos
* Para un formulario del sitio desde el que no desee crear puntos de contacto, asegúrese de añadir la variable [!DNL Marketo Measure] Excluir script
   * Este script de exclusiones garantizará que las variables [!DNL Marketo Measure] los datos de sesión no se interrumpen y los datos de origen permanecen en su lugar
      * Estos son algunos ejemplos de formularios comunes que se deben suprimir:
         * Inicios de sesión del cliente
         * Formularios de restablecimiento de contraseña
         * Cancelar suscripción a formularios
         * Formularios de solicitud de empleo
* Revise las secciones &quot;Consideraciones adicionales&quot; y &quot;Forms para Prestar atención adicional a&quot; de la sección Adición [!DNL Marketo Measure] Script de recurso que se enumera a continuación para comprobar si hay algún escenario que pueda necesitar una administración especial

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Mientras que la configuración del [!DNL Marketo Measure] JavaScript se cubre durante la implementación inicial, los cambios en el sitio o en el equipo que lo administra pueden provocar interrupciones en el [!DNL Marketo Measure] seguimiento. Le recomendamos que confirme la [!DNL Marketo Measure] Una vez al año, JavaScript se implementa de forma correcta y completa. Además, si su organización tiene algún tipo de documentación de protocolo de cambio para el sitio web, asegúrese de que haya una parte que explique eso [!DNL Marketo Measure] JavaScript debe conservarse o agregarse a todas las páginas nuevas.

Otras razones que podrían déclencheur revisar la configuración de JavaScript incluyen...

* Facturación en su equipo de marketing
* Cambios y actualizaciones en la estructura del sitio
* Migraciones del sitio
* Cambios en su dominio
* Adquisición de otras empresas y sus propiedades web
