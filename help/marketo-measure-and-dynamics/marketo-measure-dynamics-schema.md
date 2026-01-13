---
description: Esquema de Dynamics [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: Esquema de Dynamics [!DNL Marketo Measure]
exl-id: f8da47b1-d844-4bd2-8125-8689cbb5cc30
feature: Microsoft Dynamics
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 66%

---


# Esquema de Dynamics [!DNL Marketo Measure] {#marketo-measure-dynamics-schema}

>[!NOTE]
>Puede que vea instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero seguirá viendo &quot;Bizible&quot; en su CRM. Estamos trabajando para que se actualice y el cambio de marca se reflejará pronto en su CRM.

A continuación se muestra el esquema de Dynamics necesario para comenzar con [!DNL Marketo Measure]. Se muestran todas las entidades y campos, junto con el acceso de lectura o escritura requerido.

## Buyer Touchpoints {#buyer-touchpoints}

Buyer Touchpoint es una entidad personalizada [!DNL Marketo Measure] para encapsular las interacciones de marketing de contactos y posibles clientes.

## Relaciones de Buyer Touchpoint {#buyer-touchpoint-relationships}

Este diagrama es una visualización de alto nivel de las relaciones entre las entidades de Dynamics Stock y Buyer Touchpoint.

## Buyer Touchpoint {#buyer-touchpoint}

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Campaign_Id</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Campaign_Name</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Content</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Destination_URL</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Group_Id</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Group_Name</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Id</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Bizible_TouchpointId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Browser</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_CampaignId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_ContactId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Count_First_Touch</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Count_Lead_Conversion_Touch</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Count_U_Shaped</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Form_URL</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Form_URL_Raw</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Geo_City</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_País_geográfico</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Región_geográfica</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Keyword_Id</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Keyword_MatchType</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Keyword_Text</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Landing_Page</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Landing_Page_Raw</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_LeadId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Marketing_Channel</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Marketing_Channel_Path</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Medium</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Name</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Placement_Id</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Placement_Name</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Platform</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Referrer_Page</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Referrer_Page_Raw</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Search_Phrase</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Segmento</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Site_Id</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Site_Name</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_Date</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_Position</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_Source</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_Type</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_UniqueId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Account</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
 </tbody>
</table>

## Buyer Attribution Touchpoint {#buyer-attribution-touchpoint}

Buyer Attribution Touchpoint es una entidad personalizada [!DNL Marketo Measure] para encapsular la influencia del marketing en Oportunidades.

## Relaciones de Buyer Attribution Touchpoint {#buyer-attribution-touchpoint-relationships}

Este diagrama es una visualización de alto nivel de las relaciones entre las entidades de Dynamics Stock y Buyer Attribution Touchpoint.

## Buyer Attribution Touchpoints {#buyer-attribution-touchpoints}

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>bizible2_AccountId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Campaign_Id</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Campaign_Name</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Content</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Destination_URL</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Group_Id</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Group_Name</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Ad_Id</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Attribution_Custom_Model</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Atribución_Modelo_Personalizado_2</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Atribución_Primer_toque</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Attribution_Lead_Conversion_Touch</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Atribución_Forma_U</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Atribución_W_Shape</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Bizible_Attribution_TouchpointId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Browser</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_CampaignId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_ContactId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Count_Custom_Model</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Count_Custom_Model_2</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Count_First_Touch</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Count_Lead_Creation_Touch</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Count_U_Shaped</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Count_W_Shaped</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Form_URL</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Form_URL_Raw</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Geo_City</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_País_geográfico</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Región_geográfica</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Keyword_Id</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Keyword_MatchType</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Keyword_Text</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Landing_Page</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Landing_Page_Raw</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Marketing_Channel</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Marketing_Channel_Path</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Medium</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Name</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_OpportunityId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Placement_Id</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Placement_Name</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Platform</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Referrer_Page</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Referrer_Page_Raw</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Revenue_Custom_Model</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Revenue_Custom_Model_2</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_revenue_custom_model_2_Base</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_revenue_custom_model_Base</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Revenue_First_Touch</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_revenue_first_touch_Base</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Revenue_Lead_Conversion_Touch</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_revenue_lead_conversion_Base</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Revenue_U_Shaped</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_revenue_u_shape_Base</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Revenue_W_Shaped</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_revenue_w_shape_Base</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Search_Phrase</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Segmento</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Site_Id</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Site_Name</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_Date</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_Position</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_Source</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_Type</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_UniqueId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
 </tbody>
</table>

## [!DNL Marketo Measure] pruebas AB {#marketo-measure-ab-tests}

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>bizible2_Bizible_ABTestId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_BizibleId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_ContactId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_DateReported</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Experimento</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_ExperimentId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_LeadId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Name</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_OpportunityId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_UserId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Variation</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_VariationId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
 </tbody>
</table>

## [!DNL Marketo Measure] Eventos {#marketo-measure-events}

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>bizible2_Bizible_EventId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_BizibleId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_ContactId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_DateReported</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_EventName</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_EventValue</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_LeadId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Name</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_OpportunityId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
 </tbody>
</table>

## Historial de [!DNL Marketo Measure] {#marketo-measure-history}

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>bizible2_Bizible_HistoryId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Entity_Type</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_EntityId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_EntityLogicalName</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Name</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
 </tbody>
</table>

## Entidades estándar de Dynamics {#dynamics-standard-entities}

Esta lista proporciona las entidades de Dynamics Standard con las que interactúa [!DNL Marketo Measure] y los campos personalizados que agregamos a estas entidades.

**Posible cliente**

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>plomizo</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>emailaddress1</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>código de estado</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>código de estado</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>creado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>modificado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>contactid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>calificaciónoportunityid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>websiteurl</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>companyname</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>bizible2_Account</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_BizibleId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
 </tbody>
</table>

**Contacto**

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>contactid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>emailaddress1</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>accountid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>creado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>modificado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>bizible2_BizibleId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
 </tbody>
</table>

**Cuenta**

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>accountid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>websiteurl</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>creado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>modificado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>bizible2_Engagement_Score</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
 </tbody>
</table>

**Oportunidad**

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>oportunityid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>accountid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>creado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>modificado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>código de estado</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>statecodename</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>etapa de ventas</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>salesstagecode</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>estimatedclosedate</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>valor real</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>bizible2_Bizible_Opportunity_Amount</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_bizible_Opportunity_amount_Base</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
 </tbody>
</table>

**Campaña**

También se requieren permisos de &quot;creación&quot; de Campaign, además de los permisos de lectura y escritura que se indican a continuación.

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>campaignid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>typecode</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>typecodename</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>creado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>modificado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>bizible2_Bizible_Attribution_SyncType</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Marketing_Lists_Sync</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_UniqueId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_End_Date</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_Start_Date</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
 </tbody>
</table>

**Respuesta de campaña**

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>activityid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>activitypecode</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>activitypecodename</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>creado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>modificado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>código de respuesta</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>responsecodename</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>cliente</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>con respecto a objectid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>bizible2_Bizible_Touchpoint_Date</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_Status_Date</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_Status_Contact</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_Status_Leade</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_Touchpoint_Status_Opportunity</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
 </tbody>
</table>

**Lista**

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>listid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>createdfromcode</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>membertype</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>creado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>modificado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>bizible2_Bizible_Touchpoint_Date</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
 </tbody>
</table>

**ListMember**

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>listid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>entityid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>listmemberid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>creado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>modificado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
 </tbody>
</table>

**Llamada de teléfono**

<table>
 <tbody>
  <tr>
   <th><p>Nombre del esquema</p></th>
   <th><p>Estándar/Personalizado</p></th>
   <th><p>Lectura</p></th>
   <th><p>Escritura</p></th>
  </tr>
  <tr>
   <td><p>activityid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>activitypecode</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>activitypecodename</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>creado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>modificado el</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>cliente</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>con respecto a objectid</p></td>
   <td><p>Estándar</p></td>
   <td><p>x</p></td>
   <td> </td>
  </tr>
  <tr>
   <td><p>bizible2_Bizible_Touchpoint_Date</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
  <tr>
   <td><p>bizible2_BizibleId</p></td>
   <td><p>Personalizado</p></td>
   <td><p>x</p></td>
   <td><p>x</p></td>
  </tr>
 </tbody>
</table>

[] = Solo clientes heredados de V1
