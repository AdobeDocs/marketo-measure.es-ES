---
description: Recomendaciones para la realización de pruebas para usuarios de Marketo Measure
title: Prácticas recomendadas para pruebas
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 17%

---

# Prácticas recomendadas para pruebas {#best-practices-for-testing}

Debe probar todos los tipos de formularios que tiene para asegurarse de que el JavaScript [!DNL Marketo Measure] funciona correctamente.

## Proceso de prueba recomendado {#recommended-test-process}

1. Use un explorador de incógnito o borre las cookies entre cada prueba de envío de formulario _y_ y use una dirección de correo electrónico diferente cada vez.

   >[!TIP]
   >
   >Una práctica recomendada es utilizar un correo electrónico falso que contenga algo que indique que es una prueba, así como la hora del día. Por ejemplo: `testing830am@test.com`.

1. Inicie la búsqueda en un motor de búsqueda (por ejemplo, `google.com`) o navegue directamente a un formulario.

1. Envíe el formulario a su sitio web utilizando una dirección de correo electrónico única.

1. Registre la dirección URL de la página en la que está enviando el formulario y la dirección de correo electrónico utilizada.

1. Busque el registro creado en su CRM (posible cliente o contacto) para dicho envío de formulario y compruebe que se creó correctamente un punto de contacto.

>[!NOTE]
>
>Puede usar un informe de existencias de [!DNL Marketo Measure], como posibles clientes con [!DNL Marketo Measure] puntos de contacto, o mirar el diseño de página de posible cliente/contacto si decide actualizar los diseños de página con [!DNL Marketo Measure] detalles. Los datos podrían tardar un poco en procesarse.
