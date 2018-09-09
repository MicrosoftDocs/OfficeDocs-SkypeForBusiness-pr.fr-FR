---
title: Mise à niveau à partir d’un Skype pour le déploiement local de Business aux équipes - Microsoft Teams
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considérations relatives à la mise à niveau aux équipes un Skype pour Business déploiement local.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c70ef403754bcf64fe757ea2a5290229e4426513
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887633"
---
<span data-ttu-id="fb661-103">![Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation] (media/upgrade-banner-deployment.png "Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation")</span><span class="sxs-lookup"><span data-stu-id="fb661-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="fb661-104">Cet article fait partie de la phase de déploiement et l’implémentation de votre parcours de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="fb661-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="fb661-105">Avant de continuer, vérifiez que vous avez effectué les activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb661-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="fb661-106">Inscrit les parties prenantes du projet</span><span class="sxs-lookup"><span data-stu-id="fb661-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="fb661-107">Définies par l’étendue de votre projet</span><span class="sxs-lookup"><span data-stu-id="fb661-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="fb661-108">Comprendre la coexistence et l’interopérabilité de Skype pour professionnels et les équipes</span><span class="sxs-lookup"><span data-stu-id="fb661-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="fb661-109">Choisi votre parcours de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="fb661-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="fb661-110">Préparer votre environnement</span><span class="sxs-lookup"><span data-stu-id="fb661-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="fb661-111">Préparation de votre organisation</span><span class="sxs-lookup"><span data-stu-id="fb661-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="fb661-112">Mené un projet pilote</span><span class="sxs-lookup"><span data-stu-id="fb661-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="fb661-113">Mise à niveau à partir d’un Skype pour le déploiement local de Business aux équipes</span><span class="sxs-lookup"><span data-stu-id="fb661-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="fb661-114">Suivez les instructions de cet article si vous avez déployé Skype pour les entreprises ou Microsoft Lync sur site et votre organisation souhaite mettre à niveau vers les équipes soit sélectivement — à l’aide de plusieurs modes de coexistence, ou tout en.</span><span class="sxs-lookup"><span data-stu-id="fb661-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="fb661-115">La première étape consiste à configurer la connectivité hybride avec votre client Office 365, puis déplacer les utilisateurs vers Skype pour Business Online et affecter la coexistence appropriée et le mode de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="fb661-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="fb661-116">Étape 1 : Déploiement de connectivité hybride</span><span class="sxs-lookup"><span data-stu-id="fb661-116">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="fb661-117">Les éléments prérequis clés pour la mise à niveau de vos utilisateurs à des équipes consiste à déployer la connectivité hybride.</span><span class="sxs-lookup"><span data-stu-id="fb661-117">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="fb661-118">Cela peut impliquer le déploiement de nouvelles connectivité externe pour votre Skype existant pour le déploiement de Lync ou de l’entreprise, ou la configuration simplement une relation hybride avec votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb661-118">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span>

<span data-ttu-id="fb661-119">Pour plus d’informations, voir [déployer la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="fb661-119">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="fb661-120">Étape 2 : Déplacer les utilisateurs vers Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="fb661-120">Step 2: Move users to Skype for Business Online</span></span>

<span data-ttu-id="fb661-121">Une fois que vous avez terminé votre configuration hybride, déplacer des utilisateurs vers Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="fb661-121">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span> 

<span data-ttu-id="fb661-122">Pour plus d’informations, voir [déplacer des utilisateurs à partir de sur site à Skype pour Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="fb661-122">For more information, see [Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span></span>

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="fb661-123">Étape 3 : Attribuer une coexistence et le mode de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="fb661-123">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="fb661-124">Une fois que vous avez déplacé vos utilisateurs à Skype pour Business Online, vous pouvez affecter le mode de coexistence approprié en fonction de la mise à niveau voyage que votre organisation a choisi.</span><span class="sxs-lookup"><span data-stu-id="fb661-124">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="fb661-125">Pour plus d’informations, voir [configuration de votre coexistence et de paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence) et [TeamsUpgradePolicy : gestion de migration et coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="fb661-125">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="fb661-126">Avec Skype pour Business Server 2019 et une mise à jour cumulative futur de Skype pour Business Server 2015, vous serez en mesure d’effectuer l’étape 2 (déplacement d’utilisateurs vers Skype pour Business Online) et l’étape 3 (mise à niveau des utilisateurs aux équipes) en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="fb661-126">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="fb661-127">Vous trouverez plus d’informations après la sortie de Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fb661-127">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="fb661-128">Mise à niveau système téléphonique et les équipes</span><span class="sxs-lookup"><span data-stu-id="fb661-128">Phone System and Teams upgrade</span></span>

<span data-ttu-id="fb661-129">Si vous passez vos Skype pour le déploiement local de Business de voix entreprise au système téléphonique avec des Plans de l’appel de Microsoft sera votre fournisseur de réseau téléphonique commuté — et en supposant que vous avez terminé le numéro de téléphone portage : mise à niveau de vos utilisateurs à des équipes passera automatiquement aux appels PSTN entrants aux équipes.</span><span class="sxs-lookup"><span data-stu-id="fb661-129">If you’re transitioning your Skype for Business on-premises deployment from enterprise voice to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="fb661-130">Si des Plans de l’appel n’est pas disponible, vous devez effectuer la transition de votre déploiement d’enterprise voice au routage Direct de Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="fb661-130">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="fb661-131">Pour mettre à niveau vos utilisateurs à des équipes, voir les [Considérations supplémentaires pour le routage d’un système téléphonique directe](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="fb661-131">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>