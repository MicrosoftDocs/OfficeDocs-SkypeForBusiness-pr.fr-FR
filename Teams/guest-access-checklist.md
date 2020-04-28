---
title: Liste de contrôle de l’accès invité Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: En savoir plus sur l’activation et la configuration de l’accès invité dans Microsoft teams en tant qu’administrateur général ou Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 04627c74528972aad69b1e810e222f55cae49588
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902579"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="5541b-103">Liste de contrôle de l’accès invité Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5541b-103">Microsoft Teams guest access checklist</span></span>
=========================================

<span data-ttu-id="5541b-104">Utilisez cette liste de vérification pour activer et configurer l’accès invité dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5541b-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="5541b-105">Pour apporter ces modifications, vous devez être un administrateur général ou un administrateur Teams.</span><span class="sxs-lookup"><span data-stu-id="5541b-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5541b-106">Il est possible que vous deviez patienter quelques heures avant que les modifications soient prises en compte.</span><span class="sxs-lookup"><span data-stu-id="5541b-106">You may have to wait a couple of hours for your changes to take effect.</span></span> 

<span data-ttu-id="5541b-107">Regardez cette courte vidéo (5:31 minutes) pour découvrir comment activer l’accès invité dans Microsoft 365, y compris les équipes.</span><span class="sxs-lookup"><span data-stu-id="5541b-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="5541b-108">Étape 1 : activer l’accès invité au niveau de l’organisation à l’échelle de l’organisation</span><span class="sxs-lookup"><span data-stu-id="5541b-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="5541b-109">Pour activer l’accès invité, accédez au **Centre d’administration Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="5541b-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="5541b-110">Dans le Centre d'administration Teams, sélectionnez **paramètres Org-wide** > **accès invité**.</span><span class="sxs-lookup"><span data-stu-id="5541b-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="5541b-111">Mettre le bouton bascule**Autoriser l’accès invité dans Microsoft Teams** sur **On**.</span><span class="sxs-lookup"><span data-stu-id="5541b-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Capture d’écran montrant un exemple de commutateurs de paramètres de Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="5541b-113">Sur cette même page, activez ou désactivez **Appel**, **Réunion** et **Messagerie** pour les invités.</span><span class="sxs-lookup"><span data-stu-id="5541b-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="5541b-114">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5541b-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="5541b-115">Si vous utilisez les paramètres par défaut dans les groupes Azure Active Directory, SharePoint Online et Microsoft 365, vous pouvez être amené à configurer l’accès invité.</span><span class="sxs-lookup"><span data-stu-id="5541b-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Microsoft 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="5541b-116">Dans ce cas, vous pouvez ignorer le reste des étapes.</span><span class="sxs-lookup"><span data-stu-id="5541b-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="5541b-117">Si vous n’êtes pas sûr, ou si vous utilisez des paramètres personnalisés pour les groupes AAD, SharePoint Online ou Microsoft 365, poursuivez le reste des étapes décrites dans cette liste de vérification.</span><span class="sxs-lookup"><span data-stu-id="5541b-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Microsoft 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="5541b-118">Étape 2 : configurer les paramètres interentreprises d'Azure AD</span><span class="sxs-lookup"><span data-stu-id="5541b-118">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="5541b-119">Il s’agit des paramètres Azure AD qui prennent en charge l’accès invité dans Teams.</span><span class="sxs-lookup"><span data-stu-id="5541b-119">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="5541b-120">Une fois ces paramètres configurés, vous pouvez [ajouter](add-guests.md) et [gérer les invités](manage-guests.md) dans Teams.</span><span class="sxs-lookup"><span data-stu-id="5541b-120">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="5541b-121">Connectez-vous au [Portail Azure](https://portal.azure.com) entant qu’administrateur client.</span><span class="sxs-lookup"><span data-stu-id="5541b-121">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="5541b-122">Sélectionnez **Azure Active Directory** > **Utilisateurs** > **Paramètres utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="5541b-122">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="5541b-123">Sous **Utilisateurs externes**, sélectionnez **Gérer les paramètres de collaboration externe**.</span><span class="sxs-lookup"><span data-stu-id="5541b-123">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="5541b-124">Les **Paramètres de collaboration externe** sont également disponibles dans la page **Relations organisationnelles**.</span><span class="sxs-lookup"><span data-stu-id="5541b-124">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="5541b-125">Dans Azure Active Directory, sous **Gérer**, accédez à **Relations organisationnelles** > **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="5541b-125">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="5541b-126">Dans la page **Paramètres de collaboration externe**, sélectionnez les stratégies que vous voulez activer.</span><span class="sxs-lookup"><span data-stu-id="5541b-126">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="5541b-127">**Les autorisations des utilisateurs invités sont limitées** : cette stratégie détermine les autorisations des invités de votre annuaire.</span><span class="sxs-lookup"><span data-stu-id="5541b-127">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="5541b-128">Sélectionnez **Oui** pour bloquer les invités de certaines tâches d’annuaire, comme l’énumération des utilisateurs, des groupes ou d’autres ressources d’annuaire.</span><span class="sxs-lookup"><span data-stu-id="5541b-128">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="5541b-129">Sélectionnez **Non** pour donner aux invités les mêmes accès aux données d’annuaire que les utilisateurs réguliers dans votre annuaire.</span><span class="sxs-lookup"><span data-stu-id="5541b-129">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="5541b-130">**Les administrateurs et les utilisateurs membres du rôle Inviteur d’invités peuvent envoyer des invitations** : pour autoriser les administrateurs et les utilisateurs du rôle « Inviteur d’invités » à inviter des invités, attribuez la valeur **Oui**à cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="5541b-130">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="5541b-131">**Les membres peuvent envoyer des invitations** : pour autoriser les membres non administrateurs de votre annuaire à convier des invités, attribuez la valeur **Oui** (recommandé) à cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="5541b-131">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="5541b-132">Si vous préférez que seuls les administrateurs puissent ajouter des invités, vous pouvez affecter la valeur **Non**à cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="5541b-132">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="5541b-133">Ne pas oublier que le paramètre **Non** limite l’expérience invité aux propriétaires d’équipes non administrateurs ; ils ne pourront ajouter des invités dans Teams que si ceux-ci ont déjà été ajoutés par l'administrateur dans Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5541b-133">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="5541b-134">**Les invités peuvent inviter** : pour autoriser les invités à inviter d’autres personnes, configurez cette stratégie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="5541b-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="5541b-135">Actuellement, Teams ne prend pas en charge le rôle d’inviteur invité. Par conséquent, même si vous définissez **Les invités peuvent inviter** sur **Oui**, les invités ne peuvent pas avoir d’autres invités dans Teams.</span><span class="sxs-lookup"><span data-stu-id="5541b-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="5541b-136">**Activer le code secret à usage unique du courrier pour les invités (préversion)** : pour plus d’informations sur la fonctionnalité code secret unique, consultez[Authentification par code secret unique (préversion)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="5541b-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="5541b-137">**Restrictions de collaboration** : pour plus d’informations sur l’autorisation ou le blocage d’invitations à des domaines spécifiques, consultez [Autoriser ou bloquer des invitations à des utilisateurs B2B d’organisations spécifiques](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="5541b-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="5541b-138">Pour plus d’informations sur les restrictions de collaboration, consultez [Activer la collaboration externe B2B et gérer les utilisateurs pouvant inviter des invités](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="5541b-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
    <span data-ttu-id="5541b-139">Pour plus d’informations sur le contrôle de qui peut ajouter des invités, voir [Permettre une collaboration B2B externe et gérer qui peut inviter des invités](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="5541b-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-microsoft-365-groups"></a><span data-ttu-id="5541b-140">Étape 3 : configurer les groupes Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5541b-140">Step 3: Configure Microsoft 365 Groups</span></span>

1. <span data-ttu-id="5541b-141">Dans le centre d’administration 365 Microsoft, accédez à**paramètres**des **paramètres** > , cliquez sur **services**, puis sélectionnez **groupes Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="5541b-141">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Services**, and then select **Microsoft 365 Groups**.</span></span>

     ![Capture d’écran montrant les paramètres des groupes Microsoft 365](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="5541b-143">Assurez-vous que la case à cocher **Permettre aux membres du groupe extérieurs à l’organisation d’accéder au contenu du groupe** est activée.</span><span class="sxs-lookup"><span data-stu-id="5541b-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="5541b-144">Si ce paramètre n’est pas sélectionné, les invités ne pourront pas accéder au contenu du groupe.</span><span class="sxs-lookup"><span data-stu-id="5541b-144">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![Capture d’écran montrant les paramètres des groupes Microsoft 365](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="5541b-146">Assurez-vous que la case à cocher **Permettre aux propriétaires de groupe d’ajouter des personnes en dehors de l’organisation aux groupes** est activée.</span><span class="sxs-lookup"><span data-stu-id="5541b-146">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="5541b-147">Si ce paramètre n’est pas sélectionné, les propriétaires d’équipe ne peuvent pas ajouter de nouveaux invités.</span><span class="sxs-lookup"><span data-stu-id="5541b-147">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="5541b-148">Au minimum, ce paramètre doit être activé pour prendre en charge l’accès invité.</span><span class="sxs-lookup"><span data-stu-id="5541b-148">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="5541b-149">Pour obtenir des instructions détaillées sur la configuration de ces paramètres, voir [gérer l’accès invité dans les groupes microsoft 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) et [contrôler l’accès invité dans les groupes Microsoft 365](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span><span class="sxs-lookup"><span data-stu-id="5541b-149">For detailed instructions about configuring these settings, see [Manage guest access in Microsoft 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Microsoft 365 Groups](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="5541b-150">Étape 4 : configurer le partage dans Office 365</span><span class="sxs-lookup"><span data-stu-id="5541b-150">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="5541b-151">Assurez-vous que les utilisateurs peuvent ajouter des invités.</span><span class="sxs-lookup"><span data-stu-id="5541b-151">Make sure that users can add guests.</span></span> <span data-ttu-id="5541b-152">Voici comment procéder :</span><span class="sxs-lookup"><span data-stu-id="5541b-152">Here's how:</span></span>

1. <span data-ttu-id="5541b-153">Dans le Centre d’administration Microsoft 365, accédez à **Paramètres** > **Paramètres**, cliquez sur **Sécurité et confidentialité**, puis sélectionnez **Partage**.</span><span class="sxs-lookup"><span data-stu-id="5541b-153">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![Capture d’écran montrant un exemple de paramètres de services](media/guest-access-checklist-security-privacy-settings.png)
 
2. <span data-ttu-id="5541b-155">Activez la case à cocher **Permettre aux utilisateurs d’ajouter des invités à cette organisation**, puis cliquez sur **Enregistrer les modifications**.</span><span class="sxs-lookup"><span data-stu-id="5541b-155">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![Capture d’écran montrant un exemple de commutateurs de paramètres de partage](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > <span data-ttu-id="5541b-157">Ce paramètre équivaut au paramètre **Les membres peuvent inviter** dans **Paramètres de l’utilisateur** > **Utilisateurs externes** dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5541b-157">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="5541b-158">Étape 5 : vérifier le paramètre de partage dans SharePoint</span><span class="sxs-lookup"><span data-stu-id="5541b-158">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="5541b-159">Connectez-vous au Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5541b-159">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="5541b-160">Sous **Centres d’administration**, sélectionnez **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="5541b-160">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="5541b-161">Dans le nouveau Centre d’administration SharePoint, sous**Sites** sélectionnez **sites actifs**.</span><span class="sxs-lookup"><span data-stu-id="5541b-161">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![Activer les sites dans le Centre d’administration SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="5541b-163">Sélectionnez le site, puis cliquez sur **Partage**.</span><span class="sxs-lookup"><span data-stu-id="5541b-163">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="5541b-164">Assurez-vous que l’option **Tout le monde** ou **Invités nouveaux et existants** est activée.</span><span class="sxs-lookup"><span data-stu-id="5541b-164">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![Capture d’écran montrant un exemple de commutateurs de paramètres de SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="5541b-166">Étape 6 : configurer les autorisations d’utilisateur invité</span><span class="sxs-lookup"><span data-stu-id="5541b-166">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="5541b-167">Dans l’application Teams, au niveau de l’équipe, configurez des autorisations invité qui contrôlent la possibilité pour les invités de créer, mettre à jour ou supprimer des canaux.</span><span class="sxs-lookup"><span data-stu-id="5541b-167">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="5541b-168">Les administrateurs Teams et les propriétaires d’équipe peuvent configurer ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="5541b-168">Teams admins as well as team owners can configure these settings.</span></span>

![Capture d’écran montrant un exemple de commutateurs de paramètres d’équipe/canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="5541b-170">Pour en savoir plus sur l’accès invité, consultez [l’accès invité dans Teams](guest-access.md) et [Activer ou désactiver l’accès invité à Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="5541b-170">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="5541b-171">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="5541b-171">Troubleshooting</span></span>

<span data-ttu-id="5541b-172">Si vous rencontrez des problèmes lors de la configuration de l’accès invité ou de l’ajout d’invités dans Teams, utilisez ces ressources pour vous aider :</span><span class="sxs-lookup"><span data-stu-id="5541b-172">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="5541b-173">Résolution des problèmes liés à l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5541b-173">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="5541b-174">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="5541b-174">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
