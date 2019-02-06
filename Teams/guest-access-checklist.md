---
title: Liste de contrôle de l’accès invité Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 01/22/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Utilisez cette liste de vérification pour vous aider à configurer l’accès invité dans Microsoft Access d’invité équipes.
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 660b838c38da478be2f1226fcdd1b104c3b10b54
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753931"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="f7a41-103">Liste de vérification de l’accès invité équipes</span><span class="sxs-lookup"><span data-stu-id="f7a41-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="f7a41-104">Utilisez cette liste de vérification pour vous aider à activer et configurer la fonctionnalité d’accès invité dans Microsoft Teams selon les préférences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f7a41-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="f7a41-105">Comprendre les limites pour les visiteurs</span><span class="sxs-lookup"><span data-stu-id="f7a41-105">Understand the limitations for guests</span></span>

<span data-ttu-id="f7a41-106">L’expérience de l’invité présente les limitations par sa conception.</span><span class="sxs-lookup"><span data-stu-id="f7a41-106">The guest experience has limitations by design.</span></span> <span data-ttu-id="f7a41-107">Assurez-vous que vous comprenez l’expérience invité afin de ne pas essayer de résoudre un élément qui n’est pas un problème.</span><span class="sxs-lookup"><span data-stu-id="f7a41-107">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="f7a41-108">Par exemple, voici une liste de certaines des fonctionnalités qui n’est pas disponible pour un invité dans Microsoft Teams :</span><span class="sxs-lookup"><span data-stu-id="f7a41-108">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="f7a41-109">OneDrive entreprise</span><span class="sxs-lookup"><span data-stu-id="f7a41-109">OneDrive for Business</span></span>
- <span data-ttu-id="f7a41-110">Recherche de personnes en dehors des équipes</span><span class="sxs-lookup"><span data-stu-id="f7a41-110">People search outside of Teams</span></span>
- <span data-ttu-id="f7a41-111">Calendrier, les réunions planifiées ou détails de la réunion</span><span class="sxs-lookup"><span data-stu-id="f7a41-111">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="f7a41-112">PSTN</span><span class="sxs-lookup"><span data-stu-id="f7a41-112">PSTN</span></span>
- <span data-ttu-id="f7a41-113">Organigramme hiérarchique</span><span class="sxs-lookup"><span data-stu-id="f7a41-113">Organization chart</span></span>
- <span data-ttu-id="f7a41-114">Créer ou modifier une équipe</span><span class="sxs-lookup"><span data-stu-id="f7a41-114">Create or revise a team</span></span>
- <span data-ttu-id="f7a41-115">Rechercher une équipe</span><span class="sxs-lookup"><span data-stu-id="f7a41-115">Browse for a team</span></span>
- <span data-ttu-id="f7a41-116">Télécharger les fichiers dans une conversation de personne à personne</span><span class="sxs-lookup"><span data-stu-id="f7a41-116">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="f7a41-117">Pour plus d’informations, voir [Nouveautés de l’expérience de l’invité](guest-experience.md) et [l’accès invité dans des groupes d’Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="f7a41-117">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="f7a41-118">Accès invité et l’accès externe (fédération)</span><span class="sxs-lookup"><span data-stu-id="f7a41-118">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="f7a41-119">Si vos invités constatez des erreurs de licence</span><span class="sxs-lookup"><span data-stu-id="f7a41-119">If your guests are seeing license errors</span></span>

<span data-ttu-id="f7a41-120">Accès invité dans Microsoft Teams utilise Azure Active Directory entreprise à entreprise (B2B) et son modèle de licence.</span><span class="sxs-lookup"><span data-stu-id="f7a41-120">Guest access in Microsoft Teams uses Azure Active Directory Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="f7a41-121">Si vous voyez la gestion des licences des erreurs, veillez à lire le Guide de gestion des licences B2B pour comprendre les conditions de licence qu'a de votre organisation afin que vos utilisateurs soient en mesure d’invités à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f7a41-121">If you’re seeing licensing errors, make sure to read the B2B licensing guidance to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="f7a41-122">N’oubliez pas les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f7a41-122">A few things to remember:</span></span>

- <span data-ttu-id="f7a41-123">Pour chaque payante licence Azure AD que vous attribuez à un utilisateur, vos utilisateurs peuvent inviter jusqu'à cinq utilisateurs invités sous l’allocation de l’utilisateur externe.</span><span class="sxs-lookup"><span data-stu-id="f7a41-123">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="f7a41-124">Les invités sont les utilisateurs en dehors de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f7a41-124">Guests are users outside your organization.</span></span> <span data-ttu-id="f7a41-125">Vos employés, sous-traitants sur site, les agents sur site et ainsi de suite ne peut pas être ajoutés en tant qu’invités.</span><span class="sxs-lookup"><span data-stu-id="f7a41-125">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="f7a41-126">Les mêmes s’applique à vos filiales.</span><span class="sxs-lookup"><span data-stu-id="f7a41-126">The same applies to your affiliates.</span></span>
- <span data-ttu-id="f7a41-127">Les licences invité sont comptabilisées par rapport à l’organisation invitation.</span><span class="sxs-lookup"><span data-stu-id="f7a41-127">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="f7a41-128">Considérez cela lorsque vous calculez le nombre de licences dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="f7a41-128">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="f7a41-129">Si les invités provenant d’un autre client Office 365 ou sont à l’aide de leurs adresses de messagerie personnels, les licences sont comptabilisées par rapport à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f7a41-129">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="f7a41-130">□ Étape 1 : configurer les paramètres dans Azure AD pour entreprises</span><span class="sxs-lookup"><span data-stu-id="f7a41-130">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="f7a41-131">Se connecter à https://portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="f7a41-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="f7a41-132">Dans le volet gauche, cliquez sur **Azure Active directory** .</span><span class="sxs-lookup"><span data-stu-id="f7a41-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="f7a41-133">Sous **Gérer**, cliquez sur **paramètres de l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="f7a41-134">Dans la liste **des utilisateurs externes**, cliquez sur **externe gérer les paramètres de collaboration**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-134">Under **External users**, click **Manage External collaboration settings**.</span></span>
5. <span data-ttu-id="f7a41-135">Dans la page **paramètres de collaboration externe** Assurez-vous que **les membres peuvent inviter** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-135">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.</span></span>

      ![<span data-ttu-id="f7a41-136">Capture d’écran montre un exemple d’un bouton bascule paramètres DAS.</span><span class="sxs-lookup"><span data-stu-id="f7a41-136">Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    <span data-ttu-id="f7a41-137">Pour prendre en charge les visiteurs, **les membres peuvent inviter** doit être définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-137">To support guests, **Members can invite** must be set to **Yes**.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="f7a41-138">Si vous la valeur **membres peuvent inviter** **non** et ensuite activez l’accès invité dans Office 365 groupes et Teams Microsoft, les administrateurs peuvent contrôler les invitations aux invités dans votre répertoire.</span><span class="sxs-lookup"><span data-stu-id="f7a41-138">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="f7a41-139">Une fois que les invités sont dans le répertoire, ils peuvent être ajoutés aux équipes par les membres non-admin qui sont propriétaires d’équipe.</span><span class="sxs-lookup"><span data-stu-id="f7a41-139">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

<span data-ttu-id="f7a41-140">Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="f7a41-140">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="f7a41-141">□ Étape 2 : configurer des groupes d’Office 365</span><span class="sxs-lookup"><span data-stu-id="f7a41-141">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="f7a41-142">Dans le centre d’administration Microsoft 365, accédez à **paramètres** > **& Services complémentaires** > **Groupes d’Office 365**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-142">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="f7a41-143">Assurez-vous que **laisser les membres du groupe en dehors du contenu de groupe organisation access** est **activé**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-143">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="f7a41-144">Si ce paramètre est désactivé, les invités sera en mesure d’accéder au contenu de groupe.</span><span class="sxs-lookup"><span data-stu-id="f7a41-144">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="f7a41-145">Assurez-vous que **vous permettent d’ajouter des personnes à l’extérieur de l’organisation aux groupes de propriétaires de groupe** est **activé**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-145">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="f7a41-146">Si ce paramètre est désactivé, les propriétaires de l’équipe sera en mesure d’ajouter de nouveaux invités.</span><span class="sxs-lookup"><span data-stu-id="f7a41-146">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="f7a41-147">Au minimum, ce paramètre doit correspondre à la prise en charge l’accès invité.</span><span class="sxs-lookup"><span data-stu-id="f7a41-147">At a minimum, this setting must be On to support guest access.</span></span>

     ![Capture d’écran montre la bascule groupes Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="f7a41-149">Pour obtenir des instructions détaillées sur la configuration de ces paramètres, voir la section « Office 365 groupes » dans [Autoriser l’accès invité dans les équipes Microsoft](Teams-dependencies.md)et [gérer l’accès invité dans des groupes d’Office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) .</span><span class="sxs-lookup"><span data-stu-id="f7a41-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="f7a41-150">□ Étape 3 : activer l’accès invité au niveau du client</span><span class="sxs-lookup"><span data-stu-id="f7a41-150">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="f7a41-151">Au minimum, vous devez activer l’accès invité pour Teams Microsoft dans le **Centre d’administration équipes Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-151">At a minimum, you must turn on Guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="f7a41-152">Dans le centre d’administration équipes, sélectionnez **paramètres à l’échelle de la société** > **accès invité**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-152">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="f7a41-153">Configurer le commutateur **Autoriser l’accès invité dans les équipes Microsoft** **sur**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-153">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Capture d’écran montre un exemple d’un bouton Paramètres d’équipes](media/set-up-guests-image1.png)

3. <span data-ttu-id="f7a41-155">Sur la même page Configurer d’autres paramètres d’invité dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="f7a41-155">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="f7a41-156">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-156">Click **Save**.</span></span>

<span data-ttu-id="f7a41-157">Pour obtenir des instructions détaillées, voir [Activer ou désactiver l’accès invité aux équipes de Microsoft](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="f7a41-157">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="f7a41-158">□ Étape 4 : configurer le partage dans Office 365</span><span class="sxs-lookup"><span data-stu-id="f7a41-158">□  Step 4: Configure Sharing in Office 365</span></span> 

<span data-ttu-id="f7a41-159">Assurez-vous que les utilisateurs peuvent ajouter des invités.</span><span class="sxs-lookup"><span data-stu-id="f7a41-159">Make sure that users can add guests.</span></span> <span data-ttu-id="f7a41-160">Voici comment :</span><span class="sxs-lookup"><span data-stu-id="f7a41-160">Here's how:</span></span>

1. <span data-ttu-id="f7a41-161">Dans le centre d’administration Microsoft 365, accédez à **paramètres** > **sécurité & confidentialité**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-161">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Capture d’écran montre un exemple de paramètres de Services](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="f7a41-163">Dans **partage**, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-163">In **Sharing**, select **Edit**.</span></span>

     ![Capture d’écran montre un exemple d’un bouton bascule le partage des paramètres](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="f7a41-165">La valeur **permettent aux utilisateurs ajouter de nouveaux invités à cette organisation** **sur**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-165">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Capture d’écran montre un exemple d’un bouton bascule le partage des paramètres](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="f7a41-167">Ce paramètre est équivalent au paramètre **d’Inviter des membres** dans **les paramètres utilisateur** > **des utilisateurs externes** dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f7a41-167">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="f7a41-168">□ Étape 5 : Vérifiez le paramètre partage dans SharePoint</span><span class="sxs-lookup"><span data-stu-id="f7a41-168">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="f7a41-169">Connectez-vous au Centre d'administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7a41-169">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="f7a41-170">Cliquez sur **Centre d’administration**, puis sélectionnez **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-170">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="f7a41-171">Dans le centre d’administration SharePoint, sélectionnez le **partage**.</span><span class="sxs-lookup"><span data-stu-id="f7a41-171">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="f7a41-172">Assurez-vous que l’option pour **ne pas autoriser le partage en dehors de votre organisation** n’est *pas* sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f7a41-172">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Capture d’écran montre un exemple d’un bouton bascule Sparepoint les paramètres en ligne.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="f7a41-174">□ Étape 6 : activer les paramètres spécifiques pour les canaux</span><span class="sxs-lookup"><span data-stu-id="f7a41-174">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="f7a41-175">Dans l’application d’équipes, au niveau équipe individuels, configurez des autorisations invité afin que les invités peuvent créer, mettre à jour et supprimer des chaînes.</span><span class="sxs-lookup"><span data-stu-id="f7a41-175">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="f7a41-176">En plus des administrateurs, les propriétaires de l’équipe peuvent configurer ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="f7a41-176">In addition to admins,  team owners can configure this setting.</span></span>

![Capture d’écran montre un exemple d’un bouton bascule des paramètres d’équipe/de canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="f7a41-178">Pour plus d’informations, notamment des vidéos de procédures, voir [accès invité dans les équipes Microsoft](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="f7a41-178">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="f7a41-179">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="f7a41-179">Troubleshooting</span></span>

<span data-ttu-id="f7a41-180">Si vous avez des problèmes avec ajout invités dans Microsoft Teams, consultez le [Guide de dépannage de l’accès invité](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="f7a41-180">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


