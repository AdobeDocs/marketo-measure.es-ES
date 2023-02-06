---
unique-page-id: 18874680
description: "[!DNL Facebook] API - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Facebook] API"
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 3%

---

# [!DNL Facebook] API {#facebook-api}

## Introducción {#introduction}

Similar a nuestras AdWords y [!DNL Bing Ads] integraciones, nuestra [!DNL Facebook] la integración realiza dos acciones fundamentales:

* Etiquetar automáticamente todo [!DNL Facebook] Anuncios con un [!DNL Marketo Measure] parámetro (_bf)
* Descargar información sobre los costos de publicidad en todas las publicidades activas de Facebook

## Cómo configurar la variable [!DNL Facebook] Integración {#how-to-configure-the-facebook-integration}

En cuanto a la configuración, hay que completar siete pasos dentro de la variable [!DNL Marketo Measure] aplicación.

1. Vaya a [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} e inicie sesión.
1. En Mi cuenta , seleccione **[!UICONTROL Configuración]**.
1. En Integraciones , seleccione **[!UICONTROL Conexiones]**.
1. Select **[!UICONTROL Configurar nueva conexión de anuncios]** y aparecerá una ventana emergente. Select **[!UICONTROL Facebook]** e inicie sesión con sus credenciales de Facebook.

   >[!NOTE]
   >
   >La persona que conecta el [!DNL Facebook Ads] La cuenta debe ser un administrador dentro de la variable [!DNL Facebook Ads] cuenta.

1. Una vez [!DNL Marketo Measure] está conectado a su cuenta de Facebook, haga clic en el icono de lápiz situado junto a la cuenta.
1. Dentro de esta vista, mueva el &quot;¿Etiquetado automático?&quot; cambie a Sí. A continuación, seleccione la casilla de verificación que se encuentra en la variable [!UICONTROL Más información] para aceptar los términos y condiciones. Asegúrese de que la variable [!UICONTROL Etiquetado automático] alternar sigue configurado como &#39;[!UICONTROL Sí]&#39;.

## Conexión de la cuenta {#connecting-the-account}

![](assets/1.gif)

## Habilitación del etiquetado automático {#enabling-autotagging}

>[!NOTE]
>
>Si habilita el etiquetado automático, restableceremos el historial de conversión y la prueba social de todas las publicidades que etiquetamos. Recomendamos encarecidamente [exportación de estos datos como CSV](https://www.facebook.com/business/help/205067636197240) antes de habilitar el etiquetado automático.

![](assets/2-2.png)

Una vez que haya habilitado la integración, [!DNL Marketo Measure] empezará a descargar el coste de nivel de anuncio en la variable [!DNL Marketo Measure Marketing ROI] Tablero.

Para que la integración funcione correctamente, debe habilitar el etiquetado automático en su [!DNL Facebook] cuenta. Esto permitirá que nuestro sistema agregue un parámetro _bf en todos los vínculos de anuncios. Este proceso agregará el nuevo parámetro sobre cualquier otro parámetro de seguimiento que ya haya agregado al informe [!DNL Facebook] anuncios.

![](assets/3.gif)

## Asignación de campos {#field-mapping}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p><strong>Campo de punto de contacto</strong></p></th> 
   <th><p><strong>Valor</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>ID de campaña de publicidad</p></td> 
   <td><p>[[!DNL Facebook] Identificación de la campaña]</p></td> 
  </tr> 
  <tr> 
   <td><p>Nombre de campaña de publicidad </p></td> 
   <td><p>[[!DNL Facebook] Nombre de campaña] o [utm_campaign] si se proporciona</p></td> 
  </tr> 
  <tr> 
   <td><p>ID del grupo de publicidad</p></td> 
   <td><p>[[!DNL Facebook] ID del conjunto de anuncios]</p></td> 
  </tr> 
  <tr> 
   <td><p>Nombre del grupo de anuncios</p></td> 
   <td><p>[[!DNL Facebook] Nombre del conjunto de anuncios]</p></td> 
  </tr> 
  <tr> 
   <td><p>Fuente del Touchpoint</p></td> 
   <td><p>"[!DNL Facebook]", o [utm_source] si se proporciona</p></td> 
  </tr> 
  <tr> 
   <td><p>Media</p></td> 
   <td><p>"Social" o [utm_medium] si se proporciona</p></td> 
  </tr> 
  <tr> 
   <td><p>ID de anuncio o Creative_Unique_Id (Data Warehouse)</p></td> 
   <td><p>[ID personalizado generado a partir de utm_content]</p></td> 
  </tr> 
  <tr> 
   <td><p>Contenido del anuncio o Nombre_creativo (Data Warehouse)</p></td> 
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
   <td><p>Nombre_anuncio (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Nombre del aviso]</p></td> 
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
   <td><p>[[!DNL Facebook] cuenta #]</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Name (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Nombre de la cuenta]</p></td> 
  </tr> 
 </tbody> 
</table>

## Preguntas frecuentes {#faq}

**P: Qué [!DNL Facebook] Los anuncios son compatibles con [!DNL Marketo Measure]?**

A: Carrusel, Imagen única. No vídeo, presentación o colección en este momento.

**P: ¿Qué es la prueba social?**

A: La prueba social es una participación visible, como &quot;Me gusta&quot;, clics, comentarios y compartidos.

**P: Qué ocurre cuando [!DNL Marketo Measure] etiqueta la publicidad?**

A: [!DNL Facebook] no permite que se editen las publicidades [!DNL Marketo Measure] debe eliminar el elemento creativo, que contiene la dirección URL de destino, y luego volver a crear la publicidad con los nuevos parámetros.

**P: Why [!DNL Marketo Measure] actualizar todo [!DNL Facebook] ¿Publicidades?**

A: La variable [!DNL Marketo Measure] es etiquetar todos los anuncios en caso de que se reactiven.

**P: ¿Qué permiso necesita el usuario conectado?**

A: ads_management, correo electrónico

**P: ¿Cuánto tiempo se puede tardar en importar los datos de gasto?**

A: 1 hora

**P: ¿Cuánto tiempo se puede tardar en importar datos de publicidad?**

A: 4 horas
