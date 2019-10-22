---
title: Expiration et renouvellement de l’équipe dans Microsoft teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abhisgu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Apprenez-en davantage sur l’expiration et le renouvellement d’une équipe et l’utilisation de la stratégie d’expiration de groupe Office 365 pour nettoyer automatiquement les équipes inutilisées dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fd7dfdececc9a490ff930bdba9948e9196c74f2
ms.sourcegitcommit: fc7d5e812873b648b374eef23d02c914a56b51d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/21/2019
ms.locfileid: "37608721"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Expiration et renouvellement de l’équipe dans Microsoft teams

Les équipes ayant un grand nombre d’équipes disposent souvent d’équipes qui ne sont jamais utilisées. Cela peut se produire pour plusieurs raisons, notamment pour une expérimentation du produit, une collaboration d’équipe à court terme ou des propriétaires d’équipe quittant l’organisation. Au fil du temps, ces équipes peuvent s’accumuler et créer un fardeau sur les ressources client.  

Pour limiter le nombre d’équipes inutilisées, en tant qu’administrateur, vous pouvez utiliser la [stratégie d’expiration de groupe Office 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy) pour nettoyer automatiquement les équipes inutilisées. Étant donné que les équipes sont régularisées par des groupes, les stratégies d’expiration de groupe s’appliquent automatiquement aux équipes.

Lorsque vous appliquez une stratégie d’expiration à une équipe, le propriétaire d’une équipe reçoit une notification pour le renouvellement d’équipe 30 jours, 15 jours et 1 jour avant la date d’expiration de l’équipe. Lorsque le propriétaire de l’équipe reçoit la notification, il peut cliquer sur **renouveler maintenant** dans les paramètres de l’équipe pour renouveler l’équipe.

![Capture d’écran du bouton renouveler maintenant pour renouveler une équipe dans les paramètres d’équipe](media/team-expiration.png "Capture d’écran du bouton renouveler maintenant pour renouveler une équipe dans les paramètres d’équipe")

Si le propriétaire de l’équipe ne renouvelle pas l’équipe, l’équipe est placée dans un état « supprimé (e) », ce qui signifie qu’elle peut être restaurée dans les 30 prochains jours.

## <a name="team-auto-renewal"></a>Renouvellement automatique d’équipe

Il peut arriver que le propriétaire d’une équipe ne parvient pas à renouveler son équipe, car il a oublié de le renouveler ou était absent lorsque le renouvellement est échu. Dans ces scénarios, une équipe en cours d’utilisation peut être supprimée en raison de stratégies d’expiration qui s’appliquent à l’équipe.  

Pour éviter toute suppression accidentelle, le renouvellement automatique est activé automatiquement pour une équipe dans la stratégie d’expiration du groupe. Lorsque la stratégie d’expiration du groupe est configurée, n’importe quelle équipe ayant au moins une visite de canal depuis n’importe quel membre de l’équipe avant sa date d’expiration est automatiquement renouvelée sans aucune intervention manuelle du propriétaire de l’équipe.

## <a name="known-issues"></a>Problèmes connus

**La date d’expiration de l’équipe et du groupe sous-jacent ne correspondent pas**

Avant le renouvellement d’une équipe, le groupe qui recule l’équipe est d’abord renouvelé. Dans le cadre du renouvellement, une nouvelle date d’expiration est définie dans le groupe pour une date ultérieure. Cette nouvelle date risque de ne pas être visible immédiatement dans Teams. La synchronisation peut durer jusqu’à 24 heures. Si vous voyez une différence entre la date d’expiration d’une équipe et son groupe sous-jacent, attendez 24 heures avant de rechercher une assistance supplémentaire.
