---
description: '[!DNL Salesforce] Consolidación de paquetes - [!DNL Marketo Measure] - Documentación del producto'
title: '[!DNL Salesforce] Consolidación de paquetes'
exl-id: f1bd5dcb-d021-4140-b6b9-cdb40e566c4b
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 0%

---

# [!DNL Salesforce] Consolidación de paquetes {#salesforce-package-consolidation}

Nos complace anunciar próximos cambios en los paquetes de Marketo Measure Salesforce. En un esfuerzo por mejorar la experiencia del usuario y simplificar el uso, estamos consolidando todos los paquetes existentes en un único paquete completo.

## Retirada de paquetes {#package-retirement}

Como consecuencia de esta consolidación, la versión actual de V1, V2_EXT, V2_Security y todos los paquetes de informes se retirarán después de agosto de 2023. Si ya tiene instalado el paquete V2, debe actualizarlo a la nueva versión consolidada.

## Nuevo paquete consolidado {#new-consolidated-package}

El nuevo paquete consolidado de la versión 2 incorpora todas las funciones y funcionalidades de los paquetes anteriores, lo que proporciona una experiencia de usuario mejorada. Este paquete actualizado permite un seguimiento más eficiente del rendimiento de ventas y marketing, así como una perspectiva más detallada del comportamiento de los clientes.

Se han añadido dos campos nuevos para mejorar las funciones de creación de informes:

* form_name: ahora disponible en objetos BT/BAT, este campo permite a los usuarios crear informes basados en nombres de formulario.
* user_touchpoint_id: este campo permite a los usuarios crear informes con recuentos de puntos de contacto de usuario únicos.

## Soporte y transición {#support-and-transition}

Entendemos que este cambio puede requerir ajustes y nos comprometemos a apoyarle durante todo el proceso. Nuestro [Equipo de soporte](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} está fácilmente disponible para responder a cualquier pregunta y ayudar a garantizar una transición sin problemas al nuevo paquete consolidado.

## Acciones requeridas {#retired-actions}

* Si ya tiene instalado el paquete V2, debe actualizarlo a la nueva versión consolidada.
* Si tiene informes o tableros de cualquier paquete de informes, puede volver a crearlos fácilmente sin necesidad de realizar modificaciones, ya que todos los campos utilizados existen en el paquete consolidado.
* Si tiene informes con campos en el paquete V2_EXT, puede volver a crearlos en el paquete consolidado siguiendo los pasos a continuación:
   * Todos los datos de los campos V2_EXT están disponibles en los campos Touchpoint, por lo que puede modificar los informes para recuperar datos de los campos de punto de contacto V2 correspondientes añadiendo un filtro en la posición del punto de contacto.
   * Informe de ejemplo que recupera todos los posibles clientes con contenido de publicidad que contiene texto &quot;Divulgación&quot;.
      * Consulta V2_EXT:
         * bizible2_ext__Ad_Content_FT__c contiene Alcance

![](assets/package-consolidation-1.png)

* Consulta correspondiente en el paquete consolidado:
   * bizible2__Touchpoint_Position__c contiene FT AND
   * bizible2__Ad_Content__c contiene Alcance

![](assets/salesforce-package-consolidation-2.png)

## Preguntas frecuentes {#faq}

**¿El paquete consolidado tiene conflictos con los campos de mi paquete existente?**

No es necesario desinstalar el paquete antes de instalar el paquete consolidado. No habrá conflictos en los campos, ya que estarán en un área de nombres diferente.

**¿Cómo puedo rellenar los datos de mis paquetes actuales?**

Puede presentar un ticket [con soporte](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} para rellenar y reprocesar datos BT/BAT, rellene los campos ID de Touchpoint e ID de formulario.

**¿Estarán disponibles los campos de los paquetes V1 y V2_EXT en el paquete consolidado?**

Sí. El paquete consolidado contendrá los mismos campos en la versión 1 con más desgloses por objetos y los campos V2_EXT a través de los campos Touchpoint.

**¿Pueden volver a crearse los informes que utilizan campos V2_EXT en el paquete consolidado?**

Sí. Siga los pasos de la sección [Acciones requeridas](#retired-actions) sección anterior.
