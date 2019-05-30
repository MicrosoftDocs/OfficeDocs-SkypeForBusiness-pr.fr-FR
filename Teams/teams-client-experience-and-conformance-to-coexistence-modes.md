---
title: Expérience client Teams et conformité aux modes coexistence
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Découverte et transformation du client teams en modes de coexistence
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08bc09ac316a41dfe7ff39bc741dbaa514f30044
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548652"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="5833c-103">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="5833c-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="5833c-104">Cette page décrit les modifications importantes apportées récemment au comportement du client teams lorsque les utilisateurs travaillent dans l’un des modes Skype entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span><span class="sxs-lookup"><span data-stu-id="5833c-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="5833c-105">Le mode de coexistence est d’offrir une utilisation simple et prévisible aux utilisateurs finaux dans le cadre de la transition de Skype entreprise à Teams.</span><span class="sxs-lookup"><span data-stu-id="5833c-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="5833c-106">Dans le cas d’une organisation migrant vers Teams, le mode TeamsOnly est la destination finale de chaque utilisateur, mais tous les utilisateurs ne doivent pas avoir besoin d’être TeamsOnly (ou n’importe quel autre mode) en même temps.</span><span class="sxs-lookup"><span data-stu-id="5833c-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="5833c-107">Dans le cas où les utilisateurs accèdent au mode TeamsOnly, les organisations peuvent utiliser n’importe quel mode Skype entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) pour garantir une communication prévisible entre les utilisateurs TeamsOnly et ceux qui ne le sont pas encore.</span><span class="sxs-lookup"><span data-stu-id="5833c-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="5833c-108">Lorsque l’utilisateur se trouve dans l’un des modes Skype entreprise, toutes les conversations et tous les appels entrants sont acheminés vers le client Skype entreprise de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5833c-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="5833c-109">Afin d’éviter la confusion des utilisateurs finaux et de veiller à ce que le routage, les appels et les discussions appropriés dans le client teams soient désactivés lorsqu’un utilisateur se trouve dans l’un des modes Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="5833c-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="5833c-110">De la même façon, la planification de réunions en équipes est désactivée explicitement lorsque les utilisateurs se trouvent dans les modes SfBOnly ou SfBWithTeamsCollab, et activés de manière explicite lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="5833c-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="5833c-111">Comment les fonctionnalités disponibles dans teams client changent en fonction du mode</span><span class="sxs-lookup"><span data-stu-id="5833c-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="5833c-112">Les fonctionnalités disponibles dans teams dépendent du mode de coexistence de l’utilisateur, tel qu’il est défini par TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="5833c-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="5833c-113">Le tableau ci-dessous résume le comportement:</span><span class="sxs-lookup"><span data-stu-id="5833c-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="5833c-114">Mode d’efficacité de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="5833c-114">User's effective mode</span></span>|<span data-ttu-id="5833c-115">Découvrir le client Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="5833c-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="5833c-116">Tout mode Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="5833c-116">Any Skype for Business mode</span></span>|<span data-ttu-id="5833c-117">Les appels et les discussions sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="5833c-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="5833c-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="5833c-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="5833c-119">La planification de réunion est disponible</span><span class="sxs-lookup"><span data-stu-id="5833c-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="5833c-120">SfBWithTeamsCollab ou SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5833c-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="5833c-121">La planification de la réunion n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="5833c-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="5833c-122">Les captures d’écran ci-dessous illustrent la différence entre le mode TeamsOnly ou le mode îlot et tous les autres modes.</span><span class="sxs-lookup"><span data-stu-id="5833c-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="5833c-123">Notez que les icônes de discussion et d’appels sont disponibles en mode TeamsOnly ou îlots (capture de la gauche), mais pas avec les autres modes (capture d’écran de droite):</span><span class="sxs-lookup"><span data-stu-id="5833c-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Comparaison côte à côte des modes d’équipe](media/teams-mode-comparison.png)


 
<span data-ttu-id="5833c-125">**Remarque:**
<sup>1</sup> pour le moment, SfBwithTeamsCollab et SfBOnly se comportent de la même façon, mais l’intention est pour le mode SfBOnly de désactiver également les fonctionnalités canaux et fichiers dans Teams. en revanche, il n’existe actuellement aucun paramètre permettant de désactiver cette fonctionnalité dans Teams.</span><span class="sxs-lookup"><span data-stu-id="5833c-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="5833c-126">Impact du mode sur les autres paramètres de stratégie</span><span class="sxs-lookup"><span data-stu-id="5833c-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="5833c-127">Comme décrit ci-dessus, les fonctionnalités du mode de coexistence d’un utilisateur sont celles disponibles dans le client teams de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5833c-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="5833c-128">Cela signifie que la valeur du mode peut être prioritaire par rapport à d’autres paramètres de stratégie, en fonction du mode.</span><span class="sxs-lookup"><span data-stu-id="5833c-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="5833c-129">Plus précisément, le mode de coexistence a un impact sur le respect des paramètres de stratégie suivants:</span><span class="sxs-lookup"><span data-stu-id="5833c-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="5833c-130">**Modalité (application)**</span><span class="sxs-lookup"><span data-stu-id="5833c-130">**Modality (App)**</span></span>|<span data-ttu-id="5833c-131">**Policy. Setting**</span><span class="sxs-lookup"><span data-stu-id="5833c-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="5833c-132">Conversation</span><span class="sxs-lookup"><span data-stu-id="5833c-132">Chat</span></span>|<span data-ttu-id="5833c-133">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="5833c-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="5833c-134">Appels</span><span class="sxs-lookup"><span data-stu-id="5833c-134">Calling</span></span>|<span data-ttu-id="5833c-135">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="5833c-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="5833c-136">Planification de réunions</span><span class="sxs-lookup"><span data-stu-id="5833c-136">Meeting scheduling</span></span>|<span data-ttu-id="5833c-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="5833c-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="5833c-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="5833c-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="5833c-139">Les administrateurs ont besoin de *ne pas* définir explicitement ces paramètres de stratégie lors de l’utilisation du mode de coexistence, mais il est important de se familiariser avec ces paramètres comme suit pour un mode donné.</span><span class="sxs-lookup"><span data-stu-id="5833c-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="5833c-140">Veille</span><span class="sxs-lookup"><span data-stu-id="5833c-140">Mode</span></span>|<span data-ttu-id="5833c-141">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="5833c-141">AllowUserChat</span></span>|<span data-ttu-id="5833c-142">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="5833c-142">AllowPrivateCalling</span></span>|<span data-ttu-id="5833c-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="5833c-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="5833c-144">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="5833c-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="5833c-145">TeamsOnly ou îles</span><span class="sxs-lookup"><span data-stu-id="5833c-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="5833c-146">Activé</span><span class="sxs-lookup"><span data-stu-id="5833c-146">Enabled</span></span>|<span data-ttu-id="5833c-147">Activé</span><span class="sxs-lookup"><span data-stu-id="5833c-147">Enabled</span></span>|<span data-ttu-id="5833c-148">Activé</span><span class="sxs-lookup"><span data-stu-id="5833c-148">Enabled</span></span>|<span data-ttu-id="5833c-149">Activé</span><span class="sxs-lookup"><span data-stu-id="5833c-149">Enabled</span></span>|
|<span data-ttu-id="5833c-150">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="5833c-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="5833c-151">Désactivé</span><span class="sxs-lookup"><span data-stu-id="5833c-151">Disabled</span></span>|<span data-ttu-id="5833c-152">Désactivé</span><span class="sxs-lookup"><span data-stu-id="5833c-152">Disabled</span></span>|<span data-ttu-id="5833c-153">Activé</span><span class="sxs-lookup"><span data-stu-id="5833c-153">Enabled</span></span>|<span data-ttu-id="5833c-154">Activé</span><span class="sxs-lookup"><span data-stu-id="5833c-154">Enabled</span></span>|
|<span data-ttu-id="5833c-155">SfBWithTeamsCollab ou SfBOnly</span><span class="sxs-lookup"><span data-stu-id="5833c-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="5833c-156">Désactivé</span><span class="sxs-lookup"><span data-stu-id="5833c-156">Disabled</span></span>|<span data-ttu-id="5833c-157">Désactivé</span><span class="sxs-lookup"><span data-stu-id="5833c-157">Disabled</span></span>|<span data-ttu-id="5833c-158">Désactivé</span><span class="sxs-lookup"><span data-stu-id="5833c-158">Disabled</span></span>|<span data-ttu-id="5833c-159">Désactivé</span><span class="sxs-lookup"><span data-stu-id="5833c-159">Disabled</span></span>|
||||||

<span data-ttu-id="5833c-160">Lors de l’utilisation de `Grant-CsTeamsUpgradePolicy` PowerShell, l’applet de contrôle vérifie la configuration des paramètres correspondants dans TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy pour déterminer si ces paramètres sont remplacés par TeamsUpgradePolicy et, si tel est le cas, un le message d’information est fourni dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5833c-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="5833c-161">Comme indiqué plus haut, il n’est plus nécessaire de définir les autres paramètres de stratégie.</span><span class="sxs-lookup"><span data-stu-id="5833c-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="5833c-162">Vous trouverez ci-dessous un exemple d’avertissement dans PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5833c-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="5833c-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5833c-163">Related topics</span></span>

[<span data-ttu-id="5833c-164">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="5833c-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




