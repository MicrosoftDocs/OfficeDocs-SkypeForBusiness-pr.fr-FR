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
description: Découvrez comment déplacer vos équipes Microsoft StaffHub et programmer des données pour les déplacements dans Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ca4249c88ce5793cd04eb2e2cc1ed3035915975
ms.sourcegitcommit: 790ca37e2b12e4c8adcc526b1695017161749f51
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33526855"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="4c24c-103">Atteindre vos équipes Microsoft StaffHub équipes dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c24c-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c24c-104">Effet 2019, octobre 1, Microsoft StaffHub sera être retirée.</span><span class="sxs-lookup"><span data-stu-id="4c24c-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="4c24c-105">Nous créons StaffHub fonctionnalités dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4c24c-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="4c24c-106">Aujourd'hui, les équipes inclut l’application des équipes de gestion de la planification et des fonctionnalités supplémentaires seront intégrées au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="4c24c-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="4c24c-107">StaffHub cessera de fonctionner pour tous les utilisateurs sur le 1 octobre 2019.</span><span class="sxs-lookup"><span data-stu-id="4c24c-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="4c24c-108">Toute personne qui essaie d’ouvrir StaffHub s’affichera un message pronom pour télécharger les équipes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="4c24c-109">Pour plus d’informations, voir [Microsoft StaffHub à retirer](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="4c24c-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="4c24c-110">La fonctionnalité abordée dans cet article n’a pas encore été publiée.</span><span class="sxs-lookup"><span data-stu-id="4c24c-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="4c24c-111">Il est été annoncé et sera bientôt disponible, vers le milieu de mai 2019.</span><span class="sxs-lookup"><span data-stu-id="4c24c-111">It's been announced, and is coming soon, towards the middle of May 2019.</span></span> <span data-ttu-id="4c24c-112">Si vous êtes un administrateur, vous pouvez savoir lorsqu’il sera disponible dans le centre de messages (dans le [Centre d’administration Microsoft 365](https://portal.office.com/adminportal/home)).</span><span class="sxs-lookup"><span data-stu-id="4c24c-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="4c24c-113">L’application d’équipes dans les équipes fournit une approche simple de gérer les planifications et le flux de constant de permutations MAJ et les annulations qui se produisent au quotidien.</span><span class="sxs-lookup"><span data-stu-id="4c24c-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="4c24c-114">Membres de l’équipe peuvent accéder à son calendrier et informations MAJ directement dans l’application sur leurs appareils pour définir leurs préférences, gérer leurs calendriers et durée hors de la demande.</span><span class="sxs-lookup"><span data-stu-id="4c24c-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="4c24c-115">Cet article vous explique comment déplacer les équipes StaffHub de votre organisation et planifier les données aux équipes de travail en équipe.</span><span class="sxs-lookup"><span data-stu-id="4c24c-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="4c24c-116">Si vous êtes une petite entreprise avec un ou deux équipes StaffHub ou une grande entreprise avec des centaines de StaffHub équipes, vous trouverez les instructions d’administration que vous avez besoin pour réussir votre transition aux équipes réussie.</span><span class="sxs-lookup"><span data-stu-id="4c24c-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="4c24c-117">Vous devez être un administrateur global pour effectuer les étapes décrites dans cet article.</span><span class="sxs-lookup"><span data-stu-id="4c24c-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="4c24c-118">Si vous n’avez pas déjà fait, jetez un œil via le [retrait StaffHub FAQ](microsoft-staffhub-to-be-retired.md) pour obtenir des réponses à des questions, que vous devrez peut-être.</span><span class="sxs-lookup"><span data-stu-id="4c24c-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="4c24c-119">Ce que vous devez savoir sur le déplacement aux équipes</span><span class="sxs-lookup"><span data-stu-id="4c24c-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="4c24c-120">Quand déplacer aux équipes</span><span class="sxs-lookup"><span data-stu-id="4c24c-120">When to move to Teams</span></span>

<span data-ttu-id="4c24c-121">Effet 2019, octobre 1, StaffHub système être retirée.</span><span class="sxs-lookup"><span data-stu-id="4c24c-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="4c24c-122">Nous vous invitons à commencer à utiliser les équipes aujourd'hui et commencer à effectuer la transition de votre organisation équipes et les utilisateurs de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="4c24c-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="4c24c-123">Avec la gestion de la planification en cours de la fonctionnalité plus fréquemment utilisées dans StaffHub, nous vous recommandons de qu'utiliser l’application d’équipes dans les équipes avançant.</span><span class="sxs-lookup"><span data-stu-id="4c24c-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="4c24c-124">Quel est déplacé vers les équipes</span><span class="sxs-lookup"><span data-stu-id="4c24c-124">What is moved to Teams</span></span>

<span data-ttu-id="4c24c-125">Détails de l’utilisateur, les informations de planification et données conversation et de fichiers sont passées aux équipes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="4c24c-126">Cela inclut l’appartenance de l’équipe, les planifications de l’équipe et les conversations et les fichiers au cours des 90 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="4c24c-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="4c24c-127">Chaque équipe StaffHub a besoin d’un groupe de 365 Office correspondant.</span><span class="sxs-lookup"><span data-stu-id="4c24c-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="4c24c-128">Si une équipe StaffHub ne possède pas un groupe d’Office 365 lui est associé, une est automatiquement créée pour prendre en charge la transition.</span><span class="sxs-lookup"><span data-stu-id="4c24c-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="4c24c-129">Étant donné la différence de l’équipe et le groupe d’affectation de noms entre les équipes et StaffHub, vous pouvez voir un nom différent de l’équipe dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="4c24c-130">Transition entre les équipes de StaffHub aux équipes, les utilisateurs n’aura plus accès à leurs planifications dans StaffHub et sont redirigés vers les équipes de travail en équipe.</span><span class="sxs-lookup"><span data-stu-id="4c24c-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="4c24c-131">Nous vous recommandons de que vous communiquez ce changement dans votre organisation pour réduire l’interruption et encourager les utilisateurs à adopter et Explorer les équipes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span>

## <a name="prepare"></a><span data-ttu-id="4c24c-132">Préparer</span><span class="sxs-lookup"><span data-stu-id="4c24c-132">Prepare</span></span>

<span data-ttu-id="4c24c-133">Voici comment préparer le déplacement aux équipes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-133">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="4c24c-134">Assigner des licences Teams</span><span class="sxs-lookup"><span data-stu-id="4c24c-134">Assign Teams licenses</span></span>

<span data-ttu-id="4c24c-135">Chaque utilisateur doit disposer d’une licence Microsoft 365 ou Office 365 active à partir [d’un plan éligible](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) et doit être attribué une licence d’équipes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-135">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="4c24c-136">Attribution des licences équipes aux utilisateurs leur donne accès aux équipes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-136">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="4c24c-137">Gérer les licences d’équipes dans le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c24c-137">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4c24c-138">Pour plus d’informations, voir [gérer l’accès utilisateur aux équipes](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4c24c-138">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4c24c-139">Si votre organisation utilise Skype pour les entreprises et vous n’êtes pas prêt à passer tous vos utilisateurs à des équipes, vous pouvez activer les équipes pour vos employés Firstline qui peut ensuite exécuter les équipes à côté de Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="4c24c-139">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="4c24c-140">Dans ce mode de coexistence, appelé *(îles)*, chaque application client fonctionne comme une solution distincte.</span><span class="sxs-lookup"><span data-stu-id="4c24c-140">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="4c24c-141">Pour plus d’informations, voir [comprendre les équipes et Skype pour l’interopérabilité et coexistence d’entreprise](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="4c24c-141">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="4c24c-142">Mise en service des comptes pour les utilisateurs StaffHub qui n’ont pas d’identité dans Azure AD</span><span class="sxs-lookup"><span data-stu-id="4c24c-142">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="4c24c-143">Chaque responsable et un membre de l’équipe doivent avoir une identité dans Azure Active Directory (AD Azure).</span><span class="sxs-lookup"><span data-stu-id="4c24c-143">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="4c24c-144">Si un utilisateur n’a pas encore une identité dans Azure AD, configurez un compte pour eux.</span><span class="sxs-lookup"><span data-stu-id="4c24c-144">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="4c24c-145">Voici comment procéder.</span><span class="sxs-lookup"><span data-stu-id="4c24c-145">Here's how.</span></span>

- <span data-ttu-id="4c24c-146">Les responsables et les propriétaires de l’équipe StaffHub peuvent convertir un compte factice ou inactif et le lier à un compte dans StaffHub mis en service en modifiant l’adresse de messagerie de l’utilisateur à un nom UPN valid dans la page Paramètres de l’équipe StaffHub.</span><span class="sxs-lookup"><span data-stu-id="4c24c-146">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="4c24c-147">Administrateurs peuvent exécuter l' [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) et sauvegarder des applets de commande [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) pour supprimer un compte non mis en service d’une équipe StaffHub et ajoutez le compte à l’aide de l’UPN.</span><span class="sxs-lookup"><span data-stu-id="4c24c-147">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="4c24c-148">Installer le module PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="4c24c-148">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="4c24c-149">Si vous n’avez pas déjà fait, [installez le module StaffHub PowerShell](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="4c24c-149">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="4c24c-150">Lorsque vous déplacez une équipe StaffHub, la demande de déplacement vérifie les conditions préalables.</span><span class="sxs-lookup"><span data-stu-id="4c24c-150">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="4c24c-151">Voici les raisons de l’échec une demande de déplacement :</span><span class="sxs-lookup"><span data-stu-id="4c24c-151">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="4c24c-152">L’utilisateur connecté n’est pas un administrateur global</span><span class="sxs-lookup"><span data-stu-id="4c24c-152">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="4c24c-153">Les équipes est désactivé pour tous les utilisateurs dans le client</span><span class="sxs-lookup"><span data-stu-id="4c24c-153">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="4c24c-154">Création de groupes d’Office 365 est désactivée dans le client</span><span class="sxs-lookup"><span data-stu-id="4c24c-154">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="4c24c-155">L’ID d’équipe StaffHub n’est pas valide ou n’a aucun membre</span><span class="sxs-lookup"><span data-stu-id="4c24c-155">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="4c24c-156">L’équipe StaffHub inclut des membres qui ne sont pas liés à un compte Azure AD</span><span class="sxs-lookup"><span data-stu-id="4c24c-156">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="4c24c-157">Exécuter un projet pilote</span><span class="sxs-lookup"><span data-stu-id="4c24c-157">Run a pilot</span></span>

<span data-ttu-id="4c24c-158">Nous vous recommandons de que commencer par le déplacement de deux ou trois équipes StaffHub pour un groupe particulier de premiers.</span><span class="sxs-lookup"><span data-stu-id="4c24c-158">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="4c24c-159">Exécuter un pilote vous permet d’affiner votre plan de transition et vérifiez que vous êtes prêt à passer des équipes de StaffHub ensemble de l’entreprise à des équipes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-159">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="4c24c-160">Il identifie également les champions qui peuvent aider à encourager l’adoption au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4c24c-160">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="4c24c-161">Si vous êtes une petite entreprise qui n’ont pas besoin une approche progressive, les étapes décrites dans cette section peuvent être il que vous suffit de passer StaffHub aux équipes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-161">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="4c24c-162">Identifier les équipes pilotes</span><span class="sxs-lookup"><span data-stu-id="4c24c-162">Identify pilot teams</span></span>

<span data-ttu-id="4c24c-163">Atteindre pour identifier les deux ou trois équipes pilotes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-163">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="4c24c-164">Tous les membres de l’équipe doivent valider à l’utilisation d’équipes dans les équipes à gérer leurs calendriers et communiquer et collaborer avec eux.</span><span class="sxs-lookup"><span data-stu-id="4c24c-164">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="4c24c-165">Identifier les champions de l’équipe</span><span class="sxs-lookup"><span data-stu-id="4c24c-165">Identify team champions</span></span>

<span data-ttu-id="4c24c-166">Identifier les champions équipes de pilote et les inscrire pour vous aider à faire connaître les déplacements.</span><span class="sxs-lookup"><span data-stu-id="4c24c-166">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="4c24c-167">Champions de l’équipe sont passionnées sur dans ce cas, le partage de leurs propres connaissances pour offrir une prise en charge et des conseils aux membres d’équipe.</span><span class="sxs-lookup"><span data-stu-id="4c24c-167">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="4c24c-168">Les champions de l’équipe peuvent être propriétaires d’équipe ou les responsables.</span><span class="sxs-lookup"><span data-stu-id="4c24c-168">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="4c24c-169">Champions de l’équipe devraient vous assurer que les membres de l’équipe sont définis par heure dédiant pour tout le monde pour [obtenir les clients d’équipes](../../get-clients.md), se connecter à des équipes et extrayez planifications leurs équipes et démarrer la conversation entre eux.</span><span class="sxs-lookup"><span data-stu-id="4c24c-169">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="4c24c-170">Les utilisateurs qui sont déjà familiarisés avec StaffHub seront en cours d’exécution rapidement en équipe.</span><span class="sxs-lookup"><span data-stu-id="4c24c-170">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="4c24c-171">Vous pouvez également qu’ils pointent vers [Des équipes aide](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) pour une assistance supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="4c24c-171">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="4c24c-172">Déplacer une équipe StaffHub (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="4c24c-172">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="4c24c-173">Utilisez ces étapes pour déplacer une équipe StaffHub à la fois.</span><span class="sxs-lookup"><span data-stu-id="4c24c-173">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="4c24c-174">Nous vous recommandons cette approche pour les équipes de votre pilotes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-174">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="4c24c-175">Plus tard, lorsque vous êtes prêt à passer des équipes de StaffHub ensemble de l’entreprise, voir [déplacer vos équipes StaffHub](#move-your-staffhub-teams-coming-soon) pour connaître les étapes sur la façon de déplacer plusieurs équipes à la fois.</span><span class="sxs-lookup"><span data-stu-id="4c24c-175">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="4c24c-176">Exécutez la commande suivante pour déplacer une équipe StaffHub.</span><span class="sxs-lookup"><span data-stu-id="4c24c-176">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="4c24c-177">Voici un exemple de la réponse que vous obtenez lorsque vous envoyez une demande de déplacement d’une équipe StaffHub aux équipes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-177">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="4c24c-178">Pour vérifier l’état d’une demande de déplacement, exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="4c24c-178">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="4c24c-179">Voici un exemple de la réponse que vous obtenez lorsqu’un déplacement est en cours.</span><span class="sxs-lookup"><span data-stu-id="4c24c-179">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="4c24c-180">Effectuer la transition à partir de StaffHub aux équipes</span><span class="sxs-lookup"><span data-stu-id="4c24c-180">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="4c24c-181">Sensibilisation</span><span class="sxs-lookup"><span data-stu-id="4c24c-181">Raise awareness</span></span>

<span data-ttu-id="4c24c-182">Lorsque vous êtes prêt à aller au-delà de vos équipes pilotes et déplacer les équipes de votre organisation StaffHub aux équipes, il est important de communiquer tout d’abord la modification au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4c24c-182">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="4c24c-183">Diffusion équipes et la transition vers les équipes pour sensibiliser, générer enthousiasme et d’adoption du lecteur.</span><span class="sxs-lookup"><span data-stu-id="4c24c-183">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="4c24c-184">Déplacer vos équipes StaffHub (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="4c24c-184">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="4c24c-185">Utilisez ces étapes pour déplacer des équipes StaffHub en bloc.</span><span class="sxs-lookup"><span data-stu-id="4c24c-185">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="4c24c-186">Vous pouvez choisir déplacer les équipes StaffHub ensemble de l’entreprise ou des équipes StaffHub spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4c24c-186">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="4c24c-187">Si vous souhaitez déplacer que les équipes StaffHub un à la fois, voir [déplacer une équipe StaffHub](#move-a-staffhub-team-coming-soon).</span><span class="sxs-lookup"><span data-stu-id="4c24c-187">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="4c24c-188">Déplacer toutes les équipes StaffHub (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="4c24c-188">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="4c24c-189">Exécutez ce qui suit pour obtenir une liste de toutes les équipes StaffHub dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4c24c-189">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="4c24c-190">Ensuite, exécutez la commande suivante pour déplacer toutes les équipes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-190">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="4c24c-191">Voici un exemple de la réponse.</span><span class="sxs-lookup"><span data-stu-id="4c24c-191">Here's an example of the response.</span></span>

<span data-ttu-id="4c24c-192">Pour une équipe qui a été déjà déplacée aux équipes ou existe déjà dans les équipes, le jobId sera « null » comme une tâche n’a pas besoin d’être envoyés à déplacer que l’équipe.</span><span class="sxs-lookup"><span data-stu-id="4c24c-192">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="4c24c-193">Déplacer des équipes StaffHub spécifiques (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="4c24c-193">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="4c24c-194">Exécutez ce qui suit pour obtenir une liste de tous les StaffHub équipe ID dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4c24c-194">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="4c24c-195">Dans les résultats renvoyés par la `Get-StaffHubteamsForTenant` applet de commande que vous avez exécuté précédemment, sélectionnez les ID de l’équipe vous souhaitez déplacer, puis les ajouter à un fichier de valeurs séparées par des virgules (CSV).</span><span class="sxs-lookup"><span data-stu-id="4c24c-195">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="4c24c-196">Voici un exemple de la façon dont le fichier CSV doit être mis en forme.</span><span class="sxs-lookup"><span data-stu-id="4c24c-196">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="4c24c-197">ID</span><span class="sxs-lookup"><span data-stu-id="4c24c-197">Id</span></span>  |
|---------|
|<span data-ttu-id="4c24c-198">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="4c24c-198">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="4c24c-199">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="4c24c-199">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="4c24c-200">TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="4c24c-200">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="4c24c-201">TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="4c24c-201">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="4c24c-202">Après avoir créé le fichier CSV, exécutez la commande suivante pour déplacer les équipes que vous avez spécifié dans le fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="4c24c-202">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="4c24c-203">Vérifiez que vos équipes StaffHub ont déplacés aux équipes (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="4c24c-203">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="4c24c-204">Exécutez ce qui suit pour obtenir la liste de toutes les équipes de déplacements au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4c24c-204">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="4c24c-205">Surveiller l’utilisation d’équipes</span><span class="sxs-lookup"><span data-stu-id="4c24c-205">Monitor Teams usage</span></span>

<span data-ttu-id="4c24c-206">Rapports d’utilisation peuvent vous aider à mieux comprendre les modèles d’utilisation et vous donner des idées permettant de hiérarchiser les efforts de formation et de communication au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4c24c-206">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="4c24c-207">Équipes étant une application dans les équipes, vous pouvez afficher l’utilisation par le biais de rapports d’équipes.</span><span class="sxs-lookup"><span data-stu-id="4c24c-207">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="4c24c-208">Pour plus d’informations, voir [équipes de création de rapports dans le centre d’administration Microsoft équipes](../../teams-analytics-and-reports/teams-reporting-reference.md) et des [rapports d’activité équipes dans le centre d’administration Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="4c24c-208">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4c24c-209">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c24c-209">Related topics</span></span>
- [<span data-ttu-id="4c24c-210">Fin de parcours pour Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="4c24c-210">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="4c24c-211">Gérer l’application Shifts pour votre organisation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c24c-211">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="4c24c-212">Référence StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c24c-212">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
