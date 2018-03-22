---
title: Liste de contrôle de l’accès invité Microsoft équipes
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Cette liste de vérification permet de configurer l’accès invité dans l’accès des invités aux équipes Microsoft.
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53800ddf452fd6596abe3e4404c79352483e946
ms.sourcegitcommit: ccbe086ccb2c0be716984010a1253a4c8c0276b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2018
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="b9ef5-103">Liste de contrôle de l’accès invité équipes</span><span class="sxs-lookup"><span data-stu-id="b9ef5-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="b9ef5-104">Utilisez cette liste de vérification pour vous aider à activer et configurer la fonction accès invité dans Microsoft Teams en fonction des préférences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>




## <a name="--enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="b9ef5-105">□ Activer invité l’accès au niveau du client</span><span class="sxs-lookup"><span data-stu-id="b9ef5-105">□  Enable guest access at the tenant level</span></span>

<span data-ttu-id="b9ef5-106">Au minimum, vous devez activer Microsoft Teams pour tous les utilisateurs du type de licence **invité**.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-106">At a minimum, you must turn on Microsoft Teams for all users of the license type **Guest**.</span></span> <span data-ttu-id="b9ef5-107">Pour obtenir des instructions détaillées, voir [Activer ou désactiver l’accès invité pour les équipes de Microsoft](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="b9ef5-107">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

![Capture d’écran montre un exemple d’un bouton Paramètres des équipes](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a><span data-ttu-id="b9ef5-109">□ Activer des paramètres spécifiques pour les canaux</span><span class="sxs-lookup"><span data-stu-id="b9ef5-109">□ Enable specific settings for channels</span></span> 
<span data-ttu-id="b9ef5-110">Dans l’application d’équipes, au niveau de l’équipe individuels, configurer les autorisations invité afin que les invités peuvent créer, mettre à jour et supprimer des canaux.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-110">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="b9ef5-111">En plus des administrateurs, les propriétaires de l’équipe peuvent configurer ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-111">In addition to admins,  team owners can configure this setting.</span></span>

![Capture d’écran montre un exemple d’un bouton bascule de paramètres d’équipe/canal](media/guest-access-checklist-TeamsSettings2.png)


<span data-ttu-id="b9ef5-113">Pour plus d’informations, y compris les vidéos de procédure, reportez-vous à la section [accès invité dans des équipes de Microsoft](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="b9ef5-113">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>



## <a name="--configure-sharing-in-office-365"></a><span data-ttu-id="b9ef5-114">□ Configurer le partage dans Office 365</span><span class="sxs-lookup"><span data-stu-id="b9ef5-114">□  Configure Sharing in Office 365</span></span> 

<span data-ttu-id="b9ef5-115">□ Assurez-vous que les utilisateurs peuvent ajouter des invités.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-115">□ Make sure users can add guests.</span></span> <span data-ttu-id="b9ef5-116">Voici comment :</span><span class="sxs-lookup"><span data-stu-id="b9ef5-116">Here's how:</span></span>

1. <span data-ttu-id="b9ef5-117">Dans le centre d’administration Office 365, cliquez sur **paramètres** > **sécurité et confidentialité**.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-117">In the Office 365 admin center, go to **Settings** > **Security & privacy**.</span></span>
<span data-ttu-id="b9ef5-118">![Capture d’écran montre un exemple de paramètres de Services](media/guest-access-checklist-Office365Admin_Services_addins.png)</span><span class="sxs-lookup"><span data-stu-id="b9ef5-118">![Screenshot shows an example of a Services settings](media/guest-access-checklist-Office365Admin_Services_addins.png)</span></span>
1. <span data-ttu-id="b9ef5-119">Dans le **partage**, sélectionnez **Modifier**. ![Capture d’écran montre un exemple d’un bouton de modification des paramètres de partage](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span><span class="sxs-lookup"><span data-stu-id="b9ef5-119">In **Sharing**, select **Edit**.![Screenshot shows an example of a Sharing Settings edit button](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span></span>
2. <span data-ttu-id="b9ef5-120">La valeur **permettent aux utilisateurs de l’ajouter de nouveau invités à cette organisation** **sur**, puis cliquez sur **Enregistrer**. ![Capture d’écran montre un exemple d’un bouton Paramètres de partage](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span><span class="sxs-lookup"><span data-stu-id="b9ef5-120">Set **Let users add new guests to this organization** to **On**, and then click **Save**.![Screenshot shows an example of a Sharing Settings toggle](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span></span>
 

 > [!NOTE]
> <span data-ttu-id="b9ef5-121">Ce paramètre est équivalent au paramètre **peuvent inviter des membres** dans les paramètres de l’utilisateur > utilisateurs externes dans Active Directory Azure.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-121">This setting is equivalent to the **Members can invite** setting in  User settings > External users  in Azure AD.</span></span>  




## <a name="-configure-office-365-groups"></a><span data-ttu-id="b9ef5-122">□ Configurer des groupes d’Office 365</span><span class="sxs-lookup"><span data-stu-id="b9ef5-122">□ Configure Office 365 Groups</span></span>

<span data-ttu-id="b9ef5-123">Dans le centre d’administration Office 365, cliquez sur **paramètres** > **Services et compléments** > **Groupes d’Office 365**.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-123">In the Office 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>

<span data-ttu-id="b9ef5-124">Veillez à **que laisser les membres du groupe en dehors du contenu de groupe d’accès organisation** est définie sur **On**.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-124">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="b9ef5-125">Si ce paramètre est désactivé, les invités ne seront en mesure d’accéder à n’importe quel contenu de groupe.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-125">If this setting is turned off, guests won't be able to access any group content.</span></span>

<span data-ttu-id="b9ef5-126">Assurez-vous que **vous permettent d’ajouter des personnes à l’extérieur de l’organisation à des groupes de propriétaires de groupe** est définie sur **On**.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-126">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="b9ef5-127">Si ce paramètre est désactivé, les propriétaires de l’équipe ne seront en mesure d’ajouter de nouveaux invités.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-127">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="b9ef5-128">(Toutefois, si un administrateur a ajouté un utilisateur invité à AD Azure, puis le propriétaire de l’équipe serait en mesure d’ajouter cet utilisateur à l’équipe.) Au minimum, ce paramètre doit être « on » pour prendre en charge de l’accès invité.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-128">(However, if an admin had added a guest user to Azure AD, then the Team owner would be able to add that user to the Team.) At a minimum,  this setting must be "on" to support guest access.</span></span>

<span data-ttu-id="b9ef5-129">Pour obtenir des instructions détaillées sur la configuration de ces paramètres, reportez-vous à la section « Office 365 groupes » [Autoriser l’accès invité dans des équipes de Microsoft](Teams-dependencies.md) et [Autoriser/bloquer l’accès invité à des groupes d’Office 365](https://go.microsoft.com/fwlink/?linkid=869658).</span><span class="sxs-lookup"><span data-stu-id="b9ef5-129">For detailed instructions about configuring these settings, see the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md) and [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=869658).</span></span>
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a><span data-ttu-id="b9ef5-130">Configurer les paramètres □ dans Azure AD entreprise-entreprise (B2B)</span><span class="sxs-lookup"><span data-stu-id="b9ef5-130">□ Configure settings in Azure AD business-to-business (B2B)</span></span>
1. <span data-ttu-id="b9ef5-131">Connexion à https://portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="b9ef5-132">Dans le volet gauche, cliquez sur **Azure Active directory** .</span><span class="sxs-lookup"><span data-stu-id="b9ef5-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="b9ef5-133">Sous **Gérer**, cliquez sur **paramètres de l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="b9ef5-134">**Les utilisateurs externes**, assurez-vous que **peuvent inviter des membres** est définie sur **Oui**. ![Capture d’écran montre un exemple d’un bouton Paramètres du DAS.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-134">In **External users**, make sure **Members can invite** is set to **Yes**.![Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    

<span data-ttu-id="b9ef5-135">► Au minimum pour prendre en charge des invités, **peuvent inviter des membres** doit être définie à **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-135">► At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>

> > [!NOTE]
> <span data-ttu-id="b9ef5-136">Si vous définissez **peuvent inviter des membres** **non** et activez l’accès invité dans Office 365 groupes et Teams de Microsoft, les administrateurs peuvent contrôler des invitations des invités dans votre répertoire.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-136">If you set **Members can invite** to **No** and enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="b9ef5-137">Après que les invités sont dans le répertoire, ils peuvent être ajoutés aux équipes par les membres non-admin (propriétaires d’équipe).</span><span class="sxs-lookup"><span data-stu-id="b9ef5-137">After guests are in the directory, they can be added to Teams by non-admin members (team owners).</span></span>


<span data-ttu-id="b9ef5-138">Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="b9ef5-138">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>







## <a name="-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="b9ef5-139">Paramètre de partage vérifier □ dans SharePoint</span><span class="sxs-lookup"><span data-stu-id="b9ef5-139">□ Verify sharing setting in SharePoint</span></span>
1. <span data-ttu-id="b9ef5-140">Connectez-vous au Centre d'administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-140">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="b9ef5-141">Cliquez sur **Admin center**et sélectionnez **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-141">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="b9ef5-142">Dans le centre d’administration SharePoint, sélectionnez le **partage**.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-142">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="b9ef5-143">Assurez-vous que l’option pour **ne pas autoriser le partage à l’extérieur de votre organisation** n’est *pas* sélectionnée. ![Capture d’écran montre un exemple d’un bouton de bascule Sparepoint les paramètres en ligne.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-143">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.![Screenshot shows an example of a Sparepoint Online Settings toggle.</span></span> ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a><span data-ttu-id="b9ef5-144">Types et licences de compte □ vérifier</span><span class="sxs-lookup"><span data-stu-id="b9ef5-144">□ Verify account licenses and types</span></span>

- <span data-ttu-id="b9ef5-145">**Compte de licence pour les équipes**: pour un compte « Invité » est associé à une racine dans un compte d’utilisateur réel dans certains autres clients Office 365, ce compte utilisateur réel doit posséder une licence pour les équipes de « Invité ».</span><span class="sxs-lookup"><span data-stu-id="b9ef5-145">**Account licensed for Teams**: For a "Guest" account rooted in a real user account in some other Office 365 tenant, that real user account must be licensed for Teams for “Guest”.</span></span> 
- <span data-ttu-id="b9ef5-146">**Compte doit être Office 365 école ou au travail de compte, ou MSA**: actuellement, les utilisateurs qui ont une adresse de messagerie correspondant à un compte Microsoft (MSA) Active Directory Azure, Office 365 travail ou compte de l’établissement peuvent être ajoutés en tant qu’invité.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-146">**Account must be Office 365 school or work account, or MSA account**: Currently, users who have an email address corresponding to an Azure Active Directory, Office 365 work or school account, or a Microsoft account (MSA) can be added as a guest user.</span></span> 
 
## <a name="-configure-environment"></a><span data-ttu-id="b9ef5-147">Environnement de configuration □</span><span class="sxs-lookup"><span data-stu-id="b9ef5-147">□ Configure environment</span></span>


<span data-ttu-id="b9ef5-148">Invités doivent utiliser une authentification multifacteur (AMF) si le locataire hébergement l’exige.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-148">Guests are required to use multi-factor authentication (MFA) if the hosting tenant requires it.</span></span>
<span data-ttu-id="b9ef5-149">Pour plus d’informations, consultez [modèles d’identité et d’authentification dans des équipes de Microsoft](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="b9ef5-149">For more details, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="-understand-limitations-for-guests"></a><span data-ttu-id="b9ef5-150">Limitations de comprendre □ pour les visiteurs</span><span class="sxs-lookup"><span data-stu-id="b9ef5-150">□ Understand limitations for guests</span></span>

<span data-ttu-id="b9ef5-151">L’expérience de l’invité a des limitations à la conception.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-151">The guest experience has limitations by design.</span></span> <span data-ttu-id="b9ef5-152">Assurez-vous que vous comprenez l’expérience invité afin de ne pas tenter de réparer quelque chose qui n’est pas un problème.</span><span class="sxs-lookup"><span data-stu-id="b9ef5-152">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span>
<span data-ttu-id="b9ef5-153">Par exemple, voici une liste de quelques-unes des fonctionnalités qui n’est pas disponible à un invité dans Microsoft Teams :</span><span class="sxs-lookup"><span data-stu-id="b9ef5-153">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="b9ef5-154">OneDrive pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="b9ef5-154">OneDrive for Business</span></span>
- <span data-ttu-id="b9ef5-155">En dehors des équipes de recherche de personnes</span><span class="sxs-lookup"><span data-stu-id="b9ef5-155">People search outside of Teams</span></span>
- <span data-ttu-id="b9ef5-156">Calendrier, réunions planifiées ou détails de la réunion</span><span class="sxs-lookup"><span data-stu-id="b9ef5-156">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="b9ef5-157">PSTN</span><span class="sxs-lookup"><span data-stu-id="b9ef5-157">PSTN</span></span>
- <span data-ttu-id="b9ef5-158">Organigramme hiérarchique</span><span class="sxs-lookup"><span data-stu-id="b9ef5-158">Organization chart</span></span>
- <span data-ttu-id="b9ef5-159">Créer ou modifier une équipe</span><span class="sxs-lookup"><span data-stu-id="b9ef5-159">Create or revise a team</span></span>
- <span data-ttu-id="b9ef5-160">Recherchez une équipe</span><span class="sxs-lookup"><span data-stu-id="b9ef5-160">Browse for a team</span></span>
- <span data-ttu-id="b9ef5-161">Télécharger des fichiers à une conversation de personne à personne</span><span class="sxs-lookup"><span data-stu-id="b9ef5-161">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="b9ef5-162">Pour plus d’informations, consultez [Nouveautés de l’expérience d’invité](guest-experience.md) et [l’accès invité dans groupes d’Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="b9ef5-162">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>




## <a name="troubleshooting"></a><span data-ttu-id="b9ef5-163">Identification et résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="b9ef5-163">Troubleshooting</span></span>

<span data-ttu-id="b9ef5-164">Si vous avez des problèmes avec ajout d’invités dans Teams de Microsoft, consultez le [Guide de dépannage de l’accès invité](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="b9ef5-164">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


