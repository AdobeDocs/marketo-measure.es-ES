---
unique-page-id: 18874680
description: "[!DNL Facebook] API - [!DNL Marketo Measure]"
title: "[!DNL Facebook] API"
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
feature: APIs, Integration, UTM Parameters
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 2%

---

# [!DNL Facebook] API {#facebook-api}

## Introducción {#introduction}

Similar a nuestro AdWords &amp; [!DNL Bing Ads] integraciones, nuestras [!DNL Facebook] La integración de realiza dos acciones fundamentales:

* Etiquetar automáticamente todo [!DNL Facebook] Anuncios con un [!DNL Marketo Measure] parámetro (_bf)
* Descargar información de coste de anuncio en todos los anuncios activos de Facebook

## Cómo configurar el [!DNL Facebook] Integración {#how-to-configure-the-facebook-integration}

En cuanto a la configuración, hay siete pasos que completar dentro de la [!DNL Marketo Measure] aplicación.

1. Vaya a [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} e inicie sesión.
1. En Mi cuenta, seleccione **[!UICONTROL Configuración]**.
1. En Integraciones, seleccione **[!UICONTROL Conexiones]**.
1. Seleccionar **[!UICONTROL Configuración de una nueva conexión de anuncios]** y aparecerá una ventana emergente. Seleccionar **[!UICONTROL Facebook]** e inicie sesión con sus credenciales de Facebook.

   >[!NOTE]
   >
   >La persona que conecta el [!DNL Facebook Ads] La cuenta debe ser un administrador dentro de [!DNL Facebook Ads] cuenta.

1. Una [!DNL Marketo Measure] está conectado a su cuenta de Facebook, haga clic en el icono de lápiz situado junto a la cuenta.
1. Dentro de esta vista, mueva el icono &quot;¿Etiquetado automático?&quot; Cambie a &#39;Sí&#39;. A continuación, active la casilla de verificación que se encuentra en la [!UICONTROL Más información] para aceptar los términos y condiciones. Asegúrese de que la [!UICONTROL Etiquetado automático] toggle sigue establecido en &#39;[!UICONTROL Sí]&#39;.

## Conexión de la cuenta {#connecting-the-account}

![](assets/1.gif)

## Activación del etiquetado automático {#enabling-autotagging}

>[!NOTE]
>
>Si habilita el etiquetado automático, restableceremos el historial de conversión y la prueba social de todos los anuncios que etiquetamos. Recomendamos encarecidamente [exportación de estos datos como CSV](https://www.facebook.com/business/help/205067636197240) antes de habilitar el etiquetado automático.

![](assets/2-2.png)

Una vez habilitada la integración, [!DNL Marketo Measure] comenzará a descargar el coste a nivel de anuncio en [!DNL Marketo Measure Marketing ROI] Tablero.

Para que la integración funcione correctamente, debe habilitar el etiquetado automático en su [!DNL Facebook] cuenta. Esto permitirá que el sistema añada un parámetro _bf en todos los vínculos de publicidad. Este proceso añadirá el nuevo parámetro sobre cualquier otro parámetro de seguimiento que ya haya añadido a su [!DNL Facebook] anuncios.

![](assets/3.gif)

## Asignación de campos {#field-mapping}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p><strong>Campo Touchpoint</strong></p></th> 
   <th><p><strong>Valor</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>ID de campaña de publicidad</p></td> 
   <td><p>[[!DNL Facebook] ID de campaña]</p></td> 
  </tr> 
  <tr> 
   <td><p>Nombre de campaña de anuncios </p></td> 
   <td><p>[[!DNL Facebook] [Nombre de campaña] o [utm_campaign] si se proporcionan</p></td> 
  </tr> 
  <tr> 
   <td><p>ID de grupo de publicidad</p></td> 
   <td><p>[[!DNL Facebook] ID del conjunto de anuncios</p></td> 
  </tr> 
  <tr> 
   <td><p>Nombre del grupo de anuncios</p></td> 
   <td><p>[[!DNL Facebook] Nombre del conjunto de anuncios]</p></td> 
  </tr> 
  <tr> 
   <td><p>Origen del Touchpoint</p></td> 
   <td><p>"[!DNL Facebook]", o [utm_source] si se proporciona</p></td> 
  </tr> 
  <tr> 
   <td><p>Medio</p></td> 
   <td><p>"Social" o [utm_medium] si se proporcionan</p></td> 
  </tr> 
  <tr> 
   <td><p>ID de anuncio o Creative_Unique_Id (Data Warehouse)</p></td> 
   <td><p>[ID personalizado generado a partir de utm_content]</p></td> 
  </tr> 
  <tr> 
   <td><p>Contenido del anuncio o Creative_Name (Data Warehouse)</p></td> 
   <td><p>[utm_content] si se proporciona</p></td> 
  </tr> 
  <tr> 
   <td><p>Texto de palabra clave o Nombre_palabra_clave (Data Warehouse)</p></td> 
   <td><p>[utm_term] si se proporciona</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Unique_Id (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] ID de anuncio]</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Name (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Nombre del anuncio]</p></td> 
  </tr> 
  <tr> 
   <td><p>Keyword_Unique_Id (Data Warehouse)</p></td> 
   <td><p>[ID personalizado generado a partir de utm_term]</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Provider (Data Warehouse)</p></td> 
   <td><p>"[!DNL Facebook]"</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Unique_ID (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] N.º cuenta]</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Name (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Nombre de la cuenta]</p></td> 
  </tr> 
 </tbody> 
</table>

## Preguntas frecuentes {#faq}

**P: Qué [!DNL Facebook] Los anuncios son compatibles con [!DNL Marketo Measure]?**

R: Carrusel, Imagen única. En este momento no es vídeo, presentación ni colección.

**P: ¿Qué es la prueba social?**

R: La prueba social es una participación visible como &quot;me gusta&quot;, clics, comentarios y difusiones.

**P: ¿Qué sucede cuando [!DNL Marketo Measure] ¿Desea etiquetar el anuncio?**

A: [!DNL Facebook] no permite que se editen anuncios, por lo que [!DNL Marketo Measure] debe eliminar el elemento creativo, que contiene la dirección URL de destino, y luego volver a crear el anuncio con los nuevos parámetros.

**P: ¿Por qué [!DNL Marketo Measure] actualizar todo [!DNL Facebook] ¿Anuncios?**

R: El [!DNL Marketo Measure] El proceso consiste en etiquetar todos los anuncios en caso de que se reactiven.

**P: ¿Qué permiso necesita el usuario conectado?**

R: ads_management, correo electrónico

**P: ¿Cuánto tiempo puede tardar la importación de datos de gasto?**

A: 1 hora

**P: ¿Cuánto tiempo puede tardar la importación de datos de publicidad?**

A: 4 horas
