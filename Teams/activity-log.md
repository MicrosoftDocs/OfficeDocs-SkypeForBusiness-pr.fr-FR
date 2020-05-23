---
title: Afficher vos affectations de stratégie dans le journal d’activité dans le centre d’administration Microsoft teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment afficher les activités d’affectation de stratégie dans le journal d’activité dans le centre d’administration Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a363d934ffd66d04bc3eb778380613e33e460a9
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350072"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>Afficher vos affectations de stratégie dans le journal d’activité

Lorsque vous attribuez des stratégies aux utilisateurs dans le centre d’administration Microsoft Teams, vous pouvez afficher l’état de ces affectations de stratégie dans le journal d’activité. Le journal d’activité affiche les affectations de stratégie aux lots de plus de 20 utilisateurs par le biais du centre d’administration Microsoft teams depuis les 30 derniers jours. Gardez à l’esprit que le journal d’activité ne montre pas les affectations de packages de stratégie, les affectations de stratégie aux lots de moins de 20 utilisateurs via le centre d’administration Microsoft teams ou les affectations de stratégie via PowerShell.

![Capture d’écran de la page Journal d’activité](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Afficher vos activités d’attribution de stratégie dans le journal d’activité

Pour afficher vos affectations de stratégie dans le journal d’activité :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez au **tableau de bord**, puis sous **Journal d’activité**, sélectionnez Afficher les **Détails**.
2. Vous pouvez afficher toutes les affectations de stratégie ou filtrer la liste par État pour afficher uniquement les affectations **non commencées**, **en cours**ou **achevées**. Les informations suivantes s’affichent sur chaque affectation :
    - **Nom**: nom de l’affectation de stratégie. Cliquez sur le lien pour afficher plus de détails. Il s’agit du nombre d’utilisateurs auxquels la stratégie a été affectée et du nombre d’affectations achevées, en cours et non démarrées. Vous pouvez également afficher la liste des utilisateurs dans le lot et l’État et le résultat de chaque utilisateur. Voici un exemple :

        ![Capture d’écran du](media/activity-log-policy-assignment-detail.png)

    - **Envoyé**: date et heure de soumission de l’affectation de stratégie.
    - **Heure de fin**: date et heure de fin de l’affectation de stratégie.
    - **Impact sur**: nombre d’utilisateurs du lot.
    - **État global**: état de l’affectation de stratégie.

> [!NOTE]
> Vous pouvez également accéder au Journal d’activité à partir de la page **utilisateurs** . Après avoir cliqué sur **appliquer** pour valider une affectation de stratégie en bloc, une bannière apparaît en haut de la page. Cliquez sur le lien **Journal d’activité** dans la bannière.

## <a name="related-topics"></a>Rubriques connexes

- [Attribution de stratégies aux utilisateurs](assign-policies.md)
