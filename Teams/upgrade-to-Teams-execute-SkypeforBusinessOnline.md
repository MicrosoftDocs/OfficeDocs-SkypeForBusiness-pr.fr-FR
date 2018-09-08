---
title: Mise à niveau à partir de Skype pour les entreprises en ligne aux équipes - équipes Microsoft
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considérations relatives à la mise à niveau pour les équipes de Skype pour Business Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50c595643e9c6a1805c44676cfa38fd04beb11bb
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883006"
---
<span data-ttu-id="c57f6-103">![Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation] (media/upgrade-banner-deployment.png "Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation")</span><span class="sxs-lookup"><span data-stu-id="c57f6-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="c57f6-104">Cet article fait partie de la phase de déploiement et l’implémentation de votre parcours de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="c57f6-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="c57f6-105">Avant de continuer, vérifiez que vous avez effectué les activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="c57f6-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="c57f6-106">Inscrit les parties prenantes du projet</span><span class="sxs-lookup"><span data-stu-id="c57f6-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="c57f6-107">Définies par l’étendue de votre projet</span><span class="sxs-lookup"><span data-stu-id="c57f6-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="c57f6-108">Comprendre la coexistence et l’interopérabilité de Skype pour professionnels et les équipes</span><span class="sxs-lookup"><span data-stu-id="c57f6-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="c57f6-109">Choisi votre parcours de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="c57f6-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="c57f6-110">Préparer votre environnement</span><span class="sxs-lookup"><span data-stu-id="c57f6-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="c57f6-111">Préparation de votre organisation</span><span class="sxs-lookup"><span data-stu-id="c57f6-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="c57f6-112">Mené un projet pilote</span><span class="sxs-lookup"><span data-stu-id="c57f6-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="c57f6-113">Mise à niveau à partir de Skype pour les entreprises en ligne aux équipes</span><span class="sxs-lookup"><span data-stu-id="c57f6-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="c57f6-114">Suivez les instructions de cet article si vous avez déployé entièrement Skype pour Business Online et que vous souhaitez mettre à niveau vos utilisateurs à partir de Skype pour les entreprises aux équipes.</span><span class="sxs-lookup"><span data-stu-id="c57f6-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="c57f6-115">Vous pouvez mettre à niveau les utilisateurs sélectivement ou tout en, en fonction de la mise à niveau de route que votre organisation a choisi, en affectant le mode de mise à niveau et la coexistence appropriée à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c57f6-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="c57f6-116">Affecter le mode de mise à niveau et de coexistence</span><span class="sxs-lookup"><span data-stu-id="c57f6-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="c57f6-117">Mise à niveau vers les équipes permettre faire en affectant le mode TeamsOnly de TeamsUpgradePolicy, qui peut être effectuée à l’aide de Microsoft Teams & Skype pour Business Admin Center ou un Skype pour la session Windows Powershell à distance Business.</span><span class="sxs-lookup"><span data-stu-id="c57f6-117">Upgrading to Teams can be accomplished by assigning the TeamsOnly mode of TeamsUpgradePolicy, which can be performed by using Microsoft Teams & Skype for Business Admin Center or a Skype for Business remote Windows Powershell session.</span></span>

<span data-ttu-id="c57f6-118">Pour plus d’informations, voir [configuration de votre coexistence et de paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence) et [TeamsUpgradePolicy : gestion de migration et coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="c57f6-118">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="c57f6-119">Mise à niveau système téléphonique et les équipes</span><span class="sxs-lookup"><span data-stu-id="c57f6-119">Phone System and Teams upgrade</span></span>

<span data-ttu-id="c57f6-120">Si votre Skype pour le déploiement d’entreprise en ligne inclut le système téléphonique avec des Plans de l’appel et Microsoft est votre fournisseur de réseau téléphonique commuté, la mise à niveau de vos utilisateurs à des équipes passera automatiquement PSTN entrant aux équipes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c57f6-120">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="c57f6-121">Si votre Skype pour le déploiement d’entreprise en ligne comprend un système téléphonique avec le nuage connecteur Edition, consultez les [Considérations supplémentaires pour le routage d’un système téléphonique directe](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="c57f6-121">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>