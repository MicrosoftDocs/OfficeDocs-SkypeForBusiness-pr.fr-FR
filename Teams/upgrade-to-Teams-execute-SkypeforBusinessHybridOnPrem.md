---
title: Effectuer la mise à niveau vers Teams à partir d’un déploiement hybride ou local de Skype Entreprise - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Remarques concernant la mise à niveau vers teams à partir d’une version hybride ou d’un déploiement local de Skype entreprise.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 118bae776f4bb3709d62dea1f384ccaa0707397b
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493978"
---
<span data-ttu-id="e37d5-103">![Diagramme de parcours de mise à niveau, mise en évidence du déploiement et de l’implémentation] (media/upgrade-banner-deployment.png "Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de déploiement et d’implémentation")</span><span class="sxs-lookup"><span data-stu-id="e37d5-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="e37d5-104">Cet article fait partie de l’étape de déploiement et d’implémentation de votre parcours de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="e37d5-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="e37d5-105">Avant de continuer, confirmez que vous avez terminé les activités suivantes:</span><span class="sxs-lookup"><span data-stu-id="e37d5-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="e37d5-106">Inscription des parties prenantes du projet</span><span class="sxs-lookup"><span data-stu-id="e37d5-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="e37d5-107">Définition de l’objectif de votre projet</span><span class="sxs-lookup"><span data-stu-id="e37d5-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="e37d5-108">Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes</span><span class="sxs-lookup"><span data-stu-id="e37d5-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="e37d5-109">Choix de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="e37d5-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="e37d5-110">Préparé votre environnement</span><span class="sxs-lookup"><span data-stu-id="e37d5-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="e37d5-111">Préparé votre organisation</span><span class="sxs-lookup"><span data-stu-id="e37d5-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="e37d5-112">A mené une pilote</span><span class="sxs-lookup"><span data-stu-id="e37d5-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a><span data-ttu-id="e37d5-113">Effectuer une mise à niveau vers teams depuis un déploiement hybride ou local Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="e37d5-113">Upgrade to Teams from a Skype for Business hybrid or on-premises deployment</span></span>

<span data-ttu-id="e37d5-114">Suivez les recommandations de cet article si vous avez déployé Skype entreprise ou Microsoft Lync en local et que votre organisation souhaite effectuer une mise à niveau vers des équipes de manière sélective, en utilisant plusieurs modes de coexistence, ou tout le tout.</span><span class="sxs-lookup"><span data-stu-id="e37d5-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="e37d5-115">La première étape consiste à configurer la connectivité hybride avec votre client Office 365, puis à déplacer vos utilisateurs vers Skype entreprise Online et à leur affecter le mode de coexistence et de mise à niveau appropriés.</span><span class="sxs-lookup"><span data-stu-id="e37d5-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="e37d5-116">Étape 1: déployer une connectivité hybride</span><span class="sxs-lookup"><span data-stu-id="e37d5-116">Step 1: Deploy hybrid connectivity</span></span> 

<span data-ttu-id="e37d5-117">La configuration minimale requise pour la mise à niveau de vos utilisateurs vers teams consiste à déployer une connectivité hybride.</span><span class="sxs-lookup"><span data-stu-id="e37d5-117">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="e37d5-118">Cela peut impliquer le déploiement de nouvelles connexions externes pour votre déploiement Skype entreprise ou Lync, ou la configuration d’une relation hybride avec votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="e37d5-118">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span> 

<span data-ttu-id="e37d5-119">Pour plus d’informations, reportez-vous à la section déploiement d’une [connectivité hybride entre Skype entreprise Server et Skype entreprise Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="e37d5-119">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="e37d5-120">Étape 2: déplacer des utilisateurs vers Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e37d5-120">Step 2: Move users to Skype for Business Online</span></span> 

<span data-ttu-id="e37d5-121">Lorsque vous avez terminé la configuration hybride, déplacez les utilisateurs vers Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="e37d5-121">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span> 

<span data-ttu-id="e37d5-122">Pour plus d’informations, reportez-vous à la rubrique [déplacer des utilisateurs de local vers Skype entreprise Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="e37d5-122">For more information, see [Move users from on premises to Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span> 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="e37d5-123">Étape 3: affecter une coexistence et un mode de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="e37d5-123">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="e37d5-124">Après avoir déplacé vos utilisateurs vers Skype entreprise Online, vous pouvez leur affecter le mode de coexistence approprié en fonction du parcours de mise à niveau choisi par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e37d5-124">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="e37d5-125">Pour plus d’informations, reportez-vous à [définition de votre coexistence et de vos paramètres de mise à](https://aka.ms/SkypeToTeams-SetCoexistence) [TeamsUpgradePolicy: gestion de la migration et de](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)la coexistence.</span><span class="sxs-lookup"><span data-stu-id="e37d5-125">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="e37d5-126">Avec Skype entreprise Server 2019 et une prochaine mise à jour cumulative de Skype entreprise Server 2015, vous serez en mesure de passer à l’étape 2 (déplacer les utilisateurs vers Skype entreprise Online) et à l’étape 3 (mettre à niveau les utilisateurs vers les équipes) en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="e37d5-126">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="e37d5-127">Des informations supplémentaires seront fournies après le lancement de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e37d5-127">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="e37d5-128">Mise à niveau du système téléphonique et des équipes</span><span class="sxs-lookup"><span data-stu-id="e37d5-128">Phone System and Teams upgrade</span></span>

<span data-ttu-id="e37d5-129">Si vous migrez votre déploiement hybride Skype entreprise vers votre système téléphonique avec des plans d’appels, Microsoft sera votre fournisseur de réseau téléphonique commuté (PSTN), et en supposant que vous avez terminé le transfert du numéro de téléphone, la mise à niveau de vos utilisateurs vers Teams va automatiquement migrer les appels RTC entrants vers Teams.</span><span class="sxs-lookup"><span data-stu-id="e37d5-129">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="e37d5-130">Si les plans d’appel ne sont pas disponibles, vous devez migrer votre déploiement voix entreprise vers le routage direct du système Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="e37d5-130">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="e37d5-131">Pour mettre à niveau vos utilisateurs vers Teams, reportez-vous à la rubrique [Considérations supplémentaires sur le routage direct du système téléphonique](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="e37d5-131">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
