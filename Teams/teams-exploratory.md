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
appliesto:
- Microsoft Teams
ms.openlocfilehash: a266d9d3ea8fd572cca171768174d86094a8c945
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766967"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="388a0-103">Gérer la licence exploratoire Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="388a0-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="388a0-104">L’expérience Microsoft Teams Exploratory permet aux utilisateurs de Azure Active Directory (AAD) de votre organisation qui n’ont pas de licence Teams de lancer l’expérience de l’exploration de Teams.</span><span class="sxs-lookup"><span data-stu-id="388a0-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="388a0-105">Les administrateurs peuvent activer ou désactiver cette fonctionnalité pour les utilisateurs de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="388a0-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="388a0-106">La précédente [Version d'évaluation dans le cloud commercial Microsoft](iw-trial-teams.md) est désormais remplacée par l'expérience exploratoire Teams.</span><span class="sxs-lookup"><span data-stu-id="388a0-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="388a0-107">Qu’est-ce que l’expérience exploratoire Teams ?</span><span class="sxs-lookup"><span data-stu-id="388a0-107">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="388a0-108">Les plans de service qu’un administrateur peut voir dans le cadre de l’expérience exploratoire Teams sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="388a0-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="388a0-109">Exchange Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="388a0-109">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="388a0-110">Flux pour Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="388a0-110">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="388a0-111">Informations obtenues par MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="388a0-111">Insights by MyAnalytics</span></span>
- <span data-ttu-id="388a0-112">Microsoft Forms (plan E1)</span><span class="sxs-lookup"><span data-stu-id="388a0-112">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="388a0-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="388a0-113">Microsoft Planner</span></span>
- <span data-ttu-id="388a0-114">Recherche Microsoft</span><span class="sxs-lookup"><span data-stu-id="388a0-114">Microsoft Search</span></span>
- <span data-ttu-id="388a0-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="388a0-115">Microsoft StaffHub</span></span>
- <span data-ttu-id="388a0-116">Microsoft Stream pour Microsoft 365 et Office 365 E1 SKU <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="388a0-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="388a0-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="388a0-117">Microsoft Teams</span></span>
- <span data-ttu-id="388a0-118">Gestion des appareils mobiles pour Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="388a0-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="388a0-119">Applications Office Mobile pour Office 365</span><span class="sxs-lookup"><span data-stu-id="388a0-119">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="388a0-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="388a0-120">Office Online</span></span>
- <span data-ttu-id="388a0-121">PowerApp pour Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="388a0-121">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="388a0-122">SharePoint Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="388a0-122">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="388a0-123">Sway</span><span class="sxs-lookup"><span data-stu-id="388a0-123">Sway</span></span>
- <span data-ttu-id="388a0-124">Tâches (plan 1)</span><span class="sxs-lookup"><span data-stu-id="388a0-124">To-Do (Plan 1)</span></span>
- <span data-ttu-id="388a0-125">Tableau blanc (plan 1)</span><span class="sxs-lookup"><span data-stu-id="388a0-125">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="388a0-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="388a0-126">Yammer Enterprise</span></span>

  <span data-ttu-id="388a0-127"><sup>1</sup> Les modifications apportées à l’utilisation de Microsoft Stream pour [OneDrive Entreprise et SharePoint pour les enregistrements de réunion](tmr-meeting-recording-change.md) auront une approche progressive.</span><span class="sxs-lookup"><span data-stu-id="388a0-127"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="388a0-128">Au démarrage, vous pourrez choisir cette expérience.</span><span class="sxs-lookup"><span data-stu-id="388a0-128">At launch you'll be able to opt in to this experience.</span></span> <span data-ttu-id="388a0-129">En novembre, vous devrez abandonner cette option si vous souhaitez continuer à utiliser Stream.</span><span class="sxs-lookup"><span data-stu-id="388a0-129">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="388a0-130">Au début de 2021, nous demanderons à tous les clients d’utiliser OneDrive Entreprise et SharePoint pour les nouveaux enregistrements de réunion.</span><span class="sxs-lookup"><span data-stu-id="388a0-130">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="388a0-131">Critères d’éligibilité</span><span class="sxs-lookup"><span data-stu-id="388a0-131">Who's eligible</span></span>

<span data-ttu-id="388a0-132">Les utilisateurs éligibles à l’expérience Teams Exploratory sont les utilisateurs qui:</span><span class="sxs-lookup"><span data-stu-id="388a0-132">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="388a0-133">Disposent d’une adresse e-mail du domaine Azure AD gérée.</span><span class="sxs-lookup"><span data-stu-id="388a0-133">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="388a0-134">Appartiennent à un client disposant d’un abonnement payant.</span><span class="sxs-lookup"><span data-stu-id="388a0-134">Belong to a tenant with a paid subscription.</span></span>

<span data-ttu-id="388a0-135">Les utilisateurs doivent être autorisés à s’inscrire aux applications et aux essais (dans le Centre d’administration Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="388a0-135">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="388a0-136">Pour plus d’informations, voir [Gérer l’expérience exploratoire Teams](#manage-the-teams-exploratory-experience) plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="388a0-136">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="388a0-137">Qui n'est pas éligible ?</span><span class="sxs-lookup"><span data-stu-id="388a0-137">Who isn't eligible</span></span>

<span data-ttu-id="388a0-138">Les utilisateurs inéligibles sont les utilisateurs qui:</span><span class="sxs-lookup"><span data-stu-id="388a0-138">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="388a0-139">Disposent ou ont disposé de Teams grâce à une licence payée, non payée ou d’évaluation ;</span><span class="sxs-lookup"><span data-stu-id="388a0-139">Currently or previously had Teams from a paid, unpaid or trial license</span></span> 
- <span data-ttu-id="388a0-140">Se trouvent dans un client qui utilise ou a reçu au moins une offre spéciale COVID.</span><span class="sxs-lookup"><span data-stu-id="388a0-140">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="388a0-141">Votre organisation n’est pas éligible pour cette offre si vous êtes un client partenaire de syndication ou un client GCC, GCC élevé, DoD ou EDU.</span><span class="sxs-lookup"><span data-stu-id="388a0-141">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="388a0-142">Comment les utilisateurs s’inscrivent pour l’expérience exploratoire Teams ?</span><span class="sxs-lookup"><span data-stu-id="388a0-142">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="388a0-143">Les utilisateurs éligibles peuvent s’inscrire à l’expérience exploratoire Teams en se connectant à Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="388a0-143">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="388a0-144">Cette licence leur est attribuée automatiquement et l’administrateur client reçoit une notification par e-mail la première fois qu’une personne au sein de votre organisation démarre l’expérience Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="388a0-144">They'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="388a0-145">Gérer l’expérience Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="388a0-145">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="388a0-146">L’expérience Teams Exploratory est destinée aux utilisateurs finaux individuels et vous ne pouvez pas lancer cette offre pour le compte d’employés de l’utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="388a0-146">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="388a0-147">L’expérience Teams Exploratory est offerte avec une licence Exchange Online, mais elle ne peut être attribuée à l’utilisateur que par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="388a0-147">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="388a0-148">Si l’utilisateur ne dispose pas déjà d’une licence Exchange et que l’administrateur ne lui a pas encore attribué la licence Exchange Online, l’utilisateur ne peut pas planifier de réunions dans Teams et pourrait manquer d’autres fonctionnalités Teams.</span><span class="sxs-lookup"><span data-stu-id="388a0-148">If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="388a0-149">Les administrateurs peuvent désactiver la possibilité pour les utilisateurs finaux d’exécuter l’expérience exploratoire des équipes au sein de leur organisation à l’aide du commutateur des **applications et services d’essai** .</span><span class="sxs-lookup"><span data-stu-id="388a0-149">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="388a0-150">Empêcher les utilisateurs d’installer des applications et services à l’essai</span><span class="sxs-lookup"><span data-stu-id="388a0-150">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="388a0-151">Vous pouvez désactiver la possibilité pour un utilisateur d’installer des applications et des services d’essai, ce qui l’empêche d’exécuter l’expérience exploratoire Teams.</span><span class="sxs-lookup"><span data-stu-id="388a0-151">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="388a0-152">Dans le Centre d’administration Microsoft 365, accédez à **Paramètres** > **Paramètres org** , sélectionnez **Services** , puis choisissez **Services et applications propriétés de l'utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="388a0-152">From the Microsoft 365 admin center, go to **Settings** > **Org settings** , select **Services** , and then select **User owned apps and services** .</span></span>

    ![La page Services dans le Centre d’administration](media/iw-trial-services.png)

2. <span data-ttu-id="388a0-154">Désactivez la cache à cocher **Permettre aux utilisateurs d'installer les applications et services à l’essai** .</span><span class="sxs-lookup"><span data-stu-id="388a0-154">Clear the **Let users install trial apps and services** check box.</span></span>

    ![L’Utilisateur dispose d’une page des applications et services dans le Centre d’administration](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="388a0-156">Si votre organisation n’est pas éligible à l’expérience exploratoire Teams, l'option **Laisser les utilisateurs installer les applications et services d’essai** ne s’affiche pas.</span><span class="sxs-lookup"><span data-stu-id="388a0-156">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="388a0-157">Gérer la disponibilité pour un utilisateur disposant d’une licence incluant Teams</span><span class="sxs-lookup"><span data-stu-id="388a0-157">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="388a0-158">Un utilisateur détenteur d’une licence incluant Team n’est pas admissible à l’expérience exploratoire Teams.</span><span class="sxs-lookup"><span data-stu-id="388a0-158">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="388a0-159">Lorsque le plan de service Teams est activé, l’utilisateur peut se connecter et utiliser Teams.</span><span class="sxs-lookup"><span data-stu-id="388a0-159">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="388a0-160">Si le plan de service est désactivé, l’utilisateur ne peut pas se connecter et l’expérience exploratoire Teams n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="388a0-160">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="388a0-161">Vous devez disposer de privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="388a0-161">You must have admin privileges.</span></span>

<span data-ttu-id="388a0-162">Pour désactiver l’accès à Microsoft Teams :</span><span class="sxs-lookup"><span data-stu-id="388a0-162">To turn off access to Teams:</span></span>

1. <span data-ttu-id="388a0-163">Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs** .</span><span class="sxs-lookup"><span data-stu-id="388a0-163">In the Microsoft 365 admin center, select **Users** > **Active users** .</span></span>

2. <span data-ttu-id="388a0-164">Activez la case à cocher située en regard du nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="388a0-164">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="388a0-165">Sur la ligne **Licences de produits** , sélectionnez **Modifier** .</span><span class="sxs-lookup"><span data-stu-id="388a0-165">In the **Product licenses** row, choose **Edit** .</span></span>

4. <span data-ttu-id="388a0-166">Dans le volet **Licences de produit** , sélectionnez **Désactivé** .</span><span class="sxs-lookup"><span data-stu-id="388a0-166">In the **Product licenses** pane, switch the toggle to **Off** .</span></span>

    ![la page Licences de produit dans le centre d’administration.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="388a0-168">Gérer la disponibilité Teams pour les utilisateurs qui utilisent déjà l’expérience exploratoire Teams</span><span class="sxs-lookup"><span data-stu-id="388a0-168">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="388a0-169">Si un utilisateur exécute l’expérience exploratoire Teams, vous pouvez la désactiver en supprimant la licence ou le plan de service.</span><span class="sxs-lookup"><span data-stu-id="388a0-169">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span> <span data-ttu-id="388a0-170">Vous devez disposer de privilèges d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="388a0-170">You must have admin privileges.</span></span>

<span data-ttu-id="388a0-171">Pour désactiver la licence de l’expérience Teams Exploratory:</span><span class="sxs-lookup"><span data-stu-id="388a0-171">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="388a0-172">Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs** .</span><span class="sxs-lookup"><span data-stu-id="388a0-172">In the Microsoft 365 admin center, select **Users** > **Active users** .</span></span>

2. <span data-ttu-id="388a0-173">Activez la case à cocher située en regard du nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="388a0-173">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="388a0-174">Sur la ligne **Licences de produits** , sélectionnez **Modifier** .</span><span class="sxs-lookup"><span data-stu-id="388a0-174">In the **Product licenses** row, choose **Edit** .</span></span>

4. <span data-ttu-id="388a0-175">Dans le volet **Licences de produit** , sélectionnez **Désactivé** pour cette licence exploratoire.</span><span class="sxs-lookup"><span data-stu-id="388a0-175">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off** .</span></span>

    >[!Note]
    ><span data-ttu-id="388a0-176">Le commutateur de bascule exploratoire Teams apparaît une fois que le premier utilisateur de l’organisation a lancé l’expérience exploratoire Teams.</span><span class="sxs-lookup"><span data-stu-id="388a0-176">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="388a0-177">Gérer Teams pour les utilisateurs disposant d’une licence exploratoire Teams</span><span class="sxs-lookup"><span data-stu-id="388a0-177">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="388a0-178">Vous pouvez gérer les utilisateurs qui ont une licence exploratoire Teams de la même façon que vous gérez ceux qui ont une licence payante régulière.</span><span class="sxs-lookup"><span data-stu-id="388a0-178">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="388a0-179">Pour plus d’informations[Gérer les paramètres de Teams pour votre organisation](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="388a0-179">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="388a0-180">Mettre à niveau les utilisateurs de la licence exploratoire Teams</span><span class="sxs-lookup"><span data-stu-id="388a0-180">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="388a0-181">Pour mettre à niveau les utilisateurs à partir de la licence Teams Exploratory, vous devez disposer de privilèges d’administrateur et procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="388a0-181">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="388a0-182">Achetez un abonnement incluant Teams.</span><span class="sxs-lookup"><span data-stu-id="388a0-182">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="388a0-183">Supprimez l’abonnement exploratoire Teams pour l’utilisateur en question.</span><span class="sxs-lookup"><span data-stu-id="388a0-183">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="388a0-184">Affectez la licence nouvellement achetée.</span><span class="sxs-lookup"><span data-stu-id="388a0-184">Assign the newly purchased license.</span></span>

<span data-ttu-id="388a0-185">Pour plus d’informations, voir [Description du service Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="388a0-185">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="388a0-186">Si la licence Teams Exploratory expire et l’utilisateur n’est pas immédiatement mis à niveau vers un abonnement comprenant Teams, ils disposent de 30 jours de délai de grâce, puis de 30 jours supplémentaires. Après ce délai les données sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="388a0-186">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted.</span></span> <span data-ttu-id="388a0-187">L’utilisateur demeure dans Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="388a0-187">The user still exists in Azure Active Directory.</span></span> <span data-ttu-id="388a0-188">Une fois qu’une nouvelle licence est attribuée à l’utilisateur pour réactiver la fonctionnalité Teams, tout le contenu reste en l’état si l’utilisateur est ajouté dans le cadre du délai de grâce.</span><span class="sxs-lookup"><span data-stu-id="388a0-188">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="388a0-189">Qu’arrive-t-il aux licences d’évaluation cloud commercial de Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="388a0-189">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="388a0-190">À partir de février 2020, les utilisateurs éligibles peuvent commencer à utiliser l’expérience la plus récente de Microsoft Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="388a0-190">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="388a0-191">Toutes les versions d’évaluation du Cloud commercial sont automatiquement converties à la nouvelle offre avant l’expiration de la période d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="388a0-191">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="388a0-192">Lorsqu'un utilisateur se connecte pour la première fois à la version d'évaluation cloud commercial de Teams expiré, nous lui attribuons automatiquement une licence d'expérience Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="388a0-192">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users.</span></span> <span data-ttu-id="388a0-193">Les utilisateurs ne sont pas convertis avant de s'être inscrits.</span><span class="sxs-lookup"><span data-stu-id="388a0-193">Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="388a0-194">Supprimer une licence exploratoire Teams</span><span class="sxs-lookup"><span data-stu-id="388a0-194">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="388a0-195">Si vous souhaitez supprimer cette licence à l’aide PowerShell, voir [Supprimer des licences de comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="388a0-195">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="388a0-196">Si vous souhaitez supprimer cette licence via le portail d’administration, consultez : [Supprimer un utilisateur de votre organisation](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="388a0-196">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="388a0-197">Explication de la stratégie de rétention des données </span><span class="sxs-lookup"><span data-stu-id="388a0-197">What is the data retention policy</span></span>

<span data-ttu-id="388a0-198">Consultez [informations d’abonnement 365](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="388a0-198">See [Microsoft 365 subscription information](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="388a0-199">Combien de temps dure l’expérience d’exploration de Teams ?</span><span class="sxs-lookup"><span data-stu-id="388a0-199">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="388a0-200">L’expérience Microsoft Teams Exploratory est disponible sans frais supplémentaires jusqu’à la prochaine **date anniversaire** ou au prochain **renouvellement** de votre contrat d’entreprise survenant à compter du mois de janvier 2021.</span><span class="sxs-lookup"><span data-stu-id="388a0-200">The Microsoft Teams Exploratory experience is available at no additional cost until your next **agreement anniversary** or **renewal** on or after January 2021.</span></span> <span data-ttu-id="388a0-201">À ce stade, les utilisateurs finaux ayant une licence d’expérience exploratoire Microsoft doivent migrer vers une licence payante incluant Teams.</span><span class="sxs-lookup"><span data-stu-id="388a0-201">At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams.</span></span> <span data-ttu-id="388a0-202">Toutes les licences d’expérience exploratoire Microsoft commencées après cette période resteront valables sans frais supplémentaires jusqu’au prochain cycle **anniversaire** ou de **renouvellement** .</span><span class="sxs-lookup"><span data-stu-id="388a0-202">Any Microsoft Exploratory experience licenses initiated after that will remain available at no additional cost until your next **anniversary** or **renewal** cycle.</span></span>

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a><span data-ttu-id="388a0-203">Implications du lancement par un utilisateur final de l'expérience Microsoft Teams Exploratory juste avant la date d'anniversaire ou de renouvellement</span><span class="sxs-lookup"><span data-stu-id="388a0-203">What happens if an end user initiates the Microsoft Teams Exploratory experience just before the anniversary or renewal date</span></span>

<span data-ttu-id="388a0-204">Les licences de l’expérience Microsoft Teams Exploratory lancées dans le délai de 90 jours de la **date anniversaire** ou du **renouvellement** de votre contrat n’auront pas à migrer vers une licence payante avant le prochain cycle d’anniversaire ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="388a0-204">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** won't be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span>

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="388a0-205">Que se passe-t-il si mon contrat ne possède pas de date de anniversaire ou de renouvellement annuel (par exemple, des contrats de mois à mois)</span><span class="sxs-lookup"><span data-stu-id="388a0-205">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)</span></span>

<span data-ttu-id="388a0-206">Pour les contrats qui n’ont pas de date de anniversaire ou de renouvellement annuel, l’année suivant l’activation par le premier utilisateur des licences Microsoft Teams Exploratory est traitée comme la date anniversaire ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="388a0-206">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end-user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date.</span></span> <span data-ttu-id="388a0-207">Les utilisateurs de la licence Microsoft Teams Exploratory doivent passer à la licence payante avant cette date chaque année, conformément aux stratégies décrites dans cet article.</span><span class="sxs-lookup"><span data-stu-id="388a0-207">Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined in this article.</span></span>

<span data-ttu-id="388a0-208">Par exemple, si le premier utilisateur final active Microsoft Teams exploratoire le 19 juin 2020, les utilisateurs éligibles et tous les autres utilisateurs éligibles du locataire client doivent effectuer une conversion vers une licence payante avec Teams avant le 19 juin 2021.</span><span class="sxs-lookup"><span data-stu-id="388a0-208">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span>

> [!Note]
> <span data-ttu-id="388a0-209">Les clients seront désactivés et bloqués pour le démarrage d’une nouvelle licence d’évaluation de Exploratory pendant 3 mois après l’expiration de la licence d’évaluation Exploratory précédente.</span><span class="sxs-lookup"><span data-stu-id="388a0-209">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>
