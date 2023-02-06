---
unique-page-id: 18874708
description: Atribución de actividades de Salesforce [!DNL Marketo Measure] - Documentación del producto
title: Atribución de actividades de Salesforce
exl-id: 1dc6f15b-2a45-4ed3-9fa3-5267366d1f45
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 1%

---

# Atribución de actividades de Salesforce {#salesforce-activities-attribution}

La variable [!DNL Marketo Measure] La integración de actividades de Salesforce introducirá registros de tarea y evento específicos en el modelo de atribución. Empiece a rastrear cosas como correos electrónicos de ventas o llamadas telefónicas de ventas que no recibían el crédito debido. Para configurar la regla de actividades, debe ir a [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. Desde allí, vaya a la **[!UICONTROL Configuración]** y haga clic en **[!UICONTROL Actividades]** pestaña .

¡Estás a punto de hacer que tu equipo de ventas sea muy feliz! Déjenos guiarle por un tutorial rápido.

![](assets/1.png)

Para empezar, estamos presentando un nuevo concepto llamado [!DNL Marketo Measure] Campaña. Para cada regla que defina, agrupará los registros en una [!DNL Marketo Measure] Campaña a la que puede asignar un nombre. Agregue varias campañas según sea necesario. Imagine la medición de la eficacia de una campaña de ventas salientes junto a una campaña de medios pagados.

Va a usar esto [!DNL Marketo Measure] Nombre de campaña para indicarnos a qué canal se debe asignar. Si todavía está pensando en las ventas salientes, tal vez todas las campañas de ventas salientes deberían sentarse en un canal BDR.

Familiarícese con esta jerarquía:

* Canal
   * Subcanal
      * Campaña
      * Campaña
   * Subcanal
      * Campaña

>[!TIP]
>
>Si desea configurar una campaña única para cada representante de ventas, por ejemplo, utilice nuestros parámetros de reemplazo dinámico para rellenar la variable [!DNL Marketo Measure] Nombre de campaña. En el mismo ejemplo, puede introducir `"Outbound Sales - {AssignedTo}"` y lo transformaremos en algo como `"Outbound Sales - Jill"` o `"Outbound Sales - Jack."` ¡No tienes ni idea de cuánto tiempo te salvamos!

![](assets/2.png)

Una vez que [!DNL Marketo Measure] Nombre de campaña está establecido, es hora de configurar las reglas de actividad.

Las reglas actúan como un filtro para decirnos qué registros son elegibles para la atribución. Imagine que está creando un informe en su CRM utilizando una lógica similar para generar ese informe. Tiene la flexibilidad de usar una combinación de instrucciones y/o y varios operadores como coincide con cualquiera, contiene, comienza con, termina con, es igual a, etc. Defina las instrucciones &quot;y&quot; dentro de una regla en caja o de las instrucciones de capa &quot;o&quot; fuera del cuadro.

![](assets/3.png)

>[!NOTE]
>
>Los campos de fórmula no se pueden usar dentro de las reglas y no aparecerán en la lista de selección. Dado que las fórmulas calculan en segundo plano y no modifican un registro, [!DNL Marketo Measure] no puede detectar si un registro se ajusta a una regla o no.
>
>Asegúrese de utilizar valores correctos para campos de ID como CrmEvent.CreatedById. [!DNL Salesforce IDs] tienen 18 caracteres de longitud (por ejemplo, 0054H000007WmrfQAC).

Por último, vamos a elegir uno de sus campos de fecha y hora para usar como Fecha de punto de contacto del comprador. Se pueden seleccionar los campos estándar y personalizados.

>[!TIP]
>
>Con la instalación del paquete, [!DNL Marketo Measure] incluye un campo Fecha de punto de contacto del comprador personalizado en el registro de actividad. Si desea utilizar una fecha dinámica, como la fecha en la que cambia el estado, es posible utilizar un flujo de trabajo CRM para establecer la &quot;Fecha del punto de contacto del comprador&quot; y, a continuación, seleccione aquí en este paso la Fecha del punto de contacto del comprador.

![](assets/4.png)

No olvide establecer reglas diferentes para Tareas o Eventos. Tendrá que saber qué objeto utiliza su equipo de ventas para registrar sus actividades.

![](assets/5.png)

Probablemente quiera colocar estos nuevos puntos de contacto en su lugar apropiado [Canal de marketing](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Channels.Online%20Channels){target="_blank"}. Puede hacerlo definiendo el canal con la nueva asignación de campaña que acaba de crear. Tal vez cree una nueva fila para el canal BDR donde la campaña comience por saliente.

>[!TIP]
>
>Al agregar una definición de canal, utilice valores comodín para los operadores de estado de una forma más sencilla como:
>
>comienza con ( saliente&#42; )
>
>contiene ( &#42;Saliente&#42; )
>
>termina con ( &#42;Saliente )
>
>Ninguna comodín significa básicamente &quot;es igual a&quot;, así que asegúrese de usarlas según sea necesario.

| **Operador** | **Caso de uso** |
|---|---|
| Is Equal To | Valor único: coincidencia exacta |
| Contiene | Valor único: contiene valor |
| Coincide con cualquier | Varios valores: Coincidencia exacta |
| Coincide con Cualquiera (Contiene) | Varios valores - &#42;value&#42;, &#42;valor, &#42;value&#42; |

![](assets/6.png)

Y por último, pero no menos importante, tienes la opción de introducir los costos de tus nuevos canales. Nuestra [Carga de gasto de marketing](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Reporting.Marketing%20Spend){target="_blank"} le permite introducir sus gastos a nivel de canal, subcanal o campaña. Con el nuevo [!DNL Marketo Measure] Campañas, puede agregar esos costos relacionados por mes y luego ver el ROI de cada campaña.

![](assets/7.png)

>[!MORELIKETHIS]
>
>[Preguntas frecuentes sobre la atribución de actividades](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)
