---
title: Répondre aux appels dans la file d’attente ou du standard automatique directement à partir de Teams
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 8e864e32409730373d98263215b0bcc35d9b404d
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825312"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="b1d66-103">Répondre aux appels dans la file d’attente ou du standard automatique directement à partir de Teams</span><span class="sxs-lookup"><span data-stu-id="b1d66-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="b1d66-104">Les utilisateurs teams peuvent recevoir des appels et y répondre à partir de standards automatiques Cloud et de files d’attente d’appels directement depuis leur client Teams.</span><span class="sxs-lookup"><span data-stu-id="b1d66-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span> <span data-ttu-id="b1d66-105">Pour les utilisateurs d’équipes, la fonction standard automatique est désormais disponible en général et la fonctionnalité de la file d’attente d’appels est disponible en aperçu.</span><span class="sxs-lookup"><span data-stu-id="b1d66-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="b1d66-106">Présentation des standards automatiques et des files d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="b1d66-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="b1d66-107">Les standards automatiques du Cloud fournissent une série d’invites vocales ou un fichier audio que les appelants entendent à la place d’un opérateur humain au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="b1d66-107">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="b1d66-108">Un standard automatique permet aux utilisateurs de parcourir le système de menu, de passer des appels ou de rechercher des utilisateurs en utilisant un clavier téléphonique (DTMF) ou effectuer des entrées vocales à l'aide de la reconnaissance vocale.</span><span class="sxs-lookup"><span data-stu-id="b1d66-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="b1d66-109">Les files d’attente d’appels Cloud incluent des messages d’accueil qui sont utilisés lorsque quelqu’un vous appelle pour appeler un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher le prochain agent d’appel disponible pour gérer l’appel alors que les personnes qui rejoignent les appels sont écouter de la musique pendant l’attente.</span><span class="sxs-lookup"><span data-stu-id="b1d66-109">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="b1d66-110">Vous pouvez créer des files d’attente d’appels uniques ou multiples pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b1d66-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="b1d66-111">Gestion d’un appel de standard automatique ou de file d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="b1d66-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="b1d66-112">Les utilisateurs peuvent différencier les appels entrants d’un standard automatique ou d’une file d’attente d’appels avant de répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="b1d66-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="b1d66-113">Outre le nom et/ou le numéro de l’appelant, chaque appel inclut des informations sur les personnes que l’appelant essayait de joindre, offrant ainsi aux utilisateurs un meilleur contexte pour l’adressage de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="b1d66-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="b1d66-114">L’illustration suivante décrit le mode d’affichage d’un appel entrant d’un standard automatique ou d’une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="b1d66-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Capture d’écran d’une notification d’appel entrant](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="b1d66-116">Lorsque le standard automatique ou la file d’attente d’appels est reçu, l’utilisateur peut traiter l’appel comme tout autre appel &#x2014; il peut ajouter ou organiser une conférence à un autre utilisateur ou transférer l’appel vers une autre personne.</span><span class="sxs-lookup"><span data-stu-id="b1d66-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="b1d66-117">De plus, les appels de standard automatique seront transférés en fonction de la configuration de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b1d66-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="b1d66-118">Les appels de file d’attente d’appels ne sont pas transférés en fonction de la configuration de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b1d66-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="b1d66-119">Cela permet de s’assurer que les appelants restent dans la file d’attente jusqu’à ce qu’un agent puisse répondre à l’appel et que l’appelant ne soit pas transféré de manière inattendue.</span><span class="sxs-lookup"><span data-stu-id="b1d66-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="b1d66-120">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="b1d66-120">Supported clients</span></span>

<span data-ttu-id="b1d66-121">La prise en charge des appels de standard automatique et de file d’attente d’appels est disponible dans les clients suivants :</span><span class="sxs-lookup"><span data-stu-id="b1d66-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="b1d66-122">Client Microsoft Teams (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="b1d66-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="b1d66-123">Client Microsoft teams Mac</span><span class="sxs-lookup"><span data-stu-id="b1d66-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="b1d66-124">Application Microsoft teams pour iPhone</span><span class="sxs-lookup"><span data-stu-id="b1d66-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="b1d66-125">Application Android Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="b1d66-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="b1d66-126">Configurer le standard automatique et la prise en charge de la file d’attente des appels pour Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="b1d66-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="b1d66-127">Pour recevoir des appels de standard automatique et de file d’attente d’appels sur Microsoft Teams, vous devez configurer votre stratégie d’interopérabilité et votre stratégie de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="b1d66-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="b1d66-128">Passez en revue la [migration et l’interopérabilité des organisations qui utilisent des équipes dans Skype entreprise](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="b1d66-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="b1d66-129">Si vous n’avez pas configuré le standard automatique et/ou la file d’attente d’appels, puis souhaitez le faire, voir [configurer un standard automatique Cloud](create-a-phone-system-auto-attendant.md) et [créer une file d’attente d’appels Cloud](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="b1d66-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1d66-130">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="b1d66-130">Related topics</span></span>

-   [<span data-ttu-id="b1d66-131">Qu’est-ce que le système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="b1d66-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="b1d66-132">Créer une file d’attente d’appels cloud</span><span class="sxs-lookup"><span data-stu-id="b1d66-132">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-   [<span data-ttu-id="b1d66-133">Un standard Cloud automatique, qu’est-ce que c’est ?</span><span class="sxs-lookup"><span data-stu-id="b1d66-133">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="b1d66-134">Configurer un standard automatique dans le cloud</span><span class="sxs-lookup"><span data-stu-id="b1d66-134">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

