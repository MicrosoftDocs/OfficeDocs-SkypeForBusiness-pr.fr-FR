---
title: Expiration et renouvellement de l’équipe dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez l’expiration et le renouvellement de l’équipe et comment utiliser la stratégie d’expiration de groupe Microsoft 365 pour nettoyer automatiquement les équipes inutilisées dans Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1a322e07df81727c75c05ebb16c4cdabc0916a4
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564172"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Expiration et renouvellement de l’équipe dans Microsoft Teams

Les organisations avec un grand nombre d’équipes ont souvent des équipes qui ne sont jamais réellement utilisées. Cela peut se produire pour plusieurs raisons, notamment l’expérimentation de produits, la collaboration d’équipe à court terme ou le départ des propriétaires d’équipe de l’organisation. Au fil du temps, ces équipes peuvent s’accumuler et créer une charge sur les ressources du locataire.  

Pour réduire le nombre d’équipes inutilisées, en tant qu’administrateur, vous pouvez utiliser la [stratégie d’expiration de groupe Microsoft 365](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) pour nettoyer automatiquement les équipes inutilisées. Étant donné que les équipes sont soutenues par des groupes, les stratégies d’expiration de groupe s’appliquent automatiquement également aux équipes.

Lorsque vous appliquez une stratégie d’expiration à une équipe, un propriétaire d’équipe reçoit une notification pour le renouvellement de l’équipe 30 jours, 15 jours et 1 jour avant la date d’expiration de l’équipe. Lorsque le propriétaire de l’équipe reçoit la notification, il peut cliquer sur **Renouveler maintenant** dans les paramètres de l’équipe pour renouveler l’équipe.

![Capture d’écran du bouton Renouveler maintenant pour renouveler une équipe dans les paramètres de l’équipe.](media/team-expiration.png "Capture d’écran du bouton Renouveler maintenant pour renouveler une équipe dans les paramètres de l’équipe")

Si le propriétaire de l’équipe ne renouvelle pas l’équipe et qu’il n’y a plus d’activité sur l’équipe jusqu’à la fin de la stratégie d’expiration, l’équipe est placée dans un état « supprimé de manière réversible », ce qui signifie qu’elle peut être restaurée dans les 30 prochains jours.

## <a name="team-auto-renewal"></a>Renouvellement automatique de l’équipe

Il peut arriver qu’un propriétaire d’équipe ne puisse pas renouveler l’équipe, peut-être parce qu’il a oublié de le renouveler ou s’est absenté lorsque le renouvellement était dû. Dans ces scénarios, une équipe active peut être supprimée en raison des stratégies d’expiration qui s’appliquent à l’équipe.  

Pour éviter une suppression accidentelle, le renouvellement automatique est automatiquement activé pour une équipe dans la stratégie d’expiration du groupe. Lorsque la stratégie d’expiration du groupe est configurée, toute équipe disposant d’au moins une visite de canal de n’importe quel membre de l’équipe avant sa date d’expiration est automatiquement renouvelée sans intervention manuelle du propriétaire de l’équipe.

## <a name="known-issues"></a>Problèmes connus

**La date d’expiration de l’équipe et du groupe sous-jacent ne correspond pas**

Avant le renouvellement d’une équipe, le groupe qui soutient l’équipe est d’abord renouvelé. Dans le cadre du renouvellement, une nouvelle date d’expiration est définie sur le groupe pour une date ultérieure. Cette nouvelle date peut ne pas être immédiatement visible dans Teams. La synchronisation peut prendre jusqu’à 24 heures. Si vous constatez une différence entre la date d’expiration d’une équipe et son groupe sous-jacent, attendez 24 heures avant de demander un support supplémentaire.