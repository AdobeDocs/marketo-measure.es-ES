---
unique-page-id: 18874722
description: 'Prácticas recomendadas para pruebas: [!DNL Marketo Measure] - Documentación del producto'
title: Prácticas recomendadas para pruebas
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 1%

---

# Prácticas recomendadas para pruebas {#best-practices-for-testing}

Debe probar todos los diferentes tipos de formularios para asegurarse de que la variable [!DNL Marketo Measure] JavaScript funciona correctamente.

## Proceso de prueba recomendado {#recommended-test-process}

1. Utilice un explorador incógnito o borre las cookies entre cada prueba de envío de formulario _y_ utilice una dirección de correo electrónico diferente cada vez.

   >[!TIP]
   >
   >Una práctica recomendada es utilizar un correo electrónico falso que contenga algo que indique que es una prueba, así como la hora del día. Por ejemplo: `testing830am@test.com`.

1. Inicie la búsqueda en un motor de búsqueda (p. ej., `google.com`) o navegue hasta un formulario directamente.

1. Envíe el formulario a su sitio web utilizando una dirección de correo electrónico única.

1. Registre la dirección URL de la página en la que envía el formulario y la dirección de correo electrónico utilizada.

1. Busque el registro creado en su CRM (posible cliente o contacto) para ese envío de formulario y verifique que se haya creado correctamente un punto de contacto.

>[!NOTE]
>
>Puede usar un [!DNL Marketo Measure] informe de existencias, como Posibles clientes con [!DNL Marketo Measure] Touchpoints o observe el diseño de página de posible cliente/contacto si elige actualizar los diseños de página con [!DNL Marketo Measure] detalles. Esto podría tardar algún tiempo en procesarse.
