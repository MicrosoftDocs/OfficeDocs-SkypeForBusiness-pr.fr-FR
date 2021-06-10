---
title: Gérer Skype Entreprise de données dans le Centre Microsoft Teams’administration
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment gérer les paramètres des fonctionnalités Skype Entreprise dans le Centre Microsoft Teams’administration.
ms.openlocfilehash: 6e1052b4f4a0e85d4d18123b3c0a0f051f6065f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117002"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="aabf0-103">Gérer Skype Entreprise de données dans le Centre Microsoft Teams’administration</span><span class="sxs-lookup"><span data-stu-id="aabf0-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="aabf0-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="aabf0-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="aabf0-105">En tant qu’administrateur, Microsoft Teams centre d’administration vous permet de gérer Skype Entreprise fonctionnalités pour les Skype Entreprise utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="aabf0-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="aabf0-106">Vous pouvez gérer les [paramètres](#manage-skype-for-business-settings-for-your-organization) de votre organisation sur la page **Skype Entreprise** et les [paramètres](#manage-skype-for-business-settings-for-individual-users) des utilisateurs individuels dans **l’onglet** Skype Entreprise des pages de détails de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="aabf0-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="aabf0-107">Vous verrez uniquement la page **Skype Entreprise** de coexistence si le mode de coexistence pour votre organisation n’est pas **Teams.**</span><span class="sxs-lookup"><span data-stu-id="aabf0-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="aabf0-108">De même, vous ne verrez l’onglet **Skype Entreprise** de l’utilisateur que si le mode de coexistence de l’utilisateur n’est **pas Teams uniquement.**</span><span class="sxs-lookup"><span data-stu-id="aabf0-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="aabf0-109">Pour en savoir plus sur les modes de coexistence, voir Comprendre Teams et [Skype Entreprise coexistence](teams-and-skypeforbusiness-coexistence-and-interoperability.md) et l’interopérabilité, et Définir vos paramètres de coexistence et [de mise à niveau.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="aabf0-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="aabf0-110">Skype Entreprise de gestion de données étaient auparavant dans **le portail hérité** du Centre Microsoft Teams’administration.</span><span class="sxs-lookup"><span data-stu-id="aabf0-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="aabf0-111">Avec l’abandon de l’ancien portail, nous avons migré les paramètres vers ces nouveaux emplacements dans le centre d’administration Teams pour Skype Entreprise gestion.</span><span class="sxs-lookup"><span data-stu-id="aabf0-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="aabf0-112">Le rôle d’administrateur [Azure AD](/azure/active-directory/roles/permissions-reference) de l’administrateur global ou de l’administrateur de Skype Entreprise doit vous aider à gérer les fonctionnalités de gestion des Skype Entreprise dans le Microsoft Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="aabf0-112">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="aabf0-113">Gérer Skype Entreprise de gestion des paramètres pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="aabf0-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="aabf0-114">Dans le panneau de navigation gauche du Microsoft Teams d’administration, voir **Paramètres à** l’échelle de l’organisation  >  **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="aabf0-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="aabf0-115">À partir de là, vous pouvez configurer et gérer la diffusion Réunion Skype, la confidentialité des informations de présence et les notifications sur les appareils mobiles pour tous les Skype Entreprise utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="aabf0-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="aabf0-116">Diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="aabf0-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="aabf0-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="aabf0-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="aabf0-118">Utilisez les paramètres suivants pour gérer [Réunion Skype diffusion](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="aabf0-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Capture d’écran Réunion Skype paramètres de diffusion dans le Centre d’administration":::

- <span data-ttu-id="aabf0-120">**Réunion Skype diffusions :** activez cette fonction pour activer Réunion Skype diffusion pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="aabf0-120">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="aabf0-121">Après avoir activé cette fonctionnalité, vous devez configurer votre réseau pour [Réunion Skype diffusion.](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)</span><span class="sxs-lookup"><span data-stu-id="aabf0-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="aabf0-122">**Découvrez les fonctionnalités d’aperçu**: vous pouvez l’activer pour accéder en avant-première aux nouvelles fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="aabf0-122">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="aabf0-123">**Les organisateurs peuvent planifier** des réunions anonymes : activer cette fonction si vous souhaitez que les organisateurs créent des événements de diffusion qui permettent à tous les utilisateurs extérieurs à votre organisation de participer sans avoir à se connecter.</span><span class="sxs-lookup"><span data-stu-id="aabf0-123">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="aabf0-124">**Enregistrer Réunion Skype diffusion de réunions**: activez cette fonction pour permettre aux organisateurs et aux présentateurs d’enregistrer les réunions.</span><span class="sxs-lookup"><span data-stu-id="aabf0-124">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="aabf0-125">**URL du support** technique pour les participants : Entrez l’URL du support technique que les participants à la réunion peuvent utiliser s’ils ont besoin d’aide pendant une réunion.</span><span class="sxs-lookup"><span data-stu-id="aabf0-125">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="aabf0-126">Notifications de présence et de téléphone mobile</span><span class="sxs-lookup"><span data-stu-id="aabf0-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="aabf0-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="aabf0-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="aabf0-128">Utilisez les paramètres suivants pour gérer les notifications Skype Entreprise confidentialité de la présence mobile et les notifications mobiles dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="aabf0-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Capture d’écran des paramètres de présence dans le Centre d’administration":::

#### <a name="presence"></a><span data-ttu-id="aabf0-130">Présence</span><span class="sxs-lookup"><span data-stu-id="aabf0-130">Presence</span></span>

<span data-ttu-id="aabf0-131">Par défaut, Skype Entreprise utilisateurs de votre organisation peuvent voir le statut de présence (par exemple Disponible, Occupé(e) ou Absent(e) d’autres Skype Entreprise utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="aabf0-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="aabf0-132">Choisissez l’une des personnes suivantes pour définir qui peut voir la présence de vos Skype Entreprise utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="aabf0-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="aabf0-133">**Afficher automatiquement** les informations de présence : tout Skype Entreprise utilisateur de votre organisation qui  n’a pas été ajouté à la liste des utilisateurs externes ou bloqués peut voir sa présence. </span><span class="sxs-lookup"><span data-stu-id="aabf0-133">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="aabf0-134">Afficher les informations de présence uniquement aux **contacts d’un** utilisateur : tout utilisateur Skype Entreprise dans  la  liste des contacts de l’utilisateur qui n’est pas ajouté à sa liste externe ou bloquée peut voir la présence de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="aabf0-134">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="aabf0-135">Les utilisateurs peuvent remplacer ce paramètre dans Skype Entreprise en vous Paramètres  >  **Options**  >  **outils.**</span><span class="sxs-lookup"><span data-stu-id="aabf0-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="aabf0-136">Notifications mobiles</span><span class="sxs-lookup"><span data-stu-id="aabf0-136">Mobile notifications</span></span>

<span data-ttu-id="aabf0-137">Vous pouvez définir si vos utilisateurs mobiles Skype Entreprise recevoir des alertes concernant les messages instantanés entrants et manqués, les messages vocaux et les appels manqués via un service de notifications Push.</span><span class="sxs-lookup"><span data-stu-id="aabf0-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="aabf0-138">En fonction des appareils mobiles utilisés dans votre organisation, vous pouvez utiliser le service de notifications Push **Microsoft,** le service de **notifications Push Apple,** ou les deux.</span><span class="sxs-lookup"><span data-stu-id="aabf0-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="aabf0-139">Tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="aabf0-139">Keep the following in mind:</span></span>

- <span data-ttu-id="aabf0-140">Si vous désactiver les notifications Push, les utilisateurs recevront toutes les alertes la prochaine fois qu’ils démarreront Skype Entreprise sur leur appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="aabf0-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="aabf0-141">Par défaut, les notifications Push sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="aabf0-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="aabf0-142">Les utilisateurs individuels peuvent les désactiver Skype Entreprise sur leur appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="aabf0-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="aabf0-143">Une fois les notifications Push désactivées, les utilisateurs ne peuvent plus les réactiver.</span><span class="sxs-lookup"><span data-stu-id="aabf0-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="aabf0-144">Microsoft utilise d'autres sociétés pour fournir des notifications Skype Entreprise pour appareils mobiles en temps réel aux utilisateurs de Windows Phone, iPhone et iPad.</span><span class="sxs-lookup"><span data-stu-id="aabf0-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="aabf0-145">Consultez cette [déclaration de confidentialité.](https://go.microsoft.com/fwlink/p/?linkid=247732)</span><span class="sxs-lookup"><span data-stu-id="aabf0-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="aabf0-146">Gérer les Skype Entreprise de gestion des utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="aabf0-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="aabf0-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="aabf0-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="aabf0-148">Pour gérer les paramètres de Skype Entreprise d’utilisateurs individuels, dans le navigation gauche du Centre d’administration Teams, sélectionnez Utilisateurs, cliquez sur le nom complet de l’utilisateur pour ouvrir la page des détails de l’utilisateur, puis sélectionnez l’onglet **paramètres Skype Entreprise.** À partir de là, vous pouvez configurer l’accès externe et les paramètres de réunion pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="aabf0-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Capture d’écran Skype Entreprise’onglet accueil sur la page de détails de l’utilisateur":::

### <a name="external-access-settings"></a><span data-ttu-id="aabf0-150">Paramètres d’accès externe</span><span class="sxs-lookup"><span data-stu-id="aabf0-150">External access settings</span></span>

<span data-ttu-id="aabf0-151">Vous pouvez autoriser ou bloquer de manière sélective la communication d’un utilisateur avec des personnes extérieures à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="aabf0-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="aabf0-152">**Utilisateurs Skype Entreprise** externes : activer cette fonction si vous voulez autoriser l’utilisateur à communiquer avec d Skype Entreprise utilisateurs dans des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="aabf0-152">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="aabf0-153">**Utilisateurs Skype externes**: activer cette fonction si vous voulez autoriser l’utilisateur à communiquer avec Skype utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="aabf0-153">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="aabf0-154">Paramètres de réunion</span><span class="sxs-lookup"><span data-stu-id="aabf0-154">Meeting settings</span></span>

<span data-ttu-id="aabf0-155">Vous pouvez configurer les paramètres de réunion suivants pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="aabf0-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="aabf0-156">**Vidéo & :** choisissez l’un des paramètres audio et vidéo suivants :</span><span class="sxs-lookup"><span data-stu-id="aabf0-156">**Audio & Video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="aabf0-157">**Aucun**: l’utilisateur ne peut pas utiliser l’audio ou la vidéo.</span><span class="sxs-lookup"><span data-stu-id="aabf0-157">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="aabf0-158">**Audio uniquement**: l’utilisateur peut utiliser l’audio, mais pas la vidéo.</span><span class="sxs-lookup"><span data-stu-id="aabf0-158">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="aabf0-159">**Audio et vidéo**: l’utilisateur peut utiliser l’audio et la vidéo.</span><span class="sxs-lookup"><span data-stu-id="aabf0-159">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="aabf0-160">**Audio et vidéo (HD)**: l’utilisateur peut utiliser l’audio et la vidéo haute définition.</span><span class="sxs-lookup"><span data-stu-id="aabf0-160">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="aabf0-161">**Enregistrer des conversations & réunions**: activer cette fonction pour permettre à l’utilisateur d’enregistrer des conversations et des réunions.</span><span class="sxs-lookup"><span data-stu-id="aabf0-161">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="aabf0-162">**Conformité**: Activer cette fonction si vous êtes légalement tenu de conserver les informations stockées électroniquement.</span><span class="sxs-lookup"><span data-stu-id="aabf0-162">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span>