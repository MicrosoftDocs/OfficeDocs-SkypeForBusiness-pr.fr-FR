---
title: Effectuer une mise à niveau vers teams à partir d’un déploiement local de Skype entreprise-Microsoft teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf51019aad5b2deb6239c698623475263241b3f
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940641"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="f6ce7-103">Outils pour la mise à niveau vers teams &mdash; pour les administrateurs informatiques</span><span class="sxs-lookup"><span data-stu-id="f6ce7-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="f6ce7-104">Cet article décrit les outils de mise à niveau vers Teams.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="f6ce7-105">Cet article est le troisième de nombreux aspects relatifs à la mise à niveau et à l’implémentation pour les administrateurs informatiques.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="f6ce7-106">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="f6ce7-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="f6ce7-107">Méthodes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="f6ce7-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="f6ce7-108">**Outils de gestion de votre mise à niveau**   (cet article)</span><span class="sxs-lookup"><span data-stu-id="f6ce7-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="f6ce7-109">Autres considérations concernant les organisations avec Skype entreprise en local</span><span class="sxs-lookup"><span data-stu-id="f6ce7-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="f6ce7-110">Implémenter votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="f6ce7-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="f6ce7-111">Considérations relatives au réseau téléphonique public commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="f6ce7-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="f6ce7-112">De plus, les articles suivants décrivent des concepts importants de mise à niveau et des comportements de coexistence :</span><span class="sxs-lookup"><span data-stu-id="f6ce7-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="f6ce7-113">Coexistence des équipes et de Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="f6ce7-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="f6ce7-114">Modes de coexistence-référence</span><span class="sxs-lookup"><span data-stu-id="f6ce7-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="f6ce7-115">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="f6ce7-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="f6ce7-116">Outils de gestion de la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="f6ce7-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="f6ce7-117">Quelle que soit la méthode de mise à niveau choisie, vous gérez la transition vers TeamsOnly à l’aide de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), qui contrôle le mode de coexistence d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-117">Whichever upgrade method you choose, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="f6ce7-118">Pour plus d’informations sur chacun des modes, voir [modes de coexistence](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="f6ce7-118">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="f6ce7-119">Que vous effectuiez une transition sélection de fonctionnalités à l’aide du mode Skype entreprise ou que vous soyez simplement dans le mode TeamsOnly à partir de la configuration des îles par défaut, TeamsUpgradePolicy est l’outil principal.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-119">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool.</span></span> <span data-ttu-id="f6ce7-120">À l’instar des autres stratégies dans Teams, vous pouvez attribuer TeamsUpgradePolicy directement à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-120">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="f6ce7-121">Vous pouvez également définir la stratégie en tant que niveau de client par défaut.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-121">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="f6ce7-122">Tout devoir d’un utilisateur est prioritaire sur le paramètre par défaut du client.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-122">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="f6ce7-123">Vous pouvez gérer la stratégie dans la console d’administration des équipes et dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-123">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="f6ce7-124">Vous pouvez attribuer n’importe quel mode de TeamsUpgradePolicy aux utilisateurs, que l’utilisateur soit hébergé dans Skype entreprise Online ou en local, **sauf que le mode TeamsOnly ne peut être attribué qu’à un utilisateur déjà associé dans Skype entreprise Online**.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-124">You can assign any mode of TeamsUpgradePolicy to users whether the user is homed in Skype for Business Online or on-premises, **except that TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="f6ce7-125">En effet, les fonctionnalités d’interopérabilité avec les utilisateurs et la Fédération Skype entreprise, ainsi que les fonctionnalités du système téléphonique Microsoft 365 ne sont possibles que si l’utilisateur est hébergé dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-125">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span>

<span data-ttu-id="f6ce7-126">Les utilisateurs disposant d’un compte Skype entreprise sur site hébergé sur site [doivent être déplacés en ligne](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (à partir de Skype entreprise Online ou directement à Teams) à l’aide de Move-Csuser dans l’ensemble d’outils Skype entreprise local.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-126">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="f6ce7-127">Ces utilisateurs peuvent être déplacés vers TeamsOnly en 1 ou 2 étapes :</span><span class="sxs-lookup"><span data-stu-id="f6ce7-127">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="f6ce7-128">1 étape : spécifiez le commutateur-MoveToTeams dans Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-128">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="f6ce7-129">Pour cela, vous devez disposer de Skype entreprise Server 2019 ou de Skype entreprise Server 2015 avec CU8 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-129">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="f6ce7-130">2 étapes : après avoir exécuté Move-CsUser, octroyez le mode TeamsOnly à l’utilisateur à l’aide de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-130">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="f6ce7-131">Contrairement aux autres stratégies, il n’est pas possible de créer de nouvelles instances de TeamsUpgradePolicy dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-131">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f6ce7-132">Toutes les instances existantes sont intégrées au service.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-132">All the existing instances are built into the service.</span></span>  <span data-ttu-id="f6ce7-133">(Notez que le mode est une propriété dans TeamsUpgradePolicy, plutôt que le nom d’une instance de stratégie.) Dans certains cas, mais pas dans tous les cas, le nom de l’instance de stratégie est le même que le mode.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-133">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="f6ce7-134">En particulier, pour affecter le mode TeamsOnly à un utilisateur, vous devez attribuer l’instance « UpgradeToTeams » de TeamsUpgradePolicy à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-134">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="f6ce7-135">Pour afficher une liste de toutes les instances, vous pouvez exécuter la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f6ce7-135">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="f6ce7-136">Pour mettre à niveau un utilisateur en ligne vers le mode TeamsOnly, attribuez l’instance « UpgradeToTeams » :</span><span class="sxs-lookup"><span data-stu-id="f6ce7-136">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="f6ce7-137">Pour passer d’un utilisateur Skype entreprise local au mode TeamsOnly, utilisez Move-CsUser dans l’ensemble d’outils local :</span><span class="sxs-lookup"><span data-stu-id="f6ce7-137">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="f6ce7-138">Pour modifier le mode de tous les utilisateurs du client, à l’exception de ceux qui ont une autorisation explicite par utilisateur (prioritaire), exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f6ce7-138">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="f6ce7-139">Si vos utilisateurs disposent d’un compte Skype entreprise local, vous ne devez pas affecter le mode TeamsOnly au niveau du client, sauf si vous affectez explicitement un autre mode à tous les utilisateurs disposant de comptes Skype entreprise locaux.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-139">If you have any users with Skype for Business accounts on-premises, you must not assign TeamsOnly mode at the tenant level, unless you explicitly assign some other mode to all users with on-premises Skype for Business accounts.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="f6ce7-140">Utilisation des notifications dans les clients Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="f6ce7-140">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="f6ce7-141">Les administrateurs ont la possibilité de fournir des notifications aux utilisateurs finaux dans le client Skype entreprise pour informer les utilisateurs qu’ils seront bientôt mis à niveau vers Teams, comme illustré dans le schéma suivant.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-141">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="f6ce7-142">Par exemple, une semaine, avant que l’administrateur ne prévoit de mettre à niveau un groupe d’utilisateurs vers le mode TeamsOnly, l’administrateur peut activer ces notifications pour ce groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-142">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="f6ce7-143">Ces notifications sont activées à l’aide d’une instance de TeamsUpgradePolicy avec NotifySfbUsers = true.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-143">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="f6ce7-144">Pour tous les modes autres que TeamsOnly, il existe en réalité deux instances par mode, correspondant aux deux valeurs de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-144">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="f6ce7-145">Pour tous les modes autres que TeamsOnly, il existe en réalité deux instances par mode, correspondant aux deux valeurs de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-145">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagramme présentant des notifications](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="f6ce7-147">Si vos utilisateurs sont familiaux dans Skype entreprise Online, il vous suffit d’affecter l’instance de la stratégie ayant le même mode que l’utilisateur, mais avec NotifySfbUsers = true.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-147">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="f6ce7-148">Si vos utilisateurs sont hébergés dans Skype entreprise Server en local, vous devez utiliser l’ensemble d’outils local et vous aurez besoin de Skype entreprise Server 2019 ou CU8 pour Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-148">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="f6ce7-149">Pour les utilisateurs hébergés dans Skype entreprise Server sur site, la propriété mode de l’instance en ligne de TeamsUpgradePolicy est honorée, mais la propriété NotifySfbUsers ne l’est pas.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-149">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="f6ce7-150">Si les notifications sont souhaitées, vous devez créer une instance locale de TeamsUpgradePolicy pour contrôler le comportement du client.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-150">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="f6ce7-151">Dans la fenêtre PowerShell locale, créez une nouvelle instance de TeamsUpgradePolicy avec NotifySfbUsers = true :</span><span class="sxs-lookup"><span data-stu-id="f6ce7-151">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="f6ce7-152">Ensuite, à l’aide de la même fenêtre PowerShell locale, attribuez cette nouvelle stratégie aux utilisateurs souhaités :</span><span class="sxs-lookup"><span data-stu-id="f6ce7-152">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="f6ce7-153">Migration de réunion</span><span class="sxs-lookup"><span data-stu-id="f6ce7-153">Meeting migration</span></span>

<span data-ttu-id="f6ce7-154">Lorsqu’un utilisateur est déplacé vers le mode TeamsOnly, par défaut, les réunions Skype entreprise existantes qu’il a organisées seront converties en équipes.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-154">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="f6ce7-155">Vous pouvez éventuellement désactiver le comportement par défaut lors de l’attribution du mode TeamsOnly à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-155">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="f6ce7-156">Lorsque vous déplacez des utilisateurs d’un environnement local, les réunions doivent être déplacées vers le Cloud pour fonctionner avec le compte d’utilisateur en ligne, mais si vous ne spécifiez pas-MoveToTeams, les réunions seront déplacées en tant que réunions Skype entreprise, et non converties en équipes.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-156">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="f6ce7-157">Lors de l’attribution du mode TeamsOnly au niveau du client, la migration de la réunion n’est déclenchée pour aucun utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-157">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="f6ce7-158">Si vous souhaitez affecter le mode TeamsOnly au niveau du client et migrer des réunions, vous pouvez utiliser PowerShell pour obtenir la liste des utilisateurs dans le client (par exemple, en utilisant Get-CsOnlineUser avec les filtres requis), puis en boucle sur chacun de ces utilisateurs pour déclencher la migration de réunion à l’aide de Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="f6ce7-158">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="f6ce7-159">Pour plus d’informations, consultez [utilisation du service de migration de réunion (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="f6ce7-159">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="f6ce7-160">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="f6ce7-160">Related links</span></span>

[<span data-ttu-id="f6ce7-161">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="f6ce7-161">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="f6ce7-162">Configurer une connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="f6ce7-162">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="f6ce7-163">Déplacer des utilisateurs entre l’environnement local et le cloud</span><span class="sxs-lookup"><span data-stu-id="f6ce7-163">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="f6ce7-164">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="f6ce7-164">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="f6ce7-165">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="f6ce7-165">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="f6ce7-166">Utiliser le service de migration de réunion (MMS)</span><span class="sxs-lookup"><span data-stu-id="f6ce7-166">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

