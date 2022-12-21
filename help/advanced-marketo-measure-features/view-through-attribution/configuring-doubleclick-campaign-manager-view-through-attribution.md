---
unique-page-id: 18874781
description: 'Configuración de la vista del administrador de campaña de Doubleclick mediante la atribución: [!DNL Marketo Measure] - Documentación del producto'
title: Configuración de la vista de Doubleclick Campaign Manager mediante atribución
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Configuración de la vista de Doubleclick Campaign Manager mediante atribución {#configuring-doubleclick-campaign-manager-view-through-attribution}

## Medición de la visualización mediante atribución {#measuring-view-through-attribution}

>[!NOTE]
>
>Si está utilizando la variable [!DNL Marketo Measure] y la integración de DoubleClick Campaign Manager, necesitamos un [Conexión de API](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) de este modo, podemos descargar detalles de las campañas y creativos para resolver los anuncios.

Para empezar a obtener una perspectiva más granular desde la vista hasta el seguimiento con el administrador de campaña de Doubleclick, es necesario configurar nuestro píxel de seguimiento.

Por favor [haga clic aquí](/help/advanced-marketo-measure-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md) para obtener más información sobre la variable [!DNL Marketo Measure] Atribución de visualización .

[!DNL Marketo Measure] se considera una etiqueta de rebote porque es una llamada de terceros a través de la etiqueta de publicidad de DCM. Las etiquetas de Piggyback no funcionan con etiquetas de imagen, solo con etiquetas de iframe o javascript. Según el soporte de DCM, esto no ha cambiado recientemente y siempre ha sido así. Las etiquetas estándar quedaron obsoletas el 2 de octubre de 2017, pero no afectan a la capacidad de [!DNL Marketo Measure] para realizar un seguimiento de las impresiones.

En el caso de que aproveche una jerarquía principal y secundaria en DCM, necesitaremos que nuestra etiqueta se aplique a todos los niveles para el seguimiento de impresiones.

## Cómo añadir la etiqueta de imagen {#how-to-add-the-image-tag}

Agregue la etiqueta a Doubleclick en la configuración Anunciante y querrá crear una etiqueta Evento de impresión.

1. Agregue el siguiente código como píxel de imagen 1x1.

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. Una vez añadida, confirme que los delimitadores están asignados de la siguiente manera. Debe ser automático una vez aplicada la etiqueta :

   v = %eadv! Expandir Id Del Anunciante\
   a = %eaid! Expandir Id De Publicidad\
   c = %ecid! Expandir Id Del Creativo\
   s = %esid! Expandir Id Del Sitio\
   p = %epid! Expandir Id De Colocación\
   m = %m Coincidencia de macro\
   n = %n Macro de número aleatorio

   ![](assets/1.png)

## Preguntas frecuentes {#faq}

**P: ¿Es segura la etiqueta de imagen?**

A: Sí. No es una etiqueta JavaScript, es una etiqueta de imagen.

**P: ¿Qué permisos necesita el usuario conectado?**

A: tráfico de drogas, informes, userinfo.email

**P: ¿Cuánto tiempo se puede tardar en importar los datos de gasto?**

A: Hasta 6 horas

**P: ¿Cuánto tiempo se puede tardar en importar datos de publicidad?**

A: Hasta 6 horas
