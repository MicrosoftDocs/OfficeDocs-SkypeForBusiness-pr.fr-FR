---
title: Activation ou désactivation de l’accès invité à Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Découvrez comment activer ou désactiver la fonctionnalité d’accès invité dans Microsoft teams en tant qu’administrateur 365 Office.
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 297a101389de2e1609697ffa2c30a2a8b7a84080
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042776"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="569c6-103">Activation ou désactivation de l’accès invité à Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="569c6-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="569c6-104">Par défaut, l’accès invité est désactivé.</span><span class="sxs-lookup"><span data-stu-id="569c6-104">By default, guest access is turned off.</span></span> <span data-ttu-id="569c6-105">En tant qu’administrateur Microsoft 365 ou Office 365, vous devez activer l’accès invité pour les équipes pour que l’administrateur ou les propriétaires d’équipes puissent ajouter des invités.</span><span class="sxs-lookup"><span data-stu-id="569c6-105">As the Microsoft 365 or Office 365 admin, you must turn on guest access for Teams before the admin or team owners can add guests.</span></span> <span data-ttu-id="569c6-106">Pour activer l’accès invité, utilisez la [liste de contrôle d’accès invité](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="569c6-106">To turn on guest access, use the [Guest access checklist](guest-access-checklist.md).</span></span> 

<span data-ttu-id="569c6-107">Après avoir activé l’accès invité, il est possible que les modifications soient prises en compte.</span><span class="sxs-lookup"><span data-stu-id="569c6-107">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="569c6-108">Si un utilisateur voit le message « contactez votre administrateur » lorsqu’il essaye d’ajouter un invité à son équipe, il est probable que l’accès invité n’ait pas été activé ou que les paramètres ne soient pas encore effectifs.</span><span class="sxs-lookup"><span data-stu-id="569c6-108">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="569c6-109">L’activation de l’accès invité dépend des paramètres d’Azure Active Directory, de Microsoft 365 ou d’Office 365, SharePoint Online et Teams.</span><span class="sxs-lookup"><span data-stu-id="569c6-109">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365 or Office 365, SharePoint Online, and Teams.</span></span> <span data-ttu-id="569c6-110">Pour plus d’informations, voir [autoriser l’accès invité dans Microsoft teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="569c6-110">For more information, see [Authorize guest access in Teams](Teams-dependencies.md).</span></span>



## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="569c6-111">Configurer l’accès invité dans le centre d’administration teams</span><span class="sxs-lookup"><span data-stu-id="569c6-111">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="569c6-112">Se connecter au centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="569c6-112">Sign in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="569c6-113">Sélectionnez **paramètres Org-wide** > **accès invité**.</span><span class="sxs-lookup"><span data-stu-id="569c6-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="569c6-114">Définissez **autoriser l’accès invité dans Microsoft teams** **sur activé**.</span><span class="sxs-lookup"><span data-stu-id="569c6-114">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="569c6-115">Bouton Autoriser l’accès invité sur On</span><span class="sxs-lookup"><span data-stu-id="569c6-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="569c6-116">Sous **appel**, **réunion**et **messagerie**, sélectionnez **activé** ou **désactivé** pour chaque fonctionnalité, en fonction de ce que vous voulez autoriser pour les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="569c6-116">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="569c6-117">**Passer des appels privés** : mettre ce paramètre sur **On** pour permettre aux invités d’effectuer des appels privés.</span><span class="sxs-lookup"><span data-stu-id="569c6-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="569c6-118">**Autoriser IP vidéo** : mettre ce paramètre sur**On** pour permettre aux invités d’utiliser la vidéo dans leurs appels et réunions.</span><span class="sxs-lookup"><span data-stu-id="569c6-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="569c6-119">**Mode de partage d’écran** : ce paramètre détermine la disponibilité de l’écran de partage pour les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="569c6-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="569c6-120">Mettre ce paramètre sur **Désactivé** pour supprimer la possibilité pour les invités de partager leurs écrans dans Teams.</span><span class="sxs-lookup"><span data-stu-id="569c6-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="569c6-121">Activez ce paramètre sur **Application unique** pour autoriser le partage d’applications individuelles.</span><span class="sxs-lookup"><span data-stu-id="569c6-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="569c6-122">Activez ce paramètre sur **Écran entier** pour autoriser le partage d’écran entier.</span><span class="sxs-lookup"><span data-stu-id="569c6-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="569c6-123">**Autoriser Conférence maintenant** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser la fonctionnalité Conférence maintenant dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="569c6-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="569c6-124">**Modifier les messages envoyés** : mettre ce paramètre sur**On** pour permettre aux invités de modifier les messages électroniques qu’ils ont envoyés précédemment.</span><span class="sxs-lookup"><span data-stu-id="569c6-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="569c6-125">**Invités peuvent supprimer les messages envoyés** : mettre ce paramètre sur**On** pour permettre aux invités de supprimer les messages électroniques qu’ils ont envoyés précédemment.</span><span class="sxs-lookup"><span data-stu-id="569c6-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="569c6-126">**Conversation** : mettre ce paramètre sur**On** pour donner aux invités la possibilité d’utiliser la conversation dans Teams.</span><span class="sxs-lookup"><span data-stu-id="569c6-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="569c6-127">**Utiliser Giphys dans les conversations** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser des Giphys dans les conversations.</span><span class="sxs-lookup"><span data-stu-id="569c6-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="569c6-128">Giphy est une base de données en ligne et moteur de recherche qui permet aux utilisateurs de rechercher et partager des fichiers GIF animés.</span><span class="sxs-lookup"><span data-stu-id="569c6-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="569c6-129">Chaque Giphy est affecté à une évaluation du contenu.</span><span class="sxs-lookup"><span data-stu-id="569c6-129">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="569c6-130">**Évaluation du contenu Giphy** : sélectionner une note dans la liste déroulante :</span><span class="sxs-lookup"><span data-stu-id="569c6-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="569c6-131">**Autoriser tout le contenu** : les invités pourront insérer tous les Giphys dans des conversations, quelle que soit l’évaluation du contenu.</span><span class="sxs-lookup"><span data-stu-id="569c6-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="569c6-132">**Modéré** : les invités pourront insérer Giphys dans les conversations, mais seront relativement limités pour le contenu adulte.</span><span class="sxs-lookup"><span data-stu-id="569c6-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="569c6-133">**Strict** : les invités seront en mesure d’insérer des Giphys dans les discussions, mais ils ne seront pas autorisés à insérer des contenus adultes.</span><span class="sxs-lookup"><span data-stu-id="569c6-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="569c6-134">**Utiliser mèmes dans conversations** : activez ce paramètre pour autoriser les **invités à utiliser** mèmes dans les conversations.</span><span class="sxs-lookup"><span data-stu-id="569c6-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="569c6-135">**Utiliser des Autocollants dans les conversations** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser des Autocollants dans les conversations.</span><span class="sxs-lookup"><span data-stu-id="569c6-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

5. <span data-ttu-id="569c6-136">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="569c6-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="569c6-137">Utiliser PowerShell pour activer ou désactiver l’accès invité</span><span class="sxs-lookup"><span data-stu-id="569c6-137">Use PowerShell to turn guest access on or off</span></span>

<span data-ttu-id="569c6-138">Lire [Utiliser PowerShell pour activer ou désactiver l’accès invité](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="569c6-138">Read [Use PowerShell to turn guest access on or off](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span></span>


## <a name="video-adding-guests-in-teams"></a><span data-ttu-id="569c6-139">Vidéo : ajout d’invités dans teams</span><span class="sxs-lookup"><span data-stu-id="569c6-139">Video: Adding guests in Teams</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="569c6-140">Ajout d'invités dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="569c6-140">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="569c6-141">Accès externe (fédération) et accès invité</span><span class="sxs-lookup"><span data-stu-id="569c6-141">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]