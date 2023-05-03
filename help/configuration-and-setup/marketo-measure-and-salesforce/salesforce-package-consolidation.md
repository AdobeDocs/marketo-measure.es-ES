---
description: "[!DNL Salesforce] Consolidación de paquetes - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Salesforce] Consolidación de paquetes"
source-git-commit: 279d9a18dca59de9ad99113624f4c9b2bcea0d01
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 0%

---

# [!DNL Salesforce] Consolidación de paquetes {#salesforce-package-consolidation}

Estamos encantados de anunciar los próximos cambios en los paquetes de Marketo Measure Salesforce. En un esfuerzo por mejorar la experiencia del usuario y simplificar el uso, estamos consolidando todos los paquetes existentes en un paquete único e integral.

## Retirada de paquetes {#package-retirement}

Como consecuencia de esta consolidación, los paquetes V1, V2_EXT, V2_Security y Reporting actuales se retirarán después de agosto de 2023. Si ya tiene instalado el paquete V2, debe actualizarlo a la nueva versión consolidada.

## Nuevo paquete consolidado {#new-consolidated-package}

El nuevo paquete V2 consolidado incorpora todas las funciones y funcionalidades de los paquetes anteriores, lo que proporciona una experiencia de usuario mejorada. Este paquete actualizado permite un seguimiento de marketing y del rendimiento de ventas más eficaz y permite obtener perspectivas más detalladas sobre el comportamiento de los clientes.

## Asistencia y transición {#support-and-transition}

Entendemos que este cambio puede requerir ajustes, y nos comprometemos a apoyarle durante todo el proceso. Nuestra [Equipo de asistencia](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} está fácilmente disponible para responder a cualquier pregunta y ayudar a garantizar una transición sin problemas al nuevo paquete consolidado.

## Acciones necesarias {#retired-actions}

* Si ya tiene instalado el paquete V2, debe actualizarlo a la nueva versión consolidada.
* Si tiene informes o tableros de cualquier paquete de informes, puede recrearlos fácilmente sin necesidad de realizar ninguna modificación, ya que todos los campos utilizados existen en el paquete consolidado.
* Si tiene informes utilizando campos en el paquete V2_EXT , puede volver a crearlos en el paquete consolidado mediante los pasos siguientes:
   * Todos los datos de los campos V2_EXT están disponibles en los campos de Touchpoint, por lo que puede modificar los informes para recuperar datos de los campos de touchpoint V2 correspondientes añadiendo un filtro en la posición de touchpoint.
   * Informe de ejemplo que obtiene todos los posibles clientes con el contenido de anuncio FT que contiene el texto &quot;Extensión&quot;.
      * Consulta V2_EXT:
         * bizible2_ext_Ad_Content_FT_c contiene Extensión

![](assets/salesforce-package-consolidation-1.png)

* Consulta correspondiente en el paquete consolidado:
   * bizible2__Touchpoint_Position__c contiene FT Y
   * bizible2__Ad_Content__c contiene Extensión

![](assets/salesforce-package-consolidation-2.png)

## Preguntas frecuentes {#faq}

**¿Tendrá el paquete consolidado conflictos con los campos de mi paquete existente?**

No es necesario desinstalar el paquete antes de instalar el paquete consolidado. No habrá conflictos en los campos, ya que estarán en un área de nombres diferente.

**¿Cómo puedo rellenar los datos de mis paquetes actuales?**

Puede presentar un ticket [con asistencia técnica](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} para rellenar y reprocesar datos BT/BAT para rellenar los campos ID de punto de contacto e ID de formulario .

**¿Los campos de los paquetes V1 y V2_EXT estarán disponibles en el paquete consolidado?**

Sí. El paquete consolidado contendrá los mismos campos en V1 con desgloses adicionales por objetos y campos V2_EXT a través de campos Touchpoint.

**¿Se pueden volver a crear en el paquete consolidado los informes que utilizan campos V2_EXT?**

Sí. Siga los pasos de la sección [Acciones necesarias](#retired-actions) sección anterior.
