---
title: Expérience de réunion en affichage seul
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: En savoir plus sur l’expérience de réunion en affichage seul teams pour les administrateurs, les présentateurs et les participants
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54bbb3c00aae8a2785e867be9614f8509ca9344d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237454"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="7cc5d-103">Expérience de réunion en affichage seul dans Teams</span><span class="sxs-lookup"><span data-stu-id="7cc5d-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="7cc5d-104">L’expérience de réunion en affichage seul sera disponible début mars 2021.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-104">View-only meeting experience will be available in early March 2021.</span></span>

> [!Note]
> <span data-ttu-id="7cc5d-105">Nous avons temporairement augmenté l’expérience d’affichage seul pour 20 000 participants, mais nous reverrons le support à 10 000 participants le 30 juin 2021.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-105">We've temporarily increased view-only experience for 20,000 attendees, but we'll revert support to 10,000 attendees on June 30, 2021.</span></span>

<span data-ttu-id="7cc5d-106">Microsoft Teams permet à jusqu’à 10 000 participants de participer à une réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-106">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="7cc5d-107">Une fois la capacité de la réunion principale atteinte, les participants supplémentaires la rejoignent avec une expérience de vue seule.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-107">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="7cc5d-108">Les participants qui rejoignent la réunion en premier, jusqu’à la capacité de la réunion, auront accès à l’expérience complète de la réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-108">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="7cc5d-109">Ils peuvent partager des fichiers audio et vidéo, voir des vidéos partagées et participer à une conversation de réunion.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-109">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="7cc5d-110">Les participants qui rejoignent la réunion une fois la capacité principale de la réunion atteinte auront une expérience en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-110">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="7cc5d-111">Nous avons un support mobile Android et iOS complet pour qu’un participant participe.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-111">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="7cc5d-112">La limite actuelle du nombre de personnes qui peuvent discuter et appeler pour une réunion est de 300 dans WW et 250 dans GCC, GCC High et DoD.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-112">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="7cc5d-113">L’expérience d’affichage seul est activée par défaut pour tout organisateur dispose de la référence SKU E3/E5/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-113">The view-only experience is enabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="7cc5d-114">Aucune autre configuration ou configuration n’est requise.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-114">No further configuration or setup is required.</span></span>

### <a name="disable-teams-view-only-experience"></a><span data-ttu-id="7cc5d-115">Désactiver l’affichage seul dans Teams</span><span class="sxs-lookup"><span data-stu-id="7cc5d-115">Disable Teams view-only experience</span></span>

<span data-ttu-id="7cc5d-116">Les administrateurs peuvent désactiver l’expérience d’affichage seul à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-116">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="7cc5d-117">À l’avenir, les administrateurs pourront également désactiver l’expérience d’affichage seul dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-117">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="7cc5d-118">Impact sur les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="7cc5d-118">Impact to users</span></span>

<span data-ttu-id="7cc5d-119">L’expérience d’un utilisateur varie en fonction de plusieurs facteurs.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-119">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="7cc5d-120">Une fois la capacité de la réunion principale atteinte, un participant ne pourra pas participer à la réunion si l’une des raisons suivantes est vraie :</span><span class="sxs-lookup"><span data-stu-id="7cc5d-120">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="7cc5d-121">Un administrateur a désactivé l’expérience teams en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-121">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="7cc5d-122">Le participant n’est pas autorisé à contourner la salle d’accueil.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-122">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="7cc5d-123">Une fois la capacité de la réunion principale atteinte, l’organisateur et les présentateurs de la réunion voient une bannière les informant que la capacité de la réunion a été atteinte et que les nouveaux participants rejoindront un participant en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-123">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![Panne du client Teams et de la bannière pour les organisateurs et les présentateurs](media/chat-and-banner-message.png)

<span data-ttu-id="7cc5d-125">Une fois la capacité de la réunion principale atteinte, les participants à la réunion seront informés, sur l’écran de pré-participation, qu’ils la rejoignent en mode affichage seul.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-125">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Écran de pré-participation à Teams et message pour les participants leur disant qu’ils seront rejoints en mode affichage seul](media/view-only-pre-join-screen.png)

<span data-ttu-id="7cc5d-127">S’il y a de l’espace, un utilisateur participera toujours à la réunion principale.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-127">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="7cc5d-128">Si la réunion principale atteint sa capacité et qu’un ou plusieurs participants quittent la réunion principale, la réunion principale a une capacité disponible.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-128">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="7cc5d-129">Les participants qui rejoignent (ou rejoignent) la réunion rejoindront la réunion principale jusqu’à ce qu’elle atteigne à nouveau sa capacité.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-129">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="7cc5d-130">Les participants à l’expérience en affichage seul ne sont pas automatiquement promus à la réunion principale et ne peuvent pas actuellement être promus manuellement à la réunion principale.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-130">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="7cc5d-131">Si les rôles de présentateur/participant n’ont pas été définies, les espaces de la réunion principale sont remplis sur la base du premier arrivé, premier servi.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-131">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="7cc5d-132">Une fois la capacité de la réunion atteinte, tous les autres utilisateurs la rejoignent avec une expérience en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-132">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="7cc5d-133">Impact sur les présentateurs de réunion</span><span class="sxs-lookup"><span data-stu-id="7cc5d-133">Impact to meeting presenters</span></span>

<span data-ttu-id="7cc5d-134">Nous réserverons de l’espace dans la réunion normale aux utilisateurs explicitement indiqués comme présentateurs dans les options de la réunion.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-134">We'll reserve space in the normal meeting for users explicitly indicated as presenters in the meeting options.</span></span> <span data-ttu-id="7cc5d-135">Si un présentateur quitte la réunion, puis le rejoint par la suite, il sera invité à rejoindre la réunion en tant que présentateur.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-135">If a presenter leaves and then later rejoins the meeting, they'll be let into the meeting as a presenter.</span></span>

<span data-ttu-id="7cc5d-136">Les limitations qui s’appliquent aux présentateurs de réunion sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="7cc5d-136">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="7cc5d-137">Vous n’aurez aucune information sur le participant en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-137">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="7cc5d-138">La découverte électronique n’est pas prise en charge pour les participants en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-138">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="7cc5d-139">Les utilisateurs ne peuvent pas voir les participants en affichage seul.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-139">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="7cc5d-140">Vous ne pouvez pas supprimer un participant en affichage seul de la réunion.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-140">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="7cc5d-141">Le nombre de participants reflète uniquement les participants à la réunion et non les personnes dans la salle de débordement.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-141">Attendee count will only reflect the people in the meeting and not the people in the overflow room.</span></span> <span data-ttu-id="7cc5d-142">Par conséquent, les présentateurs ne peuvent pas obtenir le nombre exact des personnes présentes dans l’expérience de affichage seul.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-142">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="7cc5d-143">Expérience pour les participants en affichage seul</span><span class="sxs-lookup"><span data-stu-id="7cc5d-143">Experience for view-only attendees</span></span>

<span data-ttu-id="7cc5d-144">L’expérience Teams en affichage seul permet aux participants d':</span><span class="sxs-lookup"><span data-stu-id="7cc5d-144">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="7cc5d-145">Écoutez les participants à la réunion Teams principale.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-145">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="7cc5d-146">Consultez le flux vidéo du haut-parleur actif (si celui-ci partage la vidéo).</span><span class="sxs-lookup"><span data-stu-id="7cc5d-146">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="7cc5d-147">Voir le contenu partagé à l’aide de la fonctionnalité de partage du Bureau.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-147">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="7cc5d-148">Le participant en affichage seul ne pourra pas découvrir les options suivantes dans les réunions :</span><span class="sxs-lookup"><span data-stu-id="7cc5d-148">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="7cc5d-149">Participez à la réunion si le participant n’est pas autorisé à contourner la salle d’accueil en fonction des stratégies ou options définies en matière de salle d’accueil.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-149">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="7cc5d-150">Rejoignez la salle de débordement via l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-150">Join the Overflow Room via Audio Conferencing.</span></span>
- <span data-ttu-id="7cc5d-151">Rejoignez la salle de débordement via le système de salle de Réunion de Microsoft Teams ou via les services Cloud Video Interop (CVI).</span><span class="sxs-lookup"><span data-stu-id="7cc5d-151">Join the Overflow Room via Microsoft Teams Room system or via Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="7cc5d-152">Rejoignez la salle de débordement via l’application mobile Teams pour Android.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-152">Join the Overflow Room via the Teams Android mobile app.</span></span>
- <span data-ttu-id="7cc5d-153">Partagez l’audio ou la vidéo.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-153">Share their audio or video.</span></span>
- <span data-ttu-id="7cc5d-154">Voir ou participer à la conversation de réunion.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-154">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="7cc5d-155">Consultez le flux vidéo des participants à la réunion, sauf s’il s’agit du haut-parleur actif.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-155">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="7cc5d-156">Consultez les fichiers PowerPoint partagés à l’aide de la fonctionnalité de partage native de PowerPoint ou des partages d’application individuels (autres que le partage de bureau).</span><span class="sxs-lookup"><span data-stu-id="7cc5d-156">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="7cc5d-157">Limitations des fonctionnalités en affichage seul</span><span class="sxs-lookup"><span data-stu-id="7cc5d-157">View-only feature limitations</span></span>

- <span data-ttu-id="7cc5d-158">Les participants en affichage seul voient toujours les sous-titres en direct, quel que soit le paramètre de sous-titres en direct pour cette réunion.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-158">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="7cc5d-159">Seules les légendes anglaises sont actuellement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-159">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="7cc5d-160">Les participants en affichage seul seront pris en charge par la technologie de diffusion en continu.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-160">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="7cc5d-161">Les participants en affichage seul ne seront pas inclus dans le rapport de présence.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-161">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="7cc5d-162">Les participants en affichage seul n’auront qu’une expérience vidéo.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-162">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="7cc5d-163">Ils peuvent voir le haut-parleur actif ou le contenu partagé, mais pas les deux.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-163">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="7cc5d-164">Pour le moment, les dispositions **Galerie,** **Grande** galerie ou **Ensemble** ne sont pas prise en charge pour les participants en mode Affichage seul.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-164">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="7cc5d-165">Les participants en affichage seul n’auront pas la même latence qu’un participant ordinaire.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-165">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="7cc5d-166"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7cc5d-166"><sup>1</sup></span></span>

  <span data-ttu-id="7cc5d-167"><sup>1</sup> Participants en affichage seul auront un délai audio et vidéo de 30 secondes dans la réunion.</span><span class="sxs-lookup"><span data-stu-id="7cc5d-167"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="7cc5d-168">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="7cc5d-168">Related topics</span></span>

- [<span data-ttu-id="7cc5d-169">Modules de communication avancés pour Teams</span><span class="sxs-lookup"><span data-stu-id="7cc5d-169">Advanced communications add-on for Teams</span></span>](teams-add-on-licensing/advanced-communications.md)
- [<span data-ttu-id="7cc5d-170">Spécifications et limites de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7cc5d-170">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)
