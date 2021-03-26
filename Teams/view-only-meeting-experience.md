---
title: Expérience de réunion en lecture seule
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: En savoir plus sur l’expérience de réunion en lecture seule pour les administrateurs, présentateurs et participants
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25cd674e5f93e4f52f0a2cecd2acff97e4844834
ms.sourcegitcommit: f4393657584666842e874d526a08cfa1137b911d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51215329"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="e2834-103">Expérience de réunion en lecture seule de Teams</span><span class="sxs-lookup"><span data-stu-id="e2834-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="e2834-104">Les diffusions en lecture seule sont disponibles dans Microsoft 365 E3/E5 et Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="e2834-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="e2834-105">Cette fonctionnalité sera activée le 1er mars 2021 avec le mode par défaut désactivé.</span><span class="sxs-lookup"><span data-stu-id="e2834-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="e2834-106">Le déploiement de la fonctionnalité du cloud de la communauté du secteur public Microsoft 365 (GCC) commencera à la fin du mois de mars 2021.</span><span class="sxs-lookup"><span data-stu-id="e2834-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="e2834-107">Le déploiement du cloud de la communauté du secteur public de haut niveau (GCCH) et du Département de la Défense (DoD) s’effectuera à une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="e2834-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="e2834-108">Vous devez modifier la stratégie par défaut après cette date si vous voulez que la fonctionnalité fonctionne par défaut.</span><span class="sxs-lookup"><span data-stu-id="e2834-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="e2834-109">Utiliser PowerShell pour activer la valeur `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="e2834-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="e2834-110">Si votre réunion ou webinaire atteint sa capacité, Teams s’adaptera sans problème à une expérience de diffusion en lecture seule de 10 000 personnes.</span><span class="sxs-lookup"><span data-stu-id="e2834-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="e2834-111">De plus, pendant cette période de travail à distance accru, tirez parti de diffusions encore plus importantes de 20 000 personnes jusqu’à la fin de cette année.</span><span class="sxs-lookup"><span data-stu-id="e2834-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="e2834-112">Microsoft Teams permet à 10 000 participants au plus de prendre part à une réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="e2834-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="e2834-113">Une fois la capacité de la réunion principale atteinte (c’est-à-faire lorsque 300 utilisateurs de WW ou 250 utilisateurs du GCC participent à une réunion), d’autres participants la rejoindront avec une expérience en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="e2834-113">After the capacity of the main meeting has been reached (which is when 300 in WW or 250 in GCC users enter a meeting), additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="e2834-114">Les participants qui rejoignent la réunion en premier, jusqu’à la capacité de la réunion principale, auront accès à l’expérience complète de la réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="e2834-114">Attendees who join the meeting first, up to the capacity of the main meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="e2834-115">Ils peuvent partager des fichiers audio et vidéo, voir des vidéos partagées et participer à une conversation de réunion.</span><span class="sxs-lookup"><span data-stu-id="e2834-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="e2834-116">Les participants qui rejoignent la réunion après la limite de la capacité de la réunion principale, ont une expérience en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e2834-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="e2834-117">Les participants pourront rejoindre l’expérience d’affichage seul via le Bureau, le Web et Teams Mobile (Android et iOS).</span><span class="sxs-lookup"><span data-stu-id="e2834-117">Attendees will be able to join the view-only experience through desktop, web, and Teams mobile (Android and iOS).</span></span>

> [!Note]
> <span data-ttu-id="e2834-118">La capacité limite actuelle de la « réunion principale », c’est-à-dire le nombre d’utilisateurs entièrement interactifs, est de 300 dans WW et 250 dans GCC, GCC High et DoD.</span><span class="sxs-lookup"><span data-stu-id="e2834-118">The current limit capacity of the "main meeting", or in other words, the number of fully interactive users, is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

## <a name="teams-view-only-experience-controls"></a><span data-ttu-id="e2834-119">Contrôles d’expérience en affichage seul dans Teams</span><span class="sxs-lookup"><span data-stu-id="e2834-119">Teams view-only experience controls</span></span>

<span data-ttu-id="e2834-120">Vous activez l’expérience d’affichage seul à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2834-120">You enable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

<span data-ttu-id="e2834-121">Pour désactiver l’expérience d’affichage seul, vous pouvez également utiliser PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2834-121">To disable the view-only experience, you can also use PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="e2834-122">À l’avenir, vous pourrez activer ou désactiver l’expérience d’affichage seul dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="e2834-122">In the future, you'll be able to enable or disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="e2834-123">Conséquences sur les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="e2834-123">Impact to users</span></span>

<span data-ttu-id="e2834-124">L’expérience d’un utilisateur varie en fonction de plusieurs facteurs.</span><span class="sxs-lookup"><span data-stu-id="e2834-124">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="e2834-125">Une fois la capacité de la réunion principale atteinte, le participant ne peut pas prendre pas à la réunion si l’un de ces cas est avéré :</span><span class="sxs-lookup"><span data-stu-id="e2834-125">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="e2834-126">Un administrateur a désactivé l’expérience teams en affichage seul pour l’organisateur ou pour l’ensemble du client.</span><span class="sxs-lookup"><span data-stu-id="e2834-126">An administrator has disabled the Teams view-only experience for either the organizer or for the entire tenant.</span></span>
- <span data-ttu-id="e2834-127">Le participant en affichage seul ne peut pas contourner la salle d’accueil.</span><span class="sxs-lookup"><span data-stu-id="e2834-127">The view-only attendee can't bypass the lobby.</span></span> <span data-ttu-id="e2834-128">Par exemple, si l’organisateur d’une  réunion choisit d’éviter la salle d’accueil des seuls membres de mon organisation et qu’un participant extérieur à l’organisation tente de rejoindre la réunion en tant que participant en affichage seul, il sera rejeté.</span><span class="sxs-lookup"><span data-stu-id="e2834-128">As an example, if an organizer of a meeting chooses to have only **People in my organization** bypass the lobby, and an attendee who is outside of the organization attempts to join as a view-only attendee, they'll be rejected.</span></span>

<span data-ttu-id="e2834-129">Une fois la capacité de la réunion principale atteinte, l’organisateur et les présentateurs de la réunion voient une bannière les informant que de nouveaux participants rejoindront en tant que participants en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="e2834-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that new attendees will join as view-only attendees.</span></span>

  ![Le client Teams et le message de la bannière pour les organisateurs et présentateurs](media/chat-and-banner-message.png)

<span data-ttu-id="e2834-131">Une fois la capacité de la réunion principale atteinte, les participants sont informés à l’écran de participation préalable qu’ils prennent part en mode lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e2834-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![L’écran de participation préalable de Teams et le message aux participants les informant de leur participation en mode lecture seule](media/view-only-pre-join-screen.png)

<span data-ttu-id="e2834-133">S’il y a de l’espace, l’utilisateur pourra toujours participer à la réunion principale.</span><span class="sxs-lookup"><span data-stu-id="e2834-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="e2834-134">Si la réunion principale atteint sa capacité et qu’un ou plusieurs participants quittent la réunion principale, il y aura encore de la place à la réunion principale.</span><span class="sxs-lookup"><span data-stu-id="e2834-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="e2834-135">Les participants qui prennent part (ou qui participent à nouveau) à la réunion, participeront à la réunion principale jusqu’à la limite de sa capacité.</span><span class="sxs-lookup"><span data-stu-id="e2834-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="e2834-136">Les participants en mode lecture seule ne peuvent pas rejoindre automatiquement la réunion principale et ne peuvent pas le faire manuellement pour l’instant.</span><span class="sxs-lookup"><span data-stu-id="e2834-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="e2834-137">Si les rôles de présentateur et de participant ont été définies et qu’un présentateur tente de rejoindre une réunion une fois que la réunion principale de cette dernière a atteint sa capacité, il rejoint la réunion en tant que participant en affichage seul et présente les mêmes limitations que les autres participants en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="e2834-137">If presenter and attendee roles have been set, and a presenter attempts to join a meeting after the main meeting of has reached capacity, they'll join as a view-only attendee and have the same limitations as other view-only attendees.</span></span> <span data-ttu-id="e2834-138">Support pour s’assurer que tous les présentateurs rejoignent la réunion principale sera mise en place ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="e2834-138">Support to ensure all presenters join the main meeting will roll out at a later date.</span></span> <span data-ttu-id="e2834-139">L’organisateur sera toujours garanti dans la réunion principale.</span><span class="sxs-lookup"><span data-stu-id="e2834-139">The organizer will always be guaranteed space in the main meeting.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="e2834-140">Impact sur les présentateurs de réunion</span><span class="sxs-lookup"><span data-stu-id="e2834-140">Impact to meeting presenters</span></span>

<span data-ttu-id="e2834-141">Les limitations pour les présentateurs de réunion sont :</span><span class="sxs-lookup"><span data-stu-id="e2834-141">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="e2834-142">Vous n’avez aucune information sur le participant en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e2834-142">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="e2834-143">La découverte électronique n’est pas prise en charge pour les participants en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e2834-143">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="e2834-144">Les utilisateurs de la réunion principale ne peuvent pas voir les participants en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="e2834-144">Users in the main meeting can't see the view-only attendees.</span></span>
- <span data-ttu-id="e2834-145">Vous ne pouvez pas supprimer un participant en lecture seule de la réunion.</span><span class="sxs-lookup"><span data-stu-id="e2834-145">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="e2834-146">Le nombre de participants tient compte uniquement des participants à la réunion principale et non des personnes présentes dans la salle en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="e2834-146">Attendee count will only reflect the people in the main meeting and not the people in the view-only room.</span></span> <span data-ttu-id="e2834-147">Par conséquent, les présentateurs ne peuvent pas obtenir le nombre exact de personnes qui ont l’expérience lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e2834-147">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="e2834-148">Expérience des participants en lecture seule</span><span class="sxs-lookup"><span data-stu-id="e2834-148">Experience for view-only attendees</span></span>

<span data-ttu-id="e2834-149">L’expérience lecture seule de Teams permet aux participants de :</span><span class="sxs-lookup"><span data-stu-id="e2834-149">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="e2834-150">Écouter les participants à la réunion principale Teams.</span><span class="sxs-lookup"><span data-stu-id="e2834-150">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="e2834-151">Consulter le flux vidéo de l’intervenant actif (si l’intervenant  actif partage une vidéo).</span><span class="sxs-lookup"><span data-stu-id="e2834-151">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="e2834-152">Affichez le contenu partagé à l’aide de la fonctionnalité partager le Bureau ou l’écran.</span><span class="sxs-lookup"><span data-stu-id="e2834-152">See content being shared using the share desktop or screen functionality.</span></span>

<span data-ttu-id="e2834-153">Le participant en lecture seule ne pourra pas utiliser ces options dans les réunions :</span><span class="sxs-lookup"><span data-stu-id="e2834-153">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="e2834-154">Participer à la réunion si le participant n’est pas autorisé à contourner la salle d'attente en fonction des stratégies ou options de salle d'attente définies.</span><span class="sxs-lookup"><span data-stu-id="e2834-154">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="e2834-155">Rejoindre la salle de lecture seule à l’aide de la conférence audio.</span><span class="sxs-lookup"><span data-stu-id="e2834-155">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="e2834-156">Rejoignez la salle en affichage seul à l’aide du système de salles Microsoft Teams ou des services Cloud Video Interop (CVI).</span><span class="sxs-lookup"><span data-stu-id="e2834-156">Join the view-only room using Microsoft Teams Rooms system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="e2834-157">Partager leur contenu audio ou vidéo.</span><span class="sxs-lookup"><span data-stu-id="e2834-157">Share their audio or video.</span></span>
- <span data-ttu-id="e2834-158">Consulter ou participer à la conversation de réunion.</span><span class="sxs-lookup"><span data-stu-id="e2834-158">See or participate in the meeting chat.</span></span>
  - <span data-ttu-id="e2834-159">Les 1 000 premiers utilisateurs (ou 300 selon votre limite de réunion principale) invités à la réunion seront ajoutés à la conversation.</span><span class="sxs-lookup"><span data-stu-id="e2834-159">The first 1000 (or 300 depending on your main meeting limit) users invited to the meeting will be added to the chat.</span></span>
  - <span data-ttu-id="e2834-160">Si les utilisateurs en affichage seul ne peuvent pas voir la conversation pendant la réunion, ils peuvent tout de même discuter dans l’application principale s’ils sont les 350 premiers invités.</span><span class="sxs-lookup"><span data-stu-id="e2834-160">While view-only users won't see the chat in the meeting, they might still be able to chat on the main app if they were the first 350 people invited.</span></span>
  - <span data-ttu-id="e2834-161">À l’inverse, si un utilisateur interactif ne faisait pas partie des 350 premiers utilisateurs invités à la réunion, il n’aura pas accès à la conversation de réunion à la fois dans l’application Teams principale et dans la réunion.</span><span class="sxs-lookup"><span data-stu-id="e2834-161">Conversely, if an interactive user wasn't part of the first 350 users invited to the meeting, they'll not get access to the meeting chat both on the main Teams App and in the meeting.</span></span>
- <span data-ttu-id="e2834-162">Consulter le flux vidéo des participants à la réunion, sauf si le participant est l’intervenant actif.</span><span class="sxs-lookup"><span data-stu-id="e2834-162">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="e2834-163">Consultez les fichiers PowerPoint partagés à l’aide de la fonctionnalité PowerPoint Live ou des partages d’application individuels (autres que le partage de Bureau ou d’écran).</span><span class="sxs-lookup"><span data-stu-id="e2834-163">See PowerPoint files that are shared using the PowerPoint Live functionality or individual application shares (other than desktop or screen sharing).</span></span>
- <span data-ttu-id="e2834-164">Le lever la main dans la réunion.</span><span class="sxs-lookup"><span data-stu-id="e2834-164">Raise their hand in the meeting.</span></span>
- <span data-ttu-id="e2834-165">Envoyer ou voir les réactions.</span><span class="sxs-lookup"><span data-stu-id="e2834-165">Send or see reactions.</span></span>
- <span data-ttu-id="e2834-166">Interagissez avec une application 3P intégrée dans Teams Meeting, y compris les sondages.</span><span class="sxs-lookup"><span data-stu-id="e2834-166">Interact with any 3P App integrating into the Teams Meeting, including Polls.</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="e2834-167">Limitations de la fonctionnalité lecture seule</span><span class="sxs-lookup"><span data-stu-id="e2834-167">View-only feature limitations</span></span>

- <span data-ttu-id="e2834-168">Les participants en affichage seul pourront uniquement afficher les sous-titres en direct sur le Bureau et sur le Web.</span><span class="sxs-lookup"><span data-stu-id="e2834-168">View-only attendees will only be able to see Live Captions on Desktop and Web.</span></span> <span data-ttu-id="e2834-169">Seuls les sous-titres en anglais sont pris en charge pour l’instant.</span><span class="sxs-lookup"><span data-stu-id="e2834-169">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="e2834-170">Les participants en lecture seule sont pris en charge par la technologie de diffusion en continu.</span><span class="sxs-lookup"><span data-stu-id="e2834-170">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="e2834-171">Les participants en lecture seule ne sont pas inclus dans le rapport de participation.</span><span class="sxs-lookup"><span data-stu-id="e2834-171">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="e2834-172">Les participants en lecture seule ont une expérience vidéo unique.</span><span class="sxs-lookup"><span data-stu-id="e2834-172">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="e2834-173">Ils peuvent voir l’intervenant actif ou le contenu partagé, mais pas les deux.</span><span class="sxs-lookup"><span data-stu-id="e2834-173">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="e2834-174">Pour le moment, les dispositions de la **Galerie**, la **Grade galerie**, ou du **Mode Ensemble** ne sont pas prises en charge pour les participants en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e2834-174">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="e2834-175">Les participants en lecture seule n’ont pas la même latence qu’un participant ordinaire.</span><span class="sxs-lookup"><span data-stu-id="e2834-175">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="e2834-176"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e2834-176"><sup>1</sup></span></span>

  <span data-ttu-id="e2834-177"><sup>1</sup> participants en lecture seule ont un retard audio et vidéo de 30 secondes pendant la réunion.</span><span class="sxs-lookup"><span data-stu-id="e2834-177"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
