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
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875054"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="118c3-103">Expérience de réunion en lecture seule de Teams</span><span class="sxs-lookup"><span data-stu-id="118c3-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="118c3-104">Les diffusions en lecture seule sont disponibles dans Microsoft 365 E3/E5 et Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="118c3-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="118c3-105">Cette fonctionnalité sera activée le 1er mars 2021 avec le mode par défaut désactivé.</span><span class="sxs-lookup"><span data-stu-id="118c3-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="118c3-106">Le déploiement de la fonctionnalité du cloud de la communauté du secteur public Microsoft 365 (GCC) commencera à la fin du mois de mars 2021.</span><span class="sxs-lookup"><span data-stu-id="118c3-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="118c3-107">Le déploiement du cloud de la communauté du secteur public de haut niveau (GCCH) et du Département de la Défense (DoD) s’effectuera à une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="118c3-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="118c3-108">Vous devez modifier la stratégie par défaut après cette date si vous voulez que la fonctionnalité fonctionne par défaut.</span><span class="sxs-lookup"><span data-stu-id="118c3-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="118c3-109">Utiliser PowerShell pour activer la valeur `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="118c3-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="118c3-110">Si votre réunion ou webinaire atteint sa capacité, Teams s’adaptera sans problème à une expérience de diffusion en lecture seule de 10 000 personnes.</span><span class="sxs-lookup"><span data-stu-id="118c3-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="118c3-111">De plus, pendant cette période de travail à distance accru, tirez parti de diffusions encore plus importantes de 20 000 personnes jusqu’à la fin de cette année.</span><span class="sxs-lookup"><span data-stu-id="118c3-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="118c3-112">Microsoft Teams permet à 10 000 participants au plus de prendre part à une réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="118c3-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="118c3-113">Une fois la capacité de la réunion principale atteinte, d’autres participants y prendront part avec une expérience de lecture seule.</span><span class="sxs-lookup"><span data-stu-id="118c3-113">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="118c3-114">Les participants qui rejoignent en premier la réunion, avant que la capacité de la réunion soit atteinte, pourront obtenir l’expérience de réunion complète de Teams.</span><span class="sxs-lookup"><span data-stu-id="118c3-114">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="118c3-115">Ils peuvent partager des fichiers audio et vidéo, voir des vidéos partagées et participer à une conversation de réunion.</span><span class="sxs-lookup"><span data-stu-id="118c3-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="118c3-116">Les participants qui rejoignent la réunion après la limite de la capacité de la réunion principale, ont une expérience en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="118c3-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="118c3-117">Nous offrons un support mobile complet Android et iOS pour que les participants prennent part.</span><span class="sxs-lookup"><span data-stu-id="118c3-117">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="118c3-118">La limite actuelle pour le nombre de personnes autorisées à discuter et à appeler en réunion est de 300 en WW et 250 en, GCC, GCC de haut niveau, et DoD.</span><span class="sxs-lookup"><span data-stu-id="118c3-118">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="118c3-119">L’expérience lecture seule est désactivée par défaut pour tout organisateur ayant une référence SKU E3/E5/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="118c3-119">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="118c3-120">Aucune configuration supplémentaire n’est requise.</span><span class="sxs-lookup"><span data-stu-id="118c3-120">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="118c3-121">Désactiver l’expérience lecture seule de Teams</span><span class="sxs-lookup"><span data-stu-id="118c3-121">Disable Teams view-only experience</span></span>

<span data-ttu-id="118c3-122">Les administrateurs peuvent désactiver l’expérience lecture seule à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="118c3-122">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="118c3-123">Dans le futur, les administrateurs pourront également désactiver l’expérience lecture seule dans le centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="118c3-123">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="118c3-124">Conséquences sur les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="118c3-124">Impact to users</span></span>

<span data-ttu-id="118c3-125">L’expérience d’un utilisateur varie en fonction de plusieurs facteurs.</span><span class="sxs-lookup"><span data-stu-id="118c3-125">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="118c3-126">Une fois la capacité de la réunion principale atteinte, le participant ne peut pas prendre pas à la réunion si l’un de ces cas est avéré :</span><span class="sxs-lookup"><span data-stu-id="118c3-126">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="118c3-127">Un administrateur a désactivé l’expérience lecture seule de Teams.</span><span class="sxs-lookup"><span data-stu-id="118c3-127">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="118c3-128">Le participant n’est pas autorisé à contourner la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="118c3-128">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="118c3-129">Une fois la capacité de la réunion principale atteinte, l’organisateur et les présentateurs de la réunion voient une bannière les informant que la capacité de la réunion est atteinte et que les nouveaux participants prendront part en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="118c3-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![Le client Teams et le message de la bannière pour les organisateurs et présentateurs](media/chat-and-banner-message.png)

<span data-ttu-id="118c3-131">Une fois la capacité de la réunion principale atteinte, les participants sont informés à l’écran de participation préalable qu’ils prennent part en mode lecture seule.</span><span class="sxs-lookup"><span data-stu-id="118c3-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![L’écran de participation préalable de Teams et le message aux participants les informant de leur participation en mode lecture seule](media/view-only-pre-join-screen.png)

<span data-ttu-id="118c3-133">S’il y a de l’espace, l’utilisateur pourra toujours participer à la réunion principale.</span><span class="sxs-lookup"><span data-stu-id="118c3-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="118c3-134">Si la réunion principale atteint sa capacité et qu’un ou plusieurs participants quittent la réunion principale, il y aura encore de la place à la réunion principale.</span><span class="sxs-lookup"><span data-stu-id="118c3-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="118c3-135">Les participants qui prennent part (ou qui participent à nouveau) à la réunion, participeront à la réunion principale jusqu’à la limite de sa capacité.</span><span class="sxs-lookup"><span data-stu-id="118c3-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="118c3-136">Les participants en mode lecture seule ne peuvent pas rejoindre automatiquement la réunion principale et ne peuvent pas le faire manuellement pour l’instant.</span><span class="sxs-lookup"><span data-stu-id="118c3-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="118c3-137">Si les rôles de présentateur/participant n’ont pas été définis, les espaces de la réunion principale sont remplis selon le principe du premier arrivé, premier servi.</span><span class="sxs-lookup"><span data-stu-id="118c3-137">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="118c3-138">Une fois la capacité de la réunion atteinte, tous les autres utilisateurs peuvent participer avec une expérience lecture seule.</span><span class="sxs-lookup"><span data-stu-id="118c3-138">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="118c3-139">Impact sur les présentateurs de réunion</span><span class="sxs-lookup"><span data-stu-id="118c3-139">Impact to meeting presenters</span></span>

<span data-ttu-id="118c3-140">Les limitations pour les présentateurs de réunion sont :</span><span class="sxs-lookup"><span data-stu-id="118c3-140">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="118c3-141">Vous n’avez aucune information sur le participant en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="118c3-141">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="118c3-142">La découverte électronique n’est pas prise en charge pour les participants en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="118c3-142">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="118c3-143">Les utilisateurs ne peuvent pas voir les participants en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="118c3-143">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="118c3-144">Vous ne pouvez pas supprimer un participant en lecture seule de la réunion.</span><span class="sxs-lookup"><span data-stu-id="118c3-144">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="118c3-145">Le nombre de participants reflète uniquement les participants à la réunion, et non les participants dans la salle de lecture seule.</span><span class="sxs-lookup"><span data-stu-id="118c3-145">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="118c3-146">Par conséquent, les présentateurs ne peuvent pas obtenir le nombre exact de personnes qui ont l’expérience lecture seule.</span><span class="sxs-lookup"><span data-stu-id="118c3-146">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="118c3-147">Expérience des participants en lecture seule</span><span class="sxs-lookup"><span data-stu-id="118c3-147">Experience for view-only attendees</span></span>

<span data-ttu-id="118c3-148">L’expérience lecture seule de Teams permet aux participants de :</span><span class="sxs-lookup"><span data-stu-id="118c3-148">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="118c3-149">Écouter les participants à la réunion principale Teams.</span><span class="sxs-lookup"><span data-stu-id="118c3-149">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="118c3-150">Consulter le flux vidéo de l’intervenant actif (si l’intervenant  actif partage une vidéo).</span><span class="sxs-lookup"><span data-stu-id="118c3-150">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="118c3-151">Consulter le contenu partagé à l’aide de la fonctionnalité Partager le bureau.</span><span class="sxs-lookup"><span data-stu-id="118c3-151">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="118c3-152">Le participant en lecture seule ne pourra pas utiliser ces options dans les réunions :</span><span class="sxs-lookup"><span data-stu-id="118c3-152">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="118c3-153">Participer à la réunion si le participant n’est pas autorisé à contourner la salle d'attente en fonction des stratégies ou options de salle d'attente définies.</span><span class="sxs-lookup"><span data-stu-id="118c3-153">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="118c3-154">Rejoindre la salle de lecture seule à l’aide de la conférence audio.</span><span class="sxs-lookup"><span data-stu-id="118c3-154">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="118c3-155">Rejoindre la salle de lecture seule à l’aide du système de salle Microsoft Teams ou des services Cloud Video Interop (CVI).</span><span class="sxs-lookup"><span data-stu-id="118c3-155">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="118c3-156">Partager leur contenu audio ou vidéo.</span><span class="sxs-lookup"><span data-stu-id="118c3-156">Share their audio or video.</span></span>
- <span data-ttu-id="118c3-157">Consulter ou participer à la conversation de réunion.</span><span class="sxs-lookup"><span data-stu-id="118c3-157">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="118c3-158">Consulter le flux vidéo des participants à la réunion, sauf si le participant est l’intervenant actif.</span><span class="sxs-lookup"><span data-stu-id="118c3-158">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="118c3-159">Consulter les fichiers PowerPoint partagés à l’aide de la fonctionnalité de partage natif de PowerPoint ou des partages d’applications individuels (autres que le partage de bureau).</span><span class="sxs-lookup"><span data-stu-id="118c3-159">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="118c3-160">Limitations de la fonctionnalité lecture seule</span><span class="sxs-lookup"><span data-stu-id="118c3-160">View-only feature limitations</span></span>

- <span data-ttu-id="118c3-161">Les participants en lecture seule voient toujours des sous-titres en direct, quel que soit le paramètre de sous-titres en direct de cette réunion.</span><span class="sxs-lookup"><span data-stu-id="118c3-161">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="118c3-162">Seuls les sous-titres en anglais sont pris en charge pour l’instant.</span><span class="sxs-lookup"><span data-stu-id="118c3-162">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="118c3-163">Les participants en lecture seule sont pris en charge par la technologie de diffusion en continu.</span><span class="sxs-lookup"><span data-stu-id="118c3-163">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="118c3-164">Les participants en lecture seule ne sont pas inclus dans le rapport de participation.</span><span class="sxs-lookup"><span data-stu-id="118c3-164">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="118c3-165">Les participants en lecture seule ont une expérience vidéo unique.</span><span class="sxs-lookup"><span data-stu-id="118c3-165">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="118c3-166">Ils peuvent voir l’intervenant actif ou le contenu partagé, mais pas les deux.</span><span class="sxs-lookup"><span data-stu-id="118c3-166">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="118c3-167">Pour le moment, les dispositions de la **Galerie**, la **Grade galerie**, ou du **Mode Ensemble** ne sont pas prises en charge pour les participants en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="118c3-167">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="118c3-168">Les participants en lecture seule n’ont pas la même latence qu’un participant ordinaire.</span><span class="sxs-lookup"><span data-stu-id="118c3-168">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="118c3-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="118c3-169"><sup>1</sup></span></span>

  <span data-ttu-id="118c3-170"><sup>1</sup> participants en lecture seule ont un retard audio et vidéo de 30 secondes pendant la réunion.</span><span class="sxs-lookup"><span data-stu-id="118c3-170"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
