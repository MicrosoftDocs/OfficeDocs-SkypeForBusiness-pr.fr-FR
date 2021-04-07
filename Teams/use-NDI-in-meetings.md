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
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598463"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="f5003-103">Utiliser la technologie ® NDI dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5003-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="f5003-104">La technologie NewTek NDI® (Network Device Interface) est une solution moderne pour connecter des périphériques multimédias (par exemple, une caméra de studio et un mixer).</span><span class="sxs-lookup"><span data-stu-id="f5003-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="f5003-105">Au lieu d’utiliser des connexions physiques, la technologie NDI® active la connectivité sur un intranet local, y compris sur un ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="f5003-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="f5003-106">La technologie NDI® est devenue une solution du secteur standard pour la production de contenu en direct pour les flux et a acquis une connaissance et une adoption significatives du monde de la diffusion professionnelle.</span><span class="sxs-lookup"><span data-stu-id="f5003-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="f5003-107">Skype a ajouté précédemment NDI®-out à Skype fin 2018.</span><span class="sxs-lookup"><span data-stu-id="f5003-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="f5003-108">Microsoft Teams utilise cette fonctionnalité pour améliorer l’expérience de réunion.</span><span class="sxs-lookup"><span data-stu-id="f5003-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="f5003-109">La technologie NDI® est limitée à un réseau local et ne doit être considérée qu’comme faisant partie du flux de travail de production, et non d’une solution de diffusion.</span><span class="sxs-lookup"><span data-stu-id="f5003-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="f5003-110">Activer la technologie NDI®</span><span class="sxs-lookup"><span data-stu-id="f5003-110">Turn on NDI® technology</span></span>

<span data-ttu-id="f5003-111">La technologie ® NDI nécessite deux étapes pour être mise en marche pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f5003-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="f5003-112">L’administrateur des locataires doit activer la propriété « AllowNDIStreaming » dans CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="f5003-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="f5003-113">Une fois cette modification remplie, l’utilisateur final doit activer la technologie NDI® de son client spécifique à partir des  >  **autorisations de paramètres.**</span><span class="sxs-lookup"><span data-stu-id="f5003-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="f5003-114">Lorsqu’un utilisateur rejoint une réunion, un message l’avertit de la diffusion de la réunion.</span><span class="sxs-lookup"><span data-stu-id="f5003-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="f5003-115">Si les utilisateurs ne souhaitent pas être inclus dans la diffusion, ils doivent abandonner la réunion.</span><span class="sxs-lookup"><span data-stu-id="f5003-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="f5003-116">L’image suivante montre le message bannière qu’un utilisateur voit dans une réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="f5003-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Bannière technologie ® NDI qui s’affiche dans une réunion Teams.](media/NDI-disclosure.png)

<span data-ttu-id="f5003-118">La bannière est un lien vers la politique [de confidentialité de Microsoft.](https://aka.ms/teamsprivacy)</span><span class="sxs-lookup"><span data-stu-id="f5003-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

> [!NOTE]
> <span data-ttu-id="f5003-119">NDI® est activé par session uniquement.</span><span class="sxs-lookup"><span data-stu-id="f5003-119">NDI® is activated per session only.</span></span> <span data-ttu-id="f5003-120">Lors de la prochaine connexion, l’utilisateur doit l’activer avant d’utiliser NDI®.</span><span class="sxs-lookup"><span data-stu-id="f5003-120">On the next login, the user must activate it before using NDI®.</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="f5003-121">Paramètres régionaux et types d’utilisateur pris en charge</span><span class="sxs-lookup"><span data-stu-id="f5003-121">Supported locales and user types</span></span>

<span data-ttu-id="f5003-122">La technologie ® NDI est prise en charge dans tous les paramètres régionaux.</span><span class="sxs-lookup"><span data-stu-id="f5003-122">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="f5003-123">Les utilisateurs suivants sont inclus dans un flux de technologie NDI® mais tous ne peuvent pas accéder au flux de technologie NDI® :</span><span class="sxs-lookup"><span data-stu-id="f5003-123">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="f5003-124">Dans le client : support total, livré en fonction de l’anneau/tenantId/userId (contrôlé par la stratégie Réunions)</span><span class="sxs-lookup"><span data-stu-id="f5003-124">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="f5003-125">Fédérés – aucun accès aux flux (même s’ils ont NDI® sur)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5003-125">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="f5003-126">Premium - pas d’accès aux flux</span><span class="sxs-lookup"><span data-stu-id="f5003-126">Premium - no stream access</span></span>
- <span data-ttu-id="f5003-127">Anonyme – aucun accès aux flux</span><span class="sxs-lookup"><span data-stu-id="f5003-127">Anonymous – no stream access</span></span>
- <span data-ttu-id="f5003-128">Invité – aucun accès aux flux</span><span class="sxs-lookup"><span data-stu-id="f5003-128">Guest – no stream access</span></span>  

<span data-ttu-id="f5003-129"><sup>1 Les</sup> appareils ont un paramètre ® NDI qui est par défaut.</span><span class="sxs-lookup"><span data-stu-id="f5003-129"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="f5003-130">Si un participant à la réunion utilise un appareil avec la technologie NDI® est éteinte, il doit activer la technologie ® NDI.</span><span class="sxs-lookup"><span data-stu-id="f5003-130">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
