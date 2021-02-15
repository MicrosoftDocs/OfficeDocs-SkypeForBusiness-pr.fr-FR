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
description: Les utilisateurs de Microsoft 365 ou Office 365 qui ne disposent pas d’une licence Microsoft Teams peuvent initier une licence exploratoire.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9aa7b0a26e947eaa961db5d5be3b793d50474867
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196468"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="be999-103">Gérer la licence exploratoire Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be999-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="be999-104">L’expérience Microsoft Teams Exploratory permet aux utilisateurs de Azure Active Directory (AAD) de votre organisation qui n’ont pas de licence Teams de lancer l’expérience de l’exploration de Teams.</span><span class="sxs-lookup"><span data-stu-id="be999-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="be999-105">Les administrateurs peuvent activer ou désactiver cette fonctionnalité pour les utilisateurs de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="be999-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="be999-106">La précédente [Version d'évaluation dans le cloud commercial Microsoft](iw-trial-teams.md) est désormais remplacée par l'expérience exploratoire Teams.</span><span class="sxs-lookup"><span data-stu-id="be999-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="be999-107">Qu’est-ce que l’expérience exploratoire Teams ?</span><span class="sxs-lookup"><span data-stu-id="be999-107">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="be999-108">Les plans de service qu’un administrateur peut voir dans le cadre de l’expérience exploratoire Teams sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="be999-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="be999-109">Exchange Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="be999-109">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="be999-110">Flux pour Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="be999-110">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="be999-111">Informations obtenues par MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="be999-111">Insights by MyAnalytics</span></span>
- <span data-ttu-id="be999-112">Microsoft Forms (plan E1)</span><span class="sxs-lookup"><span data-stu-id="be999-112">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="be999-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="be999-113">Microsoft Planner</span></span>
- <span data-ttu-id="be999-114">Recherche Microsoft</span><span class="sxs-lookup"><span data-stu-id="be999-114">Microsoft Search</span></span>
- <span data-ttu-id="be999-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="be999-115">Microsoft StaffHub</span></span>
- <span data-ttu-id="be999-116">Microsoft Stream pour Microsoft 365 et Office 365 E1 SKU <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="be999-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="be999-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be999-117">Microsoft Teams</span></span>
- <span data-ttu-id="be999-118">Gestion des appareils mobiles pour Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="be999-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="be999-119">Applications Office Mobile pour Office 365</span><span class="sxs-lookup"><span data-stu-id="be999-119">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="be999-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="be999-120">Office Online</span></span>
- <span data-ttu-id="be999-121">PowerApp pour Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="be999-121">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="be999-122">SharePoint Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="be999-122">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="be999-123">Sway</span><span class="sxs-lookup"><span data-stu-id="be999-123">Sway</span></span>
- <span data-ttu-id="be999-124">Tâches (plan 1)</span><span class="sxs-lookup"><span data-stu-id="be999-124">To-Do (Plan 1)</span></span>
- <span data-ttu-id="be999-125">Tableau blanc (plan 1)</span><span class="sxs-lookup"><span data-stu-id="be999-125">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="be999-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="be999-126">Yammer Enterprise</span></span>

  <span data-ttu-id="be999-127"><sup>1</sup> Les modifications apportées à l’utilisation de Microsoft Stream pour [OneDrive Entreprise et SharePoint pour les enregistrements de réunion](tmr-meeting-recording-change.md) auront une approche progressive.</span><span class="sxs-lookup"><span data-stu-id="be999-127"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="be999-128">Au démarrage, vous pourrez choisir cette expérience.</span><span class="sxs-lookup"><span data-stu-id="be999-128">At launch, you'll be able to opt in to this experience.</span></span> <span data-ttu-id="be999-129">En novembre, vous devrez abandonner cette option si vous souhaitez continuer à utiliser Stream.</span><span class="sxs-lookup"><span data-stu-id="be999-129">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="be999-130">Au début de 2021, nous demanderons à tous les clients d’utiliser OneDrive Entreprise et SharePoint pour les nouveaux enregistrements de réunion.</span><span class="sxs-lookup"><span data-stu-id="be999-130">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="be999-131">Critères d’éligibilité</span><span class="sxs-lookup"><span data-stu-id="be999-131">Who's eligible</span></span>

<span data-ttu-id="be999-132">Les utilisateurs éligibles à l’expérience Teams Exploratory sont les utilisateurs qui:</span><span class="sxs-lookup"><span data-stu-id="be999-132">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="be999-133">Disposent d’une adresse e-mail du domaine Azure AD gérée.</span><span class="sxs-lookup"><span data-stu-id="be999-133">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="be999-134">Appartiennent à un client disposant d’un abonnement payant.</span><span class="sxs-lookup"><span data-stu-id="be999-134">Belong to a tenant with a paid subscription.</span></span>
- <span data-ttu-id="be999-135">N’avez pas de licence Teams active.</span><span class="sxs-lookup"><span data-stu-id="be999-135">Do not have an active Teams license.</span></span>
- <span data-ttu-id="be999-136">Ne se trouve pas dans un client où une stratégie d’attribution de licence a été créée.</span><span class="sxs-lookup"><span data-stu-id="be999-136">Are not in a tenant where a license assignment policy was created.</span></span>

<span data-ttu-id="be999-137">Les utilisateurs doivent être autorisés à s’inscrire aux applications et aux essais (dans le Centre d’administration Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="be999-137">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="be999-138">Pour plus d’informations, voir [Gérer l’expérience exploratoire Teams](#manage-the-teams-exploratory-experience) plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="be999-138">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="be999-139">Qui n'est pas éligible ?</span><span class="sxs-lookup"><span data-stu-id="be999-139">Who isn't eligible</span></span>

<span data-ttu-id="be999-140">Les utilisateurs inéligibles sont les utilisateurs qui :</span><span class="sxs-lookup"><span data-stu-id="be999-140">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="be999-141">disposent ou ont disposé de Teams grâce à une licence payée, non payée ou d’évaluation ;</span><span class="sxs-lookup"><span data-stu-id="be999-141">Currently or previously had Teams from a paid, unpaid, or trial license</span></span>
- <span data-ttu-id="be999-142">se trouvent dans un client qui utilise ou a reçu au moins une offre spéciale COVID.</span><span class="sxs-lookup"><span data-stu-id="be999-142">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="be999-143">Votre organisation n’est pas éligible pour cette offre si vous êtes un client partenaire de syndication ou un client GCC, GCC élevé, DoD ou EDU.</span><span class="sxs-lookup"><span data-stu-id="be999-143">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="be999-144">Comment les utilisateurs s’inscrivent pour l’expérience exploratoire Teams ?</span><span class="sxs-lookup"><span data-stu-id="be999-144">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="be999-145">Les utilisateurs éligibles peuvent s’inscrire à l’expérience exploratoire Teams en se connectant à Teams à partir de l’ordinateur de bureau ou web ([teams.microsoft.com](https://teams.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="be999-145">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="be999-146">Pour l’instant, l’activation de exploratoire via mobile n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="be999-146">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="be999-147">Lorsqu’il s’inscrivent, la licence leur est attribuée automatiquement et l’administrateur client reçoit une notification par e-mail la première fois qu’une personne au sein de votre organisation démarre l’expérience Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="be999-147">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="be999-148">Gérer l’expérience Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="be999-148">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="be999-149">L’expérience Teams Exploratory est destinée aux utilisateurs finaux individuels et vous ne pouvez pas lancer cette offre pour le compte d’employés de l’utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="be999-149">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="be999-150">L’expérience Teams Exploratory est offerte avec une licence Exchange Online, mais elle ne peut être attribuée à l’utilisateur que par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="be999-150">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="be999-151">Si l’utilisateur ne dispose pas déjà d’une licence Exchange et que l’administrateur ne lui a pas encore attribué la licence Exchange Online, l’utilisateur ne peut pas planifier de réunions dans Teams et pourrait manquer d’autres fonctionnalités Teams.</span><span class="sxs-lookup"><span data-stu-id="be999-151">If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="be999-152">Les administrateurs peuvent désactiver la possibilité pour les utilisateurs finaux d’exécuter l’expérience exploratoire des équipes au sein de leur organisation à l’aide du commutateur des **applications et services d’essai**.</span><span class="sxs-lookup"><span data-stu-id="be999-152">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="be999-153">Empêcher les utilisateurs d’installer des applications et services à l’essai</span><span class="sxs-lookup"><span data-stu-id="be999-153">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="be999-154">Vous pouvez désactiver la possibilité pour un utilisateur d’installer des applications et des services d’essai, ce qui l’empêche d’exécuter l’expérience exploratoire Teams.</span><span class="sxs-lookup"><span data-stu-id="be999-154">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="be999-155">Dans le Centre d’administration Microsoft 365, accédez à **Paramètres** > **Paramètres org**, sélectionnez **Services**, puis choisissez **Services et applications propriétés de l'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="be999-155">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![La page Services dans le Centre d’administration](media/iw-trial-services.png)

2. <span data-ttu-id="be999-157">Désactivez la cache à cocher **Permettre aux utilisateurs d'installer les applications et services à l’essai**.</span><span class="sxs-lookup"><span data-stu-id="be999-157">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![L’Utilisateur dispose d’une page des applications et services dans le Centre d’administration](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="be999-159">Si votre organisation n’est pas éligible à l’expérience exploratoire Teams, l'option **Laisser les utilisateurs installer les applications et services d’essai** ne s’affiche pas.</span><span class="sxs-lookup"><span data-stu-id="be999-159">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="be999-160">Gérer la disponibilité pour un utilisateur disposant d’une licence incluant Teams</span><span class="sxs-lookup"><span data-stu-id="be999-160">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="be999-161">Un utilisateur détenteur d’une licence incluant Team n’est pas admissible à l’expérience exploratoire Teams.</span><span class="sxs-lookup"><span data-stu-id="be999-161">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="be999-162">Lorsque le plan de service Teams est activé, l’utilisateur peut se connecter et utiliser Teams.</span><span class="sxs-lookup"><span data-stu-id="be999-162">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="be999-163">Si le plan de service est désactivé, l’utilisateur ne peut pas se connecter et l’expérience exploratoire Teams n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="be999-163">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="be999-164">Vous devez disposer de privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="be999-164">You must have admin privileges.</span></span>

<span data-ttu-id="be999-165">Pour désactiver l’accès à Microsoft Teams :</span><span class="sxs-lookup"><span data-stu-id="be999-165">To turn off access to Teams:</span></span>

1. <span data-ttu-id="be999-166">Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs**.</span><span class="sxs-lookup"><span data-stu-id="be999-166">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="be999-167">Activez la case à cocher située en regard du nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="be999-167">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="be999-168">Sur la ligne **Licences de produits**, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="be999-168">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="be999-169">Dans le volet **Licences de produit**, sélectionnez **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="be999-169">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![la page Licences de produit dans le centre d’administration.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="be999-171">Gérer la disponibilité Teams pour les utilisateurs qui utilisent déjà l’expérience exploratoire Teams</span><span class="sxs-lookup"><span data-stu-id="be999-171">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="be999-172">Si un utilisateur exécute l’expérience exploratoire Teams, vous pouvez la désactiver en supprimant la licence ou le plan de service.</span><span class="sxs-lookup"><span data-stu-id="be999-172">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span> <span data-ttu-id="be999-173">Vous devez disposer de privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="be999-173">You must have admin privileges.</span></span>

<span data-ttu-id="be999-174">Pour désactiver la licence de l’expérience Teams Exploratory:</span><span class="sxs-lookup"><span data-stu-id="be999-174">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="be999-175">Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs**.</span><span class="sxs-lookup"><span data-stu-id="be999-175">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="be999-176">Activez la case à cocher située en regard du nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="be999-176">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="be999-177">Sur la ligne **Licences de produits**, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="be999-177">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="be999-178">Dans le volet **Licences de produit**, sélectionnez **Désactivé** pour cette licence exploratoire.</span><span class="sxs-lookup"><span data-stu-id="be999-178">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    >[!Note]
    ><span data-ttu-id="be999-179">Le commutateur de bascule exploratoire Teams apparaît une fois que le premier utilisateur de l’organisation a lancé l’expérience exploratoire Teams.</span><span class="sxs-lookup"><span data-stu-id="be999-179">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="be999-180">Gérer Teams pour les utilisateurs disposant d’une licence exploratoire Teams</span><span class="sxs-lookup"><span data-stu-id="be999-180">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="be999-181">Vous pouvez gérer les utilisateurs qui ont une licence exploratoire Teams de la même façon que vous gérez ceux qui ont une licence payante régulière.</span><span class="sxs-lookup"><span data-stu-id="be999-181">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="be999-182">Pour plus d’informations[Gérer les paramètres de Teams pour votre organisation](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="be999-182">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="be999-183">Mettre à niveau les utilisateurs de la licence exploratoire Teams</span><span class="sxs-lookup"><span data-stu-id="be999-183">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="be999-184">Pour mettre à niveau les utilisateurs à partir de la licence Teams Exploratory, vous devez disposer de privilèges d’administrateur et procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="be999-184">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="be999-185">Achetez un abonnement incluant Teams.</span><span class="sxs-lookup"><span data-stu-id="be999-185">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="be999-186">Supprimez l’abonnement exploratoire Teams pour l’utilisateur en question.</span><span class="sxs-lookup"><span data-stu-id="be999-186">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="be999-187">Affectez la licence nouvellement achetée.</span><span class="sxs-lookup"><span data-stu-id="be999-187">Assign the newly purchased license.</span></span>

<span data-ttu-id="be999-188">Pour plus d’informations, voir [Description du service Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="be999-188">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="be999-189">Si la licence Teams Exploratory expire et l’utilisateur n’est pas immédiatement mis à niveau vers un abonnement comprenant Teams, ils disposent de 30 jours de délai de grâce, puis de 30 jours supplémentaires. Après ce délai les données sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="be999-189">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted.</span></span> <span data-ttu-id="be999-190">L’utilisateur demeure dans Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="be999-190">The user still exists in Azure Active Directory.</span></span> <span data-ttu-id="be999-191">Une fois qu’une nouvelle licence est attribuée à l’utilisateur pour réactiver la fonctionnalité Teams, tout le contenu reste en l’état si l’utilisateur est ajouté dans le cadre du délai de grâce.</span><span class="sxs-lookup"><span data-stu-id="be999-191">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="be999-192">Qu’arrive-t-il aux licences d’évaluation cloud commercial de Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="be999-192">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="be999-193">À partir de février 2020, les utilisateurs éligibles peuvent commencer à utiliser l’expérience la plus récente de Microsoft Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="be999-193">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="be999-194">Toutes les versions d’évaluation du Cloud commercial sont automatiquement converties à la nouvelle offre avant l’expiration de la période d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="be999-194">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="be999-195">Lorsqu'un utilisateur se connecte pour la première fois à la version d'évaluation cloud commercial de Teams expiré, nous lui attribuons automatiquement une licence d'expérience Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="be999-195">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users.</span></span> <span data-ttu-id="be999-196">Les utilisateurs ne sont pas convertis avant de s'être inscrits.</span><span class="sxs-lookup"><span data-stu-id="be999-196">Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="be999-197">Supprimer une licence exploratoire Teams</span><span class="sxs-lookup"><span data-stu-id="be999-197">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="be999-198">Si vous souhaitez supprimer cette licence à l’aide PowerShell, voir [Supprimer des licences de comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="be999-198">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="be999-199">Si vous souhaitez supprimer cette licence via le portail d’administration, consultez : [Supprimer un utilisateur de votre organisation](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="be999-199">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="be999-200">En quoi consiste la stratégie de conservation des données ?</span><span class="sxs-lookup"><span data-stu-id="be999-200">What is the data retention policy</span></span>

<span data-ttu-id="be999-201">Consultez [informations d’abonnement 365](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="be999-201">See [Microsoft 365 subscription information](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="be999-202">Combien de temps dure l’expérience d’exploration de Teams ?</span><span class="sxs-lookup"><span data-stu-id="be999-202">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="be999-203">A partir de début 2021, Teams exploratoire est disponible sous la forme d'un abonnement de 12 mois (à partir de l'inscription initiale de l'utilisateur) pour tous les nouveaux clients.</span><span class="sxs-lookup"><span data-stu-id="be999-203">As of early 2021, Teams Exploratory is available as a 12 month subscription (from initial user sign-up) for all new customers.</span></span> <span data-ttu-id="be999-204">Le nouvel abonnement Teams exploratoire démarre lorsque le premier utilisateur d’une organisation s’est abonné à Teams exploratoire et expirera au bout de 12 mois.</span><span class="sxs-lookup"><span data-stu-id="be999-204">The new Teams Exploratory subscription starts when the first user in an organization signs-up for Teams Exploratory and it will expire after 12 months.</span></span> <span data-ttu-id="be999-205">La date d’expiration s’applique à tous les utilisateurs du même client. La période de 12 mois commence à la date d’inscription du premier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="be999-205">The expiry date will apply to all users in the same tenant as the 12-month term begins on the first user's sign-up date.</span></span>

> [!NOTE]
> <span data-ttu-id="be999-206">La date de fin de l’expérience est configurée au niveau de l’organisation, ce qui signifie qu’elle s’applique à tous les utilisateurs d’une même organisation.</span><span class="sxs-lookup"><span data-stu-id="be999-206">The end date for the experience is configured at an organization level, meaning it will apply to all users in the same organization.</span></span> <span data-ttu-id="be999-207">Par exemple, l’utilisateur 1 s’est abonné à l’abonnement le 1er janvier 2021.</span><span class="sxs-lookup"><span data-stu-id="be999-207">For example, User 1 signs up for the subscription on January 1, 2021.</span></span> <span data-ttu-id="be999-208">Cela déclenche la date de fin de l’abonnement le 31 décembre 2021.</span><span class="sxs-lookup"><span data-stu-id="be999-208">This initiates a subscription end-date of December 31, 2021.</span></span> <span data-ttu-id="be999-209">Un autre utilisateur, Utilisateur 2, s’est abonné à l’abonnement le 1er octobre 2021.</span><span class="sxs-lookup"><span data-stu-id="be999-209">Another user, User 2, signs up for the subscription on October 1, 2021.</span></span> <span data-ttu-id="be999-210">L’utilisateur 2 peut utiliser Teams exploratoire pour deux mois, sa date de fin étant le 31 décembre 2021, car il est dans le cadre de l’abonnement de la même organisation que Utilisateur 1.</span><span class="sxs-lookup"><span data-stu-id="be999-210">User 2 can use Teams Exploratory for two months, as their end-date will be December 31, 2021 because they're under the same organization's subscription as User 1.</span></span>

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a><span data-ttu-id="be999-211">Que doivent faire les administrateurs à la fin des 12 mois d’expérience Teams exploratoire</span><span class="sxs-lookup"><span data-stu-id="be999-211">What should administrators do at the end of the 12 month Teams Exploratory experience</span></span>

<span data-ttu-id="be999-212">À la fin de l'abonnement de 12 mois, les administrateurs doivent convertir tous les utilisateurs de Teams exploratoire en une licence payante qui inclut Teams.</span><span class="sxs-lookup"><span data-stu-id="be999-212">At the end of the 12 month subscription, administrators should convert all Teams Exploratory users to a paid license that includes Teams.</span></span> <span data-ttu-id="be999-213">Il est essentiel de s’assurer que cette opération se termine avant l’expiration de l’abonnement Teams exploratoire Pour éviter toute interruption de l’expérience de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="be999-213">It is vital to ensure this is completed before the Teams Exploratory subscription expires to avoid any disruption to user's experience.</span></span>

<span data-ttu-id="be999-214">Pour plus d’informations, consultez la rubrique [Mise à niveau des utilisateurs à partir de licence Teams exploratoire](#upgrade-users-from-the-teams-exploratory-license), plus haut dans cet article.</span><span class="sxs-lookup"><span data-stu-id="be999-214">For more information, see [Upgrade users from the Teams Exploratory license](#upgrade-users-from-the-teams-exploratory-license)), above in this article.</span></span>
