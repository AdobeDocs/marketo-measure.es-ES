---
description: ¿Qué es Adobe Marketo Measure?
title: ¿Qué es Adobe Marketo Measure?
hide: true
hidefromtoc: true
source-git-commit: 7c3f586e308ba885d10f3f9b8925af93277ad2e0
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 0%

---

# ¿Qué es Adobe Marketo Measure? {#what-is-adobe-marketo-measure}

Adobe Marketo Measure (anteriormente conocido como Bizible) es una plataforma de atribución multitáctil líder.

Consolida datos de diferentes fuentes de datos (CRM, automatización de marketing, sitio web, etc.). Con esos datos en una ubicación, crea una serie temporal de eventos (los puntos de contacto mencionados) para cada persona, identificados por su dirección de correo electrónico única.

Estos puntos de contacto se relacionan con oportunidades a través de metodologías basadas en cuentas o en roles de contactos de oportunidades, de modo que podemos atribuir oportunidades de nuevo a los diferentes puntos de contacto que jugaron un papel en el recorrido de cada oportunidad.

Mediante varios modelos de atribución basados en reglas y en posiciones (que analizaremos mucho más adelante), se asigna un peso a cada punto de contacto relacionado con una oportunidad y, a continuación, se asigna un valor en dólares a cada punto de contacto.

Cada punto de contacto se clasifica como canal, subcanal, campaña y otros segmentos definidos, lo que le permite averiguar qué actividades de marketing están más correlacionadas con oportunidades y ganancias.

Hablemos más acerca de cómo se hace esto
Cómo funciona Marketo Measure
Marketo Measure se integra con muchas de las herramientas de su pila tecnológica. También se integra directamente con las plataformas de publicidad enumeradas a continuación.

●    Google Ads
●    Bing Ads
●    Facebook/Meta
●    LinkedIn

Estas integraciones ayudan a resolver el tráfico de campañas de medios pagados a la campaña de publicidad exacta desde estas plataformas, cuando se activa el etiquetado automático.

Estas integraciones también incorporan automáticamente toda la campaña de publicidad y el gasto en publicidad de estas plataformas, directamente en la plataforma de Marketo Measure.

Nota: Estas integraciones no pueden traer puntos de contacto dentro de los jardines amurallados de medios de pago, con la excepción de la integración del formulario LinkedIn Lead Gen. Esto significa que no obtendrá puntos de contacto para cosas como comentarios, difusiones y &quot;me gusta&quot;... o cualquier otra interacción que tenga lugar únicamente dentro de estas plataformas.
Marketo Measure también tiene un javascript que se coloca en el sitio web y que crea puntos de contacto a partir de interacciones web. A continuación, estos puntos de contacto se clasifican en canales y subcanales en función de reglas que utilizan parámetros de UTM, información de campaña, páginas de aterrizaje o direcciones URL de referencia. Más información sobre esta funcionalidad más adelante.

También se integra con su CRM para incorporar oportunidades, cuentas, contactos, posibles clientes, funciones de contacto de oportunidades, campañas, miembros de campañas y actividades (tareas y eventos). Esta integración le permite configurar reglas que creen puntos de contacto a partir de la pertenencia a Campaign, así como actividades registradas contra una persona (llamadas telefónicas, correos electrónicos, reuniones, etc.). De nuevo, más información sobre esta configuración más adelante.

Marketo Measure también se puede integrar directamente con Marketo Engage. Esta integración le permite crear reglas que creen puntos de contacto a partir de la pertenencia al programa y el registro de actividad de Marketo. Vamos a profundizar en esta funcionalidad también.

Con todos esos datos, ahora está creando puntos de contacto a partir de una plétora de diferentes fuentes de datos. A estos puntos de contacto se les asigna un canal y, en algunos casos, un subcanal. Esto categoriza los puntos de contacto en función de su origen.

Los puntos de contacto también se asignan a una posición. Esta posición se basa en dónde se encuentra el punto de contacto en el proceso de compra y el recorrido. Existen cuatro posiciones estándar y tiene la capacidad de crear posiciones personalizadas. Las posiciones estándar son las siguientes...

●    Primer contacto (FT): el primer punto de contacto (puede ser anónimo)
●    Creación de posibles clientes (LC): el primer punto de contacto en el que capturamos una dirección de correo electrónico
●    Creación de Oportunidades (OC): El último contacto antes de la creación de una Oportunidad
●    Cerrado: el último contacto antes del cierre (cerrado, ganado o cerrado, perdido) de una oportunidad

A continuación, las posiciones dictan el peso en función de los diferentes modelos de atribución.

Las oportunidades, entonces, tienen su valor dividido entre todos los puntos de contacto que los influenciaron, como los pedazos de pastel, para dar a cada punto de contacto un valor.

Por ejemplo, si un punto de contacto tiene una ponderación del 30 % y está relacionado con una oportunidad con un valor de 10 000 $, ese punto de contacto se valora en 3000 $.
