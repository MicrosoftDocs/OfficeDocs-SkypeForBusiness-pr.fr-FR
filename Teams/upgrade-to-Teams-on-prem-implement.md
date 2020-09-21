---
title: Effectuer une mise à niveau vers teams à partir d’un déploiement local de Skype entreprise-Microsoft teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
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
ms.openlocfilehash: 8239d1fdbda10a61cd0846a0d56b1f1ffa62f597
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955901"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="ac133-103">Mettre en œuvre la mise à niveau de Skype entreprise vers teams &mdash; pour les administrateurs informatiques</span><span class="sxs-lookup"><span data-stu-id="ac133-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="ac133-104">Cet article décrit comment implémenter la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="ac133-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="ac133-105">Cet article est le cinquième de ceux qui décrivent les concepts de mise à niveau et l’implémentation pour les administrateurs informatiques.</span><span class="sxs-lookup"><span data-stu-id="ac133-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="ac133-106">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="ac133-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="ac133-107">Méthodes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="ac133-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="ac133-108">Outils de gestion de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="ac133-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="ac133-109">Autres considérations concernant les organisations avec Skype entreprise en local</span><span class="sxs-lookup"><span data-stu-id="ac133-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="ac133-110">**Mettre en œuvre la mise à niveau** (cet article)</span><span class="sxs-lookup"><span data-stu-id="ac133-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="ac133-111">Considérations relatives au réseau téléphonique public commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="ac133-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="ac133-112">De plus, les articles suivants décrivent des concepts importants de mise à niveau et des comportements de coexistence :</span><span class="sxs-lookup"><span data-stu-id="ac133-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="ac133-113">Coexistence des équipes et de Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="ac133-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="ac133-114">Modes de coexistence-référence</span><span class="sxs-lookup"><span data-stu-id="ac133-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="ac133-115">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="ac133-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="ac133-116">Options de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="ac133-116">Upgrade options</span></span>

<span data-ttu-id="ac133-117">Cette section décrit comment implémenter la mise à niveau en utilisant l’une des options de mise à niveau suivantes :</span><span class="sxs-lookup"><span data-stu-id="ac133-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="ac133-118">Mise à niveau des fonctionnalités qui se chevauchent (à l’aide du mode îlot)</span><span class="sxs-lookup"><span data-stu-id="ac133-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="ac133-119">Mise à niveau des fonctionnalités SELECT pour une organisation qui n’a pas encore commencé à utiliser teams</span><span class="sxs-lookup"><span data-stu-id="ac133-119">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="ac133-120">Mise à niveau des fonctionnalités SELECT pour une organisation qui utilise déjà teams en mode îlot</span><span class="sxs-lookup"><span data-stu-id="ac133-120">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="ac133-121">Si vous avez besoin d’informations supplémentaires sur les options, assurez-vous d’avoir déjà lu les [méthodes de mise à niveau](upgrade-to-teams-on-prem-upgrade-methods.md).</span><span class="sxs-lookup"><span data-stu-id="ac133-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="ac133-122">Mise à niveau des fonctionnalités qui se chevauchent (à l’aide du mode îlot)</span><span class="sxs-lookup"><span data-stu-id="ac133-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="ac133-123">Pour l’option de mise à niveau des fonctionnalités qui se chevauchent :</span><span class="sxs-lookup"><span data-stu-id="ac133-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="ac133-124">Cette option est utile si vous pouvez effectuer une mise à niveau rapide de votre organisation globale.</span><span class="sxs-lookup"><span data-stu-id="ac133-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="ac133-125">Dans la mesure où il existe des risques potentiels de confusion pour les utilisateurs finaux exécutant les deux clients, il est préférable de réduire le temps de fonctionnement des utilisateurs aux deux clients.</span><span class="sxs-lookup"><span data-stu-id="ac133-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="ac133-126">Vous devez veiller à ce que les utilisateurs sachent exécuter les deux clients.</span><span class="sxs-lookup"><span data-stu-id="ac133-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="ac133-127">Cette option est le modèle de la boîte et ne nécessite pas d’action de l’administrateur pour commencer à utiliser teams à l’exception de l’attribution de la licence Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac133-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="ac133-128">Si vos utilisateurs disposent déjà de Skype entreprise Online, il est possible que vous soyez déjà dans ce modèle.</span><span class="sxs-lookup"><span data-stu-id="ac133-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="ac133-129">Il peut être difficile de sortir du mode de superposition des capacités et de migrer vers TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ac133-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="ac133-130">Étant donné que les utilisateurs mis à niveau communiquent uniquement par le biais d’équipes, tout autre utilisateur de l’organisation qui communique avec cet utilisateur doit utiliser Teams.</span><span class="sxs-lookup"><span data-stu-id="ac133-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="ac133-131">Si certains de vos utilisateurs ne sont pas encore en cours d’utilisation, ils seront exposés à des messages manquants.</span><span class="sxs-lookup"><span data-stu-id="ac133-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="ac133-132">De plus, ils ne verront pas les utilisateurs de TeamsOnly en ligne dans Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="ac133-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="ac133-133">Certaines organisations choisissent de procéder à la mise à niveau du client à l’aide de la stratégie globale du client pour éviter cela, mais cela nécessite une planification approfondie ainsi que l’attente de la mise à niveau de tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ac133-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="ac133-134">Mise à niveau des fonctionnalités SELECT pour une organisation qui n’a pas encore commencé à utiliser teams</span><span class="sxs-lookup"><span data-stu-id="ac133-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="ac133-135">Si votre organisation n’a pas encore de personnes actives dans Teams, la première étape consiste à définir la stratégie à l’échelle de locataire par défaut de TeamsUpgradePolicy sur l’un des modes Skype entreprise, par exemple, SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="ac133-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="ac133-136">Les utilisateurs qui n’ont pas encore commencé à utiliser Teams ne noteront aucune différence de comportement.</span><span class="sxs-lookup"><span data-stu-id="ac133-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="ac133-137">Toutefois, la définition de cette stratégie au niveau du client permet de commencer à mettre à niveau les utilisateurs vers le mode TeamsOnly et de s’assurer que les utilisateurs mis à niveau peuvent toujours communiquer avec des utilisateurs non mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="ac133-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="ac133-138">Une fois que vous avez identifié vos utilisateurs pilotes, vous pouvez les mettre à niveau vers TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ac133-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="ac133-139">S’il s’agit d’un environnement local, utilisez Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="ac133-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="ac133-140">S’il est connecté, affectez-lui simplement le mode TeamsOnly à l’aide de Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="ac133-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="ac133-141">Par défaut, toutes les réunions Skype entreprise planifiées par ces utilisateurs seront déplacées vers Teams.</span><span class="sxs-lookup"><span data-stu-id="ac133-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="ac133-142">Voici les commandes clés :</span><span class="sxs-lookup"><span data-stu-id="ac133-142">Following are the key commands:</span></span>

1. <span data-ttu-id="ac133-143">Définissez la valeur par défaut du client sur mode SfbWithTeamsCollab comme suit :</span><span class="sxs-lookup"><span data-stu-id="ac133-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="ac133-144">Mettez à niveau les utilisateurs pilotes vers TeamsOnly comme suit :</span><span class="sxs-lookup"><span data-stu-id="ac133-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="ac133-145">Pour un utilisateur qui est en ligne :</span><span class="sxs-lookup"><span data-stu-id="ac133-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="ac133-146">Pour un utilisateur local :</span><span class="sxs-lookup"><span data-stu-id="ac133-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="ac133-147">Remarques</span><span class="sxs-lookup"><span data-stu-id="ac133-147">Notes</span></span>
 
- <span data-ttu-id="ac133-148">Au lieu de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab, vous pouvez la définir sur SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="ac133-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="ac133-149">Ainsi, tous les utilisateurs peuvent planifier toutes les nouvelles réunions dans Teams.</span><span class="sxs-lookup"><span data-stu-id="ac133-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="ac133-150">`Move-CsUser` est une cmdlet dans les outils locaux.</span><span class="sxs-lookup"><span data-stu-id="ac133-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="ac133-151">Le `MoveToTeams` commutateur nécessite Skype entreprise server 2019 ou Skype entreprise server 2015 avec CU8 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="ac133-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="ac133-152">Si vous utilisez une version antérieure, vous pouvez d’abord déplacer l’utilisateur vers Skype entreprise Online, puis accorder le mode TeamsOnly à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ac133-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="ac133-153">Par défaut, les réunions Skype entreprise sont déplacées vers teams lors de la mise à niveau vers le mode TeamsOnly ou lors de l’attribution du mode SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="ac133-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="ac133-154">Le diagramme ci-dessous présente les phases conceptuelles de la mise à niveau de fonctionnalités sélectionnées pour une organisation sans utilisation antérieure d’Teams.</span><span class="sxs-lookup"><span data-stu-id="ac133-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="ac133-155">La hauteur des barres représente le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ac133-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="ac133-156">Pendant une phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="ac133-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="ac133-157">Les utilisateurs de Skype entreprise communiquent avec des utilisateurs de TeamsOnly à l’aide d’interopérabilité, et inversement.</span><span class="sxs-lookup"><span data-stu-id="ac133-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="ac133-158">Les utilisateurs en mode îlot doivent veiller à exécuter les deux clients.</span><span class="sxs-lookup"><span data-stu-id="ac133-158">Users in Islands mode must be sure to run both clients.</span></span>

![Diagramme illustrant la mise à niveau de fonctionnalités sélectionnées sans utilisation antérieure des équipes](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="ac133-160">Mise à niveau des fonctionnalités SELECT pour une organisation qui utilise déjà teams en mode îlot</span><span class="sxs-lookup"><span data-stu-id="ac133-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="ac133-161">Si certains utilisateurs de votre organisation utilisent activement teams en mode îlot, il est probable que vous ne vouliez pas supprimer les fonctionnalités des utilisateurs existants.</span><span class="sxs-lookup"><span data-stu-id="ac133-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="ac133-162">Par conséquent, une étape supplémentaire est requise avant de modifier la stratégie à l’échelle du client.</span><span class="sxs-lookup"><span data-stu-id="ac133-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="ac133-163">La solution est de « grand-moi », qui sont des utilisateurs d’équipes actives actuellement en mode îlot, avant de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="ac133-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="ac133-164">Une fois cette opération effectuée, vous pourrez procéder au déploiement comme décrit ci-dessus, mais vous aurez deux groupes d’utilisateurs qui migrent vers TeamsOnly : les utilisateurs qui ont été actifs dans teams seront en mode d’îlot de travail et les utilisateurs restants seront en mode SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="ac133-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="ac133-165">Vous pouvez déplacer progressivement ces utilisateurs vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ac133-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="ac133-166">Recherchez les utilisateurs actifs dans teams en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="ac133-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="ac133-167">Dans le centre d’administration Microsoft 365, dans la barre de navigation gauche, accédez à rapports, puis sur utilisation.</span><span class="sxs-lookup"><span data-stu-id="ac133-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="ac133-168">Dans la liste déroulante « Sélectionner un rapport », cliquez sur Microsoft Teams, puis sur activité de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ac133-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="ac133-169">Cela permet de fournir une table exportable d’utilisateurs qui ont été actifs dans Teams.</span><span class="sxs-lookup"><span data-stu-id="ac133-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="ac133-170">Cliquez sur Exporter, ouvrir Excel et filtre pour afficher uniquement les utilisateurs actifs dans Teams.</span><span class="sxs-lookup"><span data-stu-id="ac133-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="ac133-171">Pour chaque utilisateur d’équipe actif trouvé à l’étape 1, attribuez-lui le mode îlots dans Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac133-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="ac133-172">Cela vous permet d’accéder à l’étape suivante et de ne pas modifier l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ac133-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="ac133-173">Définissez la stratégie à l’échelle du client sur SfbWithTeamsCollab :</span><span class="sxs-lookup"><span data-stu-id="ac133-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="ac133-174">Mettre à niveau les utilisateurs sélectionnés vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ac133-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="ac133-175">Vous pouvez choisir de mettre à niveau les utilisateurs en mode îlot ou SfbWithTeamsCollab, même si vous souhaitez que la mise à niveau des utilisateurs en mode îlot soit prioritaire pour réduire le risque de confusion lorsque les utilisateurs sont en mode îlot.</span><span class="sxs-lookup"><span data-stu-id="ac133-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="ac133-176">Pour les utilisateurs hébergés dans Skype entreprise Online :</span><span class="sxs-lookup"><span data-stu-id="ac133-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="ac133-177">Pour les utilisateurs hébergés dans Skype entreprise Server en local :</span><span class="sxs-lookup"><span data-stu-id="ac133-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="ac133-178">Le diagramme ci-dessous présente les phases conceptuelles d’une transition de sélection de fonctionnalités dans laquelle les utilisateurs d’îlots sont actifs au début.</span><span class="sxs-lookup"><span data-stu-id="ac133-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="ac133-179">La hauteur des barres représente le nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ac133-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="ac133-180">Pendant une phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.</span><span class="sxs-lookup"><span data-stu-id="ac133-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="ac133-181">Les utilisateurs de Skype entreprise communiquent avec des utilisateurs de TeamsOnly à l’aide d’interopérabilité, et inversement.</span><span class="sxs-lookup"><span data-stu-id="ac133-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Diagramme illustrant l’option Sélectionner les fonctionnalités mise à niveau avec des utilisateurs actifs en mode d’îlot](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="ac133-183">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="ac133-183">Related links</span></span>

[<span data-ttu-id="ac133-184">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="ac133-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="ac133-185">Configurer une connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="ac133-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="ac133-186">Déplacer des utilisateurs entre l’environnement local et le cloud</span><span class="sxs-lookup"><span data-stu-id="ac133-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="ac133-187">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="ac133-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="ac133-188">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="ac133-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="ac133-189">Utiliser le service de migration de réunion (MMS)</span><span class="sxs-lookup"><span data-stu-id="ac133-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

