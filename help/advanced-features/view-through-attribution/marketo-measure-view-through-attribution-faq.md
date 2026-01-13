---
description: Preguntas frecuentes sobre la atribución de vista [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: Preguntas frecuentes sobre la atribución de visualizaciones de [!DNL Marketo Measure]
exl-id: d20e88f3-3ff8-4381-a4b8-6862798caa74
feature: Attribution
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 27%

---


# Preguntas frecuentes sobre la atribución de visualizaciones de [!DNL Marketo Measure] {#marketo-measure-view-through-attribution-faq}

## ¿Qué es la Vista a través de la atribución? {#what-is-view-through-attribution}

La característica [!DNL Marketo Measure] [!UICONTROL Atribución de visualización] incluye la capacidad de incluir impresiones de anuncios en el modelo de atribución.

>[!IMPORTANT]
>Debido a cuestiones de privacidad, las cookies de terceros están a punto de desaparecer. La obsolescencia de las cookies de terceros anunciada por Google Chrome en el tercer trimestre de 2024 marca el final de esta forma de seguimiento. Por consiguiente, Adobe va a dejar de utilizar las funciones de Marketo Measure que dependan de cookies de terceros; en concreto Seguimiento entre dominios y Atribución de visualización, que utilizan la cookie de impresión de Google/DoubleClick. Ninguna otra función de Marketo Measure se verá afectada. El uso de cookies de origen tampoco se verá afectado. En vista de la programación de Google, la fecha prevista de obsolescencia de las dos funciones anteriores es el 1/6/2024. Los datos relacionados recopilados antes de esta fecha permanecen a disposición de los clientes de Adobe.

## ¿Por qué es importante [!UICONTROL Ver a través de la atribución]? {#why-is-view-through-attribution-important}

Históricamente, los especialistas en marketing han tenido dificultades para tener en cuenta la resegmentación o la publicidad de impresión en el análisis de atribución. Es posible que, una y otra vez, los clientes potenciales estén expuestos a anuncios de retargeting, pero es poco probable que hagan clic en uno de estos anuncios y rellenen un formulario dentro de la misma sesión. Nuestra solución de Atribución de vistas ahora tiene la capacidad de rastrear si alguien estuvo expuesto o no a un anuncio de impresión. Este punto de contacto se adjuntará al registro individual y se aplicará hasta que el cliente potencial se convierta en cliente. Con esta información, el experto en marketing ahora obtendrá un mejor insight en el rendimiento de su publicidad de redireccionamiento.

## ¿Qué se necesita para configurar esto? {#what-is-involved-in-setting-this-up}

Para que [!DNL Marketo Measure] empiece a medir las impresiones de publicidad, existe una etiqueta de impresión que debe colocarse en el administrador de campañas de doble clic. Una vez implementada la etiqueta, las impresiones se almacenan en nuestros registros y nos encargamos del resto. Póngase en contacto con el administrador de éxito si está interesado en medir la vista mediante atribución.

## ¿Qué plataformas de publicidad son compatibles? {#which-ad-platforms-are-supported}

Actualmente admitimos [!DNL Doubleclick] Campaign Manager.

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
   <td>0 %</td>
   <td>0 %</td>
   <td>10 %</td>
   <td>10 %</td>
   <td>10 %</td>
   <td>Personalizado</td>
  </tr>
  <tr>
   <td><strong>FT</strong></td>
   <td>100 %</td>
   <td>0 %</td>
   <td>35 %</td>
   <td>26,6 %</td>
   <td>20 %</td>
   <td>Personalizado</td>
  </tr>
  <tr>
   <td><strong>LC</strong></td>
   <td>0 %</td>
   <td>100 %</td>
   <td>35 %</td>
   <td>26,6 %</td>
   <td>20 %</td>
   <td>Personalizado</td>
  </tr>
  <tr>
   <td><strong>OC</strong></td>
   <td>0 %</td>
   <td>0 %</td>
   <td>0 %</td>
   <td>26,6 %</td>
   <td>20 %</td>
   <td>Personalizado</td>
  </tr>
  <tr>
   <td><strong>Cerrado</strong></td>
   <td>0 %</td>
   <td>0 %</td>
   <td>0 %</td>
   <td>0 %</td>
   <td>20 %</td>
   <td>Personalizado</td>
  </tr>
  <tr>
   <td><strong>Segundo nombre</strong></td>
   <td>0 %</td>
   <td>0 %</td>
   <td>20 %</td>
   <td>10 %</td>
   <td>10 %</td>
   <td>Personalizado</td>
  </tr>
 </tbody>
</table>

## ¿Qué aspecto tendrá esto en [!DNL Salesforce?]? {#what-will-this-look-like-in-salesforce}

[!DNL Marketo Measure] creará un solo punto de contacto de impresión en cualquier posible cliente que se haya expuesto al anuncio en pantalla. Podemos asignar al usuario incluso después de que llegue a su sitio web (FT) y rellene un formulario (LC). El punto de contacto contendrá información de la publicidad, como el nombre o ID de la campaña de publicidad, el ID de publicidad, el contenido del anuncio, el nombre o ID del sitio, el nombre o ID de ubicación, el canal de marketing, la ubicación geográfica, la página de referente, etc.

El modelo de atribución de visualizaciones dependerá del cliente y de sus datos.
