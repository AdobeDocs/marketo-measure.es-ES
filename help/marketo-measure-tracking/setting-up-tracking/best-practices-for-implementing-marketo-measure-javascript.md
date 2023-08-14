---
description: Documentación del producto  [!DNL Marketo Measure] . Prácticas recomendadas para la implementación de JavaScript de  [!DNL Marketo Measure] .
title: Prácticas recomendadas para implementar el JavaScript de  [!DNL Marketo Measure]
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 100%

---

# Prácticas recomendadas para implementar el JavaScript de [!DNL Marketo Measure] {#best-practices-for-implementing-marketo-measure-javascript}

## Información general {#overview}

El JavaScript de [!DNL Marketo Measure] realiza un seguimiento de las interacciones de marketing digital de los visitantes web y es fundamental para la capacidad de [!DNL Marketo Measure] de crear datos de Touchpoint en línea. Tener el JavaScript de [!DNL Marketo Measure] implementado correctamente y de forma exhaustiva en todo el sitio le asegurará de que los datos de sesión recopilados produzcan datos precisos de Touchpoint.

Las incoherencias en la implementación del JavaScript de [!DNL Marketo Measure] provocarán interrupciones en los datos de sesión que pueden dar lugar a lo siguiente:

* Atribución de canal/subcanal incorrecta
* Pérdida de datos de origen
* Niveles altos de tráfico directo erróneo
* Creación de informes incoherentes

El JavaScript de [!DNL Marketo Measure] es una parte fundamental de su cuenta de [!DNL Marketo Measure] y la clave del éxito

## Práctica recomendada {#best-practice}

Cuando se trata de implementar y administrar el JavaScript de [!DNL Marketo Measure], tenga en cuenta las siguientes prácticas recomendadas.

* Confirme que todos los dominios se hayan enumerado en la cuenta de [!DNL Marketo Measure]
   * Si tiene dudas con respecto a sus dominios, póngase en contacto con el equipo de soporte
* Implementar JavaScript en TODAS las páginas.
   * Si coloca JavaScript solo en determinadas páginas, se producirán interrupciones en los datos de la sesión, lo que provocará errores de datos en [!DNL Marketo Measure]
* Para un formulario del sitio desde el que no desee crear Touchpoints, asegúrese de añadir el script de exclusión de [!DNL Marketo Measure]
   * Este script de exclusión garantizará que los datos de la sesión de [!DNL Marketo Measure] no se interrumpan y los datos de origen permanezcan en su lugar
      * Estos son algunos ejemplos de formularios comunes que se deben suprimir:
         * Inicios de sesión del cliente
         * Formularios de restablecimiento de contraseña
         * Cancelar la suscripción a formularios
         * Formularios de solicitud de empleo
* Revise las secciones “Consideraciones adicionales” y “Formularios a los que debe prestarse especial atención” de la sección Añadir recurso de script de [!DNL Marketo Measure] que se enumera a continuación, para comprobar si hay algún escenario que pueda necesitar un tratamiento especial

## Práctica recomendada para el mantenimiento {#best-practice-for-maintenance}

Mientras que la configuración de JavaScript de [!DNL Marketo Measure] se cubre durante la implementación inicial, los cambios en el sitio o en el equipo que lo administra pueden provocar interrupciones en el seguimiento de [!DNL Marketo Measure]. Le recomendamos que confirme si el JavaScript de [!DNL Marketo Measure] se implementa de forma correcta y completa una vez al año. Además, si su organización tiene algún tipo de documentación de protocolo de cambio para el sitio web, asegúrese de que haya una parte que explique que el JavaScript de [!DNL Marketo Measure] debe conservarse o añadirse a todas las páginas nuevas.

Otras razones que podrían activar una revisión de la configuración de JavaScript incluyen las siguientes:

* Rotación en su equipo de marketing
* Cambios y actualizaciones en la estructura del sitio
* Migraciones del sitio
* Cambios en su dominio
* Adquisición de otras empresas y sus propiedades web
