---
title: Microsoft Teams utilisation des visites virtuelles
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
description: Découvrez comment utiliser le rapport Utilisation des visites virtuelles dans le Centre Microsoft Teams d’administration pour avoir une vue d’ensemble de l’activité des visites virtuelles dans votre organisation.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b3432ea92ad89c5304d81b266fce61fb9b95d5b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435848"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams utilisation des visites virtuelles

Le rapport utilisation des visites virtuelles dans le centre Microsoft Teams d’administration vous donne une vue d’ensemble de Teams de l’activité de visites virtuelles dans votre organisation. Vous pouvez afficher l’activité détaillée des rendez-vous virtuels [programmés](../expand-teams-across-your-org/bookings-virtual-visits.md) via l’application Bookings et le connecteur Microsoft Teams dossier médicaux [électronique (EHR](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-visits-and-electronic-healthcare-record-ehr-integration)).

Pour afficher le rapport, vous devez être administrateur global ou Teams administrateur.

Le rapport contient les onglets suivants. Les informations que vous verrez dans le rapport varient selon que vous avez une licence pour l’application Bookings, le connecteur Teams EHR ou les deux.

|Tabulation |Description  |
|---------|---------|
|**[Visites virtuelles](#virtual-visits)**     |Affiche le nombre total de visites virtuelles, avec une répartition du nombre de visites prévues à l’aide de l’application Bookings et des réunions intégrées Teams EHR réalisées à partir de votre système EHR.         |
|**[Durée](#duration)**     |Affiche la durée moyenne des visites et le temps d’attente moyen des participants dans la salle d’attente.         |
|**[Bookings](#bookings)**     |Affiche le nombre de visites prévues via l’application Bookings.         |
|**[EHR](#ehr)**     |Indique le nombre de visites Teams intégrées par ehr effectuées à partir de votre système EHR.         |  

Utilisez ce rapport pour obtenir des informations sur l’activité des visites virtuelles et les tendances de votre organisation. Ces informations peuvent vous aider à optimiser les visites virtuelles pour optimiser les résultats d’entreprise.

## <a name="view-the-virtual-visits-usage-report"></a>Afficher le rapport utilisation des visites virtuelles

1. Dans la barre de navigation gauche du Microsoft Teams d’administration, sélectionnez **Analyse de & rapports** >  **d’utilisation des rapports**. Sous **l’onglet Afficher les rapports** , sous **Rapport**, sélectionnez **Utilisation des visites virtuelles**.
2. Sous **Plage de dates**, sélectionnez une plage de dates de 7 jours, 30 jours ou 90 jours. Sélectionnez ensuite **Exécuter le rapport**.

> [!NOTE]
> Par défaut, l’analyse des visites virtuelles est en cours et le rapport est disponible. En utilisant ce rapport, vous autorisez Microsoft à collecter des données sur les visites virtuelles dans votre organisation. Pour plus d’informations sur nos stratégies de rétention des données, voir Rétention[, suppression et destruction des données dans Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).
>
>Si vous voulez désactiver le rapport pour votre organisation, vous pouvez le faire dans Paramètres coin  supérieur droit de la page. L’application de ce paramètre peut prendre de 0 (zéro) à 2 heures.

## <a name="interpret-the-report"></a>Interpréter le rapport

### <a name="virtual-visits"></a>Visites virtuelles

Les graphiques qui s’afficheront ici varient selon que vous avez une licence pour l’application Bookings, le Teams EHR ou les deux. Pour plus d’informations, voir Gérer l’application [Bookings](../bookings-app-admin.md) et [l’intégration dans Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) ou [Intégration à Ehr Android](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="Capture d’écran de l’onglet Visites virtuelles du rapport d’utilisation des visites virtuelles montrant des appels numéroés." lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|Légende |Description  |
|--------|-------------|
|**1**   |Chaque rapport indique la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**2**   |L’axe X est la plage de dates sélectionnée pour le rapport. L’axe Y est le nombre de visites.<br>Pointez sur le point à une date donnée pour voir le nombre de visites à cette date.|
|**3**   |Vous pouvez filtrer ce que vous voyez sur le graphique en sélectionnant un élément dans la légende. Par exemple, sélectionnez **Total Bookings Virtual Visits** ou **Total EHR Virtual Visits** pour voir uniquement les informations relatives à chacune de ces visites. La modification de cette sélection ne modifie pas les informations du tableau lui-même. |
|**4**   |Le tableau vous donne des informations détaillées sur chaque visite qui a eu lieu pendant la plage de dates sélectionnée. <ul><li>**L’heure de début (UTC)** est la date et l’heure à laquelle un membre du personnel et un participant participent à la réunion, ou la première activité qui s’est produite au cours de la réunion.  </li> <li>**L’ID de** réunion est l’ID unique de la réunion.</li> <li>**Le temps d’attente** dans la salle d’attente est le délai entre la première fois qu’un participant rejoint la salle d’attente et à quel moment ce même participant ou un autre participant est admis à la réunion par un membre du personnel enseignant.</li><li>**La durée** est la différence de temps entre l’heure de début et la dernière personne qui quitte la réunion. Si un membre du personnel et un participant n’ont pas rejoint la réunion, la durée indique 0 (zéro).</li> <li>**Le statut** affiche le statut de la réunion. <ul><li>**Terminé :** Si un ou plusieurs membres du personnel et participants rejoignent la réunion et que la réunion est terminée. Ou, si un ou plusieurs participants rejoignent la réunion et que celle-ci est terminée.</li> <li> **Aucun show** : si un membre du personnel rejoint la réunion mais aucune autre personne ne la rejoint et que la réunion est terminée. </li></ul> </li> <li>**Le type de** réunion indique si le rendez-vous virtuel a été programmé via l’application Bookings ou Teams connecteur EHR.</li> <li>**Les participants sont** le nombre total de membres du personnel et de participants à la réunion.</li> <li>**Le SMS envoyé** indique si une notification SMS a été envoyée aux participants. </li> </li> </ul> |
|**5**   |**Sélectionnez Paramètres** pour ouvrir le volet **d’analyse Visites virtuelles**. À partir de là, vous pouvez désactiver ou activer les rapports de visites virtuelles pour votre organisation et ajouter ou supprimer des colonnes dans la table. Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**6**   |Vous pouvez exporter le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion. **Sélectionnez Exporter vers Excel**, puis sous l’onglet **Téléchargements**, sélectionnez Télécharger  pour télécharger le rapport lorsqu’il est prêt.|

### <a name="duration"></a>Durée

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="Capture d’écran de l’onglet Durée du rapport Utilisation des visites virtuelles montrant des appels numéroés." lightbox="../media/virtual-visits-usage-report-duration.png":::

|Légende |Description  |
|--------|-------------|
|**1**   |Chaque rapport indique la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**2**   |L’axe X est la plage de dates sélectionnée pour le rapport. L’axe Y est le nombre de minutes.<br>Pointez sur le point sur une date donnée pour voir la durée moyenne d’une visite ou le temps d’attente moyen d’une salle d’attente pour une date donnée.  |
|**3**   |Vous pouvez filtrer ce que vous voyez sur le graphique en sélectionnant un élément dans la légende. Par exemple, sélectionnez **Durée de la visite virtuelle** moyenne ou **Attente moyenne d’attente** pour voir uniquement les informations relatives à chacune de ces activités. La modification de cette sélection ne modifie pas les informations du tableau lui-même. |
|**4**   |Le tableau vous donne des informations détaillées sur chaque visite qui a eu lieu pendant la plage de dates sélectionnée. <ul><li>**L’heure de début (UTC)** est la date et l’heure à laquelle un membre du personnel et un participant participent à la réunion, ou la première activité qui s’est produite au cours de la réunion.  </li> <li>**L’ID de** réunion est l’ID unique de la réunion.</li> <li>**Le temps d’attente** dans la salle d’attente est le délai entre la première fois qu’un participant rejoint la salle d’attente et à quel moment ce même participant ou un autre participant est admis à la réunion par un membre du personnel enseignant.</li><li>**La durée** est la différence de temps entre l’heure de début et la dernière personne qui quitte la réunion. Si un membre du personnel et un participant n’ont pas rejoint la réunion, la durée indique 0 (zéro).</li> <li>**Le statut** affiche le statut de la réunion. <ul><li>**Terminé :** Si un ou plusieurs membres du personnel et participants rejoignent la réunion et que la réunion est terminée. Ou, si un ou plusieurs participants rejoignent la réunion et que celle-ci est terminée.</li> <li> **Aucun show** : si un membre du personnel rejoint la réunion mais aucune autre personne ne la rejoint et que la réunion est terminée. </li></ul> </li> <li>**Le type de** réunion indique si le rendez-vous virtuel a été programmé via l’application Bookings ou Teams connecteur EHR.</li> <li>**Les participants sont** le nombre total de membres du personnel et de participants à la réunion.</li> <li>**Le SMS envoyé** indique si une notification SMS a été envoyée aux participants. </li> </li> </ul>|
|**5**   |**Sélectionnez Paramètres** pour ouvrir le volet **d’analyse Visites virtuelles**. À partir de là, vous pouvez désactiver ou activer les rapports de visites virtuelles pour votre organisation et ajouter ou supprimer des colonnes dans la table. Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**6**   |Vous pouvez exporter le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion. **Sélectionnez Exporter vers Excel**, puis sous l’onglet **Téléchargements**, sélectionnez Télécharger  pour télécharger le rapport lorsqu’il est prêt.|
### <a name="bookings"></a>Bookings

Cet onglet s’inclut si vous avez une licence qui inclut l’application Bookings. Pour en savoir plus, [voir Gérer l’application Bookings](../bookings-app-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="Capture d’écran de l’onglet Bookings du rapport d’utilisation des visites virtuelles affichant des appels numéroés." lightbox="../media/virtual-visits-usage-report-bookings.png":::

|Légende |Description  |
|--------|-------------|
|**1**   |Chaque rapport indique la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**2**   |L’axe X est la plage de dates sélectionnée pour le rapport. L’axe Y est le nombre de visites sur Bookings.<br>Pointez sur le point sur une date donnée pour voir le nombre de visites sur Bookings à cette date.|
|**3**   |Le tableau vous donne des informations détaillées sur chaque visite qui a eu lieu pendant la plage de dates sélectionnée. <ul><li>**L’heure de début (UTC)** est la date et l’heure à laquelle un membre du personnel et un participant participent à la réunion, ou la première activité qui s’est produite au cours de la réunion.  </li> <li>**L’ID de** réunion est l’ID unique de la réunion.</li> <li>**Le temps d’attente** dans la salle d’attente est le délai entre la première fois qu’un participant rejoint la salle d’attente et à quel moment ce même participant ou un autre participant est admis à la réunion par un membre du personnel enseignant.</li><li>**La durée** est la différence de temps entre l’heure de début et la dernière personne qui quitte la réunion. Si un membre du personnel et un participant n’ont pas rejoint la réunion, la durée indique 0 (zéro).</li> <li>**Le statut** affiche le statut de la réunion. <ul><li>**Terminé :** Si un ou plusieurs membres du personnel et participants rejoignent la réunion et que la réunion est terminée. Ou, si un ou plusieurs participants rejoignent la réunion et que celle-ci est terminée.</li> <li> **Aucun show** : si un membre du personnel rejoint la réunion mais aucune autre personne ne la rejoint et que la réunion est terminée. </li></ul> </li> <li>**Le type de** réunion indique si le rendez-vous virtuel a été programmé via l’application Bookings ou Teams connecteur EHR.</li> <li>**Les participants sont** le nombre total de membres du personnel et de participants à la réunion.</li> <li>**Le SMS envoyé** indique si une notification SMS a été envoyée aux participants. </li> </li> </ul>|
|**4**   |**Sélectionnez Paramètres** pour ouvrir le volet **d’analyse Visites virtuelles**. À partir de là, vous pouvez désactiver ou activer les rapports de visites virtuelles pour votre organisation et ajouter ou supprimer des colonnes dans la table. Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**5**   |Vous pouvez exporter le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion. **Sélectionnez Exporter vers Excel**, puis sous l’onglet **Téléchargements**, sélectionnez Télécharger  pour télécharger le rapport lorsqu’il est prêt.|
### <a name="ehr"></a>EHR

Cet onglet s’inclut si vous avez une licence qui Teams connecteur EHR. Pour plus d’informations, voir [Intégration à Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) [ou Intégration dans ehrhienne](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="Capture d’écran de l’onglet EHR du rapport d’utilisation des visites virtuelles montrant des appels numéroés." lightbox="../media/virtual-visits-usage-report-ehr.png":::

|Légende |Description  |
|--------|-------------|
|**1**   |Chaque rapport indique la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**2**   |L’axe X est la plage de dates sélectionnée pour le rapport. L’axe Y est le nombre de visites par ehr.<br>Pointez sur le point à une date donnée pour voir le nombre de visites par ehr à cette date.|
|**3**   |Le tableau vous donne des informations détaillées sur chaque visite qui a eu lieu pendant la plage de dates sélectionnée. <ul><li>**L’heure de début (UTC)** est la date et l’heure à laquelle un membre du personnel et un participant participent à la réunion, ou la première activité qui s’est produite au cours de la réunion.  </li> <li>**L’ID de** réunion est l’ID unique de la réunion.</li> <li>**Le temps d’attente** dans la salle d’attente est le délai entre la première fois qu’un participant rejoint la salle d’attente et à quel moment ce même participant ou un autre participant est admis à la réunion par un membre du personnel enseignant.</li><li>**La durée** est la différence de temps entre l’heure de début et la dernière personne qui quitte la réunion. Si un membre du personnel et un participant n’ont pas rejoint la réunion, la durée indique 0 (zéro).</li> <li>**Le statut** affiche le statut de la réunion. <ul><li>**Terminé :** Si un ou plusieurs membres du personnel et participants rejoignent la réunion et que la réunion est terminée. Ou, si un ou plusieurs participants rejoignent la réunion et que celle-ci est terminée.</li> <li> **Aucun show** : si un membre du personnel rejoint la réunion mais aucune autre personne ne la rejoint et que la réunion est terminée. </li></ul> </li> <li>**Le type de** réunion indique si le rendez-vous virtuel a été programmé via l’application Bookings ou Teams connecteur EHR.</li> <li>**Les participants sont** le nombre total de membres du personnel et de participants à la réunion.</li> <li>**Le SMS envoyé** indique si une notification SMS a été envoyée aux participants. </li> </li> </ul>|
|**4**   |**Sélectionnez Paramètres** pour ouvrir le volet **d’analyse Visites virtuelles**. À partir de là, vous pouvez désactiver ou activer les rapports de visites virtuelles pour votre organisation et ajouter ou supprimer des colonnes dans la table. Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.|
|**5**   |Vous pouvez exporter le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion. **Sélectionnez Exporter vers Excel**, puis sous l’onglet **Téléchargements**, sélectionnez Télécharger  pour télécharger le rapport lorsqu’il est prêt.|

> [!NOTE]
> Si votre organisation souhaite participer à la prévisualisation privée pour que les utilisateurs non administrateurs, tels que les décideurs d’entreprise, peuvent accéder à ce rapport et le [consulter](mailto:tapmwtanalytics@microsoft.com), adressez-nous.

## <a name="related-articles"></a>Articles connexes

- [Analyses et rapports Teams](teams-reporting-reference.md)
- [Visites virtuelles avec Teams et l’application Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [Visites virtuelles avec Teams - Intégration à EhRExique](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [Visites virtuelles avec des Teams - Intégration à l’intégration à l’intégration EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
