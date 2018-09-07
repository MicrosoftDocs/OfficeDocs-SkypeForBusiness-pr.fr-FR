---
title: Liste de vérification Microsoft équipes invité Access
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Utilisez cette liste de vérification pour vous aider à configurer l’accès invité dans Microsoft Access d’invité équipes.
localization_priority: Priority
search.appverid: MET150
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0b8d8e4f9563cb7087b28c4adc77e6db4d6d335
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850176"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="23dad-103">Liste de vérification de l’accès invité équipes</span><span class="sxs-lookup"><span data-stu-id="23dad-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="23dad-104">Utilisez cette liste de vérification pour vous aider à activer et configurer la fonctionnalité d’accès invité dans Microsoft Teams selon les préférences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="23dad-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>




## <a name="--enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="23dad-105">□ Activer invité l’accès au niveau du client</span><span class="sxs-lookup"><span data-stu-id="23dad-105">□  Enable guest access at the tenant level</span></span>

<span data-ttu-id="23dad-106">Au minimum, vous devez activer Microsoft Teams pour tous les utilisateurs du type de licence **invité**.</span><span class="sxs-lookup"><span data-stu-id="23dad-106">At a minimum, you must turn on Microsoft Teams for all users of the license type **Guest**.</span></span> <span data-ttu-id="23dad-107">Pour obtenir des instructions détaillées, voir [Activer ou désactiver l’accès invité aux équipes de Microsoft](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="23dad-107">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

![Capture d’écran montre un exemple d’un bouton Paramètres d’équipes](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a><span data-ttu-id="23dad-109">□ Activer des paramètres spécifiques pour les canaux</span><span class="sxs-lookup"><span data-stu-id="23dad-109">□ Enable specific settings for channels</span></span> 
<span data-ttu-id="23dad-110">Dans l’application d’équipes, au niveau équipe individuels, configurez des autorisations invité afin que les invités peuvent créer, mettre à jour et supprimer des chaînes.</span><span class="sxs-lookup"><span data-stu-id="23dad-110">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="23dad-111">En plus des administrateurs, les propriétaires de l’équipe peuvent configurer ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="23dad-111">In addition to admins,  team owners can configure this setting.</span></span>

![Capture d’écran montre un exemple d’un bouton bascule des paramètres d’équipe/de canal](media/guest-access-checklist-TeamsSettings2.png)


<span data-ttu-id="23dad-113">Pour plus d’informations, notamment des vidéos de procédures, voir [accès invité dans les équipes Microsoft](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="23dad-113">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>



## <a name="--configure-sharing-in-office-365"></a><span data-ttu-id="23dad-114">□ Configurer le partage dans Office 365</span><span class="sxs-lookup"><span data-stu-id="23dad-114">□  Configure Sharing in Office 365</span></span> 

<span data-ttu-id="23dad-115">□ Assurez-vous que les utilisateurs peuvent ajouter des invités.</span><span class="sxs-lookup"><span data-stu-id="23dad-115">□ Make sure users can add guests.</span></span> <span data-ttu-id="23dad-116">Voici comment :</span><span class="sxs-lookup"><span data-stu-id="23dad-116">Here's how:</span></span>

1. <span data-ttu-id="23dad-117">Dans le centre d’administration Office 365, accédez à **paramètres** > **sécurité et confidentialité**.</span><span class="sxs-lookup"><span data-stu-id="23dad-117">In the Office 365 admin center, go to **Settings** > **Security & privacy**.</span></span>
<span data-ttu-id="23dad-118">![Capture d’écran montre un exemple de paramètres de Services](media/guest-access-checklist-Office365Admin_Services_addins.png)</span><span class="sxs-lookup"><span data-stu-id="23dad-118">![Screenshot shows an example of a Services settings](media/guest-access-checklist-Office365Admin_Services_addins.png)</span></span>
1. <span data-ttu-id="23dad-119">Dans **partage**, sélectionnez **Modifier**. ![Capture d’écran montre un exemple d’un bouton de modifier des paramètres de partage](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span><span class="sxs-lookup"><span data-stu-id="23dad-119">In **Sharing**, select **Edit**.![Screenshot shows an example of a Sharing Settings edit button](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span></span>
2. <span data-ttu-id="23dad-120">La valeur **permettent aux utilisateurs ajouter de nouveaux invités à cette organisation** **sur**, puis cliquez sur **Enregistrer**. ![Capture d’écran montre un exemple d’un bouton bascule le partage des paramètres](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span><span class="sxs-lookup"><span data-stu-id="23dad-120">Set **Let users add new guests to this organization** to **On**, and then click **Save**.![Screenshot shows an example of a Sharing Settings toggle](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span></span>
 

 > [!NOTE]
> <span data-ttu-id="23dad-121">Ce paramètre est équivalent au paramètre **d’Inviter des membres** dans les paramètres utilisateur > utilisateurs externes dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="23dad-121">This setting is equivalent to the **Members can invite** setting in  User settings > External users  in Azure AD.</span></span>  




## <a name="-configure-office-365-groups"></a><span data-ttu-id="23dad-122">□ Configurer des groupes d’Office 365</span><span class="sxs-lookup"><span data-stu-id="23dad-122">□ Configure Office 365 Groups</span></span>

<span data-ttu-id="23dad-123">Dans le centre d’administration Office 365, accédez à **paramètres** > **Services et compléments** > **Groupes d’Office 365**.</span><span class="sxs-lookup"><span data-stu-id="23dad-123">In the Office 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>

<span data-ttu-id="23dad-124">Assurez-vous que **laisser les membres du groupe en dehors du contenu de groupe organisation access** est **activé**.</span><span class="sxs-lookup"><span data-stu-id="23dad-124">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="23dad-125">Si ce paramètre est désactivé, les invités sera en mesure d’accéder au contenu de groupe.</span><span class="sxs-lookup"><span data-stu-id="23dad-125">If this setting is turned off, guests won't be able to access any group content.</span></span>

<span data-ttu-id="23dad-126">Assurez-vous que **vous permettent d’ajouter des personnes à l’extérieur de l’organisation aux groupes de propriétaires de groupe** est **activé**.</span><span class="sxs-lookup"><span data-stu-id="23dad-126">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="23dad-127">Si ce paramètre est désactivé, les propriétaires de l’équipe sera en mesure d’ajouter de nouveaux invités.</span><span class="sxs-lookup"><span data-stu-id="23dad-127">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="23dad-128">Au minimum, ce paramètre doit être « sur » pour prendre en charge l’accès invité.</span><span class="sxs-lookup"><span data-stu-id="23dad-128">At a minimum,  this setting must be "on" to support guest access.</span></span>

<span data-ttu-id="23dad-129">Pour obtenir des instructions détaillées sur la configuration de ces paramètres, consultez la section « Office 365 groupes « [Autoriser l’accès invité dans les équipes Microsoft](Teams-dependencies.md) et [Autoriser/bloquer l’accès invité à des groupes d’Office 365](https://go.microsoft.com/fwlink/?linkid=869658).</span><span class="sxs-lookup"><span data-stu-id="23dad-129">For detailed instructions about configuring these settings, see the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md) and [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=869658).</span></span>
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a><span data-ttu-id="23dad-130">Configurer les paramètres □ dans Azure AD-entreprises (B2B)</span><span class="sxs-lookup"><span data-stu-id="23dad-130">□ Configure settings in Azure AD business-to-business (B2B)</span></span>
1. <span data-ttu-id="23dad-131">Se connecter à https://portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="23dad-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="23dad-132">Dans le volet gauche, cliquez sur **Azure Active directory** .</span><span class="sxs-lookup"><span data-stu-id="23dad-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="23dad-133">Sous **Gérer**, cliquez sur **paramètres de l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="23dad-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="23dad-134">Dans la liste **des utilisateurs externes**, cliquez sur **externe gérer les paramètres de collaboration**</span><span class="sxs-lookup"><span data-stu-id="23dad-134">Under **External users**, click **Manage External collaboration settings**</span></span>
5. <span data-ttu-id="23dad-135">Dans la page **paramètres de collaboration externe** Assurez-vous que **les membres peuvent inviter** est définie sur **Oui**. ![Capture d’écran montre un exemple d’un bouton bascule paramètres DAS.</span><span class="sxs-lookup"><span data-stu-id="23dad-135">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.![Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    

<span data-ttu-id="23dad-136">► Au minimum pour prendre en charge les visiteurs, **les membres peuvent inviter** doit être définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="23dad-136">► At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>

> > [!NOTE]
> <span data-ttu-id="23dad-137">Si vous la valeur **membres peuvent inviter** **non** et activez l’accès invité dans Office 365 groupes et Teams Microsoft, les administrateurs peuvent contrôler les invitations aux invités dans votre répertoire.</span><span class="sxs-lookup"><span data-stu-id="23dad-137">If you set **Members can invite** to **No** and enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="23dad-138">Une fois que les invités sont dans le répertoire, ils peuvent être ajoutés aux équipes par les membres non-admin (propriétaires d’équipe).</span><span class="sxs-lookup"><span data-stu-id="23dad-138">After guests are in the directory, they can be added to Teams by non-admin members (team owners).</span></span>


<span data-ttu-id="23dad-139">Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="23dad-139">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>







## <a name="-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="23dad-140">Paramètre de partage Verify □ dans SharePoint</span><span class="sxs-lookup"><span data-stu-id="23dad-140">□ Verify sharing setting in SharePoint</span></span>
1. <span data-ttu-id="23dad-141">Connectez-vous au Centre d'administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="23dad-141">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="23dad-142">Cliquez sur **Centre d’administration**, puis sélectionnez **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="23dad-142">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="23dad-143">Dans le centre d’administration SharePoint, sélectionnez le **partage**.</span><span class="sxs-lookup"><span data-stu-id="23dad-143">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="23dad-144">Assurez-vous que l’option pour **ne pas autoriser le partage en dehors de votre organisation** n’est *pas* sélectionnée. ![Capture d’écran montre un exemple d’un bouton bascule Sparepoint les paramètres en ligne.</span><span class="sxs-lookup"><span data-stu-id="23dad-144">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.![Screenshot shows an example of a Sparepoint Online Settings toggle.</span></span> ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a><span data-ttu-id="23dad-145">Types et des licences de compte □ vérifier</span><span class="sxs-lookup"><span data-stu-id="23dad-145">□ Verify account licenses and types</span></span>

- <span data-ttu-id="23dad-146">**Compte de licence pour les équipes**: pour un compte « Invité » fait en sorte que dans un compte d’utilisateur réel dans certains autres clients Office 365, ce compte d’utilisateur réel doit être une licence pour les équipes de « Invité ».</span><span class="sxs-lookup"><span data-stu-id="23dad-146">**Account licensed for Teams**: For a "Guest" account rooted in a real user account in some other Office 365 tenant, that real user account must be licensed for Teams for “Guest”.</span></span> 
- <span data-ttu-id="23dad-147">**Compte doit être école Office 365 ou utiliser le compte, ou MSA**: actuellement, les utilisateurs qui disposent d’une adresse de messagerie correspondant à un Azure Active Directory, bureau Office 365 ou compte de l’école ou un compte Microsoft (MSA) peuvent être ajoutés en tant qu’invité.</span><span class="sxs-lookup"><span data-stu-id="23dad-147">**Account must be Office 365 school or work account, or MSA account**: Currently, users who have an email address corresponding to an Azure Active Directory, Office 365 work or school account, or a Microsoft account (MSA) can be added as a guest user.</span></span> 
 
## <a name="-configure-environment"></a><span data-ttu-id="23dad-148">Environnement de configurer □</span><span class="sxs-lookup"><span data-stu-id="23dad-148">□ Configure environment</span></span>


<span data-ttu-id="23dad-149">Les invités sont requis pour utiliser l’authentification multifacteur (MFA) si le client d’hébergement exige.</span><span class="sxs-lookup"><span data-stu-id="23dad-149">Guests are required to use multi-factor authentication (MFA) if the hosting tenant requires it.</span></span>
<span data-ttu-id="23dad-150">Pour plus d’informations, voir [modèles d’identité et authentification dans les équipes Microsoft](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="23dad-150">For more details, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="-understand-limitations-for-guests"></a><span data-ttu-id="23dad-151">Limitations de comprendre □ pour les visiteurs</span><span class="sxs-lookup"><span data-stu-id="23dad-151">□ Understand limitations for guests</span></span>

<span data-ttu-id="23dad-152">L’expérience de l’invité présente les limitations par sa conception.</span><span class="sxs-lookup"><span data-stu-id="23dad-152">The guest experience has limitations by design.</span></span> <span data-ttu-id="23dad-153">Assurez-vous que vous comprenez l’expérience invité afin de ne pas essayer de résoudre un élément qui n’est pas un problème.</span><span class="sxs-lookup"><span data-stu-id="23dad-153">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span>
<span data-ttu-id="23dad-154">Par exemple, voici une liste de certaines des fonctionnalités qui n’est pas disponible pour un invité dans Microsoft Teams :</span><span class="sxs-lookup"><span data-stu-id="23dad-154">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="23dad-155">OneDrive entreprise</span><span class="sxs-lookup"><span data-stu-id="23dad-155">OneDrive for Business</span></span>
- <span data-ttu-id="23dad-156">Recherche de personnes en dehors des équipes</span><span class="sxs-lookup"><span data-stu-id="23dad-156">People search outside of Teams</span></span>
- <span data-ttu-id="23dad-157">Calendrier, les réunions planifiées ou détails de la réunion</span><span class="sxs-lookup"><span data-stu-id="23dad-157">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="23dad-158">PSTN</span><span class="sxs-lookup"><span data-stu-id="23dad-158">PSTN</span></span>
- <span data-ttu-id="23dad-159">Organigramme hiérarchique</span><span class="sxs-lookup"><span data-stu-id="23dad-159">Organization chart</span></span>
- <span data-ttu-id="23dad-160">Créer ou modifier une équipe</span><span class="sxs-lookup"><span data-stu-id="23dad-160">Create or revise a team</span></span>
- <span data-ttu-id="23dad-161">Rechercher une équipe</span><span class="sxs-lookup"><span data-stu-id="23dad-161">Browse for a team</span></span>
- <span data-ttu-id="23dad-162">Télécharger les fichiers dans une conversation de personne à personne</span><span class="sxs-lookup"><span data-stu-id="23dad-162">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="23dad-163">Pour plus d’informations, voir [Nouveautés de l’expérience de l’invité](guest-experience.md) et [l’accès invité dans des groupes d’Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="23dad-163">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>




## <a name="troubleshooting"></a><span data-ttu-id="23dad-164">Identification et résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="23dad-164">Troubleshooting</span></span>

<span data-ttu-id="23dad-165">Si vous avez des problèmes avec ajout invités dans Microsoft Teams, consultez le [Guide de dépannage de l’accès invité](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="23dad-165">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


