---
title: Liste de contrôle de l’accès invité Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Utilisez cette liste de contrôle pour configurer l’accès invité dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04594f578d2375f69c38243251ee64506880d00e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753319"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="9cb2d-103">Liste de contrôle de l’accès invité Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9cb2d-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="9cb2d-104">Utilisez cette liste de vérification pour vous aider à activer et configurer l’accès invité dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cb2d-105">Il est possible que vous deviez attendre 24 heures pour que vos modifications soient prises en compte.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-105">You may have to wait up to 24 hours for your changes to take effect.</span></span> 



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="9cb2d-106">Étape 1 : activer l’accès invité pour le niveau de l’organisation au sein de l’Organisation</span><span class="sxs-lookup"><span data-stu-id="9cb2d-106">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="9cb2d-107">Pour activer l’accès invité, accédez au **Centre d’administration Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-107">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="9cb2d-108">Dans le centre d’administration Teams, sélectionnez > **accès invité aux**paramètres à l' **échelle de l’organisation**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-108">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="9cb2d-109">Activez l’option **autoriser l’accès invité dans Microsoft teams** **.**</span><span class="sxs-lookup"><span data-stu-id="9cb2d-109">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Capture d’écran montrant un exemple de bouton bascule pour les paramètres d’équipe](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="9cb2d-111">Dans la même page, activez ou désactivez les paramètres d' **appel**, de **réunion**et de **messagerie** pour les invités.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-111">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="9cb2d-112">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-112">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="9cb2d-113">Si vous utilisez les paramètres par défaut dans les groupes Azure Active Directory, SharePoint Online et Office 365, il est possible que vous ayez terminé de configurer l’accès invité.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-113">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="9cb2d-114">Dans ce cas, vous pouvez ignorer les étapes restantes.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-114">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="9cb2d-115">Si vous n’êtes pas sûr, ou si vous utilisez des paramètres personnalisés pour les groupes AAD, SharePoint Online ou Office 365, poursuivez le reste des étapes décrites dans cette liste de vérification.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-115">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="9cb2d-116">Étape 2 : configurer les paramètres d’entreprise pour les entreprises d’Azure AD</span><span class="sxs-lookup"><span data-stu-id="9cb2d-116">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="9cb2d-117">Connectez-vous au [portail Azure](https://portal.azure.com) en tant qu’administrateur client.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-117">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="9cb2d-118">Sélectionnez > **utilisateurs**d' **Azure Active Directory** > **paramètres utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-118">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="9cb2d-119">Sous **utilisateurs externes**, sélectionnez **gérer les paramètres de collaboration externes**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-119">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="9cb2d-120">Les **paramètres de collaboration externes** sont également disponibles à partir de la page **relations d’organisation** .</span><span class="sxs-lookup"><span data-stu-id="9cb2d-120">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="9cb2d-121">Dans Azure Active Directory, sous **Manage (gérer**), accédez à**paramètres**de l' **organisation** > .</span><span class="sxs-lookup"><span data-stu-id="9cb2d-121">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="9cb2d-122">Dans la page **paramètres de collaboration externe** , sélectionnez les stratégies que vous souhaitez activer.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-122">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="9cb2d-123">**Les autorisations des utilisateurs invités sont limitées**: cette stratégie détermine les autorisations des invités dans votre annuaire.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-123">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="9cb2d-124">Sélectionnez **Oui** pour bloquer les invités de certaines tâches d’annuaire, comme l’énumération des utilisateurs, des groupes ou d’autres ressources de l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-124">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="9cb2d-125">Sélectionnez **non** pour permettre aux invités d’accéder aux données de l’annuaire en tant qu’utilisateurs réguliers dans votre annuaire.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-125">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="9cb2d-126">Les **administrateurs et les utilisateurs du rôle d’invité invité peuvent inviter**: pour permettre aux administrateurs et aux utilisateurs du rôle « invité invité » d’inviter des invités, définissez cette stratégie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-126">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="9cb2d-127">**Les membres peuvent inviter**: pour autoriser les membres non administrateur de votre annuaire à inviter des invités, attribuez la valeur **Oui**à cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-127">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="9cb2d-128">Si vous définissez des **membres comme invités** sur **non** , puis activez l’accès invité aux groupes Office 365 et Microsoft Teams, l’administrateur peut contrôler les invitations des invités à votre annuaire.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-128">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="9cb2d-129">Lorsque les invités sont dans l’annuaire, ils peuvent être ajoutés à des équipes par des membres non administrateurs qui sont des propriétaires d’équipe.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-129">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="9cb2d-130">Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="9cb2d-130">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="9cb2d-131">Pour que l’accès invité puisse fonctionner du tout dans Teams, vous devez définir **les membres peuvent inviter** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-131">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
   - <span data-ttu-id="9cb2d-132">Les **invités peuvent inviter**: pour permettre aux invités d’inviter d’autres personnes, attribuez la valeur **Oui**à cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-132">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="9cb2d-133">Pour l’instant, Teams ne prend pas en charge le rôle d’invité invité, donc même si vous définissez les **invités peuvent inviter** sur **Oui**, les invités ne peuvent pas inviter d’autres invités dans Teams.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-133">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
   - <span data-ttu-id="9cb2d-134">**Activer le mot de passe unique pour les invités (** préversion) : pour plus d’informations sur la fonctionnalité de code secret unique, voir [authentification par code électronique unique (Preview) par courrier électronique](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="9cb2d-134">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="9cb2d-135">**Restrictions de collaboration**: pour plus d’informations sur l’autorisation ou le blocage d’invitations dans des domaines spécifiques, voir [autoriser ou bloquer les invitations d’utilisateurs B2B d’organisations spécifiques](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="9cb2d-135">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
      > [!NOTE]
      > <span data-ttu-id="9cb2d-136">Pour des restrictions de collaboration, voir [activer la collaboration externe B2B et gérer qui peut inviter des invités](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="9cb2d-136">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
<span data-ttu-id="9cb2d-137">Pour plus d’informations sur le contrôle de qui peut ajouter des invités, voir [Permettre une collaboration B2B externe et gérer qui peut inviter des invités](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="9cb2d-137">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="9cb2d-138">Étape 3 : configurer les groupes Office 365</span><span class="sxs-lookup"><span data-stu-id="9cb2d-138">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="9cb2d-139">Dans le centre d’administration 365 de Microsoft, accédez à **paramètres** > **des services & des** > compléments**Office 365**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-139">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="9cb2d-140">Veillez **à**ce que **les membres du groupe qui se trouvent en dehors de l’organisation aient accès au contenu du groupe** .</span><span class="sxs-lookup"><span data-stu-id="9cb2d-140">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="9cb2d-141">Si ce paramètre est désactivé, les invités ne seront pas en mesure d’accéder aux contenus du groupe.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-141">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="9cb2d-142">Assurez-vous que **les propriétaires de groupe peuvent ajouter des personnes en dehors de l’organisation aux groupes** est **activé**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-142">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="9cb2d-143">Si ce paramètre est désactivé, les propriétaires d’équipe ne peuvent pas ajouter de nouveaux invités.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-143">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="9cb2d-144">Ce paramètre doit être activé pour prendre en charge l’accès invité.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-144">At a minimum, this setting must be On to support guest access.</span></span>

     ![La capture d’écran indique le bouton bascule groupes d’Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="9cb2d-146">Pour obtenir des instructions détaillées sur la configuration de ces paramètres, voir [gérer l’accès invité dans les groupes office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) et [contrôler l’accès invité dans les groupes Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="9cb2d-146">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="9cb2d-147">Étape 4 : configurer le partage dans Office 365</span><span class="sxs-lookup"><span data-stu-id="9cb2d-147">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="9cb2d-148">Assurez-vous que les utilisateurs peuvent ajouter des invités.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-148">Make sure that users can add guests.</span></span> <span data-ttu-id="9cb2d-149">Voici comment procéder :</span><span class="sxs-lookup"><span data-stu-id="9cb2d-149">Here's how:</span></span>

1. <span data-ttu-id="9cb2d-150">Dans le centre d’administration 365 de Microsoft, accédez à **paramètres** > **sécurité & confidentialité**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-150">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Capture d’écran illustrant un exemple de paramètres de services](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="9cb2d-152">Dans **partage**, sélectionnez **modifier**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-152">In **Sharing**, select **Edit**.</span></span>

     ![La capture d’écran illustre un exemple de bascule paramètres de partage](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="9cb2d-154">Définissez **permettre aux utilisateurs d’ajouter des invités à cette organisation** **, puis**cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-154">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![La capture d’écran illustre un exemple de bascule paramètres de partage](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="9cb2d-156">Ce paramètre est équivalent au paramètre les **membres peuvent inviter** dans les **paramètres** > de l’utilisateur**les utilisateurs externes** d’Azure ad.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-156">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="9cb2d-157">Étape 5 : vérifier le paramètre de partage dans SharePoint</span><span class="sxs-lookup"><span data-stu-id="9cb2d-157">Step 5: Verify sharing setting in SharePoint</span></span>

<span data-ttu-id="9cb2d-158">C’est un peu d’une prétease Brain.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-158">This one's a bit of a brain teaser.</span></span> <span data-ttu-id="9cb2d-159">L’accès invité dans Teams ne fonctionne pas si le paramètre **ne pas autoriser le partage à l’extérieur de votre organisation** est sélectionné dans le centre d’administration SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-159">Guest access in Teams doesn't work if the **Don't allow sharing outside your organization** setting is selected in the SharePoint admin center.</span></span>

1. <span data-ttu-id="9cb2d-160">Connectez-vous au centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="9cb2d-161">Cliquez sur **Centre d’administration**, puis sélectionnez **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-161">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="9cb2d-162">Dans le centre d’administration SharePoint, sélectionnez **partage**.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-162">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="9cb2d-163">Assurez-vous que l’option ne pas autoriser le partage à l' **extérieur de votre organisation** n’est *pas* sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-163">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Capture d’écran illustrant un exemple de bouton bascule SparePoint en ligne.](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="9cb2d-165">Étape 6 : configurer les autorisations des utilisateurs invités</span><span class="sxs-lookup"><span data-stu-id="9cb2d-165">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="9cb2d-166">Dans l’application Teams, au niveau de l’équipe individuelle, configurez des autorisations d’invité pour contrôler si les invités peuvent créer, mettre à jour ou supprimer des canaux.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-166">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="9cb2d-167">Les administrateurs des équipes et les propriétaires d’équipe peuvent configurer ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="9cb2d-167">Teams admins as well as team owners can configure these settings.</span></span>

![Capture d’écran montrant un exemple de bascule des paramètres d’équipe/canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="9cb2d-169">Pour en savoir plus sur l’accès invité, voir [accès invité dans Microsoft teams](guest-access.md) et [activation ou désactivation de l’accès invité à Microsoft teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="9cb2d-169">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="9cb2d-170">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="9cb2d-170">Troubleshooting</span></span>

<span data-ttu-id="9cb2d-171">Si vous rencontrez des problèmes pour configurer l’accès invité ou ajouter des invités dans Microsoft Teams, utilisez les ressources suivantes pour vous aider :</span><span class="sxs-lookup"><span data-stu-id="9cb2d-171">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="9cb2d-172">Résoudre les problèmes liés à l’accès invité dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="9cb2d-172">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="9cb2d-173">Résolution des problèmes dans teams</span><span class="sxs-lookup"><span data-stu-id="9cb2d-173">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



