---
title: Déplacez vos équipes StaffHub vers des équipes
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu, gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment déplacer vos équipes Microsoft StaffHub et planifier des données en équipes dans Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- SPO_Content
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e0bf24c32854ddf2498b8a00874ad1d358c8fb8a
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326791"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="63edc-103">Déplacer vos équipes Microsoft StaffHub vers des équipes dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="63edc-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63edc-104">À compter du 31 décembre 2019, Microsoft StaffHub sera supprimé.</span><span class="sxs-lookup"><span data-stu-id="63edc-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="63edc-105">Nous développons des fonctionnalités StaffHub dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="63edc-106">Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps.</span><span class="sxs-lookup"><span data-stu-id="63edc-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="63edc-107">StaffHub s’arrêtera de fonctionner pour tous les utilisateurs du 31 décembre 2019.</span><span class="sxs-lookup"><span data-stu-id="63edc-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="63edc-108">Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="63edc-109">Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="63edc-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="63edc-110">L’application Shifts dans teams fournit une méthode simple pour gérer les plannings et le flux constant de permutations et d’annulations de Shift qui se produisent quotidiennement.</span><span class="sxs-lookup"><span data-stu-id="63edc-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="63edc-111">Les membres d’une équipe peuvent accéder à leur planning et leur transférer directement dans l’application et sur leurs appareils pour définir leurs préférences, gérer leur planning et demander un congé.</span><span class="sxs-lookup"><span data-stu-id="63edc-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="63edc-112">Cet article vous explique comment déplacer les équipes StaffHub de votre organisation et planifier vos données en vue de leur déplacement dans Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-112">This article walks you through how to move your organization's StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="63edc-113">Ce service comprend les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="63edc-113">It covers:</span></span>

- [<span data-ttu-id="63edc-114">Ce que vous devez savoir sur le déplacement dans teams</span><span class="sxs-lookup"><span data-stu-id="63edc-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="63edc-115">Prévenir</span><span class="sxs-lookup"><span data-stu-id="63edc-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="63edc-116">Conduire une pilote</span><span class="sxs-lookup"><span data-stu-id="63edc-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="63edc-117">Aller au-delà de votre pilote et déplacer toutes les équipes de StaffHub</span><span class="sxs-lookup"><span data-stu-id="63edc-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="63edc-118">Surveiller l’utilisation des équipes</span><span class="sxs-lookup"><span data-stu-id="63edc-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="63edc-119">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="63edc-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="63edc-120">Que vous soyez une petite entreprise disposant d’une ou de deux équipes StaffHub ou d’une grande entreprise ayant des centaines d’équipes, vous trouverez ci-dessous les conseils d’administration dont vous avez besoin pour faciliter la transition vers les équipes.</span><span class="sxs-lookup"><span data-stu-id="63edc-120">Whether you're a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you'll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="63edc-121">Pour pouvoir effectuer les étapes décrites dans cet article, vous devez être un administrateur général.</span><span class="sxs-lookup"><span data-stu-id="63edc-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="63edc-122">Si vous ne l’avez pas déjà fait, consultez le [Forum aux questions de retraite StaffHub](microsoft-staffhub-to-be-retired.md) pour obtenir des réponses aux questions que vous pourriez rencontrer.</span><span class="sxs-lookup"><span data-stu-id="63edc-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="63edc-123">Ce que vous devez savoir sur le déplacement dans teams</span><span class="sxs-lookup"><span data-stu-id="63edc-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="63edc-124">Quand déplacer vers teams</span><span class="sxs-lookup"><span data-stu-id="63edc-124">When to move to Teams</span></span>

<span data-ttu-id="63edc-125">À compter du 31 décembre 2019, StaffHub sera supprimé.</span><span class="sxs-lookup"><span data-stu-id="63edc-125">Effective December 31, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="63edc-126">Nous vous encourageons à commencer à utiliser teams dès aujourd’hui et à migrer les équipes et les utilisateurs de votre organisation à partir de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="63edc-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="63edc-127">Avec la gestion des plannings étant la fonctionnalité la plus couramment utilisée dans StaffHub, nous vous recommandons d’utiliser l’application Shifts dans les équipes qui progressent.</span><span class="sxs-lookup"><span data-stu-id="63edc-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="63edc-128">Ce qui est déplacé vers teams</span><span class="sxs-lookup"><span data-stu-id="63edc-128">What is moved to Teams</span></span>

<span data-ttu-id="63edc-129">Lorsque vous déplacez une équipe StaffHub, l’appartenance à une équipe, les détails de l’utilisateur, les planifications d’équipe et les données de conversation sont déplacées vers Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="63edc-130">Les fichiers ne sont pas déplacés lorsque vous déplacez une équipe StaffHub.</span><span class="sxs-lookup"><span data-stu-id="63edc-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="63edc-131">S’il s’agit d’une équipe StaffHub qui contient les fichiers que vous voulez déplacer vers Teams, vous pouvez déplacer les fichiers dans une autre étape.</span><span class="sxs-lookup"><span data-stu-id="63edc-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="63edc-132">Chaque équipe StaffHub doit avoir un groupe Office 365 correspondant.</span><span class="sxs-lookup"><span data-stu-id="63edc-132">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="63edc-133">Si une équipe StaffHub est associée à un groupe Office 365, le paramètre de confidentialité du groupe est conservé lorsque vous déplacez l’équipe.</span><span class="sxs-lookup"><span data-stu-id="63edc-133">If a StaffHub team is associated with an Office 365 Group, the privacy setting of the group is retained when you move the team.</span></span> <span data-ttu-id="63edc-134">Si une équipe StaffHub n’a pas de groupe Office 365 associé, un groupe avec un paramètre de confidentialité de privé est créé automatiquement pour que vous la prennez en charge.</span><span class="sxs-lookup"><span data-stu-id="63edc-134">If a StaffHub team doesn't have an Office 365 Group associated with it, a group with a privacy setting of Private is automatically created for you to support the transition.</span></span>  <span data-ttu-id="63edc-135">En raison de la différence entre les noms d’équipe et de groupe entre teams et StaffHub, il est possible que vous voyiez un nom d’équipe différent dans Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-135">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span> 

<span data-ttu-id="63edc-136">Lorsque vous transformez des équipes de StaffHub en équipes, les utilisateurs n’ont plus accès à leur planning dans StaffHub et sont redirigés vers des équipes dans Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-136">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="63edc-137">Nous vous recommandons de communiquer ce changement au sein de votre organisation afin de limiter les perturbations et d’encourager les utilisateurs à adopter et à explorer les équipes.</span><span class="sxs-lookup"><span data-stu-id="63edc-137">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="63edc-138">Si vous disposez d’Azure AD Premium, vous pouvez [exécuter un rapport](run-report-to-show-staffhub-usage.md) pour obtenir la liste des utilisateurs de StaffHub de votre organisation qui doivent savoir ce changement.</span><span class="sxs-lookup"><span data-stu-id="63edc-138">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="63edc-139">Il n’existe aucune option de restauration après le déplacement d’une équipe StaffHub vers Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-139">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="63edc-140">Utilisation de l’interface utilisateur lorsque vous déplacez une équipe</span><span class="sxs-lookup"><span data-stu-id="63edc-140">User experience when you move a team</span></span>

<span data-ttu-id="63edc-141">Il y a un minimum d’interruption de service (moins d’une seconde, le cas échéant) pour les utilisateurs lorsque leur équipe passe de StaffHub à équipes.</span><span class="sxs-lookup"><span data-stu-id="63edc-141">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="63edc-142">Les utilisateurs peuvent continuer à utiliser StaffHub jusqu’à ce que le passage aux équipes soit terminé.</span><span class="sxs-lookup"><span data-stu-id="63edc-142">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="63edc-143">Lorsque le déplacement est terminé, les membres de l’équipe voient s’afficher un message lui informant qu’ils doivent commencer par utiliser les Shifts dans teams pour accéder à leur planning d’équipe.</span><span class="sxs-lookup"><span data-stu-id="63edc-143">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="63edc-144">Voici un exemple du message que les utilisateurs voient dans StaffHub une fois que l’équipe StaffHub a été déplacée vers Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-144">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="63edc-145">![Exemple du message que les utilisateurs voient.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Exemple du message que les utilisateurs voient dans StaffHub après le déplacement de l’équipe StaffHub vers teams")</span><span class="sxs-lookup"><span data-stu-id="63edc-145">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="63edc-146">Prévenir</span><span class="sxs-lookup"><span data-stu-id="63edc-146">Prepare</span></span>

<span data-ttu-id="63edc-147">Voici comment préparer le déplacement vers Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-147">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="63edc-148">Vérifier que les conditions préalables sont remplies</span><span class="sxs-lookup"><span data-stu-id="63edc-148">Check that prerequisites are met</span></span>

<span data-ttu-id="63edc-149">Avant de déplacer une équipe StaffHub vers Teams, assurez-vous que :</span><span class="sxs-lookup"><span data-stu-id="63edc-149">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="63edc-150">L’utilisateur connecté est un administrateur global.</span><span class="sxs-lookup"><span data-stu-id="63edc-150">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="63edc-151">Équipes est activée pour tous les utilisateurs du client.</span><span class="sxs-lookup"><span data-stu-id="63edc-151">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="63edc-152">La création de groupes Microsoft 365 est activée dans le client.</span><span class="sxs-lookup"><span data-stu-id="63edc-152">Microsoft 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="63edc-153">StaffHub teamId est valide.</span><span class="sxs-lookup"><span data-stu-id="63edc-153">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="63edc-154">L’équipe StaffHub possède au moins un propriétaire d’équipe.</span><span class="sxs-lookup"><span data-stu-id="63edc-154">The StaffHub team has at least one team owner.</span></span>
- <span data-ttu-id="63edc-155">L’équipe StaffHub contient les membres.</span><span class="sxs-lookup"><span data-stu-id="63edc-155">The StaffHub team contains members.</span></span>
- <span data-ttu-id="63edc-156">Tous les membres de l’équipe StaffHub sont liés à un compte Azure AD.</span><span class="sxs-lookup"><span data-stu-id="63edc-156">All StaffHub team members are linked to an Azure AD account.</span></span>
- <span data-ttu-id="63edc-157">Tous les membres de l’équipe StaffHub disposent d’une licence Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-157">All StaffHub team members are assigned a Teams license.</span></span>  

<span data-ttu-id="63edc-158">Si ces éléments requis n’ont pas été satisfaits, la demande de déplacement échoue.</span><span class="sxs-lookup"><span data-stu-id="63edc-158">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="63edc-159">Assigner des licences Teams</span><span class="sxs-lookup"><span data-stu-id="63edc-159">Assign Teams licenses</span></span>

<span data-ttu-id="63edc-160">Chaque utilisateur doit avoir une licence Microsoft 365 ou Office 365 active d' [un plan éligible](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) et être disposant d’une licence d’équipe.</span><span class="sxs-lookup"><span data-stu-id="63edc-160">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="63edc-161">L’attribution d’une licence d’équipe aux utilisateurs leur permet d’accéder à Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-161">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="63edc-162">Pour gérer les licences d’équipe, vous devez utiliser le centre d’administration 365 Microsoft.</span><span class="sxs-lookup"><span data-stu-id="63edc-162">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="63edc-163">Pour en savoir plus, reportez-vous à la rubrique [Gestion de l'accès des utilisateurs à Microsoft Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="63edc-163">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="63edc-164">Si votre organisation utilise Skype entreprise et que vous n’êtes pas prêt à déplacer tous vos utilisateurs vers Teams, vous pouvez activer les équipes pour vos travailleurs terrain qui peuvent alors exécuter des équipes en même temps que Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="63edc-164">If your organization uses Skype for Business and you're not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="63edc-165">Dans ce mode de coexistence, intitulé *îlots*, chaque application cliente fonctionne en tant que solution distincte.</span><span class="sxs-lookup"><span data-stu-id="63edc-165">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="63edc-166">Pour en savoir plus, reportez-vous à la rubrique [Présentation des équipes et coexistence et interopérabilité de Skype entreprise](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="63edc-166">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a><span data-ttu-id="63edc-167">Installez la version préliminaire du module PowerShell StaffHub</span><span class="sxs-lookup"><span data-stu-id="63edc-167">Install the prerelease version of the StaffHub PowerShell module</span></span>

<span data-ttu-id="63edc-168">Si ce n’est déjà fait, [Installez la version préliminaire du module PowerShell StaffHub](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="63edc-168">If you haven't already, [install the prerelease version of the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="63edc-169">Vous devez avoir installé la version préliminaire du module pour déplacer vos équipes StaffHub vers Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-169">You must have the prerelease version of the module installed to move your StaffHub teams to Teams.</span></span>

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="63edc-170">Créer un lien vers un compte Azure AD pour les membres de l’équipe StaffHub qui n’en ont pas</span><span class="sxs-lookup"><span data-stu-id="63edc-170">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="63edc-171">Chaque membre de l’équipe StaffHub doit être lié à un compte Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="63edc-171">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="63edc-172">Les utilisateurs de votre organisation ne seront pas associés à un compte Azure AD si l’un des scénarios suivants s’appliquent :</span><span class="sxs-lookup"><span data-stu-id="63edc-172">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="63edc-173">Un propriétaire d’équipe a ajouté un utilisateur qui ne possède pas de compte Azure AD.</span><span class="sxs-lookup"><span data-stu-id="63edc-173">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="63edc-174">Un propriétaire d’équipe a invité un utilisateur à une équipe StaffHub et ce dernier n’a pas accepté l’invitation.</span><span class="sxs-lookup"><span data-stu-id="63edc-174">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="63edc-175">Ces utilisateurs ont des comptes inactifs et indiquent l’état d’utilisateur inconnu, invité ou InviteRejected.</span><span class="sxs-lookup"><span data-stu-id="63edc-175">These users have inactive accounts and show a user state of Unknown, Invited, or InviteRejected.</span></span> <span data-ttu-id="63edc-176">Vous pouvez lier un compte Azure AD pour ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="63edc-176">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="63edc-177">Voici comment procéder.</span><span class="sxs-lookup"><span data-stu-id="63edc-177">Here's how.</span></span>

#### <a name="get-a-list-of-all-inactive-accounts-on-staffhub-teams"></a><span data-ttu-id="63edc-178">Obtenir la liste de tous les comptes inactifs dans StaffHub teams</span><span class="sxs-lookup"><span data-stu-id="63edc-178">Get a list of all inactive accounts on StaffHub teams</span></span>

<span data-ttu-id="63edc-179">Pour obtenir la liste de tous les comptes inactifs dans StaffHub Teams, exécutez les commandes suivantes, puis exportez la liste dans un fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="63edc-179">Run the following series of commands to get a list of all inactive accounts on StaffHub teams and export the list to a CSV file.</span></span> <span data-ttu-id="63edc-180">Chaque commande doit être exécutée séparément.</span><span class="sxs-lookup"><span data-stu-id="63edc-180">Each command should be run separately.</span></span>

```PowerShell
$InvitedUsersObject = @()

$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }

foreach($team in $StaffHubTeams[0])
{ 
    Write-host $team.name
    $StaffHubUsers = Get-StaffHubMember -TeamId $team.Id | where {$_.State -eq "Invited"}
    foreach($StaffHubUser in $StaffHubUsers) {
        $InvitedUsersObject  += New-Object PsObject -Property @{
          "TeamID"="$($team.Id)"
          "TeamName"="$($team.name)"
          "MemberID"="$($StaffHubUser.Id)"
            }
    }
}

$InvitedUsersObject | SELECT * | export-csv InvitedUsers.csv -NoTypeInformation  
```

#### <a name="link-the-account"></a><span data-ttu-id="63edc-181">Lier le compte</span><span class="sxs-lookup"><span data-stu-id="63edc-181">Link the account</span></span>

<span data-ttu-id="63edc-182">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="63edc-182">Do one of the following:</span></span>

- <span data-ttu-id="63edc-183">Conversion et liaison du compte.</span><span class="sxs-lookup"><span data-stu-id="63edc-183">Convert and link the account.</span></span>

  <span data-ttu-id="63edc-184">Les propriétaires d’équipes et responsables de StaffHub peuvent convertir un compte inactif et le lier à un compte Azure AD dans StaffHub en définissant l’adresse de courrier de l’utilisateur sur un UPN valide dans la page Paramètres de l’équipe StaffHub.</span><span class="sxs-lookup"><span data-stu-id="63edc-184">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="63edc-185">Supprimez le compte non lié, puis rajoutez-le à l’aide du nom d’utilisateur principal.</span><span class="sxs-lookup"><span data-stu-id="63edc-185">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="63edc-186">Exécutez l’applet de passe [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) pour supprimer le compte non approvisionné de l’équipe StaffHub.</span><span class="sxs-lookup"><span data-stu-id="63edc-186">Run the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="63edc-187">Exécutez l’applet de passe [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) pour ajouter le compte à l’équipe StaffHub à l’aide du nom d’utilisateur principal.</span><span class="sxs-lookup"><span data-stu-id="63edc-187">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="63edc-188">Supprimez le compte inactif.</span><span class="sxs-lookup"><span data-stu-id="63edc-188">Remove the inactive account.</span></span> <span data-ttu-id="63edc-189">Utilisez cette option si le compte d’utilisateur n’est plus nécessaire.</span><span class="sxs-lookup"><span data-stu-id="63edc-189">Use this option if the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="63edc-190">Affecter la stratégie de configuration de l’application FirstlineWorker aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="63edc-190">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="63edc-191">Teams inclut une stratégie intégrée de configuration de l’application FirstlineWorker que vous pouvez utiliser pour personnaliser teams afin de mettre en évidence les applications les plus importantes pour les travailleurs terrain au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="63edc-191">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="63edc-192">Lorsque vous attribuez ce paramètre de stratégie aux utilisateurs, les applications de la stratégie sont épinglées à la barre de l’application dans teams pour un accès rapide et facile.</span><span class="sxs-lookup"><span data-stu-id="63edc-192">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="63edc-193">Les autres applications ajoutées aux équipes sont accessibles dans la barre de l’application en cliquant sur **... D’autres applications** sont installées sur les clients de bureau et Web teams en effectuant un balayage vers le haut dans le client Microsoft teams mobile.</span><span class="sxs-lookup"><span data-stu-id="63edc-193">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="63edc-194">Par défaut, la stratégie de configuration de l’application FirstlineWorker comprend les applications activité, équipes, discussions et appels.</span><span class="sxs-lookup"><span data-stu-id="63edc-194">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="63edc-195">Pour plus d’informations sur l’affectation de la stratégie de configuration de l’application FirstlineWorker aux utilisateurs, voir [utilisation de la stratégie de configuration des applications FirstlineWorker pour épingler des équipes à des équipes](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span><span class="sxs-lookup"><span data-stu-id="63edc-195">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="63edc-196">Dès lors que vous attribuez une stratégie, plusieurs heures peuvent être prises en compte.</span><span class="sxs-lookup"><span data-stu-id="63edc-196">After you assign a policy, it can take a few hours to take effect.</span></span>

<span data-ttu-id="63edc-197">Nous vous recommandons de terminer cette étape au moins une semaine avant de déplacer vos équipes et utilisateurs StaffHub vers Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-197">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="63edc-198">Lorsque les utilisateurs sont sur Teams, assurez-vous qu’ils peuvent afficher l’application Shifts et y accéder.</span><span class="sxs-lookup"><span data-stu-id="63edc-198">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="63edc-199">Vous pouvez également créer des stratégies de configuration d’applications personnalisées et modifier les paramètres de la stratégie de configuration de l’application globale.</span><span class="sxs-lookup"><span data-stu-id="63edc-199">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="63edc-200">Pour en savoir plus, consultez [gérer les stratégies de configuration des applications dans Microsoft teams](../../teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="63edc-200">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="63edc-201">Utilisateurs intégrés à teams</span><span class="sxs-lookup"><span data-stu-id="63edc-201">Onboard users to Teams</span></span>

<span data-ttu-id="63edc-202">Dans le cadre de votre stratégie d’intégration, vous pouvez fournir des formations et des conseils pour permettre aux utilisateurs de se familiariser avec Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-202">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="63edc-203">Partagez les ressources suivantes avec des utilisateurs afin qu’ils sachent où sont les clients Teams, la formation et l’assistance technique :</span><span class="sxs-lookup"><span data-stu-id="63edc-203">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="63edc-204">Client Web Teams</span><span class="sxs-lookup"><span data-stu-id="63edc-204">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="63edc-205">Liens de téléchargement du client de bureau et mobile</span><span class="sxs-lookup"><span data-stu-id="63edc-205">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="63edc-206">Vidéos de formation Teams</span><span class="sxs-lookup"><span data-stu-id="63edc-206">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="63edc-207">Documentation d'aide Teams</span><span class="sxs-lookup"><span data-stu-id="63edc-207">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="63edc-208">Pour obtenir des instructions sur le déploiement d’équipes et le développement d’équipes, reportez-vous [à la rubrique déploiement d’équipes](../../How-to-roll-out-teams.md) et [adoption d’équipes](../../adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="63edc-208">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="63edc-209">Conduire une pilote</span><span class="sxs-lookup"><span data-stu-id="63edc-209">Conduct a pilot</span></span>

<span data-ttu-id="63edc-210">Nous vous recommandons de commencer par déplacer deux ou trois équipes de StaffHub pour un groupe de sélection d’adoptateurs précoces.</span><span class="sxs-lookup"><span data-stu-id="63edc-210">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="63edc-211">L’exécution d’un pilote vous permet d’affiner votre plan de transition et de vous assurer que vous êtes prêt à déplacer toutes les équipes StaffHub de votre organisation vers Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-211">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="63edc-212">Il permet également d’identifier les champions qui peuvent favoriser l’adoption de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="63edc-212">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="63edc-213">S’il s’agit d’une petite entreprise qui n’a pas besoin d’une approche progressive, il est possible que vous n’ayez pas besoin de suivre les étapes décrites dans cette section pour basculer entre StaffHub et Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-213">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="63edc-214">Identifiez les équipes pilotes</span><span class="sxs-lookup"><span data-stu-id="63edc-214">Identify pilot teams</span></span>

<span data-ttu-id="63edc-215">Contactez-vous pour identifier deux ou trois équipes pilote.</span><span class="sxs-lookup"><span data-stu-id="63edc-215">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="63edc-216">Tous les membres de l’équipe doivent s’engager à utiliser les Shifts dans teams pour gérer leur planning et communiquer et collaborer entre eux.</span><span class="sxs-lookup"><span data-stu-id="63edc-216">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="63edc-217">Identifier les champions d’équipe</span><span class="sxs-lookup"><span data-stu-id="63edc-217">Identify team champions</span></span>

<span data-ttu-id="63edc-218">Identifiez des champions au sein des équipes pilote et inscrivez-les pour favoriser la sensibilisation des équipes.</span><span class="sxs-lookup"><span data-stu-id="63edc-218">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="63edc-219">Les champions d’équipe ont une passion quant à leur fonction, en partageant leurs propres formations afin de fournir une assistance et des recommandations aux membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="63edc-219">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="63edc-220">Les champions d’équipe peuvent être propriétaires d’équipes ou dirigeants.</span><span class="sxs-lookup"><span data-stu-id="63edc-220">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="63edc-221">Les champions doivent s’assurer que les membres de l’équipe sont configurés en consacrant du temps à tous [les](../../get-clients.md)utilisateurs, à se connecter à teams et à consulter leur planning par équipes, et à discuter avec eux.</span><span class="sxs-lookup"><span data-stu-id="63edc-221">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="63edc-222">Les utilisateurs qui connaissent déjà StaffHub seront rapidement opérationnels en équipe.</span><span class="sxs-lookup"><span data-stu-id="63edc-222">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="63edc-223">Vous pouvez également les [désigner pour une aide supplémentaire](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) .</span><span class="sxs-lookup"><span data-stu-id="63edc-223">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="63edc-224">Déplacer une équipe StaffHub</span><span class="sxs-lookup"><span data-stu-id="63edc-224">Move a StaffHub team</span></span>

<span data-ttu-id="63edc-225">Pour déplacer une équipe StaffHub à la fois, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="63edc-225">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="63edc-226">Nous recommandons cette approche pour vos équipes pilote.</span><span class="sxs-lookup"><span data-stu-id="63edc-226">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="63edc-227">Par la suite, lorsque vous êtes prêt à déplacer toutes les équipes StaffHub de votre organisation, voir [déplacer vos équipes de StaffHub](#move-your-staffhub-teams) pour savoir comment déplacer plusieurs équipes à la fois.</span><span class="sxs-lookup"><span data-stu-id="63edc-227">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="63edc-228">Exécutez la commande suivante pour déplacer une équipe StaffHub.</span><span class="sxs-lookup"><span data-stu-id="63edc-228">Run the following to move a StaffHub team.</span></span>

```PowerShell
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="63edc-229">Example</span><span class="sxs-lookup"><span data-stu-id="63edc-229">Example:</span></span>

```PowerShell
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="63edc-230">Voici un exemple de réponse que vous obtenez lorsque vous envoyez une demande de migration d’une équipe StaffHub vers Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-230">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```console
 jobId                                      teamId                                      teamAlreadyInMicrosofteams  
---------------------------------------    ----------------------------------------    ---------------------------          
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="63edc-231">Pour vérifier l’état d’une demande de déplacement, exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="63edc-231">To check the status of a move request, run the following.</span></span>

```PowerShell
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="63edc-232">Example</span><span class="sxs-lookup"><span data-stu-id="63edc-232">Example:</span></span>

```PowerShell
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="63edc-233">Voici un exemple de réponse que vous obtenez lorsqu’un déplacement est en cours.</span><span class="sxs-lookup"><span data-stu-id="63edc-233">Here's an example of the response you get when a move is in progress.</span></span>

```console
jobId                                     status       teamId                                     isO365GroupCreated  Error
----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="63edc-234">Déplacer des fichiers d’une équipe StaffHub vers teams</span><span class="sxs-lookup"><span data-stu-id="63edc-234">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="63edc-235">Cette étape ne s’applique qu’aux équipes de StaffHub que vous avez déplacées vers Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-235">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="63edc-236">Vous pouvez déplacer des fichiers directement dans SharePoint Online ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63edc-236">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="63edc-237">Dans SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="63edc-237">In SharePoint Online</span></span>

<span data-ttu-id="63edc-238">Découvrez [Comment déplacer des fichiers dans SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span><span class="sxs-lookup"><span data-stu-id="63edc-238">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="63edc-239">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="63edc-239">Using PowerShell</span></span>

<span data-ttu-id="63edc-240">Téléchargez et installez [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), si ce n’est déjà fait.</span><span class="sxs-lookup"><span data-stu-id="63edc-240">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="63edc-241">Il contient les applets de service nécessaires pour déplacer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="63edc-241">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="63edc-242">Utilisez l’applet de [connexion Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) pour vous connecter au site d’équipe SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="63edc-242">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```PowerShell
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="63edc-243">Pour chaque fichier que vous souhaitez déplacer de StaffHub vers Teams, utilisez l’applet de passe [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) pour déplacer le fichier.</span><span class="sxs-lookup"><span data-stu-id="63edc-243">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```PowerShell
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="63edc-244">Pour déplacer plusieurs fichiers, effectuez une boucle sur les fichiers et exécutez la deuxième commande sur la boucle.</span><span class="sxs-lookup"><span data-stu-id="63edc-244">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="63edc-245">Vous n’avez pas besoin de répéter la première commande si la session reste active.</span><span class="sxs-lookup"><span data-stu-id="63edc-245">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="63edc-246">Aller au-delà de votre pilote et déplacer toutes les équipes de StaffHub</span><span class="sxs-lookup"><span data-stu-id="63edc-246">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="63edc-247">Sensibiliser</span><span class="sxs-lookup"><span data-stu-id="63edc-247">Raise awareness</span></span>

<span data-ttu-id="63edc-248">Lorsque vous êtes prêt à aller au-delà de vos équipes pilote et à déplacer les équipes StaffHub de votre organisation vers Teams, il est important d’abord communiquer le changement au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="63edc-248">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="63edc-249">Vous pouvez diffuser le mot sur les Shifts et la transition vers teams pour susciter une sensibilisation, susciter une excitation et conduire une adoption.</span><span class="sxs-lookup"><span data-stu-id="63edc-249">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="63edc-250">Déplacer vos équipes StaffHub</span><span class="sxs-lookup"><span data-stu-id="63edc-250">Move your StaffHub teams</span></span>

<span data-ttu-id="63edc-251">Suivez ces étapes pour déplacer en bloc StaffHub Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-251">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="63edc-252">Vous pouvez choisir de déplacer toutes les équipes StaffHub de votre organisation ou de déplacer des équipes StaffHub spécifiques.</span><span class="sxs-lookup"><span data-stu-id="63edc-252">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="63edc-253">Si vous voulez déplacer les équipes StaffHub une par une, voir [déplacer une équipe StaffHub](#move-a-staffhub-team).</span><span class="sxs-lookup"><span data-stu-id="63edc-253">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="63edc-254">Déplacer toutes les équipes de StaffHub</span><span class="sxs-lookup"><span data-stu-id="63edc-254">Move all StaffHub teams</span></span>

<span data-ttu-id="63edc-255">Exécutez la commande suivante pour obtenir la liste de toutes les équipes de StaffHub au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="63edc-255">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```PowerShell
$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
```

<span data-ttu-id="63edc-256">Ensuite, exécutez la commande suivante pour déplacer toutes les équipes.</span><span class="sxs-lookup"><span data-stu-id="63edc-256">Then, run the following to move all teams.</span></span>

```PowerShell
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="63edc-257">Voici un exemple de réponse.</span><span class="sxs-lookup"><span data-stu-id="63edc-257">Here's an example of the response.</span></span>

<span data-ttu-id="63edc-258">Dans le cas d’une équipe qui a déjà été déplacée vers teams ou qui existe déjà dans Teams, le jobId sera « nul », car il n’est pas nécessaire de soumettre une demande de transfert à cette équipe.</span><span class="sxs-lookup"><span data-stu-id="63edc-258">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```console
jobId                                      teamId                                      teamAlreadyInMicrosofteams  
----------------------------------------   -----------------------------------------   --------------------------         
null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="63edc-259">Déplacer des équipes StaffHub spécifiques</span><span class="sxs-lookup"><span data-stu-id="63edc-259">Move specific StaffHub teams</span></span>

<span data-ttu-id="63edc-260">Exécutez la commande suivante pour obtenir la liste de tous les ID d’équipe StaffHub au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="63edc-260">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="63edc-261">Dans les résultats renvoyés par l' `Get-StaffHubteamsForTenant` applet de requête que vous avez exécutée précédemment, sélectionnez les ID d’équipe que vous voulez déplacer, puis ajoutez-les à un fichier de valeurs séparées par des virgules (CSV).</span><span class="sxs-lookup"><span data-stu-id="63edc-261">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="63edc-262">Voici un exemple de mise en forme du fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="63edc-262">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="63edc-263">ID</span><span class="sxs-lookup"><span data-stu-id="63edc-263">Id</span></span>  |
|---------|
|<span data-ttu-id="63edc-264">TEAM_4bbc03af-C764-497F-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="63edc-264">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="63edc-265">TEAM_81b1f191-3e19-45CE-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="63edc-265">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="63edc-266">TEAM_b42d0fa2-0fc9-408B-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="63edc-266">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="63edc-267">TEAM_b42d0fa2-0fc9-408B-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="63edc-267">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="63edc-268">Après avoir créé le fichier CSV, exécutez ce qui suit pour déplacer les équipes que vous avez spécifiées dans le fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="63edc-268">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```PowerShell
$StaffHubTeams = Import-Csv .\teams.csv

foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="63edc-269">Vérifier que vos équipes StaffHub ont été déplacées vers teams</span><span class="sxs-lookup"><span data-stu-id="63edc-269">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="63edc-270">Exécutez la commande suivante pour obtenir la liste de toutes les équipes dans les équipes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="63edc-270">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="63edc-271">Déplacer des fichiers de vos équipes StaffHub vers teams</span><span class="sxs-lookup"><span data-stu-id="63edc-271">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="63edc-272">Si les équipes de StaffHub que vous avez déplacées contiennent des fichiers que vous voulez déplacer vers Teams, voir [déplacer des fichiers d’une équipe StaffHub vers](#move-files-from-a-staffhub-team-to-teams)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-272">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="63edc-273">Surveiller l’utilisation des équipes</span><span class="sxs-lookup"><span data-stu-id="63edc-273">Monitor Teams usage</span></span>

<span data-ttu-id="63edc-274">Les rapports d’utilisation peuvent vous aider à mieux comprendre les modèles d’utilisation et vous fournir des informations sur la priorité des efforts de formation et de communication au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="63edc-274">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="63edc-275">Vous pouvez exécuter des rapports qui décrivent l’utilisation globale des équipes, les types d’activités exécutées par les utilisateurs dans Teams, le mode de connexion des utilisateurs aux équipes, etc.</span><span class="sxs-lookup"><span data-stu-id="63edc-275">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="63edc-276">Pour plus d’informations, reportez-vous à la rubrique Création de rapports d’activité dans [le centre d’administration Microsoft teams](../../teams-analytics-and-reports/teams-reporting-reference.md) et [dans le centre d’administration Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="63edc-276">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="63edc-277">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="63edc-277">Troubleshooting</span></span>

<span data-ttu-id="63edc-278">**Obtenir plus d’informations sur les erreurs d’échec**</span><span class="sxs-lookup"><span data-stu-id="63edc-278">**How to get more information about failure errors**</span></span>

<span data-ttu-id="63edc-279">Exécutez la commande suivante pour obtenir plus d’informations sur les erreurs de « défaillance » qui se produisent lorsque vous tentez de déplacer une équipe :</span><span class="sxs-lookup"><span data-stu-id="63edc-279">Run the following to get more information about "Failure" errors that occur when you try to move a team:</span></span>

```PowerShell
Move-StaffHubTeam -TeamId <TeamId>

$res = Get-TeamMigrationJobStatus -JobId <JobId>

$res.Status
```

<span data-ttu-id="63edc-280">Vous verrez l’un des statuts suivants renvoyés : réussite, échec, inprogression, en file d’attente.</span><span class="sxs-lookup"><span data-stu-id="63edc-280">You'll see one of the following statuses returned: Success, Failure, InProgress, Queued.</span></span>

<span data-ttu-id="63edc-281">Si « Failure » est retourné, exécutez la commande suivante pour obtenir plus d’informations sur l’erreur :</span><span class="sxs-lookup"><span data-stu-id="63edc-281">If "Failure" is returned, run the following to get more information about the error:</span></span>

```PowerShell
$res.Result.Error.Innererror
```

<span data-ttu-id="63edc-282">**Lorsque vous tentez de déplacer une équipe StaffHub, l’état indique « échec » et vous recevez un message d’erreur « Impossible de récupérer les catégories SKU applicables pour l’utilisateur ».**</span><span class="sxs-lookup"><span data-stu-id="63edc-282">**When you try to move a StaffHub team, the status shows as "Failure" and you receive a "Failed to retrieve applicable SKU categories for the user" error message**</span></span>

<span data-ttu-id="63edc-283">Cela peut se produire si le ou les membres d’une équipe n’ont pas de licence Teams.</span><span class="sxs-lookup"><span data-stu-id="63edc-283">This can occur if one or more team members don't have a Teams license.</span></span> <span data-ttu-id="63edc-284">Accédez à portal.office.com, repérez le groupe, puis vérifiez que les membres du groupe reçoivent une licence d’équipe.</span><span class="sxs-lookup"><span data-stu-id="63edc-284">Go to portal.office.com, find the group, and then confirm that group members are assigned a Teams license.</span></span>

<span data-ttu-id="63edc-285">**Lorsque vous tentez de déplacer une équipe StaffHub, l’état indique « échec » et le message d’erreur « propriétaire de l’équipe introuvable » s’affiche**</span><span class="sxs-lookup"><span data-stu-id="63edc-285">**When you try to move a StaffHub team, the status shows as "Failure" and you receive a "Team owner not found" error message**</span></span>

<span data-ttu-id="63edc-286">Cela peut se produire si le groupe associé à l’équipe StaffHub ne possède pas de propriétaire d’équipe.</span><span class="sxs-lookup"><span data-stu-id="63edc-286">This can occur if the group that's associated with the StaffHub team doesn't have a team owner.</span></span> <span data-ttu-id="63edc-287">Accédez à portal.office.com, recherchez le groupe, puis ajoutez un ou plusieurs propriétaires au groupe.</span><span class="sxs-lookup"><span data-stu-id="63edc-287">Go to portal.office.com, find the group, and then add one or more owners to the group.</span></span>

<span data-ttu-id="63edc-288">**Lorsque vous tentez de déplacer les fichiers de StaffHub vers Teams, vous recevez un message d’erreur « autorisation refusée ».**</span><span class="sxs-lookup"><span data-stu-id="63edc-288">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="63edc-289">Cela risque de se produire si vous essayez de déplacer des fichiers dans un groupe Office 365 privé dont vous n’êtes pas membre.</span><span class="sxs-lookup"><span data-stu-id="63edc-289">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="63edc-290">Si tel est le cas, utilisez l’applet de demande [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) pour vous ajouter à l’équipe StaffHub, puis déplacer les fichiers.</span><span class="sxs-lookup"><span data-stu-id="63edc-290">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="63edc-291">Après avoir déplacé les fichiers, utilisez l’applet de passe [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) pour vous supprimer de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="63edc-291">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="63edc-292">**Lorsque vous tentez de déplacer les fichiers de StaffHub vers Teams, un message d’erreur indiquant que le dossier général n’existe pas s’affiche.**</span><span class="sxs-lookup"><span data-stu-id="63edc-292">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="63edc-293">Exécutez la commande suivante pour ajouter le dossier général à SharePoint, puis réessayez :</span><span class="sxs-lookup"><span data-stu-id="63edc-293">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```PowerShell
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="63edc-294">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="63edc-294">Related topics</span></span>
- [<span data-ttu-id="63edc-295">Comment mettre en place Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63edc-295">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="63edc-296">Fin de parcours pour Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="63edc-296">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="63edc-297">Gérer l’application Shifts pour votre organisation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63edc-297">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="63edc-298">Référence PowerShell StaffHub</span><span class="sxs-lookup"><span data-stu-id="63edc-298">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
