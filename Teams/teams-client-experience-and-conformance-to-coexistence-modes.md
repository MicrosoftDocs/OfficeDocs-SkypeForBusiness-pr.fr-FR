---
title: Expérience client Teams et conformité aux modes coexistence
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Équipes de l’expérience client et comformance aux modes de coexistence
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91a67c7fb9afb5633494815129d141d5a08708d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930341"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="03209-103">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="03209-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="03209-104">Cette page décrit les modifications importantes, récemment publiées dans le comportement du client équipes lorsque vous êtes dans une de le Skype pour les modes d’entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span><span class="sxs-lookup"><span data-stu-id="03209-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="03209-105">L’objectif des modes de coexistence est de fournir une expérience prévisible simple pour les utilisateurs finaux en tant que la transition des organisations de Skype pour les entreprises aux équipes.</span><span class="sxs-lookup"><span data-stu-id="03209-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="03209-106">Pour une organisation déplacement aux équipes, le mode TeamsOnly est la destination finale pour chaque utilisateur, même si tous les utilisateurs ne doivent être attribués TeamsOnly (ou tout autre mode) en même temps.</span><span class="sxs-lookup"><span data-stu-id="03209-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="03209-107">Avant d’atteindre le mode TeamsOnly des utilisateurs, organisations peuvent utiliser de la Skype pour les modes d’entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) pour assurer la communication entre les utilisateurs qui sont TeamsOnly et ceux qui ne sont pas encore prévisible.</span><span class="sxs-lookup"><span data-stu-id="03209-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="03209-108">Lorsqu’un utilisateur est dans un de la Skype pour les modes d’entreprise, toutes les conversations entrantes et les appels sont routés vers Skype l’utilisateur pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="03209-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="03209-109">Pour éviter toute confusion d’utilisateur final et garantir un routage correct, les fonctionnalités d’appel et de conversation dans le client d’équipes sont désactivée lorsqu’un utilisateur est dans un de la Skype pour les modes d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="03209-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="03209-110">De même, planifier des réunions dans les équipes est désactivé lorsque vous êtes dans les modes SfBOnly ou SfBWithTeamsCollab et explicitement activée lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="03209-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="03209-111">Comment les fonctionnalités disponibles dans le client équipes changent selon le mode</span><span class="sxs-lookup"><span data-stu-id="03209-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="03209-112">Les fonctionnalités disponibles dans les équipes dépendent de mode de coexistence de l’utilisateur, tel que défini par TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="03209-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="03209-113">Le tableau ci-dessous résume le comportement :</span><span class="sxs-lookup"><span data-stu-id="03209-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="03209-114">Mode efficace de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="03209-114">User's effective mode</span></span>|<span data-ttu-id="03209-115">Expérience client d’équipes</span><span class="sxs-lookup"><span data-stu-id="03209-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="03209-116">N’importe quel Skype pour le mode d’entreprise</span><span class="sxs-lookup"><span data-stu-id="03209-116">Any Skype for Business mode</span></span>|<span data-ttu-id="03209-117">Appel et conversation sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="03209-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="03209-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="03209-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="03209-119">Planification de la réunion est disponible</span><span class="sxs-lookup"><span data-stu-id="03209-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="03209-120">SfBWithTeamsCollab ou SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="03209-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="03209-121">Planification de la réunion n’est pas disponible</span><span class="sxs-lookup"><span data-stu-id="03209-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="03209-122">Les captures d’écran suivantes illustrent la différence entre le mode TeamsOnly ou (îles) et tous les autres modes.</span><span class="sxs-lookup"><span data-stu-id="03209-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="03209-123">Notez que les icônes de conversation et d’appel sont disponibles avec TeamsOnly ou (îles) mode (capture d’écran de gauche), mais pas avec les autres modes (capture d’écran droite) :</span><span class="sxs-lookup"><span data-stu-id="03209-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Affiche les comparaisons de mode d’équipes](media/teams-mode-comparison.png)


 
<span data-ttu-id="03209-125">**Remarque :**
<sup>1</sup> pour l’instant, SfBwithTeamsCollab et SfBOnly ont le même comportement, mais le but est pour le mode SfBOnly également désactiver la fonctionnalité de canaux et les fichiers dans les équipes ; Toutefois, il n’existe actuellement aucun paramètre qui permet cette fonctionnalité dans les équipes à désactiver.</span><span class="sxs-lookup"><span data-stu-id="03209-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="03209-126">Impact du Mode d’autres paramètres de stratégie</span><span class="sxs-lookup"><span data-stu-id="03209-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="03209-127">Comme indiqué ci-dessus, l’impact de l’utilisateur coexistence en mode fonctionnalité est disponible dans le client de l’utilisateur aux équipes.</span><span class="sxs-lookup"><span data-stu-id="03209-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="03209-128">Cela signifie que la valeur de mode a priorité sur la valeur d’autres paramètres de stratégie, selon le mode.</span><span class="sxs-lookup"><span data-stu-id="03209-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="03209-129">Plus précisément, de cohabitation a un impact sur si les paramètres de stratégie suivants sont respectés :</span><span class="sxs-lookup"><span data-stu-id="03209-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="03209-130">**Modalité (application)**</span><span class="sxs-lookup"><span data-stu-id="03209-130">**Modality (App)**</span></span>|<span data-ttu-id="03209-131">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="03209-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="03209-132">Conversation</span><span class="sxs-lookup"><span data-stu-id="03209-132">Chat</span></span>|<span data-ttu-id="03209-133">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="03209-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="03209-134">Appels</span><span class="sxs-lookup"><span data-stu-id="03209-134">Calling</span></span>|<span data-ttu-id="03209-135">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="03209-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="03209-136">Planification de la réunion</span><span class="sxs-lookup"><span data-stu-id="03209-136">Meeting scheduling</span></span>|<span data-ttu-id="03209-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="03209-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="03209-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="03209-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="03209-139">Les administrateurs doivent *pas* explicitement définies avant de ces paramètres de stratégie à l’aide du mode de coexistence, mais il est important de comprendre que ces paramètres efficacement se comportent comme suit pour un mode donné.</span><span class="sxs-lookup"><span data-stu-id="03209-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="03209-140">Mode</span><span class="sxs-lookup"><span data-stu-id="03209-140">Mode</span></span>|<span data-ttu-id="03209-141">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="03209-141">AllowUserChat</span></span>|<span data-ttu-id="03209-142">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="03209-142">AllowPrivateCalling</span></span>|<span data-ttu-id="03209-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="03209-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="03209-144">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="03209-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="03209-145">TeamsOnly ou (îles)</span><span class="sxs-lookup"><span data-stu-id="03209-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="03209-146">Activé</span><span class="sxs-lookup"><span data-stu-id="03209-146">Enabled</span></span>|<span data-ttu-id="03209-147">Activé</span><span class="sxs-lookup"><span data-stu-id="03209-147">Enabled</span></span>|<span data-ttu-id="03209-148">Activé</span><span class="sxs-lookup"><span data-stu-id="03209-148">Enabled</span></span>|<span data-ttu-id="03209-149">Activé</span><span class="sxs-lookup"><span data-stu-id="03209-149">Enabled</span></span>|
|<span data-ttu-id="03209-150">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="03209-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="03209-151">Désactivé</span><span class="sxs-lookup"><span data-stu-id="03209-151">Disabled</span></span>|<span data-ttu-id="03209-152">Désactivé</span><span class="sxs-lookup"><span data-stu-id="03209-152">Disabled</span></span>|<span data-ttu-id="03209-153">Activé</span><span class="sxs-lookup"><span data-stu-id="03209-153">Enabled</span></span>|<span data-ttu-id="03209-154">Activé</span><span class="sxs-lookup"><span data-stu-id="03209-154">Enabled</span></span>|
|<span data-ttu-id="03209-155">SfBWithTeamsCollab ou SfBOnly</span><span class="sxs-lookup"><span data-stu-id="03209-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="03209-156">Désactivé</span><span class="sxs-lookup"><span data-stu-id="03209-156">Disabled</span></span>|<span data-ttu-id="03209-157">Désactivé</span><span class="sxs-lookup"><span data-stu-id="03209-157">Disabled</span></span>|<span data-ttu-id="03209-158">Désactivé</span><span class="sxs-lookup"><span data-stu-id="03209-158">Disabled</span></span>|<span data-ttu-id="03209-159">Désactivé</span><span class="sxs-lookup"><span data-stu-id="03209-159">Disabled</span></span>|
||||||

<span data-ttu-id="03209-160">Lors de l’utilisation de PowerShell, la `Grant-CsTeamsUpgradePolicy` cmdlet vérifie la configuration des paramètres correspondants dans TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy pour déterminer si ces paramètres doit être remplacés par TeamsUpgradePolicy et dans ce cas, un message d’information est fournie dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03209-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="03209-161">Comme mentionné ci-dessus, n’est plus nécessaire de définir les autres paramètres de stratégie.</span><span class="sxs-lookup"><span data-stu-id="03209-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="03209-162">Voici un exemple de quel l’avertissement PowerShell ressemble à :</span><span class="sxs-lookup"><span data-stu-id="03209-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="03209-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="03209-163">Related topics</span></span>

[<span data-ttu-id="03209-164">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="03209-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




