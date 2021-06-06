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
ms.openlocfilehash: 8d25f37f94a514b83bd37e44d1b022bac064a839
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739654"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="4d793-103">Stratégies d’enregistrement d’événements en direct Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4d793-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="4d793-104">Plusieurs options s’offrent à vous pour enregistrer Microsoft Teams événement en direct.</span><span class="sxs-lookup"><span data-stu-id="4d793-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="4d793-105">Les options d’enregistrement sont définies à l’aide de stratégies d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="4d793-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="4d793-106">Cet article décrit les différents paramètres.</span><span class="sxs-lookup"><span data-stu-id="4d793-106">This article describes the various settings.</span></span>

<span data-ttu-id="4d793-107">Les options d’enregistrement sont définies à l’aide de la commande PowerShell [Set-CsTeamsMeetingBroadcastPolicy.](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="4d793-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="4d793-108">Planification et comportements des options</span><span class="sxs-lookup"><span data-stu-id="4d793-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="4d793-109">Deux options d’organisateur sont disponibles lors de la planification de l’enregistrement d’un événement en direct :</span><span class="sxs-lookup"><span data-stu-id="4d793-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="4d793-110">Enregistrement disponible pour les producteurs et les présentateurs</span><span class="sxs-lookup"><span data-stu-id="4d793-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="4d793-111">Fichier d’enregistrement : fournit un fichier d’enregistrement que les producteurs et les présentateurs peuvent télécharger une fois l’événement terminé.</span><span class="sxs-lookup"><span data-stu-id="4d793-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="4d793-112">Enregistrement disponible pour les participants</span><span class="sxs-lookup"><span data-stu-id="4d793-112">Recording available for attendees</span></span>

  - <span data-ttu-id="4d793-113">DVR : un enregistreur vidéo numérique (DVR) permet aux participants de rembobiner et de suspendre pendant l’événement</span><span class="sxs-lookup"><span data-stu-id="4d793-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="4d793-114">VOD : une vidéo à la demande permet aux participants de regarder l’événement une fois l’événement terminé</span><span class="sxs-lookup"><span data-stu-id="4d793-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="4d793-115">Paramètre de stratégie d’enregistrement de diffusion</span><span class="sxs-lookup"><span data-stu-id="4d793-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="4d793-116">Dans le cadre de la stratégie de diffusion, vous pouvez activer ou désactiver l’enregistrement pour un événement en direct.</span><span class="sxs-lookup"><span data-stu-id="4d793-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="4d793-117">Enregistrement disponible pour les producteurs et les présentateurs</span><span class="sxs-lookup"><span data-stu-id="4d793-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="4d793-118">Enregistrement disponible pour les participants</span><span class="sxs-lookup"><span data-stu-id="4d793-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="4d793-119">Toujours enregistrer</span><span class="sxs-lookup"><span data-stu-id="4d793-119">Always record</span></span>               | <span data-ttu-id="4d793-120">Désactivé et sélectionné</span><span class="sxs-lookup"><span data-stu-id="4d793-120">Disabled and selected</span></span>                                | <span data-ttu-id="4d793-121">Activé et sélectionné</span><span class="sxs-lookup"><span data-stu-id="4d793-121">Enabled and selected</span></span>         |
| <span data-ttu-id="4d793-122">L’organisateur peut enregistrer ou non</span><span class="sxs-lookup"><span data-stu-id="4d793-122">Organizer can record or not</span></span> | <span data-ttu-id="4d793-123">Activé et sélectionné par défaut</span><span class="sxs-lookup"><span data-stu-id="4d793-123">Enabled and selected by default</span></span>                  | <span data-ttu-id="4d793-124">Activé et sélectionné par défaut</span><span class="sxs-lookup"><span data-stu-id="4d793-124">Enabled and selected by default</span></span>   |
| <span data-ttu-id="4d793-125">N’enregistrez jamais</span><span class="sxs-lookup"><span data-stu-id="4d793-125">Never record</span></span>               | <span data-ttu-id="4d793-126">Désactivé et non sélectionné</span><span class="sxs-lookup"><span data-stu-id="4d793-126">Disabled and not selected</span></span>                            | <span data-ttu-id="4d793-127">Désactivé et non sélectionné</span><span class="sxs-lookup"><span data-stu-id="4d793-127">Disabled and not selected</span></span>      |

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="4d793-128">Stockage et de persistance</span><span class="sxs-lookup"><span data-stu-id="4d793-128">Storage and persistence behavior</span></span>

| <span data-ttu-id="4d793-129">Option</span><span class="sxs-lookup"><span data-stu-id="4d793-129">Option</span></span>                                       | <span data-ttu-id="4d793-130">État</span><span class="sxs-lookup"><span data-stu-id="4d793-130">State</span></span>   | <span data-ttu-id="4d793-131">DVR</span><span class="sxs-lookup"><span data-stu-id="4d793-131">DVR</span></span>                                                   | <span data-ttu-id="4d793-132">VOD</span><span class="sxs-lookup"><span data-stu-id="4d793-132">VOD</span></span>                                                     | <span data-ttu-id="4d793-133">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="4d793-133">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="4d793-134">Enregistrement disponible pour les participants</span><span class="sxs-lookup"><span data-stu-id="4d793-134">Recording available for attendees</span></span> | <span data-ttu-id="4d793-135">Sélectionné</span><span class="sxs-lookup"><span data-stu-id="4d793-135">Selected</span></span>     | <span data-ttu-id="4d793-136">DVR est disponible et le Azure Media Services (AMS) est stocké pendant 180 jours</span><span class="sxs-lookup"><span data-stu-id="4d793-136">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="4d793-137">Les participants peuvent accéder à l’événement et le regarder</span><span class="sxs-lookup"><span data-stu-id="4d793-137">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="4d793-138">Non sélectionné</span><span class="sxs-lookup"><span data-stu-id="4d793-138">Not Selected</span></span> | <span data-ttu-id="4d793-139">DVR est disponible et le bien AMS est stocké pendant 180 jours</span><span class="sxs-lookup"><span data-stu-id="4d793-139">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="4d793-140">Le participant ne sera pas autorisé à accéder à l’événement une fois celui-ci terminé</span><span class="sxs-lookup"><span data-stu-id="4d793-140">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="4d793-141">Désactivé (non sélectionné)</span><span class="sxs-lookup"><span data-stu-id="4d793-141">Disabled (Not selected)</span></span>|<span data-ttu-id="4d793-142">DVR est disponible et l’actif AMS est supprimé après l’événement</span><span class="sxs-lookup"><span data-stu-id="4d793-142">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="4d793-143">Le participant ne sera pas autorisé à accéder à l’événement une fois celui-ci terminé</span><span class="sxs-lookup"><span data-stu-id="4d793-143">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="4d793-144">Enregistrement disponible pour les producteurs et les présentateurs</span><span class="sxs-lookup"><span data-stu-id="4d793-144">Recording available to producers and presenters</span></span> | <span data-ttu-id="4d793-145">Sélectionné</span><span class="sxs-lookup"><span data-stu-id="4d793-145">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="4d793-146">Un mp4 est créé et stocké</span><span class="sxs-lookup"><span data-stu-id="4d793-146">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="4d793-147">Non sélectionné</span><span class="sxs-lookup"><span data-stu-id="4d793-147">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="4d793-148">Aucun fichier n’est créé</span><span class="sxs-lookup"><span data-stu-id="4d793-148">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="4d793-149">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="4d793-149">Related topics</span></span>

- [<span data-ttu-id="4d793-150">Comprendre un événement en direct Teams</span><span class="sxs-lookup"><span data-stu-id="4d793-150">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="4d793-151">Offre pour les événements en direct Teams</span><span class="sxs-lookup"><span data-stu-id="4d793-151">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="4d793-152">Configurer les paramètres d’événements en direct dans Teams</span><span class="sxs-lookup"><span data-stu-id="4d793-152">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="4d793-153">Teams de réunion en nuages</span><span class="sxs-lookup"><span data-stu-id="4d793-153">Teams clouds meeting recording</span></span>](../cloud-recording.md)
