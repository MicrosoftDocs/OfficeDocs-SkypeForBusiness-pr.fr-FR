---
title: Mise à niveau vers Teams à partir d’un déploiement local de Skype Entreprise - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bec5c2b10dc2e09092cd7c26284c04868982e287
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533601"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="8dcea-103">Implémenter la mise à niveau de Skype Entreprise vers Teams &mdash; pour les administrateurs informatiques</span><span class="sxs-lookup"><span data-stu-id="8dcea-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="8dcea-104">Cet article décrit comment implémenter votre mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="8dcea-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="8dcea-105">Cet article est le cinquième de ceux qui décrivent les concepts de mise à niveau et d’implémentation pour les administrateurs informatiques.</span><span class="sxs-lookup"><span data-stu-id="8dcea-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="8dcea-106">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="8dcea-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="8dcea-107">Méthodes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="8dcea-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="8dcea-108">Outils de gestion de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="8dcea-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="8dcea-109">Autres éléments à prendre en considération pour les organisations avec Skype Entreprise sur site</span><span class="sxs-lookup"><span data-stu-id="8dcea-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="8dcea-110">**Implémenter votre mise à** niveau (cet article)</span><span class="sxs-lookup"><span data-stu-id="8dcea-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="8dcea-111">Considérations sur le réseau téléphonique commuté (PSTN)</span><span class="sxs-lookup"><span data-stu-id="8dcea-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="8dcea-112">De plus, les articles suivants décrivent les concepts de mise à niveau et les comportements de coexistence importants :</span><span class="sxs-lookup"><span data-stu-id="8dcea-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="8dcea-113">Coexistence de Teams et de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="8dcea-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="8dcea-114">Modes de coexistence - Référence</span><span class="sxs-lookup"><span data-stu-id="8dcea-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="8dcea-115">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="8dcea-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="8dcea-116">Options de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="8dcea-116">Upgrade options</span></span>

<span data-ttu-id="8dcea-117">Cette section explique comment implémenter votre mise à niveau à l’aide de l’une des options de mise à niveau suivantes :</span><span class="sxs-lookup"><span data-stu-id="8dcea-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="8dcea-118">Mise à niveau des fonctionnalités superposées (à l’aide du mode Îles)</span><span class="sxs-lookup"><span data-stu-id="8dcea-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="8dcea-119">Mise à niveau des fonctionnalités de sélection pour une organisation qui n’a pas encore commencé à utiliser Teams</span><span class="sxs-lookup"><span data-stu-id="8dcea-119">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="8dcea-120">Mise à niveau des fonctionnalités sélectionnées pour une organisation qui utilise déjà Teams en mode Îles</span><span class="sxs-lookup"><span data-stu-id="8dcea-120">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="8dcea-121">Si vous avez besoin d’informations supplémentaires sur les options, assurez-vous que vous avez déjà lu les [méthodes de mise à niveau.](upgrade-to-teams-on-prem-upgrade-methods.md)</span><span class="sxs-lookup"><span data-stu-id="8dcea-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="8dcea-122">Mise à niveau des fonctionnalités superposées (à l’aide du mode Îles)</span><span class="sxs-lookup"><span data-stu-id="8dcea-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="8dcea-123">Pour l’option de mise à niveau des fonctionnalités superposées :</span><span class="sxs-lookup"><span data-stu-id="8dcea-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="8dcea-124">Envisagez cette option si vous pouvez mettre à niveau rapidement l’ensemble de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8dcea-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="8dcea-125">Étant donné qu’il existe un risque potentiel de confusion pour les utilisateurs finaux lors de l’exécution des deux clients, il est préférable de réduire la période pendant laquelle les utilisateurs doivent exécuter les deux clients.</span><span class="sxs-lookup"><span data-stu-id="8dcea-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="8dcea-126">Vous devez vous assurer que vos utilisateurs savent exécuter les deux clients.</span><span class="sxs-lookup"><span data-stu-id="8dcea-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="8dcea-127">Cette option est le modèle pré-standard et ne nécessite aucune action de l’administrateur pour prendre en charge Teams, sauf pour affecter la licence Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="8dcea-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="8dcea-128">Si vos utilisateurs ont déjà Skype Entreprise Online, il est possible que vous soyez déjà dans ce modèle.</span><span class="sxs-lookup"><span data-stu-id="8dcea-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="8dcea-129">Il peut être difficile de sortir du mode de fonctionnalités superposées et de passer à TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="8dcea-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="8dcea-130">Étant donné que les utilisateurs mis à niveau communiquent uniquement via Teams, tous les autres utilisateurs de l’organisation qui communiquent avec cet utilisateur doivent utiliser Teams.</span><span class="sxs-lookup"><span data-stu-id="8dcea-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="8dcea-131">Si vous avez des utilisateurs qui n’ont pas commencé à utiliser Teams, ils sont exposés à des messages manquants.</span><span class="sxs-lookup"><span data-stu-id="8dcea-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="8dcea-132">De plus, ils ne voient pas les utilisateurs de TeamsOnly en ligne dans Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="8dcea-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="8dcea-133">Certaines organisations choisissent d’opter pour une mise à niveau à l’échelle du client à l’aide de la stratégie globale du client afin d’éviter ce problème, ce qui nécessite toutefois une planification préalable et attendre que tous les utilisateurs soient prêts à mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="8dcea-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="8dcea-134">Mise à niveau des fonctionnalités de sélection pour une organisation qui n’a pas encore commencé à utiliser Teams</span><span class="sxs-lookup"><span data-stu-id="8dcea-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="8dcea-135">Si votre organisation n’a pas encore d’utilisateurs actifs dans Teams, la première étape consiste à définir la stratégie par défaut à l’échelle du client pour TeamsUpgradePolicy sur l’un des modes Skype Entreprise, par exemple, SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="8dcea-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="8dcea-136">Les utilisateurs qui n’ont pas encore commencé à utiliser Teams ne remarqueront aucune différence de comportement.</span><span class="sxs-lookup"><span data-stu-id="8dcea-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="8dcea-137">Toutefois, la définition de cette stratégie au niveau du client permet de commencer la mise à niveau des utilisateurs vers le mode TeamsOnly et garantit que les utilisateurs mis à niveau peuvent toujours communiquer avec des utilisateurs qui ne sont pas mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="8dcea-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="8dcea-138">Après avoir identifié vos utilisateurs pilotes, vous pouvez les mettre à niveau vers TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="8dcea-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="8dcea-139">S’ils sont locaux, utilisez Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="8dcea-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="8dcea-140">S’ils sont en ligne, affectez-les simplement en mode TeamsOnly à l’aide de Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="8dcea-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="8dcea-141">Par défaut, les réunions Skype Entreprise programmées par ces utilisateurs sont migrées vers Teams.</span><span class="sxs-lookup"><span data-stu-id="8dcea-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="8dcea-142">Voici les principales commandes :</span><span class="sxs-lookup"><span data-stu-id="8dcea-142">Following are the key commands:</span></span>

1. <span data-ttu-id="8dcea-143">Définissez le mode SfbWithTeamsCollab à l’échelle du client comme suit :</span><span class="sxs-lookup"><span data-stu-id="8dcea-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="8dcea-144">Mettre à niveau les utilisateurs pilotes vers TeamsOnly comme suit :</span><span class="sxs-lookup"><span data-stu-id="8dcea-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="8dcea-145">Pour un utilisateur en ligne :</span><span class="sxs-lookup"><span data-stu-id="8dcea-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="8dcea-146">Pour un utilisateur sur site :</span><span class="sxs-lookup"><span data-stu-id="8dcea-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="8dcea-147">Remarques</span><span class="sxs-lookup"><span data-stu-id="8dcea-147">Notes</span></span>
 
- <span data-ttu-id="8dcea-148">Au lieu de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab, vous pouvez la définir sur SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="8dcea-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="8dcea-149">Ainsi, tous les utilisateurs peuvent planifier toutes les nouvelles réunions dans Teams.</span><span class="sxs-lookup"><span data-stu-id="8dcea-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="8dcea-150">`Move-CsUser` est une cmdlet dans les outils locaux.</span><span class="sxs-lookup"><span data-stu-id="8dcea-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="8dcea-151">Le `MoveToTeams` basculement nécessite Skype Entreprise Server 2019 ou Skype Entreprise Server 2015 avec CU8 ou une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="8dcea-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="8dcea-152">Si vous utilisez une version antérieure, vous pouvez d’abord déplacer l’utilisateur vers Skype Entreprise Online, puis lui octroyer le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="8dcea-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="8dcea-153">Par défaut, les réunions Skype Entreprise sont migrées vers Teams lors de la mise à niveau vers le mode TeamsOnly ou lors de l’affectation du mode SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="8dcea-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="8dcea-154">Le diagramme ci-dessous présente les phases conceptuelles de la mise à niveau des fonctionnalités sélectionnées pour une organisation sans utilisation préalable de Teams.</span><span class="sxs-lookup"><span data-stu-id="8dcea-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="8dcea-155">La hauteur des barres représente le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8dcea-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="8dcea-156">Pendant toute phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="8dcea-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="8dcea-157">Les utilisateurs de Skype Entreprise communiquent avec les utilisateurs de TeamsOnly à l’aide d’Interop, et inversement.</span><span class="sxs-lookup"><span data-stu-id="8dcea-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="8dcea-158">Les utilisateurs en mode Îles doivent être certains d’exécuter les deux clients.</span><span class="sxs-lookup"><span data-stu-id="8dcea-158">Users in Islands mode must be sure to run both clients.</span></span>

![Diagramme montrant la mise à niveau des fonctionnalités de sélection sans utilisation préalable de Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="8dcea-160">Mise à niveau des fonctionnalités sélectionnées pour une organisation qui utilise déjà Teams en mode Îles</span><span class="sxs-lookup"><span data-stu-id="8dcea-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="8dcea-161">Si certains utilisateurs de votre organisation utilisent activement Teams en mode Îles, vous ne souhaitez probablement pas supprimer la fonctionnalité des utilisateurs existants.</span><span class="sxs-lookup"><span data-stu-id="8dcea-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="8dcea-162">Par conséquent, une étape supplémentaire est requise avant de modifier la stratégie à l’échelle du client.</span><span class="sxs-lookup"><span data-stu-id="8dcea-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="8dcea-163">La solution consiste à « transformer » ces utilisateurs existants de Teams en mode Îles, avant de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="8dcea-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="8dcea-164">Une fois que vous aurez effectué cela, vous pourrez procéder au déploiement comme ci-dessus. Toutefois, vous aurez deux groupes d’utilisateurs qui vont passer à TeamsOnly : les utilisateurs qui étaient actifs dans Teams seront en mode Îles et les autres utilisateurs seront en mode SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="8dcea-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="8dcea-165">Vous pouvez progressivement déplacer ces utilisateurs vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="8dcea-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="8dcea-166">Recherchez les utilisateurs actifs dans Teams comme suit :</span><span class="sxs-lookup"><span data-stu-id="8dcea-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="8dcea-167">Dans le centre d’administration Microsoft 365, dans le panneau de navigation gauche, allez dans Rapports, puis Utilisation.</span><span class="sxs-lookup"><span data-stu-id="8dcea-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="8dcea-168">Dans ladown « Sélectionner un rapport », sélectionnez Microsoft Teams, puis Activité de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8dcea-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="8dcea-169">Vous aurez ainsi une table exportable d’utilisateurs ayant été actifs dans Teams.</span><span class="sxs-lookup"><span data-stu-id="8dcea-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="8dcea-170">Cliquez sur Exporter, ouvrez Excel et filtrez pour afficher uniquement les utilisateurs actifs dans Teams.</span><span class="sxs-lookup"><span data-stu-id="8dcea-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="8dcea-171">Pour chaque utilisateur actif de Teams trouvé à l’étape 1, affectez-lui le mode Îles dans une powerShell distante.</span><span class="sxs-lookup"><span data-stu-id="8dcea-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="8dcea-172">Cela vous permet de passer à l’étape suivante et de ne pas modifier l’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8dcea-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="8dcea-173">Définissez la stratégie à l’échelle du client sur SfbWithTeamsCollab :</span><span class="sxs-lookup"><span data-stu-id="8dcea-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="8dcea-174">Mettre à niveau les utilisateurs sélectionnés vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="8dcea-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="8dcea-175">Vous pouvez choisir de mettre à niveau soit les utilisateurs en mode Islands, soit en mode SfbWithTeamsCollab, même si vous pouvez d’abord hiérarchiser la mise à niveau des utilisateurs en mode Islands afin de minimiser la confusion potentielle qui peut survenir lorsque les utilisateurs sont en mode Islands.</span><span class="sxs-lookup"><span data-stu-id="8dcea-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="8dcea-176">Pour les utilisateurs homed in Skype Entreprise Online :</span><span class="sxs-lookup"><span data-stu-id="8dcea-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="8dcea-177">Pour les utilisateurs homed in Skype Entreprise Server sur site :</span><span class="sxs-lookup"><span data-stu-id="8dcea-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="8dcea-178">Le diagramme ci-dessous montre les phases conceptuelles d’une transition de fonctionnalités sélectionnées dans laquelle les utilisateurs d’îles actives sont au début.</span><span class="sxs-lookup"><span data-stu-id="8dcea-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="8dcea-179">La hauteur des barres représente le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8dcea-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="8dcea-180">Pendant toute phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="8dcea-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="8dcea-181">Les utilisateurs de Skype Entreprise communiquent avec les utilisateurs de TeamsOnly à l’aide d’interop, et vice versa.</span><span class="sxs-lookup"><span data-stu-id="8dcea-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Diagramme montrant la mise à niveau des fonctionnalités sélectionnées avec des utilisateurs actifs en mode Îles](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="8dcea-183">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="8dcea-183">Related links</span></span>

[<span data-ttu-id="8dcea-184">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="8dcea-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="8dcea-185">Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="8dcea-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="8dcea-186">Déplacer des utilisateurs entre l’environnement local et le cloud</span><span class="sxs-lookup"><span data-stu-id="8dcea-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="8dcea-187">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="8dcea-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="8dcea-188">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="8dcea-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="8dcea-189">Utilisation du service Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="8dcea-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

