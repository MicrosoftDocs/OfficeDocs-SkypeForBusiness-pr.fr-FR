---
title: Expérience client Teams et conformité aux modes coexistence
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: En savoir plus sur l’expérience du client Teams et la conformité aux modes de coexistence (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e07d33b8aa1b379823ffa3aaa605dc26c31604c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119253"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="88a21-103">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="88a21-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="88a21-104">L’objectif des modes de coexistence Skype Entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) est d’offrir aux utilisateurs finaux une expérience simple et prévisible au sein de la transition entre Skype Entreprise et Teams au sein des organisations.</span><span class="sxs-lookup"><span data-stu-id="88a21-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="88a21-105">Pour une organisation qui passe à Teams, le mode **Teams** uniquement est la destination finale pour chaque utilisateur, même si tous ne doivent pas être affectés à **Teams** uniquement (ou tout autre mode) en même temps.</span><span class="sxs-lookup"><span data-stu-id="88a21-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="88a21-106">Avant que les utilisateurs n’atteignent le mode TeamsOnly, les organisations peuvent utiliser n’importe quel mode de coexistence Skype Entreprise pour assurer une communication prévisible entre les utilisateurs qui utilisent **Teams** uniquement et ceux qui ne le sont pas encore.</span><span class="sxs-lookup"><span data-stu-id="88a21-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="88a21-107">Lorsqu’un utilisateur est dans l’un des modes Skype Entreprise, toutes les conversations et appels entrants sont acheminés vers le client Skype Entreprise de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="88a21-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="88a21-108">Pour éviter la confusion des utilisateurs finaux et assurer un routage approprié, les fonctionnalités d’appel et de conversation dans le client Teams sont désactivées lorsqu’un utilisateur est dans l’un des modes Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="88a21-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="88a21-109">De même, la planification de réunions dans Teams est explicitement désactivée lorsque les utilisateurs sont dans les modes SfBOnly ou SfBWithTeamsCollab et sont explicitement activés lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="88a21-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="88a21-110">Étant donné que la présence est une indication de l’accessibilité par le biais de la conversation et des appels, lorsque la conversation et les appels sont désactivés, la présence autonome dans Teams (autrement dit, l’affichage de sa propre présence dans le client Teams dans l’image de l’utilisateur) est également masquée.</span><span class="sxs-lookup"><span data-stu-id="88a21-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="88a21-111">Changement des fonctionnalités disponibles dans le client Teams en fonction du mode</span><span class="sxs-lookup"><span data-stu-id="88a21-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="88a21-112">Les fonctionnalités disponibles dans Teams dépendent du mode de coexistence de l’utilisateur, tel que le définisse TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="88a21-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="88a21-113">Le tableau suivant résume le comportement :</span><span class="sxs-lookup"><span data-stu-id="88a21-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="88a21-114">Mode effectif de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="88a21-114">User's effective mode</span></span>|<span data-ttu-id="88a21-115">Expérience client Teams</span><span class="sxs-lookup"><span data-stu-id="88a21-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="88a21-116">N’importe quel mode Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="88a21-116">Any Skype for Business mode</span></span>|<span data-ttu-id="88a21-117">Les appels, les discussions et la présence autonome sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="88a21-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="88a21-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="88a21-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="88a21-119">La planification de réunion est disponible</span><span class="sxs-lookup"><span data-stu-id="88a21-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="88a21-120">SfBWithTeamsCollab ou SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="88a21-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="88a21-121">La planification de réunion n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="88a21-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="88a21-122">Les captures d’écran suivantes illustrent la différence entre le mode **Teams uniquement** ou **Islands** et tous les autres modes.</span><span class="sxs-lookup"><span data-stu-id="88a21-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="88a21-123">Notez que les icônes de conversation et d’appel sont disponibles par défaut avec le mode **Équipes** uniquement ou **Îles** (capture d’écran de gauche), mais pas avec les autres modes (capture d’écran de droite) :</span><span class="sxs-lookup"><span data-stu-id="88a21-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Comparaison côte à côte des modes Teams](media/teams-mode-comparison.png)

<span data-ttu-id="88a21-125">De plus, la présence automatique n’est pas disponible dans les autres modes, comme illustré ici.</span><span class="sxs-lookup"><span data-stu-id="88a21-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![Capture d’écran de l’auto-présence dans Réunions Tout d’abord](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="88a21-127">**Remarque :** 
 <sup>1</sup> Pour le moment, SfBwithTeamsCollab et SfBOnly se comportent à l’identique, mais l’objectif est que le mode SfBOnly désactive également la fonctionnalité Canaux et fichiers dans Teams.</span><span class="sxs-lookup"><span data-stu-id="88a21-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="88a21-128">Les canaux peuvent être masqués temporairement à l’aide de la stratégie Autorisations d’application.</span><span class="sxs-lookup"><span data-stu-id="88a21-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="88a21-129">Impact du mode sur les autres paramètres de stratégie</span><span class="sxs-lookup"><span data-stu-id="88a21-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="88a21-130">Comme décrit ci-dessus, le mode de coexistence d’un utilisateur a une incidence sur la fonctionnalité disponible dans le client Teams de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="88a21-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="88a21-131">Cela signifie que la valeur du mode peut être prioritaire sur la valeur des autres paramètres de stratégie, selon le mode.</span><span class="sxs-lookup"><span data-stu-id="88a21-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="88a21-132">Plus précisément, le mode de coexistence a un impact si les paramètres de stratégie suivants sont respecter :</span><span class="sxs-lookup"><span data-stu-id="88a21-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="88a21-133">**Modalité (Application)**</span><span class="sxs-lookup"><span data-stu-id="88a21-133">**Modality (App)**</span></span>|<span data-ttu-id="88a21-134">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="88a21-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="88a21-135">Conversation</span><span class="sxs-lookup"><span data-stu-id="88a21-135">Chat</span></span>|<span data-ttu-id="88a21-136">TeamsMesspolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="88a21-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="88a21-137">Appel</span><span class="sxs-lookup"><span data-stu-id="88a21-137">Calling</span></span>|<span data-ttu-id="88a21-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="88a21-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="88a21-139">Planification de réunions</span><span class="sxs-lookup"><span data-stu-id="88a21-139">Meeting scheduling</span></span>|<span data-ttu-id="88a21-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="88a21-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="88a21-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="88a21-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="88a21-142">Les administrateurs n’ont pas besoin de définir explicitement ces paramètres de stratégie lors de l’utilisation du mode de co-existence, mais il est important de comprendre que ces paramètres se comportent de façon efficace comme suit pour un mode donné. </span><span class="sxs-lookup"><span data-stu-id="88a21-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="88a21-143">Mode</span><span class="sxs-lookup"><span data-stu-id="88a21-143">Mode</span></span>|<span data-ttu-id="88a21-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="88a21-144">AllowUserChat</span></span>|<span data-ttu-id="88a21-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="88a21-145">AllowPrivateCalling</span></span>|<span data-ttu-id="88a21-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="88a21-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="88a21-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="88a21-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="88a21-148">TeamsOnly ou Islands</span><span class="sxs-lookup"><span data-stu-id="88a21-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="88a21-149">Activé</span><span class="sxs-lookup"><span data-stu-id="88a21-149">Enabled</span></span>|<span data-ttu-id="88a21-150">Activé</span><span class="sxs-lookup"><span data-stu-id="88a21-150">Enabled</span></span>|<span data-ttu-id="88a21-151">Activé</span><span class="sxs-lookup"><span data-stu-id="88a21-151">Enabled</span></span>|<span data-ttu-id="88a21-152">Activé</span><span class="sxs-lookup"><span data-stu-id="88a21-152">Enabled</span></span>|
|<span data-ttu-id="88a21-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="88a21-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="88a21-154">Désactivé</span><span class="sxs-lookup"><span data-stu-id="88a21-154">Disabled</span></span>|<span data-ttu-id="88a21-155">Désactivé</span><span class="sxs-lookup"><span data-stu-id="88a21-155">Disabled</span></span>|<span data-ttu-id="88a21-156">Activé</span><span class="sxs-lookup"><span data-stu-id="88a21-156">Enabled</span></span>|<span data-ttu-id="88a21-157">Activé</span><span class="sxs-lookup"><span data-stu-id="88a21-157">Enabled</span></span>|
|<span data-ttu-id="88a21-158">SfBWithTeamsCollab ou SfBOnly</span><span class="sxs-lookup"><span data-stu-id="88a21-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="88a21-159">Désactivé</span><span class="sxs-lookup"><span data-stu-id="88a21-159">Disabled</span></span>|<span data-ttu-id="88a21-160">Désactivé</span><span class="sxs-lookup"><span data-stu-id="88a21-160">Disabled</span></span>|<span data-ttu-id="88a21-161">Désactivé</span><span class="sxs-lookup"><span data-stu-id="88a21-161">Disabled</span></span>|<span data-ttu-id="88a21-162">Désactivé</span><span class="sxs-lookup"><span data-stu-id="88a21-162">Disabled</span></span>|
||||||

<span data-ttu-id="88a21-163">Lors de l’utilisation de PowerShell, l’cmdlet vérifie la configuration des `Grant-CsTeamsUpgradePolicy` paramètres correspondants dans TeamsMess niveauPolicy, TeamsCallingPolicy et TeamsMeetingPolicy pour déterminer si ces paramètres doivent être suivis par TeamsUpgradePolicy et, si c’est le cas, un message d’information est fourni dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88a21-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="88a21-164">Comme indiqué ci-dessus, il n’est plus nécessaire de définir ces autres paramètres de stratégie.</span><span class="sxs-lookup"><span data-stu-id="88a21-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="88a21-165">Voici un exemple de l’avertissement PowerShell :</span><span class="sxs-lookup"><span data-stu-id="88a21-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="88a21-166">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="88a21-166">Related topics</span></span>

[<span data-ttu-id="88a21-167">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="88a21-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)