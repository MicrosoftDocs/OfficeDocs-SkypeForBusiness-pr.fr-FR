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
ms.openlocfilehash: 7a5f793230798c68f0a39e2d9a3500eab9791065
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119163"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="645f4-103">Stratégies d’enregistrement d’événements en direct dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="645f4-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="645f4-104">Plusieurs options s’offrent à vous pour enregistrer un événement en direct Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="645f4-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="645f4-105">Les options d’enregistrement sont définies à l’aide de stratégies d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="645f4-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="645f4-106">Cet article décrit les différents paramètres.</span><span class="sxs-lookup"><span data-stu-id="645f4-106">This article describes the various settings.</span></span>

<span data-ttu-id="645f4-107">Les options d’enregistrement sont définies à l’aide de la commande PowerShell [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="645f4-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="645f4-108">Planification et comportements des options</span><span class="sxs-lookup"><span data-stu-id="645f4-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="645f4-109">Deux options d’organisateur sont disponibles lors de la planification de l’enregistrement d’un événement en direct :</span><span class="sxs-lookup"><span data-stu-id="645f4-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="645f4-110">Enregistrement disponible pour les producteurs et les présentateurs</span><span class="sxs-lookup"><span data-stu-id="645f4-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="645f4-111">Fichier d’enregistrement : fournit un fichier d’enregistrement que les producteurs et les présentateurs peuvent télécharger une fois l’événement terminé.</span><span class="sxs-lookup"><span data-stu-id="645f4-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="645f4-112">Enregistrement disponible pour les participants</span><span class="sxs-lookup"><span data-stu-id="645f4-112">Recording available for attendees</span></span>

  - <span data-ttu-id="645f4-113">DVR : un enregistreur vidéo numérique (DVR) permet aux participants de rembobiner et de suspendre pendant l’événement</span><span class="sxs-lookup"><span data-stu-id="645f4-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="645f4-114">VOD : une vidéo à la demande permet aux participants de regarder l’événement une fois l’événement terminé</span><span class="sxs-lookup"><span data-stu-id="645f4-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="645f4-115">Paramètre de stratégie d’enregistrement de diffusion</span><span class="sxs-lookup"><span data-stu-id="645f4-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="645f4-116">Dans le cadre de la stratégie de diffusion, vous pouvez activer ou désactiver l’enregistrement pour un événement en direct.</span><span class="sxs-lookup"><span data-stu-id="645f4-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="645f4-117">Enregistrement disponible pour les producteurs et les présentateurs</span><span class="sxs-lookup"><span data-stu-id="645f4-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="645f4-118">Enregistrement disponible pour les participants</span><span class="sxs-lookup"><span data-stu-id="645f4-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="645f4-119">Toujours enregistrer</span><span class="sxs-lookup"><span data-stu-id="645f4-119">Always record</span></span>               | <span data-ttu-id="645f4-120">Désactivé et sélectionné</span><span class="sxs-lookup"><span data-stu-id="645f4-120">Disabled and selected</span></span>                                | <span data-ttu-id="645f4-121">Désactivé et sélectionné</span><span class="sxs-lookup"><span data-stu-id="645f4-121">Disabled and selected</span></span>         |
| <span data-ttu-id="645f4-122">L’organisateur peut enregistrer ou non</span><span class="sxs-lookup"><span data-stu-id="645f4-122">Organizer can record or not</span></span> | <span data-ttu-id="645f4-123">Activé et non sélectionné par défaut</span><span class="sxs-lookup"><span data-stu-id="645f4-123">Enabled and not selected by default</span></span>                  | <span data-ttu-id="645f4-124">Activé et non sélectionné par défaut</span><span class="sxs-lookup"><span data-stu-id="645f4-124">Enabled and not selected by default</span></span>   |
| <span data-ttu-id="645f4-125">N’enregistrez jamais</span><span class="sxs-lookup"><span data-stu-id="645f4-125">Never record</span></span>               | <span data-ttu-id="645f4-126">Désactivé et non sélectionné</span><span class="sxs-lookup"><span data-stu-id="645f4-126">Disabled and not selected</span></span>                            | <span data-ttu-id="645f4-127">Désactivé et non sélectionné</span><span class="sxs-lookup"><span data-stu-id="645f4-127">Disabled and not selected</span></span>      |

<span data-ttu-id="645f4-128">Lorsque la stratégie est définie sur **Toujours enregistrer,** la page de stratégie possède les options sélectionnées suivantes :</span><span class="sxs-lookup"><span data-stu-id="645f4-128">When the policy is set to **Always record**, the policy page has the following selected options:</span></span>

<span data-ttu-id="645f4-129">![Paramètres de stratégie des événements en direct](../media/live-event-recording-policy.png "Capture d’écran des paramètres de stratégie d’événements en direct dans le centre d’administration de Microsoft Teams.")</span><span class="sxs-lookup"><span data-stu-id="645f4-129">![live events policy settings](../media/live-event-recording-policy.png "Screen shot of live events policy settings in the Microsoft Teams admin center")</span></span>

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="645f4-130">Comportement de stockage et de persistance</span><span class="sxs-lookup"><span data-stu-id="645f4-130">Storage and persistence behavior</span></span>

| <span data-ttu-id="645f4-131">Option</span><span class="sxs-lookup"><span data-stu-id="645f4-131">Option</span></span>                                       | <span data-ttu-id="645f4-132">État</span><span class="sxs-lookup"><span data-stu-id="645f4-132">State</span></span>   | <span data-ttu-id="645f4-133">DVR</span><span class="sxs-lookup"><span data-stu-id="645f4-133">DVR</span></span>                                                   | <span data-ttu-id="645f4-134">VOD</span><span class="sxs-lookup"><span data-stu-id="645f4-134">VOD</span></span>                                                     | <span data-ttu-id="645f4-135">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="645f4-135">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="645f4-136">Enregistrement disponible pour les producteurs et les présentateurs</span><span class="sxs-lookup"><span data-stu-id="645f4-136">Recording available to producers and presenters</span></span> | <span data-ttu-id="645f4-137">Sélectionné</span><span class="sxs-lookup"><span data-stu-id="645f4-137">Selected</span></span>     | <span data-ttu-id="645f4-138">DVR est disponible et le bien Azure Media Services (AMS) est stocké pendant 180 jours</span><span class="sxs-lookup"><span data-stu-id="645f4-138">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="645f4-139">Les participants peuvent accéder à l’événement et le regarder</span><span class="sxs-lookup"><span data-stu-id="645f4-139">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="645f4-140">Non sélectionné</span><span class="sxs-lookup"><span data-stu-id="645f4-140">Not Selected</span></span> | <span data-ttu-id="645f4-141">DVR est disponible et le bien AMS est stocké pendant 180 jours</span><span class="sxs-lookup"><span data-stu-id="645f4-141">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="645f4-142">Le participant ne sera pas autorisé à accéder à l’événement une fois celui-ci terminé</span><span class="sxs-lookup"><span data-stu-id="645f4-142">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="645f4-143">Désactivé (non sélectionné)</span><span class="sxs-lookup"><span data-stu-id="645f4-143">Disabled (Not selected)</span></span>|<span data-ttu-id="645f4-144">DVR est disponible et l’actif AMS est supprimé après l’événement</span><span class="sxs-lookup"><span data-stu-id="645f4-144">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="645f4-145">Le participant ne sera pas autorisé à accéder à l’événement une fois celui-ci terminé</span><span class="sxs-lookup"><span data-stu-id="645f4-145">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="645f4-146">Enregistrement disponible pour les producteurs et les présentateurs</span><span class="sxs-lookup"><span data-stu-id="645f4-146">Recording available to producers and presenters</span></span> | <span data-ttu-id="645f4-147">Sélectionné</span><span class="sxs-lookup"><span data-stu-id="645f4-147">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="645f4-148">Un mp4 est créé et stocké</span><span class="sxs-lookup"><span data-stu-id="645f4-148">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="645f4-149">Non sélectionné</span><span class="sxs-lookup"><span data-stu-id="645f4-149">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="645f4-150">Aucun fichier n’est créé</span><span class="sxs-lookup"><span data-stu-id="645f4-150">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="645f4-151">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="645f4-151">Related topics</span></span>

- [<span data-ttu-id="645f4-152">Comprendre un événement en direct Teams</span><span class="sxs-lookup"><span data-stu-id="645f4-152">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="645f4-153">Offre pour les événements en direct Teams</span><span class="sxs-lookup"><span data-stu-id="645f4-153">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="645f4-154">Configurer les paramètres d’événements en direct dans Teams</span><span class="sxs-lookup"><span data-stu-id="645f4-154">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="645f4-155">Enregistrement de réunion en nuages dans Teams</span><span class="sxs-lookup"><span data-stu-id="645f4-155">Teams clouds meeting recording</span></span>](../cloud-recording.md)