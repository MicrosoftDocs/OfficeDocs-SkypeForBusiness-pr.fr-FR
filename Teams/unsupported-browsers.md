---
title: Réunions Microsoft teams sur les navigateurs non pris en charge
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment teams prend en charge l’audio et la vidéo dans les navigateurs non pris en charge.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51d19affd962b396af42f4efaec707388b186094
ms.sourcegitcommit: 27fb021e46d775652a99d862b19d94f3fc020594
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778046"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="f6fe6-103">Réunions Microsoft teams sur les navigateurs non pris en charge</span><span class="sxs-lookup"><span data-stu-id="f6fe6-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="f6fe6-104">Certains navigateurs tels qu’Internet Explorer 11, Safari et Firefox prennent en charge Microsoft teams Web App, mais ne prennent pas en charge certaines fonctionnalités d’appel et de réunion.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="f6fe6-105">Pour contourner cette limitation, Team Web App permet aux utilisateurs de recevoir du son par le biais d’une connexion RTC et de lui permettre d’afficher le contenu présenté (partage d’écran) à un tarif réduit.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

> [!Note]
> <span data-ttu-id="f6fe6-106">Les applications et services Microsoft 365 ne prennent pas en charge Internet Explorer 11 au début du 17 août 2021 (Microsoft Teams ne prend pas en charge Internet Explorer 11 plus tôt, à compter du 30 novembre 2020).</span><span class="sxs-lookup"><span data-stu-id="f6fe6-106">Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting  November 30, 2020).</span></span> <span data-ttu-id="f6fe6-107">[En savoir plus](https://aka.ms/AA97tsw).</span><span class="sxs-lookup"><span data-stu-id="f6fe6-107">[Learn more](https://aka.ms/AA97tsw).</span></span> <span data-ttu-id="f6fe6-108">Veuillez noter que le navigateur Internet Explorer 11 reste pris en charge.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-108">Please note that Internet Explorer 11 will remain a supported browser.</span></span> <span data-ttu-id="f6fe6-109">Internet Explorer 11 est un composant du système d’exploitation Windows et [suit la politique de cycle de vie](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) pour le produit sur lequel il est installé.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-109">Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is  installed.</span></span>

<span data-ttu-id="f6fe6-110">Lorsque teams détecte un navigateur non pris en charge, un message s’affiche automatiquement pour vous expliquer le problème et les limites de la session.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-110">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="f6fe6-111">Le message fournit des instructions supplémentaires pour accéder à l’audio de la réunion, par exemple pour indiquer à l’utilisateur de laisser un numéro d’appel pour que les équipes puissent appeler l’utilisateur, ou pour demander à l’utilisateur d’appeler le numéro de la Conférence incluse dans l’invitation à la réunion.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-111">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="f6fe6-112">Le message encourage également l’utilisateur à télécharger et utiliser le [client de bureau teams](https://teams.microsoft.com/downloads) pour l’expérience complète de teams.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-112">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="f6fe6-113">Si RTC n’est pas disponible, l’utilisateur ne verra pas les instructions d’accès à la réunion et ne pourra pas participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-113">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="f6fe6-114">Limitations du navigateur</span><span class="sxs-lookup"><span data-stu-id="f6fe6-114">Browser limitations</span></span>

<span data-ttu-id="f6fe6-115">Les utilisateurs d’Team Web App sur les navigateurs non pris en charge sont soumis aux limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f6fe6-115">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="f6fe6-116">L’audio est disponible via une connexion RTC uniquement.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-116">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="f6fe6-117">Les utilisateurs ne peuvent pas utiliser leur micro.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-117">Users can't use their microphone.</span></span>
- <span data-ttu-id="f6fe6-118">Les utilisateurs ne peuvent pas partager leur caméra ou voir les vidéos des autres participants, mais peuvent afficher le contenu présenté par le biais du partage d’écran basé sur une image.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-118">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="f6fe6-119">Les utilisateurs ne peuvent pas partager leur écran, même s’ils peuvent voir un écran qu’un autre participant à une réunion partage.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-119">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="f6fe6-120">Les utilisateurs ne peuvent pas prendre le contrôle pendant une session de partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-120">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="f6fe6-121">Les utilisateurs ne reçoivent pas les notifications d’appel entrant.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-121">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="f6fe6-122">Si l’appel est interrompu, la réunion ne se reconnecte pas automatiquement.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-122">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="f6fe6-123">Les utilisateurs ne peuvent pas démarrer de réunions.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-123">Users can't start meetings.</span></span>

<span data-ttu-id="f6fe6-124">Pour plus d’informations sur la prise en charge du navigateur dans Teams, voir [limites et spécifications pour teams](/microsoftteams/limits-specifications-teams#browsers).</span><span class="sxs-lookup"><span data-stu-id="f6fe6-124">For more information about browser support in Teams, see [Limits and specifications for Teams](/microsoftteams/limits-specifications-teams#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f6fe6-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f6fe6-125">Related topics</span></span>

- [<span data-ttu-id="f6fe6-126">Participation à une réunion teams sur un navigateur non pris en charge</span><span class="sxs-lookup"><span data-stu-id="f6fe6-126">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
