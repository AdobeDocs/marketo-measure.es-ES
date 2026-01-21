---
description: Consolidación de paquetes de [!DNL Salesforce] - [!DNL Marketo Measure]
title: Consolidación de paquetes de [!DNL Salesforce]
exl-id: ae559f5f-91bf-4504-9d5a-af47f95ca01f
feature: Salesforce
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 6%

---

# Consolidación de paquetes de [!DNL Salesforce] {#salesforce-package-consolidation}

Para mejorar la experiencia del usuario y simplificar el uso, los paquetes existentes se están compilando en un paquete único y completo.

## Retirada de paquetes {#package-retirement}

Como consecuencia de esta consolidación, la versión actual de V1, V2_EXT, V2_Security y todos los paquetes de informes se retirarán después de agosto de 2023. Si ya tiene instalado el paquete V2, debe actualizarlo a la nueva versión consolidada.

## Nuevo paquete consolidado {#new-consolidated-package}

El nuevo paquete consolidado de la versión 2 incorpora todas las funciones y funcionalidades de los paquetes anteriores, lo que proporciona una experiencia de usuario mejorada. Este paquete actualizado permite un seguimiento más eficiente del rendimiento de ventas y marketing, así como una perspectiva más detallada del comportamiento de los clientes.

Existen dos nuevos campos para mejorar las capacidades de creación de informes:

* form_name: ahora disponible en objetos BT/BAT, este campo permite a los usuarios crear informes basados en nombres de formulario.
* user_touchpoint_id: este campo permite a los usuarios crear informes con recuentos de puntos de contacto de usuario únicos (`bizible2__User_Touchpoint_V2__c` en Salesforce).

## Soporte y transición {#support-and-transition}

El [equipo de atención al cliente](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} está disponible para responder cualquier pregunta y ayudar a garantizar una transición sin problemas al nuevo paquete consolidado.

## Acciones necesarias {#retired-actions}

* Si ya tiene instalado el paquete V2, debe actualizarlo a la nueva versión consolidada.
* Si tiene informes o tableros de cualquier paquete de informes, puede volver a crearlos fácilmente sin necesidad de realizar modificaciones, ya que todos los campos existen en el paquete consolidado.
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

**¿El paquete consolidado tendrá conflictos con los campos de mi paquete existente?**

No es necesario desinstalar el paquete antes de instalar el paquete consolidado. No habrá conflictos en los campos porque están en un área de nombres diferente.

**¿Cómo puedo rellenar los datos de mis paquetes actuales?**

Puede presentar un ticket [con soporte](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} para rellenar y reprocesar los datos de BT/BAT a fin de rellenar los campos ID de Touchpoint e ID de formulario.

**¿Estarán disponibles los campos de los paquetes V1 y V2_EXT en el paquete consolidado?**

Sí. El paquete consolidado contiene los mismos campos en la versión 1, con más desgloses por objetos y los campos V2_EXT a través de los campos Touchpoint.

**¿Pueden volver a crearse los informes que utilizan campos V2_EXT en el paquete consolidado?**

Sí. Siga los pasos de la sección [Acciones requeridas](#retired-actions).
