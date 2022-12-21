---
unique-page-id: 18874652
description: "[!DNL Marketo Measure] Preguntas frecuentes sobre la atribución de visualizaciones: [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Ver preguntas frecuentes sobre atribución"
exl-id: d20e88f3-3ff8-4381-a4b8-6862798caa74
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 13%

---

# [!DNL Marketo Measure] Preguntas frecuentes sobre la atribución de Visualizaciones {#marketo-measure-view-through-attribution-faq}

## ¿Qué es la atribución a través de la vista? {#what-is-view-through-attribution}

La variable [!DNL Marketo Measure] La función de atribución de visualización incluye la capacidad de incluir impresiones de publicidad en el modelo de atribución.

## ¿Por qué es importante la atribución de visualizaciones? {#why-is-view-through-attribution-important}

Históricamente, para los especialistas en marketing ha sido difícil tener en cuenta la reorientación o la publicidad de impresión en el análisis de atribución. Los posibles clientes pueden, una y otra vez, verse expuestos a nuevos anuncios de objetivo, pero es poco probable que hagan clic en uno de estos anuncios y rellenen un formulario en la misma sesión. Nuestra solución de atribución de visualización ahora tiene la capacidad de rastrear si alguien estuvo expuesto o no a un anuncio de impresión. Este punto de contacto se anexará al registro individual y se mantendrá hasta que el cliente potencial se convierta en cliente. Con esta información, el especialista en marketing ahora obtendrá una mejor perspectiva del rendimiento de su publicidad de redireccionamiento.

## ¿Qué implica configurar esto? {#what-is-involved-in-setting-this-up}

Para [!DNL Marketo Measure] para empezar a medir las impresiones de la publicidad, hay una etiqueta de impresión que debe colocarse en el administrador de campaña de Doubleclick. Una vez implementada la etiqueta , las impresiones se almacenan en nuestros registros y nosotros nos encargamos del resto. Póngase en contacto con el administrador de éxito si está interesado en medir la vista a través de la atribución.

## ¿Qué plataformas de publicidad se admiten? {#which-ad-platforms-are-supported}

Actualmente admitimos el administrador de campaña de Doubleclick.

## ¿Cómo se calcula la atribución? {#how-is-the-attribution-calculated}

Realizamos un análisis cuidadoso de los datos de impresión y su influencia en las conversiones en todas las etapas y canales de marketing. La distribución varía según el modelo, como puede verse en la siguiente tabla:

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><br></th> 
   <th>Primera instancia de interacción</th> 
   <th>Creación de cliente potencial</th> 
   <th>En forma de U</th> 
   <th>En forma de W</th> 
   <th>Ruta completa</th> 
   <th>Modelo personalizado</th> 
  </tr> 
  <tr> 
   <td><strong>Impresiones</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>Personalizado</td> 
  </tr> 
  <tr> 
   <td><strong>FT</strong></td> 
   <td>100%</td> 
   <td>0%</td> 
   <td>35%</td> 
   <td>26.6%</td> 
   <td>20%</td> 
   <td>Personalizado</td> 
  </tr> 
  <tr> 
   <td><strong>LC</strong></td> 
   <td>0%</td> 
   <td>100%</td> 
   <td>35%</td> 
   <td>26.6%</td> 
   <td>20%</td> 
   <td>Personalizado</td> 
  </tr> 
  <tr> 
   <td><strong>OC</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>26.6%</td> 
   <td>20%</td> 
   <td>Personalizado</td> 
  </tr> 
  <tr> 
   <td><strong>Cerrado</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>20%</td> 
   <td>Personalizado</td> 
  </tr> 
  <tr> 
   <td><strong>Medio</strong></td> 
   <td>0%</td> 
   <td>0%</td> 
   <td>20%</td> 
   <td>10%</td> 
   <td>10%</td> 
   <td>Personalizado</td> 
  </tr> 
 </tbody> 
</table>

## ¿Cómo se verá esto en Salesforce? {#what-will-this-look-like-in-salesforce}

[!DNL Marketo Measure] creará un touchpoint de impresión única en cualquier posible posible cliente expuesto al anuncio en pantalla. Podemos asignar al usuario incluso después de que acceda por primera vez a su sitio web (FT) y rellene un formulario (LC). El touchpoint contendrá información de la publicidad, como el nombre/ID de la campaña de publicidad, el ID del anuncio, el contenido de la publicidad, el ID/nombre del sitio, el ID de ubicación, el canal de marketing, la información geográfica, la página de referente, etc.

El modelo de atribución de visualización dependerá del cliente y de sus datos.
