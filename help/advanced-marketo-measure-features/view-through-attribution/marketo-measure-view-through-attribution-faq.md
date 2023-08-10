---
unique-page-id: 18874652
description: "[!DNL Marketo Measure] Preguntas frecuentes sobre la atribución de visualización: [!DNL Marketo Measure] - Documentación del producto"
title: '"[!DNL Marketo Measure] Preguntas frecuentes sobre "Ver mediante atribución"'
exl-id: d20e88f3-3ff8-4381-a4b8-6862798caa74
feature: Attribution
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 14%

---

# Preguntas frecuentes sobre la atribución de visualizaciones de [!DNL Marketo Measure] {#marketo-measure-view-through-attribution-faq}

## ¿Qué es la Vista a través de la atribución? {#what-is-view-through-attribution}

El [!DNL Marketo Measure] La función Ver a través de atribución incluye la capacidad de incluir impresiones de publicidad en el modelo de atribución.

## ¿Por qué es importante la vista a través de la atribución? {#why-is-view-through-attribution-important}

Históricamente, los especialistas en marketing han tenido dificultades para tener en cuenta la resegmentación o la publicidad de impresión en el análisis de atribución. Los clientes potenciales pueden, una y otra vez, estar expuestos a anuncios de retargeting, pero es poco probable que hagan clic en uno de estos anuncios y completen un formulario dentro de la misma sesión. Nuestra solución de Atribución de vistas ahora tiene la capacidad de rastrear si alguien estuvo expuesto o no a un anuncio de impresión. Este punto de contacto se adjuntará al registro individual y se aplicará hasta que el cliente potencial se convierta en cliente. Con esta información, el experto en marketing ahora obtendrá un mejor conocimiento del rendimiento de su publicidad de redireccionamiento.

## ¿Qué se necesita para configurar esto? {#what-is-involved-in-setting-this-up}

Para que [!DNL Marketo Measure] para empezar a medir las impresiones de publicidad, existe una etiqueta de impresión que debe colocarse en el administrador de campañas de doble clic. Una vez implementada la etiqueta, las impresiones se almacenan en nuestros registros y nos encargamos del resto. Póngase en contacto con su administrador de éxito si está interesado en medir la vista mediante atribución.

## ¿Qué plataformas de publicidad son compatibles? {#which-ad-platforms-are-supported}

Actualmente admitimos Doubleclick Campaign Manager.

## ¿Cómo se calcula la atribución? {#how-is-the-attribution-calculated}

Hemos realizado un análisis cuidadoso de los datos de impresión y su influencia en las conversiones en todas las etapas y canales de marketing. La distribución varía según el modelo, como se puede ver en la tabla siguiente:

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
   <th>Primer contacto</th> 
   <th>Creación de posibles clientes</th> 
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

## ¿Qué aspecto tendrá esto en Salesforce? {#what-will-this-look-like-in-salesforce}

[!DNL Marketo Measure] creará un único punto de contacto de impresión en cualquier posible cliente que se haya expuesto al anuncio en pantalla. Podemos asignar al usuario incluso después de que llegue a su sitio web (FT) y rellene un formulario (LC). El punto de contacto contendrá información de la publicidad, como el nombre o ID de la campaña de publicidad, el ID de publicidad, el contenido del anuncio, el nombre o ID del sitio, el nombre o ID de ubicación, el canal de marketing, la ubicación geográfica, la página de referente, etc.

El modelo de atribución de visualizaciones dependerá del cliente y de sus datos.
