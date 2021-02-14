---
title: Utiliser NDI dans Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser NDI dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1ad11000de2ae0dac7563d785dfaea8c34978ed
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337013"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="ef171-103">Utiliser la technologie ® NDI dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ef171-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="ef171-104">La technologie NewTek NDI® (Network Device Interface) est une solution moderne pour connecter des périphériques multimédias (par exemple, une caméra de studio et un mixer).</span><span class="sxs-lookup"><span data-stu-id="ef171-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="ef171-105">Au lieu d’utiliser des connexions physiques, la technologie NDI® active la connectivité sur un intranet local, y compris sur un ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="ef171-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="ef171-106">La technologie NDI® est devenue une solution du secteur standard pour la production de contenu en direct pour les flux et a acquis une connaissance et une adoption significatives du monde de la diffusion professionnelle.</span><span class="sxs-lookup"><span data-stu-id="ef171-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="ef171-107">Skype a ajouté précédemment NDI®-out à Skype fin 2018.</span><span class="sxs-lookup"><span data-stu-id="ef171-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="ef171-108">Microsoft Teams utilise cette fonctionnalité pour améliorer l’expérience de réunion.</span><span class="sxs-lookup"><span data-stu-id="ef171-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="ef171-109">La technologie NDI® est limitée à un réseau local et ne doit être considérée qu’comme faisant partie du flux de travail de production, et non d’une solution de diffusion.</span><span class="sxs-lookup"><span data-stu-id="ef171-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="ef171-110">Activer la technologie NDI®</span><span class="sxs-lookup"><span data-stu-id="ef171-110">Turn on NDI® technology</span></span>

<span data-ttu-id="ef171-111">La technologie ® NDI nécessite deux étapes pour être mise en marche pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ef171-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="ef171-112">L’administrateur client doit activer la propriété « AllowNDIStreaming » dans CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="ef171-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="ef171-113">Une fois cette modification remplie, l’utilisateur final doit activer la technologie NDI® de son client spécifique à partir des  >  **autorisations de paramètres.**</span><span class="sxs-lookup"><span data-stu-id="ef171-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="ef171-114">Lorsqu’un utilisateur rejoint une réunion, un message l’informe de la diffusion de la réunion.</span><span class="sxs-lookup"><span data-stu-id="ef171-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="ef171-115">Si les utilisateurs ne souhaitent pas être inclus dans la diffusion, ils doivent abandonner la réunion.</span><span class="sxs-lookup"><span data-stu-id="ef171-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="ef171-116">L’image suivante montre le message bannière qu’un utilisateur voit dans une réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="ef171-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Bannière technologie ® NDI qui s’affiche dans une réunion Teams.](media/NDI-disclosure.png)

<span data-ttu-id="ef171-118">La bannière est un lien vers la politique [de confidentialité de Microsoft.](https://aka.ms/teamsprivacy)</span><span class="sxs-lookup"><span data-stu-id="ef171-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="ef171-119">Paramètres régionaux et types d’utilisateur pris en charge</span><span class="sxs-lookup"><span data-stu-id="ef171-119">Supported locales and user types</span></span>

<span data-ttu-id="ef171-120">La technologie ® NDI est prise en charge dans tous les paramètres régionaux.</span><span class="sxs-lookup"><span data-stu-id="ef171-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="ef171-121">Les utilisateurs suivants sont inclus dans un flux ® NDI, mais tous ne peuvent pas accéder au flux de technologie NDI® :</span><span class="sxs-lookup"><span data-stu-id="ef171-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="ef171-122">Dans le client : support total, livré en fonction de l’anneau/tenantId/userId (contrôlé par la stratégie Réunions)</span><span class="sxs-lookup"><span data-stu-id="ef171-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="ef171-123">Fédérés – aucun accès aux flux (même s’ils ont NDI® sur)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ef171-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="ef171-124">Premium - pas d’accès aux flux</span><span class="sxs-lookup"><span data-stu-id="ef171-124">Premium - no stream access</span></span>
- <span data-ttu-id="ef171-125">Anonyme – aucun accès aux flux</span><span class="sxs-lookup"><span data-stu-id="ef171-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="ef171-126">Invité – aucun accès aux flux</span><span class="sxs-lookup"><span data-stu-id="ef171-126">Guest – no stream access</span></span>  

<span data-ttu-id="ef171-127"><sup>1 Les</sup> appareils ont un paramètre ® NDI qui est par défaut.</span><span class="sxs-lookup"><span data-stu-id="ef171-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="ef171-128">Si un participant à la réunion utilise un appareil avec la technologie NDI® est éteinte, il doit activer la technologie ® NDI.</span><span class="sxs-lookup"><span data-stu-id="ef171-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
