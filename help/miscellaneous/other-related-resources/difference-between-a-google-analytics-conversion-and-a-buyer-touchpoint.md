---
unique-page-id: 18874648
description: 'Diferencia entre una conversión de Google Analytics y un punto de contacto de comprador: [!DNL Marketo Measure] - Documentación del producto'
title: Diferencia entre una conversión de Google Analytics y un punto de contacto de comprador
exl-id: d09d963c-3207-467c-852a-d1edd49511fa
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---

# Diferencia entre una conversión de Google Analytics y un punto de contacto de comprador {#difference-between-a-google-analytics-conversion-and-a-buyer-touchpoint}

Aprenda a [!DNL Google Analytics (GA)] es y cómo se diferencia de un punto de contacto del comprador.

**¿Qué son las conversiones de los Google Analytics?**

[!UICONTROL Google Analytics] las conversiones están completamente determinadas por el modo en que un especialista en marketing o un desarrollador web codifica las finalizaciones de &quot;objetivo&quot; en un sitio web en particular. Los objetivos, según Google, podrían considerarse como &quot;realizar una compra (para un sitio de comercio electrónico), completar un nivel de juego (para una aplicación de juegos móvil) o enviar un formulario de información de contacto (para un sitio de marketing o de generación de posibles clientes)&quot;. La mayoría de las veces, los especialistas en marketing ven los objetivos y las conversiones como alguien que rellena un formulario informativo.

Sin embargo, los objetivos no se pueden codificar para administrar comportamientos muy específicos. En su lugar, hay tipos de objetivos que un desarrollador web puede configurar. A continuación se muestran algunos de estos ejemplos:

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><strong>Tipo de objetivo</strong></td> 
   <td><p><strong>Descripción</strong></p></td> 
   <td><strong>Ejemplo</strong></td> 
  </tr> 
  <tr> 
   <td><p>Destino</p></td> 
   <td>Se carga una ubicación específica</td> 
   <td><em>¡Gracias por registrarse!</em> página web o pantalla de la aplicación</td> 
  </tr> 
  <tr> 
   <td>Duración</td> 
   <td>Sesiones que duran una cantidad específica de tiempo o más</td> 
   <td>10 minutos o más en un sitio de soporte</td> 
  </tr> 
  <tr> 
   <td>Páginas/pantallas por sesión</td> 
   <td>Un usuario ve un número específico de páginas o pantallas</td> 
   <td>Se han cargado 5 páginas o pantallas</td> 
  </tr> 
  <tr> 
   <td>Evento</td> 
   <td>Se activa una acción definida como Evento</td> 
   <td>Recomendación social, reproducción de vídeo y clic</td> 
  </tr> 
 </tbody> 
</table>

La mayoría de los especialistas en marketing configuran sus conversiones como &quot;Objetivos de destino&quot;, lo que significa que normalmente crean una página de agradecimiento después de un formulario para considerar que es una conversión formal.

Esto significa que Google considerará las vistas de página de agradecimiento como una conversión. Desde el punto de vista de los Google Analytics, esto supone una comprensión de que la mayoría de los especialistas en marketing están de acuerdo.

Sin embargo, los puntos de contacto del comprador actúan de forma muy diferente.

**¿En qué se diferencian los puntos de contacto del comprador?**

[!DNL Marketo Measure] JavaScript rastrea los datos de sesión y los envíos de formularios en todas las formas de un sitio en particular. No es necesario codificar los objetivos de un [!DNL Marketo Measure] punto de vista. Este proceso es automático. Para envíos de formularios, [!DNL Marketo Measure] informa de la cumplimentación de un formulario cada vez que un usuario anónimo rellena campos de información en un formulario concreto y también hace clic en el botón de envío del formulario. [!DNL Marketo Measure] no necesita una página de agradecimiento para registrar el envío del formulario.

[!DNL Marketo Measure] creará un touchpoint de formulario cuando:

* Un posible cliente o contacto asociado a esas conversiones aparece en su CRM.
* La variable [!DNL Marketo Measure] JS está presente en las páginas web que contienen el formulario.
* Un formulario se envía en una sesión de 30 minutos.

[!DNL Marketo Measure] ignorará las conversiones de destino de Google Analytics cuando:

* Un bot envía formularios en un sitio web (estos bots no suelen entrar en el CRM de un cliente).
* Un usuario envía más formularios después del primer envío. [!DNL Marketo Measure] solo inserta la primera conversión de esa sesión.
* El usuario hace clic varias veces en el envío del formulario. [!DNL Marketo Measure] solo considerará el primer envío de formulario.
* El usuario vuelve a cargar la página de agradecimiento varias veces.
* El usuario utiliza cualquier herramienta de bloqueo de anuncios.

Como puede ver, hay diferencias fundamentales entre lo que GA y [!DNL Marketo Measure] considere una conversión. Por lo tanto, es muy probable que el número de conversiones y el número de Touchpoints del formulario difieran.
