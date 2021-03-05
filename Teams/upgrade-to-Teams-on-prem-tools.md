---
title: Outils pour la mise à niveau vers Teams à partir d’un déploiement local de Skype Entreprise
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Outils de mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c272cdd6eac98b8847b6f915d59b62444d16c97
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460434"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="74e98-103">Outils de mise à niveau vers Teams &mdash; pour les administrateurs informatiques</span><span class="sxs-lookup"><span data-stu-id="74e98-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="74e98-104">Cet article décrit les outils permettant de mettre à niveau vers Teams à partir de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="74e98-104">This article describes tools for upgrading to Teams from Skype for Business.</span></span> 

<span data-ttu-id="74e98-105">Avant de commencer votre mise à niveau, Microsoft recommande les articles suivants qui décrivent les concepts de mise à niveau et les comportements de coexistence importants :</span><span class="sxs-lookup"><span data-stu-id="74e98-105">Before beginning your upgrade, Microsoft recommends the following articles that describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="74e98-106">Coexistence de Teams et de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="74e98-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="74e98-107">Modes de coexistence - Référence</span><span class="sxs-lookup"><span data-stu-id="74e98-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="74e98-108">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="74e98-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="74e98-109">Outils de gestion de la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="74e98-109">Tools for managing the upgrade</span></span>

<span data-ttu-id="74e98-110">Quelle que soit la méthode de mise à niveau que vous choisissez, pour les utilisateurs qui ont déjà Skype Entreprise Online, vous gérez la transition vers TeamsOnly à l’aide de [TeamsUpgradePolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)qui contrôle le mode de coexistence d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="74e98-110">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="74e98-111">Pour les utilisateurs utilisant un compte local dans Skype Entreprise Server, vous pouvez également les `Move-CsUser` [déplacer vers le cloud.](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="74e98-111">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="74e98-112">Pour plus d’informations sur chacun des modes, voir [Modes de coexistence.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="74e98-112">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="74e98-113">Si vous utilisez actuellement Skype Entreprise Online Connector pour gérer vos services, vous devez passer au module Teams PowerShell et mettre à jour vos scripts PowerShell existants.</span><span class="sxs-lookup"><span data-stu-id="74e98-113">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="74e98-114">Pour [plus d’informations,](teams-powershell-move-from-sfbo.md) voir Déplacer de Skype Entreprise Online Connector vers le module Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74e98-114">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="74e98-115">Que vous effectuez une transition de fonctionnalités sélectionnées à l’aide des modes Skype Entreprise ou que vous passiez simplement à la mise à niveau vers le mode TeamsOnly à partir de la configuration îles par défaut, TeamsUpgradePolicy est l’outil principal pour les utilisateurs qui ont déjà Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="74e98-115">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="74e98-116">Comme toute autre stratégie dans Teams, vous pouvez affecter TeamsUpgradePolicy directement à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="74e98-116">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="74e98-117">Vous pouvez également définir la stratégie comme stratégie par défaut à l’échelle du client.</span><span class="sxs-lookup"><span data-stu-id="74e98-117">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="74e98-118">Toute affectation à un utilisateur est prioritaire sur le paramètre par défaut du client.</span><span class="sxs-lookup"><span data-stu-id="74e98-118">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="74e98-119">Vous pouvez gérer la stratégie dans la Console d’administration Teams et dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74e98-119">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="74e98-120">Vous pouvez également affecter n’importe quel mode de TeamsUpgradePolicy, à l’exception du mode TeamsOnly, aux utilisateurs homed in Skype Entreprise sur site.</span><span class="sxs-lookup"><span data-stu-id="74e98-120">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="74e98-121">**Le mode TeamsOnly ne peut être affecté** qu’à un utilisateur déjà domicile dans Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="74e98-121">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="74e98-122">Cela est dû au fait que l’interopation avec les utilisateurs et la fédération Skype Entreprise ainsi que les fonctionnalités du système téléphonique Microsoft 365 ne sont possibles que si l’utilisateur est do domicile dans Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="74e98-122">This is because interop with Skype for Business users and federation and Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="74e98-123">En outre, vous ne pouvez pas attribuer le **mode TeamsOnly** comme mode par défaut à l’échelle du client si vous avez un déploiement local de Skype Entreprise (détecté par la présence d’un enregistrement DNS lyncdiscover qui pointe vers un emplacement autre qu’Office 365).</span><span class="sxs-lookup"><span data-stu-id="74e98-123">In addition, **you can't assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="74e98-124">Les utilisateurs départagent des comptes Skype Entreprise sur site [doivent](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) être déplacés en ligne (vers Skype Entreprise Online ou directement dans Teams) à l’aide de Move-CsUser dans le jeu d’outils Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="74e98-124">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="74e98-125">Ces utilisateurs peuvent être déplacés vers TeamsOnly en 1 ou 2 étapes :</span><span class="sxs-lookup"><span data-stu-id="74e98-125">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="74e98-126">1 étape : spécifier le commutateur -MoveToTeams dans Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="74e98-126">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="74e98-127">Cela nécessite Skype Entreprise Server 2019 ou Skype Entreprise Server 2015 avec CU8 ou une suite ultérieure.</span><span class="sxs-lookup"><span data-stu-id="74e98-127">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="74e98-128">2 étapes : Après avoir exécutez Move-CsUser, accordez le mode TeamsOnly à l’utilisateur utilisant TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="74e98-128">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="74e98-129">Contrairement à d’autres stratégies, il n’est pas possible de créer de nouvelles instances de TeamsUpgradePolicy dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="74e98-129">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="74e98-130">Toutes les instances existantes sont intégrées au service.</span><span class="sxs-lookup"><span data-stu-id="74e98-130">All the existing instances are built into the service.</span></span>  <span data-ttu-id="74e98-131">(Notez que le mode est une propriété dans TeamsUpgradePolicy, plutôt que le nom d’une instance de stratégie.) Dans certains cas, mais pas tous, le nom de l’instance de stratégie est identique à celui du mode.</span><span class="sxs-lookup"><span data-stu-id="74e98-131">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="74e98-132">En particulier, pour affecter le mode TeamsOnly à un utilisateur, vous accordez l’instance « UpgradeToTeams » de TeamsUpgradePolicy à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="74e98-132">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="74e98-133">Pour voir la liste de toutes les instances, vous pouvez exécuter la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="74e98-133">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="74e98-134">Pour mettre à niveau un utilisateur en ligne vers le mode TeamsOnly, affectez l’instance « UpgradeToTeams » :</span><span class="sxs-lookup"><span data-stu-id="74e98-134">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="74e98-135">Pour mettre à niveau un utilisateur Skype Entreprise sur site vers le mode TeamsOnly, utilisez Move-CsUser dans le jeu d’outils local :</span><span class="sxs-lookup"><span data-stu-id="74e98-135">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="74e98-136">Pour modifier le mode pour tous les utilisateurs du client, à l’exception de ceux qui ont une autorisation explicite par utilisateur (qui prend la priorité), exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="74e98-136">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="74e98-137">Si vous avez des utilisateurs avec des comptes Skype Entreprise en local, vous ne pouvez pas affecter le mode TeamsOnly au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="74e98-137">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="74e98-138">Vous devez déplacer ces utilisateurs individuellement vers le cloud à l’aide de Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="74e98-138">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="74e98-139">Utilisation des notifications dans les clients Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="74e98-139">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="74e98-140">Les administrateurs ont la possibilité de fournir des notifications aux utilisateurs finaux dans le client Skype Entreprise pour informer les utilisateurs qu’ils seront bientôt mis à niveau vers Teams, comme illustré dans le diagramme suivant.</span><span class="sxs-lookup"><span data-stu-id="74e98-140">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="74e98-141">Par exemple, une semaine avant que l’administrateur envisage de mettre à niveau un groupe d’utilisateurs en mode TeamsOnly, l’administrateur peut activer ces notifications pour ce groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="74e98-141">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="74e98-142">Ces notifications sont activées à l’aide d’une instance de TeamsUpgradePolicy avec NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="74e98-142">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="74e98-143">Pour tous les modes autres que TeamsOnly, il existe en réalité deux instances par mode, correspondant aux deux valeurs de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="74e98-143">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="74e98-144">Pour tous les modes autres que TeamsOnly, il existe en réalité deux instances par mode, correspondant aux deux valeurs de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="74e98-144">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagramme montrant les notifications](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="74e98-146">Si vos utilisateurs sont homed in Skype Entreprise Online, affectez simplement l’instance de stratégie ayant le même mode que l’utilisateur, mais avec NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="74e98-146">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="74e98-147">Si vos utilisateurs sont homed dans Skype Entreprise Server sur site, vous devez utiliser le jeu d’outils local et vous avez besoin de Skype Entreprise Server 2019 ou CU8 pour Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="74e98-147">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="74e98-148">Pour les utilisateurs homed in Skype For Business Server local, la propriété de mode de l’instance en ligne de TeamsUpgradePolicy est honorée, mais la propriété NotifySfbUsers ne l’est pas.</span><span class="sxs-lookup"><span data-stu-id="74e98-148">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="74e98-149">Si vous souhaitez recevoir des notifications, vous devez créer une instance sur site de TeamsUpgradePolicy pour contrôler le comportement du client.</span><span class="sxs-lookup"><span data-stu-id="74e98-149">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="74e98-150">Dans la fenêtre PowerShell en local, créez une instance de TeamsUpgradePolicy avec NotifySfbUsers=true :</span><span class="sxs-lookup"><span data-stu-id="74e98-150">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="74e98-151">Ensuite, à l’aide de la même fenêtre PowerShell en local, affectez cette nouvelle stratégie aux utilisateurs souhaités :</span><span class="sxs-lookup"><span data-stu-id="74e98-151">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="74e98-152">Migration de réunions</span><span class="sxs-lookup"><span data-stu-id="74e98-152">Meeting migration</span></span>

<span data-ttu-id="74e98-153">Lorsqu’un utilisateur est migré vers le mode TeamsOnly, par défaut ses réunions Skype Entreprise existantes qu’il a organisées sont converties en équipes.</span><span class="sxs-lookup"><span data-stu-id="74e98-153">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="74e98-154">Vous pouvez éventuellement désactiver le comportement par défaut lors de l’attribution du mode TeamsOnly à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="74e98-154">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="74e98-155">Lors du déplacement d’utilisateurs à partir du site, les réunions doivent être migrées vers le cloud pour fonctionner avec le compte d’utilisateur en ligne, mais si vous ne spécifiez pas -MoveToTeams, les réunions seront migrées en tant que réunions Skype Entreprise, plutôt que converties en équipes.</span><span class="sxs-lookup"><span data-stu-id="74e98-155">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="74e98-156">Lors de l’attribution du mode TeamsOnly au niveau du client, la migration de réunions n’est déclenchée pour aucun utilisateur.</span><span class="sxs-lookup"><span data-stu-id="74e98-156">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="74e98-157">Si vous souhaitez attribuer le mode TeamsOnly au niveau du client et migrer des réunions, vous pouvez utiliser PowerShell pour obtenir la liste des utilisateurs dans le client (par exemple, en utilisant Get-CsOnlineUser avec les filtres nécessaires), puis passer en boucle chacun de ces utilisateurs pour déclencher la migration de réunion à l’aide de Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="74e98-157">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="74e98-158">Pour plus d’informations, [consultez Utiliser meeting Migration Service (MMS).](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="74e98-158">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="74e98-159">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="74e98-159">Related links</span></span>

[<span data-ttu-id="74e98-160">Modes de coexistence - Référence</span><span class="sxs-lookup"><span data-stu-id="74e98-160">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="74e98-161">Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="74e98-161">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="74e98-162">Déplacer des utilisateurs entre l’environnement local et le cloud</span><span class="sxs-lookup"><span data-stu-id="74e98-162">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="74e98-163">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="74e98-163">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="74e98-164">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="74e98-164">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="74e98-165">Utilisation du service Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="74e98-165">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

