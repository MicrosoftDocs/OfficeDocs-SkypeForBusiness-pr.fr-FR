---
title: Vue d’ensemble de l’implémentation de votre mise à niveau vers Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Déterminez le chemin de mise à niveau optimal vers Microsoft Teams en fonction de votre déploiement actuel de Skype Entreprise.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0db2e752bb163f806c5dcba7aa56fc36bae7c2ef
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578357"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="1d021-103">Vue d’ensemble de l’implémentation de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="1d021-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="1d021-104">![Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation")</span><span class="sxs-lookup"><span data-stu-id="1d021-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="1d021-105">Cet article fait partie de la phase déploiement et implémentation de votre parcours vers la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="1d021-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="1d021-106">Activités de planification des conditions préalables</span><span class="sxs-lookup"><span data-stu-id="1d021-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d021-107">Avant de poursuivre votre implémentation de la mise à niveau, confirmez que vous avez lu le contenu de planification à partir de [Planifier](upgrade-plan-journey.md) votre mise à niveau afin de vous assurer que vous avez terminé toutes les planifications préalables.</span><span class="sxs-lookup"><span data-stu-id="1d021-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="1d021-108">Demandez aux parties prenantes de votre projet</span><span class="sxs-lookup"><span data-stu-id="1d021-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="1d021-109">Étendue définie de votre projet</span><span class="sxs-lookup"><span data-stu-id="1d021-109">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="1d021-110">Coexistence et interopérabilité comprises de Skype Entreprise et Teams</span><span class="sxs-lookup"><span data-stu-id="1d021-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="1d021-111">Nous avons choisi votre chemin de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="1d021-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="1d021-112">Pilote d’utilisateur planifié</span><span class="sxs-lookup"><span data-stu-id="1d021-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="1d021-113">Préparé votre environnement</span><span class="sxs-lookup"><span data-stu-id="1d021-113">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="1d021-114">Préparé votre organisation</span><span class="sxs-lookup"><span data-stu-id="1d021-114">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="1d021-115">Choisir le point de départ de la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="1d021-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="1d021-116">Les étapes à suivre pour effectuer votre mise à niveau vers Teams dépendent de votre déploiement actuel de Skype Entreprise :</span><span class="sxs-lookup"><span data-stu-id="1d021-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="1d021-117">En fonction de votre environnement actuel, choisissez votre point de départ :</span><span class="sxs-lookup"><span data-stu-id="1d021-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="1d021-118">**Si vous faites une mise à** niveau de Skype Entreprise Online vers Teams, suivez les étapes de la mise à niveau de Skype Entreprise Online vers [Teams.](https://aka.ms/SkypeToTeams-UpgradeOnline)</span><span class="sxs-lookup"><span data-stu-id="1d021-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

-  <span data-ttu-id="1d021-119">Si vous effectuez une mise à niveau à partir d’un environnement local Skype Entreprise, vous devrez effectuer quelques **étapes** supplémentaires pour configurer la connectivité entre vos environnements locaux et en ligne avant de déplacer vos utilisateurs vers Teams.</span><span class="sxs-lookup"><span data-stu-id="1d021-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="1d021-120">Pour plus d’informations, consultez la mise à niveau de Skype Entreprise en [local vers Teams.](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)</span><span class="sxs-lookup"><span data-stu-id="1d021-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
