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
ms.openlocfilehash: d971a7c9e44e2fbf7c3d2500f237e3755c5f89d0
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522901"
---
# <a name="use-ndi-in-microsoft-teams"></a><span data-ttu-id="50577-103">Utiliser NDI dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="50577-103">Use NDI in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="50577-104">Network Device Interface (NDI) est une solution moderne de connexion des appareils multimédias (caméra et mixeur Studio, par exemple).</span><span class="sxs-lookup"><span data-stu-id="50577-104">Network Device Interface (NDI) is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="50577-105">Au lieu d’utiliser les connexions physiques, NDI autorise la connectivité via un intranet local, y compris sur un ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="50577-105">Instead of using physical connections, NDI enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="50577-106">NewTek NDI® est devenu une solution standard pour la production de contenus en direct pour les flux et a gagné en connaissance et en adoption dans le monde de la diffusion professionnelle.</span><span class="sxs-lookup"><span data-stu-id="50577-106">NewTek NDI® has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="50577-107">Skype a auparavant ajouté des fonctionnalités NDIes à Skype en fin de 2018.</span><span class="sxs-lookup"><span data-stu-id="50577-107">Skype previously added NDI-Out functionality to Skype in late 2018.</span></span> <span data-ttu-id="50577-108">Microsoft teams tire parti de cette fonctionnalité pour améliorer l’utilisation de la réunion.</span><span class="sxs-lookup"><span data-stu-id="50577-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="50577-109">NDI est limité à un réseau local et ne doit être considéré qu’une partie du flux de travail de production, et non d’une solution de diffusion.</span><span class="sxs-lookup"><span data-stu-id="50577-109">NDI is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi"></a><span data-ttu-id="50577-110">Activation de NDI</span><span class="sxs-lookup"><span data-stu-id="50577-110">Turn on NDI</span></span>

<span data-ttu-id="50577-111">L’activation de NDI nécessite deux étapes.</span><span class="sxs-lookup"><span data-stu-id="50577-111">NDI requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="50577-112">L’administrateur client doit activer l’indicateur de fonctionnalité enableStreamingCallsOverNdi.</span><span class="sxs-lookup"><span data-stu-id="50577-112">The tenant admin must enable the feature flag enableStreamingCallsOverNdi.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="50577-113">Une fois cette modification remplie, l’utilisateur final doit activer NDI pour son client spécifique dans les **Settings**  >  **autorisations**de paramètres.</span><span class="sxs-lookup"><span data-stu-id="50577-113">After this change has populated, the end user must turn on NDI for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="50577-114">Lorsqu’un utilisateur rejoint une réunion, un message s’affiche indiquant que la réunion est en cours de diffusion.</span><span class="sxs-lookup"><span data-stu-id="50577-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="50577-115">Si les utilisateurs ne veulent pas être inclus dans la diffusion, ils devront les supprimer de la réunion.</span><span class="sxs-lookup"><span data-stu-id="50577-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="50577-116">L’image ci-après illustre le message d’une bannière qu’un utilisateur voit dans une réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="50577-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Image de la bannière NDI qui s’affiche dans une réunion Teams.](media/NDI-disclosure.png)

<span data-ttu-id="50577-118">La bannière comporte un lien vers la [politique de confidentialité Microsoft](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi).</span><span class="sxs-lookup"><span data-stu-id="50577-118">The banner has a link to the [Microsoft privacy policy](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="50577-119">Paramètres régionaux et types d’utilisateurs pris en charge</span><span class="sxs-lookup"><span data-stu-id="50577-119">Supported locales and user types</span></span>

<span data-ttu-id="50577-120">NDI est pris en charge dans tous les pays/régions.</span><span class="sxs-lookup"><span data-stu-id="50577-120">NDI is supported in all locales.</span></span> <span data-ttu-id="50577-121">Les utilisateurs suivants sont pris en charge dans une réunion NDI :</span><span class="sxs-lookup"><span data-stu-id="50577-121">The following users are supported in an NDI meeting:</span></span>

- <span data-ttu-id="50577-122">In-client-support complet, fourni en fonction de la sonnerie/IDClient/Id_utilisateur (gérée par la stratégie de réunion + indicateur de fonctionnalité)</span><span class="sxs-lookup"><span data-stu-id="50577-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy + Feature Flag)</span></span>
- <span data-ttu-id="50577-123">Federated-non (même lorsqu’ils ont NDI)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50577-123">Federated – no (even when they have NDI on)<sup>1</sup></span></span>
- <span data-ttu-id="50577-124">Freemium-non (valeur par défaut)</span><span class="sxs-lookup"><span data-stu-id="50577-124">Freemium - no (default value)</span></span>
- <span data-ttu-id="50577-125">Anonymat-non (valeur par défaut)</span><span class="sxs-lookup"><span data-stu-id="50577-125">Anonymous – no (default value)</span></span>
- <span data-ttu-id="50577-126">Guest-non (valeur par défaut)</span><span class="sxs-lookup"><span data-stu-id="50577-126">Guest – no  (default value)</span></span>

<span data-ttu-id="50577-127"><sup>1</sup> les appareils ont un paramètre NDI qui est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="50577-127"><sup>1</sup> Devices have an NDI setting that is on by default.</span></span> <span data-ttu-id="50577-128">Si un participant à une réunion utilise un appareil sur lequel NDI est désactivé, il doit activer NDI.</span><span class="sxs-lookup"><span data-stu-id="50577-128">If a meeting participant is using a device with NDI off, they'll need to turn on NDI.</span></span>
