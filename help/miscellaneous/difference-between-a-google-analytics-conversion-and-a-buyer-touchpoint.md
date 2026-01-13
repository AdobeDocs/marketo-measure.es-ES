---
description: Diferencia entre una conversión de Google Analytics y un punto de contacto de comprador
title: Diferencia entre una conversión de Google Analytics y un punto de contacto de comprador
exl-id: d09d963c-3207-467c-852a-d1edd49511fa
feature: Touchpoints
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 7%

---


# Diferencia entre una conversión de Google Analytics y un punto de contacto de comprador {#difference-between-a-google-analytics-conversion-and-a-buyer-touchpoint}

Descubra qué es una meta de [!DNL Google Analytics (GA)] y cómo se diferencia de una Buyer Touchpoint.

**¿Qué son las conversiones de Google Analytics?**

Las conversiones de [!UICONTROL Google Analytics] están determinadas por la forma en que un experto en marketing o un desarrollador web codifica las finalizaciones de &quot;objetivos&quot; en un sitio web en particular. Los objetivos, según Google, podrían considerarse como &quot;realizar una compra (para un sitio de comercio electrónico), completar un nivel de juego (para una aplicación de juegos móvil) o enviar un formulario de información de contacto (para un sitio de marketing o de generación de posibles clientes)&quot;. La mayoría de las veces, los especialistas en marketing ven los objetivos y las conversiones como alguien que rellena un formulario informativo.

Sin embargo, los objetivos no se pueden codificar para administrar un comportamiento específico. En su lugar, hay tipos de objetivos que un desarrollador web puede configurar. A continuación se muestran algunos de estos ejemplos:

<table>
 <colgroup>
  <col>
  <col>
  <col>
 </colgroup>
 <tbody>
  <tr>
   <td><strong>Tipo de meta</strong></td>
   <td><p><strong>Descripción</strong></p></td>
   <td><strong>Ejemplo</strong></td>
  </tr>
  <tr>
   <td><p>Destino</p></td>
   <td>Se carga una ubicación específica</td>
   <td><em>¡Gracias por registrarse!</em> página web o pantalla de aplicación</td>
  </tr>
  <tr>
   <td>Duración</td>
   <td>Sesiones que duran una cantidad de tiempo específica o más</td>
   <td>10 minutos o más en un sitio de asistencia</td>
  </tr>
  <tr>
   <td>Páginas/Screens por sesión</td>
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

La mayoría de los especialistas en marketing configuran sus conversiones como &quot;Objetivos de destino&quot;, lo que significa que generalmente crean una página de agradecimiento después de un formulario para considerar que se trata de una conversión formal.

Esto significa que Google considera las vistas de la página de agradecimiento como una conversión. Desde el punto de vista de Google Analytics, se trata de una comprensión con la que la mayoría de los especialistas en marketing están de acuerdo.

Sin embargo, los puntos de contacto del comprador actúan de forma diferente.

**¿En qué se diferencian los puntos de contacto del comprador?**

[!DNL Marketo Measure] JavaScript rastrea los datos de sesión y los envíos de formularios en todos los formularios de un sitio en particular. No es necesario codificar los objetivos desde el punto de vista de [!DNL Marketo Measure]. Este proceso es automático. Para los envíos de formularios, [!DNL Marketo Measure] informa de que se ha completado un formulario cada vez que un usuario anónimo rellena los campos de información de un formulario concreto y también hace clic en el botón de envío del formulario. [!DNL Marketo Measure] no necesita una página de agradecimiento para registrar el envío del formulario.

[!DNL Marketo Measure] crea un punto de contacto de formulario cuando:

* Un posible cliente/contacto asociado a esas conversiones aparece en su CRM.
* El JS [!DNL Marketo Measure] está presente en las páginas web que contienen el formulario.
* Se envía un formulario en una sesión de 30 minutos.

[!DNL Marketo Measure] ignora las conversiones de Google Analytics de destino cuando:

* Un bot envía formularios en un sitio web (estos bots generalmente no llegan a la CRM de un cliente).
* Un usuario envía más formularios después de su primer envío de formulario. [!DNL Marketo Measure] solo insertará la primera conversión desde esa sesión.
* El usuario hace clic en el envío del formulario varias veces. [!DNL Marketo Measure] solo considerará el primer envío de formulario.
* El usuario vuelve a cargar la página de agradecimiento varias veces.
* El usuario está utilizando cualquier herramienta de bloqueo de publicidad.

Como puede ver, existen diferencias fundamentales entre lo que GA y [!DNL Marketo Measure] consideran una conversión. Por lo tanto, es probable que el número de conversiones y el número de puntos de contacto de formulario sean diferentes.
