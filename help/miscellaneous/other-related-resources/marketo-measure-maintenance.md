---
unique-page-id: 18874556
description: '[!DNL Marketo Measure] mantenimiento - [!DNL Marketo Measure]'
title: Mantenimiento de [!DNL Marketo Measure]
exl-id: 4e1d53bb-0af8-4774-9f69-6a95516b3d11
feature: Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 95%

---

# Mantenimiento de [!DNL Marketo Measure] {#marketo-measure-maintenance}

[!DNL Marketo Measure] extrae casi todo lo que necesita de su CRM diariamente, pero hay algunas tareas de mantenimiento que debe programar regularmente para mantener [!DNL Marketo Measure] funcionando y enviando la información más precisa posible.

**Sincronizar Buyer Touchpoints para nuevas campañas sin conexión (2 veces al mes)**

Como ha aprendido durante la incorporación, [!DNL Marketo Measure] obtiene información sobre sus esfuerzos de marketing sin conexión sincronizándolos con las campañas de su CRM. A medida que su organización inicie nuevas campañas, asegúrese de habilitar los Buyer Touchpoints para cada campaña, según corresponda.

**Cargue el gasto para todos los canales (1 vez al mes)**

Para aprovechar las ventajas de las funciones completas de informes de ingresos y ROI para[!DNL Marketo Measure], debe saber [!DNL Marketo Measure] cuánto está gastando en cada uno de sus canales y subcanales de marketing. Designe al propietario de cada canal o subcanal y haga que esas personas informen sobre los gastos a una sola parte responsable de cargar la nueva información de costes mensualmente.

Actualice la memoria sobre cómo cargar información de costes leyendo [este artículo](/help/marketing-spend/spend-management/marketing-channel-costs.md).

**Actualice la lista de dominios para rastrear (una vez al mes)**

Marketo Measure realiza un seguimiento de todas las páginas y subdominios donde Javascript está activo, pero solo de los dominios que conocemos. Si recientemente ha debutado un nuevo dominio, se ha expandido internacionalmente o ha cambiado su dominio principal, comuníquese con el [Soporte técnico de Marketo](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} para asegurarse de que actualizamos su cuenta en consecuencia.

**Revise la asignación de canales personalizados para comprobar su precisión (una vez al mes).**

Durante la incorporación, puede configurar la asignación de canales personalizados para sus esfuerzos de marketing en línea y sin conexión. A medida que evoluciona su estrategia de marketing y el uso de Marketo Measure, debe prestar atención a esa lógica de asignación para garantizar que todos sus puntos de contacto se clasifiquen correctamente.

Recuerde, [!DNL Marketo Measure] vuelve a procesar los datos al editar la lógica de asignación, por lo que no podrá cambiar estas reglas más de una vez cada siete días.

Haga referencia a [este artículo](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) para la configuración en línea, a [este artículo](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md) para la configuración sin conexión y a la siguiente lista de prácticas recomendadas recopiladas de nuestros clientes:

* Revise los Touchpoints que se encuentran actualmente en los canales “Other” o “NULL” que haya configurado. Si procede, actualice la lógica de asignación para reclasificar estos Touchpoints en canales más precisos.
* Revise los Touchpoints que actualmente pertenecen a sus canales directos. Si en algunas de las campañas de marketing por correo electrónico u otros esfuerzos faltan parámetros de UTM, es muy probable que el tráfico se esté agrupando de forma incorrecta en un canal directo. Considere la posibilidad de actualizar los parámetros de UTM para capturar la fuente de referencia.

**Evalúe la configuración de supresión de Touchpoints (1x/trimestre)**

Si está viendo muchos Touchpoints que preferiría que no se tuvieran en cuenta en la historia de atribución (de un [!DNL Login] o [!DNL Unsubscribe forms], una página Empleo o una aplicación interna, por ejemplo), es posible que desee evaluar la configuración de supresión de Touchpoints existente. Una vez al trimestre, localice cualquier grupo de Touchpoints que estén creando ruido innecesario y actualice correctamente la lógica de supresión. [Este es un artículo útil](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)  con los procedimientos.

**Revise la asignación de etapas personalizada para comprobar su precisión (1 x/trimestre) (si corresponde)**

Si utiliza fases personalizadas de [!UICONTROL Cliente potencial], [!UICONTROL Contacto] u [!UICONTROL Oportunidades], también puede haber personalizado a qué parte de la canalización se asignan esas fases y si esas fases se incluyen en un modelo de atribución personalizado. Una vez al trimestre, visite [este artículo](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md) para actualizar la memoria sobre la asignación de etapas personalizada y asegurarse de que realiza un seguimiento preciso de las etapas personalizadas.

**Compare el modelo de aprendizaje automático con la ponderación del modelo personalizado (1x/trimestre) (si corresponde)**

Si tiene licencia para el [!DNL Marketo Measure]Modelo personalizado, también tiene datos disponibles de nuestro Modelo de aprendizaje automático (MLM) en [!UICONTROL Configuración] > [!UICONTROL Configuración de atribución]. MLM calcula la importancia de cada fase utilizando los datos de Touchpoint de su cuenta y puede ayudarle a decidir cómo asignar el peso de atribución en el modelo personalizado. Recomendamos comparar el MLM con su modelo personalizado una vez al trimestre y discutir las implicaciones de posibles cambios en su modelo personalizado con su MSM.

Para obtener más información sobre el [!DNL Marketo Measure] Modelo de aprendizaje automático, compruebe [este artículo](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).
