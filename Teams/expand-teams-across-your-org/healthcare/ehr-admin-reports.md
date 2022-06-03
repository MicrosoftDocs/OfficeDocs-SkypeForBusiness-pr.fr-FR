---
title: Rapport des rendez-vous virtuels du connecteur EHR Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Découvrez comment utiliser le rapport rendez-vous virtuels du connecteur DSE Teams dans le Centre d’administration Microsoft Teams pour obtenir une vue d’ensemble de l’utilisation des rendez-vous virtuels intégrés à la DSE dans votre organisation.
ms.openlocfilehash: 0e78b89c934eac101b863bd7b5ba9957939f994b
ms.sourcegitcommit: cf2f2d23e6dcda0c03f22a5800a210a1c88e583f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "65883537"
---
# <a name="microsoft-teams-ehr-connector-virtual-appointments-report"></a>Rapport des rendez-vous virtuels du connecteur EHR Microsoft Teams

Le rapport des rendez-vous virtuels du connecteur Microsoft Teams Electronic Health Record (EHR) dans le Centre d’administration Microsoft Teams vous offre un moyen rapide et simple d’afficher l’utilisation des rendez-vous virtuels intégrés à la DSE Teams dans votre organisation.

Pour afficher le rapport, vous devez être administrateur général, administrateur Teams, lecteur général ou lecteur de rapport.

## <a name="view-the-report"></a>Afficher le rapport

Il existe deux façons d’accéder au rapport et de l’afficher dans le Centre d’administration Teams.

- Via la [carte d’utilisation du connecteur EHR](#the-ehr-connector-usage-card) dans le tableau de bord
- Directement en choisissant [**rendez-vous virtuels du connecteur EHR**](#the-teams-ehr-connector-virtual-appointments-report) dans **Analytics & rapports** > **d’utilisation**

### <a name="the-ehr-connector-usage-card"></a>Carte d’utilisation du connecteur EHR

Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, choisissez **Tableau de bord**, puis accédez à la carte **rendez-vous virtuels du connecteur EHR** .

Ici, vous obtenez une vue d’ensemble de l’activité de rendez-vous virtuels intégrés à la DSE Teams par mois, y compris les rendez-vous terminés, l’allocation restante et si vous avez dépassé la limite mensuelle (en fonction de la licence dont vous disposez).

:::image type="content" source="../../media/ehr-connector-report-card.png" alt-text="Capture d’écran de la carte d’utilisation du connecteur EHR dans le tableau de bord du Centre d’administration Teams." lightbox="../../media/ehr-connector-report-card.png":::

Choisissez **Afficher les détails** pour afficher les détails du rapport. Pour acheter plus de licences, **choisissez Acheter plus**.

### <a name="the-teams-ehr-connector-virtual-appointments-report"></a>Rapport des rendez-vous virtuels du connecteur DSE Teams

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Analytics & rapports** > **d’utilisation**.
1. Sous l’onglet **Afficher les rapports** , choisissez **Rendez-vous virtuels du connecteur EHR** et une plage de dates. Ensuite, sélectionnez **Exécuter le rapport**.

    :::image type="content" source="../../media/ehr-connector-report.png" alt-text="Capture d’écran du rapport rendez-vous virtuels du connecteur DSE Teams dans le Centre d’administration Teams." lightbox="../../media/ehr-connector-report.png":::

#### <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Chaque rapport affiche la date de génération du rapport et la plage de dates que vous avez choisie.|
|**2**   |Le tableau vous fournit des informations détaillées sur chaque rendez-vous qui a eu lieu pendant la plage de dates sélectionnée. N’oubliez pas que vous ne verrez pas d’entrées pour les rendez-vous auxquels un membre du personnel ou un patient n’a pas participé. <ul><li>**L’heure de début (UTC)** correspond à la date et à l’heure auxquelles un membre du personnel et un participant participent au rendez-vous.  </li> <li>**La durée** correspond à l’intervalle de temps entre l’heure de début et le moment où la dernière personne quitte le rendez-vous.</li> <li>**Le principal** est le nom de l’organisateur de la réunion. <li>**L’adresse e-mail du principal** est l’adresse e-mail de l’organisateur de la réunion.</li> <li> **Le ministère** est l’information du ministère pour la nomination. Si les informations ne s’affichent pas correctement, contactez votre équipe de support technique de DSE. Pour l’intégration à Epic, assurez-vous qu’il ```&departmentId=%PERFDEPID;;; ; ;;NONE;%``` fait partie de l’enregistrement d’intégration du fournisseur. </li></li> <li>**Les standards** sont le nombre total de membres du personnel et de participants au rendez-vous.</li> <li>**Dans la limite** indique si le rendez-vous est dans la limite d’allocation. </li> </ul> |
|**3**   |Vous pouvez exporter le rapport vers un fichier CSV pour une analyse hors connexion. Sélectionnez **Exporter vers Excel** pour télécharger le rapport. |
|**4**   |Sélectionnez **Filtrer** pour filtrer l’affichage des détails du rapport. |
|**5**   |Sélectionnez **Plein écran** pour afficher le rapport en mode plein écran. |
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau |

> [!NOTE]
> Pour plus d’analyses sur les rendez-vous virtuels intégrés à la DSE Teams, consultez le [rapport d’utilisation des visites virtuelles](../../teams-analytics-and-reports/virtual-visits-usage-report.md). Avec le rapport d’utilisation des visites virtuelles, vous pouvez afficher des métriques clés telles que le nombre total de rendez-vous, le temps d’attente de la salle d’attente, la durée du rendez-vous et aucun affichage. Utilisez ces informations pour obtenir des insights sur les tendances d’utilisation afin de vous aider à optimiser les rendez-vous virtuels pour obtenir de meilleurs résultats métier.

## <a name="related-articles"></a>Articles connexes

- [Rendez-vous virtuels avec Teams - Intégration à Cerner EHR](ehr-admin-cerner.md)
- [Rendez-vous virtuels avec Teams - Intégration à Epic EHR](ehr-admin.md) 
