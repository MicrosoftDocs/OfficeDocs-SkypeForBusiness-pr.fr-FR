---
title: Déplacer vos équipes de StaffHub vers Shifts dans Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment déplacer vos équipes Microsoft StaffHub et planifier des données vers Shifts dans Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780808"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="daa95-103">Faire passer vos équipes de Microsoft StaffHub vers Shifts dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-103">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="daa95-104">Microsoft StaffHub sera retiré le 1er octobre 2019.</span><span class="sxs-lookup"><span data-stu-id="daa95-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="daa95-105">Nous développons les fonctionnalités StaffHub dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="daa95-106">Aujourd’hui, Teams inclut l’application Shifts pour la gestion de la planification et des fonctionnalités supplémentaires seront déployées à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="daa95-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="daa95-107">StaffHub cessera de fonctionner pour tous les utilisateurs le 1er octobre 2019.</span><span class="sxs-lookup"><span data-stu-id="daa95-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="daa95-108">Toute personne qui essaie d’ouvrir StaffHub verra s’afficher un message lui permettant de télécharger Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="daa95-109">Pour en savoir plus, consultez l’article [Retrait de Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="daa95-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="daa95-110">L’application Shifts dans Teams offre une approche simple pour gérer les plannings et le flux constant des échanges et des annulations de planning qui se produisent quotidiennement.</span><span class="sxs-lookup"><span data-stu-id="daa95-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="daa95-111">Les membres d’une équipe peuvent accéder à leurs informations de planification et de services directement dans l’application et sur leurs appareils pour définir leurs préférences, gérer leurs plannings et demander des congés.</span><span class="sxs-lookup"><span data-stu-id="daa95-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="daa95-112">Cet article vous explique comment déplacer les équipes StaffHub de votre organisation et planifier des données de Shifts dans Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="daa95-113">Cela couvre les sujets suivants :</span><span class="sxs-lookup"><span data-stu-id="daa95-113">It covers:</span></span>

- [<span data-ttu-id="daa95-114">Ce que vous devez savoir sur la migration vers Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="daa95-115">Préparation</span><span class="sxs-lookup"><span data-stu-id="daa95-115">Prepare Schema</span></span>](#prepare)
- [<span data-ttu-id="daa95-116">Organiser un projet pilote</span><span class="sxs-lookup"><span data-stu-id="daa95-116">Conduct a user pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="daa95-117">Aller au-delà de votre pilote et déplacer toutes les équipes StaffHub</span><span class="sxs-lookup"><span data-stu-id="daa95-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="daa95-118">Surveiller l’utilisation de Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="daa95-119">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="daa95-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="daa95-120">Que vous travailliez dans une petite entreprise avec une ou deux équipes StaffHub ou une grande entreprise disposant de centaines d’équipes StaffHub, vous trouverez ici les conseils d’administration nécessaires pour améliorer la transition vers Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="daa95-121">Vous devez être un administrateur général pour effectuer les étapes décrites dans cet article.</span><span class="sxs-lookup"><span data-stu-id="daa95-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="daa95-122">Si vous ne l’avez pas déjà fait, consultez le [forum aux questions sur le retrait StaffHub](microsoft-staffhub-to-be-retired.md)pour obtenir des réponses aux questions que vous vous posez.</span><span class="sxs-lookup"><span data-stu-id="daa95-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="daa95-123">Ce que vous devez savoir sur la migration vers Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="daa95-124">Quand déplacer vers Teams ?</span><span class="sxs-lookup"><span data-stu-id="daa95-124">When to move to Teams</span></span>

<span data-ttu-id="daa95-125">StaffHub sera retiré le 1er octobre 2019.</span><span class="sxs-lookup"><span data-stu-id="daa95-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="daa95-126">Nous vous encourageons à commencer à utiliser Teams aujourd’hui et à migrer les équipes et les utilisateurs de votre organisation à partir de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="daa95-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="daa95-127">Avec la gestion des planifications comme la fonctionnalité la plus fréquemment utilisée dans StaffHub, nous vous recommandons d’utiliser l’application Shifts dans Teams pour continuer.</span><span class="sxs-lookup"><span data-stu-id="daa95-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="daa95-128">Ce qui est déplacé vers Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-128">What is moved to Teams</span></span>

<span data-ttu-id="daa95-129">Les détails de l’utilisateur, les informations de calendrier, les conversations et les données de fichier sont transférés vers Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-129">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="daa95-130">Cela inclut les membres de l’équipe, les plannings d’équipe, les conversations et les fichiers des 90 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="daa95-130">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="daa95-131">Chaque équipe StaffHub a besoin d’un groupe Office 365 correspondant.</span><span class="sxs-lookup"><span data-stu-id="daa95-131">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="daa95-132">Si une équipe StaffHub ne possède pas de groupe Office 365 associé, un groupe Office est automatiquement créé pour vous permettre de prendre en charge la transition.</span><span class="sxs-lookup"><span data-stu-id="daa95-132">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="daa95-133">Étant donné la différence entre les noms d’équipes et les noms des groupes entre Teams et StaffHub, vous risquez d’avoir un nom d’équipe différent dans Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-133">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="daa95-134">Au fur et à mesure que vous transférez des équipes de StaffHub à Teams, les utilisateurs n’ont plus accès à leur planning dans StaffHub et sont redirigés vers Shifts dans Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-134">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="daa95-135">Nous vous recommandons de communiquer ce changement au sein de votre organisation pour minimiser les perturbations et encourager les utilisateurs à adopter et explorer Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-135">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="daa95-136">Si vous avez Azure AD Premium, vous pouvez [exécuter un rapport](run-report-to-show-staffhub-usage.md) pour obtenir la liste des utilisateurs StaffHub au sein de votre organisation qui ont besoin d’en savoir plus sur cette modification.</span><span class="sxs-lookup"><span data-stu-id="daa95-136">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="daa95-137">Il n’existe pas d’option de restauration une fois que vous avez déplacé une équipe StaffHub vers Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-137">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="daa95-138">Expérience utilisateur lorsque vous déplacez une équipe</span><span class="sxs-lookup"><span data-stu-id="daa95-138">User experience when you move a team</span></span>

<span data-ttu-id="daa95-139">Il y a peu de temps d’arrêt (moins d’une seconde, le cas échéant) pour les utilisateurs lorsque leurs équipes passent de StaffHub à Shifts dans Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-139">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="daa95-140">Les utilisateurs peuvent continuer à utiliser StaffHub jusqu’à ce que la migration vers Teams soit terminée.</span><span class="sxs-lookup"><span data-stu-id="daa95-140">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="daa95-141">Une fois le déplacement terminé, les membres de l’équipe voient s’afficher un message leur indiquant qu’ils doivent commencer à utiliser Shifts dans Teams pour accéder à leur planning d’équipe.</span><span class="sxs-lookup"><span data-stu-id="daa95-141">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="daa95-142">Voici un exemple de message que les utilisateurs voient dans StaffHub une fois l’équipe StaffHub déplacée vers Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-142">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="daa95-143">![Exemple de message que voient les utilisateurs.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Voici un exemple de message que les utilisateurs voient dans StaffHub une fois l’équipe StaffHub déplacée vers Teams")</span><span class="sxs-lookup"><span data-stu-id="daa95-143">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="daa95-144">Préparer</span><span class="sxs-lookup"><span data-stu-id="daa95-144">Prepare Schema</span></span>

<span data-ttu-id="daa95-145">Pour préparer la migration vers Teams, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="daa95-145">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="daa95-146">Vérifier que les conditions préalables sont remplies</span><span class="sxs-lookup"><span data-stu-id="daa95-146">Ensure that deployment prerequisites are met</span></span>

<span data-ttu-id="daa95-147">Avant de transférer une équipe StaffHub à Teams, assurez-vous que :</span><span class="sxs-lookup"><span data-stu-id="daa95-147">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="daa95-148">L’utilisateur connecté est un administrateur général.</span><span class="sxs-lookup"><span data-stu-id="daa95-148">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="daa95-149">Teams est activé pour tous les utilisateurs du client.</span><span class="sxs-lookup"><span data-stu-id="daa95-149">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="daa95-150">La création de groupes Office 365 est activée dans le client.</span><span class="sxs-lookup"><span data-stu-id="daa95-150">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="daa95-151">Le teamId StaffHub est valide.</span><span class="sxs-lookup"><span data-stu-id="daa95-151">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="daa95-152">L’équipe StaffHub contient des membres.</span><span class="sxs-lookup"><span data-stu-id="daa95-152">The StaffHub team contains members.</span></span> 
- <span data-ttu-id="daa95-153">Tous les membres de l’équipe StaffHub sont liés à un compte Azure AD.</span><span class="sxs-lookup"><span data-stu-id="daa95-153">All StaffHub team members are linked to an Azure AD account.</span></span> 

<span data-ttu-id="daa95-154">Si ces conditions préalables ne sont pas remplies, la demande de déplacement échouera.</span><span class="sxs-lookup"><span data-stu-id="daa95-154">If these prerequisites aren't met, the move request will fail.</span></span> 

### <a name="assign-teams-licenses"></a><span data-ttu-id="daa95-155">Assigner des licences Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-155">Assign Teams licenses</span></span>

<span data-ttu-id="daa95-156">Chaque utilisateur doit avoir une licence Microsoft 365 ou Office 365 active d' [un plan éligible](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) et une licence de Teams doit lui être attribuée.</span><span class="sxs-lookup"><span data-stu-id="daa95-156">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="daa95-157">L’attribution d’une licence Teams permet aux utilisateurs d’accéder à Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-157">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="daa95-158">Vous gérez les licences de Teams dans le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="daa95-158">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="daa95-159">Pour en savoir plus, reportez-vous à la rubrique [Gestion de l'accès des utilisateurs à Microsoft Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="daa95-159">To learn more, see [Manage user access to Microsoft Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="daa95-160">Si votre organisation utilise Skype Entreprise et que vous n’êtes pas prêt à déplacer tous vos utilisateurs vers Teams, vous pouvez activer Teams pour vos employés de terrain qui peuvent alors exécuter Teams en parallèle de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="daa95-160">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="daa95-161">Avec ce mode de coexistence, intitulé*Islands*, chaque application cliente fonctionne comme une solution distincte.</span><span class="sxs-lookup"><span data-stu-id="daa95-161">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="daa95-162">Pour en savoir plus, lisez la rubrique [Comprendre la coexistence et l’interopérabilité de Teams et Skype Entreprise](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="daa95-162">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="daa95-163">Installer le module PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="daa95-163">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="daa95-164">Si vous ne l’avez pas encore fait,[Installer le module PowerShell StaffHub](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="daa95-164">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="daa95-165">Configurer des comptes pour les utilisateurs de StaffHub qui n’ont pas d’identité dans Azure AD</span><span class="sxs-lookup"><span data-stu-id="daa95-165">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="daa95-166">Chaque responsable et membre de l’équipe doivent avoir une identité dans Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="daa95-166">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="daa95-167">Si un utilisateur n’a pas encore d’identité dans Azure AD, configurez un compte pour lui.</span><span class="sxs-lookup"><span data-stu-id="daa95-167">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="daa95-168">Voici comment procéder.</span><span class="sxs-lookup"><span data-stu-id="daa95-168">Here's how.</span></span> 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a><span data-ttu-id="daa95-169">Obtenir la liste de tous les utilisateurs d’équipes StaffHub qui ont des membres d’équipe qui n’ont pas été configurés avec un compte Azure AD</span><span class="sxs-lookup"><span data-stu-id="daa95-169">Get a list of all users on StaffHub teams that have team members that aren't provisioned with an Azure AD account</span></span>

<span data-ttu-id="daa95-170">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="daa95-170">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a><span data-ttu-id="daa95-171">Configuration du compte</span><span class="sxs-lookup"><span data-stu-id="daa95-171">Provision the account</span></span>

<span data-ttu-id="daa95-172">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="daa95-172">Do one of the following:</span></span>

- <span data-ttu-id="daa95-173">Convertissez le compte et liez-le à un compte configuré.</span><span class="sxs-lookup"><span data-stu-id="daa95-173">Convert and link the account to a provisioned account.</span></span>

  <span data-ttu-id="daa95-174">Les propriétaires et responsables d’équipes StaffHub peuvent convertir un compte factice ou inactif et le lier à un compte configuré dans StaffHub en remplaçant l’adresse de messagerie de l’utilisateur par un nom d’utilisateur principal valide dans la page Paramètres d’équipe StaffHub.</span><span class="sxs-lookup"><span data-stu-id="daa95-174">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="daa95-175">Supprimez le compte non configuré, puis rajoutez-le à l’aide du nom d’utilisateur principal.</span><span class="sxs-lookup"><span data-stu-id="daa95-175">Remove the non-provisioned account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="daa95-176">Exécutez l'applet de commande [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) pour supprimer le compte non approvisionné de l’équipe StaffHub.</span><span class="sxs-lookup"><span data-stu-id="daa95-176">Run the [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="daa95-177">Exécutez l'applet de commande[Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) pour rajouter le compte à l’équipe StaffHub à l’aide du nom d’utilisateur principal.</span><span class="sxs-lookup"><span data-stu-id="daa95-177">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span> 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="daa95-178">Attribuer la stratégie de configuration de l’application FirstlineWorker aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="daa95-178">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="daa95-179">Teams inclut une stratégie de configuration d’application FirstlineWorker intégrée que vous pouvez utiliser pour personnaliser Teams afin de mettre en évidence les applications les plus importantes pour les employés terrain de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="daa95-179">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="daa95-180">Lorsque vous affectez cette stratégie à des utilisateurs, les applications de la stratégie sont épinglées à la barre de l’application dans Teams pour un accès rapide et facile.</span><span class="sxs-lookup"><span data-stu-id="daa95-180">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="daa95-181">Les autres applications ajoutées à Teams sont accessibles dans la barre d’application en cliquant sur **... Autres applications** sur le bureau Teams et les clients Web et en balayant vers le haut dans le client mobile Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-181">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="daa95-182">Par défaut, la stratégie de configuration de l’application FirstlineWorker inclut les applications Activité, Shifts, Chat et Appels.</span><span class="sxs-lookup"><span data-stu-id="daa95-182">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="daa95-183">Pour connaître la procédure d’affectation de la stratégie de configuration de l’application FirstlineWorker aux utilisateurs, voir [utiliser la stratégie de configuration de l’application FirstlineWorker pour épingler Shifts à Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span><span class="sxs-lookup"><span data-stu-id="daa95-183">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="daa95-184">Une fois que vous avez affecté une stratégie, la prise en compte peut prendre jusqu’à 24 heures.</span><span class="sxs-lookup"><span data-stu-id="daa95-184">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="daa95-185">Nous vous recommandons d’effectuer cette étape au moins une semaine avant de déplacer vos équipes StaffHub et vos utilisateurs vers Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-185">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="daa95-186">Lorsque les utilisateurs sont membres de Teams, assurez-vous qu’ils peuvent voir et accéder à l’application Shifts.</span><span class="sxs-lookup"><span data-stu-id="daa95-186">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="daa95-187">Vous pouvez également créer des stratégies de configuration d’applications personnalisées et modifier les paramètres dans la stratégie d’installation globale de l’application.</span><span class="sxs-lookup"><span data-stu-id="daa95-187">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="daa95-188">Pour en savoir plus, voir [gérer les stratégies de configuration des applications dans Teams](../../teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="daa95-188">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="daa95-189">Intégrer des utilisateurs à Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-189">Onboard users to Teams</span></span>

<span data-ttu-id="daa95-190">Dans le cadre de votre stratégie d’intégration, fournissez des formations et des instructions aux utilisateurs pour leur permettre de se familiariser avec Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-190">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="daa95-191">N’oubliez pas d’inclure les ressources suivantes pour qu’ils sachent où obtenir des clients Teams, les formations et le support :</span><span class="sxs-lookup"><span data-stu-id="daa95-191">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="daa95-192">Client Web Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-192">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="daa95-193">Liens de téléchargement du client de bureau et mobile</span><span class="sxs-lookup"><span data-stu-id="daa95-193">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="daa95-194">Vidéos de formation Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-194">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="daa95-195">Documentation d'aide Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-195">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="daa95-196">Pour obtenir des instructions sur le déploiement de Teams et la conduite de l’adoption de Teams, voir comment[déployer Teams](../../How-to-roll-out-teams.md) et [adopter Teams](../../adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="daa95-196">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="daa95-197">Mener un projet pilote</span><span class="sxs-lookup"><span data-stu-id="daa95-197">Conduct a user pilot</span></span>

<span data-ttu-id="daa95-198">Nous vous recommandons de commencer par déplacer deux ou trois équipes StaffHub pour un groupe sélectionné d’adoptions précoces.</span><span class="sxs-lookup"><span data-stu-id="daa95-198">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="daa95-199">L’exécution d’un pilote vous permet d’affiner votre plan de transition et de vous assurer que vous êtes prêt à déplacer toutes les équipes StaffHub de votre organisation vers Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-199">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="daa95-200">Il permet également d’identifier les champions qui peuvent favoriser l’adoption au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="daa95-200">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="daa95-201">Si vous êtes une petite entreprise qui n’a pas besoin d’une approche progressive, il se peut que tout ce que vous avez besoin de faire est effectuer la procédure décrite dans cette section pour passer de StaffHub à Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-201">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="daa95-202">Identification des équipes pilotes</span><span class="sxs-lookup"><span data-stu-id="daa95-202">Identify pilot teams</span></span>

<span data-ttu-id="daa95-203">Renseignez-vous sur l’identification de deux ou trois équipes pilotes.</span><span class="sxs-lookup"><span data-stu-id="daa95-203">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="daa95-204">Tous les membres de l’équipe doivent s’engager à utiliser Shifts dans Teams pour gérer leurs plannings et communiquer et collaborer ensemble.</span><span class="sxs-lookup"><span data-stu-id="daa95-204">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="daa95-205">Identifier les champions d’équipe</span><span class="sxs-lookup"><span data-stu-id="daa95-205">Identify team champions</span></span>

<span data-ttu-id="daa95-206">Identifiez les champions au sein des équipes pilotes et encadrez-les pour favoriser la promotion de Shifts.</span><span class="sxs-lookup"><span data-stu-id="daa95-206">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="daa95-207">Les champions d’équipe sont passionnés par ce qu’ils font, partageant leurs propres apprentissages pour offrir un support et des conseils aux membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="daa95-207">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="daa95-208">Les champions d’équipe peuvent être des responsables d’équipe ou des gestionnaires.</span><span class="sxs-lookup"><span data-stu-id="daa95-208">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="daa95-209">Les champions d’équipe doivent s’assurer que les membres de l’équipe sont configurés en leur permettant d’[obtenir des clients Teams](../../get-clients.md), de se connecter à Teams et de consulter leur planning dans Shifts, et de commencer à discuter.</span><span class="sxs-lookup"><span data-stu-id="daa95-209">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="daa95-210">Les utilisateurs qui connaissent déjà StaffHub seront opérationnels rapidement dans Shifts.</span><span class="sxs-lookup"><span data-stu-id="daa95-210">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="daa95-211">Vous pouvez également les diriger vers [l’aide Shifts](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) pour obtenir de l’aide supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="daa95-211">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="daa95-212">Déplacer une équipe StaffHub</span><span class="sxs-lookup"><span data-stu-id="daa95-212">Move a StaffHub team</span></span>

<span data-ttu-id="daa95-213">Pour déplacer une équipe StaffHub à la fois, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="daa95-213">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="daa95-214">Nous vous recommandons d’utiliser cette approche pour vos équipes pilotes.</span><span class="sxs-lookup"><span data-stu-id="daa95-214">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="daa95-215">Plus tard, lorsque vous serez prêt à déplacer toutes les équipes StaffHub de votre organisation, voir [déplacer vos équipes StaffHub](#move-your-staffhub-teams) pour connaître la procédure de déplacement de plusieurs équipes à la fois.</span><span class="sxs-lookup"><span data-stu-id="daa95-215">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="daa95-216">Exécutez la commande suivante pour déplacer une équipe StaffHub.</span><span class="sxs-lookup"><span data-stu-id="daa95-216">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="daa95-217">Exemple :</span><span class="sxs-lookup"><span data-stu-id="daa95-217">Example</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="daa95-218">Voici un exemple de réponse que vous obtenez lorsque vous envoyez une demande de déplacement d’une équipe StaffHub vers Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-218">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="daa95-219">Procédez comme suit pour vérifier l’état de vos demandes de déplacement.</span><span class="sxs-lookup"><span data-stu-id="daa95-219">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="daa95-220">Exemple :</span><span class="sxs-lookup"><span data-stu-id="daa95-220">Example</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="daa95-221">Voici un exemple de réponse que vous obtenez lorsqu’un déplacement est en cours.</span><span class="sxs-lookup"><span data-stu-id="daa95-221">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="daa95-222">Déplacer des fichiers d’une équipe StaffHub vers Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-222">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="daa95-223">Cette étape s’applique uniquement si l’équipe StaffHub que vous avez déplacée vers Teams a des fichiers que vous voulez déplacer également vers Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-223">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="daa95-224">Vous pouvez déplacer des fichiers directement dans SharePoint Online ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="daa95-224">You can move files directly in SharePoint Online or by using PowerShell.</span></span> 

#### <a name="in-sharepoint-online"></a><span data-ttu-id="daa95-225">Dans SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="daa95-225">In SharePoint Online</span></span>

<span data-ttu-id="daa95-226">Découvrez [comment déplacer des fichiers dans SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span><span class="sxs-lookup"><span data-stu-id="daa95-226">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="daa95-227">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="daa95-227">Using Windows PowerShell</span></span>

<span data-ttu-id="daa95-228">Téléchargez et installez le fichier [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588) si ce n’est pas déjà fait.</span><span class="sxs-lookup"><span data-stu-id="daa95-228">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="daa95-229">Il contient les applets de commande dont vous avez besoin pour déplacer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="daa95-229">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="daa95-230">Utilisez l'applet de commande [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps)pour vous connecter au site d’équipe SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="daa95-230">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="daa95-231">Pour chaque fichier que vous voulez déplacer de StaffHub à Teams, utilisez l'applet de commande [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile)pour déplacer le fichier.</span><span class="sxs-lookup"><span data-stu-id="daa95-231">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="daa95-232">Pour déplacer plusieurs fichiers, parcourez les fichiers et exécutez la deuxième commande sur la boucle.</span><span class="sxs-lookup"><span data-stu-id="daa95-232">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="daa95-233">Vous n’avez pas besoin de répéter la première commande si la session reste active.</span><span class="sxs-lookup"><span data-stu-id="daa95-233">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="daa95-234">Aller au-delà de votre pilote et déplacer toutes les équipes StaffHub</span><span class="sxs-lookup"><span data-stu-id="daa95-234">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="daa95-235">Sensibilisation</span><span class="sxs-lookup"><span data-stu-id="daa95-235">Raise awareness</span></span>

<span data-ttu-id="daa95-236">Lorsque vous êtes prêt à aller au-delà de vos équipes pilotes et à déplacer les équipes StaffHub de votre organisation vers Teams, il est important de commencer par communiquer la modification au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="daa95-236">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="daa95-237">Diffusez la nouvelle sur Shifts et la transition vers Teams afin de sensibiliser les membres, de susciter l’enthousiasme et d’adopter l’adoption.</span><span class="sxs-lookup"><span data-stu-id="daa95-237">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="daa95-238">Déplacer vos équipes StaffHub</span><span class="sxs-lookup"><span data-stu-id="daa95-238">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>

<span data-ttu-id="daa95-239">Pour déplacer toutes les équipes StaffHub en même temps, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="daa95-239">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="daa95-240">Vous pouvez choisir de déplacer toutes les équipes StaffHub de votre organisation ou de déplacer des équipes StaffHub spécifiques.</span><span class="sxs-lookup"><span data-stu-id="daa95-240">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="daa95-241">Si vous voulez déplacer StaffHub équipes l’une après l’autre, voir [déplacer une équipe StaffHub](#move-a-staffhub-team).</span><span class="sxs-lookup"><span data-stu-id="daa95-241">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="daa95-242">Déplacer toutes vos équipes StaffHub</span><span class="sxs-lookup"><span data-stu-id="daa95-242">Move all StaffHub teams</span></span>

<span data-ttu-id="daa95-243">Exécutez la commande suivante pour obtenir la liste de toutes les équipes StaffHub au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="daa95-243">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="daa95-244">Ensuite, exécutez la commande suivante pour déplacer toutes les équipes.</span><span class="sxs-lookup"><span data-stu-id="daa95-244">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="daa95-245">Voici un exemple de la réponse.</span><span class="sxs-lookup"><span data-stu-id="daa95-245">Here's an example of the response.</span></span>

<span data-ttu-id="daa95-246">Pour les équipes qui ont déjà été déplacées vers Teams ou qui existent déjà dans Teams, le jobId est «nul», car il n’est pas nécessaire d’effectuer une tâches pour déplacer l’équipe.</span><span class="sxs-lookup"><span data-stu-id="daa95-246">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="daa95-247">Déplacer des équipes StaffHub spécifiques</span><span class="sxs-lookup"><span data-stu-id="daa95-247">Move specific StaffHub teams</span></span>

<span data-ttu-id="daa95-248">Exécutez la commande suivante pour obtenir la liste de tous les ID d’équipes StaffHub au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="daa95-248">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="daa95-249">Dans les résultats renvoyés par `Get-StaffHubteamsForTenant` l’applet de commande que vous avez exécutée précédemment, sélectionnez les ID d’équipe que vous voulez déplacer, puis ajoutez-les à un fichier CSV (valeurs séparées par des virgules).</span><span class="sxs-lookup"><span data-stu-id="daa95-249">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="daa95-250">Voici un exemple de mise en forme du fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="daa95-250">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="daa95-251">Id</span><span class="sxs-lookup"><span data-stu-id="daa95-251">ID</span></span>  |
|---------|
|<span data-ttu-id="daa95-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="daa95-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="daa95-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="daa95-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="daa95-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="daa95-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="daa95-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="daa95-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="daa95-256">Une fois que vous avez créé le fichier CSV, exécutez la commande suivante pour déplacer les équipes que vous avez spécifiées dans le fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="daa95-256">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="daa95-257">Vérifier que vos équipes StaffHub ont été déplacées vers Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-257">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="daa95-258">Exécutez la commande suivante pour obtenir la liste de toutes les équipes Shifts au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="daa95-258">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="daa95-259">Déplacer des fichiers de vos équipes StaffHub vers Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-259">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="daa95-260">Si les équipes StaffHub que vous avez déplacées contiennent des fichiers que vous voulez déplacer vers Teams, voir [déplacer des fichiers d’une équipe StaffHub vers Teams](#move-files-from-a-staffhub-team-to-teams).</span><span class="sxs-lookup"><span data-stu-id="daa95-260">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="daa95-261">Surveiller l’utilisation de Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-261">Monitor Teams usage</span></span>

<span data-ttu-id="daa95-262">Les rapports d’utilisation peuvent vous aider à mieux comprendre les modèles d’utilisation et vous donne la perspective nécessaire pour savoir où hiérarchiser les efforts de formation et de communication dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="daa95-262">Usage reports can help you better understand usage patterns, and along with user feedback, give you insights to inform your wider rollout and where to prioritize training and communication efforts.</span></span> <span data-ttu-id="daa95-263">Étant donné que Shifts est une application dans Teams, vous pouvez afficher l’utilisation via les rapports de Teams.</span><span class="sxs-lookup"><span data-stu-id="daa95-263">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="daa95-264">Pour plus d’informations, voir[Création de rapports Teams dans le Centre d’administration Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md)et[Rapports sur l’activité de Teams dans le Centre d’administration Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="daa95-264">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="daa95-265">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="daa95-265">Troubleshooting</span></span> 

<span data-ttu-id="daa95-266">**Lorsque vous tentez de déplacer des fichiers de StaffHub à Teams, un message d’erreur «autorisation refusée» s’affiche.**</span><span class="sxs-lookup"><span data-stu-id="daa95-266">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="daa95-267">Cela peut se produire si vous essayez de déplacer des fichiers dans un groupe Office 365 privé dont vous n’êtes pas membre.</span><span class="sxs-lookup"><span data-stu-id="daa95-267">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="daa95-268">Si c’est le cas, utilisez l'applet de commande [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) pour vous ajouter à l’équipe StaffHub, puis déplacez les fichiers.</span><span class="sxs-lookup"><span data-stu-id="daa95-268">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="daa95-269">Une fois les fichiers déplacés, utilisez l’applet de commande [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember)pour vous supprimer de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="daa95-269">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="daa95-270">**Lorsque vous essayez de déplacer des fichiers de StaffHub à Teams, un message d’erreur indique que le dossier général n’existe pas.**</span><span class="sxs-lookup"><span data-stu-id="daa95-270">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="daa95-271">Exécutez la commande suivante pour ajouter le dossier général à SharePoint, puis réessayez :</span><span class="sxs-lookup"><span data-stu-id="daa95-271">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="daa95-272">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="daa95-272">Related topics</span></span>
- [<span data-ttu-id="daa95-273">Comment déployer Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-273">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="daa95-274">Fin de parcours pour Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="daa95-274">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="daa95-275">Gérer l’application Shifts pour votre organisation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="daa95-275">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="daa95-276">Référence PowerShell StaffHub</span><span class="sxs-lookup"><span data-stu-id="daa95-276">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
