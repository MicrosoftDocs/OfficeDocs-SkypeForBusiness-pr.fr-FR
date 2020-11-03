---
title: Gérer les paramètres de Skype entreprise dans le centre d’administration Microsoft teams
author: lanachin
ms.author: v-lanac
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
description: Découvrez comment gérer les paramètres des fonctionnalités Skype entreprise dans le centre d’administration Microsoft Teams.
ms.openlocfilehash: 0a74b2586fa706dc8fe9db73c58b7d938eae59ee
ms.sourcegitcommit: 54e685b07d1c23100951d46913480989f046d534
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2020
ms.locfileid: "48827758"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="6d7db-103">Gérer les paramètres de Skype entreprise dans le centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="6d7db-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="6d7db-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="6d7db-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="6d7db-105">En tant qu’administrateur, le centre d’administration Microsoft teams vous permet de gérer les fonctionnalités de Skype entreprise pour les utilisateurs Skype entreprise de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d7db-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="6d7db-106">Vous pouvez gérer les paramètres [de votre organisation](#manage-skype-for-business-settings-for-your-organization) dans la page **Skype entreprise** et [les paramètres d’utilisateurs individuels](#manage-skype-for-business-settings-for-individual-users) dans l’onglet **Skype entreprise** de la page de détails de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d7db-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="6d7db-107">La page **Skype entreprise** s’affiche uniquement si le mode de coexistence pour votre organisation n’est pas défini sur **équipes uniquement**.</span><span class="sxs-lookup"><span data-stu-id="6d7db-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="6d7db-108">De même, vous ne verrez que l’onglet **Skype entreprise** pour un utilisateur si le mode de coexistence de l’utilisateur n’est pas l' **équipe**.</span><span class="sxs-lookup"><span data-stu-id="6d7db-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="6d7db-109">Pour en savoir plus sur les modes de coexistence, voir [comprendre les équipes et la coexistence et l’interopérabilité de Skype entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md) et [définir vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6d7db-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6d7db-110">Les paramètres de Skype entreprise étaient auparavant dans le **portail hérité** dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d7db-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6d7db-111">Avec la mise hors service du portail hérité, nous avons migré les paramètres vers ces nouveaux emplacements dans le centre d’administration teams pour la gestion de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="6d7db-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="6d7db-112">Pour pouvoir gérer les fonctionnalités de Skype entreprise dans le centre d’administration de Microsoft Teams, vous devez avoir le rôle d’administrateur [Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de l’administrateur général ou de l’administrateur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="6d7db-112">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="6d7db-113">Gestion des paramètres de Skype entreprise pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="6d7db-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="6d7db-114">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à paramètres à l’échelle de l' **organisation**  >  **Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="6d7db-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="6d7db-115">À partir de cet emplacement, vous pouvez configurer et gérer la diffusion de réunion Skype, la confidentialité de présence et les notifications de périphériques mobiles pour tous les utilisateurs Skype entreprise de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d7db-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="6d7db-116">Diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="6d7db-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="6d7db-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="6d7db-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="6d7db-118">Utilisez les paramètres suivants pour gérer la [diffusion de réunion Skype](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d7db-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Capture d’écran des paramètres de diffusion de réunion Skype dans le centre d’administration":::

- <span data-ttu-id="6d7db-120">**Diffusions de réunion Skype** : activez cette fonction pour activer la diffusion de réunion Skype pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d7db-120">**Skype Meeting Broadcasts** : Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="6d7db-121">Après avoir activé cette fonction, vous devez [configurer votre réseau pour la diffusion de réunion Skype](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span><span class="sxs-lookup"><span data-stu-id="6d7db-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="6d7db-122">Pour accéder en avant-première aux nouvelles fonctionnalités, **voir fonctionnalités d’aperçu** : activez cette fonction.</span><span class="sxs-lookup"><span data-stu-id="6d7db-122">**See preview features** : Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="6d7db-123">Les **organisateurs peuvent planifier des réunions anonymes** : activez cette fonction si vous voulez permettre aux organisateurs de créer des événements de diffusion qui permettent à tout le monde à l’extérieur de votre organisation de participer sans se connecter.</span><span class="sxs-lookup"><span data-stu-id="6d7db-123">**Organizers can schedule anonymous meetings** : Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="6d7db-124">**Enregistrez des réunions de diffusion de réunion Skype** : activez cette fonction pour permettre aux organisateurs et aux présentateurs d’enregistrer les réunions.</span><span class="sxs-lookup"><span data-stu-id="6d7db-124">**Record Skype Meeting Broadcast meetings** : Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="6d7db-125">**URL du support technique pour les participants** : entrez l’URL d’assistance technique de votre organisation pour permettre aux participants de la réunion d’avoir besoin d’aide pendant une réunion.</span><span class="sxs-lookup"><span data-stu-id="6d7db-125">**Helpdesk support URL for attendees** : Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="6d7db-126">Notifications de présence et de téléphone mobile</span><span class="sxs-lookup"><span data-stu-id="6d7db-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="6d7db-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="6d7db-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="6d7db-128">Utilisez les paramètres suivants pour gérer la confidentialité de présence de Skype entreprise et les notifications mobiles au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d7db-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Capture d’écran des paramètres de présence dans le centre d’administration":::

#### <a name="presence"></a><span data-ttu-id="6d7db-130">Présence</span><span class="sxs-lookup"><span data-stu-id="6d7db-130">Presence</span></span>

<span data-ttu-id="6d7db-131">Par défaut, les utilisateurs Skype entreprise de votre organisation peuvent voir le statut de présence (disponible, occupé ou absent) d’autres utilisateurs de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="6d7db-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="6d7db-132">Choisissez l’une des options suivantes pour définir qui peut voir la présence de vos utilisateurs Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="6d7db-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="6d7db-133">**Afficher automatiquement les informations de présence** : tout utilisateur de Skype entreprise de votre organisation qui n’a pas été ajouté à la liste **externe** ou **bloquée** de l’utilisateur peut voir la présence de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d7db-133">**Automatically display presence information** : Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="6d7db-134">**Afficher les informations de présence uniquement aux contacts d’un utilisateur** : tout utilisateur Skype entreprise dans la liste des contacts de l’utilisateur qui n’est pas ajouté à sa liste des contacts **externes** ou **bloqués** peut voir la présence de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d7db-134">**Display presence information only to a user's contacts** : Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="6d7db-135">Les utilisateurs peuvent ignorer ce paramètre dans Skype entreprise en accédant aux **Settings**  >  **Tools**  >  **options** outils de configuration.</span><span class="sxs-lookup"><span data-stu-id="6d7db-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="6d7db-136">Notifications mobiles</span><span class="sxs-lookup"><span data-stu-id="6d7db-136">Mobile notifications</span></span>

<span data-ttu-id="6d7db-137">Vous pouvez déterminer si vos utilisateurs mobiles Skype entreprise reçoivent des alertes concernant les messages instantanés entrants et manqués, les messages vocaux et les appels en absence via un service de notifications de transmission.</span><span class="sxs-lookup"><span data-stu-id="6d7db-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="6d7db-138">En fonction des appareils mobiles utilisés dans votre organisation, vous pouvez utiliser le **service de notification Microsoft émission** , le **service de notifications de transmission d’Apple** ou les deux.</span><span class="sxs-lookup"><span data-stu-id="6d7db-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service** , the **Apple Push Notification Service** , or both.</span></span>

<span data-ttu-id="6d7db-139">Tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="6d7db-139">Keep the following in mind:</span></span>

- <span data-ttu-id="6d7db-140">Si vous désactivez les notifications de transmission, les utilisateurs recevront toutes les alertes lors du prochain démarrage de Skype entreprise sur leur appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="6d7db-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="6d7db-141">Par défaut, les notifications de transmission sont activées.</span><span class="sxs-lookup"><span data-stu-id="6d7db-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="6d7db-142">Les utilisateurs individuels peuvent les désactiver dans Skype entreprise sur leur appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="6d7db-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="6d7db-143">Une fois les notifications Push désactivées, les utilisateurs ne peuvent plus les réactiver.</span><span class="sxs-lookup"><span data-stu-id="6d7db-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6d7db-144">Microsoft utilise d'autres sociétés pour fournir des notifications Skype Entreprise pour appareils mobiles en temps réel aux utilisateurs de Windows Phone, iPhone et iPad.</span><span class="sxs-lookup"><span data-stu-id="6d7db-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="6d7db-145">Consultez cette déclaration sur le respect de la [vie privée](https://go.microsoft.com/fwlink/p/?linkid=247732).</span><span class="sxs-lookup"><span data-stu-id="6d7db-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="6d7db-146">Gestion des paramètres de Skype entreprise pour les utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="6d7db-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="6d7db-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="6d7db-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="6d7db-148">Pour gérer les paramètres de Skype entreprise pour les utilisateurs individuels, dans le volet de navigation de gauche du centre d’administration Teams, accédez à **utilisateurs** , cliquez sur le nom complet de l’utilisateur pour ouvrir la page des détails de l’utilisateur, puis sélectionnez l’onglet **paramètres de Skype entreprise** . À partir de cet emplacement, vous pouvez configurer l’accès externe et les paramètres de réunion pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d7db-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users** , click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Capture d’écran de l’onglet Skype entreprise sur la page des détails de l’utilisateur":::

### <a name="external-access-settings"></a><span data-ttu-id="6d7db-150">Paramètres d’accès externe</span><span class="sxs-lookup"><span data-stu-id="6d7db-150">External access settings</span></span>

<span data-ttu-id="6d7db-151">Vous pouvez autoriser ou bloquer de manière sélective si un utilisateur peut communiquer avec des personnes extérieures à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d7db-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="6d7db-152">**Utilisateurs Skype entreprise externes** : activez cette fonction si vous voulez autoriser l’utilisateur à communiquer avec des utilisateurs de Skype entreprise dans des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="6d7db-152">**External Skype for Business users** : Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="6d7db-153">**Utilisateurs Skype externes** : activez cette fonction si vous voulez autoriser l’utilisateur à communiquer avec des utilisateurs de Skype.</span><span class="sxs-lookup"><span data-stu-id="6d7db-153">**External Skype users** : Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="6d7db-154">Paramètres de la réunion</span><span class="sxs-lookup"><span data-stu-id="6d7db-154">Meeting settings</span></span>

<span data-ttu-id="6d7db-155">Vous pouvez configurer les paramètres de réunion suivants pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6d7db-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="6d7db-156">**Audio & vidéo** : choisissez l’un des paramètres audio et vidéo suivants :</span><span class="sxs-lookup"><span data-stu-id="6d7db-156">**Audio & Video** : Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="6d7db-157">**Aucun** : l’utilisateur ne peut pas utiliser l’audio ou la vidéo.</span><span class="sxs-lookup"><span data-stu-id="6d7db-157">**None** : User can't use audio or video.</span></span>
    - <span data-ttu-id="6d7db-158">**Audio uniquement** : l’utilisateur peut utiliser le son, mais pas la vidéo.</span><span class="sxs-lookup"><span data-stu-id="6d7db-158">**Audio only** : User can use audio but not video.</span></span>
    - <span data-ttu-id="6d7db-159">**Audio et vidéo** : l’utilisateur peut utiliser les fonctionnalités audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="6d7db-159">**Audio and video** : User can use audio and video.</span></span>
    - <span data-ttu-id="6d7db-160">**Audio et vidéo (HD)** : l’utilisateur peut utiliser le son et la vidéo haute définition.</span><span class="sxs-lookup"><span data-stu-id="6d7db-160">**Audio and video (HD)** : User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="6d7db-161">**Enregistrer des conversations & des réunions** : activez cette fonction pour permettre à l’utilisateur d’enregistrer des conversations et des réunions.</span><span class="sxs-lookup"><span data-stu-id="6d7db-161">**Record conversations & meetings** : Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="6d7db-162">**Conformité** : activez cette fonction si vous êtes légalement tenu de conserver les informations stockées électroniquement.</span><span class="sxs-lookup"><span data-stu-id="6d7db-162">**Compliance** : Turn this on if you're legally required to retain electronically stored information.</span></span> 
