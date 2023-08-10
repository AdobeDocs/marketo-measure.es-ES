---
unique-page-id: 18874556
description: "[!DNL Marketo Measure] Mantenimiento - [!DNL Marketo Measure] - Documentación del producto"
title: "[!DNL Marketo Measure] Mantenimiento"
exl-id: 4e1d53bb-0af8-4774-9f69-6a95516b3d11
feature: Tracking
source-git-commit: 3df1bd288ebd65f75a2ed52d7c8a6faf50c7ff1f
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 1%

---

# Mantenimiento de [!DNL Marketo Measure] {#marketo-measure-maintenance}

[!DNL Marketo Measure] extrae casi todo lo que necesita de su CRM diariamente, pero hay algunas tareas de mantenimiento que querrá programar regularmente para mantener [!DNL Marketo Measure] tarareando y enviando la información más precisa posible.

**Sincronizar puntos de contacto del comprador para nuevas campañas sin conexión (2 veces al mes)**

Como ha aprendido durante la incorporación, [!DNL Marketo Measure] obtiene información sobre sus esfuerzos de marketing sin conexión sincronizándolos con las campañas de su CRM. A medida que su organización inicie nuevas campañas, asegúrese de habilitar los puntos de contacto del comprador para cada campaña, según corresponda. Desproteger [este artículo](/help/channel-tracking-and-setup/offline-channels/deprecated-processes/syncing-offline-campaigns.md)para obtener más información.

**Gasto de carga para todos los canales (1 vez al mes)**

Para aprovechar las ventajas de las funciones completas de informes de ingresos y ROI para[!DNL Marketo Measure], tiene que decir [!DNL Marketo Measure] cuánto está gastando en cada uno de sus canales y subcanales de marketing. Se recomienda designar al propietario de cada canal o subcanal y hacer que esas personas informen del gasto a una sola parte responsable de cargar la nueva información de costes mensualmente.

Actualice la memoria sobre cómo cargar información de costes leyendo [este artículo](/help/marketing-spend/spend-management/marketing-channel-costs.md).

**Actualizar lista de dominios para rastrear (1 vez al mes)**

Marketo Measure realiza un seguimiento de todas las páginas y subdominios donde Javascript está activo, pero solo de los dominios que conocemos. Si ha debutado recientemente un nuevo dominio, se ha expandido internacionalmente o ha cambiado su dominio principal, póngase en contacto con [Asistencia de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} para asegurarnos de que actualizamos su cuenta en consecuencia.

**Revise la asignación de canales personalizados para comprobar su precisión (1 vez al mes).**

Durante la incorporación, puede configurar la asignación de canal personalizada para sus esfuerzos de marketing en línea y sin conexión. A medida que evolucione su estrategia de marketing y el uso de Marketo Measure, querrá estar atento a esa lógica de asignación para garantizar que todos sus puntos de contacto se clasifiquen correctamente.

Recuerde, [!DNL Marketo Measure] vuelve a procesar los datos al editar la lógica de asignación, por lo que no podrá cambiar estas reglas más de una vez cada 7 días.

Referencia [este artículo](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) para la configuración en línea, [este artículo](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md) para la configuración sin conexión y esta lista de prácticas recomendadas recopiladas de nuestros clientes:

* Revise los puntos de contacto que actualmente están cayendo en cualquier &quot;Otro&quot; o &quot;NULL&quot; canales que pueda haber configurado. Si procede, actualice la lógica de asignación para volver a clasificar esos puntos de contacto en canales más precisos.
* Revise los puntos de contacto que actualmente están entrando en sus canales directos. Si en algunas de las campañas de marketing por correo electrónico u otros esfuerzos faltan parámetros de UTM, es muy probable que el tráfico se esté agrupando de forma incorrecta en un canal directo. Considere la posibilidad de actualizar los parámetros de UTM para capturar la fuente de referencia.

**Evaluar la configuración de supresión de puntos de contacto (1x/trimestre)**

Si está viendo muchos puntos de contacto que preferiría que no se tuvieran en cuenta en la historia de atribución (de un [!DNL Login] o [!DNL Unsubscribe forms], una página Empleo o una aplicación interna, por ejemplo), es posible que desee evaluar la configuración de supresión de puntos de contacto existente. Una vez al trimestre, localice cualquier grupo de puntos de contacto que estén creando ruido innecesario y actualice correctamente la lógica de supresión. [Este es un artículo útil](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)  con los procedimientos.

**Revise la asignación de etapas personalizada para comprobar su precisión (1 x/trimestre) (si corresponde)**

Si utiliza cualquier personalizado de [!UICONTROL Posible cliente], [!UICONTROL Contacto], o [!UICONTROL Oportunidades] , también puede haber personalizado a qué parte de la canalización se asignan esas fases y si esas fases se incluyen o no en un modelo de atribución personalizado. Una vez al trimestre, visite [este artículo](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md) para actualizar la memoria en la asignación de etapas personalizada y asegurarse de que está realizando un seguimiento preciso de las etapas personalizadas.

**Compare el modelo de aprendizaje automático con la ponderación del modelo personalizado (1x/trimestre) (si corresponde)**

Si tiene licencia para el [!DNL Marketo Measure] Modelo personalizado, también tiene datos disponibles de nuestro Modelo de aprendizaje automático (MLM) en [!UICONTROL Configuración] > [!UICONTROL Configuración de atribución]. MLM calcula la importancia de cada fase utilizando los datos de punto de contacto de su cuenta y puede ayudarle a decidir cómo asignar el peso de atribución en el modelo personalizado. Recomendamos comparar el MLM con su modelo personalizado una vez al trimestre y discutir las implicaciones de posibles cambios en su modelo personalizado con su MSM.

Para obtener más información sobre [!DNL Marketo Measure] Modelo de aprendizaje automático, retirar [este artículo](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).
