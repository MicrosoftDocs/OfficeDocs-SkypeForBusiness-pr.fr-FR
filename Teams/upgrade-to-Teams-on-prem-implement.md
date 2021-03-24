---
title: Stratégies de mise à niveau pour les administrateurs informatiques
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Cet article est pour les administrateurs informatiques et décrit les stratégies de mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 44c9559ca0576bb189b0934b9c487d5548de01bd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096068"
---
# <a name="upgrade-strategies-for-it-administrators"></a><span data-ttu-id="80b4c-103">Stratégies de mise à niveau pour les administrateurs informatiques</span><span class="sxs-lookup"><span data-stu-id="80b4c-103">Upgrade strategies for IT administrators</span></span>

<span data-ttu-id="80b4c-104">![Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation")</span><span class="sxs-lookup"><span data-stu-id="80b4c-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="80b4c-105">Cet article est pour les administrateurs informatiques qui souhaitent implémenter leur mise à niveau vers Teams à partir de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="80b4c-105">This article is for IT administrators who want to implement their upgrade to Teams from Skype for Business.</span></span>

<span data-ttu-id="80b4c-106">Avant d’implémenter votre mise à niveau, nous vous recommandons les articles suivants qui décrivent les concepts de mise à niveau et les comportements de coexistence importants :</span><span class="sxs-lookup"><span data-stu-id="80b4c-106">Before implementing your upgrade, we recommend the following articles which describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="80b4c-107">Comprendre la coexistence et l’interopérabilité de Microsoft Teams et De Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="80b4c-107">Understand Microsoft Teams and Skype for Business coexistence and interoperability</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="80b4c-108">Modes de coexistence - Référence</span><span class="sxs-lookup"><span data-stu-id="80b4c-108">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="80b4c-109">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="80b4c-109">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="80b4c-110">Options de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="80b4c-110">Upgrade options</span></span>

<span data-ttu-id="80b4c-111">Cette section explique comment implémenter votre mise à niveau à l’aide de l’une des options de mise à niveau suivantes :</span><span class="sxs-lookup"><span data-stu-id="80b4c-111">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="80b4c-112">Mise à niveau des fonctionnalités superposées (à l’aide du mode Îles)</span><span class="sxs-lookup"><span data-stu-id="80b4c-112">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="80b4c-113">Mise à niveau des fonctionnalités de sélection pour une organisation qui n’a pas encore commencé à utiliser Teams</span><span class="sxs-lookup"><span data-stu-id="80b4c-113">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="80b4c-114">Mise à niveau des fonctionnalités sélectionnées pour une organisation qui utilise déjà Teams en mode Îles</span><span class="sxs-lookup"><span data-stu-id="80b4c-114">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="80b4c-115">Si vous avez besoin d’informations supplémentaires sur les options, assurez-vous que vous avez déjà lu Le chemin de mise à niveau de Skype Entreprise [vers Teams.](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="80b4c-115">If you need more information about the options, make sure you have already read [Choose your upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="80b4c-116">Mise à niveau des fonctionnalités superposées (à l’aide du mode Îles)</span><span class="sxs-lookup"><span data-stu-id="80b4c-116">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="80b4c-117">Pour l’option de mise à niveau des fonctionnalités superposées :</span><span class="sxs-lookup"><span data-stu-id="80b4c-117">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="80b4c-118">Vous pouvez utiliser cette option si vous pouvez mettre à niveau rapidement l’ensemble de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="80b4c-118">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="80b4c-119">Étant donné qu’il existe un risque potentiel de confusion pour les utilisateurs finaux lors de l’exécution des deux clients, il est préférable de réduire la période pendant laquelle les utilisateurs doivent exécuter les deux clients.</span><span class="sxs-lookup"><span data-stu-id="80b4c-119">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="80b4c-120">Vous devez vous assurer que vos utilisateurs savent exécuter les deux clients.</span><span class="sxs-lookup"><span data-stu-id="80b4c-120">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="80b4c-121">Cette option est le modèle pré-standard et ne nécessite aucune action de l’administrateur pour prendre en charge Teams, sauf pour affecter la licence Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="80b4c-121">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="80b4c-122">Si vos utilisateurs ont déjà Skype Entreprise Online, il est possible que vous soyez déjà dans ce modèle.</span><span class="sxs-lookup"><span data-stu-id="80b4c-122">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="80b4c-123">Il peut être difficile de sortir du mode de fonctionnalités superposées et de passer à TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="80b4c-123">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="80b4c-124">Étant donné que les utilisateurs mis à niveau communiquent uniquement via Teams, tous les autres utilisateurs de l’organisation qui communiquent avec cet utilisateur doivent utiliser Teams.</span><span class="sxs-lookup"><span data-stu-id="80b4c-124">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="80b4c-125">Si vous avez des utilisateurs qui n’ont pas commencé à utiliser Teams, ils sont exposés à des messages manquants.</span><span class="sxs-lookup"><span data-stu-id="80b4c-125">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="80b4c-126">De plus, ils ne voient pas les utilisateurs de TeamsOnly en ligne dans Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="80b4c-126">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="80b4c-127">Certaines organisations choisissent d’opter pour une mise à niveau à l’échelle du client à l’aide de la stratégie globale du client afin d’éviter ce problème, ce qui nécessite toutefois une planification préalable et attendre que tous les utilisateurs soient prêts à mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="80b4c-127">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="80b4c-128">Mise à niveau des fonctionnalités de sélection pour une organisation qui n’a pas encore commencé à utiliser Teams</span><span class="sxs-lookup"><span data-stu-id="80b4c-128">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="80b4c-129">Si votre organisation n’a pas encore d’utilisateurs actifs dans Teams, la première étape consiste à définir la stratégie par défaut à l’échelle du client pour TeamsUpgradePolicy sur l’un des modes Skype Entreprise, par exemple, SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="80b4c-129">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="80b4c-130">Les utilisateurs qui n’ont pas encore commencé à utiliser Teams ne remarqueront aucune différence de comportement.</span><span class="sxs-lookup"><span data-stu-id="80b4c-130">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="80b4c-131">Toutefois, la définition de cette stratégie au niveau du client permet de commencer la mise à niveau des utilisateurs vers le mode TeamsOnly et garantit que les utilisateurs mis à niveau peuvent toujours communiquer avec des utilisateurs qui ne sont pas mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="80b4c-131">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="80b4c-132">Après avoir identifié vos utilisateurs pilotes, vous pouvez les mettre à niveau vers TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="80b4c-132">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="80b4c-133">S’ils sont locaux, utilisez Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="80b4c-133">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="80b4c-134">S’ils sont en ligne, affectez-les simplement en mode TeamsOnly à l’aide de Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="80b4c-134">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="80b4c-135">Par défaut, les réunions Skype Entreprise programmées par ces utilisateurs sont migrées vers Teams.</span><span class="sxs-lookup"><span data-stu-id="80b4c-135">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="80b4c-136">Voici les principales commandes :</span><span class="sxs-lookup"><span data-stu-id="80b4c-136">Following are the key commands:</span></span>

1. <span data-ttu-id="80b4c-137">Définissez le mode SfbWithTeamsCollab à l’échelle du client comme suit :</span><span class="sxs-lookup"><span data-stu-id="80b4c-137">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="80b4c-138">Mettre à niveau les utilisateurs pilotes vers TeamsOnly comme suit :</span><span class="sxs-lookup"><span data-stu-id="80b4c-138">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="80b4c-139">Pour un utilisateur en ligne :</span><span class="sxs-lookup"><span data-stu-id="80b4c-139">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="80b4c-140">Pour un utilisateur sur site :</span><span class="sxs-lookup"><span data-stu-id="80b4c-140">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="80b4c-141">Remarques</span><span class="sxs-lookup"><span data-stu-id="80b4c-141">Notes</span></span>
 
- <span data-ttu-id="80b4c-142">Au lieu de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab, vous pouvez la définir sur SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="80b4c-142">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="80b4c-143">Ainsi, tous les utilisateurs peuvent planifier toutes les nouvelles réunions dans Teams.</span><span class="sxs-lookup"><span data-stu-id="80b4c-143">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="80b4c-144">`Move-CsUser` est une cmdlet dans les outils locaux.</span><span class="sxs-lookup"><span data-stu-id="80b4c-144">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="80b4c-145">Le `MoveToTeams` basculement nécessite Skype Entreprise Server 2019 ou Skype Entreprise Server 2015 avec CU8 ou une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="80b4c-145">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="80b4c-146">Si vous utilisez une version antérieure, vous pouvez d’abord déplacer l’utilisateur vers Skype Entreprise Online, puis lui octroyer le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="80b4c-146">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="80b4c-147">Par défaut, les réunions Skype Entreprise sont migrées vers Teams lors de la mise à niveau vers le mode TeamsOnly ou lors de l’affectation du mode SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="80b4c-147">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="80b4c-148">Le diagramme ci-dessous présente les phases conceptuelles de la mise à niveau des fonctionnalités de sélection pour une organisation sans utilisation préalable de Teams.</span><span class="sxs-lookup"><span data-stu-id="80b4c-148">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="80b4c-149">La hauteur des barres représente le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="80b4c-149">The height of the bars represents number of users.</span></span> <span data-ttu-id="80b4c-150">Pendant toute phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="80b4c-150">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="80b4c-151">Les utilisateurs de Skype Entreprise communiquent avec les utilisateurs de TeamsOnly à l’aide d’Interop, et inversement.</span><span class="sxs-lookup"><span data-stu-id="80b4c-151">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="80b4c-152">Les utilisateurs en mode Îles doivent s’assurer d’exécuter les deux clients.</span><span class="sxs-lookup"><span data-stu-id="80b4c-152">Users in Islands mode must be sure to run both clients.</span></span>

![Diagramme montrant la mise à niveau des fonctionnalités de sélection sans utilisation préalable de Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="80b4c-154">Mise à niveau des fonctionnalités sélectionnées pour une organisation qui utilise déjà Teams en mode Îles</span><span class="sxs-lookup"><span data-stu-id="80b4c-154">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="80b4c-155">Si certains utilisateurs de votre organisation utilisent activement Teams en mode Îles, vous ne souhaitez probablement pas supprimer la fonctionnalité des utilisateurs existants.</span><span class="sxs-lookup"><span data-stu-id="80b4c-155">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="80b4c-156">Par conséquent, une étape supplémentaire est requise avant de modifier la stratégie à l’échelle du client.</span><span class="sxs-lookup"><span data-stu-id="80b4c-156">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="80b4c-157">La solution consiste à « transformer » ces utilisateurs teams existants en mode Islands, avant de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="80b4c-157">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="80b4c-158">Une fois que vous aurez effectué cela, vous pourrez procéder au déploiement comme ci-dessus. Toutefois, vous aurez deux groupes d’utilisateurs qui vont passer à TeamsOnly : les utilisateurs qui étaient actifs dans Teams seront en mode Îles et les autres utilisateurs seront en mode SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="80b4c-158">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="80b4c-159">Vous pouvez progressivement déplacer ces utilisateurs vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="80b4c-159">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="80b4c-160">Recherchez les utilisateurs actifs dans Teams comme suit :</span><span class="sxs-lookup"><span data-stu-id="80b4c-160">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="80b4c-161">Dans le centre d’administration Microsoft 365, dans le panneau de navigation gauche, allez dans Rapports, puis Utilisation.</span><span class="sxs-lookup"><span data-stu-id="80b4c-161">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="80b4c-162">Dans ladown « Sélectionner un rapport », sélectionnez Microsoft Teams, puis Activité de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="80b4c-162">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="80b4c-163">Vous aurez ainsi une table exportable d’utilisateurs ayant été actifs dans Teams.</span><span class="sxs-lookup"><span data-stu-id="80b4c-163">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="80b4c-164">Cliquez sur Exporter, ouvrez Excel et filtrez pour afficher uniquement les utilisateurs actifs dans Teams.</span><span class="sxs-lookup"><span data-stu-id="80b4c-164">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="80b4c-165">Pour chaque utilisateur actif de Teams trouvé à l’étape 1, affectez-lui le mode Îles dans une powershell distante.</span><span class="sxs-lookup"><span data-stu-id="80b4c-165">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="80b4c-166">Cela vous permet de passer à l’étape suivante et de ne pas modifier l’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="80b4c-166">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="80b4c-167">Définissez la stratégie à l’échelle du client sur SfbWithTeamsCollab :</span><span class="sxs-lookup"><span data-stu-id="80b4c-167">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="80b4c-168">Mettre à niveau les utilisateurs sélectionnés vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="80b4c-168">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="80b4c-169">Vous pouvez choisir de mettre à niveau soit les utilisateurs en mode Islands, soit en mode SfbWithTeamsCollab, même si vous pouvez d’abord hiérarchiser la mise à niveau des utilisateurs en mode Islands afin de minimiser la confusion potentielle qui peut survenir lorsque les utilisateurs sont en mode Islands.</span><span class="sxs-lookup"><span data-stu-id="80b4c-169">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="80b4c-170">Pour les utilisateurs homed in Skype Entreprise Online :</span><span class="sxs-lookup"><span data-stu-id="80b4c-170">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="80b4c-171">Pour les utilisateurs homed in Skype Entreprise Server sur site :</span><span class="sxs-lookup"><span data-stu-id="80b4c-171">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="80b4c-172">Le diagramme ci-dessous montre les phases conceptuelles d’une transition de fonctionnalités sélectionnées dans laquelle les utilisateurs d’îles actives sont au début.</span><span class="sxs-lookup"><span data-stu-id="80b4c-172">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="80b4c-173">La hauteur des barres représente le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="80b4c-173">The height of the bars represents the number of users.</span></span> <span data-ttu-id="80b4c-174">Pendant toute phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="80b4c-174">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="80b4c-175">Les utilisateurs de Skype Entreprise communiquent avec les utilisateurs de TeamsOnly à l’aide d’interop, et vice versa.</span><span class="sxs-lookup"><span data-stu-id="80b4c-175">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Diagramme montrant la mise à niveau des fonctionnalités sélectionnées avec des utilisateurs actifs en mode Îles](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="80b4c-177">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="80b4c-177">Related links</span></span>

[<span data-ttu-id="80b4c-178">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="80b4c-178">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="80b4c-179">Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="80b4c-179">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="80b4c-180">Déplacer des utilisateurs entre l’environnement local et le cloud</span><span class="sxs-lookup"><span data-stu-id="80b4c-180">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="80b4c-181">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="80b4c-181">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="80b4c-182">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="80b4c-182">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="80b4c-183">Utilisation du service Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="80b4c-183">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)