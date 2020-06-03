---
title: Mise à niveau de Skype Entreprise local vers Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez comment migrer votre organisation vers Microsoft teams à partir d’un déploiement local de Skype entreprise.
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
ms.openlocfilehash: bea614da76bd61cf7c29b0e8f150f1aac85223a7
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523157"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="5cd5a-103">Effectuer une mise à niveau d’un déploiement local de Skype entreprise vers teams</span><span class="sxs-lookup"><span data-stu-id="5cd5a-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="5cd5a-104">![Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de déploiement et d’implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de déploiement et d’implémentation")</span><span class="sxs-lookup"><span data-stu-id="5cd5a-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="5cd5a-105">Cet article fait partie de l’étape de déploiement et d’implémentation de votre parcours de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="5cd5a-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="5cd5a-106">Avant de continuer, confirmez que vous avez terminé les activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="5cd5a-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="5cd5a-107">Inscription des parties prenantes du projet</span><span class="sxs-lookup"><span data-stu-id="5cd5a-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="5cd5a-108">Définition de l’objectif de votre projet</span><span class="sxs-lookup"><span data-stu-id="5cd5a-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="5cd5a-109">Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes</span><span class="sxs-lookup"><span data-stu-id="5cd5a-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="5cd5a-110">Choix de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="5cd5a-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="5cd5a-111">Préparé votre environnement</span><span class="sxs-lookup"><span data-stu-id="5cd5a-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="5cd5a-112">Préparé votre organisation</span><span class="sxs-lookup"><span data-stu-id="5cd5a-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="5cd5a-113">A mené une pilote</span><span class="sxs-lookup"><span data-stu-id="5cd5a-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="5cd5a-114">Suivez les recommandations de cet article si vous avez déployé Skype entreprise ou Microsoft Lync en local et que votre organisation souhaite effectuer une mise à niveau vers Microsoft teams de manière sélective, à l’aide de plusieurs modes de coexistence (ou tout le tout).</span><span class="sxs-lookup"><span data-stu-id="5cd5a-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="5cd5a-115">Étape 1 : déployer une connectivité hybride</span><span class="sxs-lookup"><span data-stu-id="5cd5a-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="5cd5a-116">La configuration minimale requise pour la mise à niveau de vos utilisateurs vers teams consiste à déployer une connectivité hybride.</span><span class="sxs-lookup"><span data-stu-id="5cd5a-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="5cd5a-117">Pour plus d’informations, reportez-vous à la section déploiement d’une [connectivité hybride entre Skype entreprise Server et Skype entreprise Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="5cd5a-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="5cd5a-118">Étape 2 : implémenter le voyage de mise à niveau choisi pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="5cd5a-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="5cd5a-119">Une fois que vous avez terminé la configuration hybride, vous pouvez planifier la migration de vos utilisateurs vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="5cd5a-119">After you've completed your hybrid setup, you can plan to move your users to Office 365.</span></span>

<span data-ttu-id="5cd5a-120">Pour plus d’informations, consultez :</span><span class="sxs-lookup"><span data-stu-id="5cd5a-120">For more information, see:</span></span>

- <span data-ttu-id="5cd5a-121">[TeamsUpgradePolicy : gestion de la migration et de la coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="5cd5a-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="5cd5a-122">[Déplacez les utilisateurs de local vers Skype entreprise Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="5cd5a-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="5cd5a-123">Mise à niveau du système téléphonique et des équipes</span><span class="sxs-lookup"><span data-stu-id="5cd5a-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="5cd5a-124">Le passage des systèmes téléphoniques locaux à teams vous permet de tirer parti du routage direct du système téléphonique (« routage directe ») ou des offres d’appels fournies par Microsoft pour Office 365.</span><span class="sxs-lookup"><span data-stu-id="5cd5a-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Office 365.</span></span>

<span data-ttu-id="5cd5a-125">Si vous n’utilisez pas les forfaits d’appels dans Office 365, vous devez faire basculer votre déploiement de voix entreprise vers le routage direct du système téléphonique dans le cadre de la mise à niveau vers Teams.</span><span class="sxs-lookup"><span data-stu-id="5cd5a-125">If you're not using Calling Plans in Office 365, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="5cd5a-126">Pour plus d’informations, reportez-vous [à considérations supplémentaires sur le routage direct du système téléphonique](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="5cd5a-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="5cd5a-127">Si vous envisagez d’utiliser des plans d’appel dans Office 365, consultez nos recommandations pour [le transfert de vos numéros de téléphone vers teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="5cd5a-127">If you are planning to use Calling Plans in Office 365, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>