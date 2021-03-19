---
title: Répondre aux appels du attendant automatique et de la file d’attente d’appels
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Décrit les files d’attente et les files d’attente automatiques dans le cloud, et explique comment vous pouvez répondre à ces appels dans Teams.
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
ms.openlocfilehash: cca068ab1194a48eb775550e4bf3f99826d82d2a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874664"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="fb778-103">Répondre aux appels dans la file d’attente ou du standard automatique directement à partir de Teams</span><span class="sxs-lookup"><span data-stu-id="fb778-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="fb778-104">Les utilisateurs de Teams peuvent recevoir et recevoir des appels à partir de attendants automatiques cloud et de files d’attente d’appels directement à partir de leur client Teams.</span><span class="sxs-lookup"><span data-stu-id="fb778-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="fb778-105">Que sont les files d’attente et les files d’attente automatiques ?</span><span class="sxs-lookup"><span data-stu-id="fb778-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="fb778-106">Les serveurs automatiques cloud fournissent une série d’invites vocales ou un fichier audio que les appelants entendent au lieu d’un opérateur lorsqu’ils appellent une organisation.</span><span class="sxs-lookup"><span data-stu-id="fb778-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="fb778-107">Un standard automatique permet aux utilisateurs de parcourir le système de menu, de passer des appels ou de rechercher des utilisateurs en utilisant un clavier téléphonique (DTMF) ou effectuer des entrées vocales à l'aide de la reconnaissance vocale.</span><span class="sxs-lookup"><span data-stu-id="fb778-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="fb778-108">Les files d’attente d’appels cloud incluent des salutations qui sont utilisées lorsque quelqu’un appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher le prochain agent d’appel disponible pour gérer l’appel pendant que l’appelant écoute la musique mise en attente.</span><span class="sxs-lookup"><span data-stu-id="fb778-108">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="fb778-109">Vous pouvez créer une ou plusieurs files d’attente pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fb778-109">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="fb778-110">Gestion d’un traitement automatique ou d’un appel de la file d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="fb778-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="fb778-111">Les utilisateurs pourront différencier les appels entrants à partir d’un traitement automatique ou d’une file d’attente d’appels avant de répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="fb778-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="fb778-112">En plus du nom et/ou du numéro de l’appelant, chaque appel inclut des informations sur les personnes que l’appelant essayait de joindre, afin de donner aux utilisateurs un meilleur contexte pour s’adresser à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="fb778-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="fb778-113">L’illustration suivante montre comment un appel entrant d’un employé de service automatique ou d’une file d’attente d’appels s’affiche pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fb778-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Capture d’écran d’une notification d’appel entrant](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="fb778-115">Une fois qu’un attendant automatique ou un appel de la file d’attente d’appels a été reçu, l’utilisateur peut traiter l’appel comme n’importe quel autre &#x2014; il peut ajouter ou conférencer dans un autre utilisateur ou transférer l’appel à une autre partie.</span><span class="sxs-lookup"><span data-stu-id="fb778-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="fb778-116">Par ailleurs, les appels du attendant automatique seront transmis en fonction de la configuration de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fb778-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="fb778-117">Les appels de la file d’attente ne sont pas transmis en fonction de la configuration de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fb778-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="fb778-118">Ceci permet de s’assurer que les appelants restent dans la file d’attente jusqu’à ce qu’un agent puisse répondre à l’appel et que l’appelant ne soit pas transmis de manière inattendue.</span><span class="sxs-lookup"><span data-stu-id="fb778-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

> <span data-ttu-id="fb778-119">Les agents sont informés des appels manqués ou des messages vocaux pour les appels de la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="fb778-119">Agents are not notified of any missed calls or voicemails for call queue calls.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="fb778-120">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="fb778-120">Supported clients</span></span>

<span data-ttu-id="fb778-121">La prise en charge du service de support automatique et des appels en file d’attente est disponible dans les clients suivants :</span><span class="sxs-lookup"><span data-stu-id="fb778-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="fb778-122">Client Windows Microsoft Teams (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="fb778-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="fb778-123">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="fb778-123">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="fb778-124">Application Microsoft Teams pour iPhone</span><span class="sxs-lookup"><span data-stu-id="fb778-124">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="fb778-125">Application Microsoft Teams pour Android</span><span class="sxs-lookup"><span data-stu-id="fb778-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="fb778-126">Configurer le support de la file d’attente automatique et du support des files d’attente pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fb778-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="fb778-127">Pour recevoir des appels de attendant automatique et de file d’attente sur Microsoft Teams, vous devez configurer votre stratégie d’interopérabilité et de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="fb778-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="fb778-128">Consultez la [migration et l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="fb778-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="fb778-129">Si vous n’avez pas de attendant automatique et/ou de file d’attente d’appels configuré et souhaitez le faire, consultez Configurer un attendant [automatique](create-a-phone-system-auto-attendant.md) cloud et Créer une file d’attente d’appels [cloud.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="fb778-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="fb778-130">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="fb778-130">Known Issues</span></span>

<span data-ttu-id="fb778-131">Lorsqu’un agent de la file d’attente d’appels reçoit un appel sur son appareil mobile, les appels peuvent être mis en attente si l’appareil est verrouillé.</span><span class="sxs-lookup"><span data-stu-id="fb778-131">When a call queue agents receives a call on their mobile device, calls may go on hold if the device is locked.</span></span> <span data-ttu-id="fb778-132">L’utilisateur doit tout d’abord déverrouiller l’appareil, puis répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="fb778-132">User must unlock device first and then answer the call.</span></span>


## <a name="related-topics"></a><span data-ttu-id="fb778-133">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="fb778-133">Related topics</span></span>

-    [<span data-ttu-id="fb778-134">Qu’est-ce que Phone System dans Microsoft 365 ou Office 365 ?</span><span class="sxs-lookup"><span data-stu-id="fb778-134">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="fb778-135">Créer une file d’attente d’appels cloud</span><span class="sxs-lookup"><span data-stu-id="fb778-135">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="fb778-136">Un standard Cloud automatique, qu’est-ce que c’est ?</span><span class="sxs-lookup"><span data-stu-id="fb778-136">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="fb778-137">Configurer un standard automatique dans le cloud</span><span class="sxs-lookup"><span data-stu-id="fb778-137">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

