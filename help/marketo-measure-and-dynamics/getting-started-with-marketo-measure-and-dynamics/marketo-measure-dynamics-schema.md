---
unique-page-id: 18874523
description: "[!DNL Marketo Measure] Esquema de Dynamics [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Esquema de Dynamics"
exl-id: f8da47b1-d844-4bd2-8125-8689cbb5cc30
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '1408'
ht-degree: 19%

---

# [!DNL Marketo Measure] Esquema de Dynamics {#marketo-measure-dynamics-schema}

>[!NOTE]
>
>Puede ver instrucciones que especifican &quot;[!DNL Marketo Measure]&quot; en nuestra documentación, pero aún así ver &quot;Bizible&quot; en su CRM. Estamos trabajando para que esto se actualice y el cambio de marca se reflejará pronto en su CRM.

A continuación encontrará el esquema de Dynamics necesario para empezar a usar [!DNL Marketo Measure]. Se muestran todas las entidades y campos, junto con el acceso de lectura o escritura requerido.

## Buyer Touchpoints {#buyer-touchpoints}

El punto de contacto del comprador es un [!DNL Marketo Measure] entidad personalizada para encapsular las interacciones de marketing para Contactos y Posibles clientes.

## Relaciones entre puntos de contacto del comprador {#buyer-touchpoint-relationships}

Este diagrama es una visualización de alto nivel de las relaciones entre las entidades de Dynamics Stock y el punto de contacto del comprador.

## Punto de contacto del comprador {#buyer-touchpoint}

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
   <td><p>bizible2_Geo_Country</p></td> 
   <td><p>Personalizado</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Geo_Region</p></td> 
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
   <td><p>bizible2_Medio</p></td> 
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
   <td><p>bizible2_Segment</p></td> 
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

## Punto de contacto de atribución del comprador {#buyer-attribution-touchpoint}

El punto de contacto de atribución de comprador es un [!DNL Marketo Measure] entidad personalizada para encapsular la influencia del marketing en Oportunidades.

## Relaciones de puntos de contacto de atribución de comprador {#buyer-attribution-touchpoint-relationships}

Este diagrama es una visualización de alto nivel de las relaciones entre las entidades de Dynamics Stock y el punto de contacto de atribución del comprador.

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
   <td><p>bizible2_Attribution_Custom_Model_2</p></td> 
   <td><p>Personalizado</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_First_Touch</p></td> 
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
   <td><p>bizible2_Attribution_U_Shaped</p></td> 
   <td><p>Personalizado</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_W_Shaped</p></td> 
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
   <td><p>bizible2_Geo_Country</p></td> 
   <td><p>Personalizado</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Geo_Region</p></td> 
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
   <td><p>bizible2_Medio</p></td> 
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
   <td><p>bizible2_oportunityId</p></td> 
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
   <td><p>bizible2_Segment</p></td> 
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

## [!DNL Marketo Measure] Pruebas AB {#marketo-measure-ab-tests}

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
   <td><p>bizible2_oportunityId</p></td> 
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
   <td><p>bizible2_oportunityId</p></td> 
   <td><p>Personalizado</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

## [!DNL Marketo Measure] Historial {#marketo-measure-history}

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

## Entidades de Dynamics Standard {#dynamics-standard-entities}

Esta lista proporciona las entidades de Dynamics Standard que [!DNL Marketo Measure] interactúa con, así como con los campos personalizados que agregamos a estas entidades.

**Cliente potencial**

<table> 
 <tbody> 
  <tr> 
   <th><p>Nombre del esquema</p></th> 
   <th><p>Estándar/Personalizado</p></th> 
   <th><p>Lectura</p></th> 
   <th><p>Escritura</p></th> 
  </tr> 
  <tr> 
   <td><p>Leadid</p></td> 
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
   <td><p>statcode</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>statuscode</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>creado</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>modifiedon</p></td> 
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
   <td><p>califyingoportunityid</p></td> 
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
   <td><p>creado</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>modifiedon</p></td> 
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
   <td><p>creado</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>modifiedon</p></td> 
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
   <td><p>creado</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>modifiedon</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>statcode</p></td> 
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
   <td><p>salesstage</p></td> 
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
   <td><p>estimmatedclosedate</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>actualvalue</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Bizible_Oportunity_Amount</p></td> 
   <td><p>Personalizado</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_bizible_oportunidad_cantidad_base</p></td> 
   <td><p>Personalizado</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

**Campaña**

<table> 
 <tbody> 
  <tr> 
   <th><p>Nombre del esquema</p></th> 
   <th><p>Estándar/Personalizado</p></th> 
   <th><p>Lectura</p></th> 
   <th><p>Escritura</p></th> 
  </tr> 
  <tr> 
   <td><p>campaign</p></td> 
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
   <td><p>creado</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>modifiedon</p></td> 
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
   <td><p>creado</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>modifiedon</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>responsecode</p></td> 
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
   <td><p>sobreobjectid</p></td> 
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
   <td><p>bizible2_Touchpoint_Status_Oportunity</p></td> 
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
   <td><p>creado</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>modifiedon</p></td> 
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
   <td><p>creado</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>modifiedon</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

**Llamada telefónica**

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
   <td><p>creado</p></td> 
   <td><p>Estándar</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>modifiedon</p></td> 
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
   <td><p>sobreobjectid</p></td> 
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
