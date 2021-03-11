---
title: Stratégies d’enregistrement des événements en direct
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: En savoir plus sur les stratégies d’enregistrement d’événements en direct.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9fd67ce67d31effdba0d152a3d5920bb17f23b25
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615168"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="b556c-103">Stratégies d’enregistrement d’événements en direct dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b556c-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="b556c-104">Plusieurs options s’offrent à vous pour enregistrer un événement en direct Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b556c-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="b556c-105">Les options d’enregistrement sont définies à l’aide de stratégies d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="b556c-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="b556c-106">Cet article décrit les différents paramètres.</span><span class="sxs-lookup"><span data-stu-id="b556c-106">This article describes the various settings.</span></span>

<span data-ttu-id="b556c-107">Les options d’enregistrement sont définies à l’aide de la commande PowerShell [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="b556c-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="b556c-108">Planification et comportements des options</span><span class="sxs-lookup"><span data-stu-id="b556c-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="b556c-109">Deux options d’organisateur sont disponibles lors de la planification de l’enregistrement d’un événement en direct :</span><span class="sxs-lookup"><span data-stu-id="b556c-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="b556c-110">Enregistrement disponible pour les producteurs et les présentateurs</span><span class="sxs-lookup"><span data-stu-id="b556c-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="b556c-111">Fichier d’enregistrement : fournit un fichier d’enregistrement que les producteurs et les présentateurs peuvent télécharger une fois l’événement terminé.</span><span class="sxs-lookup"><span data-stu-id="b556c-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="b556c-112">Enregistrement disponible pour les participants</span><span class="sxs-lookup"><span data-stu-id="b556c-112">Recording available for attendees</span></span>

  - <span data-ttu-id="b556c-113">DVR : un enregistreur vidéo numérique (DVR) permet aux participants de rembobiner et de suspendre pendant l’événement</span><span class="sxs-lookup"><span data-stu-id="b556c-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="b556c-114">VOD : une vidéo à la demande permet aux participants de les regarder une fois l’événement terminé</span><span class="sxs-lookup"><span data-stu-id="b556c-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="b556c-115">Paramètre de stratégie d’enregistrement de diffusion</span><span class="sxs-lookup"><span data-stu-id="b556c-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="b556c-116">Dans le cadre de la stratégie de diffusion, vous pouvez activer ou désactiver l’enregistrement d’un événement en direct à partir d’un paramètre.</span><span class="sxs-lookup"><span data-stu-id="b556c-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="b556c-117">Enregistrement disponible pour les producteurs et les présentateurs</span><span class="sxs-lookup"><span data-stu-id="b556c-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="b556c-118">Enregistrement disponible pour les participants</span><span class="sxs-lookup"><span data-stu-id="b556c-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="b556c-119">Toujours enregistrer</span><span class="sxs-lookup"><span data-stu-id="b556c-119">Always record</span></span>               | <span data-ttu-id="b556c-120">Désactivé et sélectionné</span><span class="sxs-lookup"><span data-stu-id="b556c-120">Disabled and selected</span></span>                                | <span data-ttu-id="b556c-121">Désactivé et sélectionné</span><span class="sxs-lookup"><span data-stu-id="b556c-121">Disabled and selected</span></span>         |
| <span data-ttu-id="b556c-122">L’organisateur peut enregistrer ou non</span><span class="sxs-lookup"><span data-stu-id="b556c-122">Organizer can record or not</span></span> | <span data-ttu-id="b556c-123">Activé et non sélectionné par défaut</span><span class="sxs-lookup"><span data-stu-id="b556c-123">Enabled and not selected by default</span></span>                  | <span data-ttu-id="b556c-124">Activé et non sélectionné par défaut</span><span class="sxs-lookup"><span data-stu-id="b556c-124">Enabled and not selected by default</span></span>   |
| <span data-ttu-id="b556c-125">N’enregistrez jamais</span><span class="sxs-lookup"><span data-stu-id="b556c-125">Never record</span></span>               | <span data-ttu-id="b556c-126">Désactivé et non sélectionné</span><span class="sxs-lookup"><span data-stu-id="b556c-126">Disabled and not selected</span></span>                            | <span data-ttu-id="b556c-127">Désactivé et non sélectionné</span><span class="sxs-lookup"><span data-stu-id="b556c-127">Disabled and not selected</span></span>      |

<span data-ttu-id="b556c-128">Lorsque la stratégie est définie sur **Toujours enregistrer,** la page de stratégie possède les options sélectionnées suivantes :</span><span class="sxs-lookup"><span data-stu-id="b556c-128">When the policy is set to **Always record**, the policy page has the following selected options:</span></span>

<span data-ttu-id="b556c-129">![Paramètres de stratégie des événements en direct](../media/live-event-recording-policy.png "Capture d’écran des paramètres de stratégie d’événements en direct dans le centre d’administration de Microsoft Teams.")</span><span class="sxs-lookup"><span data-stu-id="b556c-129">![live events policy settings](../media/live-event-recording-policy.png "Screen shot of live events policy settings in the Microsoft Teams admin center")</span></span>

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="b556c-130">Comportement de stockage et de persistance</span><span class="sxs-lookup"><span data-stu-id="b556c-130">Storage and persistence behavior</span></span>

| <span data-ttu-id="b556c-131">Option</span><span class="sxs-lookup"><span data-stu-id="b556c-131">Option</span></span>                                       | <span data-ttu-id="b556c-132">État</span><span class="sxs-lookup"><span data-stu-id="b556c-132">State</span></span>   | <span data-ttu-id="b556c-133">DVR</span><span class="sxs-lookup"><span data-stu-id="b556c-133">DVR</span></span>                                                   | <span data-ttu-id="b556c-134">VOD</span><span class="sxs-lookup"><span data-stu-id="b556c-134">VOD</span></span>                                                     | <span data-ttu-id="b556c-135">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="b556c-135">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="b556c-136">Enregistrement disponible pour les producteurs et les présentateurs</span><span class="sxs-lookup"><span data-stu-id="b556c-136">Recording available to producers and presenters</span></span> | <span data-ttu-id="b556c-137">Sélectionné</span><span class="sxs-lookup"><span data-stu-id="b556c-137">Selected</span></span>     | <span data-ttu-id="b556c-138">DVR est disponible et le bien Azure Media Services (AMS) est stocké pendant 180 jours</span><span class="sxs-lookup"><span data-stu-id="b556c-138">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="b556c-139">Les participants peuvent accéder à l’événement et le regarder</span><span class="sxs-lookup"><span data-stu-id="b556c-139">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="b556c-140">Non sélectionné</span><span class="sxs-lookup"><span data-stu-id="b556c-140">Not Selected</span></span> | <span data-ttu-id="b556c-141">DVR est disponible et le bien AMS est stocké pendant 180 jours</span><span class="sxs-lookup"><span data-stu-id="b556c-141">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="b556c-142">Le participant ne sera pas autorisé à accéder à l’événement une fois celui-ci terminé</span><span class="sxs-lookup"><span data-stu-id="b556c-142">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="b556c-143">Désactivé (non sélectionné)</span><span class="sxs-lookup"><span data-stu-id="b556c-143">Disabled (Not selected)</span></span>|<span data-ttu-id="b556c-144">DVR est disponible et l’actif AMS est supprimé après l’événement</span><span class="sxs-lookup"><span data-stu-id="b556c-144">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="b556c-145">Le participant ne sera pas autorisé à accéder à l’événement une fois celui-ci terminé</span><span class="sxs-lookup"><span data-stu-id="b556c-145">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="b556c-146">Enregistrement disponible pour les producteurs et les présentateurs</span><span class="sxs-lookup"><span data-stu-id="b556c-146">Recording available to producers and presenters</span></span> | <span data-ttu-id="b556c-147">Sélectionné</span><span class="sxs-lookup"><span data-stu-id="b556c-147">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="b556c-148">Un mp4 est créé et stocké</span><span class="sxs-lookup"><span data-stu-id="b556c-148">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="b556c-149">Non sélectionné</span><span class="sxs-lookup"><span data-stu-id="b556c-149">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="b556c-150">Aucun fichier n’est créé</span><span class="sxs-lookup"><span data-stu-id="b556c-150">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="b556c-151">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="b556c-151">Related topics</span></span>

- [<span data-ttu-id="b556c-152">Qu’est-ce que les événements en direct Teams ?</span><span class="sxs-lookup"><span data-stu-id="b556c-152">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="b556c-153">Offre pour les événements en direct Teams</span><span class="sxs-lookup"><span data-stu-id="b556c-153">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="b556c-154">Configurer les paramètres d’événements en direct dans Teams</span><span class="sxs-lookup"><span data-stu-id="b556c-154">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="b556c-155">Enregistrement de réunion en nuages dans Teams</span><span class="sxs-lookup"><span data-stu-id="b556c-155">Teams clouds meeting recording</span></span>](../cloud-recording.md)
