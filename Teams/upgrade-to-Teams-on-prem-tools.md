---
title: Outils de mise à niveau Teams d’un déploiement Skype Entreprise local
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Outils de mise à niveau Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 677f642bdb940706079370635a5aa9eec87241fb
ms.sourcegitcommit: e19fdedca6573110d08c7d114e05b84779e36b58
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437631"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="1626f-103">Outils pour la mise à niveau vers Teams &mdash; administrateurs informatiques</span><span class="sxs-lookup"><span data-stu-id="1626f-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="1626f-104">Cet article décrit les outils permettant de mettre à Teams niveau vers Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="1626f-104">This article describes tools for upgrading to Teams from Skype for Business.</span></span> 

<span data-ttu-id="1626f-105">Avant de commencer votre mise à niveau, Microsoft recommande les articles suivants qui décrivent les concepts de mise à niveau et les comportements de coexistence importants :</span><span class="sxs-lookup"><span data-stu-id="1626f-105">Before beginning your upgrade, Microsoft recommends the following articles that describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="1626f-106">Coexistence de Teams et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="1626f-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="1626f-107">Modes de coexistence - Référence</span><span class="sxs-lookup"><span data-stu-id="1626f-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="1626f-108">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="1626f-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="1626f-109">Outils de gestion de la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="1626f-109">Tools for managing the upgrade</span></span>

<span data-ttu-id="1626f-110">Quelle que soit la méthode de mise à niveau que vous choisissez, pour les utilisateurs qui ont déjà Skype Entreprise Online, vous gérez la transition vers TeamsOnly à l’aide de [TeamsUpgradePolicy,](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)qui contrôle le mode de coexistence d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1626f-110">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="1626f-111">Pour les utilisateurs qui ont un compte local dans Skype Entreprise Server, vous pouvez également les déplacer `Move-CsUser` [vers le cloud.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="1626f-111">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="1626f-112">Pour plus d’informations sur chacun des modes, voir [Modes de coexistence.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="1626f-112">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1626f-113">Si vous utilisez actuellement Skype Entreprise Online Connector pour gérer vos services, vous devez passer au module Teams PowerShell et mettre à jour vos scripts PowerShell existants.</span><span class="sxs-lookup"><span data-stu-id="1626f-113">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="1626f-114">Pour [plus d’Skype Entreprise, voir Déplacer du connecteur en ligne vers Teams module PowerShell.](teams-powershell-move-from-sfbo.md)</span><span class="sxs-lookup"><span data-stu-id="1626f-114">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="1626f-115">Que vous effectuez une transition de fonctionnalités sélectionnées à l’aide des modes Skype Entreprise ou que vous passiez simplement à niveau vers le mode TeamsOnly à partir de la configuration îles par défaut, TeamsUpgradePolicy est l’outil principal. Comme toute autre stratégie Teams, vous pouvez affecter TeamsUpgradePolicy directement à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1626f-115">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool.Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="1626f-116">Vous pouvez également définir la stratégie comme stratégie par défaut à l’échelle du client.</span><span class="sxs-lookup"><span data-stu-id="1626f-116">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="1626f-117">Toute affectation à un utilisateur est prioritaire sur le paramètre par défaut du client.</span><span class="sxs-lookup"><span data-stu-id="1626f-117">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="1626f-118">Vous pouvez gérer la stratégie dans la console d’administration Teams et dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1626f-118">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="1626f-119">Vous pouvez affecter n’importe quel mode de TeamsUpgradePolicy, à l’exception du mode TeamsOnly, aux utilisateurs Skype Entreprise sur site.</span><span class="sxs-lookup"><span data-stu-id="1626f-119">You can assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="1626f-120">À l’inverse, seul le mode TeamsOnly peut être attribué aux utilisateurs homed in the cloud.</span><span class="sxs-lookup"><span data-stu-id="1626f-120">Conversely, users homed in the cloud can only be assigned TeamsOnly mode.</span></span> <span data-ttu-id="1626f-121">Le **mode TeamsOnly** ne peut être affecté qu’à un utilisateur qui est déjà dopé dans le cloud, car interop et la fédération avec des utilisateurs Skype Entreprise ainsi que des fonctionnalités de Microsoft 365 Système téléphonique ne sont possibles que si l’utilisateur est doté sur Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="1626f-121">**TeamsOnly mode can only be assigned to a user who is already homed in the cloud** because interop and federation with Skype for Business users as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span>  <span data-ttu-id="1626f-122">En outre, vous ne pouvez pas attribuer le **mode TeamsOnly** comme mode par défaut à l’échelle du client si vous avez un déploiement Skype Entreprise local (détecté par la présence d’un enregistrement DNS lyncdiscover qui pointe vers un emplacement autre que Office 365).</span><span class="sxs-lookup"><span data-stu-id="1626f-122">Further, **you can't assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span> <span data-ttu-id="1626f-123">Pour plus d’informations, voir Désactiver votre configuration hybride pour achever la [migration vers Teams uniquement.](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid)</span><span class="sxs-lookup"><span data-stu-id="1626f-123">For details, see [Disable your hybrid configuration to complete migration to Teams Only](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>

<span data-ttu-id="1626f-124">Les utilisateurs Skype Entreprise comptes locaux doivent être [](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) déplacés en ligne vers le mode Teams Uniquement à l’aide de Move-CsUser dans le jeu d’outils Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="1626f-124">Users with Skype for Business accounts homed on-premises [must be moved online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) to Teams Only mode using Move-CsUser in the Skype for Business on-premises toolset.</span></span> 

<span data-ttu-id="1626f-125">Contrairement à d’autres stratégies, il n’est pas possible de créer de nouvelles instances de TeamsUpgradePolicy Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="1626f-125">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="1626f-126">Toutes les instances existantes sont intégrées au service.</span><span class="sxs-lookup"><span data-stu-id="1626f-126">All the existing instances are built into the service.</span></span>  <span data-ttu-id="1626f-127">(Notez que le mode est une propriété dans TeamsUpgradePolicy, plutôt que le nom d’une instance de stratégie.) Dans certains cas, mais pas tous, le nom de l’instance de stratégie est identique à celui du mode.</span><span class="sxs-lookup"><span data-stu-id="1626f-127">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="1626f-128">En particulier, pour affecter le mode TeamsOnly à un utilisateur, vous accordez l’instance « UpgradeToTeams » de TeamsUpgradePolicy à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1626f-128">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="1626f-129">Pour voir la liste de toutes les instances, vous pouvez exécuter la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1626f-129">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="1626f-130">Pour mettre à niveau un utilisateur en ligne vers le mode TeamsOnly, affectez l’instance « UpgradeToTeams » :</span><span class="sxs-lookup"><span data-stu-id="1626f-130">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="1626f-131">Pour mettre à niveau un utilisateur Skype Entreprise site vers le mode TeamsOnly, utilisez Move-CsUser dans le jeu d’outils local :</span><span class="sxs-lookup"><span data-stu-id="1626f-131">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

<span data-ttu-id="1626f-132">Pour modifier le mode pour tous les utilisateurs du client, à l’exception de ceux qui ont une autorisation explicite par utilisateur (qui prend la priorité), exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1626f-132">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="1626f-133">Si vous avez des utilisateurs Skype Entreprise comptes locaux, vous ne pouvez pas affecter le mode TeamsOnly au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="1626f-133">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="1626f-134">Vous devez déplacer ces utilisateurs individuellement vers Teams mode Uniquement à l’aide de Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="1626f-134">You must move these users individually to Teams Only mode using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="1626f-135">Utilisation des notifications dans Skype Entreprise clients</span><span class="sxs-lookup"><span data-stu-id="1626f-135">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="1626f-136">Les administrateurs ont la possibilité de fournir des notifications aux utilisateurs finaux dans le client Skype Entreprise pour informer les utilisateurs qu’ils seront bientôt mis à niveau vers Teams, comme illustré dans le diagramme suivant.</span><span class="sxs-lookup"><span data-stu-id="1626f-136">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="1626f-137">Par exemple, une semaine avant que l’administrateur envisage de mettre à niveau un groupe d’utilisateurs en mode TeamsOnly, l’administrateur peut activer ces notifications pour ce groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1626f-137">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="1626f-138">Ces notifications sont activées à l’aide d’une instance de TeamsUpgradePolicy avec NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="1626f-138">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="1626f-139">Pour tous les modes autres que TeamsOnly, il existe en réalité deux instances par mode, correspondant aux deux valeurs de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="1626f-139">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="1626f-140">Pour tous les modes autres que TeamsOnly, il existe en réalité deux instances par mode, correspondant aux deux valeurs de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="1626f-140">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagramme montrant les notifications](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="1626f-142">Si vos utilisateurs sont homed in Skype Entreprise Online, affectez simplement l’instance de stratégie ayant le même mode que l’utilisateur, mais avec NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="1626f-142">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="1626f-143">Si vos utilisateurs sont accueil dans Skype Entreprise Server local, vous devez utiliser le groupe d’outils local et vous devez utiliser Skype Entreprise Server 2019 ou CU8 pour Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1626f-143">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="1626f-144">Pour les utilisateurs homed in Skype Entreprise Server local, la propriété de mode de l’instance en ligne de TeamsUpgradePolicy est honorée, mais la propriété NotifySfbUsers ne l’est pas.</span><span class="sxs-lookup"><span data-stu-id="1626f-144">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="1626f-145">Si vous souhaitez recevoir des notifications, vous devez créer une instance sur site de TeamsUpgradePolicy pour contrôler le comportement du client.</span><span class="sxs-lookup"><span data-stu-id="1626f-145">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="1626f-146">Dans la fenêtre PowerShell en local, créez une instance de TeamsUpgradePolicy avec NotifySfbUsers=true :</span><span class="sxs-lookup"><span data-stu-id="1626f-146">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="1626f-147">Ensuite, à l’aide de la même fenêtre PowerShell en local, affectez cette nouvelle stratégie aux utilisateurs souhaités :</span><span class="sxs-lookup"><span data-stu-id="1626f-147">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="1626f-148">Migration de réunions</span><span class="sxs-lookup"><span data-stu-id="1626f-148">Meeting migration</span></span>

<span data-ttu-id="1626f-149">Lorsqu’un utilisateur est migré vers le mode TeamsOnly, par défaut ses Skype Entreprise réunions existantes qu’il a organisées sont converties en Teams.</span><span class="sxs-lookup"><span data-stu-id="1626f-149">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="1626f-150">Vous pouvez éventuellement désactiver le comportement par défaut lors de l’attribution du mode TeamsOnly à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1626f-150">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="1626f-151">Lors du déplacement d’utilisateurs à partir du site, les réunions doivent être migrées vers le cloud pour fonctionner avec le compte d’utilisateur en ligne, mais si vous ne spécifiez pas -MoveToTeams, les réunions seront migrées en tant que réunions Skype Entreprise, au lieu d’être converties en Teams.</span><span class="sxs-lookup"><span data-stu-id="1626f-151">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="1626f-152">Lors de l’attribution du mode TeamsOnly au niveau du client, la migration de réunions n’est déclenchée pour aucun utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1626f-152">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="1626f-153">Si vous souhaitez attribuer le mode TeamsOnly au niveau du client et migrer des réunions, vous pouvez utiliser PowerShell pour obtenir la liste des utilisateurs dans le client (par exemple, en utilisant Get-CsOnlineUser avec les filtres nécessaires), puis passer en boucle chacun de ces utilisateurs pour déclencher la migration de réunion à l’aide de Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="1626f-153">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="1626f-154">Pour plus d’informations, [consultez Utiliser meeting Migration Service (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="1626f-154">For details, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="1626f-155">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="1626f-155">Related links</span></span>

[<span data-ttu-id="1626f-156">Modes de coexistence - Référence</span><span class="sxs-lookup"><span data-stu-id="1626f-156">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="1626f-157">Configurer la connectivité hybride entre les Skype Entreprise Server et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="1626f-157">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="1626f-158">Déplacer des utilisateurs entre l’environnement local et le cloud</span><span class="sxs-lookup"><span data-stu-id="1626f-158">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="1626f-159">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="1626f-159">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="1626f-160">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="1626f-160">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="1626f-161">Utilisation du service Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="1626f-161">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
