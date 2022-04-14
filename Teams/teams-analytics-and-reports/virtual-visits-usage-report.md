---
title: Microsoft Teams rapport d’utilisation des visites virtuelles
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser le rapport d’utilisation des visites virtuelles dans le centre d’administration Microsoft Teams pour obtenir une vue d’ensemble de l’activité des rendez-vous virtuels dans votre organisation.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91f1aa8ff25b591305c8d5ca41485f7ceec9faca
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853215"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams rapport d’utilisation des visites virtuelles

Le rapport d’utilisation des visites virtuelles dans le centre d’administration Microsoft Teams vous donne une vue d’ensemble de Teams activité de rendez-vous virtuels dans votre organisation. Vous pouvez afficher l’activité détaillée des rendez-vous virtuels planifiés par le biais de [l’application Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md) et du [connecteur Microsoft Teams d’enregistrement d’intégrité électronique (EHR](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-appointments-and-electronic-healthcare-record-ehr-integration)).

Pour afficher le rapport, vous devez être administrateur général ou administrateur Teams.

Le rapport contient les onglets suivants. Les informations que vous verrez dans le rapport varient selon que vous disposez d’une licence pour l’application Bookings, le connecteur Teams EHR ou les deux.

|Onglet |Description  |
|---------|---------|
|**[Visites virtuelles](#virtual-visits)**     |Affiche le nombre total de rendez-vous virtuels, avec une répartition du nombre de rendez-vous planifiés à l’aide de l’application Bookings et Teams réunions intégrées à la DSE effectuées à partir de votre système de DSE.         |
|**[Durée](#duration)**     |Indique la durée moyenne des rendez-vous et le temps d’attente moyen des participants.         |
|**[Bookings](#bookings)**     |Affiche le nombre de rendez-vous planifiés via l’application Bookings.         |
|**[DSE](#ehr)**     |Affiche le nombre de rendez-vous intégrés à la DSE Teams effectués à partir de votre système de DSE.         |  

Utilisez ce rapport pour obtenir des informations sur l’activité et les tendances des rendez-vous virtuels dans votre organisation. Ces informations peuvent vous aider à optimiser les rendez-vous virtuels pour obtenir de meilleurs résultats opérationnels.

## <a name="view-the-virtual-visits-usage-report"></a>Afficher le rapport d’utilisation des visites virtuelles

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, choisissez **Analytics &** **reportsUsage** > . Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **Utilisation des visites virtuelles**.
2. Sous **Plage de dates**, sélectionnez une plage de dates de 7 jours, 30 jours ou 90 jours. Ensuite, choisissez **Exécuter le rapport**.

> [!NOTE]
> Par défaut, l’analytique des visites virtuelles est activée et le rapport est disponible. À l’aide de ce rapport, vous autorisez Microsoft à collecter des données sur les rendez-vous virtuels dans votre organisation. Pour plus d’informations sur nos stratégies de rétention des données, consultez [Conservation des données, suppression et destruction dans Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).
>
>Si vous souhaitez désactiver le rapport pour votre organisation, vous pouvez le faire dans **Paramètres** dans le coin supérieur droit de la page. Ce paramètre peut prendre entre 0 (zéro) et 2 heures après sa modification.

## <a name="interpret-the-report"></a>Interpréter le rapport

### <a name="virtual-visits"></a>Visites virtuelles

Les graphiques que vous verrez ici varient selon que vous disposez d’une licence pour l’application Bookings, le connecteur Teams DSE ou les deux. Pour plus d’informations, consultez [Gérer l’application Bookings](../bookings-app-admin.md) et [Intégration dans Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) ou [Intégration à Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="Capture d’écran de l’onglet Visites virtuelles du rapport d’utilisation des visites virtuelles montrant les légendes numérotées." lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|Légende |Description  |
|--------|-------------|
|**1**   |Chaque rapport a une date de génération du rapport. Les rapports reflètent généralement une latence de 24 à 48 heures à partir du moment de l’activité. |
|**2**   |L’axe X est la plage de dates sélectionnée pour le rapport. L’axe Y correspond au nombre de rendez-vous.<br>Pointez sur le point à une date donnée pour voir le nombre de rendez-vous à cette date.|
|**3**   |Vous pouvez filtrer ce que vous voyez sur le graphique en sélectionnant un élément dans la légende. Par exemple, sélectionnez **Total Bookings Visites virtuelles** ou **Nombre total de visites virtuelles ehr** pour afficher uniquement les informations relatives à chacune d’elles. La modification de cette sélection ne modifie pas les informations du tableau lui-même. |
|**4**   |Le tableau vous fournit des informations détaillées sur chaque rendez-vous qui a eu lieu pendant la plage de dates sélectionnée. <ul><li>**L’heure de début (UTC)** correspond à la date et à l’heure auxquelles un membre du personnel et un participant participent à la réunion ou lorsque la première activité s’est produite dans la réunion.  </li> <li>**L’ID de réunion** est l’ID unique de la réunion.</li> <li>**Le temps d’attente** de la salle d’attente est le délai entre le moment où un participant rejoint la salle d’attente pour la première fois et le moment où ce même participant ou un autre participant est admis à la réunion par un membre du personnel.</li><li>**La durée** correspond à l’intervalle de temps entre l’heure de début et le moment où la dernière personne quitte la réunion. Si un membre du personnel et un participant ne se sont pas joints à la réunion, la durée est égale à 0 (zéro).</li> <li>**L’état** indique l’état de la réunion. <ul><li>**Terminé** : Si un ou plusieurs membres du personnel et participants participent à la réunion et que la réunion est terminée. Ou, si un ou plusieurs participants rejoignent la réunion et que la réunion est terminée.</li> <li> **Aucun spectacle** : si un membre du personnel participe à la réunion mais qu’aucune autre personne n’y participe et que la réunion est terminée. </li></ul> </li> <li>**Le type de réunion** indique si le rendez-vous virtuel a été planifié via l’application Bookings ou le connecteur Teams DSE.</li> <li>**Les participants** sont le nombre total de membres du personnel et de participants à la réunion.</li> <li>**Les SMS envoyés** indiquent si une notification SMS a été envoyée aux participants. </li> </li> </ul> |
|**5**   |Sélectionnez **Paramètres** pour ouvrir le volet **Analytique des visites virtuelles**. À partir de là, vous pouvez désactiver ou activer la création de rapports de visites virtuelles pour votre organisation et ajouter ou supprimer des colonnes dans la table. Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**6**   |Vous pouvez exporter le rapport vers un fichier CSV pour une analyse hors connexion. Sélectionnez **Exporter pour Excel**, puis sous l’onglet **Téléchargements**, **choisissez Télécharger** pour télécharger le rapport lorsqu’il est prêt.|

### <a name="duration"></a>Durée

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="Capture d’écran de l’onglet Durée du rapport d’utilisation des visites virtuelles montrant les légendes numérotées." lightbox="../media/virtual-visits-usage-report-duration.png":::

|Légende |Description  |
|--------|-------------|
|**1**   |Chaque rapport a une date de génération du rapport. Les rapports reflètent généralement une latence de 24 à 48 heures à partir du moment de l’activité. |
|**2**   |L’axe X est la plage de dates sélectionnée pour le rapport. L’axe Y est le nombre de minutes.<br>Pointez sur le point à une date donnée pour voir la durée moyenne du rendez-vous ou le temps d’attente moyen de la salle d’attente pour une date donnée.  |
|**3**   |Vous pouvez filtrer ce que vous voyez sur le graphique en sélectionnant un élément dans la légende. Par exemple, sélectionnez **Durée moyenne de visite virtuelle** ou **Délai d’attente moyen de la salle d’attente** pour afficher uniquement les informations relatives à chacune d’elles. La modification de cette sélection ne modifie pas les informations du tableau lui-même. |
|**4**   |Le tableau vous fournit des informations détaillées sur chaque rendez-vous qui a eu lieu pendant la plage de dates sélectionnée. <ul><li>**L’heure de début (UTC)** correspond à la date et à l’heure auxquelles un membre du personnel et un participant participent à la réunion ou lorsque la première activité s’est produite dans la réunion.  </li> <li>**L’ID de réunion** est l’ID unique de la réunion.</li> <li>**Le temps d’attente** de la salle d’attente est le délai entre le moment où un participant rejoint la salle d’attente pour la première fois et le moment où ce même participant ou un autre participant est admis à la réunion par un membre du personnel.</li><li>**La durée** correspond à l’intervalle de temps entre l’heure de début et le moment où la dernière personne quitte la réunion. Si un membre du personnel et un participant ne se sont pas joints à la réunion, la durée est égale à 0 (zéro).</li> <li>**L’état** indique l’état de la réunion. <ul><li>**Terminé** : Si un ou plusieurs membres du personnel et participants participent à la réunion et que la réunion est terminée. Ou, si un ou plusieurs participants rejoignent la réunion et que la réunion est terminée.</li> <li> **Aucun spectacle** : si un membre du personnel participe à la réunion mais qu’aucune autre personne n’y participe et que la réunion est terminée. </li></ul> </li> <li>**Le type de réunion** indique si le rendez-vous virtuel a été planifié via l’application Bookings ou le connecteur Teams DSE.</li> <li>**Les participants** sont le nombre total de membres du personnel et de participants à la réunion.</li> <li>**Les SMS envoyés** indiquent si une notification SMS a été envoyée aux participants. </li> </li> </ul>|
|**5**   |Sélectionnez **Paramètres** pour ouvrir le volet **Analytique des visites virtuelles**. À partir de là, vous pouvez désactiver ou activer la création de rapports de visites virtuelles pour votre organisation et ajouter ou supprimer des colonnes dans la table. Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**6**   |Vous pouvez exporter le rapport vers un fichier CSV pour une analyse hors connexion. Sélectionnez **Exporter pour Excel**, puis sous l’onglet **Téléchargements**, **choisissez Télécharger** pour télécharger le rapport lorsqu’il est prêt.|
### <a name="bookings"></a>Bookings

Cet onglet s’affiche si vous disposez d’une licence qui inclut l’application Bookings. Pour plus d’informations, consultez [Gérer l’application Bookings](../bookings-app-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="Capture d’écran de l’onglet Bookings du rapport d’utilisation des visites virtuelles montrant les légendes numérotées." lightbox="../media/virtual-visits-usage-report-bookings.png":::

|Légende |Description  |
|--------|-------------|
|**1**   |Chaque rapport a une date de génération du rapport. Les rapports reflètent généralement une latence de 24 à 48 heures à partir du moment de l’activité. |
|**2**   |L’axe X est la plage de dates sélectionnée pour le rapport. L’axe Y est le nombre de rendez-vous Bookings.<br>Pointez sur le point à une date donnée pour voir le nombre de rendez-vous Bookings qui se sont produits à cette date.|
|**3**   |Le tableau vous fournit des informations détaillées sur chaque rendez-vous qui a eu lieu pendant la plage de dates sélectionnée. <ul><li>**L’heure de début (UTC)** correspond à la date et à l’heure auxquelles un membre du personnel et un participant participent à la réunion ou lorsque la première activité s’est produite dans la réunion.  </li> <li>**L’ID de réunion** est l’ID unique de la réunion.</li> <li>**Le temps d’attente** de la salle d’attente est le délai entre le moment où un participant rejoint la salle d’attente pour la première fois et le moment où ce même participant ou un autre participant est admis à la réunion par un membre du personnel.</li><li>**La durée** correspond à l’intervalle de temps entre l’heure de début et le moment où la dernière personne quitte la réunion. Si un membre du personnel et un participant ne se sont pas joints à la réunion, la durée est égale à 0 (zéro).</li> <li>**L’état** indique l’état de la réunion. <ul><li>**Terminé** : Si un ou plusieurs membres du personnel et participants participent à la réunion et que la réunion est terminée. Ou, si un ou plusieurs participants rejoignent la réunion et que la réunion est terminée.</li> <li> **Aucun spectacle** : si un membre du personnel participe à la réunion mais qu’aucune autre personne n’y participe et que la réunion est terminée. </li></ul> </li> <li>**Le type de réunion** indique si le rendez-vous virtuel a été planifié via l’application Bookings ou le connecteur Teams DSE.</li> <li>**Les participants** sont le nombre total de membres du personnel et de participants à la réunion.</li> <li>**Les SMS envoyés** indiquent si une notification SMS a été envoyée aux participants. </li> </li> </ul>|
|**4**   |Sélectionnez **Paramètres** pour ouvrir le volet **Analytique des visites virtuelles**. À partir de là, vous pouvez désactiver ou activer la création de rapports de visites virtuelles pour votre organisation et ajouter ou supprimer des colonnes dans la table. Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**5**   |Vous pouvez exporter le rapport vers un fichier CSV pour une analyse hors connexion. Sélectionnez **Exporter pour Excel**, puis sous l’onglet **Téléchargements**, **choisissez Télécharger** pour télécharger le rapport lorsqu’il est prêt.|
### <a name="ehr"></a>DSE

Cet onglet s’affiche si vous disposez d’une licence qui inclut le connecteur Teams DSE. Pour plus d’informations, consultez [Intégration dans Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) ou [Intégration à Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="Capture d’écran de l’onglet DSE du rapport d’utilisation des visites virtuelles montrant les légendes numérotées." lightbox="../media/virtual-visits-usage-report-ehr.png":::

|Légende |Description  |
|--------|-------------|
|**1**   |Chaque rapport a une date de génération du rapport. Les rapports reflètent généralement une latence de 24 à 48 heures à partir du moment de l’activité. |
|**2**   |L’axe X est la plage de dates sélectionnée pour le rapport. L’axe Y correspond au nombre de rendez-vous DSE.<br>Pointez sur le point à une date donnée pour voir le nombre de rendez-vous DSE à cette date.|
|**3**   |Le tableau vous fournit des informations détaillées sur chaque rendez-vous qui a eu lieu pendant la plage de dates sélectionnée. <ul><li>**L’heure de début (UTC)** correspond à la date et à l’heure auxquelles un membre du personnel et un participant participent à la réunion ou lorsque la première activité s’est produite dans la réunion.  </li> <li>**L’ID de réunion** est l’ID unique de la réunion.</li> <li>**Le temps d’attente** de la salle d’attente est le délai entre le moment où un participant rejoint la salle d’attente pour la première fois et le moment où ce même participant ou un autre participant est admis à la réunion par un membre du personnel.</li><li>**La durée** correspond à l’intervalle de temps entre l’heure de début et le moment où la dernière personne quitte la réunion. Si un membre du personnel et un participant ne se sont pas joints à la réunion, la durée est égale à 0 (zéro).</li> <li>**L’état** indique l’état de la réunion. <ul><li>**Terminé** : Si un ou plusieurs membres du personnel et participants participent à la réunion et que la réunion est terminée. Ou, si un ou plusieurs participants rejoignent la réunion et que la réunion est terminée.</li> <li> **Aucun spectacle** : si un membre du personnel participe à la réunion mais qu’aucune autre personne n’y participe et que la réunion est terminée. </li></ul> </li> <li>**Le type de réunion** indique si le rendez-vous virtuel a été planifié via l’application Bookings ou le connecteur Teams DSE.</li> <li>**Les participants** sont le nombre total de membres du personnel et de participants à la réunion.</li> <li>**Les SMS envoyés** indiquent si une notification SMS a été envoyée aux participants. </li> </li> </ul>|
|**4**   |Sélectionnez **Paramètres** pour ouvrir le volet **Analytique des visites virtuelles**. À partir de là, vous pouvez désactiver ou activer la création de rapports de visites virtuelles pour votre organisation et ajouter ou supprimer des colonnes dans la table. Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**5**   |Vous pouvez exporter le rapport vers un fichier CSV pour une analyse hors connexion. Sélectionnez **Exporter pour Excel**, puis sous l’onglet **Téléchargements**, **choisissez Télécharger** pour télécharger le rapport lorsqu’il est prêt.|

> [!NOTE]
> Si votre organisation souhaite participer à la préversion privée pour que les utilisateurs non administrateurs, tels que les décideurs d’entreprise, aient accès à ce rapport et l’affichent, [contactez-nous](mailto:tapmwtanalytics@microsoft.com).

## <a name="related-articles"></a>Articles connexes

- [Analyses et rapports Teams](teams-reporting-reference.md)
- [Rendez-vous virtuels avec Teams et l’application Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [Rendez-vous virtuels avec Teams - Intégration à Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [Rendez-vous virtuels avec Teams - Intégration à Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
