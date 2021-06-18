---
title: Expiration et renouvellement des équipes dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: En savoir plus sur l’expiration et le renouvellement des équipes et comment utiliser la stratégie d’expiration des groupes Microsoft 365 pour nettoyer automatiquement les équipes inutilisées dans Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 606d957b703725d631beec38237f4d9b4272433e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116952"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Expiration et renouvellement des équipes dans Microsoft Teams

Les organisations avec un grand nombre d’équipes ont souvent des équipes qui ne sont jamais utilisées. Cela peut se produire pour diverses raisons, notamment l’expérimentation du produit, la collaboration à court terme de l’équipe ou le départ des propriétaires d’équipe de l’organisation. Au fil du temps, ces équipes peuvent accumuler et créer une charge sur les ressources client.  

Pour resserrez le nombre d’équipes inutilisées, en tant qu’administrateur, vous pouvez utiliser la stratégie d’expiration des groupes [Microsoft 365](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) pour nettoyer automatiquement les équipes inutilisées. Étant donné que les équipes sont dosées par des groupes, les stratégies d’expiration des groupes s’appliquent automatiquement aux équipes également.

Lorsque vous appliquez une stratégie d’expiration à une équipe, un propriétaire d’équipe reçoit une notification pour le renouvellement de l’équipe 30 jours, 15 jours et 1 jour avant la date d’expiration de l’équipe. Lorsque le propriétaire de l’équipe reçoit la notification, il peut cliquer sur Renouveler **maintenant** dans les paramètres de l’équipe pour renouveler l’équipe.

![Capture d’écran du bouton Renouveler maintenant pour renouveler une équipe dans les paramètres d’une équipe](media/team-expiration.png "Capture d’écran du bouton Renouveler maintenant pour renouveler une équipe dans les paramètres d’une équipe")

Si le propriétaire de l’équipe ne renouvelle pas l’équipe et qu’aucune activité ne s’y trouve avant la fin de la stratégie d’expiration, l’équipe est dans un état « supprimé (supprimé de façon soft) », ce qui signifie qu’elle peut être restaurée dans les 30 prochains jours.

## <a name="team-auto-renewal"></a>Renouvellement automatique d’équipe

Parfois, un propriétaire d’équipe ne peut pas renouveler son équipe, peut-être parce qu’il a oublié de le renouveler ou qu’il est absent à l’échéance du renouvellement. Dans ces scénarios, une équipe en cours d’utilisation peut être supprimée en raison des stratégies d’expiration qui s’appliquent à l’équipe.  

Pour éviter toute suppression accidentelle, le renouvellement automatique est automatiquement activé pour une équipe dans la stratégie d’expiration du groupe. Lorsque la stratégie d’expiration du groupe est définie, toute équipe qui a au moins un canal visité par un membre de l’équipe avant sa date d’expiration est automatiquement renouvelée sans aucune intervention manuelle du propriétaire de l’équipe.

## <a name="known-issues"></a>Problèmes connus

**Date d’expiration de l’équipe et du groupe sous-jacent ne correspondent pas**

Avant le renouvellement d’une équipe, le groupe qui la constitue est tout d’abord renouvelé. Dans le cadre du renouvellement, une nouvelle date d’expiration est définie sur le groupe pour une date future. Cette nouvelle date peut ne pas être visible immédiatement dans Teams. La synchronisation peut prendre jusqu’à 24 heures. Si vous constatez un écart entre la date d’expiration d’une équipe et son groupe sous-jacent, attendez 24 heures avant de demander un support supplémentaire.