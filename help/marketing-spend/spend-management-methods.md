---
description: Métodos de administración de gastos - [!DNL Marketo Measure]
title: Métodos de administración de gastos
exl-id: 36478d8d-986c-4d4f-8854-3287d6c57a9d
feature: Spend Management
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 1%

---


# Métodos de administración de gastos {#spend-management-methods}

Gastar datos es clave para el éxito de la generación de informes de retorno de la inversión con [!DNL Marketo Measure]. Para disponer de informes de ROI precisos y completos en todos tus canales y subcanales, debes asegurarte de que se estén extrayendo los datos de gasto correspondientes en [!DNL Marketo Measure].

Existen tres maneras de obtener los datos de gasto en [!DNL Marketo Measure]. Cada método está diseñado para extraer datos gastados de entradas de datos concretas.

**1 cuentas conectadas a la API**

Cualquier cuenta de publicidad a la que se haya conectado [!DNL Marketo Measure] mediante una API cuyo gasto se haya recuperado automáticamente en [!DNL Marketo Measure] para la creación de informes de retorno de la inversión. Para comprobar qué cuentas ha conectado y, por lo tanto, retirar el gasto, vaya a su aplicación [!DNL Marketo Measure] y seleccione la pestaña [!UICONTROL Conexiones] en la sección [!UICONTROL Integraciones]. Para obtener más información sobre cómo configurar las conexiones de API, revisa [Plataformas de publicidad integradas](/help/api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms).

**2 Sincronización de costos de CRM Campaign**

Cada cuenta de [!DNL Marketo Measure] tiene acceso a una característica llamada [Sincronizar costos de campaña de CRM](/help/marketing-spend/crm-campaign-costs.md#availability). De forma predeterminada, este bit de característica está establecido en &quot;No&quot;, pero se puede activar en cualquier momento.

![Página de configuración de conexiones que muestra la opción de sincronización de costos de CRM Campaign](assets/spend-management-methods-1.png)

Cuando está habilitada, esta función extrae automáticamente el gasto de cualquier campaña o programa de CRM que cumpla los siguientes criterios:

i. [!DNL Marketo Measure] busca primero si la campaña o el programa está creando puntos de contacto, ya sea a partir de una [regla de sincronización de campañas](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md) que se haya creado, o a partir de una [regla de sincronización de programas](/help/marketo-measure-and-marketo/marketo-engage-programs-integration.md) que se haya creado, o bien si el valor [Habilitar puntos de contacto del comprador](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints) es &quot;Incluir todos los miembros de la campaña&quot; o &quot;Incluir miembros de la campaña que hayan respondido&quot;.&quot;

ii. Se debe completar una Fecha de inicio en la campaña o programa

iii. Se debe completar una fecha de finalización en la campaña o programa

iv. Se debe especificar el coste real (para campañas en SFDC) o el coste del período (para programas en Marketo).

**3 Carga manual de costos**

Este método le permite [cargar manualmente los datos de gasto](/help/marketing-spend/marketing-channel-costs.md#uploading-marketing-costs) de los canales y subcanales que no están cubiertos por las cuentas conectadas a la API o por la sincronización de costos de la campaña de CRM. Si navega a la sección Gasto en marketing de la configuración de [!DNL Marketo Measure], podrá cargar los datos del gasto a través de un archivo CSV para cualquiera de sus canales.

Los clientes pueden usar una combinación de estos tres métodos para administrar su gasto, según la configuración específica de [!DNL Marketo Measure]. Dado que existen tres métodos para importar el gasto en [!DNL Marketo Measure], le recomendamos encarecidamente que utilice su panel Gasto en marketing ubicado en Discover para obtener una vista completa de todos los datos de gasto. Este tablero es el único lugar en el que podrá ver todos sus canales y su gasto asociado. El panel Gasto en marketing puede ayudarle a identificar rápidamente dónde pueden existir lagunas en los datos de gasto y cómo puede mejorar la creación de informes de ROI.
