---
title: Mise à niveau Skype pour les entreprises en ligne pour les équipes Microsoft | Déployer
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considérations relatives à la mise à niveau pour les équipes de Skype pour Business Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 44f3cdad4ab65935c2721244364861db7a140f15
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349294"
---
<span data-ttu-id="79bc8-103">![Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation] (media/upgrade-banner-deployment.png "Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation")</span><span class="sxs-lookup"><span data-stu-id="79bc8-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="79bc8-104">Cet article fait partie de la phase de déploiement et l’implémentation de votre parcours de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="79bc8-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="79bc8-105">Avant de continuer, vérifiez que vous avez effectué les activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="79bc8-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="79bc8-106">Inscrit les parties prenantes du projet</span><span class="sxs-lookup"><span data-stu-id="79bc8-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="79bc8-107">Définies par l’étendue de votre projet</span><span class="sxs-lookup"><span data-stu-id="79bc8-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="79bc8-108">Comprendre la coexistence et l’interopérabilité de Skype pour professionnels et les équipes</span><span class="sxs-lookup"><span data-stu-id="79bc8-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="79bc8-109">Choisi votre parcours de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="79bc8-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="79bc8-110">Préparer votre environnement</span><span class="sxs-lookup"><span data-stu-id="79bc8-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="79bc8-111">Préparation de votre organisation</span><span class="sxs-lookup"><span data-stu-id="79bc8-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="79bc8-112">Mené un projet pilote</span><span class="sxs-lookup"><span data-stu-id="79bc8-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="79bc8-113">Mise à niveau à partir de Skype pour les entreprises en ligne aux équipes</span><span class="sxs-lookup"><span data-stu-id="79bc8-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="79bc8-114">Suivez les instructions de cet article si vous avez déployé entièrement Skype pour Business Online et que vous souhaitez mettre à niveau vos utilisateurs à partir de Skype pour les entreprises aux équipes.</span><span class="sxs-lookup"><span data-stu-id="79bc8-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="79bc8-115">Vous pouvez mettre à niveau les utilisateurs sélectivement ou tout en, en fonction de la mise à niveau de route que votre organisation a choisi, en affectant le mode de mise à niveau et la coexistence appropriée à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="79bc8-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="79bc8-116">Affecter le mode de mise à niveau et de coexistence</span><span class="sxs-lookup"><span data-stu-id="79bc8-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="79bc8-117">Vous pouvez mettre à niveau vos utilisateurs par les équipes en affectant le mode TeamsOnly de TeamsUpgradePolicy, qui peut être effectuée à l’aide de la & Microsoft Teams Skype pour Business Admin Center ou un Skype pour la session Windows Powershell à distance Business.</span><span class="sxs-lookup"><span data-stu-id="79bc8-117">You can upgrade your users by Teams by assigning the TeamsOnly mode of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams & Skype for Business Admin Center or a Skype for Business remote Windows Powershell session.</span></span>

<span data-ttu-id="79bc8-118">Pour plus d’informations, voir [configuration de votre coexistence et de paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence) et [TeamsUpgradePolicy : gestion de migration et coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="79bc8-118">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="79bc8-119">Mettre à niveau simultanément tous les utilisateurs à des équipes</span><span class="sxs-lookup"><span data-stu-id="79bc8-119">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="79bc8-120">Suivez ces étapes pour mettre à niveau tous les utilisateurs à des équipes en même temps.</span><span class="sxs-lookup"><span data-stu-id="79bc8-120">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change"></a><span data-ttu-id="79bc8-121">Étape 1 : Avertir les utilisateurs de la modification</span><span class="sxs-lookup"><span data-stu-id="79bc8-121">Step 1: Notify the users of the change</span></span>

1. <span data-ttu-id="79bc8-122">Dans le Microsoft Teams & Skype entreprise centre d’administration, sélectionnez **paramètres à l’échelle de la société** > **équipes de mise à niveau**.</span><span class="sxs-lookup"><span data-stu-id="79bc8-122">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="79bc8-123">Sous **mode de Coexistence**, remplacez le commutateur **Skype de notification pour les utilisateurs qu’une mise à niveau pour les équipes est disponible** **sur**.</span><span class="sxs-lookup"><span data-stu-id="79bc8-123">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-for-the-users"></a><span data-ttu-id="79bc8-124">Étape 2 : Définir le mode de coexistence pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="79bc8-124">Step 2: Set the coexistence mode for the users</span></span>

1. <span data-ttu-id="79bc8-125">Dans le Microsoft Teams & Skype entreprise centre d’administration, sélectionnez **paramètres de l’organisation**.</span><span class="sxs-lookup"><span data-stu-id="79bc8-125">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="79bc8-126">Sélectionnez mode **d’Équipes uniquement** à partir de la liste déroulante **mode de Coexistence** .</span><span class="sxs-lookup"><span data-stu-id="79bc8-126">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="79bc8-127">Mise à niveau par étapes</span><span class="sxs-lookup"><span data-stu-id="79bc8-127">Upgrade users in stages</span></span>

<span data-ttu-id="79bc8-128">Si vous souhaitez mise à niveau progressive de vos utilisateurs à des équipes, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="79bc8-128">Follow these steps if you want to gradually upgrade your users to Teams.</span></span>

### <a name="step-1-create-your-user-cohorts-for-the-upgrade"></a><span data-ttu-id="79bc8-129">Étape 1 : Créer votre cohortes utilisateur pour la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="79bc8-129">Step 1: Create your user cohorts for the upgrade</span></span>

<span data-ttu-id="79bc8-130">Cohortes utilisateur sont des groupes d’utilisateurs qui seront déplacées vers le mode équipes uniquement en même temps.</span><span class="sxs-lookup"><span data-stu-id="79bc8-130">User cohorts are groups of users who will be moved to Teams Only mode at the same time.</span></span>

<span data-ttu-id="79bc8-131">Pour créer votre cohortes utilisateur (ajouter un lien vers la page de sélection de l’utilisateur)</span><span class="sxs-lookup"><span data-stu-id="79bc8-131">To create your user cohorts (Add link to user selection page)</span></span>

### <a name="step-2-set-the-user-mode-to-islands"></a><span data-ttu-id="79bc8-132">Étape 2 : Définir le mode utilisateur pour (îles)</span><span class="sxs-lookup"><span data-stu-id="79bc8-132">Step 2: Set the user mode to Islands</span></span>

1. <span data-ttu-id="79bc8-133">Dans le Microsoft Teams & Skype entreprise centre d’administration, sélectionnez **utilisateurs**, puis sélectionnez un cohorte utilisateur.</span><span class="sxs-lookup"><span data-stu-id="79bc8-133">In the Microsoft Teams & Skype for Business Admin Center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="79bc8-134">En regard de **mise à niveau des équipes**, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="79bc8-134">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="79bc8-135">Dans le volet de **Mise à niveau des équipes** , sous **mode de Coexistence**, sélectionnez **(îles)** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="79bc8-135">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Islands** from the drop-down list.</span></span>

### <a name="step-3-set-notification-for-the-user-optional"></a><span data-ttu-id="79bc8-136">Étape 3 : Configurer la notification de l’utilisateur (facultatif)</span><span class="sxs-lookup"><span data-stu-id="79bc8-136">Step 3: Set notification for the user (optional)</span></span>

1. <span data-ttu-id="79bc8-137">Dans le Microsoft Teams & Skype entreprise centre d’administration, sélectionnez **les utilisateurs**et sélectionnez un cohorte utilisateur.</span><span class="sxs-lookup"><span data-stu-id="79bc8-137">In the Microsoft Teams & Skype for Business Admin Center, select **Users**, and select a user cohort.</span></span>
2. <span data-ttu-id="79bc8-138">En regard de **mise à niveau des équipes**, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="79bc8-138">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="79bc8-139">Dans le volet de **Mise à niveau des équipes** , sous **mode de Coexistence**, modifier commutateur **notifier le Skype pour utilisateur professionnel** **activé**.</span><span class="sxs-lookup"><span data-stu-id="79bc8-139">In the **Teams Upgrade** pane, under **Coexistence mode**, change **Notify the Skype for Business user** switch to **On**.</span></span>

### <a name="step-4-set-the-user-mode-to-teams-only"></a><span data-ttu-id="79bc8-140">Étape 4 : Définissez le mode utilisateur pour les équipes uniquement</span><span class="sxs-lookup"><span data-stu-id="79bc8-140">Step 4: Set the user mode to Teams Only</span></span>

<span data-ttu-id="79bc8-141">Lorsque vous êtes prêt à mettre à niveau des utilisateurs afin d’utiliser des équipes comme leur application uniquement, définissez le mode de Coexistence pour l’utilisateur d’équipes uniquement.</span><span class="sxs-lookup"><span data-stu-id="79bc8-141">When you are ready to upgrade the users to use Teams as their only application, set the Coexistence mode for the user to Teams Only.</span></span>

1. <span data-ttu-id="79bc8-142">Dans le Microsoft Teams & Skype entreprise centre d’administration, sélectionnez **utilisateurs**, puis sélectionnez un cohorte utilisateur.</span><span class="sxs-lookup"><span data-stu-id="79bc8-142">In the Microsoft Teams & Skype for Business Admin Center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="79bc8-143">En regard de **mise à niveau des équipes**, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="79bc8-143">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="79bc8-144">Dans le volet de **Mise à niveau des équipes** , sous **mode de Coexistence**, sélectionnez **Équipes uniquement** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="79bc8-144">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Teams Only** from the drop-down list.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="79bc8-145">Mise à niveau système téléphonique et les équipes</span><span class="sxs-lookup"><span data-stu-id="79bc8-145">Phone System and Teams upgrade</span></span>

<span data-ttu-id="79bc8-146">Si votre Skype pour le déploiement d’entreprise en ligne inclut le système téléphonique avec des Plans de l’appel et Microsoft est votre fournisseur de réseau téléphonique commuté, la mise à niveau de vos utilisateurs à des équipes passera automatiquement PSTN entrant aux équipes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="79bc8-146">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="79bc8-147">Si votre Skype pour le déploiement d’entreprise en ligne comprend un système téléphonique avec le nuage connecteur Edition, consultez les [Considérations supplémentaires pour le routage d’un système téléphonique directe](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="79bc8-147">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>