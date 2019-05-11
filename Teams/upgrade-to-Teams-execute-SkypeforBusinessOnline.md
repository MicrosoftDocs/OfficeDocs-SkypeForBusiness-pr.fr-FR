---
title: Mise à niveau Skype pour les entreprises en ligne pour les équipes Microsoft | Déployer
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considérations relatives à la mise à niveau pour les équipes de Skype pour Business Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6748397c354f9238282f9646388993fc0e9f7b88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902718"
---
<span data-ttu-id="46216-103">![Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation] (media/upgrade-banner-deployment.png "Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation")</span><span class="sxs-lookup"><span data-stu-id="46216-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="46216-104">Cet article fait partie de la phase de déploiement et l’implémentation de votre parcours de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="46216-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="46216-105">Avant de continuer, vérifiez que vous avez effectué les activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="46216-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="46216-106">Inscrit les parties prenantes du projet</span><span class="sxs-lookup"><span data-stu-id="46216-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="46216-107">Définies par l’étendue de votre projet</span><span class="sxs-lookup"><span data-stu-id="46216-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="46216-108">Comprendre la coexistence et l’interopérabilité de Skype pour professionnels et les équipes</span><span class="sxs-lookup"><span data-stu-id="46216-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="46216-109">Choisi votre parcours de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="46216-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="46216-110">Préparer votre environnement</span><span class="sxs-lookup"><span data-stu-id="46216-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="46216-111">Préparation de votre organisation</span><span class="sxs-lookup"><span data-stu-id="46216-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="46216-112">Mené un projet pilote</span><span class="sxs-lookup"><span data-stu-id="46216-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="46216-113">Mise à niveau de Skype Entreprise Online vers Teams</span><span class="sxs-lookup"><span data-stu-id="46216-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="46216-114">Suivez les instructions de cet article si vous avez déployé entièrement Skype pour Business Online et que vous souhaitez mettre à niveau vos utilisateurs à partir de Skype pour les entreprises aux équipes.</span><span class="sxs-lookup"><span data-stu-id="46216-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="46216-115">Vous pouvez mettre à niveau les utilisateurs sélectivement ou tout en, en fonction de la mise à niveau de route que votre organisation a choisi, en affectant le mode de mise à niveau et la coexistence appropriée à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="46216-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="46216-116">Affecter le mode de mise à niveau et de coexistence</span><span class="sxs-lookup"><span data-stu-id="46216-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="46216-117">Vous pouvez mettre à niveau vos utilisateurs en mode TeamsOnly en affectant l’instance UpgradeToTeams de TeamsUpgradePolicy, qui peut être effectuée à l’aide du centre d’administration Microsoft Teams ou un Skype pour la session Windows Powershell à distance Business.</span><span class="sxs-lookup"><span data-stu-id="46216-117">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="46216-118">Vous pouvez le faire par utilisateur, soit sur un client à l’échelle si vous souhaitez de mise à niveau du client entier en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="46216-118">You can do this either on a per user basis, or on a tenant-wide basis if you want to ugprade the entire tenant in one step.</span></span> 

<span data-ttu-id="46216-119">Pour plus d’informations, voir [configuration de votre coexistence et de paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence) et [TeamsUpgradePolicy : gestion de migration et coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="46216-119">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="46216-120">Mettre à niveau simultanément tous les utilisateurs à des équipes</span><span class="sxs-lookup"><span data-stu-id="46216-120">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="46216-121">Suivez ces étapes pour mettre à niveau tous les utilisateurs à des équipes en même temps.</span><span class="sxs-lookup"><span data-stu-id="46216-121">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="46216-122">Étape 1 : Avertir les utilisateurs de la modification (facultative)</span><span class="sxs-lookup"><span data-stu-id="46216-122">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="46216-123">Dans le centre d’administration Microsoft Teams, sélectionnez **paramètres à l’échelle de la société** > **équipes de mise à niveau**.</span><span class="sxs-lookup"><span data-stu-id="46216-123">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="46216-124">Sous **mode de Coexistence**, remplacez le commutateur **Skype de notification pour les utilisateurs qu’une mise à niveau pour les équipes est disponible** **sur**.</span><span class="sxs-lookup"><span data-stu-id="46216-124">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="46216-125">Étape 2 : Définir le mode de coexistence pour TeamsOnly pour l’organisation</span><span class="sxs-lookup"><span data-stu-id="46216-125">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="46216-126">Dans le centre d’administration Microsoft Teams, sélectionnez **paramètres de l’organisation**.</span><span class="sxs-lookup"><span data-stu-id="46216-126">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="46216-127">Sélectionnez mode **d’Équipes uniquement** à partir de la liste déroulante **mode de Coexistence** .</span><span class="sxs-lookup"><span data-stu-id="46216-127">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="46216-128">Mise à niveau par étapes</span><span class="sxs-lookup"><span data-stu-id="46216-128">Upgrade users in stages</span></span>

<span data-ttu-id="46216-129">Si vous souhaitez mettre à niveau progressive vos utilisateurs vers TeamsOnly, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="46216-129">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="46216-130">Étape 1 : Identifier les groupes d’utilisateurs pour la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="46216-130">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="46216-131">Souvent, les organisations peuvent choisir de mettre à niveau leurs organisations vagues de réussite des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="46216-131">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="46216-132">Vous souhaiterez identifier ces utilisateurs en premier afin que vous pouvez facilement les rechercher dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="46216-132">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="46216-133">Vous pouvez également utiliser PowerShell pour effectuer cette opération plus efficacement.</span><span class="sxs-lookup"><span data-stu-id="46216-133">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="46216-134">Une fois que vous avez identifié l’ensemble des utilisateurs d’une vague de mise à niveau donnée, continuez avec les étapes restantes.</span><span class="sxs-lookup"><span data-stu-id="46216-134">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a><span data-ttu-id="46216-135">Étape 2 : Configurer la notification pour les utilisateurs de la vague de mise à niveau en cours (facultatif)</span><span class="sxs-lookup"><span data-stu-id="46216-135">Step 2: Set notification for the users in the current ugprade wave (optional)</span></span>

<span data-ttu-id="46216-136">Si vous utilisez le centre d’administration Microsoft Teams, vous pouvez configurer pour l’utilisateur jusqu'à 20 des TeamsUpgradePolicy :</span><span class="sxs-lookup"><span data-stu-id="46216-136">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="46216-137">Dans le centre d’administration Microsoft Teams, sélectionnez **les utilisateurs**et de rechercher et de sélectionner plusieurs la case à cocher pour jusqu'à 20 utilisateurs qui doivent être mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="46216-137">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="46216-138">Dans le coin supérieur gauche de la liste affichée, sélectionnez **Modifier les paramètres** .</span><span class="sxs-lookup"><span data-stu-id="46216-138">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="46216-139">Dans le volet de droite, sous **mise à niveau des équipes**, **Modifier les paramètres** modifier commutateur **notifier le Skype pour utilisateur professionnel** **activé**.</span><span class="sxs-lookup"><span data-stu-id="46216-139">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="46216-140">Remarque : Si la valeur du mode de coexistence est « paramètres d’utilisation à l’échelle de l’organisation », vous ne verrez pas ce commutateur, il vous faudra donc tout d’abord définir explicitement le mode de Coexistence pour les utilisateurs à tout ce qui est la valeur par défaut pour l’organigramme.</span><span class="sxs-lookup"><span data-stu-id="46216-140">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="46216-141">Autrement, il peut plus facile activer les notifications pour les groupes d’utilisateurs à la fois à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46216-141">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="46216-142">Étape 3 : Définir le mode de coexistence pour les utilisateurs à des équipes uniquement</span><span class="sxs-lookup"><span data-stu-id="46216-142">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="46216-143">Lorsque vous êtes prêt à mettre à niveau les utilisateurs de la génération actuelle pour utiliser des équipes comme leur application uniquement, définissez le mode de Coexistence pour les utilisateurs à des équipes uniquement.</span><span class="sxs-lookup"><span data-stu-id="46216-143">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="46216-144">Si vous utilisez le centre d’administration Microsoft Teams, vous pouvez configurer pour l’utilisateur jusqu'à 20 des TeamsUpgradePolicy :</span><span class="sxs-lookup"><span data-stu-id="46216-144">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="46216-145">Dans le centre d’administration Microsoft Teams, sélectionnez **les utilisateurs**, puis activez la case à cocher pour jusqu'à 20 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="46216-145">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="46216-146">Dans le coin supérieur gauche de la liste affichée, sélectionnez **Modifier les paramètres** .</span><span class="sxs-lookup"><span data-stu-id="46216-146">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="46216-147">Dans le volet **Modifier les paramètres** sur la droite, sous la section **mise à niveau des équipes** , définissez le mode de coexistence pour **Les équipes uniquement** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="46216-147">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="46216-148">Sinon, vous souhaiterez plus faciles à mettre à niveau des groupes d’utilisateurs à la fois à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46216-148">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="46216-149">Étape 4 : Répétez les étapes 1 à 3 pour par vagues successives d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="46216-149">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="46216-150">Lorsque vous validez votre mise à niveau vers le mode équipes uniquement et que vous êtes prêt à développer, répétez les étapes précédentes pour appliquer TeamsOnly à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="46216-150">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="46216-151">Mise à niveau système téléphonique et les équipes</span><span class="sxs-lookup"><span data-stu-id="46216-151">Phone System and Teams upgrade</span></span>

<span data-ttu-id="46216-152">Si votre Skype pour le déploiement d’entreprise en ligne inclut le système téléphonique avec des Plans de l’appel et Microsoft est votre fournisseur de réseau téléphonique commuté, la mise à niveau de vos utilisateurs à des équipes passera automatiquement PSTN entrant aux équipes de l’appel.</span><span class="sxs-lookup"><span data-stu-id="46216-152">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="46216-153">Si votre Skype pour le déploiement d’entreprise en ligne comprend un système téléphonique avec le nuage connecteur Edition, consultez les [Considérations supplémentaires pour le routage d’un système téléphonique directe](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="46216-153">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
