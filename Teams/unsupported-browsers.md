---
title: Réunions Microsoft Teams sur des navigateurs non pris en compte
author: cichur
ms.author: v-cichur
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
description: Découvrez comment Teams prend en charge l’audio et la vidéo dans les navigateurs non pris en charge.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83617628fe04140c45b005e993d95eac34c6f8bd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121312"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="66cd9-103">Réunions Microsoft Teams sur des navigateurs non pris en compte</span><span class="sxs-lookup"><span data-stu-id="66cd9-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="66cd9-104">Certains navigateurs, tels qu’Internet Explorer 11, Safari et Firefox, ne supportent pas l’application web Microsoft Teams, mais pas certaines des fonctionnalités d’appel et de réunion de Teams.</span><span class="sxs-lookup"><span data-stu-id="66cd9-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="66cd9-105">Pour contourner cette limitation, l’application web Teams permet aux utilisateurs de recevoir de l’audio via une connexion PSTN et leur permet d’afficher du contenu présenté (partage d’écran) à une vitesse d’affichage réduite.</span><span class="sxs-lookup"><span data-stu-id="66cd9-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

> [!Note]
> <span data-ttu-id="66cd9-106">Les applications et services Microsoft 365 ne prendra pas en charge Internet Explorer 11 à compter du 17 août 2021 (Microsoft Teams ne prendra pas en charge Internet Explorer 11 plus tôt, à compter du 30 novembre 2020).</span><span class="sxs-lookup"><span data-stu-id="66cd9-106">Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting  November 30, 2020).</span></span> <span data-ttu-id="66cd9-107">[En savoir plus](https://aka.ms/AA97tsw).</span><span class="sxs-lookup"><span data-stu-id="66cd9-107">[Learn more](https://aka.ms/AA97tsw).</span></span> <span data-ttu-id="66cd9-108">Veuillez noter que le navigateur Internet Explorer 11 restera un navigateur pris en charge.</span><span class="sxs-lookup"><span data-stu-id="66cd9-108">Please note that Internet Explorer 11 will remain a supported browser.</span></span> <span data-ttu-id="66cd9-109">Internet Explorer 11 est un composant [](/lifecycle/faq/internet-explorer-microsoft-edge) du système d’exploitation Windows et suit la politique de cycle de vie du produit sur lequel il est installé.</span><span class="sxs-lookup"><span data-stu-id="66cd9-109">Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is  installed.</span></span>

<span data-ttu-id="66cd9-110">Lorsque Teams détecte un navigateur non pris en défaut, il affiche automatiquement un message expliquant le problème et les limites de la session.</span><span class="sxs-lookup"><span data-stu-id="66cd9-110">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="66cd9-111">Le message fournit des instructions supplémentaires pour accéder à l’audio de la réunion, par exemple en conseillant à l’utilisateur de laisser un numéro de rappeler pour que Teams puisse appeler l’utilisateur, ou en lui demandez d’appeler le numéro de conférence inclus dans l’invitation à la réunion.</span><span class="sxs-lookup"><span data-stu-id="66cd9-111">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="66cd9-112">Ce message encourage également l’utilisateur à télécharger et à utiliser le client de [bureau Teams](https://teams.microsoft.com/downloads) pour une expérience Teams complète.</span><span class="sxs-lookup"><span data-stu-id="66cd9-112">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="66cd9-113">Si PSTN n’est pas disponible, l’utilisateur ne voit pas les instructions pour accéder à la réunion et ne peut pas participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="66cd9-113">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="66cd9-114">Limites du navigateur</span><span class="sxs-lookup"><span data-stu-id="66cd9-114">Browser limitations</span></span>

<span data-ttu-id="66cd9-115">Les personnes qui utilisent l’application web Teams sur des navigateurs non pris en défaut rencontreront les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="66cd9-115">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="66cd9-116">Le son est disponible uniquement via une connexion RSTN.</span><span class="sxs-lookup"><span data-stu-id="66cd9-116">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="66cd9-117">Les utilisateurs ne peuvent pas utiliser leur microphone.</span><span class="sxs-lookup"><span data-stu-id="66cd9-117">Users can't use their microphone.</span></span>
- <span data-ttu-id="66cd9-118">Les utilisateurs ne peuvent pas partager leur caméra ni voir les vidéos des autres participants, mais peuvent afficher le contenu présenté via le partage d’écran basé sur les images.</span><span class="sxs-lookup"><span data-stu-id="66cd9-118">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="66cd9-119">Les utilisateurs ne peuvent pas partager leur écran, même s’ils peuvent voir un écran partagé par un autre participant à la réunion.</span><span class="sxs-lookup"><span data-stu-id="66cd9-119">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="66cd9-120">Les utilisateurs ne peuvent pas prendre le contrôle pendant une session de partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="66cd9-120">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="66cd9-121">Les utilisateurs ne recevront pas de notifications d’appel entrant.</span><span class="sxs-lookup"><span data-stu-id="66cd9-121">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="66cd9-122">Si l’appel est interrompu, la réunion ne se reconnecte pas automatiquement.</span><span class="sxs-lookup"><span data-stu-id="66cd9-122">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="66cd9-123">Les utilisateurs ne peuvent pas démarrer de réunions.</span><span class="sxs-lookup"><span data-stu-id="66cd9-123">Users can't start meetings.</span></span>

<span data-ttu-id="66cd9-124">Pour plus d’informations sur la prise en charge du navigateur dans Teams, voir [Limites et spécifications pour Teams.](./limits-specifications-teams.md#browsers)</span><span class="sxs-lookup"><span data-stu-id="66cd9-124">For more information about browser support in Teams, see [Limits and specifications for Teams](./limits-specifications-teams.md#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="66cd9-125">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="66cd9-125">Related topics</span></span>

- [<span data-ttu-id="66cd9-126">Participer à une réunion Teams sur un navigateur non pris en défaut</span><span class="sxs-lookup"><span data-stu-id="66cd9-126">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)