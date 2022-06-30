---
title: Afficher vos affectations de stratégie dans le journal d’activité du Centre d’administration Microsoft Teams
ms.author: mabond
author: mkbond007
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment afficher vos activités d’affectation de stratégie dans le journal d’activité du Centre d’administration Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8243d60a2aca31a8b9158b922126c7c80a486eb
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562213"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Afficher vos affectations de stratégie dans le journal d’activité

Lorsque vous attribuez des stratégies aux utilisateurs dans le Centre d’administration Microsoft Teams, vous pouvez afficher l’état de ces affectations de stratégie dans le journal d’activité. Le journal d’activité affiche les affectations de stratégie à des lots de plus de 20 utilisateurs via le Centre d’administration Microsoft Teams au cours des 30 derniers jours. N’oubliez pas que le journal d’activité n’affiche pas les affectations de package de stratégie, les affectations de stratégie à des lots de moins de 20 utilisateurs via le Centre d’administration Microsoft Teams ou les affectations de stratégies via PowerShell.

![Capture d’écran de la page du journal d’activité.](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Afficher vos activités d’affectation de stratégie dans le journal d’activité

Pour afficher vos affectations de stratégie dans le journal d’activité :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Accueil**, puis sous **Journal d’activité**, sélectionnez **Afficher les détails**.
2. Vous pouvez afficher toutes les affectations de stratégie ou filtrer la liste par état pour afficher uniquement les affectations qui **ne sont pas démarrées**, **en cours** ou **terminées**. Vous verrez les informations suivantes sur chaque affectation :
    - **Nom** : nom de l’affectation de stratégie. Cliquez sur le lien pour afficher plus de détails. Cela inclut le nombre d’utilisateurs auxquels la stratégie a été affectée et le nombre d’affectations terminées, en cours et non démarrées. Vous verrez également la liste des utilisateurs dans le lot, ainsi que l’état et le résultat de chaque utilisateur. Voici un exemple :

        ![Capture d’écran du.](media/activity-log-policy-assignment-detail.png)

    - **Envoyé** : date et heure de soumission de l’affectation de stratégie.
    - **Heure d’achèvement** : date et heure de fin de l’attribution de stratégie.
    - **Impact sur** : nombre d’utilisateurs dans le lot.
    - **État global** : état de l’attribution de stratégie.

> [!NOTE]
> Vous pouvez également accéder au journal d’activité à partir de la page **Utilisateurs** . Une fois que vous avez cliqué sur **Appliquer** pour envoyer une affectation de stratégie en bloc, une bannière s’affiche en haut de la page. Cliquez sur le lien **du journal d’activité** dans la bannière.

## <a name="related-topics"></a>Sujets associés

- [Affecter des stratégies aux utilisateurs](policy-assignment-overview.md)
