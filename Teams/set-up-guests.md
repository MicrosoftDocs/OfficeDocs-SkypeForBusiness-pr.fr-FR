---
title: Activation ou désactivation de l’accès invité à Microsoft teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Découvrez comment activer ou désactiver la fonctionnalité d’accès invité dans Microsoft teams en tant qu’administrateur 365 Office.
ms.openlocfilehash: 54d7461e9e03cd22900e07aca7ad2d12712faab7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508061"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="bad46-103">Activation ou désactivation de l’accès invité à Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="bad46-103">Turn on or turn off guest access to Microsoft Teams</span></span>

<span data-ttu-id="bad46-104">Par défaut, l’accès invité est désactivé.</span><span class="sxs-lookup"><span data-stu-id="bad46-104">By default, guest access is turned off.</span></span> <span data-ttu-id="bad46-105">Vous devez activer l’accès invité pour les équipes pour que les administrateurs ou les propriétaires d’équipes puissent ajouter des invités.</span><span class="sxs-lookup"><span data-stu-id="bad46-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span>

<span data-ttu-id="bad46-106">Après avoir activé l’accès invité, il est possible que les modifications soient prises en compte.</span><span class="sxs-lookup"><span data-stu-id="bad46-106">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="bad46-107">Si un utilisateur voit le message « contactez votre administrateur » lorsqu’il essaye d’ajouter un invité à son équipe, il est probable que l’accès invité n’ait pas été activé ou que les paramètres ne soient pas encore effectifs.</span><span class="sxs-lookup"><span data-stu-id="bad46-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bad46-108">L’activation de l’accès invité dépend des paramètres dans Azure Active Directory, Microsoft 365, SharePoint et Teams.</span><span class="sxs-lookup"><span data-stu-id="bad46-108">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="bad46-109">Pour plus d’informations, reportez-vous à [la rubrique collaborer avec des invités dans une équipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="bad46-109">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="bad46-110">Configurer l’accès invité dans le centre d’administration teams</span><span class="sxs-lookup"><span data-stu-id="bad46-110">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="bad46-111">Connectez-vous au [Centre d’administration Microsoft teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="bad46-111">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="bad46-112">Sélectionnez **paramètres Org-wide** > **accès invité**.</span><span class="sxs-lookup"><span data-stu-id="bad46-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="bad46-113">Définissez **autoriser l’accès invité dans Microsoft teams** **sur activé**.</span><span class="sxs-lookup"><span data-stu-id="bad46-113">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="bad46-114">Bouton Autoriser l’accès invité sur On</span><span class="sxs-lookup"><span data-stu-id="bad46-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="bad46-115">Sous **appel**, **réunion**et **messagerie**, sélectionnez **activé** ou **désactivé** pour chaque fonctionnalité, en fonction de ce que vous voulez autoriser pour les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="bad46-115">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="bad46-116">**Passer des appels privés** : mettre ce paramètre sur **On** pour permettre aux invités d’effectuer des appels privés.</span><span class="sxs-lookup"><span data-stu-id="bad46-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="bad46-117">**Autoriser IP vidéo** : mettre ce paramètre sur**On** pour permettre aux invités d’utiliser la vidéo dans leurs appels et réunions.</span><span class="sxs-lookup"><span data-stu-id="bad46-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="bad46-118">**Mode de partage d’écran** : ce paramètre détermine la disponibilité de l’écran de partage pour les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="bad46-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="bad46-119">Mettre ce paramètre sur **Désactivé** pour supprimer la possibilité pour les invités de partager leurs écrans dans Teams.</span><span class="sxs-lookup"><span data-stu-id="bad46-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="bad46-120">Activez ce paramètre sur **Application unique** pour autoriser le partage d’applications individuelles.</span><span class="sxs-lookup"><span data-stu-id="bad46-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="bad46-121">Activez ce paramètre sur **Écran entier** pour autoriser le partage d’écran entier.</span><span class="sxs-lookup"><span data-stu-id="bad46-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="bad46-122">**Autoriser Conférence maintenant** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser la fonctionnalité Conférence maintenant dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bad46-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="bad46-123">**Modifier les messages envoyés** : mettre ce paramètre sur**On** pour permettre aux invités de modifier les messages électroniques qu’ils ont envoyés précédemment.</span><span class="sxs-lookup"><span data-stu-id="bad46-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="bad46-124">**Invités peuvent supprimer les messages envoyés** : mettre ce paramètre sur**On** pour permettre aux invités de supprimer les messages électroniques qu’ils ont envoyés précédemment.</span><span class="sxs-lookup"><span data-stu-id="bad46-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="bad46-125">**Conversation** : mettre ce paramètre sur**On** pour donner aux invités la possibilité d’utiliser la conversation dans Teams.</span><span class="sxs-lookup"><span data-stu-id="bad46-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="bad46-126">**Utiliser Giphys dans les conversations** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser des Giphys dans les conversations.</span><span class="sxs-lookup"><span data-stu-id="bad46-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="bad46-127">Giphy est une base de données en ligne et moteur de recherche qui permet aux utilisateurs de rechercher et partager des fichiers GIF animés.</span><span class="sxs-lookup"><span data-stu-id="bad46-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="bad46-128">Chaque Giphy est affecté à une évaluation du contenu.</span><span class="sxs-lookup"><span data-stu-id="bad46-128">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="bad46-129">**Évaluation du contenu Giphy** : sélectionner une note dans la liste déroulante :</span><span class="sxs-lookup"><span data-stu-id="bad46-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="bad46-130">**Autoriser tout le contenu** : les invités pourront insérer tous les Giphys dans des conversations, quelle que soit l’évaluation du contenu.</span><span class="sxs-lookup"><span data-stu-id="bad46-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="bad46-131">**Modéré** : les invités pourront insérer Giphys dans les conversations, mais seront relativement limités pour le contenu adulte.</span><span class="sxs-lookup"><span data-stu-id="bad46-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="bad46-132">**Strict** : les invités seront en mesure d’insérer des Giphys dans les discussions, mais ils ne seront pas autorisés à insérer des contenus adultes.</span><span class="sxs-lookup"><span data-stu-id="bad46-132">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="bad46-133">**Utiliser mèmes dans conversations** : activez ce paramètre pour autoriser les **invités à utiliser** mèmes dans les conversations.</span><span class="sxs-lookup"><span data-stu-id="bad46-133">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="bad46-134">**Utiliser des Autocollants dans les conversations** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser des Autocollants dans les conversations.</span><span class="sxs-lookup"><span data-stu-id="bad46-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

    ![Paramètres des autorisations invité dans teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="bad46-136">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="bad46-136">Click **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="bad46-137">Accès externe (fédération) et accès invité</span><span class="sxs-lookup"><span data-stu-id="bad46-137">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="bad46-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bad46-138">See also</span></span>

[<span data-ttu-id="bad46-139">Configurer la collaboration sécurisée avec Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bad46-139">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="bad46-140">Bloquer les utilisateurs invités d’une équipe en particulier</span><span class="sxs-lookup"><span data-stu-id="bad46-140">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="bad46-141">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="bad46-141">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)