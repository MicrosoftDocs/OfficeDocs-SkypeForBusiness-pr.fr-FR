---
title: Mise à niveau Skype pour déploiement hybride Business Teams Microsoft | PSTN
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considérations relatives à la mise à niveau aux équipes un Skype pour un déploiement hybride Business.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: c78c5b519997c125dc1902021acabe664ea03047
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349574"
---
<span data-ttu-id="cba8c-103">![Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation] (media/upgrade-banner-deployment.png "Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation")</span><span class="sxs-lookup"><span data-stu-id="cba8c-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="cba8c-104">Cet article fait partie de la phase de déploiement et l’implémentation de votre parcours de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cba8c-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="cba8c-105">Avant de continuer, vérifiez que vous avez effectué les activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="cba8c-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="cba8c-106">Inscrit les parties prenantes du projet</span><span class="sxs-lookup"><span data-stu-id="cba8c-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="cba8c-107">Définies par l’étendue de votre projet</span><span class="sxs-lookup"><span data-stu-id="cba8c-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="cba8c-108">Comprendre la coexistence et l’interopérabilité de Skype pour professionnels et les équipes</span><span class="sxs-lookup"><span data-stu-id="cba8c-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="cba8c-109">Choisi votre parcours de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="cba8c-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="cba8c-110">Préparer votre environnement</span><span class="sxs-lookup"><span data-stu-id="cba8c-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="cba8c-111">Préparation de votre organisation</span><span class="sxs-lookup"><span data-stu-id="cba8c-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="cba8c-112">Mené un projet pilote</span><span class="sxs-lookup"><span data-stu-id="cba8c-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="cba8c-113">Mise à niveau à partir d’un Skype pour un déploiement hybride Business aux équipes</span><span class="sxs-lookup"><span data-stu-id="cba8c-113">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="cba8c-114">Suivez les instructions de cet article si vous avez déployé Skype pour les entreprises ou Microsoft Lync sur site et configuré dans un déploiement hybride avec votre client Office 365 et que votre organisation souhaite mettre à niveau vers les équipes soit sélectivement — en utilisant plusieurs modes de coexistence, ou tout en.</span><span class="sxs-lookup"><span data-stu-id="cba8c-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 tenant, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="cba8c-115">Pour un parcours de mise à niveau, vous devez atteindre vos utilisateurs Skype pour Business Online (s’ils ne sont pas déjà hébergés en ligne), puis les affecter le mode de mise à niveau et la coexistence appropriée.</span><span class="sxs-lookup"><span data-stu-id="cba8c-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren’t already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="cba8c-116">Étape 1 : Déplacer les utilisateurs vers Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="cba8c-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="cba8c-117">Cette étape s’applique aux utilisateurs qui sont actuellement hébergés sur un système local.</span><span class="sxs-lookup"><span data-stu-id="cba8c-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="cba8c-118">Pour plus d’informations sur le déplacement de ces utilisateurs vers Skype pour Business Online, voir [déplacer des utilisateurs à partir de sur - local à Skype pour Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="cba8c-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="cba8c-119">Étape 2 : Attribuer une coexistence et le mode de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="cba8c-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="cba8c-120">Une fois que vous avez déplacé vos utilisateurs à Skype pour Business Online, vous pouvez affecter le mode de coexistence approprié en fonction de la mise à niveau voyage que votre organisation a choisi.</span><span class="sxs-lookup"><span data-stu-id="cba8c-120">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="cba8c-121">Pour plus d’informations, voir [configuration de votre coexistence et de paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence) et [TeamsUpgradePolicy : gestion de migration et coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="cba8c-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="cba8c-122">Avec Skype pour Business Server 2019 et une mise à jour cumulative futur de Skype pour Business Server 2015, vous serez en mesure d’effectuer l’étape 1 (déplacement d’utilisateurs vers Skype pour Business Online) et l’étape 2 (mise à niveau des utilisateurs aux équipes) en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="cba8c-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="cba8c-123">Vous trouverez plus d’informations après la sortie de Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cba8c-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="cba8c-124">Mise à niveau système téléphonique et les équipes</span><span class="sxs-lookup"><span data-stu-id="cba8c-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="cba8c-125">Si vous passez vos Skype pour un déploiement hybride Business au système téléphonique avec des Plans de l’appel de Microsoft sera votre fournisseur de réseau téléphonique commuté — et en supposant que vous avez terminé le portage numéro de téléphone : mise à niveau de vos utilisateurs Les équipes passera automatiquement PSTN entrant aux équipes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="cba8c-125">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="cba8c-126">Si des Plans de l’appel n’est pas disponible ou que vous comptez utiliser votre fournisseur de connectivité PSTN existante, vous devez effectuer la transition de votre déploiement d’enterprise voice, ou déploiement de voix hybride qui utilise votre local déploiement ou dans le nuage connecteur Edition — à Routage Direct système téléphonique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cba8c-126">If Calling Plans isn’t available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="cba8c-127">Pour mettre à niveau vos utilisateurs à des équipes, voir les [Considérations supplémentaires pour le routage d’un système téléphonique directe](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="cba8c-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
