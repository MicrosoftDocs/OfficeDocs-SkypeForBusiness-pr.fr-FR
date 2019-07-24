---
title: Liste de contrôle de l’accès invité Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Utilisez cette liste de contrôle pour configurer l’accès invité dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3142a30a5131ed18a76a130c420b3af214c5190b
ms.sourcegitcommit: 67282b5f2f1aac3e675c4a485f4846deba15deb4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2019
ms.locfileid: "35841375"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="af83e-103">Liste de vérification de l’accès invité teams</span><span class="sxs-lookup"><span data-stu-id="af83e-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="af83e-104">Utilisez cette liste de vérification pour vous aider à activer et configurer la fonctionnalité d’accès invité dans Microsoft Teams, conformément aux préférences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="af83e-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

> [!NOTE] 
> <span data-ttu-id="af83e-105">Pour les restrictions de collaboration [, voir Activer la collaboration externe B2B et gérer qui peut inviter des invités](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="af83e-105">For collaboration restrictions see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="af83e-106">Comprendre les limites applicables aux invités</span><span class="sxs-lookup"><span data-stu-id="af83e-106">Understand the limitations for guests</span></span>

<span data-ttu-id="af83e-107">L’interface des invités a des limitations par conception.</span><span class="sxs-lookup"><span data-stu-id="af83e-107">The guest experience has limitations by design.</span></span> <span data-ttu-id="af83e-108">Assurez-vous de bien comprendre le fonctionnement des invités afin de ne pas tenter de résoudre un problème qui ne pose pas de problème.</span><span class="sxs-lookup"><span data-stu-id="af83e-108">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="af83e-109">Par exemple, voici une liste des fonctionnalités qui ne sont pas disponibles pour un invité dans Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="af83e-109">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="af83e-110">OneDrive entreprise</span><span class="sxs-lookup"><span data-stu-id="af83e-110">OneDrive for Business</span></span>
- <span data-ttu-id="af83e-111">Recherche de personnes en dehors de teams</span><span class="sxs-lookup"><span data-stu-id="af83e-111">People search outside of Teams</span></span>
- <span data-ttu-id="af83e-112">Calendrier, réunions planifiées ou détails de la réunion</span><span class="sxs-lookup"><span data-stu-id="af83e-112">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="af83e-113">PSTN</span><span class="sxs-lookup"><span data-stu-id="af83e-113">PSTN</span></span>
- <span data-ttu-id="af83e-114">Organigramme hiérarchique</span><span class="sxs-lookup"><span data-stu-id="af83e-114">Organization chart</span></span>
- <span data-ttu-id="af83e-115">Créer ou réviser une équipe</span><span class="sxs-lookup"><span data-stu-id="af83e-115">Create or revise a team</span></span>
- <span data-ttu-id="af83e-116">Rechercher une équipe</span><span class="sxs-lookup"><span data-stu-id="af83e-116">Browse for a team</span></span>
- <span data-ttu-id="af83e-117">Télécharger des fichiers dans une conversation de personne à personne</span><span class="sxs-lookup"><span data-stu-id="af83e-117">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="af83e-118">Les invités peuvent toujours Rechercher et Rechercher des utilisateurs (en dehors de leur équipe) s’ils connaissent l’ID de courrier complet de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="af83e-118">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="af83e-119">Pour éviter ce problème, les administrateurs informatiques peuvent utiliser les modèles tels que la recherche dans l' [Annuaire](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) et permettent de limiter les invités à leur propre gal virtuelle.</span><span class="sxs-lookup"><span data-stu-id="af83e-119">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="af83e-120">Pour plus d’informations, reportez-vous à [l’interface utilisateur](guest-experience.md) et [accès invité dans les groupes Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="af83e-120">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="af83e-121">Accès invité et accès externe (fédération)</span><span class="sxs-lookup"><span data-stu-id="af83e-121">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> <span data-ttu-id="af83e-122">Pour le moment, Microsoft Teams ne prend pas en charge le rôle d’invité invité.</span><span class="sxs-lookup"><span data-stu-id="af83e-122">Currently, Microsoft Teams does not support the guest inviter role.</span></span> <span data-ttu-id="af83e-123">Au minimum, le bouton bascule «les membres peuvent inviter» doit être défini sur «Oui» pour que l’accès invité puisse travailler dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="af83e-123">At a minimum the "members can invite" toggle must be set to "Yes" for guest access to work in Microsoft Teams.</span></span> <span data-ttu-id="af83e-124">Si vous définissez «les membres peuvent inviter» sur «non», puis activez l’accès invité aux groupes Office 365 et Microsoft Teams, les administrateurs peuvent contrôler les invitations invitées dans votre annuaire.</span><span class="sxs-lookup"><span data-stu-id="af83e-124">If you set "members can invite" to "No" and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="af83e-125">Lorsque les invités sont dans l’annuaire, ils peuvent être ajoutés à des équipes par des membres non administrateurs qui sont des propriétaires d’équipe.</span><span class="sxs-lookup"><span data-stu-id="af83e-125">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="af83e-126">Si vos invités voient des erreurs de licence</span><span class="sxs-lookup"><span data-stu-id="af83e-126">If your guests are seeing license errors</span></span>

<span data-ttu-id="af83e-127">L’accès invité dans Microsoft teams utilise Azure Active Directory (Azure AD) Business to Business (B2B) et son modèle de licence.</span><span class="sxs-lookup"><span data-stu-id="af83e-127">Guest access in Microsoft Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="af83e-128">Si vous rencontrez des erreurs de gestion des licences, veillez à lire les [recommandations](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) en matière de gestion des licences interentreprises pour comprendre les exigences en matière de licences dont dispose votre organisation afin que vos utilisateurs puissent inviter des invités à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="af83e-128">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="af83e-129">Quelques points à garder à l’esprit:</span><span class="sxs-lookup"><span data-stu-id="af83e-129">A few things to remember:</span></span>

- <span data-ttu-id="af83e-130">Les invités sont des utilisateurs extérieurs à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="af83e-130">Guests are users outside your organization.</span></span> <span data-ttu-id="af83e-131">Vos employés, entrepreneurs et prestataires de site, et ainsi de suite ne peuvent pas être ajoutés comme invités.</span><span class="sxs-lookup"><span data-stu-id="af83e-131">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="af83e-132">Il en va de même pour vos affiliés.</span><span class="sxs-lookup"><span data-stu-id="af83e-132">The same applies to your affiliates.</span></span>
- <span data-ttu-id="af83e-133">Les licences invité sont comptabilisées au niveau de l’organisation d’invitation.</span><span class="sxs-lookup"><span data-stu-id="af83e-133">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="af83e-134">Tenez compte de ce qui suit lorsque vous calculez le nombre de licences dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="af83e-134">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="af83e-135">Les licences sont comptabilisées au niveau de votre organisation, que les invités invités proviennent d’un autre client Office 365 ou utilisent leurs adresses de messagerie personnelles.</span><span class="sxs-lookup"><span data-stu-id="af83e-135">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="af83e-136">□ Étape 1: configurer les paramètres d’Azure AD Business-to-Business</span><span class="sxs-lookup"><span data-stu-id="af83e-136">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="af83e-137">Connectez-vous au [portail Azure](https://portal.azure.com) en tant qu’administrateur client.</span><span class="sxs-lookup"><span data-stu-id="af83e-137">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="af83e-138">Sélectionnez > **utilisateurs**d' **Azure Active Directory** > **paramètres utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="af83e-138">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="af83e-139">Sous **utilisateurs externes**, sélectionnez **gérer les paramètres de collaboration externes**.</span><span class="sxs-lookup"><span data-stu-id="af83e-139">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="af83e-140">Les **paramètres de collaboration externes** sont également disponibles à partir de la page **relations d’organisation** .</span><span class="sxs-lookup"><span data-stu-id="af83e-140">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="af83e-141">Dans Azure Active Directory, sous **Manage (gérer**), accédez à**paramètres**de l' **organisation** > .</span><span class="sxs-lookup"><span data-stu-id="af83e-141">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="af83e-142">Dans la page **paramètres de collaboration externe** , sélectionnez les stratégies que vous souhaitez activer.</span><span class="sxs-lookup"><span data-stu-id="af83e-142">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

   ![Paramètres de collaboration externes](media/control-who-to-invite.png)

  - <span data-ttu-id="af83e-144">**Les autorisations des utilisateurs invités sont limitées**: cette stratégie détermine les autorisations des invités dans votre annuaire.</span><span class="sxs-lookup"><span data-stu-id="af83e-144">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="af83e-145">Sélectionnez **Oui** pour bloquer les invités de certaines tâches d’annuaire, comme l’énumération des utilisateurs, des groupes ou d’autres ressources de l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="af83e-145">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="af83e-146">Sélectionnez **non** pour permettre aux invités d’accéder aux données de l’annuaire en tant qu’utilisateurs réguliers dans votre annuaire.</span><span class="sxs-lookup"><span data-stu-id="af83e-146">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="af83e-147">Les **administrateurs et les utilisateurs du rôle d’invité invité peuvent inviter**: pour permettre aux administrateurs et aux utilisateurs du rôle «invité invité» d’inviter des invités, définissez cette stratégie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="af83e-147">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="af83e-148">**Les membres peuvent inviter**: pour autoriser les membres non administrateur de votre annuaire à inviter des invités, attribuez la valeur **Oui**à cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="af83e-148">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="af83e-149">Si vous définissez des **membres comme invités** sur **non** , puis activez l’accès invité aux groupes Office 365 et Microsoft Teams, l’administrateur peut contrôler les invitations des invités à votre annuaire.</span><span class="sxs-lookup"><span data-stu-id="af83e-149">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="af83e-150">Lorsque les invités sont dans l’annuaire, ils peuvent être ajoutés à des équipes par des membres non administrateurs qui sont des propriétaires d’équipe.</span><span class="sxs-lookup"><span data-stu-id="af83e-150">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="af83e-151">Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="af83e-151">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
   
   - <span data-ttu-id="af83e-152">Les **invités peuvent inviter**: pour permettre aux invités d’inviter d’autres personnes, attribuez la valeur **Oui**à cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="af83e-152">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="af83e-153">**Activer le mot de passe unique pour les invités (** préversion): pour plus d’informations sur la fonctionnalité de code secret unique, voir [authentification par code électronique unique (Preview) par courrier électronique](one-time-passcode.md).</span><span class="sxs-lookup"><span data-stu-id="af83e-153">**Enable Email One-Time Passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](one-time-passcode.md).</span></span>
   - <span data-ttu-id="af83e-154">**Restrictions de collaboration**: pour plus d’informations sur l’autorisation ou le blocage d’invitations dans des domaines spécifiques, voir [autoriser ou bloquer les invitations d’utilisateurs B2B d’organisations spécifiques](allow-deny-list.md).</span><span class="sxs-lookup"><span data-stu-id="af83e-154">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](allow-deny-list.md).</span></span>

## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="af83e-155">□ Étape 2: configurer les groupes Office 365</span><span class="sxs-lookup"><span data-stu-id="af83e-155">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="af83e-156">Dans le centre d’administration 365 de Microsoft, accédez à **paramètres** > **des services & des** > compléments**Office 365**.</span><span class="sxs-lookup"><span data-stu-id="af83e-156">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="af83e-157">Veillez à **ce que les membres du groupe qui se trouvent en dehors de l’organisation aient accès au contenu du groupe** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="af83e-157">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="af83e-158">Si ce paramètre est désactivé, les invités ne seront pas en mesure d’accéder aux contenus du groupe.</span><span class="sxs-lookup"><span data-stu-id="af83e-158">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="af83e-159">Assurez-vous que **les propriétaires de groupe peuvent ajouter des personnes en dehors de l’organisation aux groupes** est **activé**.</span><span class="sxs-lookup"><span data-stu-id="af83e-159">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="af83e-160">Si ce paramètre est désactivé, les propriétaires d’équipe ne peuvent pas ajouter de nouveaux invités.</span><span class="sxs-lookup"><span data-stu-id="af83e-160">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="af83e-161">Ce paramètre doit être activé pour prendre en charge l’accès invité.</span><span class="sxs-lookup"><span data-stu-id="af83e-161">At a minimum, this setting must be On to support guest access.</span></span>

     ![La capture d’écran indique le bouton bascule groupes d’Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="af83e-163">Pour obtenir des instructions détaillées sur la configuration de ces paramètres, voir [gérer l’accès invité dans les groupes office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) et [contrôler l’accès invité dans les groupes Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="af83e-163">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="af83e-164">□ Étape 3: activer l’accès invité au niveau du client</span><span class="sxs-lookup"><span data-stu-id="af83e-164">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="af83e-165">Au minimum, vous devez activer l’accès invité de Microsoft teams dans le **Centre d’administration Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="af83e-165">At a minimum, you must turn on guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="af83e-166">Dans le centre d’administration Teams, sélectionnez > **accès invité aux**paramètres à l' **échelle de l’organisation**.</span><span class="sxs-lookup"><span data-stu-id="af83e-166">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="af83e-167">Activez l’option **autoriser l’accès invité dans Microsoft teams** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="af83e-167">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Capture d’écran montrant un exemple de bouton bascule pour les paramètres d’équipe](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="af83e-169">Dans la même page, configurez les autres paramètres invités dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="af83e-169">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="af83e-170">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="af83e-170">Click **Save**.</span></span>

<span data-ttu-id="af83e-171">Pour obtenir des instructions détaillées, voir [activer ou désactiver l’accès invité à Microsoft teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="af83e-171">For detailed instructions, see [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="af83e-172">□ Étape 4: configurer le partage dans Office 365</span><span class="sxs-lookup"><span data-stu-id="af83e-172">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="af83e-173">Assurez-vous que les utilisateurs peuvent ajouter des invités.</span><span class="sxs-lookup"><span data-stu-id="af83e-173">Make sure that users can add guests.</span></span> <span data-ttu-id="af83e-174">Voici comment procéder:</span><span class="sxs-lookup"><span data-stu-id="af83e-174">Here's how:</span></span>

1. <span data-ttu-id="af83e-175">Dans le centre d’administration 365 de Microsoft, accédez à **paramètres** > **sécurité & confidentialité**.</span><span class="sxs-lookup"><span data-stu-id="af83e-175">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Capture d’écran illustrant un exemple de paramètres de services](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="af83e-177">Dans **partage**, sélectionnez **modifier**.</span><span class="sxs-lookup"><span data-stu-id="af83e-177">In **Sharing**, select **Edit**.</span></span>

     ![La capture d’écran illustre un exemple de bascule paramètres de partage](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="af83e-179">Définissez **permettre aux utilisateurs d’ajouter des invités à cette organisation** , puis cliquez sur **Enregistrer**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="af83e-179">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![La capture d’écran illustre un exemple de bascule paramètres de partage](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="af83e-181">Ce paramètre est équivalent au paramètre les **membres peuvent inviter** dans les **paramètres** > de l’utilisateur**les utilisateurs externes** d’Azure ad.</span><span class="sxs-lookup"><span data-stu-id="af83e-181">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="af83e-182">□ L’étape 5: vérifier le paramètre de partage dans SharePoint</span><span class="sxs-lookup"><span data-stu-id="af83e-182">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="af83e-183">Connectez-vous au centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af83e-183">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="af83e-184">Cliquez sur **Centre d’administration**, puis sélectionnez **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="af83e-184">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="af83e-185">Dans le centre d’administration SharePoint, sélectionnez **partage**.</span><span class="sxs-lookup"><span data-stu-id="af83e-185">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="af83e-186">Assurez-vous que l’option ne pas autoriser le partage à l' **extérieur de votre organisation** n’est *pas* sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="af83e-186">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Capture d’écran illustrant un exemple de bouton bascule SparePoint en ligne.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="af83e-188">□ Étape 6: activer des paramètres spécifiques pour les canaux</span><span class="sxs-lookup"><span data-stu-id="af83e-188">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="af83e-189">Dans l’application Teams, au niveau de l’équipe individuelle, configurez des autorisations d’invité pour permettre aux invités de créer, mettre à jour et supprimer des canaux.</span><span class="sxs-lookup"><span data-stu-id="af83e-189">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="af83e-190">Outre les administrateurs, les propriétaires d’équipe peuvent configurer ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="af83e-190">In addition to admins,  team owners can configure this setting.</span></span>

![Capture d’écran montrant un exemple de bascule des paramètres d’équipe/canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="af83e-192">Pour plus d’informations, y compris des vidéos sur les procédures, voir [accès invité dans Microsoft teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="af83e-192">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="af83e-193">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="af83e-193">Troubleshooting</span></span>

<span data-ttu-id="af83e-194">Si vous rencontrez des problèmes lors de l’ajout d’invités dans Microsoft Teams, voir le [Guide de résolution des problèmes d’accès invité](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="af83e-194">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


