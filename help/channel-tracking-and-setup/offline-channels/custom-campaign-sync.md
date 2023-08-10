---
unique-page-id: 18874588
description: Sincronización de campaña personalizada - [!DNL Marketo Measure] - Documentación del producto
title: Sincronización de campañas personalizadas
exl-id: 66f0e4e3-c1b6-443e-8ffa-06b67862b855
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---

# Sincronización de campañas personalizadas {#custom-campaign-sync}

Hoy, con el instalado [!DNL Marketo Measure] , puede indicar qué campañas incluir como punto de contacto apto. Existen múltiples obstáculos a esto, tal como existía anteriormente. Una vez que [!DNL Marketo Measure] está instalado en el CRM, puede tardar un tiempo en ser aprobado por el equipo de seguridad. Además, no hay flexibilidad para utilizar una sola lista de selección en el objeto de campaña. Con esta nueva función, no es necesario instalar el paquete para empezar a utilizar los registros de Campaign y de los miembros de Campaign. Se pueden crear reglas para definir exactamente qué registros se pueden crear para definir exactamente qué registros son aptos.

## Requisitos {#requirements}

* La sincronización de campañas está disponible en todos los niveles
* Para importar datos, sigue siendo necesario conectar el CRM a su [!DNL Marketo Measure] account

## Cómo funciona {#how-it-works}

1. Con los permisos de AccountAdmin, puede navegar a **[!UICONTROL Configuración]** > **[!UICONTROL Campañas]** y consulte la interfaz de usuario Sincronizar reglas de miembros de Campaign.
1. Haga clic en **+** para empezar a crear una regla.

   ![](assets/1-1.png)

1. Tiene la opción de crear una regla desde [!UICONTROL Campaign] o [!UICONTROL Miembro de campaña] campos. Complete el resto de la regla con el Operador y el Valor que se espera validar. En el ejemplo siguiente, se busca una campaña específica por su nombre.

   ![](assets/2-1.png)

   >[!NOTE]
   >
   >Los campos de fórmula no se pueden utilizar dentro de las reglas y no aparecerán en la lista de selección. Como las fórmulas calculan en segundo plano y no modifican un registro, [!DNL Marketo Measure] no puede detectar si un registro se ajusta o no a una regla.

1. Elija la Fecha de punto de contacto. La lista de fechas posibles aparecerá después de introducir un corchete `{` : a continuación, puede seleccionar la fecha que desee aplicar a todos los puntos de contacto creados a partir de la regla.

   ![](assets/3-1.png)

   >[!NOTE]
   >
   >Si utiliza reglas de sincronización de campaña personalizadas, [!DNL Marketo Measure] no leerá ninguna actualización que haya realizado con el botón Actualización masiva de fecha de punto de contacto.

1. Haga clic en la marca de verificación y luego agregue reglas adicionales para campañas adicionales según sea necesario.

   ![](assets/4-1.png)

   >[!NOTE]
   >
   >Ahora que las reglas se definen junto con la sincronización de CRM, las reglas establecidas empezarán a entrar en conflicto de forma natural. Si elige seguir utilizando la sincronización de campaña personalizada _y_ En el Tipo de sincronización de CRM, es fundamental crear reglas para que los Tipos de sincronización de CRM no se ignoren.

   ![](assets/5-1.png)

   >[!NOTE]
   >
   >Si está considerando la posibilidad de detener finalmente al usuario de [!UICONTROL Tipo de sincronización CRM], es ideal crear reglas que no hagan referencia al &quot;Tipo de sincronización&quot;, pero _fijo_ mantener los puntos de contacto actuales de CRM. De esa manera las reglas aún funcionan si/cuando se realiza ese cambio.

Este es un ejemplo de cómo sería, para que no se pierdan los puntos de contacto de CRM existentes:

## Validación {#validation}

Puede comprobar fácilmente los puntos de contacto del comprador y los registros de puntos de contacto de atribución del comprador dentro de la campaña para asegurarse de que las reglas funcionan correctamente. Aquí hay un MURCIÉLAGO que [!DNL Marketo Measure] creado con la fecha de punto de contacto dinámica adecuada, extraído de la campaña. El campo Fecha de creación está en la imagen inferior.

![](assets/6-1.png)

## Pruebas {#testing}

1. La función Campaign Sync viene con una función de prueba para que pueda comprobar si las reglas que ha creado se ajustan realmente a los criterios de Campaign. Para empezar, haga clic en [!UICONTROL Prueba] botón. Las reglas deben guardarse primero para poder iniciar la prueba.

   ![](assets/7-1.png)

   Aparecerá una ventana emergente en la que puede introducir un ID de campaña (15 o 18 caracteres desde CRM) para probar. El punto es introducir el ID de campaña desde el CRM que intentaba sincronizar para asegurarse de que coincida con la regla creada.

   ![](assets/8-1.png)

1. Después de hacer clic en [!UICONTROL Prueba], verá el nombre de la campaña y el número de miembros de la campaña aptos para los puntos de contacto. A continuación aparece una tabla con todas las reglas que coinciden con su ID de campaña. Solo aparecerán las coincidencias.

   ![](assets/9.png)

1. También puede hacer clic en el recuento de miembros para ver una lista de los posibles clientes y contactos y sus ID que forman parte de la idoneidad para la regla de Campaign. Este es solo un conjunto de muestras y mostrará hasta 50 para que pueda tener una idea de qué registros cumplen los requisitos.

   ![](assets/10.png)
