---
title: Activer ou désactiver l'accès invité dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
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
description: Découvrez comment activer ou désactiver la fonctionnalité d'accès invité dans Microsoft Teams en tant qu'administrateur d'Office 365.
ms.openlocfilehash: 34759e601f5c0cd232bcd6227ff5c7d1fef1d3fe
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107400"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="cfd4d-103">Activer ou désactiver l'accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cfd4d-103">Turn on or turn off guest access to Microsoft Teams</span></span>

> [!Note]

> <span data-ttu-id="cfd4d-104">**Jusqu’en février 2021,** l’accès invité est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-104">Until **February 2021**, guest access is turned off by default.</span></span> <span data-ttu-id="cfd4d-105">Vous devez activer l'accès invité pour Teams avant que les administrateurs ou les propriétaires d'équipes puissent ajouter des invités.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span> <span data-ttu-id="cfd4d-106">Une fois l’accès invité activer, l’application des modifications peut prendre quelques heures.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-106">After you turn on guest access, it might take a few hours for the changes to take effect.</span></span> <span data-ttu-id="cfd4d-107">Si les utilisateurs voient le **message** Contacter votre administrateur lorsqu’ils essaient d’ajouter un invité à leur équipe, il est probable que l’accès invité n’a pas été désactivé ou que les paramètres ne sont pas encore effectifs.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-107">If users see the message **Contact your administrator** when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> <span data-ttu-id="cfd4d-108">Après **février 2021,** l’accès invité dans Microsoft Teams sera désactivé par défaut pour les nouveaux clients & clients existants qui n’ont pas configuré ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-108">After **February 2021**, guest access in Microsoft Teams will be turned on by default for new customers & existing customers who haven't configured this setting.</span></span> <span data-ttu-id="cfd4d-109">Lorsque cette modification est implémentée, si vous n’avez pas encore configuré la fonctionnalité d’accès invité dans Microsoft Teams, cette fonctionnalité sera activée dans votre client.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-109">When this change is implemented, if you've not already configured guest access capability in Microsoft Teams, that capability will be enabled in your tenant.</span></span> <span data-ttu-id="cfd4d-110">Si vous souhaitez que l’accès invité reste désactivé pour votre organisation, vous  devez confirmer que le paramètre d’accès invité est définie sur Désactivé au lieu de Service **par défaut.**</span><span class="sxs-lookup"><span data-stu-id="cfd4d-110">If you want guest access to remain disabled for your organization, you'll need to confirm that the guest access setting is set to **Off** instead of **Service default**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfd4d-111">L'activation de l'accès invité dépend des paramètres d'Azure Active Directory, de Microsoft 365, de SharePoint et de Teams.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-111">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="cfd4d-112">Pour plus d’information, consultez [Collaborer avec des invités dans une équipe](/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="cfd4d-112">For more information, see [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="cfd4d-113">Configurer l’accès invité dans le centre d’administration de Teams</span><span class="sxs-lookup"><span data-stu-id="cfd4d-113">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="cfd4d-114">Se connecter au [Centre d’administration de Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="cfd4d-114">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="cfd4d-115">Sélectionnez **paramètres Org-wide** > **accès invité**.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-115">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="cfd4d-116">Définissez l’option **Autoriser l’accès invité dans Microsoft Teams** sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-116">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="cfd4d-117">Bouton Autoriser l’accès invité sur On</span><span class="sxs-lookup"><span data-stu-id="cfd4d-117">Allow guest access switch set to On</span></span> ](media/guest-access-setting.png)

4. <span data-ttu-id="cfd4d-118">Sous **Appel**, **Réunion**, et **Messagerie** sélectionnez **Activé** ou **Désactivé** pour chaque fonctionnalité, en fonction de ce que vous souhaitez autoriser pour les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-118">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="cfd4d-119">**Passer des appels privés** : mettre ce paramètre sur **On** pour permettre aux invités d’effectuer des appels privés.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-119">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="cfd4d-120">**Autoriser IP vidéo** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser la vidéo dans leurs appels et réunions.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-120">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="cfd4d-121">**Mode de partage d’écran** : ce paramètre détermine la disponibilité de l’écran de partage pour les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-121">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span>
          - <span data-ttu-id="cfd4d-122">Mettre ce paramètre sur **Désactivé** pour supprimer la possibilité pour les invités de partager leurs écrans dans Teams.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-122">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span>
          - <span data-ttu-id="cfd4d-123">Activez ce paramètre sur **Application unique** pour autoriser le partage d’applications individuelles.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-123">Turn this setting to **Single application** to allow sharing of individual applications.</span></span>
          - <span data-ttu-id="cfd4d-124">Activez ce paramètre sur **Écran entier** pour autoriser le partage d’écran entier.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-124">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="cfd4d-125">**Autoriser Conférence maintenant** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser la fonctionnalité Conférence maintenant dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-125">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="cfd4d-126">**Modifier les messages envoyés** : mettre ce paramètre sur **On** pour permettre aux invités de modifier les messages électroniques qu’ils ont envoyés précédemment.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-126">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="cfd4d-127">**Invités peuvent supprimer les messages envoyés** : mettre ce paramètre sur **On** pour permettre aux invités de supprimer les messages électroniques qu’ils ont envoyés précédemment.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-127">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="cfd4d-128">**Conversation** : mettre ce paramètre sur **On** pour donner aux invités la possibilité d’utiliser la conversation dans Teams.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-128">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="cfd4d-129">**Utiliser Giphys dans les conversations** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser des Giphys dans les conversations.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-129">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="cfd4d-130">Giphy est une base de données en ligne et moteur de recherche qui permet aux utilisateurs de rechercher et partager des fichiers GIF animés.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-130">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="cfd4d-131">Chaque Giphy est affecté à une évaluation du contenu.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-131">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="cfd4d-132">**Évaluation du contenu Giphy** : sélectionner une note dans la liste déroulante :</span><span class="sxs-lookup"><span data-stu-id="cfd4d-132">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="cfd4d-133">**Autoriser tout le contenu** : les invités pourront insérer tous les Giphys dans des conversations, quelle que soit l’évaluation du contenu.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-133">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="cfd4d-134">**Modéré** : les invités pourront insérer Giphys dans les conversations, mais seront relativement limités pour le contenu adulte.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-134">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="cfd4d-135">**Strict** – Les invités peuvent insérer des Giphys dans les conversations, mais ne peuvent pas insérer de contenu pour adultes.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-135">**Strict** – Guests can insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="cfd4d-136">**Utiliser memes dans les conversations** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser des Memes dans les conversations.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-136">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="cfd4d-137">**Utiliser des Autocollants dans les conversations** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser des Autocollants dans les conversations.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-137">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span>

    ![Paramètres des permissions des invités dans Teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="cfd4d-139">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="cfd4d-139">Select **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="cfd4d-140">Accès externe (fédération) et accès invité</span><span class="sxs-lookup"><span data-stu-id="cfd4d-140">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="cfd4d-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cfd4d-141">See also</span></span>

[<span data-ttu-id="cfd4d-142">Configurer la collaboration sécurisée avec Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cfd4d-142">Set up secure collaboration with Microsoft 365</span></span>](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="cfd4d-143">Paramètres des permissions des invités dans Teams</span><span class="sxs-lookup"><span data-stu-id="cfd4d-143">Block guest users from a specific team</span></span>](/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="cfd4d-144">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="cfd4d-144">Set-CsTeamsClientConfiguration</span></span>](/powershell/module/skype/set-csteamsclientconfiguration)