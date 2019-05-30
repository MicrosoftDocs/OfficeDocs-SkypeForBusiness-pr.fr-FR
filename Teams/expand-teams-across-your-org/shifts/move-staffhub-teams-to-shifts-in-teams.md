---
title: Déplacer vos équipes de Microsoft StaffHub vers Shifts dans Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 3/29/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment déplacer vos équipes Microsoft StaffHub et planifier des données en équipes dans Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6354c2edd4d8504aeb2c84715b982f6bf793d33
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548293"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="2ecfa-103">Déplacer vos équipes Microsoft StaffHub vers des équipes dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="2ecfa-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ecfa-104">À compter du 1er octobre 2019, Microsoft StaffHub sera supprimé.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="2ecfa-105">Nous développons des fonctionnalités StaffHub dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="2ecfa-106">Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="2ecfa-107">StaffHub ne fonctionnera pas pour tous les utilisateurs du 1er octobre 2019.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="2ecfa-108">Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="2ecfa-109">Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="2ecfa-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="2ecfa-110">La fonctionnalité décrite dans cet article n’a pas encore été publiée.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="2ecfa-111">Il a été annoncé et sera bientôt disponible à partir du 2019 du 1er juin.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-111">It's been announced, and is coming soon, in early June 2019.</span></span> <span data-ttu-id="2ecfa-112">Si vous êtes un administrateur, vous pouvez en savoir plus sur le moment où il sera disponible dans le centre de messages (dans le [Centre d’administration 365 Microsoft](https://portal.office.com/adminportal/home)).</span><span class="sxs-lookup"><span data-stu-id="2ecfa-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="2ecfa-113">L’application Shifts dans teams fournit une méthode simple pour gérer les plannings et le flux constant de permutations et d’annulations de Shift qui se produisent quotidiennement.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="2ecfa-114">Les membres d’une équipe peuvent accéder à leur planning et leur transférer directement dans l’application et sur leurs appareils pour définir leurs préférences, gérer leur planning et demander un congé.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="2ecfa-115">Cet article vous explique comment déplacer les équipes StaffHub de votre organisation et planifier vos données en vue de leur déplacement dans Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="2ecfa-116">Que vous soyez une petite entreprise disposant d’une ou de deux équipes StaffHub ou d’une grande entreprise ayant des centaines d’équipes, vous trouverez ci-dessous les conseils d’administration dont vous avez besoin pour faciliter la transition vers les équipes.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="2ecfa-117">Pour pouvoir effectuer les étapes décrites dans cet article, vous devez être un administrateur général.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="2ecfa-118">Si vous ne l’avez pas déjà fait, consultez le [Forum aux questions de retraite StaffHub](microsoft-staffhub-to-be-retired.md) pour obtenir des réponses aux questions que vous pourriez rencontrer.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="2ecfa-119">Ce que vous devez savoir sur le déplacement dans teams</span><span class="sxs-lookup"><span data-stu-id="2ecfa-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="2ecfa-120">Quand déplacer vers teams</span><span class="sxs-lookup"><span data-stu-id="2ecfa-120">When to move to Teams</span></span>

<span data-ttu-id="2ecfa-121">À compter du 1er octobre 2019, StaffHub sera supprimé.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="2ecfa-122">Nous vous encourageons à commencer à utiliser teams dès aujourd’hui et à migrer les équipes et les utilisateurs de votre organisation à partir de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="2ecfa-123">Avec la gestion des plannings étant la fonctionnalité la plus couramment utilisée dans StaffHub, nous vous recommandons d’utiliser l’application Shifts dans les équipes qui progressent.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="2ecfa-124">Ce qui est déplacé vers teams</span><span class="sxs-lookup"><span data-stu-id="2ecfa-124">What is moved to Teams</span></span>

<span data-ttu-id="2ecfa-125">Les détails de l’utilisateur, les informations de calendrier et les discussions et les données de fichier sont migrés vers Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="2ecfa-126">Il s’agit de l’appartenance à une équipe, des plannings d’équipe, des conversations et des fichiers aux derniers 90 jours.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="2ecfa-127">Chaque équipe StaffHub doit avoir un groupe Office 365 correspondant.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="2ecfa-128">Si une équipe StaffHub n’a pas de groupe Office 365 associé, vous pouvez l’utiliser pour la prise en charge de la transition.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="2ecfa-129">En raison de la différence entre les noms d’équipe et de groupe entre teams et StaffHub, il est possible que vous voyiez un nom d’équipe différent dans Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="2ecfa-130">Lorsque vous transformez des équipes de StaffHub en équipes, les utilisateurs n’ont plus accès à leur planning dans StaffHub et sont redirigés vers des équipes dans Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="2ecfa-131">Nous vous recommandons de communiquer ce changement au sein de votre organisation afin de limiter les perturbations et d’encourager les utilisateurs à adopter et à explorer les équipes.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="2ecfa-132">Si vous disposez d’Azure AD Premium, vous pouvez [exécuter un rapport](run-report-to-show-staffhub-usage.md) pour obtenir la liste des utilisateurs de StaffHub de votre organisation qui doivent savoir ce changement.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-132">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="2ecfa-133">Il n’existe aucune option de restauration après le déplacement d’une équipe StaffHub vers Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-133">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="2ecfa-134">Utilisation de l’interface utilisateur lorsque vous déplacez une équipe</span><span class="sxs-lookup"><span data-stu-id="2ecfa-134">User experience when you move a team</span></span>

<span data-ttu-id="2ecfa-135">Il y a un minimum d’interruption de service (moins d’une seconde, le cas échéant) pour les utilisateurs lorsque leur équipe passe de StaffHub à équipes.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-135">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="2ecfa-136">Les utilisateurs peuvent continuer à utiliser StaffHub jusqu’à ce que le passage aux équipes soit terminé.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-136">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="2ecfa-137">Lorsque le déplacement est terminé, les membres de l’équipe voient s’afficher un message lui informant qu’ils doivent commencer par utiliser les Shifts dans teams pour accéder à leur planning d’équipe.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-137">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="2ecfa-138">Voici un exemple du message que les utilisateurs voient dans StaffHub une fois que l’équipe StaffHub a été déplacée vers Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-138">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="2ecfa-139">![Exemple du message que les utilisateurs voient.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Exemple du message que les utilisateurs voient dans StaffHub après le déplacement de l’équipe StaffHub vers") teams</span><span class="sxs-lookup"><span data-stu-id="2ecfa-139">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="2ecfa-140">Prévenir</span><span class="sxs-lookup"><span data-stu-id="2ecfa-140">Prepare</span></span>

<span data-ttu-id="2ecfa-141">Voici comment préparer le déplacement vers Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-141">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="2ecfa-142">Assigner des licences Teams</span><span class="sxs-lookup"><span data-stu-id="2ecfa-142">Assign Teams licenses</span></span>

<span data-ttu-id="2ecfa-143">Chaque utilisateur doit avoir une licence Microsoft 365 ou Office 365 active d' [un plan éligible](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) et être disposant d’une licence d’équipe.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-143">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="2ecfa-144">L’attribution d’une licence d’équipe aux utilisateurs leur permet d’accéder à Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-144">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="2ecfa-145">Pour gérer les licences d’équipe, vous devez utiliser le centre d’administration 365 Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-145">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="2ecfa-146">Pour en savoir plus, voir [gérer l’accès des utilisateurs aux équipes](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2ecfa-146">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2ecfa-147">Si votre organisation utilise Skype entreprise et que vous n’êtes pas prêt à déplacer tous vos utilisateurs vers Teams, vous pouvez activer les équipes pour vos travailleurs terrain qui peuvent alors exécuter des équipes en même temps que Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-147">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="2ecfa-148">Dans ce mode de coexistence, \*\* intitulé îlots, chaque application cliente fonctionne en tant que solution distincte.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-148">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="2ecfa-149">Pour en savoir plus, reportez-vous à la rubrique [Présentation des équipes et coexistence et interopérabilité de Skype entreprise](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="2ecfa-149">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="2ecfa-150">Mise en service des comptes pour les utilisateurs de StaffHub qui n’ont pas d’identité dans Azure AD</span><span class="sxs-lookup"><span data-stu-id="2ecfa-150">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="2ecfa-151">Chaque responsable et membre d’équipe doit avoir une identité dans Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="2ecfa-151">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="2ecfa-152">Si un utilisateur n’a pas encore d’identité dans Azure AD, approvisionnez-en un.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-152">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="2ecfa-153">Voici comment procéder.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-153">Here's how.</span></span>

- <span data-ttu-id="2ecfa-154">Les propriétaires d’équipes et responsables de StaffHub peuvent convertir un compte fictif ou inactif et le lier à un compte approvisionné dans StaffHub en définissant l’adresse de courrier de l’utilisateur sur un UPN valide dans la page Paramètres de l’équipe StaffHub.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-154">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="2ecfa-155">Les administrateurs peuvent exécuter les applets de [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) et [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) pour supprimer un compte non approvisionné d’une équipe StaffHub et ajouter de nouveau le compte à l’aide du nom UPN.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-155">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="2ecfa-156">Installer le module PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="2ecfa-156">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="2ecfa-157">Si ce n’est déjà fait, [Installez le module StaffHub PowerShell](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="2ecfa-157">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="2ecfa-158">Lorsque vous déplacez une équipe StaffHub, la demande de déplacement vérifie la configuration requise.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-158">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="2ecfa-159">Voici quelques raisons pour lesquelles il est possible qu’une demande de déplacement réussisse:</span><span class="sxs-lookup"><span data-stu-id="2ecfa-159">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="2ecfa-160">L’utilisateur connecté n’est pas un administrateur global</span><span class="sxs-lookup"><span data-stu-id="2ecfa-160">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="2ecfa-161">Teams est désactivé pour tous les utilisateurs du client.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-161">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="2ecfa-162">La création de groupes Office 365 est désactivée dans le client</span><span class="sxs-lookup"><span data-stu-id="2ecfa-162">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="2ecfa-163">Le teamId StaffHub n’est pas valide ou ne possède pas de membres</span><span class="sxs-lookup"><span data-stu-id="2ecfa-163">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="2ecfa-164">L’équipe StaffHub inclut les membres qui ne sont pas liés à un compte Azure AD</span><span class="sxs-lookup"><span data-stu-id="2ecfa-164">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="2ecfa-165">Exécution d’un pilote</span><span class="sxs-lookup"><span data-stu-id="2ecfa-165">Run a pilot</span></span>

<span data-ttu-id="2ecfa-166">Nous vous recommandons de commencer par déplacer deux ou trois équipes de StaffHub pour un groupe de sélection d’adoptateurs précoces.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-166">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="2ecfa-167">L’exécution d’un pilote vous permet d’affiner votre plan de transition et de vous assurer que vous êtes prêt à déplacer toutes les équipes StaffHub de votre organisation vers Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-167">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="2ecfa-168">Il permet également d’identifier les champions qui peuvent favoriser l’adoption de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-168">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="2ecfa-169">S’il s’agit d’une petite entreprise qui n’a pas besoin d’une approche progressive, il est possible que vous n’ayez pas besoin de suivre les étapes décrites dans cette section pour basculer entre StaffHub et Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-169">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="2ecfa-170">Identifiez les équipes pilotes</span><span class="sxs-lookup"><span data-stu-id="2ecfa-170">Identify pilot teams</span></span>

<span data-ttu-id="2ecfa-171">Contactez-vous pour identifier deux ou trois équipes pilote.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-171">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="2ecfa-172">Tous les membres de l’équipe doivent s’engager à utiliser les Shifts dans teams pour gérer leur planning et communiquer et collaborer entre eux.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-172">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="2ecfa-173">Identifier les champions d’équipe</span><span class="sxs-lookup"><span data-stu-id="2ecfa-173">Identify team champions</span></span>

<span data-ttu-id="2ecfa-174">Identifiez des champions au sein des équipes pilote et inscrivez-les pour favoriser la sensibilisation des équipes.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-174">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="2ecfa-175">Les champions d’équipe ont une passion quant à leur fonction, en partageant leurs propres formations afin de fournir une assistance et des recommandations aux membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-175">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="2ecfa-176">Les champions d’équipe peuvent être propriétaires d’équipes ou dirigeants.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-176">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="2ecfa-177">Les champions doivent s’assurer que les membres de l’équipe sont configurés en consacrant du temps à tous [les](../../get-clients.md)utilisateurs, à se connecter à teams et à consulter leur planning par équipes, et à discuter avec eux.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-177">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="2ecfa-178">Les utilisateurs qui connaissent déjà StaffHub seront rapidement opérationnels en équipe.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-178">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="2ecfa-179">Vous pouvez également les désigner pour [](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) une aide supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-179">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="2ecfa-180">Déplacer une équipe StaffHub (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="2ecfa-180">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="2ecfa-181">Pour déplacer une équipe StaffHub à la fois, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-181">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="2ecfa-182">Nous recommandons cette approche pour vos équipes pilote.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-182">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="2ecfa-183">Par la suite, lorsque vous êtes prêt à déplacer toutes les équipes StaffHub de votre organisation, voir [déplacer vos équipes de StaffHub](#move-your-staffhub-teams-coming-soon) pour savoir comment déplacer plusieurs équipes à la fois.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-183">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="2ecfa-184">Exécutez la commande suivante pour déplacer une équipe StaffHub.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-184">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="2ecfa-185">Voici un exemple de réponse que vous obtenez lorsque vous envoyez une demande de migration d’une équipe StaffHub vers Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-185">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="2ecfa-186">Pour vérifier l’état d’une demande de déplacement, exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-186">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="2ecfa-187">Voici un exemple de réponse que vous obtenez lorsqu’un déplacement est en cours.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-187">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="2ecfa-188">Effectuer la transition de StaffHub à teams</span><span class="sxs-lookup"><span data-stu-id="2ecfa-188">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="2ecfa-189">Sensibiliser</span><span class="sxs-lookup"><span data-stu-id="2ecfa-189">Raise awareness</span></span>

<span data-ttu-id="2ecfa-190">Lorsque vous êtes prêt à aller au-delà de vos équipes pilote et à déplacer les équipes StaffHub de votre organisation vers Teams, il est important d’abord communiquer le changement au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-190">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="2ecfa-191">Vous pouvez diffuser le mot sur les Shifts et la transition vers teams pour susciter une sensibilisation, susciter une excitation et conduire une adoption.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-191">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="2ecfa-192">Déplacez vos équipes StaffHub (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="2ecfa-192">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="2ecfa-193">Suivez ces étapes pour déplacer en bloc StaffHub Teams.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-193">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="2ecfa-194">Vous pouvez choisir de déplacer toutes les équipes StaffHub de votre organisation ou de déplacer des équipes StaffHub spécifiques.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-194">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="2ecfa-195">Si vous voulez déplacer les équipes StaffHub une par une, voir [déplacer une équipe StaffHub](#move-a-staffhub-team-coming-soon).</span><span class="sxs-lookup"><span data-stu-id="2ecfa-195">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="2ecfa-196">Déplacer toutes les équipes de StaffHub (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="2ecfa-196">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="2ecfa-197">Exécutez la commande suivante pour obtenir la liste de toutes les équipes de StaffHub au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-197">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="2ecfa-198">Ensuite, exécutez la commande suivante pour déplacer toutes les équipes.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-198">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="2ecfa-199">Voici un exemple de réponse.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-199">Here's an example of the response.</span></span>

<span data-ttu-id="2ecfa-200">Dans le cas d’une équipe qui a déjà été déplacée vers teams ou qui existe déjà dans Teams, le jobId sera «nul», car il n’est pas nécessaire de soumettre une demande de transfert à cette équipe.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-200">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="2ecfa-201">Déplacer des équipes StaffHub spécifiques (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="2ecfa-201">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="2ecfa-202">Exécutez la commande suivante pour obtenir la liste de tous les ID d’équipe StaffHub au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-202">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="2ecfa-203">Dans les résultats renvoyés par `Get-StaffHubteamsForTenant` l’applet de requête que vous avez exécutée précédemment, sélectionnez les ID d’équipe que vous voulez déplacer, puis ajoutez-les à un fichier de valeurs séparées par des virgules (CSV).</span><span class="sxs-lookup"><span data-stu-id="2ecfa-203">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="2ecfa-204">Voici un exemple de mise en forme du fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-204">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="2ecfa-205">ID</span><span class="sxs-lookup"><span data-stu-id="2ecfa-205">Id</span></span>  |
|---------|
|<span data-ttu-id="2ecfa-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="2ecfa-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="2ecfa-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="2ecfa-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="2ecfa-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="2ecfa-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="2ecfa-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="2ecfa-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="2ecfa-210">Après avoir créé le fichier CSV, exécutez ce qui suit pour déplacer les équipes que vous avez spécifiées dans le fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-210">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="2ecfa-211">Confirmez que vos équipes StaffHub ont été déplacées vers Teams (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="2ecfa-211">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="2ecfa-212">Exécutez la commande suivante pour obtenir la liste de toutes les équipes dans les équipes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-212">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="2ecfa-213">Surveiller l’utilisation des équipes</span><span class="sxs-lookup"><span data-stu-id="2ecfa-213">Monitor Teams usage</span></span>

<span data-ttu-id="2ecfa-214">Les rapports d’utilisation peuvent vous aider à mieux comprendre les modèles d’utilisation et vous fournir des informations sur la priorité des efforts de formation et de communication au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-214">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="2ecfa-215">Comme Shifts est une application dans Teams, vous pouvez voir l’utilisation via des rapports d’équipes.</span><span class="sxs-lookup"><span data-stu-id="2ecfa-215">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="2ecfa-216">Pour plus d’informations, reportez-vous à la rubrique Création de rapports d’activité dans [le centre d’administration Microsoft teams](../../teams-analytics-and-reports/teams-reporting-reference.md) et [dans le centre d’administration Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="2ecfa-216">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2ecfa-217">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ecfa-217">Related topics</span></span>
- [<span data-ttu-id="2ecfa-218">Fin de parcours pour Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="2ecfa-218">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="2ecfa-219">Gérer l’application Shifts pour votre organisation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ecfa-219">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="2ecfa-220">Référence PowerShell StaffHub</span><span class="sxs-lookup"><span data-stu-id="2ecfa-220">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
