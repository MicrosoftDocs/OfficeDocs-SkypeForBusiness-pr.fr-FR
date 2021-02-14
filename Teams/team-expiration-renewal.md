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
ms.openlocfilehash: b111ddd6b874fef22a7d221f6eb932c4c14c7b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809404"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="09827-103">Expiration et renouvellement des équipes dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="09827-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="09827-104">Les organisations avec un grand nombre d’équipes ont souvent des équipes qui ne sont jamais utilisées.</span><span class="sxs-lookup"><span data-stu-id="09827-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="09827-105">Cela peut se produire pour diverses raisons, notamment l’expérimentation du produit, la collaboration à court terme de l’équipe ou le départ des propriétaires d’équipe de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="09827-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="09827-106">Au fil du temps, de telles équipes peuvent accumuler et créer une charge sur les ressources client.</span><span class="sxs-lookup"><span data-stu-id="09827-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="09827-107">Pour resserrez le nombre d’équipes inutilisées, en tant qu’administrateur, vous pouvez utiliser la stratégie d’expiration des groupes [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) pour nettoyer automatiquement les équipes inutilisées.</span><span class="sxs-lookup"><span data-stu-id="09827-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="09827-108">Étant donné que les équipes sont dosées par des groupes, les stratégies d’expiration des groupes s’appliquent automatiquement aux équipes également.</span><span class="sxs-lookup"><span data-stu-id="09827-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="09827-109">Lorsque vous appliquez une stratégie d’expiration à une équipe, un propriétaire d’équipe reçoit une notification pour le renouvellement de l’équipe 30 jours, 15 jours et 1 jour avant la date d’expiration de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="09827-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="09827-110">Lorsque le propriétaire de l’équipe reçoit la notification, il peut cliquer sur Renouveler **maintenant** dans les paramètres de l’équipe pour renouveler l’équipe.</span><span class="sxs-lookup"><span data-stu-id="09827-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="09827-111">![Capture d’écran du bouton Renouveler maintenant pour renouveler une équipe dans les paramètres d’une équipe](media/team-expiration.png "Capture d’écran du bouton Renouveler maintenant pour renouveler une équipe dans les paramètres d’une équipe")</span><span class="sxs-lookup"><span data-stu-id="09827-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="09827-112">Si le propriétaire de l’équipe ne renouvelle pas l’équipe et qu’aucune activité ne s’y trouve avant la fin de la stratégie d’expiration, l’équipe est dans un état « supprimé (supprimé de façon soft) », ce qui signifie qu’elle peut être restaurée dans les 30 prochains jours.</span><span class="sxs-lookup"><span data-stu-id="09827-112">If the team owner doesn't renew the team and there is no further activity on the team until the end of the expiration policy, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="09827-113">Renouvellement automatique d’équipe</span><span class="sxs-lookup"><span data-stu-id="09827-113">Team auto-renewal</span></span>

<span data-ttu-id="09827-114">Parfois, un propriétaire d’équipe ne peut pas renouveler son équipe, peut-être parce qu’il a oublié de le renouveler ou qu’il est absent à l’échéance du renouvellement.</span><span class="sxs-lookup"><span data-stu-id="09827-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="09827-115">Dans ces scénarios, une équipe en cours d’utilisation peut être supprimée en raison des stratégies d’expiration qui s’appliquent à l’équipe.</span><span class="sxs-lookup"><span data-stu-id="09827-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="09827-116">Pour éviter toute suppression accidentelle, le renouvellement automatique est automatiquement activé pour une équipe dans la stratégie d’expiration du groupe.</span><span class="sxs-lookup"><span data-stu-id="09827-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="09827-117">Lorsque la stratégie d’expiration du groupe est définie, toute équipe qui a au moins un canal visité par un membre de l’équipe avant sa date d’expiration est automatiquement renouvelée sans aucune intervention manuelle du propriétaire de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="09827-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="09827-118">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="09827-118">Known issues</span></span>

<span data-ttu-id="09827-119">**Date d’expiration de l’équipe et du groupe sous-jacent ne correspondent pas**</span><span class="sxs-lookup"><span data-stu-id="09827-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="09827-120">Avant le renouvellement d’une équipe, le groupe qui la constitue est tout d’abord renouvelé.</span><span class="sxs-lookup"><span data-stu-id="09827-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="09827-121">Dans le cadre du renouvellement, une nouvelle date d’expiration est définie sur le groupe pour une date future.</span><span class="sxs-lookup"><span data-stu-id="09827-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="09827-122">Cette nouvelle date peut ne pas être visible immédiatement dans Teams.</span><span class="sxs-lookup"><span data-stu-id="09827-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="09827-123">La synchronisation peut prendre jusqu’à 24 heures. Si vous constatez un écart entre la date d’expiration d’une équipe et son groupe sous-jacent, attendez 24 heures avant de demander un support supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="09827-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
