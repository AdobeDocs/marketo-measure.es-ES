---
unique-page-id: 18874716
description: 'Metodología de asignación de atribución: [!DNL Marketo Measure] - Documentación del producto'
title: Metodología de asignación de atribuciones
exl-id: 4d54dd20-9a82-4b87-8908-ced2bd9c0f2f
feature: Attribution
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 1%

---

# Metodología de asignación de atribuciones {#attribution-mapping-methodology}

La metodología de asignación de atribución es el proceso de buscar ciertos objetos en su CRM (contactos, oportunidades, cuentas) para crear puntos de contacto de atribución en la oportunidad asociada. En otras palabras, es el [!DNL Marketo Measure] forma de comprender qué puntos de contacto se incluyen en el modelo de atribución en función de los procesos actuales de CRM.

## Asignación de ID de cuenta {#account-id-mapping}

De serie, [!DNL Marketo Measure] proporciona la asignación de ID de cuenta. Esto significa que [!DNL Marketo Measure] busca la información de marketing de la Cuenta y sus Contactos para crear puntos de contacto de atribución asociados a la oportunidad. A continuación se presenta una representación sencilla de ese proceso.

![](assets/1-1.png)

Tenga en cuenta que **no todos** Los puntos de contacto de sus contactos se insertarán en la oportunidad como puntos de contacto de atribución. La cronología de la oportunidad (su fecha de primer contacto: fecha de cierre) determinará si un punto de contacto contará o no como influyente en la oportunidad. Por lo tanto, si se produce un punto de contacto en el contacto A después de que se cierre la oportunidad Ganado/Perdido, [!DNL Marketo Measure] no insertará ese punto de contacto en la oportunidad. Este procedimiento de cronología se sigue en todas las demás asignaciones de objetos de atribución.

Ventajas: Este método de atribución es muy eficaz para la mayoría de las empresas. El equipo de marketing no necesita depender del equipo de ventas para asociar todos los contactos a una oportunidad en particular (lo que a menudo es un problema). Además, incluso si un equipo de ventas asocia funciones de contacto, es posible que se pasen por alto muchas interacciones de otros contactos con materiales de marketing. Por último, este método ayuda a las estrategias ABM que se esfuerzan por influir en la totalidad de una cuenta, en lugar de influenciadores específicos.

Desventajas: Si hay SLA de marketing y ventas sólidos que definen quién debería recibir crédito por qué, este método podría resultar problemático. Además, si los usuarios no utilizan jerarquías de cuenta para definir unidades de negocio específicas dentro de una cuenta más grande (por ejemplo: IBM), las interacciones de marketing específicas de una unidad de negocio pueden propagarse entre otras oportunidades de unidad de negocio.

## Asignación de funciones de contacto de oportunidad {#opportunity-contact-role-mapping}

Mientras que la mayoría de los clientes aprovechan la asignación de ID de cuenta, [!DNL Marketo Measure] tiene la capacidad de buscar los roles de contacto (contactos asociados a la oportunidad) dentro de una oportunidad para desglosar el proceso de atribución. Esto significa que [!DNL Marketo Measure] solo insertará interacciones de marketing asociadas a las funciones de contacto en la oportunidad como puntos de contacto de atribución del comprador. A continuación se presenta una representación de este proceso.

![](assets/2-1.png)

Profesionales: Si su equipo tiene un proceso de funciones de contacto muy bien definido, este tipo de asignación de atribución puede ser ideal para usted. Ayudará a alinear las ventas y el marketing un poco más, ya que todos entenderían perfectamente cómo se desglosa la atribución. Este proceso también es muy útil cuando las organizaciones se dirigen a varias unidades de negocio dentro de una gran empresa, así como cuando venden diferentes productos al mismo tiempo.

Inconvenientes: Sin embargo, si no hay ningún proceso de función de contacto en marcha, el marketing perderá muchos datos de marketing y el equipo terminará recibiendo mucho menos crédito por sus esfuerzos de marketing que están influyendo en las oportunidades.

## Asignación de funciones de contacto principal de oportunidad {#opportunity-primary-contact-role-mapping}

Más allá de simplemente mirar los roles de contacto en la oportunidad, [!DNL Marketo Measure] puede centrarse aún más en mirar únicamente a los contactos principales de una oportunidad. Con esta configuración en mente, [!DNL Marketo Measure] solo capturará el punto de contacto de marketing asociado a los contactos principales de una oportunidad e insertará esa información en la historia de atribución de esa oportunidad específica. Consulte la siguiente imagen.

![](assets/3.png)

Profesionales: Si su equipo solo está interesado en comprender la influencia de marketing en los contactos que se establecen como &quot;principales&quot; en la oportunidad, este tipo de asignación se adaptará mejor al equipo.

Inconvenientes: Este es sin duda el proceso de asignación menos utilizado y puede socavar considerablemente la influencia de marketing que está moviendo la aguja a través de otros contactos en una oportunidad.
