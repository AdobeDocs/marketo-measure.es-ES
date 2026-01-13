---
description: 'Cómo interactúan  [!DNL Marketo Measure]  y  [!DNL Salesforce] '
title: 'Cómo interactúan  [!DNL Marketo Measure]  y  [!DNL Salesforce] '
exl-id: c2f9d7ce-c5b8-4664-8f92-cb54255190cd
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1298'
ht-degree: 99%

---


# Cómo interactúan [!DNL Marketo Measure] y [!DNL Salesforce] {#how-marketo-measure-and-salesforce-interact}

>[!NOTE]
>Puede que vea instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero seguirá viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

Echemos un vistazo de alto nivel a la relación entre [!DNL Marketo Measure] y Salesforce.

## Salesforce y [!DNL Marketo Measure]  {#salesforce-and-marketo-measure}

Una vez que se haya creado una cuenta de [!DNL Marketo Measure] y [!DNL Salesforce] está conectado, [!DNL Marketo Measure] empieza a insertar datos de marketing en la instancia de CRM, siempre y cuando el paquete administrado de [!DNL Marketo Measure] esté instalado y el usuario de Salesforce de [!DNL Marketo Measure] tenga permisos de edición.

Si no ha instalado el paquete de Salesforce de [!DNL Marketo Measure], [!DNL Marketo Measure] no escribirá ningún dato en la instancia de Salesforce.

![&#x200B; 3](assets/1-3.png)

De forma predeterminada, [!DNL Marketo Measure] exporta 200 registros por crédito de API cada vez que un trabajo envía datos a su CRM. Para la mayoría de los clientes, esto proporciona el equilibrio óptimo entre los créditos de API consumidos por [!DNL Marketo Measure] y los requisitos de recursos de CPU en CRM. Sin embargo, para los clientes con configuraciones de CRM complejas, como flujos de trabajo y activadores, un tamaño de lote más pequeño podría ser útil para mejorar el rendimiento de CRM. Con este fin, [!DNL Marketo Measure] permite a los clientes configurar el tamaño del lote de exportación de CRM. Esta configuración está disponible en la página [!UICONTROL Configuración] > [!UICONTROL CRM] > [!UICONTROL General] en la aplicación web de [!DNL Marketo Measure] y los clientes pueden elegir entre tamaños de lote de 200 (predeterminado), 100, 50 o 25.

![Configuración de tamaño de lote de exportación de Marketo Measure CRM en la aplicación web](assets/how-bizible-and-salesforce-interact-2.png)

Al modificar esta configuración, tenga en cuenta que los tamaños de lote más pequeños consumirán más créditos de API de su CRM. Es aconsejable reducir el tamaño del lote solo si está experimentando un tiempo de espera de CPU o una carga de CPU alta en su CRM.

## Permisos de usuario de Salesforce Connected {#salesforce-connected-user-permissions}

**Conjunto de permisos de administrador de Marketo Measure para usuario dedicado**: permite al administrador de SFDC realizar operaciones de CRUD en objetos de Marketo Measure.

**Ver y editar conjunto de permisos de posibles clientes convertidos**: esto permite a Marketo Measure decorar posibles clientes después de convertirlos en contactos.

**Casilla de verificación Usuario de marketing de Salesforce** permite al usuario crear campañas y utilizar el asistente para importación de campañas.

* Se requieren permisos adicionales para “Crear” y “Actualizar” Campaign en sus CRM.

* Cuando se crea un punto de contacto a partir de una actividad web, es necesario vincularlo a una campaña. Dado que las actividades web no tienen campañas de CRM correspondientes, es necesario crear una para establecer este vínculo. Esto se aplica tanto a los puntos de contacto de oportunidad como de posibles clientes. Se requiere el permiso de actualización porque la llamada que utilizamos es “upsert”: si el registro existe, lo actualizamos; de lo contrario, lo creamos. Esto solo se aplica a las campañas que creamos.

**Usuario estándar de Marketo Measure**: otorga a un usuario la capacidad de leer registros de objetos de Marketo Measure.

## Objetos estándar y acceso de Salesforce {#salesforce-standard-objects-and-access}

Esta sección enumera los objetos estándar de [!DNL Salesforce] con los que interactúa [!DNL Marketo Measure], así como los campos personalizados que se añaden a estos objetos una vez que se estableció la conexión y se realizó la instalación del paquete de [!DNL Marketo Measure]. De forma predeterminada, [!DNL Marketo Measure] NO se escribirá en ningún campo de objeto de [!DNL Salesforce] estándar.

**Posible cliente**

<table>
 <tbody>
  <tr>
   <th>Campos</th>
   <th>Estándar/Personalizado</th>
   <th>Lectura</th>
   <th>Escritura</th>
  </tr>
  <tr>
   <td>Identificación</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Correo electrónico</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Estado</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>CreatedDate</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>LastModifiedDate</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>ConvertedDate</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>ConvertedContactId</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>ConvertedOpportunityId</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsConverted</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsDeleted</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Sitio web</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Compañía</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>bizible2__Account__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
 </tbody>
</table>

**Contacto**

<table> 
 <tbody> 
  <tr> 
   <th>Campos</th> 
   <th>Estándar/Personalizado</th> 
   <th>Lectura</th> 
   <th>Escritura</th> 
  </tr> 
  <tr> 
   <td>Cuenta</td> 
   <td>Estándar</td> 
   <td><span>x</span></td> 
   <td><br></td> 
  </tr> 
  <tr> 
   <td>Identificación</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Correo electrónico</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Fecha de creación</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
 </tbody> 
</table>

**Cuenta**

<table>
 <tbody>
  <tr>
   <th>Campos</th>
   <th>Estándar/Personalizado</th>
   <th>Lectura</th>
   <th>Escritura</th>
  </tr>
  <tr>
   <td>Identificación</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Sitio web</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>LastModifiedDate</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsDeleted</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>bizible2__Engagement_Score__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x </td>
  </tr>
 </tbody>
</table>

**Oportunidad**

<table>
 <tbody>
  <tr>
   <th>Campos</th>
   <th>Estándar/Personalizado</th>
   <th>Lectura</th>
   <th>Escritura</th>
  </tr>
  <tr>
   <td>Nombre</td>
   <td>Estándar</td>
   <td>x</td>
   <td><br></td>
  </tr>
  <tr>
   <td>Cuenta</td>
   <td>Estándar</td>
   <td>x</td>
   <td><br></td>
  </tr>
  <tr>
   <td>Identificación</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>CreatedDate</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>LastModifiedDate</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsWon</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsClosed</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsDeleted</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>CloseDate</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>StageName</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Monto</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>bizible2__Bizible_Opportunity_Amount__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x </td>
  </tr>
 </tbody>
</table>

**Función de contacto de oportunidad**

<table>
 <tbody>
  <tr>
   <th>Campos</th>
   <th>Estándar/Personalizado</th>
   <th>Lectura</th>
   <th>Escritura</th>
  </tr>
  <tr>
   <td>Identificación</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>CreatedDate</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsDeleted</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>LastModifiedDate</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>OpportunityId</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Contactid</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>

<tr>
   <td>IsPrimary</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Función</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
 </tbody>
</table>

**Campaña**

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>Campos</th> 
   <th>Estándar/Personalizado</th> 
   <th>Lectura</th> 
   <th>Escritura</th> 
  </tr> 
  <tr> 
   <td>Identificación</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Correo electrónico</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Estado</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Sitio web</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Compañía</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Tipo</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
  <tr> 
   <td>StartDate</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
  <tr> 
   <td>EndDate</td> 
   <td>Estándar</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Nombre</td>
   <td>Estándar</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__UniqueId__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
 </tbody>
</table>

**Abonado de la campaña**

<table>
 <tbody>
  <tr>
   <th>Campos</th>
   <th>Estándar/Personalizado</th>
   <th>Lectura</th>
   <th>Escritura</th>
  </tr>
  <tr>
   <td>Identificación</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>CreatedDate</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>LastModifiedDate</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsDeleted</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>FirstRespondedDate</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>HasResponded</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Contactid</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>LeadId</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsConverted</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>CampaignId</td>
   <td>Estándar</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>bizible2__Bizible_Touchpoint_Date__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Status_Date__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Status_Contact__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Status_Leade__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Status_Opportunity__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>Para garantizar la precisión de Marketo Measure al capturar eventos de eliminación en su cuenta de Salesforce, se requieren permisos replicables para los objetos siguientes. Los permisos replicables están incluidos de serie con los objetos siguientes:
> Cuenta
> Campaña
> Miembro de la campaña
> Contacto
> Evento
> Posible cliente
> Oportunidad
> Tarea

## [!DNL Marketo Measure] Objetos personalizados en [!DNL Salesforce]  {#marketo-measure-custom-objects-in-salesforce}

Además de crear campos personalizados en los objetos estándar de SFDC, una vez que el paquete de [!DNL Marketo Measure] está instalado, crea un par de objetos personalizados. A continuación se muestra una lista de estos objetos personalizados junto con una tabla que indica los campos en los que [!DNL Marketo Measure] escribirá.

**Buyer Touchpoint**

Buyer Touchpoint es un objeto personalizado de [!DNL Marketo Measure] para encapsular las interacciones de marketing para contactos, posibles clientes y casos.

<table>
 <tbody>
  <tr>
   <th>Campos</th>
   <th>Estándar/Personalizado</th>
   <th>Lectura</th>
   <th>Escritura</th>
  </tr>
  <tr>
   <td>bizible2__Bizible_Person__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__SF_Campaign__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__UniqueId__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Marketing_Channel__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Marketing_Channel_Path__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Type__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Id__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Content__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Group_Id__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Group_Name__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Campaign_Id__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Campaign_Name__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Placement_Id__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Placement_Name__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Site_Id__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Site_Name__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Form_URL__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Form_URL_Raw__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Platform__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Browser__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Geo_City__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Geo_Country__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Geo_Region__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Keyword_Id__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Keyword_MatchType__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Position__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Keyword_Text__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Landing_Page__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Landing_Page_Raw__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Medium__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Referrer_Page__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Referrer_Page_Raw__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Search_Phrase__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Date__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Source__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Segment__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_First_Touch__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_Lead_Creation_Touch__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_U_Shape__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Destination_URL__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Case__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Contact__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
 </tbody>
</table>

**[!DNL Marketo Measure]Persona**

La persona de [!DNL Marketo Measure] es un objeto personalizado de [!DNL Marketo Measure] relacionado con los objetos Posible cliente, Contacto y Caso.

<table>
 <tbody>
  <tr>
   <th>Campos</th>
   <th>Estándar/Personalizado</th>
   <th>Lectura</th>
   <th>Escritura</th>
  </tr>
  <tr>
   <td>bizible2__UniqueId__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Lead__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Case__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Contact__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x </td>
  </tr>
 </tbody>
</table>

## Buyer Attribution Touchpoint {#buyer-attribution-touchpoint}

Buyer Attribution Touchpoint es un objeto personalizado de [!DNL Marketo Measure] para encapsular la influencia del marketing en las oportunidades.

**Buyer Attribution Touchpoint**

<table>
 <tbody>
  <tr>
   <th>Campos</th>
   <th>Estándar/Personalizado</th>
   <th>Lectura</th>
   <th>Escritura</th>
  </tr>
  <tr>
   <td>bizible2__Account__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__SF_Campaign__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Contact__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Opportunity__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__UniqueId__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Marketing_Channel__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Marketing_Channel_Path__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Type__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Id__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Content__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Group_Id__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Group_Name__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Campaign_Id__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Campaign_Name__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Placement_Id__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Placement_Name__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Site_Id__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Site_Name__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Form_URL__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Form_URL_Raw__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Platform__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Browser__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Geo_City__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Geo_Country__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Geo_Region__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Keyword_Id__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Keyword_MatchType__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Position__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Keyword_Text__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Landing_Page__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Landing_Page_Raw__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Medium__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Referrer_Page__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Referrer_Page_Raw__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Search_Phrase__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Date__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Source__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Segment__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Attribution_First_Touch__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Attribution_Lead_Conversion_Touch__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Attribution_U_Shaped__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Attribution_W_Shaped__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Attribution_Custom_Model__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Attribution_Custom_Model_2__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_First_Touch__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_Lead_Creation_Touch__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_U_Shape__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_W_Shaped__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_Custom_Model__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_Custom_Model_2__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Destination_URL__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Revenue_First_Touch__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Revenue_Lead_Creation_Touch__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Revenue_U_Shaped__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Revenue_W_Shaped__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Revenue_Custom_Model__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Revenue_Custom_Model_2__c</td>
   <td>Personalizado</td>
   <td>x</td>
   <td>x</td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>[Información general sobre permisos de integración](/help/api-connections/integration-permissions-overview.md){target="_blank"}
