---
title: Expérience client Teams et conformité aux modes coexistence
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Expérience client Teams et conformité aux modes coexistence
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e2687f00a2d0ccb02e742d5077e472aa1dc37ed
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706614"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="be5a7-103">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="be5a7-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="be5a7-104">L’objectif des modes de coexistence Skype entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) est d’offrir une interface simple et prévisible aux utilisateurs finaux lors de la transition de Skype entreprise à Teams.</span><span class="sxs-lookup"><span data-stu-id="be5a7-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="be5a7-105">Dans le cas d’une organisation qui migre vers Teams, le mode **équipes uniquement** représente la destination finale de chaque utilisateur, mais tous les utilisateurs ne doivent pas être disposant **uniquement d’équipes** (ou d’autres modes) en même temps.</span><span class="sxs-lookup"><span data-stu-id="be5a7-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="be5a7-106">Avant d’atteindre le mode TeamsOnly, les organisations peuvent utiliser n’importe quel mode de coexistence Skype entreprise pour garantir une communication prévisible entre les utilisateurs qui sont des **équipes uniquement** et ceux qui ne le sont pas encore.</span><span class="sxs-lookup"><span data-stu-id="be5a7-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="be5a7-107">Lorsque l’utilisateur se trouve dans l’un des modes Skype entreprise, toutes les conversations et tous les appels entrants sont acheminés vers le client Skype entreprise de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="be5a7-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="be5a7-108">Afin d’éviter la confusion des utilisateurs finaux et de veiller à ce que le routage, les appels et les discussions appropriés dans le client teams soient désactivés lorsqu’un utilisateur se trouve dans l’un des modes Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="be5a7-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="be5a7-109">De la même façon, la planification de réunions en équipes est désactivée explicitement lorsque les utilisateurs se trouvent dans les modes SfBOnly ou SfBWithTeamsCollab, et activés de manière explicite lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="be5a7-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="be5a7-110">Dans la mesure où la présence est une indication d’une accessibilité par le biais d’une conversation ou d’un appel, lorsque les discussions et les appels sont désactivés, la présence automatique dans Teams (autrement dit, l’affichage de la propre présence d’une personne dans teams dans l’image de l’utilisateur) est également cachée.</span><span class="sxs-lookup"><span data-stu-id="be5a7-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="be5a7-111">Comment les fonctionnalités disponibles dans teams client changent en fonction du mode</span><span class="sxs-lookup"><span data-stu-id="be5a7-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="be5a7-112">Les fonctionnalités disponibles dans teams dépendent du mode de coexistence de l’utilisateur, tel qu’il est défini par TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="be5a7-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="be5a7-113">Le tableau suivant récapitule le comportement :</span><span class="sxs-lookup"><span data-stu-id="be5a7-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="be5a7-114">Mode d’efficacité de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="be5a7-114">User's effective mode</span></span>|<span data-ttu-id="be5a7-115">Découvrir le client Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="be5a7-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="be5a7-116">Tout mode Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="be5a7-116">Any Skype for Business mode</span></span>|<span data-ttu-id="be5a7-117">Les appels, les discussions et la présence automatique sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="be5a7-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="be5a7-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="be5a7-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="be5a7-119">La planification de réunion est disponible</span><span class="sxs-lookup"><span data-stu-id="be5a7-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="be5a7-120">SfBWithTeamsCollab ou SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="be5a7-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="be5a7-121">La planification de la réunion n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="be5a7-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="be5a7-122">Les captures d’écran suivantes montrent la différence entre les **équipes uniquement** ou le mode **îlot** et tous les autres modes.</span><span class="sxs-lookup"><span data-stu-id="be5a7-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="be5a7-123">Notez que les icônes de discussion et d’appels sont disponibles par défaut avec les **équipes uniquement** ou le mode **îlots** (capture vers la gauche), mais pas pour les autres modes (capture d’écran droite) :</span><span class="sxs-lookup"><span data-stu-id="be5a7-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Comparaison côte à côte des modes d’équipe](media/teams-mode-comparison.png)

<span data-ttu-id="be5a7-125">De plus, la présence automatique n’est pas disponible dans les autres modes, comme le montre l’illustration ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="be5a7-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![Capture d’écran de l’auto-présence dans les réunions](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="be5a7-127">**Remarque :**
<sup>1</sup> pour le moment, SfBwithTeamsCollab et SfBOnly se comportent de la même façon, mais l’intention est pour le mode SfBOnly de désactiver également les fonctionnalités canaux et fichiers dans Teams.</span><span class="sxs-lookup"><span data-stu-id="be5a7-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="be5a7-128">Par intérim, les canaux peuvent être masqués à l’aide de la stratégie d’autorisations des applications.</span><span class="sxs-lookup"><span data-stu-id="be5a7-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="be5a7-129">Impact du mode sur les autres paramètres de stratégie</span><span class="sxs-lookup"><span data-stu-id="be5a7-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="be5a7-130">Comme décrit ci-dessus, les fonctionnalités du mode de coexistence d’un utilisateur sont celles disponibles dans le client teams de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="be5a7-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="be5a7-131">Cela signifie que la valeur du mode peut être prioritaire par rapport à d’autres paramètres de stratégie, en fonction du mode.</span><span class="sxs-lookup"><span data-stu-id="be5a7-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="be5a7-132">Plus précisément, le mode de coexistence a un impact sur le respect des paramètres de stratégie suivants :</span><span class="sxs-lookup"><span data-stu-id="be5a7-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="be5a7-133">**Modalité (application)**</span><span class="sxs-lookup"><span data-stu-id="be5a7-133">**Modality (App)**</span></span>|<span data-ttu-id="be5a7-134">**Policy. Setting**</span><span class="sxs-lookup"><span data-stu-id="be5a7-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="be5a7-135">Conversation</span><span class="sxs-lookup"><span data-stu-id="be5a7-135">Chat</span></span>|<span data-ttu-id="be5a7-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="be5a7-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="be5a7-137">Appels</span><span class="sxs-lookup"><span data-stu-id="be5a7-137">Calling</span></span>|<span data-ttu-id="be5a7-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="be5a7-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="be5a7-139">Planification de réunions</span><span class="sxs-lookup"><span data-stu-id="be5a7-139">Meeting scheduling</span></span>|<span data-ttu-id="be5a7-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="be5a7-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="be5a7-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="be5a7-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="be5a7-142">Les administrateurs ont besoin de *ne pas* définir explicitement ces paramètres de stratégie lors de l’utilisation du mode de coexistence, mais il est important de se familiariser avec ces paramètres comme suit pour un mode donné.</span><span class="sxs-lookup"><span data-stu-id="be5a7-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="be5a7-143">Veille</span><span class="sxs-lookup"><span data-stu-id="be5a7-143">Mode</span></span>|<span data-ttu-id="be5a7-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="be5a7-144">AllowUserChat</span></span>|<span data-ttu-id="be5a7-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="be5a7-145">AllowPrivateCalling</span></span>|<span data-ttu-id="be5a7-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="be5a7-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="be5a7-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="be5a7-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="be5a7-148">TeamsOnly ou îles</span><span class="sxs-lookup"><span data-stu-id="be5a7-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="be5a7-149">Activé</span><span class="sxs-lookup"><span data-stu-id="be5a7-149">Enabled</span></span>|<span data-ttu-id="be5a7-150">Activé</span><span class="sxs-lookup"><span data-stu-id="be5a7-150">Enabled</span></span>|<span data-ttu-id="be5a7-151">Activé</span><span class="sxs-lookup"><span data-stu-id="be5a7-151">Enabled</span></span>|<span data-ttu-id="be5a7-152">Activé</span><span class="sxs-lookup"><span data-stu-id="be5a7-152">Enabled</span></span>|
|<span data-ttu-id="be5a7-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="be5a7-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="be5a7-154">Désactivé</span><span class="sxs-lookup"><span data-stu-id="be5a7-154">Disabled</span></span>|<span data-ttu-id="be5a7-155">Désactivé</span><span class="sxs-lookup"><span data-stu-id="be5a7-155">Disabled</span></span>|<span data-ttu-id="be5a7-156">Activé</span><span class="sxs-lookup"><span data-stu-id="be5a7-156">Enabled</span></span>|<span data-ttu-id="be5a7-157">Activé</span><span class="sxs-lookup"><span data-stu-id="be5a7-157">Enabled</span></span>|
|<span data-ttu-id="be5a7-158">SfBWithTeamsCollab ou SfBOnly</span><span class="sxs-lookup"><span data-stu-id="be5a7-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="be5a7-159">Désactivé</span><span class="sxs-lookup"><span data-stu-id="be5a7-159">Disabled</span></span>|<span data-ttu-id="be5a7-160">Désactivé</span><span class="sxs-lookup"><span data-stu-id="be5a7-160">Disabled</span></span>|<span data-ttu-id="be5a7-161">Désactivé</span><span class="sxs-lookup"><span data-stu-id="be5a7-161">Disabled</span></span>|<span data-ttu-id="be5a7-162">Désactivé</span><span class="sxs-lookup"><span data-stu-id="be5a7-162">Disabled</span></span>|
||||||

<span data-ttu-id="be5a7-163">Lors de l’utilisation de `Grant-CsTeamsUpgradePolicy` PowerShell, l’applet de contrôle vérifie la configuration des paramètres correspondants dans TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy pour déterminer si ces paramètres sont remplacés par TeamsUpgradePolicy et, si tel est le cas, un message d’information est fourni dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be5a7-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="be5a7-164">Comme indiqué plus haut, il n’est plus nécessaire de définir les autres paramètres de stratégie.</span><span class="sxs-lookup"><span data-stu-id="be5a7-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="be5a7-165">Voici un exemple d’avertissement de PowerShell :</span><span class="sxs-lookup"><span data-stu-id="be5a7-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="be5a7-166">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="be5a7-166">Related topics</span></span>

[<span data-ttu-id="be5a7-167">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="be5a7-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




