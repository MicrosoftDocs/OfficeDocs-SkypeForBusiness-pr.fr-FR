---
title: Gérer l’expérience exploratoire de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Les utilisateurs de Microsoft 365 ou Office 365 qui ne disposent pas d’une licence Microsoft Teams peuvent initier une licence exploratoire.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 946847793ea90e549a555cd9d100cd1ae2809fa3
ms.sourcegitcommit: f3e9989cbcc2f9f83ff94204bdd75b1e6ad43b5e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "53408753"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="7c849-103">Gérer la licence exploratoire Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7c849-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="7c849-p101">L’expérience exploratoire Microsoft Teams permet aux utilisateurs de votre organisation qui ont Azure Active Directory (Azure AD) et qui ne disposent pas d’une licence Teams de lancer une expérience exploratoire de Teams. Les administrateurs peuvent activer ou désactiver cette fonctionnalité pour les utilisateurs de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="7c849-p101">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="7c849-106">Qu’est-ce que l’expérience exploratoire Teams ?</span><span class="sxs-lookup"><span data-stu-id="7c849-106">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="7c849-107">Les plans de service qu’un administrateur peut voir dans le cadre de l’expérience exploratoire Teams sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="7c849-107">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="7c849-108">Exchange Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="7c849-108">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="7c849-109">Flux pour Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="7c849-109">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="7c849-110">Informations obtenues par MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="7c849-110">Insights by MyAnalytics</span></span>
- <span data-ttu-id="7c849-111">Microsoft Forms (plan E1)</span><span class="sxs-lookup"><span data-stu-id="7c849-111">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="7c849-112">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="7c849-112">Microsoft Planner</span></span>
- <span data-ttu-id="7c849-113">Recherche Microsoft</span><span class="sxs-lookup"><span data-stu-id="7c849-113">Microsoft Search</span></span>
- <span data-ttu-id="7c849-114">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="7c849-114">Microsoft StaffHub</span></span>
- <span data-ttu-id="7c849-115">Microsoft Stream pour Microsoft 365 et Office 365 E1 SKU <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="7c849-115">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="7c849-116">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7c849-116">Microsoft Teams</span></span>
- <span data-ttu-id="7c849-117">Gestion des appareils mobiles pour Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="7c849-117">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="7c849-118">Applications Office Mobile pour Office 365</span><span class="sxs-lookup"><span data-stu-id="7c849-118">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="7c849-119">Office Online</span><span class="sxs-lookup"><span data-stu-id="7c849-119">Office Online</span></span>
- <span data-ttu-id="7c849-120">PowerApp pour Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="7c849-120">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="7c849-121">SharePoint Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="7c849-121">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="7c849-122">Sway</span><span class="sxs-lookup"><span data-stu-id="7c849-122">Sway</span></span>
- <span data-ttu-id="7c849-123">Tâches (plan 1)</span><span class="sxs-lookup"><span data-stu-id="7c849-123">To-Do (Plan 1)</span></span>
- <span data-ttu-id="7c849-124">Tableau blanc (plan 1)</span><span class="sxs-lookup"><span data-stu-id="7c849-124">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="7c849-125">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="7c849-125">Yammer Enterprise</span></span>

  <span data-ttu-id="7c849-126"><sup>1</sup> Les modifications apportées à l’utilisation de Microsoft Stream pour [OneDrive Entreprise et SharePoint pour les enregistrements de réunion](tmr-meeting-recording-change.md) auront une approche progressive.</span><span class="sxs-lookup"><span data-stu-id="7c849-126"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="7c849-127">Au démarrage, vous pourrez choisir cette expérience.</span><span class="sxs-lookup"><span data-stu-id="7c849-127">At launch, you'll be able to opt in to this experience.</span></span> <span data-ttu-id="7c849-128">En novembre, vous devrez abandonner cette option si vous souhaitez continuer à utiliser Stream.</span><span class="sxs-lookup"><span data-stu-id="7c849-128">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="7c849-129">Au début de 2021, nous demanderons à tous les clients d’utiliser OneDrive Entreprise et SharePoint pour les nouveaux enregistrements de réunion.</span><span class="sxs-lookup"><span data-stu-id="7c849-129">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="7c849-130">Critères d’éligibilité</span><span class="sxs-lookup"><span data-stu-id="7c849-130">Who's eligible</span></span>

<span data-ttu-id="7c849-131">Les utilisateurs éligibles à l’expérience Teams Exploratory sont les utilisateurs qui:</span><span class="sxs-lookup"><span data-stu-id="7c849-131">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="7c849-132">Disposent d’une adresse e-mail du domaine Azure AD gérée.</span><span class="sxs-lookup"><span data-stu-id="7c849-132">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="7c849-133">Appartiennent à un client disposant d’un abonnement payant.</span><span class="sxs-lookup"><span data-stu-id="7c849-133">Belong to a tenant with a paid subscription.</span></span>
- <span data-ttu-id="7c849-134">N’avez pas de licence Teams active.</span><span class="sxs-lookup"><span data-stu-id="7c849-134">Do not have an active Teams license.</span></span>
- <span data-ttu-id="7c849-135">Ne se trouve pas dans un client où une stratégie d’attribution de licence a été créée.</span><span class="sxs-lookup"><span data-stu-id="7c849-135">Are not in a tenant where a license assignment policy was created.</span></span>

<span data-ttu-id="7c849-136">Les utilisateurs doivent être autorisés à s’inscrire aux applications et aux essais (dans le Centre d’administration Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="7c849-136">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="7c849-137">Pour plus d’informations, voir [Gérer l’expérience exploratoire Teams](#manage-the-teams-exploratory-experience) plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="7c849-137">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="7c849-138">Qui n'est pas éligible ?</span><span class="sxs-lookup"><span data-stu-id="7c849-138">Who isn't eligible</span></span>

<span data-ttu-id="7c849-139">Les utilisateurs inéligibles sont les utilisateurs qui :</span><span class="sxs-lookup"><span data-stu-id="7c849-139">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="7c849-140">Disposez actuellement de Teams à partir d’une licence payante ou d’une licence d’évaluation, ou d’une licence d’évaluation antérieure</span><span class="sxs-lookup"><span data-stu-id="7c849-140">Currently have Teams from a paid license or trial license, or previously had trial license</span></span>
- <span data-ttu-id="7c849-141">se trouvent dans un client qui utilise ou a reçu au moins une offre spéciale COVID.</span><span class="sxs-lookup"><span data-stu-id="7c849-141">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="7c849-142">Votre organisation n’est pas éligible pour cette offre si vous êtes un client partenaire de syndication ou un client GCC, GCC élevé, DoD ou EDU.</span><span class="sxs-lookup"><span data-stu-id="7c849-142">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="7c849-143">Comment les utilisateurs s’inscrivent pour l’expérience exploratoire Teams ?</span><span class="sxs-lookup"><span data-stu-id="7c849-143">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="7c849-144">Les utilisateurs éligibles peuvent s’inscrire à l’expérience exploratoire Teams en se connectant à Teams à partir de l’ordinateur de bureau ou web ([teams.microsoft.com](https://teams.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="7c849-144">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="7c849-145">Pour l’instant, l’activation de exploratoire via mobile n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="7c849-145">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="7c849-146">Lorsqu’il s’inscrivent, la licence leur est attribuée automatiquement et l’administrateur client reçoit une notification par e-mail la première fois qu’une personne au sein de votre organisation démarre l’expérience Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="7c849-146">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="7c849-147">Gérer l’expérience Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="7c849-147">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="7c849-148">L’expérience Teams Exploratory est destinée aux utilisateurs finaux individuels et vous ne pouvez pas lancer cette offre pour le compte d’employés de l’utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="7c849-148">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="7c849-149">L’expérience Teams Exploratory est offerte avec une licence Exchange Online, mais elle ne peut être attribuée à l’utilisateur que par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="7c849-149">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="7c849-150">Si l’utilisateur ne dispose pas déjà d’une licence Exchange et que l’administrateur ne lui a pas encore attribué la licence Exchange Online, l’utilisateur ne peut pas planifier de réunions dans Teams et pourrait manquer d’autres fonctionnalités Teams.</span><span class="sxs-lookup"><span data-stu-id="7c849-150">If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="7c849-151">Les administrateurs peuvent désactiver la possibilité pour les utilisateurs finaux d’exécuter l’expérience exploratoire des équipes au sein de leur organisation à l’aide du commutateur des **applications et services d’essai**.</span><span class="sxs-lookup"><span data-stu-id="7c849-151">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="7c849-152">Empêcher les utilisateurs d’installer des applications et services à l’essai</span><span class="sxs-lookup"><span data-stu-id="7c849-152">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="7c849-153">Vous pouvez désactiver la possibilité pour un utilisateur d’installer des applications et des services d’essai, ce qui l’empêche d’exécuter l’expérience exploratoire Teams.</span><span class="sxs-lookup"><span data-stu-id="7c849-153">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="7c849-154">Dans le Centre d’administration Microsoft 365, accédez à **Paramètres** > **Paramètres org**, sélectionnez **Services**, puis choisissez **Services et applications propriétés de l'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="7c849-154">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![La page Services dans le Centre d’administration](media/iw-trial-services.png)

2. <span data-ttu-id="7c849-156">Désactivez la cache à cocher **Permettre aux utilisateurs d'installer les applications et services à l’essai**.</span><span class="sxs-lookup"><span data-stu-id="7c849-156">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![L’Utilisateur dispose d’une page des applications et services dans le Centre d’administration](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="7c849-158">Si votre organisation n’est pas éligible à l’expérience exploratoire Teams, l'option **Laisser les utilisateurs installer les applications et services d’essai** ne s’affiche pas.</span><span class="sxs-lookup"><span data-stu-id="7c849-158">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="7c849-159">Gérer la disponibilité pour un utilisateur disposant d’une licence incluant Teams</span><span class="sxs-lookup"><span data-stu-id="7c849-159">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="7c849-160">Un utilisateur détenteur d’une licence incluant Team n’est pas admissible à l’expérience exploratoire Teams.</span><span class="sxs-lookup"><span data-stu-id="7c849-160">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="7c849-161">Lorsque le plan de service Teams est activé, l’utilisateur peut se connecter et utiliser Teams.</span><span class="sxs-lookup"><span data-stu-id="7c849-161">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="7c849-162">Si le plan de service est désactivé, l’utilisateur ne peut pas se connecter et l’expérience exploratoire Teams n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="7c849-162">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="7c849-163">Vous devez disposer de privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="7c849-163">You must have admin privileges.</span></span>

<span data-ttu-id="7c849-164">Pour désactiver l’accès à Microsoft Teams :</span><span class="sxs-lookup"><span data-stu-id="7c849-164">To turn off access to Teams:</span></span>

1. <span data-ttu-id="7c849-165">Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs**.</span><span class="sxs-lookup"><span data-stu-id="7c849-165">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="7c849-166">Activez la case à cocher située en regard du nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7c849-166">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="7c849-167">Sur la ligne **Licences de produits**, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7c849-167">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="7c849-168">Dans le volet **Licences de produit**, sélectionnez **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="7c849-168">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![la page Licences de produit dans le centre d’administration.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="7c849-170">Gérer la disponibilité Teams pour les utilisateurs qui utilisent déjà l’expérience exploratoire Teams</span><span class="sxs-lookup"><span data-stu-id="7c849-170">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="7c849-p107">Si un utilisateur exécute l’expérience exploratoire Teams, vous pouvez la désactiver en supprimant la licence ou le plan de service. Vous devez disposer de privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="7c849-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="7c849-173">Pour désactiver la licence de l’expérience Teams Exploratory:</span><span class="sxs-lookup"><span data-stu-id="7c849-173">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="7c849-174">Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs**.</span><span class="sxs-lookup"><span data-stu-id="7c849-174">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="7c849-175">Activez la case à cocher située en regard du nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7c849-175">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="7c849-176">Sur la ligne **Licences de produits**, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7c849-176">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="7c849-177">Dans le volet **Licences de produit**, sélectionnez **Désactivé** pour cette licence exploratoire.</span><span class="sxs-lookup"><span data-stu-id="7c849-177">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c849-178">Le commutateur de bascule exploratoire Teams apparaît une fois que le premier utilisateur de l’organisation a lancé l’expérience exploratoire Teams.</span><span class="sxs-lookup"><span data-stu-id="7c849-178">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="7c849-179">Gérer Teams pour les utilisateurs disposant d’une licence exploratoire Teams</span><span class="sxs-lookup"><span data-stu-id="7c849-179">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="7c849-180">Vous pouvez gérer les utilisateurs qui ont une licence exploratoire Teams de la même façon que vous gérez ceux qui ont une licence payante régulière.</span><span class="sxs-lookup"><span data-stu-id="7c849-180">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="7c849-181">Pour plus d’informations[Gérer les paramètres de Teams pour votre organisation](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="7c849-181">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-teams-exploratory"></a><span data-ttu-id="7c849-182">Mettre à niveau des utilisateurs à partir de Teams Exploratoire</span><span class="sxs-lookup"><span data-stu-id="7c849-182">Upgrade users from Teams Exploratory</span></span>

<span data-ttu-id="7c849-183">Vous devez disposer de privilèges d’administrateur pour mettre à niveau les utilisateurs à partir de Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="7c849-183">You must have admin privileges to upgrade users from Teams Exploratory.</span></span> <span data-ttu-id="7c849-184">Pour plus d’informations, consultez [Mettre à niveau les utilisateurs à partir de l’essai exploratoire Teams](upgrade-from-teams-exploratory.md).</span><span class="sxs-lookup"><span data-stu-id="7c849-184">For more information see [Upgrade users from the Teams Exploratory trial](upgrade-from-teams-exploratory.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7c849-185">Si la licence exploratoire Teams se termine et qu’un utilisateur n’est pas immédiatement mis à niveau vers un abonnement incluant Teams, il perd l’accès à Teams après une période de grâce de 30 jours.</span><span class="sxs-lookup"><span data-stu-id="7c849-185">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they lose access to Teams after a 30-days grace period.</span></span> <span data-ttu-id="7c849-186">Après 30 jours, les données sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="7c849-186">Another 30 days after which, the data is deleted.</span></span> <span data-ttu-id="7c849-187">L’utilisateur demeure dans Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7c849-187">The user still exists in Azure Active Directory.</span></span> <span data-ttu-id="7c849-188">Une fois qu’une nouvelle licence est attribuée à l’utilisateur pour réactiver la fonctionnalité Teams, tout le contenu reste en l’état si l’utilisateur est ajouté dans le cadre du délai de grâce.</span><span class="sxs-lookup"><span data-stu-id="7c849-188">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="7c849-189">Supprimer une licence exploratoire Teams</span><span class="sxs-lookup"><span data-stu-id="7c849-189">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="7c849-190">Si vous souhaitez supprimer cette licence à l’aide PowerShell, voir [Supprimer des licences de comptes d’utilisateurs avec Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="7c849-190">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="7c849-191">Si vous souhaitez supprimer cette licence via le portail d’administration, consultez : [Supprimer un utilisateur de votre organisation](/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="7c849-191">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="7c849-192">En quoi consiste la stratégie de conservation des données ?</span><span class="sxs-lookup"><span data-stu-id="7c849-192">What is the data retention policy</span></span>

<span data-ttu-id="7c849-193">Consultez [informations d’abonnement 365](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="7c849-193">See [Microsoft 365 subscription information](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="7c849-194">Combien de temps dure l’expérience d’exploration de Teams ?</span><span class="sxs-lookup"><span data-stu-id="7c849-194">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="7c849-195">A partir de début 2021, Teams exploratoire est disponible sous la forme d'un abonnement de 12 mois (à partir de l'inscription initiale de l'utilisateur) pour tous les nouveaux clients.</span><span class="sxs-lookup"><span data-stu-id="7c849-195">As of early 2021, Teams Exploratory is available as a 12 month subscription (from initial user sign-up) for all new customers.</span></span> <span data-ttu-id="7c849-196">Le nouvel abonnement Teams exploratoire démarre lorsque le premier utilisateur d’une organisation s’est abonné à Teams exploratoire et expirera au bout de 12 mois.</span><span class="sxs-lookup"><span data-stu-id="7c849-196">The new Teams Exploratory subscription starts when the first user in an organization signs-up for Teams Exploratory and it will expire after 12 months.</span></span> <span data-ttu-id="7c849-197">La date d’expiration s’applique à tous les utilisateurs du même client. La période de 12 mois commence à la date d’inscription du premier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7c849-197">The expiry date will apply to all users in the same tenant as the 12-month term begins on the first user's sign-up date.</span></span>

> [!NOTE]
> <span data-ttu-id="7c849-198">La date de fin de l’expérience est configurée au niveau de l’organisation, ce qui signifie qu’elle s’applique à tous les utilisateurs d’une même organisation.</span><span class="sxs-lookup"><span data-stu-id="7c849-198">The end date for the experience is configured at an organization level, meaning it will apply to all users in the same organization.</span></span> <span data-ttu-id="7c849-199">Par exemple, l’utilisateur 1 s’est abonné à l’abonnement le 1er janvier 2021.</span><span class="sxs-lookup"><span data-stu-id="7c849-199">For example, User 1 signs up for the subscription on January 1, 2021.</span></span> <span data-ttu-id="7c849-200">Cela déclenche la date de fin de l’abonnement le 31 décembre 2021.</span><span class="sxs-lookup"><span data-stu-id="7c849-200">This initiates a subscription end-date of December 31, 2021.</span></span> <span data-ttu-id="7c849-201">Un autre utilisateur, Utilisateur 2, s’est abonné à l’abonnement le 1er octobre 2021.</span><span class="sxs-lookup"><span data-stu-id="7c849-201">Another user, User 2, signs up for the subscription on October 1, 2021.</span></span> <span data-ttu-id="7c849-202">L’utilisateur 2 peut utiliser Teams exploratoire pour deux mois, sa date de fin étant le 31 décembre 2021, car il est dans le cadre de l’abonnement de la même organisation que Utilisateur 1.</span><span class="sxs-lookup"><span data-stu-id="7c849-202">User 2 can use Teams Exploratory for two months, as their end-date will be December 31, 2021 because they're under the same organization's subscription as User 1.</span></span>

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a><span data-ttu-id="7c849-203">Que doivent faire les administrateurs à la fin des 12 mois d’expérience Teams exploratoire</span><span class="sxs-lookup"><span data-stu-id="7c849-203">What should administrators do at the end of the 12 month Teams Exploratory experience</span></span>

<span data-ttu-id="7c849-204">À la fin de l'abonnement de 12 mois, les administrateurs doivent convertir tous les utilisateurs de Teams exploratoire en une licence payante qui inclut Teams.</span><span class="sxs-lookup"><span data-stu-id="7c849-204">At the end of the 12 month subscription, administrators should convert all Teams Exploratory users to a paid license that includes Teams.</span></span> <span data-ttu-id="7c849-205">Il est essentiel de s’assurer que cette opération se termine avant l’expiration de l’abonnement Teams exploratoire Pour éviter toute interruption de l’expérience de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7c849-205">It is vital to ensure this is completed before the Teams Exploratory subscription expires to avoid any disruption to user's experience.</span></span>


> [!NOTE]
> <span data-ttu-id="7c849-206">Les clients seront désactivés et bloqués pour le démarrage d’une nouvelle licence d’évaluation de Exploratory pendant 3 mois après l’expiration de la licence d’évaluation Exploratory précédente.</span><span class="sxs-lookup"><span data-stu-id="7c849-206">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>

<span data-ttu-id="7c849-207">Pour plus d’informations, consultez [Mettre à niveau les utilisateurs de Teams Exploratory](#upgrade-users-from-teams-exploratory), ci-dessus dans cet article.</span><span class="sxs-lookup"><span data-stu-id="7c849-207">For more information, see [Upgrade users from Teams Exploratory](#upgrade-users-from-teams-exploratory), above in this article.</span></span>
