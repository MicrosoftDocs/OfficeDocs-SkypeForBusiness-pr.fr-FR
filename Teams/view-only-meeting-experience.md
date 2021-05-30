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
ms.openlocfilehash: ca53c75d12964de2d4d458b240878b14fd2ad04b
ms.sourcegitcommit: ea9a0119d184179300e51f58ca4fee249c12d00a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2021
ms.locfileid: "52699345"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="0055e-103">Expérience de réunion en lecture seule de Teams</span><span class="sxs-lookup"><span data-stu-id="0055e-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="0055e-104">Les diffusions en lecture seule sont disponibles dans Microsoft 365 E3/E5 et Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="0055e-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="0055e-105">Cette fonctionnalité sera activée le 1er mars 2021 avec le mode par défaut désactivé.</span><span class="sxs-lookup"><span data-stu-id="0055e-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="0055e-106">Le déploiement de la fonctionnalité du cloud de la communauté du secteur public Microsoft 365 (GCC) commencera à la fin du mois de mars 2021.</span><span class="sxs-lookup"><span data-stu-id="0055e-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="0055e-107">Le déploiement du cloud de la communauté du secteur public de haut niveau (GCCH) et du Département de la Défense (DoD) s’effectuera à une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="0055e-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="0055e-108">Vous devez modifier la stratégie par défaut après cette date si vous voulez que la fonctionnalité fonctionne par défaut.</span><span class="sxs-lookup"><span data-stu-id="0055e-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="0055e-109">Utiliser PowerShell pour activer la valeur `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="0055e-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="0055e-110">Si votre réunion atteint sa capacité, Teams’échelle sans problème pour s’adapter à une expérience de diffusion en affichage seul de 10 000 personnes.</span><span class="sxs-lookup"><span data-stu-id="0055e-110">If your meeting hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="0055e-111">De plus, pendant cette période de travail à distance accru, tirez parti de diffusions encore plus importantes de 20 000 personnes jusqu’à la fin de cette année.</span><span class="sxs-lookup"><span data-stu-id="0055e-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="0055e-112">Microsoft Teams permet à 10 000 participants au plus de prendre part à une réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="0055e-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="0055e-113">Une fois la capacité de la réunion principale atteinte (lorsque 1 000 utilisateurs participent à une réunion), les participants supplémentaires la rejoignent avec une expérience en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="0055e-113">After the capacity of the main meeting has been reached (which is when 1000 users enter a meeting), additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="0055e-114">Les participants qui rejoignent la réunion en premier, jusqu’à la capacité de la réunion principale, obtiennent l’expérience complète Teams réunion.</span><span class="sxs-lookup"><span data-stu-id="0055e-114">Attendees who join the meeting first, up to the capacity of the main meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="0055e-115">Ils peuvent partager des fichiers audio et vidéo, voir des vidéos partagées et participer à une conversation de réunion.</span><span class="sxs-lookup"><span data-stu-id="0055e-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="0055e-116">Les participants qui rejoignent la réunion après la limite de la capacité de la réunion principale, ont une expérience en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="0055e-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="0055e-117">Les participants pourront rejoindre l’expérience d’affichage seul via le bureau, le web et Teams mobile (Android et iOS).</span><span class="sxs-lookup"><span data-stu-id="0055e-117">Attendees will be able to join the view-only experience through desktop, web, and Teams mobile (Android and iOS).</span></span>

> [!Note]
> <span data-ttu-id="0055e-118">La capacité limite actuelle de la « réunion principale », c’est-à-dire le nombre d’utilisateurs entièrement interactifs, est de 1 000 et inclut Cloud de la communauté du secteur public.</span><span class="sxs-lookup"><span data-stu-id="0055e-118">The current limit capacity of the "main meeting", or in other words, the number of fully interactive users, is 1000 and includes GCC.</span></span>

## <a name="teams-view-only-experience-controls"></a><span data-ttu-id="0055e-119">Teams contrôles d’expérience en affichage seul</span><span class="sxs-lookup"><span data-stu-id="0055e-119">Teams view-only experience controls</span></span>

<span data-ttu-id="0055e-120">Vous activez l’expérience d’affichage seul à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0055e-120">You enable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

<span data-ttu-id="0055e-121">Pour désactiver l’expérience d’affichage seul, vous pouvez également utiliser PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0055e-121">To disable the view-only experience, you can also use PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="0055e-122">À l’avenir, vous pourrez activer ou désactiver l’expérience d’affichage seul dans le Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="0055e-122">In the future, you'll be able to enable or disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="0055e-123">Conséquences sur les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0055e-123">Impact to users</span></span>

<span data-ttu-id="0055e-124">L’expérience d’un utilisateur varie en fonction de plusieurs facteurs.</span><span class="sxs-lookup"><span data-stu-id="0055e-124">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="0055e-125">Une fois la capacité de la réunion principale atteinte, le participant ne peut pas prendre pas à la réunion si l’un de ces cas est avéré :</span><span class="sxs-lookup"><span data-stu-id="0055e-125">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="0055e-126">Un administrateur a désactivé l’Teams en affichage seul pour l’organisateur ou pour l’ensemble du client.</span><span class="sxs-lookup"><span data-stu-id="0055e-126">An administrator has disabled the Teams view-only experience for either the organizer or for the entire tenant.</span></span>
- <span data-ttu-id="0055e-127">Le participant en affichage seul ne peut pas contourner la salle d’accueil.</span><span class="sxs-lookup"><span data-stu-id="0055e-127">The view-only attendee can't bypass the lobby.</span></span> <span data-ttu-id="0055e-128">Par exemple, si l’organisateur d’une  réunion choisit que seules les personnes de mon organisation évitent la salle d’accueil et qu’un participant extérieur à l’organisation tente de rejoindre une réunion en tant que participant en affichage seul, il ne pourra pas la rejoindre.</span><span class="sxs-lookup"><span data-stu-id="0055e-128">As an example, if an organizer of a meeting chooses to have only **People in my organization** bypass the lobby, and an attendee who is outside of the organization attempts to join as a view-only attendee, they won't be able to join.</span></span>

<span data-ttu-id="0055e-129">Une fois la capacité de la réunion principale atteinte, l’organisateur et les présentateurs de la réunion voient une bannière les informant que de nouveaux participants rejoindront en tant que participants en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="0055e-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that new attendees will join as view-only attendees.</span></span>

  ![Le client Teams et le message de la bannière pour les organisateurs et présentateurs](media/chat-and-banner-message.png)

<span data-ttu-id="0055e-131">Une fois la capacité de la réunion principale atteinte, les participants sont informés à l’écran de participation préalable qu’ils prennent part en mode lecture seule.</span><span class="sxs-lookup"><span data-stu-id="0055e-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![L’écran de participation préalable de Teams et le message aux participants les informant de leur participation en mode lecture seule](media/view-only-pre-join-screen.png)

<span data-ttu-id="0055e-133">S’il y a de l’espace, l’utilisateur pourra toujours participer à la réunion principale.</span><span class="sxs-lookup"><span data-stu-id="0055e-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="0055e-134">Si la réunion principale atteint sa capacité et qu’un ou plusieurs participants quittent la réunion principale, il y aura encore de la place à la réunion principale.</span><span class="sxs-lookup"><span data-stu-id="0055e-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="0055e-135">Les participants qui prennent part (ou qui participent à nouveau) à la réunion, participeront à la réunion principale jusqu’à la limite de sa capacité.</span><span class="sxs-lookup"><span data-stu-id="0055e-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="0055e-136">Les participants à l’expérience en affichage seul ne sont pas automatiquement promus à la réunion principale et ne peuvent pas être promus manuellement à la réunion principale.</span><span class="sxs-lookup"><span data-stu-id="0055e-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't be manually promoted to the main meeting.</span></span>

<span data-ttu-id="0055e-137">Si les rôles de présentateur et de participant ont été définies et qu’un présentateur tente de rejoindre une réunion une fois que la réunion principale a atteint sa capacité, il rejoint la réunion en tant que participant en affichage seul et présente les mêmes limitations que les autres participants en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="0055e-137">If presenter and attendee roles have been set, and a presenter attempts to join a meeting after the main meeting has reached capacity, they'll join as a view-only attendee and have the same limitations as other view-only attendees.</span></span> <span data-ttu-id="0055e-138">Support pour s’assurer que tous les présentateurs rejoignent la réunion principale sera mise en place ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="0055e-138">Support to ensure all presenters join the main meeting will roll out at a later date.</span></span> <span data-ttu-id="0055e-139">L’organisateur sera toujours garanti dans la réunion principale.</span><span class="sxs-lookup"><span data-stu-id="0055e-139">The organizer will always be guaranteed space in the main meeting.</span></span>

## <a name="impact-to-meeting-presenters-and-organizers"></a><span data-ttu-id="0055e-140">Impact sur les présentateurs et organisateurs de réunion</span><span class="sxs-lookup"><span data-stu-id="0055e-140">Impact to meeting presenters and organizers</span></span>

<span data-ttu-id="0055e-141">Les limitations qui s’appliquent aux présentateurs et aux organisateurs de réunion sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="0055e-141">Limitations for meeting presenters and organizers include:</span></span>

- <span data-ttu-id="0055e-142">Vous n’avez aucune information sur le participant en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="0055e-142">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="0055e-143">La découverte électronique n’est pas prise en charge pour les participants en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="0055e-143">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="0055e-144">Les utilisateurs de la réunion principale ne peuvent pas voir les participants en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="0055e-144">Users in the main meeting can't see the view-only attendees.</span></span>
- <span data-ttu-id="0055e-145">Vous ne pouvez pas supprimer un participant en lecture seule de la réunion.</span><span class="sxs-lookup"><span data-stu-id="0055e-145">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="0055e-146">Le nombre de participants tient compte uniquement des participants à la réunion principale et non des personnes présentes dans la salle en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="0055e-146">Attendee count will only reflect the people in the main meeting and not the people in the view-only room.</span></span> <span data-ttu-id="0055e-147">Par conséquent, les présentateurs ne peuvent pas obtenir le nombre exact de personnes qui ont l’expérience lecture seule.</span><span class="sxs-lookup"><span data-stu-id="0055e-147">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="0055e-148">Expérience des participants en lecture seule</span><span class="sxs-lookup"><span data-stu-id="0055e-148">Experience for view-only attendees</span></span>

<span data-ttu-id="0055e-149">L’expérience lecture seule de Teams permet aux participants de :</span><span class="sxs-lookup"><span data-stu-id="0055e-149">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="0055e-150">Écouter les participants à la réunion principale Teams.</span><span class="sxs-lookup"><span data-stu-id="0055e-150">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="0055e-151">Consulter le flux vidéo de l’intervenant actif (si l’intervenant  actif partage une vidéo).</span><span class="sxs-lookup"><span data-stu-id="0055e-151">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="0055e-152">Affichez le contenu partagé à l’aide de la fonctionnalité partager le Bureau ou l’écran.</span><span class="sxs-lookup"><span data-stu-id="0055e-152">See content being shared using the share desktop or screen functionality.</span></span>

<span data-ttu-id="0055e-153">Le participant en lecture seule ne pourra pas utiliser ces options dans les réunions :</span><span class="sxs-lookup"><span data-stu-id="0055e-153">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="0055e-154">Participer à la réunion si le participant n’est pas autorisé à contourner la salle d'attente en fonction des stratégies ou options de salle d'attente définies.</span><span class="sxs-lookup"><span data-stu-id="0055e-154">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="0055e-155">Rejoindre la salle de lecture seule à l’aide de la conférence audio.</span><span class="sxs-lookup"><span data-stu-id="0055e-155">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="0055e-156">Rejoignez la salle en affichage seul à l’Salles Microsoft Teams cloud ou à l’aide des services Cloud Video Interop (CVI).</span><span class="sxs-lookup"><span data-stu-id="0055e-156">Join the view-only room using Microsoft Teams Rooms system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="0055e-157">Partager leur contenu audio ou vidéo.</span><span class="sxs-lookup"><span data-stu-id="0055e-157">Share their audio or video.</span></span>
- <span data-ttu-id="0055e-158">Consulter ou participer à la conversation de réunion.</span><span class="sxs-lookup"><span data-stu-id="0055e-158">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="0055e-159">Consulter le flux vidéo des participants à la réunion, sauf si le participant est l’intervenant actif.</span><span class="sxs-lookup"><span data-stu-id="0055e-159">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="0055e-160">Consultez PowerPoint fichiers partagés à l’aide de la fonctionnalité PowerPoint Live ou des partages d’application individuels (autres que le partage de bureau ou d’écran).</span><span class="sxs-lookup"><span data-stu-id="0055e-160">See PowerPoint files that are shared using the PowerPoint Live functionality or individual application shares (other than desktop or screen sharing).</span></span>
- <span data-ttu-id="0055e-161">Le lever la main dans la réunion.</span><span class="sxs-lookup"><span data-stu-id="0055e-161">Raise their hand in the meeting.</span></span>
- <span data-ttu-id="0055e-162">Envoyer ou voir les réactions.</span><span class="sxs-lookup"><span data-stu-id="0055e-162">Send or see reactions.</span></span>
- <span data-ttu-id="0055e-163">Interagissez avec une application 3P intégrée à la réunion Teams, y compris les sondages.</span><span class="sxs-lookup"><span data-stu-id="0055e-163">Interact with any 3P App integrating into the Teams Meeting, including Polls.</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="0055e-164">Limitations de la fonctionnalité lecture seule</span><span class="sxs-lookup"><span data-stu-id="0055e-164">View-only feature limitations</span></span>

- <span data-ttu-id="0055e-165">Les participants en affichage seul pourront uniquement afficher les sous-titres en direct sur le Bureau et sur le Web.</span><span class="sxs-lookup"><span data-stu-id="0055e-165">View-only attendees will only be able to see Live Captions on Desktop and Web.</span></span> <span data-ttu-id="0055e-166">Seuls les sous-titres en anglais sont pris en charge pour l’instant.</span><span class="sxs-lookup"><span data-stu-id="0055e-166">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="0055e-167">Les participants en lecture seule sont pris en charge par la technologie de diffusion en continu.</span><span class="sxs-lookup"><span data-stu-id="0055e-167">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="0055e-168">Les participants en lecture seule ne sont pas inclus dans le rapport de participation.</span><span class="sxs-lookup"><span data-stu-id="0055e-168">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="0055e-169">Les participants en lecture seule ont une expérience vidéo unique.</span><span class="sxs-lookup"><span data-stu-id="0055e-169">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="0055e-170">Ils peuvent voir l’intervenant actif ou le contenu partagé, mais pas les deux.</span><span class="sxs-lookup"><span data-stu-id="0055e-170">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="0055e-171">Pour le moment, les dispositions de la **Galerie**, la **Grade galerie**, ou du **Mode Ensemble** ne sont pas prises en charge pour les participants en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="0055e-171">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="0055e-172">Les participants en lecture seule n’ont pas la même latence qu’un participant ordinaire.</span><span class="sxs-lookup"><span data-stu-id="0055e-172">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="0055e-173"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0055e-173"><sup>1</sup></span></span>

  <span data-ttu-id="0055e-174"><sup>1</sup> participants en lecture seule ont un retard audio et vidéo de 30 secondes pendant la réunion.</span><span class="sxs-lookup"><span data-stu-id="0055e-174"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
