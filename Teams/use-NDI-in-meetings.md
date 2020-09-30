---
title: Utiliser NDI dans Microsoft teams
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a1b756cfdb56de533d4dd170f301dc38e4b3b529
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308167"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="7d40e-103">Utiliser la technologie de® NDI dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="7d40e-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="7d40e-104">NewTek NDI® (Network Device Interface) est une solution moderne de connexion des appareils multimédias (par exemple, une caméra et un mixeur Studio).</span><span class="sxs-lookup"><span data-stu-id="7d40e-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="7d40e-105">Au lieu d’utiliser des connexions physiques, NDI® technologie permet une connectivité via un intranet local, y compris sur un ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="7d40e-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="7d40e-106">NDI® technologie est devenue une solution standard pour la production de contenus en direct et de sensibilisation et d’adoption dans le monde de la diffusion professionnelle.</span><span class="sxs-lookup"><span data-stu-id="7d40e-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="7d40e-107">Skype a déjà ajouté des fonctionnalités de® NDI à Skype au plus tard 2018.</span><span class="sxs-lookup"><span data-stu-id="7d40e-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="7d40e-108">Microsoft teams utilise cette fonctionnalité pour améliorer l’utilisation de la réunion.</span><span class="sxs-lookup"><span data-stu-id="7d40e-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="7d40e-109">NDI® technologie est limitée à un réseau local et ne doit être considérée qu’une partie du flux de travail de production, et non d’une solution de diffusion.</span><span class="sxs-lookup"><span data-stu-id="7d40e-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="7d40e-110">Activation de la technologie de® NDI</span><span class="sxs-lookup"><span data-stu-id="7d40e-110">Turn on NDI® technology</span></span>

<span data-ttu-id="7d40e-111">NDI® technologie nécessite deux étapes pour être activée pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7d40e-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="7d40e-112">L’administrateur client doit activer la propriété « AllowNDIStreaming » dans CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="7d40e-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="7d40e-113">Une fois cette modification remplie, l’utilisateur final doit activer la technologie de® NDI pour son client spécifique à partir des autorisations de **paramètres**  >  **Permissions**.</span><span class="sxs-lookup"><span data-stu-id="7d40e-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="7d40e-114">Lorsqu’un utilisateur rejoint une réunion, un message s’affiche indiquant que la réunion est en cours de diffusion.</span><span class="sxs-lookup"><span data-stu-id="7d40e-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="7d40e-115">Si les utilisateurs ne veulent pas être inclus dans la diffusion, ils devront les supprimer de la réunion.</span><span class="sxs-lookup"><span data-stu-id="7d40e-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="7d40e-116">L’image ci-après illustre le message d’une bannière qu’un utilisateur voit dans une réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="7d40e-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Image de la bannière de technologie NDI® qui s’affiche dans une réunion Teams.](media/NDI-disclosure.png)

<span data-ttu-id="7d40e-118">La bannière comporte un lien vers la [politique de confidentialité Microsoft](https://aka.ms/teamsprivacy).</span><span class="sxs-lookup"><span data-stu-id="7d40e-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="7d40e-119">Paramètres régionaux et types d’utilisateurs pris en charge</span><span class="sxs-lookup"><span data-stu-id="7d40e-119">Supported locales and user types</span></span>

<span data-ttu-id="7d40e-120">NDI® technologie est prise en charge dans tous les pays/régions.</span><span class="sxs-lookup"><span data-stu-id="7d40e-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="7d40e-121">Les utilisateurs suivants sont inclus dans un flux de technologie de® NDI, mais tous les utilisateurs ne peuvent pas accéder au flux de technologie NDI® :</span><span class="sxs-lookup"><span data-stu-id="7d40e-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="7d40e-122">In-client-support complet, fourni en fonction de sonnerie/IDClient/Id_utilisateur (géré par la stratégie de réunion)</span><span class="sxs-lookup"><span data-stu-id="7d40e-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="7d40e-123">Federated – aucun flux d’accès (même si la technologie® est activée)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7d40e-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="7d40e-124">Freemium-pas d’accès aux flux</span><span class="sxs-lookup"><span data-stu-id="7d40e-124">Freemium - no stream access</span></span>
- <span data-ttu-id="7d40e-125">Anonyme-accès sans flux</span><span class="sxs-lookup"><span data-stu-id="7d40e-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="7d40e-126">Invité – aucun flux d’accès</span><span class="sxs-lookup"><span data-stu-id="7d40e-126">Guest – no stream access</span></span>  

<span data-ttu-id="7d40e-127"><sup>1</sup> les appareils ont un paramètre de technologie NDI® activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="7d40e-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="7d40e-128">Si un participant à une réunion utilise un appareil sur lequel NDI® technologie est désactivé, il doit activer NDI technologie de®.</span><span class="sxs-lookup"><span data-stu-id="7d40e-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
