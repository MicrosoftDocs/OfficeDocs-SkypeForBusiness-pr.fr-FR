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
ms.openlocfilehash: 1dfd2ba704aa2428555dd126c506e1673a120b72
ms.sourcegitcommit: 46b15a11755a89526be2a0b20befad61c628cdb4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955713"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="27353-103">Réunions Microsoft teams sur les navigateurs non pris en charge</span><span class="sxs-lookup"><span data-stu-id="27353-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="27353-104">Certains navigateurs tels qu’Internet Explorer 11, Safari et Firefox prennent en charge Microsoft teams Web App, mais ne prennent pas en charge certaines fonctionnalités d’appel et de réunion.</span><span class="sxs-lookup"><span data-stu-id="27353-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="27353-105">Pour contourner cette limitation, Team Web App permet aux utilisateurs de recevoir du son par le biais d’une connexion RTC et de lui permettre d’afficher le contenu présenté (partage d’écran) à un tarif réduit.</span><span class="sxs-lookup"><span data-stu-id="27353-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

<span data-ttu-id="27353-106">Lorsque teams détecte un navigateur non pris en charge, un message s’affiche automatiquement pour vous expliquer le problème et les limites de la session.</span><span class="sxs-lookup"><span data-stu-id="27353-106">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="27353-107">Le message fournit des instructions supplémentaires pour accéder à l’audio de la réunion, par exemple pour indiquer à l’utilisateur de laisser un numéro d’appel pour que les équipes puissent appeler l’utilisateur, ou pour demander à l’utilisateur d’appeler le numéro de la Conférence incluse dans l’invitation à la réunion.</span><span class="sxs-lookup"><span data-stu-id="27353-107">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="27353-108">Le message encourage également l’utilisateur à télécharger et utiliser le [client de bureau teams](https://teams.microsoft.com/downloads) pour l’expérience complète de teams.</span><span class="sxs-lookup"><span data-stu-id="27353-108">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="27353-109">Si RTC n’est pas disponible, l’utilisateur ne verra pas les instructions d’accès à la réunion et ne pourra pas participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="27353-109">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="27353-110">Limitations du navigateur</span><span class="sxs-lookup"><span data-stu-id="27353-110">Browser limitations</span></span>

<span data-ttu-id="27353-111">Les utilisateurs d’Team Web App sur les navigateurs non pris en charge sont soumis aux limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="27353-111">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="27353-112">L’audio est disponible via une connexion RTC uniquement.</span><span class="sxs-lookup"><span data-stu-id="27353-112">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="27353-113">Les utilisateurs ne peuvent pas utiliser leur micro.</span><span class="sxs-lookup"><span data-stu-id="27353-113">Users can't use their microphone.</span></span>
- <span data-ttu-id="27353-114">Les utilisateurs ne peuvent pas partager leur caméra ou voir les vidéos des autres participants, mais peuvent afficher le contenu présenté par le biais du partage d’écran basé sur une image.</span><span class="sxs-lookup"><span data-stu-id="27353-114">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="27353-115">Les utilisateurs ne peuvent pas partager leur écran, même s’ils peuvent voir un écran qu’un autre participant à une réunion partage.</span><span class="sxs-lookup"><span data-stu-id="27353-115">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="27353-116">Les utilisateurs ne peuvent pas prendre le contrôle pendant une session de partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="27353-116">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="27353-117">Les utilisateurs ne reçoivent pas les notifications d’appel entrant.</span><span class="sxs-lookup"><span data-stu-id="27353-117">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="27353-118">Si l’appel est interrompu, la réunion ne se reconnecte pas automatiquement.</span><span class="sxs-lookup"><span data-stu-id="27353-118">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="27353-119">Les utilisateurs ne peuvent pas démarrer de réunions.</span><span class="sxs-lookup"><span data-stu-id="27353-119">Users can't start meetings.</span></span>

<span data-ttu-id="27353-120">Pour plus d’informations sur la prise en charge du navigateur dans Teams, voir [limites et spécifications pour teams](/microsoftteams/limits-specifications-teams#browsers).</span><span class="sxs-lookup"><span data-stu-id="27353-120">For more information about browser support in Teams, see [Limits and specifications for Teams](/microsoftteams/limits-specifications-teams#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="27353-121">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="27353-121">Related topics</span></span>

- [<span data-ttu-id="27353-122">Participation à une réunion teams sur un navigateur non pris en charge</span><span class="sxs-lookup"><span data-stu-id="27353-122">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
