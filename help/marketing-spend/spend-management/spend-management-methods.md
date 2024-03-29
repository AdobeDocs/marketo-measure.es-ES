---
description: Métodos de administración de gastos - [!DNL Marketo Measure]
title: Métodos de administración de gastos
exl-id: 36478d8d-986c-4d4f-8854-3287d6c57a9d
feature: Spend Management
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 1%

---

# Métodos de administración de gastos {#spend-management-methods}

Los datos de gasto son clave para el éxito de la creación de informes de ROI con [!DNL Marketo Measure]. Para disponer de informes de ROI precisos y completos en todos sus canales y subcanales, debe asegurarse de que dispone de los datos de gasto correspondientes que se incorporan a [!DNL Marketo Measure].

Existen tres formas de introducir los datos de gasto en [!DNL Marketo Measure]. Cada método está diseñado para extraer datos gastados de entradas de datos concretas.

**1 cuenta conectada de API**

Cualquier cuenta de publicidad a la que se haya conectado [!DNL Marketo Measure] a través de una API tiene su gasto automáticamente en [!DNL Marketo Measure] para informes de ROI. Para comprobar qué cuentas ha conectado y, por lo tanto, retirar el gasto, vaya a su [!DNL Marketo Measure] Aplicación y seleccione [!UICONTROL Conexiones] debajo de la pestaña [!UICONTROL Integraciones] sección. Para obtener más información sobre la configuración de las conexiones de API, consulte [Plataformas de publicidad integradas](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms).

**2 Sincronización de costes de CRM Campaign**

Cada [!DNL Marketo Measure] tiene acceso a una función llamada [Sincronizar costes de campaña de CRM](/help/marketing-spend/spend-management/crm-campaign-costs.md#availability). De forma predeterminada, este bit de característica está establecido en &quot;No&quot;, pero se puede activar en cualquier momento.

![](assets/spend-management-methods-1.png)

Cuando está habilitada, esta función extrae automáticamente el gasto de cualquier campaña o programa de CRM que cumpla los siguientes criterios:

i. [!DNL Marketo Measure] busca primero si la campaña o el programa está creando puntos de contacto, ya sea a partir de una [Regla de sincronización de Campaign](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md) que se ha creado o una coincidencia [Regla de sincronización de programas](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md) que se ha creado, o el [Activar valor de Touchpoints del comprador](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints) es &quot;Incluir todos los miembros de la campaña&quot; o &quot;Incluir miembros de la campaña &quot;Respondidos&quot;&quot;.&quot;

ii. Se debe completar una Fecha de inicio en la campaña o programa

iii. Se debe completar una fecha de finalización en la campaña o programa

iv. Se debe especificar el coste real (para campañas en SFDC) o el coste del período (para programas en Marketo).

**3 Carga manual de costes**

Este método le permite [carga manual de datos de gasto](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs) para los canales y subcanales que no están cubiertos por las cuentas conectadas a la API o la sincronización de costes de la campaña de CRM. Si navega hasta la sección Gasto en marketing en su [!DNL Marketo Measure] Con esta configuración, puede cargar los datos de gasto a través de un archivo CSV para cualquiera de sus canales.

Los clientes pueden utilizar una combinación de estos tres métodos para administrar su gasto, según la configuración específica del [!DNL Marketo Measure]. Porque existen tres métodos para importar el gasto en [!DNL Marketo Measure], le recomendamos encarecidamente que utilice su panel Gasto en marketing ubicado en Discover para obtener una vista completa de todos los datos de gasto. Este tablero es el único lugar en el que podrá ver todos sus canales y su gasto asociado. El panel Gasto en marketing puede ayudarle a identificar rápidamente dónde pueden existir lagunas en los datos de gasto y cómo puede mejorar la creación de informes de ROI.
