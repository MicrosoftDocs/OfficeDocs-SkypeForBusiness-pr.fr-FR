---
title: Mise à niveau de Skype entreprise Online vers Microsoft teams | Deploy
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Remarques concernant la mise à niveau vers teams à partir de Skype entreprise Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b1cfb8302476983eeb5be180307bc143eb281dc
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548508"
---
<span data-ttu-id="19ef4-103">![Diagramme de parcours de mise à niveau, mise en évidence du déploiement et de l’implémentation] (media/upgrade-banner-deployment.png "Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de déploiement et d’implémentation")</span><span class="sxs-lookup"><span data-stu-id="19ef4-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="19ef4-104">Cet article fait partie de l’étape de déploiement et d’implémentation de votre parcours de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="19ef4-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="19ef4-105">Avant de continuer, confirmez que vous avez terminé les activités suivantes:</span><span class="sxs-lookup"><span data-stu-id="19ef4-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="19ef4-106">Inscription des parties prenantes du projet</span><span class="sxs-lookup"><span data-stu-id="19ef4-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="19ef4-107">Définition de l’objectif de votre projet</span><span class="sxs-lookup"><span data-stu-id="19ef4-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="19ef4-108">Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes</span><span class="sxs-lookup"><span data-stu-id="19ef4-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="19ef4-109">Choix de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="19ef4-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="19ef4-110">Préparé votre environnement</span><span class="sxs-lookup"><span data-stu-id="19ef4-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="19ef4-111">Préparé votre organisation</span><span class="sxs-lookup"><span data-stu-id="19ef4-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="19ef4-112">A mené une pilote</span><span class="sxs-lookup"><span data-stu-id="19ef4-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="19ef4-113">Mise à niveau de Skype Entreprise Online vers Teams</span><span class="sxs-lookup"><span data-stu-id="19ef4-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="19ef4-114">Suivez les recommandations de cet article si vous avez entièrement déployé Skype entreprise Online et voulez mettre à niveau vos utilisateurs de Skype entreprise vers Teams.</span><span class="sxs-lookup"><span data-stu-id="19ef4-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="19ef4-115">Vous pouvez mettre à niveau les utilisateurs de manière sélective ou sélective, en fonction du parcours de mise à niveau choisi par votre organisation, en attribuant la coexistence et le mode de mise à niveau appropriés à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="19ef4-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="19ef4-116">Attribuer le mode de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="19ef4-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="19ef4-117">Vous pouvez mettre à niveau vos utilisateurs vers le mode TeamsOnly en assignant l’instance UpgradeToTeams de TeamsUpgradePolicy, qui peut être effectuée à l’aide du centre d’administration Microsoft teams ou d’une session Windows PowerShell Skype entreprise distante.</span><span class="sxs-lookup"><span data-stu-id="19ef4-117">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="19ef4-118">Vous pouvez effectuer cette opération sur une base par utilisateur ou sur une base d’un client si vous voulez ugprade tout le client en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="19ef4-118">You can do this either on a per user basis, or on a tenant-wide basis if you want to ugprade the entire tenant in one step.</span></span> 

<span data-ttu-id="19ef4-119">Pour plus d’informations, reportez-vous à [définition de votre coexistence et de vos paramètres de mise à](https://aka.ms/SkypeToTeams-SetCoexistence) [TeamsUpgradePolicy: gestion de la migration et de](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)la coexistence.</span><span class="sxs-lookup"><span data-stu-id="19ef4-119">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="19ef4-120">Mettre à niveau tous les utilisateurs en équipes en même temps</span><span class="sxs-lookup"><span data-stu-id="19ef4-120">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="19ef4-121">Suivez ces étapes pour mettre à niveau tous vos utilisateurs vers teams en même temps.</span><span class="sxs-lookup"><span data-stu-id="19ef4-121">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="19ef4-122">Étape 1: informer les utilisateurs de la modification (facultatif)</span><span class="sxs-lookup"><span data-stu-id="19ef4-122">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="19ef4-123">Dans le centre d’administration de Microsoft Teams, sélectionnez**mise à niveau des équipes** **des paramètres** > à l’échelle de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="19ef4-123">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="19ef4-124">Sous **mode**de coexistence, changez le paramètre **informer les utilisateurs de Skype entreprise qu’une mise à niveau vers teams est disponible** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="19ef4-124">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="19ef4-125">Étape 2: définir le mode de coexistence sur TeamsOnly pour l’Organisation</span><span class="sxs-lookup"><span data-stu-id="19ef4-125">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="19ef4-126">Dans le centre d’administration de Microsoft Teams, sélectionnez **paramètres à l’échelle**de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="19ef4-126">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="19ef4-127">Sélectionner le mode **équipes uniquement** dans la liste déroulante du **mode coexistence** .</span><span class="sxs-lookup"><span data-stu-id="19ef4-127">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="19ef4-128">Mettre à niveau les utilisateurs par étapes</span><span class="sxs-lookup"><span data-stu-id="19ef4-128">Upgrade users in stages</span></span>

<span data-ttu-id="19ef4-129">Suivez ces étapes si vous souhaitez mettre à niveau progressivement vos utilisateurs vers TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="19ef4-129">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="19ef4-130">Étape 1: identifier les groupes d’utilisateurs pour la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="19ef4-130">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="19ef4-131">Il arrive souvent que les organisations choisissent de mettre à niveau leurs organisations en cas d’onde de réussite.</span><span class="sxs-lookup"><span data-stu-id="19ef4-131">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="19ef4-132">Vous souhaiterez peut-être identifier ces utilisateurs d’abord pour pouvoir les Rechercher dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="19ef4-132">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="19ef4-133">Par ailleurs, il est possible que vous souhaitiez utiliser PowerShell pour plus efficacement.</span><span class="sxs-lookup"><span data-stu-id="19ef4-133">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="19ef4-134">Une fois que vous avez identifié le jeu d’utilisateurs pour une vague de mise à niveau donnée, poursuivez les étapes restantes.</span><span class="sxs-lookup"><span data-stu-id="19ef4-134">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a><span data-ttu-id="19ef4-135">Étape 2: définir une notification pour les utilisateurs de l’onde ugprade actuelle (facultatif)</span><span class="sxs-lookup"><span data-stu-id="19ef4-135">Step 2: Set notification for the users in the current ugprade wave (optional)</span></span>

<span data-ttu-id="19ef4-136">Si vous utilisez le centre d’administration de Microsoft Teams, vous pouvez configurer TeamsUpgradePolicy pour 20 utilisateurs à la fois:</span><span class="sxs-lookup"><span data-stu-id="19ef4-136">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="19ef4-137">Dans le centre d’administration de Microsoft Teams, sélectionnez **utilisateurs**, puis recherchez et activez la case à cocher pour 20 utilisateurs maximum qui doivent être mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="19ef4-137">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="19ef4-138">Dans le coin supérieur gauche de ListView, sélectionnez **modifier les paramètres** .</span><span class="sxs-lookup"><span data-stu-id="19ef4-138">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="19ef4-139">Dans le **volet modifier les paramètres** à droite, sous **mise à niveau**de Microsoft Teams, modifiez l’option demander \*\*\*\* à **l’utilisateur de Skype entreprise** de changer.</span><span class="sxs-lookup"><span data-stu-id="19ef4-139">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="19ef4-140">Remarque: si la valeur du mode de coexistence est «utiliser les paramètres à l’échelle de l’organisation», vous ne verrez pas ce commutateur, vous devez commencer par définir explicitement le mode de coexistence pour ces utilisateurs à la valeur par défaut de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="19ef4-140">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="19ef4-141">Par ailleurs, il est possible que vous puissiez facilement activer les notifications pour les groupes d’utilisateurs à la fois à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19ef4-141">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="19ef4-142">Étape 3: définir le mode de coexistence pour les utilisateurs uniquement dans teams</span><span class="sxs-lookup"><span data-stu-id="19ef4-142">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="19ef4-143">Lorsque vous êtes prêt à mettre à niveau les utilisateurs de l’onde actuelle pour utiliser teams comme seule application, définissez le mode de coexistence pour les utilisateurs sur équipes uniquement.</span><span class="sxs-lookup"><span data-stu-id="19ef4-143">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="19ef4-144">Si vous utilisez le centre d’administration de Microsoft Teams, vous pouvez configurer TeamsUpgradePolicy pour 20 utilisateurs à la fois:</span><span class="sxs-lookup"><span data-stu-id="19ef4-144">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="19ef4-145">Dans le centre d’administration de Microsoft Teams, sélectionnez **utilisateurs**, puis cochez la case jusqu’à 20 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="19ef4-145">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="19ef4-146">Dans le coin supérieur gauche de ListView, sélectionnez **modifier les paramètres** .</span><span class="sxs-lookup"><span data-stu-id="19ef4-146">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="19ef4-147">Dans le volet **modifier les paramètres** sur la droite, sous la section **mise à niveau** de Microsoft Teams, définissez le mode de coexistence sur **équipes uniquement** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="19ef4-147">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="19ef4-148">Par ailleurs, il est possible que vous puissiez constater qu’il est plus facile de mettre à niveau des groupes d’utilisateurs à la fois avec PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19ef4-148">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="19ef4-149">Étape 4: répéter les étapes 1-3 pour les vagues successives d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="19ef4-149">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="19ef4-150">Lorsque vous validez le mode de mise à niveau en équipes uniquement et que vous êtes prêt à développer, répétez les étapes précédentes pour ajouter TeamsOnly à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="19ef4-150">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="19ef4-151">Mise à niveau du système téléphonique et des équipes</span><span class="sxs-lookup"><span data-stu-id="19ef4-151">Phone System and Teams upgrade</span></span>

<span data-ttu-id="19ef4-152">Si votre déploiement de Skype entreprise Online inclut un système téléphonique avec des plans d’appels et que Microsoft est votre fournisseur de réseau téléphonique commuté (PSTN), la mise à niveau de vos utilisateurs vers teams fera automatiquement basculer les appels RTC entrants vers Teams.</span><span class="sxs-lookup"><span data-stu-id="19ef4-152">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="19ef4-153">Si votre déploiement de Skype entreprise Online inclut un système téléphonique avec la version Cloud Connector, voir [Considérations supplémentaires relatives au routage direct du système téléphonique](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="19ef4-153">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
