---
description: '[!DNL Marketo Measure] integraciones con Adobe Analytics - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] integraciones con  [!DNL Adobe Analytics]'
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
feature: Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 1%

---


# Integraciones de [!DNL Marketo Measure] con Adobe Analytics {#marketo-measure-integrations-with-adobe-analytics}

La integración de Atributos del cliente B2B permite a los usuarios de [!DNL Marketo Measure] y Adobe Analytics enriquecer sus perfiles de usuario de [!DNL Adobe Analytics] con metadatos valiosos derivados del motor de atribución de [!DNL Marketo Measure] y a través de su capacidad de sincronización con CRM ([!DNL Microsoft Dynamics] y [!DNL Salesforce]). Está disponible de forma gratuita para todos los clientes que usen [!DNL Adobe Analytics] y [!DNL Marketo Measure].

>[!PREREQUISITES]
>Debe tener suscripciones activas a [!DNL Marketo Measure] y [!DNL Adobe Analytics].

## Configuración de la integración {#configuring-the-integration}

1. Cree un nuevo Source de datos de atributos del cliente en la consola de Experience Cloud. Encontrará instrucciones detalladas [aquí](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html?lang=es).

   Tome nota de la siguiente información, necesaria en los pasos posteriores:

   * El ID de alias, que puede ser cualquier valor que desee que sea. Recomendamos &quot;marketomeasure_id&quot;

   * El nombre de host y las credenciales del servidor FTP (nombre de usuario y contraseña)

1. Una vez creado el Source de datos de atributos del cliente, continúe con el proceso de configuración navegando a la pantalla **[!UICONTROL Integraciones]** > **[!UICONTROL Conexiones]** en el menú de administración de [!DNL Marketo Measure].

1. Haga clic en el botón **[!UICONTROL Configurar nueva conexión de atributos del cliente]** y siga las instrucciones para configurar la integración de atributos del cliente. La interfaz de usuario le solicita la información de ID de alias y conexión FTP que adquirió al crear el Source de atributos del cliente en la consola de servicios principales. Seleccione el conjunto de atributos de cuenta que desee sincronizar con su cuenta de [!DNL Adobe Analytics].

   Introduzca su ID de organización de Adobe IMS. Este ID se muestra en la esquina inferior derecha de su Admin Console de Adobe Experience Cloud. Para obtener más ayuda para encontrar este ID, consulte con el equipo de cuenta de Adobe (su administrador de cuentas).

1. Cuando haya terminado de crear la conexión en su cuenta de [!DNL Marketo Measure], debe volver a la consola de Experience Cloud para [validar el esquema](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/validate-schema.html?lang=en). No es necesario que se preocupe por la carga del archivo FTP, [!DNL Marketo Measure] ha automatizado esa parte por usted. Vaya a la pantalla de esquema &quot;Ver/Editar&quot; del Source de atributos del cliente que creó en el paso 1 y especifique a Adobe cuáles son los tipos de datos para cada uno de los atributos que [!DNL Marketo Measure] ha cargado en su nombre. También puede crear nuevos nombres descriptivos para mostrar para los atributos cargados, si lo desea.

   Si seleccionó sincronizar atributos de su objeto de cuenta de CRM, es muy recomendable que elija nuevos nombres para mostrar para ellos, ya que [!DNL Marketo Measure] solo rellena los nombres de nivel de API para estos atributos, que generalmente no son compatibles con la creación de informes.

1. El último paso es configurar Suscripciones de atributos para las aplicaciones de Experience Cloud en las que desea utilizar los atributos. Puede configurar suscripciones para [!DNL Adobe Analytics] o [!DNL Adobe Target].  Encontrará más información sobre cómo hacerlo [aquí](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/subscription.html).

## Descripciones de atributos {#attribute-descriptions}

Al crear una conexión de atributos del cliente B2B, [!DNL Marketo Measure] crea automáticamente un conjunto estándar de atributos del cliente B2B. Estos atributos se describen en la tabla siguiente.

Además de los que se enumeran a continuación, también puede cargar cualquier atributo adjunto al objeto de cuenta en su CRM. Si hay más de una cuenta vinculada al usuario determinado, [!DNL Marketo Measure] rellena todos los valores de atributo de cuenta coincidentes en una lista delimitada por punto y coma.

<table>
 <colgroup>
  <col>
  <col>
 </colgroup>
 <tbody>
  <tr>
   <td><b>Nombre del atributo</b></td>
   <td><b>Descripción</b></td>
  </tr>
  <tr>
   <td>Account.Name</td>
   <td>Los nombres de cuenta asociados con el visitante web determinado. Si hay más de una cuenta vinculada al usuario determinado, [!DNL Marketo Measure] rellena todos los nombres de cuenta coincidentes en una lista delimitada por punto y coma.<br/>
   <strong>Nota:</strong> account.name es el nombre de nivel de API de Salesforce para el atributo name del objeto de cuenta. Puede elegir un nombre para mostrar mejor (por ejemplo, "Empresa") para este atributo durante el paso Validación de esquema de la configuración de integración (paso 4).</td>
  </tr>
  <tr>
   <td>Ingresos atribuidos: ‹MODELO›</td>
   <td>Los ingresos atribuidos a este cliente en virtud de su asociación con oportunidades ganadas cerradas en su CRM, calculados por el motor de atribución [!DNL Marketo Measure].<br/>
   Hay uno de estos atributos para cada modelo de atribución que permiten sus suscripciones de [!DNL Marketo Measure] (por ejemplo, "Ingresos atribuidos - Ruta completa").</td>
  </tr>
  <tr>
   <td>Fase más profunda de Funnel</td>
   <td>La etapa de funnel más profunda de cualquier oportunidad abierta asociada con el usuario determinado.</td>
  </tr>
  <tr>
   <td>Abrir oportunidades</td>
   <td>Una lista delimitada por punto y coma de los ID de oportunidad a los que está vinculado el usuario según sus datos de CRM.</td>
  </tr>
 </tbody>
</table>

**Una nota sobre los límites de atributos**

Los atributos que surgieron a través de este recuento de integración se comparan con los límites de atributos contractuales en [!DNL Adobe Analytics] y [!DNL Adobe Target]. Solo los atributos que aparecen a través de una suscripción de atributo (paso 5 en [Configuración de la integración](#configuring-the-integration)) se contabilizan en el límite de la aplicación suscrita.

## Preguntas frecuentes {#faqs}

**¿Cómo cambio el conjunto de atributos que deseo compartir mediante esta integración?**

Para que un atributo compartido por [!DNL Marketo Measure] a su organización de Adobe IMS a través de esta integración sea visible y se utilice en [!DNL Adobe Analytics], debe mostrarse a través de una suscripción de atributo configurada en la consola de servicios principales. Por lo tanto, si desea quitar un atributo para que ya no aparezca en [!DNL Adobe Analytics], puede hacerlo simplemente eliminando la suscripción al atributo.

También puede eliminar la conexión de atributo del cliente B2B en [!DNL Marketo Measure] y volver a crearla con el atributo que ya no desea compartir excluido de la configuración de conexión. Del mismo modo, para agregar atributos a la integración, debe eliminar la conexión existente y crear una nueva con los atributos deseados agregados a la configuración.

Teniendo en cuenta lo anterior, es muy recomendable que al configurar la conexión de atributos por primera vez, sea lo más inclusivo posible al seleccionar atributos.

**¿Cuáles son algunos casos de uso de ejemplo para esta integración?**

1. Métricas de tráfico basadas en cuentas: con el atributo de nombre de cuenta, puede crear segmentos de una o más cuentas de destino en Adobe Analytics y analizar las métricas de tráfico del sitio únicamente para el subconjunto de tráfico procedente de cuentas de destino.
1. Content Analytics: utilice la métrica de ingresos para analizar qué contenido del sitio resulta más atractivo para los clientes que, en última instancia, compran su producto o servicio, o para aquellos que llegan a una fase específica de interés de funnel.
1. Asistencia técnica en vivo: Equipe a su equipo de ventas con insight procesable analizando el comportamiento del sitio para los usuarios asociados con una oportunidad abierta específica en su CRM.
