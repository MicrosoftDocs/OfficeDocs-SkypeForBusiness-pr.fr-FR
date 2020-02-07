---
title: Expiration et renouvellement de l’équipe dans Microsoft teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Apprenez-en davantage sur l’expiration et le renouvellement d’une équipe et l’utilisation de la stratégie d’expiration de groupe Office 365 pour nettoyer automatiquement les équipes inutilisées dans Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bd9949a23d18eb03c83e50ecd418abbf54c0494
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837894"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="c14c6-103">Expiration et renouvellement de l’équipe dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="c14c6-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="c14c6-104">Les équipes ayant un grand nombre d’équipes disposent souvent d’équipes qui ne sont jamais utilisées.</span><span class="sxs-lookup"><span data-stu-id="c14c6-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="c14c6-105">Cela peut se produire pour plusieurs raisons, notamment pour une expérimentation du produit, une collaboration d’équipe à court terme ou des propriétaires d’équipe quittant l’organisation.</span><span class="sxs-lookup"><span data-stu-id="c14c6-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="c14c6-106">Au fil du temps, ces équipes peuvent s’accumuler et créer un fardeau sur les ressources client.</span><span class="sxs-lookup"><span data-stu-id="c14c6-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="c14c6-107">Pour limiter le nombre d’équipes inutilisées, en tant qu’administrateur, vous pouvez utiliser la [stratégie d’expiration de groupe Office 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy) pour nettoyer automatiquement les équipes inutilisées.</span><span class="sxs-lookup"><span data-stu-id="c14c6-107">To curb the number of unused teams, as an admin, you can use [Office 365 Group expiration policy](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="c14c6-108">Étant donné que les équipes sont régularisées par des groupes, les stratégies d’expiration de groupe s’appliquent automatiquement aux équipes.</span><span class="sxs-lookup"><span data-stu-id="c14c6-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="c14c6-109">Lorsque vous appliquez une stratégie d’expiration à une équipe, le propriétaire d’une équipe reçoit une notification pour le renouvellement d’équipe 30 jours, 15 jours et 1 jour avant la date d’expiration de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="c14c6-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="c14c6-110">Lorsque le propriétaire de l’équipe reçoit la notification, il peut cliquer sur **renouveler maintenant** dans les paramètres de l’équipe pour renouveler l’équipe.</span><span class="sxs-lookup"><span data-stu-id="c14c6-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="c14c6-111">![Capture d’écran du bouton renouveler maintenant pour renouveler une équipe dans les paramètres d’équipe](media/team-expiration.png "Capture d’écran du bouton renouveler maintenant pour renouveler une équipe dans les paramètres d’équipe")</span><span class="sxs-lookup"><span data-stu-id="c14c6-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="c14c6-112">Si le propriétaire de l’équipe ne renouvelle pas l’équipe, l’équipe est placée dans un état « supprimé (e) », ce qui signifie qu’elle peut être restaurée dans les 30 prochains jours.</span><span class="sxs-lookup"><span data-stu-id="c14c6-112">If the team owner doesn't renew the team, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="c14c6-113">Renouvellement automatique d’équipe</span><span class="sxs-lookup"><span data-stu-id="c14c6-113">Team auto-renewal</span></span>

<span data-ttu-id="c14c6-114">Il peut arriver que le propriétaire d’une équipe ne parvient pas à renouveler son équipe, car il a oublié de le renouveler ou était absent lorsque le renouvellement est échu.</span><span class="sxs-lookup"><span data-stu-id="c14c6-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="c14c6-115">Dans ces scénarios, une équipe en cours d’utilisation peut être supprimée en raison de stratégies d’expiration qui s’appliquent à l’équipe.</span><span class="sxs-lookup"><span data-stu-id="c14c6-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="c14c6-116">Pour éviter toute suppression accidentelle, le renouvellement automatique est activé automatiquement pour une équipe dans la stratégie d’expiration du groupe.</span><span class="sxs-lookup"><span data-stu-id="c14c6-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="c14c6-117">Lorsque la stratégie d’expiration du groupe est configurée, n’importe quelle équipe ayant au moins une visite de canal depuis n’importe quel membre de l’équipe avant sa date d’expiration est automatiquement renouvelée sans aucune intervention manuelle du propriétaire de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="c14c6-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="c14c6-118">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="c14c6-118">Known issues</span></span>

<span data-ttu-id="c14c6-119">**La date d’expiration de l’équipe et du groupe sous-jacent ne correspondent pas**</span><span class="sxs-lookup"><span data-stu-id="c14c6-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="c14c6-120">Avant le renouvellement d’une équipe, le groupe qui recule l’équipe est d’abord renouvelé.</span><span class="sxs-lookup"><span data-stu-id="c14c6-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="c14c6-121">Dans le cadre du renouvellement, une nouvelle date d’expiration est définie dans le groupe pour une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c14c6-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="c14c6-122">Cette nouvelle date risque de ne pas être visible immédiatement dans Teams.</span><span class="sxs-lookup"><span data-stu-id="c14c6-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="c14c6-123">La synchronisation peut durer jusqu’à 24 heures. Si vous voyez une différence entre la date d’expiration d’une équipe et son groupe sous-jacent, attendez 24 heures avant de rechercher une assistance supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="c14c6-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
