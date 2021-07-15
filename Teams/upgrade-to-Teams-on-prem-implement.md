---
title: Stratégies de mise à niveau pour les administrateurs informatiques
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Cet article est pour les administrateurs informatiques et décrit les stratégies d’implémentation de leur mise à niveau Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f11d14bc7bf302a864afe3062ef8f2bb8eccd7da
ms.sourcegitcommit: e19fdedca6573110d08c7d114e05b84779e36b58
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437641"
---
# <a name="upgrade-strategies-for-it-administrators"></a><span data-ttu-id="b645c-103">Stratégies de mise à niveau pour les administrateurs informatiques</span><span class="sxs-lookup"><span data-stu-id="b645c-103">Upgrade strategies for IT administrators</span></span>

<span data-ttu-id="b645c-104">![Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation")</span><span class="sxs-lookup"><span data-stu-id="b645c-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="b645c-105">Cet article est pour les administrateurs informatiques qui souhaitent implémenter leur mise à niveau vers Teams à partir Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="b645c-105">This article is for IT administrators who want to implement their upgrade to Teams from Skype for Business.</span></span>

<span data-ttu-id="b645c-106">Avant d’implémenter votre mise à niveau, nous vous recommandons les articles suivants qui décrivent les concepts de mise à niveau et les comportements de coexistence importants :</span><span class="sxs-lookup"><span data-stu-id="b645c-106">Before implementing your upgrade, we recommend the following articles which describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="b645c-107">Comprendre Microsoft Teams coexistence et Skype Entreprise interopérabilité</span><span class="sxs-lookup"><span data-stu-id="b645c-107">Understand Microsoft Teams and Skype for Business coexistence and interoperability</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="b645c-108">Modes de coexistence - Référence</span><span class="sxs-lookup"><span data-stu-id="b645c-108">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="b645c-109">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="b645c-109">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="b645c-110">Options de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="b645c-110">Upgrade options</span></span>

<span data-ttu-id="b645c-111">Cette section explique comment implémenter votre mise à niveau à l’aide de l’une des options de mise à niveau suivantes :</span><span class="sxs-lookup"><span data-stu-id="b645c-111">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="b645c-112">Mise à niveau des fonctionnalités superposées (à l’aide du mode Îles)</span><span class="sxs-lookup"><span data-stu-id="b645c-112">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="b645c-113">Mise à niveau des fonctionnalités sélectionnées pour une organisation qui n’a pas encore commencé à utiliser Teams</span><span class="sxs-lookup"><span data-stu-id="b645c-113">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="b645c-114">Mise à niveau des fonctionnalités sélectionnées pour une organisation qui utilise déjà Teams en mode Îles</span><span class="sxs-lookup"><span data-stu-id="b645c-114">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="b645c-115">Si vous avez besoin d’informations supplémentaires sur les options, assurez-vous que vous avez déjà lu Choisir votre chemin de mise à niveau [d’Skype Entreprise à Teams.](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b645c-115">If you need more information about the options, make sure you have already read [Choose your upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="b645c-116">Mise à niveau des fonctionnalités superposées (à l’aide du mode Îles)</span><span class="sxs-lookup"><span data-stu-id="b645c-116">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="b645c-117">Pour l’option de mise à niveau des fonctionnalités superposées :</span><span class="sxs-lookup"><span data-stu-id="b645c-117">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="b645c-118">Envisagez cette option si vous pouvez mettre à niveau rapidement l’ensemble de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b645c-118">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="b645c-119">Étant donné qu’il existe un risque potentiel de confusion pour les utilisateurs finaux lors de l’exécution des deux clients, il est préférable de réduire la période pendant laquelle les utilisateurs doivent exécuter les deux clients.</span><span class="sxs-lookup"><span data-stu-id="b645c-119">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="b645c-120">Vous devez vous assurer que vos utilisateurs savent exécuter les deux clients.</span><span class="sxs-lookup"><span data-stu-id="b645c-120">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="b645c-121">Cette option est le modèle pré-standard et ne nécessite aucune action de l’administrateur pour commencer à Teams à l’exception de l’attribution de la licence Microsoft 365 ou Office 365 licence.</span><span class="sxs-lookup"><span data-stu-id="b645c-121">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="b645c-122">Si vos utilisateurs ont déjà Skype Entreprise Online, vous êtes peut-être déjà dans ce modèle.</span><span class="sxs-lookup"><span data-stu-id="b645c-122">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="b645c-123">Il peut être difficile de sortir du mode de fonctionnalités superposées et de passer à TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="b645c-123">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="b645c-124">Étant donné que les utilisateurs mis à niveau communiquent uniquement via Teams, tous les autres utilisateurs de l’organisation qui communiquent avec cet utilisateur doivent utiliser Teams.</span><span class="sxs-lookup"><span data-stu-id="b645c-124">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="b645c-125">Si vos utilisateurs n’ont pas commencé à utiliser Teams, ils sont exposés à des messages manquants.</span><span class="sxs-lookup"><span data-stu-id="b645c-125">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="b645c-126">De plus, ils ne voient pas les utilisateurs de TeamsOnly en ligne Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="b645c-126">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="b645c-127">Certaines organisations choisissent d’opter pour une mise à niveau à l’échelle du client à l’aide de la stratégie globale du client afin d’éviter ce problème, ce qui nécessite toutefois une planification préalable, ainsi que l’attente jusqu’à ce que tous les utilisateurs soient prêts à être mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="b645c-127">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="b645c-128">Mise à niveau des fonctionnalités sélectionnées pour une organisation qui n’a pas encore commencé à utiliser Teams</span><span class="sxs-lookup"><span data-stu-id="b645c-128">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="b645c-129">Si votre organisation n’a pas encore d’utilisateurs actifs dans Teams, la première étape consiste à définir la stratégie par défaut à l’échelle du client pour TeamsUpgradePolicy sur l’un des modes Skype Entreprise, par exemple, SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="b645c-129">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="b645c-130">Les utilisateurs qui n’ont pas encore commencé à Teams remarque aucune différence de comportement.</span><span class="sxs-lookup"><span data-stu-id="b645c-130">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="b645c-131">Toutefois, la définition de cette stratégie au niveau du client permet de commencer la mise à niveau des utilisateurs vers le mode TeamsOnly et garantit que les utilisateurs mis à niveau peuvent toujours communiquer avec des utilisateurs qui ne sont pas mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="b645c-131">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="b645c-132">Après avoir identifié vos utilisateurs pilotes, vous pouvez les mettre à niveau vers TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="b645c-132">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="b645c-133">S’ils sont locaux, utilisez Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="b645c-133">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="b645c-134">S’ils sont en ligne, affectez-les simplement en mode TeamsOnly à l’aide de Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="b645c-134">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="b645c-135">Par défaut, les Skype Entreprise de réunion programmées par ces utilisateurs sont migrées vers Teams.</span><span class="sxs-lookup"><span data-stu-id="b645c-135">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="b645c-136">Voici les principales commandes :</span><span class="sxs-lookup"><span data-stu-id="b645c-136">Following are the key commands:</span></span>

1. <span data-ttu-id="b645c-137">Définissez le mode SfbWithTeamsCollab à l’échelle du client comme suit :</span><span class="sxs-lookup"><span data-stu-id="b645c-137">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="b645c-138">Mettre à niveau les utilisateurs pilotes vers TeamsOnly comme suit :</span><span class="sxs-lookup"><span data-stu-id="b645c-138">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="b645c-139">Pour un utilisateur en ligne :</span><span class="sxs-lookup"><span data-stu-id="b645c-139">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="b645c-140">Pour un utilisateur sur site :</span><span class="sxs-lookup"><span data-stu-id="b645c-140">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="b645c-141">Remarques</span><span class="sxs-lookup"><span data-stu-id="b645c-141">Notes</span></span>
 
- <span data-ttu-id="b645c-142">Au lieu de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab, vous pouvez la définir sur SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="b645c-142">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="b645c-143">Ainsi, tous les utilisateurs peuvent planifier toutes les nouvelles réunions dans Teams.</span><span class="sxs-lookup"><span data-stu-id="b645c-143">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="b645c-144">Par défaut, Skype Entreprise réunions sont migrées vers Teams lors de la mise à niveau vers le mode TeamsOnly ou lors de l’affectation du mode SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="b645c-144">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

> [!NOTE]
> <span data-ttu-id="b645c-145">En préparation de la mise à l’abandon prochaine d Skype Entreprise Online, Microsoft a simplifié la façon dont les organisations passeront à l’Teams.</span><span class="sxs-lookup"><span data-stu-id="b645c-145">In preparation for the upcoming retirement of Skype for Business Online, Microsoft has simplified how organizations move to Teams.</span></span> <span data-ttu-id="b645c-146">Il n’est plus nécessaire de spécifier le commutateur pour déplacer les utilisateurs directement du site `-MoveToTeams` `Move-CsUser` directement vers TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="b645c-146">It is no longer required to specify the `-MoveToTeams` switch in `Move-CsUser` to move users directly from on-premises directly to TeamsOnly.</span></span> <span data-ttu-id="b645c-147">Auparavant, si ce commutateur n’était pas spécifié, les utilisateurs passaient de l’domicile des utilisateurs à Skype Entreprise Server en local vers Skype Entreprise Online, et leur mode restait inchangé.</span><span class="sxs-lookup"><span data-stu-id="b645c-147">Previously, if this switch was not specified, users transitioned from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remained unchanged.</span></span> <span data-ttu-id="b645c-148">Désormais, lors du déplacement d’un utilisateur du cloud local vers le cloud, les utilisateurs sont automatiquement affectés au mode TeamsOnly et leurs réunions à partir du site sont automatiquement converties en réunions Teams de façon automatique, comme si le commutateur était spécifié ou `Move-CsUser` `-MoveToTeams switch had been specified` non.</span><span class="sxs-lookup"><span data-stu-id="b645c-148">Now when moving a user from on-premises to the cloud with `Move-CsUser`, users are automatically assigned TeamsOnly mode and their meetings from on-premises are automtically converted to Teams meetings, just as if the `-MoveToTeams switch had been specified`, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="b645c-149">Ce comportement est disponible sur toutes les versions de Skype Entreprise Server et Lync Server 2013 (qui n’ont jamais été pris en `-MoveToTeams` charge).</span><span class="sxs-lookup"><span data-stu-id="b645c-149">This behavior is available on all versions of Skype For Business Server and Lync Server 2013 (which never had support for `-MoveToTeams`).</span></span>

<span data-ttu-id="b645c-150">Le diagramme ci-dessous montre les phases conceptuelles de la mise à niveau des fonctionnalités de sélection pour une organisation sans utilisation préalable d’Teams.</span><span class="sxs-lookup"><span data-stu-id="b645c-150">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="b645c-151">La hauteur des barres représente le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b645c-151">The height of the bars represents number of users.</span></span> <span data-ttu-id="b645c-152">Pendant toute phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="b645c-152">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="b645c-153">Skype Entreprise communiquent avec les utilisateurs de TeamsOnly à l’aide d’Interop, et inversement.</span><span class="sxs-lookup"><span data-stu-id="b645c-153">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="b645c-154">Les utilisateurs en mode Îles doivent s’assurer d’exécuter les deux clients.</span><span class="sxs-lookup"><span data-stu-id="b645c-154">Users in Islands mode must be sure to run both clients.</span></span>

![Diagramme montrant la mise à niveau des fonctionnalités sélectionnées sans utilisation préalable Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="b645c-156">Mise à niveau des fonctionnalités sélectionnées pour une organisation qui utilise déjà Teams en mode Îles</span><span class="sxs-lookup"><span data-stu-id="b645c-156">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="b645c-157">Si certains utilisateurs de votre organisation utilisent activement Teams en mode Îles, vous ne souhaitez probablement pas supprimer la fonctionnalité des utilisateurs existants.</span><span class="sxs-lookup"><span data-stu-id="b645c-157">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="b645c-158">Par conséquent, une étape supplémentaire est requise avant de modifier la stratégie à l’échelle du client.</span><span class="sxs-lookup"><span data-stu-id="b645c-158">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="b645c-159">La solution consiste à « transformer » ces utilisateurs Teams existants en mode Îles, avant de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="b645c-159">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="b645c-160">Une fois que vous aurez effectué cela, vous pourrez procéder au déploiement comme ci-dessus. Toutefois, vous aurez deux groupes d’utilisateurs qui vont passer à TeamsOnly : les utilisateurs qui étaient actifs dans Teams seront en mode Îles et les autres utilisateurs seront en mode SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="b645c-160">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="b645c-161">Vous pouvez progressivement déplacer ces utilisateurs vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="b645c-161">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="b645c-162">Recherchez les utilisateurs actifs dans Teams de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="b645c-162">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="b645c-163">À partir Centre d’administration Microsoft 365, dans la barre de navigation gauche, allez dans Rapports, puis Utilisation.</span><span class="sxs-lookup"><span data-stu-id="b645c-163">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="b645c-164">Dans la sous-Microsoft Teams « Sélectionner un rapport », sélectionnez Activité de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b645c-164">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="b645c-165">Vous aurez ainsi une table exportable d’utilisateurs qui ont été actifs dans Teams.</span><span class="sxs-lookup"><span data-stu-id="b645c-165">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="b645c-166">Cliquez sur Exporter, ouvrez Excel et filtrez pour afficher uniquement les utilisateurs actifs dans Teams.</span><span class="sxs-lookup"><span data-stu-id="b645c-166">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="b645c-167">Pour chaque utilisateur actif Teams l’étape 1, affectez-leur le mode Îles dans Une PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="b645c-167">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="b645c-168">Cela vous permet de passer à l’étape suivante et de ne pas modifier l’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b645c-168">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="b645c-169">Définissez la stratégie à l’échelle du client sur SfbWithTeamsCollab :</span><span class="sxs-lookup"><span data-stu-id="b645c-169">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="b645c-170">Mettre à niveau les utilisateurs sélectionnés vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="b645c-170">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="b645c-171">Vous pouvez choisir de mettre à niveau soit les utilisateurs en mode Islands, soit en mode SfbWithTeamsCollab, même si vous pouvez d’abord hiérarchiser la mise à niveau des utilisateurs en mode Islands afin de minimiser la confusion potentielle qui peut survenir lorsque les utilisateurs sont en mode Islands.</span><span class="sxs-lookup"><span data-stu-id="b645c-171">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="b645c-172">Pour les utilisateurs homed in Skype Entreprise Online :</span><span class="sxs-lookup"><span data-stu-id="b645c-172">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="b645c-173">Pour les utilisateurs homed in Skype Entreprise Server local :</span><span class="sxs-lookup"><span data-stu-id="b645c-173">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="b645c-174">Le diagramme ci-dessous montre les phases conceptuelles d’une transition de fonctionnalités sélectionnées dans laquelle les utilisateurs d’îles actives sont au début.</span><span class="sxs-lookup"><span data-stu-id="b645c-174">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="b645c-175">La hauteur des barres représente le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b645c-175">The height of the bars represents the number of users.</span></span> <span data-ttu-id="b645c-176">Pendant toute phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="b645c-176">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="b645c-177">Skype Entreprise communiquent avec les utilisateurs de TeamsOnly à l’aide d’interop, et inversement.</span><span class="sxs-lookup"><span data-stu-id="b645c-177">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Diagramme montrant la mise à niveau des fonctionnalités sélectionnées avec des utilisateurs actifs en mode Îles](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="b645c-179">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="b645c-179">Related links</span></span>

[<span data-ttu-id="b645c-180">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="b645c-180">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="b645c-181">Configurer la connectivité hybride entre les Skype Entreprise Server et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="b645c-181">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="b645c-182">Déplacer des utilisateurs entre l’environnement local et le cloud</span><span class="sxs-lookup"><span data-stu-id="b645c-182">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="b645c-183">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="b645c-183">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="b645c-184">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="b645c-184">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="b645c-185">Utilisation du service Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="b645c-185">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
