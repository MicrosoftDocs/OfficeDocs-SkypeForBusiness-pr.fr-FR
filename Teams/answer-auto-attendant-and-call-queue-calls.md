---
title: Répondre aux appels de la file d’attente automatique et des appels
ms.reviewer: waseemh
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Décrit les standards automatiques du Cloud et les files d’attente d’appels, et explique comment vous pouvez répondre à ces appels dans Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ea09e005dea2a89cb23b55a8ac59eaf491df460
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582821"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="b2414-103">Répondre aux appels dans la file d’attente ou du standard automatique directement à partir de Teams</span><span class="sxs-lookup"><span data-stu-id="b2414-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="b2414-104">Les utilisateurs teams peuvent recevoir des appels et y répondre à partir de standards automatiques Cloud et de files d’attente d’appels directement depuis leur client Teams.</span><span class="sxs-lookup"><span data-stu-id="b2414-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="b2414-105">Présentation des standards automatiques et des files d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="b2414-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="b2414-106">Les standards automatiques du Cloud fournissent une série d’invites vocales ou un fichier audio que les appelants entendent à la place d’un opérateur humain au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="b2414-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="b2414-107">Un standard automatique permet aux utilisateurs de parcourir le système de menu, de passer des appels ou de rechercher des utilisateurs en utilisant un clavier téléphonique (DTMF) ou effectuer des entrées vocales à l'aide de la reconnaissance vocale.</span><span class="sxs-lookup"><span data-stu-id="b2414-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="b2414-108">Les files d’attente d’appels Cloud incluent des messages d’accueil qui sont utilisés lorsque quelqu’un vous appelle pour appeler un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher le prochain agent d’appel disponible pour gérer l’appel alors que les personnes qui appellent écoutent de la musique pendant l’attente.</span><span class="sxs-lookup"><span data-stu-id="b2414-108">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="b2414-109">Vous pouvez créer des files d’attente d’appels uniques ou multiples pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b2414-109">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="b2414-110">Gestion d’un appel de standard automatique ou de file d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="b2414-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="b2414-111">Les utilisateurs peuvent différencier les appels entrants d’un standard automatique ou d’une file d’attente d’appels avant de répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="b2414-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="b2414-112">Outre le nom et/ou le numéro de l’appelant, chaque appel inclut des informations sur les personnes que l’appelant essayait de joindre, offrant ainsi aux utilisateurs un meilleur contexte pour l’adressage de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b2414-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="b2414-113">L’illustration suivante décrit le mode d’affichage d’un appel entrant d’un standard automatique ou d’une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="b2414-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Capture d’écran d’une notification d’appel entrant](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="b2414-115">Lorsque le standard automatique ou la file d’attente d’appels est reçu, l’utilisateur peut traiter l’appel comme tout autre appel &#x2014; il peut ajouter ou organiser une conférence à un autre utilisateur ou transférer l’appel vers une autre personne.</span><span class="sxs-lookup"><span data-stu-id="b2414-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="b2414-116">De plus, les appels de standard automatique seront transférés en fonction de la configuration de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b2414-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="b2414-117">Les appels de file d’attente d’appels ne sont pas transférés en fonction de la configuration de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b2414-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="b2414-118">Cela permet de s’assurer que les appelants restent dans la file d’attente jusqu’à ce qu’un agent puisse répondre à l’appel et que l’appelant ne soit pas transféré de manière inattendue.</span><span class="sxs-lookup"><span data-stu-id="b2414-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="b2414-119">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="b2414-119">Supported clients</span></span>

<span data-ttu-id="b2414-120">La prise en charge des appels de standard automatique et de file d’attente d’appels est disponible dans les clients suivants :</span><span class="sxs-lookup"><span data-stu-id="b2414-120">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="b2414-121">Client Microsoft Teams (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="b2414-121">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="b2414-122">Client Microsoft teams Mac</span><span class="sxs-lookup"><span data-stu-id="b2414-122">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="b2414-123">Application Microsoft teams pour iPhone</span><span class="sxs-lookup"><span data-stu-id="b2414-123">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="b2414-124">Application Android Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="b2414-124">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="b2414-125">Configurer le standard automatique et la prise en charge de la file d’attente des appels pour Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="b2414-125">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="b2414-126">Pour recevoir des appels de standard automatique et de file d’attente d’appels sur Microsoft Teams, vous devez configurer votre stratégie d’interopérabilité et votre stratégie de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="b2414-126">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="b2414-127">Passez en revue la [migration et l’interopérabilité des organisations qui utilisent des équipes dans Skype entreprise](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="b2414-127">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="b2414-128">Si vous n’avez pas configuré le standard automatique et/ou la file d’attente d’appels, puis souhaitez le faire, voir [configurer un standard automatique Cloud](create-a-phone-system-auto-attendant.md) et [créer une file d’attente d’appels Cloud](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="b2414-128">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b2414-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2414-129">Related topics</span></span>

-    [<span data-ttu-id="b2414-130">Qu’est-ce que le système téléphonique dans Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="b2414-130">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="b2414-131">Créer une file d’attente d’appels cloud</span><span class="sxs-lookup"><span data-stu-id="b2414-131">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="b2414-132">Un standard Cloud automatique, qu’est-ce que c’est ?</span><span class="sxs-lookup"><span data-stu-id="b2414-132">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="b2414-133">Configurer un standard automatique dans le cloud</span><span class="sxs-lookup"><span data-stu-id="b2414-133">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

