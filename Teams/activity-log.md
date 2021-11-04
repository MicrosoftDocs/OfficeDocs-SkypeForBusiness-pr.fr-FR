---
title: Afficher vos affectations de stratégie dans le journal d’activité du Centre Microsoft Teams’administration
author: serdars
ms.author: serdars
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment afficher vos activités d’affectation de stratégie dans le journal d’activité du Microsoft Teams d’administration.
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 21caf6d694c201b12527b4be3f33856b887d177b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743080"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Afficher vos affectations de stratégie dans le journal d’activité

Lorsque vous attribuez des stratégies à des utilisateurs dans le Microsoft Teams d’administration, vous pouvez afficher l’état de ces affectations de stratégie dans le journal d’activité. Le journal d’activité affiche les affectations de stratégie à des lots de plus de 20 utilisateurs via le Centre Microsoft Teams d’administration à partir des 30 derniers jours. Gardez à l’esprit que le journal d’activité n’affiche pas les affectations de packages de stratégie, les affectations de stratégie à des lots de moins de 20 utilisateurs via le Centre d’administration Microsoft Teams ou les affectations de stratégies via PowerShell.

![Capture d’écran de la page du journal d’activité.](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Afficher vos activités d’affectation de stratégie dans le journal d’activité

Pour afficher vos affectations de stratégie dans le journal d’activité :

1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, sélectionnez **Accueil,** puis sous Journal d’activité, sélectionnez Afficher les **détails.**
2. Vous pouvez afficher toutes les affectations de stratégie ou filtrer la liste par état pour afficher uniquement les affectations Non **commencées,** En **cours** ou **Terminées.** Vous verrez les informations suivantes sur chaque devoir :
    - **Nom**: nom de l’affectation de stratégie. Cliquez sur le lien pour afficher plus de détails. Cela inclut le nombre d’utilisateurs à qui la stratégie a été attribuée, ainsi que le nombre d’affectations terminées, en cours et non démarrées. Vous verrez également la liste des utilisateurs dans le lot, ainsi que l’état et le résultat pour chaque utilisateur. Voici un exemple :

        ![Capture d’écran du.](media/activity-log-policy-assignment-detail.png)

    - **Soumis**: Date et heure de soumettre l’affectation de stratégie.
    - **Heure d’achèvement**: date et heure d’achèvement de l’affectation de stratégie.
    - **Impact sur**: nombre d’utilisateurs du lot.
    - **État global**: état de l’affectation de stratégie.

> [!NOTE]
> Vous pouvez également ouvrir le journal d’activité à partir de la page **Utilisateurs.** Après avoir **cliqué sur Appliquer** pour envoyer une affectation de stratégie en bloc, une bannière s’affiche en haut de la page. Cliquez sur le **lien Journal d’activité** dans la bannière.

## <a name="related-topics"></a>Sujets associés

- [Attribuer des stratégies aux utilisateurs](policy-assignment-overview.md)
