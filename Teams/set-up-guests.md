---
title: Activation ou désactivation de l’accès invité à Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Activer ou désactiver la fonctionnalité d’accès invité dans Microsoft Teams
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240e93d5f6329090940e6bf49cb2d6a4ee46ce2f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221450"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="5e84e-103">Activation ou désactivation de l’accès invité à Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="5e84e-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="5e84e-104">En tant qu'administrateur d'Office 365, vous devez activer la fonctionnalité Invité pour que vous ou les utilisateurs de votre organisation (notamment les propriétaires d'équipe) puissiez ajouter des invités.</span><span class="sxs-lookup"><span data-stu-id="5e84e-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span>

<span data-ttu-id="5e84e-105">Les paramètres d'invité sont définis dans Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5e84e-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="5e84e-106">Il faut environ 2 à 24 heures pour que les modifications prennent effet dans votre organisation Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e84e-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="5e84e-107">Si un utilisateur voit le message « Contactez votre administrateur » lorsqu'il essaye d'ajouter un invité à son équipe, il est probable que la fonctionnalité d'invité ne soit pas activée ou que les paramètres ne sont pas encore actifs.</span><span class="sxs-lookup"><span data-stu-id="5e84e-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e84e-108">Pour activer l’expérience complète de la fonctionnalité d’accès invité, il est important de comprendre la dépendance des autorisations principales entre Microsfot Teams, Azure Active Directory et Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e84e-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="5e84e-109">Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="5e84e-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="5e84e-110">Accès invité et accès externe (fédération)</span><span class="sxs-lookup"><span data-stu-id="5e84e-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="5e84e-111">Configurer l’accès invité dans le centre d’administration de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5e84e-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="5e84e-112">Se connecter au centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5e84e-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="5e84e-113">Sélectionnez **paramètres Org-wide** > **accès invité**.</span><span class="sxs-lookup"><span data-stu-id="5e84e-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="5e84e-114">Mettre le bouton bascule**Autoriser l’accès invité dans Microsoft Teams** sur **On**.</span><span class="sxs-lookup"><span data-stu-id="5e84e-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="5e84e-115">Bouton Autoriser l’accès invité sur On</span><span class="sxs-lookup"><span data-stu-id="5e84e-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="5e84e-116">Mettre les boutons bascules sous **Appel**, **Réunion**, et **Messagerie** sur **On** ou **Off**, en fonction de la fonctionnalité que vous voulez autoriser pour les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="5e84e-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="5e84e-117">**Passer des appels privés** : mettre ce paramètre sur **On** pour permettre aux invités d’effectuer des appels privés.</span><span class="sxs-lookup"><span data-stu-id="5e84e-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="5e84e-118">**Autoriser IP vidéo** : mettre ce paramètre sur**On** pour permettre aux invités d’utiliser la vidéo dans leurs appels et réunions.</span><span class="sxs-lookup"><span data-stu-id="5e84e-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="5e84e-119">**Mode de partage d’écran** : ce paramètre détermine la disponibilité de l’écran de partage pour les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="5e84e-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="5e84e-120">Mettre ce paramètre sur **Désactivé** pour supprimer la possibilité pour les invités de partager leurs écrans dans Teams.</span><span class="sxs-lookup"><span data-stu-id="5e84e-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="5e84e-121">Activez ce paramètre sur **Application unique** pour autoriser le partage d’applications individuelles.</span><span class="sxs-lookup"><span data-stu-id="5e84e-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="5e84e-122">Activez ce paramètre sur **Écran entier** pour autoriser le partage d’écran entier.</span><span class="sxs-lookup"><span data-stu-id="5e84e-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="5e84e-123">**Autoriser Conférence maintenant** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser la fonctionnalité Conférence maintenant dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5e84e-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="5e84e-124">**Modifier les messages envoyés** : mettre ce paramètre sur**On** pour permettre aux invités de modifier les messages électroniques qu’ils ont envoyés précédemment.</span><span class="sxs-lookup"><span data-stu-id="5e84e-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="5e84e-125">**Invités peuvent supprimer les messages envoyés** : mettre ce paramètre sur**On** pour permettre aux invités de supprimer les messages électroniques qu’ils ont envoyés précédemment.</span><span class="sxs-lookup"><span data-stu-id="5e84e-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="5e84e-126">**Conversation** : mettre ce paramètre sur**On** pour donner aux invités la possibilité d’utiliser la conversation dans Teams.</span><span class="sxs-lookup"><span data-stu-id="5e84e-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="5e84e-127">**Utiliser Giphys dans les conversations** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser des Giphys dans les conversations.</span><span class="sxs-lookup"><span data-stu-id="5e84e-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="5e84e-128">Giphy est une base de données en ligne et moteur de recherche qui permet aux utilisateurs de rechercher et partager des fichiers GIF animés.</span><span class="sxs-lookup"><span data-stu-id="5e84e-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="5e84e-129">Chaque Giphy est affecté à une évaluation du contenu.</span><span class="sxs-lookup"><span data-stu-id="5e84e-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="5e84e-130">**Évaluation du contenu Giphy** : sélectionner une note dans la liste déroulante :</span><span class="sxs-lookup"><span data-stu-id="5e84e-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="5e84e-131">**Autoriser tout le contenu** : les invités pourront insérer tous les Giphys dans des conversations, quelle que soit l’évaluation du contenu.</span><span class="sxs-lookup"><span data-stu-id="5e84e-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="5e84e-132">**Modéré** : les invités pourront insérer Giphys dans les conversations, mais seront relativement limités pour le contenu adulte.</span><span class="sxs-lookup"><span data-stu-id="5e84e-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="5e84e-133">**Strict** : les invités seront en mesure d’insérer des Giphys dans les discussions, mais ils ne seront pas autorisés à insérer des contenus adultes.</span><span class="sxs-lookup"><span data-stu-id="5e84e-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
    - <span data-ttu-id="5e84e-134">**Utiliser mèmes dans conversations** : activez ce paramètre \*\*\*\* pour autoriser les invités à utiliser mèmes dans les conversations.</span><span class="sxs-lookup"><span data-stu-id="5e84e-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="5e84e-135">**Utiliser des Autocollants dans les conversations** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser des Autocollants dans les conversations.</span><span class="sxs-lookup"><span data-stu-id="5e84e-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="5e84e-136">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5e84e-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="5e84e-137">Utiliser PowerShell pour activer ou désactiver l’accès invité</span><span class="sxs-lookup"><span data-stu-id="5e84e-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="5e84e-138">Télécharger le module PowerShell Skype Entreprise Online à partir de https://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="5e84e-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="5e84e-139">Connecter une session PowerShell à un point de terminaison Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="5e84e-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="5e84e-140">Vérifier votre configuration et si `AllowGuestUser` est `$False`, utilisez l’applet de commande [Ensemble CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) défini sur `$True`.</span><span class="sxs-lookup"><span data-stu-id="5e84e-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="5e84e-141">Vous pouvez désormais avoir des utilisateurs invités dans Teams pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5e84e-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="5e84e-142">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="5e84e-142">More information</span></span>

<span data-ttu-id="5e84e-143">Regardez la vidéo suivante pour plus de détails à propos de l'accès invité.</span><span class="sxs-lookup"><span data-stu-id="5e84e-143">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="5e84e-144">Ajout d'invités dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5e84e-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
