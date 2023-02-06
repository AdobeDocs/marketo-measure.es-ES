---
unique-page-id: 18874716
description: Metodología de asignación de atribuciones - [!DNL Marketo Measure] - Documentación del producto
title: Metodología de asignación de atribuciones
exl-id: 4d54dd20-9a82-4b87-8908-ced2bd9c0f2f
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# Metodología de asignación de atribuciones {#attribution-mapping-methodology}

La metodología de asignación de atribuciones es el proceso de buscar ciertos objetos en su CRM (Contactos, Oportunidades, Cuentas) para crear puntos de contacto de atribución en la oportunidad asociada. En otras palabras, es el [!DNL Marketo Measure] forma de comprender qué puntos de contacto incluir en el modelo de atribución en función de los procesos actuales de CRM.

## Asignación de ID de cuenta {#account-id-mapping}

Fuera de la caja, [!DNL Marketo Measure] proporciona asignación de ID de cuenta. Esto significa que [!DNL Marketo Measure] consulte la información de marketing Cuenta y Contactos para crear Touchpoints de atribución asociados a la oportunidad. A continuación se muestra una simple representación de ese proceso.

![](assets/1-1.png)

Tenga en cuenta que: **not all** los puntos de contacto de sus contactos se insertarán en la oportunidad como puntos de contacto de atribución. La cronología de la oportunidad (su fecha de primer toque - fecha de cierre) determinará si un punto de contacto se contará o no como un influyente en la oportunidad. Por lo tanto, si se produjo un punto de contacto en el Contacto A después de que se cerrara la oportunidad, Won/Lost, [!DNL Marketo Measure] no llevará ese punto de contacto a la oportunidad. Este procedimiento de cronología se sigue en todas las demás asignaciones de objetos de atribución.

Ventajas: Este método de atribución es muy eficaz para la mayoría de las empresas. El equipo de marketing no necesita confiar en que el equipo de ventas asocie todos los contactos a una oportunidad determinada (lo que a menudo supone un problema). Además, incluso si un equipo de ventas asocia roles de contacto, es posible que se pierdan muchas otras interacciones de contacto con materiales de marketing. Por último, este método ayuda a las estrategias ABM que se esfuerzan por influir en la totalidad de una cuenta, en lugar de en los influyentes específicos.

Inconvenientes: Si hay acuerdos de nivel de servicio de marketing y ventas sólidos que definen quién debe recibir crédito por qué, este método podría resultar problemático. Además, si los usuarios no utilizan jerarquías de cuenta para definir unidades de negocio específicas dentro de una cuenta más grande (por ejemplo: IBM), las interacciones de marketing específicas de una unidad de negocio pueden distribuirse entre otras oportunidades de unidades de negocio.

## Asignación de funciones de contacto de oportunidad {#opportunity-contact-role-mapping}

Mientras que la mayoría de los clientes utilizan la asignación de ID de cuenta , [!DNL Marketo Measure] tiene la capacidad de buscar las funciones de contacto (contactos asociados a la oportunidad) dentro de una oportunidad para desglosar el proceso de atribución. Esto significa que [!DNL Marketo Measure] solo insertará interacciones de marketing asociadas a las funciones de contacto en los puntos de contacto de atribución de comprador como oportunidad. A continuación se muestra una representación de este proceso.

![](assets/2-1.png)

Ventajas: Si su equipo tiene un proceso de funciones de contacto muy bien definido, este tipo de asignación de atribución puede ser ideal para usted. Ayudará a alinear las ventas y el marketing un poco más, ya que todos comprenderían plenamente cómo se desglosa la atribución. Este proceso también es muy útil cuando las organizaciones están dirigiéndose a varias unidades de negocio dentro de una gran empresa, así como cuando venden diferentes productos al mismo tiempo.

Inconvenientes: Sin embargo, si no hay un proceso de rol de contacto, el marketing perderá muchos datos de marketing y el equipo terminará recibiendo mucho menos crédito por sus esfuerzos de marketing que están influyendo en las oportunidades.

## Asignación de funciones de contacto principal de oportunidad {#opportunity-primary-contact-role-mapping}

Más allá de simplemente mirar los roles de contacto en la oportunidad, [!DNL Marketo Measure] puede centrarse aún más para ver solo los Contactos principales en una oportunidad. Con esta configuración en mente, [!DNL Marketo Measure] solo obtendrá el punto de contacto de marketing asociado a los contactos principales en una oportunidad e insertará esa información en el historial de atribución de esa oportunidad específica. Consulte la siguiente imagen.

![](assets/3.png)

Ventajas: Si su equipo solo está interesado en comprender la influencia de marketing en los contactos que se establecen como &quot;principales&quot; en la oportunidad, este tipo de asignación se adaptará mejor al equipo.

Inconvenientes: Este es sin duda el proceso de mapeo menos utilizado y puede minar la influencia de marketing que está moviendo la aguja a través de otros contactos en una oportunidad.
