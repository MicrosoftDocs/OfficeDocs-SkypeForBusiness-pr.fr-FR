---
title: Activer ou désactiver l'accès invité de Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 10/18/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Activer ou désactiver la fonctionnalité d’accès invité dans Microsoft Teams
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc01f54229e5a2644fc004b4014ad41e3c0f8d73
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706258"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="3f3d2-103">Activer ou désactiver l'accès invité de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f3d2-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="3f3d2-104">En tant qu'administrateur d'Office 365, vous devez activer la fonctionnalité Invité pour que vous ou les utilisateurs de votre organisation (notamment les propriétaires d'équipe) puissiez ajouter des invités.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="3f3d2-105">Les paramètres d'invité sont définis dans Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="3f3d2-106">Il faut environ 2 à 24 heures pour que les modifications prennent effet dans votre organisation Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="3f3d2-107">Si un utilisateur voit le message « Contactez votre administrateur » lorsqu’ils essaient d’ajouter un invité à leur équipe, il est probable que la fonctionnalité invité n’a pas été activée ou que les paramètres ne sont pas encore efficaces.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f3d2-108">Pour activer l’expérience complète de la fonctionnalité d’accès invité, il est important de comprendre la dépendance des autorisations principales entre Microsfot Teams, Azure Active Directory et Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="3f3d2-109">Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="3f3d2-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="3f3d2-110">Accès invité et l’accès externe (fédération)</span><span class="sxs-lookup"><span data-stu-id="3f3d2-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a><span data-ttu-id="3f3d2-111">Configurer l’accès invité dans les équipes & Skype entreprise centre d’administration</span><span class="sxs-lookup"><span data-stu-id="3f3d2-111">Configure guest access in the Teams & Skype for Business admin center</span></span>

1.  <span data-ttu-id="3f3d2-112">Connectez-vous à le & équipes Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-112">Sign in to the Teams & Skype for Business admin center.</span></span>

2.  <span data-ttu-id="3f3d2-113">Sélectionnez les **paramètres à l’échelle de la société** > **accès invité**.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="3f3d2-114">La valeur du bouton bascule **Autoriser l’accès invité dans les équipes Microsoft** **sur**.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="3f3d2-115">Autoriser le commutateur d’accès invité activé</span><span class="sxs-lookup"><span data-stu-id="3f3d2-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="3f3d2-116">La valeur la bascule sous **l’appel**, la **réunion**et **de messagerie** **ou **désactiver**,** selon les fonctionnalités que vous souhaitez autoriser pour les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="3f3d2-117">**Émettre des appels privées** – activer ce paramètre **sur** pour qu’ils puissent effectuer des appels d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="3f3d2-118">**IP Autoriser vidéo** - activer ce paramètre **sur** pour qu’ils puissent utiliser la vidéo dans leurs appels et les réunions.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="3f3d2-119">**Mode de partage d’écran** – ce paramètre contrôle la disponibilité de partage pour les utilisateurs invités de l’écran.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="3f3d2-120">Activer ce paramètre sur **désactivé** pour supprimer la capacité pour les visiteurs à partager leurs écrans dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="3f3d2-121">Activer ce paramètre pour une **seule application** pour autoriser le partage d’applications individuelles.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="3f3d2-122">Activer ce paramètre à l' **écran ensemble** pour permettre le partage d’écran terminée.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="3f3d2-123">**Autoriser la conférence maintenant** – activer ce paramètre **sur** pour qu’ils puissent utiliser la fonctionnalité Conférence maintenant dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="3f3d2-124">**Modifier les messages envoyés** : activer ce paramètre **sur** pour qu’ils puissent modifier les messages qu’ils précédemment envoyés.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="3f3d2-125">**Les invités peuvent supprimer des messages envoyés** – activer ce paramètre **sur** pour qu’ils puissent supprimer les messages qu’ils précédemment envoyé.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="3f3d2-126">**Conversation** – activer ce paramètre **sur** donner invités la possibilité d’utiliser la conversation dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="3f3d2-127">**Utiliser des Giphys dans des conversations** – activer ce paramètre **sur** pour qu’ils puissent utiliser Giphys dans des conversations.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="3f3d2-128">Giphy est une base de données en ligne et le moteur de recherche qui permet aux utilisateurs de rechercher et partager les fichiers GIF animés.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="3f3d2-129">Chaque Giphy est affecté à une classification de contenu.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="3f3d2-130">**Évaluation du contenu Giphy** – sélectionnez une évaluation dans la liste déroulante :</span><span class="sxs-lookup"><span data-stu-id="3f3d2-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="3f3d2-131">**Autoriser tout le contenu** - invités pourront insérer tous les Giphys dans les salles de conversation, quelle que soit la classification du contenu.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="3f3d2-132">**Modéré** - invités sera en mesure d’insérer Giphys dans les salles de conversation, mais seront limitées moyennement du contenu pour adultes.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="3f3d2-133">**Strict** – invités sera en mesure d’insérer Giphys dans les salles de conversation, mais seront strictement limitées à partir de l’insertion de contenu pour adultes.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-133">**Strict** – Guests will be able to insert Giphys in chats, but will be strictly restricted from inserting adult content.</span></span>
    - <span data-ttu-id="3f3d2-134">**Utilisez les Memes conversations** - activer ce paramètre **sur** pour qu’ils puissent utiliser Memes dans des conversations.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-134">**Use Memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="3f3d2-135">**Utiliser des autocollants conversations** – activer ce paramètre **sur** pour qu’ils puissent utiliser autocollants dans des conversations.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="3f3d2-136">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="3f3d2-137">Utilisation de PowerShell pour activer ou désactiver les accès invité</span><span class="sxs-lookup"><span data-stu-id="3f3d2-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="3f3d2-138">Télécharger le Skype pour le module Business Online PowerShell à partir dehttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="3f3d2-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="3f3d2-139">Se connecter à une session PowerShell à la Skype pour le point de terminaison Business en ligne.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="3f3d2-140">Vérifiez votre configuration et si `AllowGuestUser` est `$False`, utilisez l’applet de commande [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) pour le définir sur `$True`.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="3f3d2-141">Vous pouvez maintenant avoir des utilisateurs invités dans les équipes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="3f3d2-142">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="3f3d2-142">More information</span></span>

<span data-ttu-id="3f3d2-143">Regardez la vidéo suivante pour plus d’informations sur l’accès invité.</span><span class="sxs-lookup"><span data-stu-id="3f3d2-143">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="3f3d2-144">Ajout d'invités dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f3d2-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
