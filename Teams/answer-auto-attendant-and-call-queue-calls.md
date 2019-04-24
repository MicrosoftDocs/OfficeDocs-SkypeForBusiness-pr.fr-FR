---
title: Répondre aux appels dans la file d’attente ou du standard automatique directement à partir de Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Décrit les standards automatiques de nuage et files d’attente des appels et explique comment vous pouvez répondre à ces appels dans les équipes.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a94f8220cca2058e993f73241e62ff3ad0ea4f2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32210930"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="a8217-103">Répondre aux appels dans la file d’attente ou du standard automatique directement à partir de Teams</span><span class="sxs-lookup"><span data-stu-id="a8217-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="a8217-104">Les utilisateurs des équipes peuvent recevoir et répondre aux appels de standards automatiques de nuage et les files d’attente d’appel directement à partir du client de leurs équipes.</span><span class="sxs-lookup"><span data-stu-id="a8217-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span> <span data-ttu-id="a8217-105">Pour les utilisateurs d’équipes, la fonctionnalité de standard automatique est désormais disponible et la fonctionnalité de file d’attente d’appel est en mode Aperçu.</span><span class="sxs-lookup"><span data-stu-id="a8217-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="a8217-106">Que sont les standards automatiques et files d’attente des appels ?</span><span class="sxs-lookup"><span data-stu-id="a8217-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="a8217-107">Standards automatiques de nuage fournissent une série d’invites vocales ou un fichier audio que les appelants entendront au lieu d’un opérateur humain quand ils appellent vers une organisation.</span><span class="sxs-lookup"><span data-stu-id="a8217-107">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="a8217-108">Un standard automatique permet aux utilisateurs de parcourir le système de menu, de passer des appels ou de rechercher des utilisateurs en utilisant un clavier téléphonique (DTMF) ou effectuer des entrées vocales à l'aide de la reconnaissance vocale.</span><span class="sxs-lookup"><span data-stu-id="a8217-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="a8217-109">Le message d’accueil qui est utilisés lorsqu’une personne appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la capacité de recherche pour l’agent disponible appel suivant gérer l’appel pendant les personnes qui sont des appels sont les files d’attente des appels dans le nuage écoute musicale.</span><span class="sxs-lookup"><span data-stu-id="a8217-109">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="a8217-110">Vous pouvez créer une seule ligne ou plusieurs files d’attente d’appel pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a8217-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="a8217-111">Gestion d’un appel de file d’attente standard ou un appel automatique</span><span class="sxs-lookup"><span data-stu-id="a8217-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="a8217-112">Les utilisateurs pourront différencier les appels entrants à partir d’une file d’attente automatique standard ou un appel avant de prendre l’appel.</span><span class="sxs-lookup"><span data-stu-id="a8217-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="a8217-113">Ainsi que le nom et/ou le numéro de l’appelant, chaque appel inclut des informations sur qui l’appelant a essayé d’atteindre, offrant aux utilisateurs un meilleur contexte pour le traitement de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="a8217-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="a8217-114">L’illustration suivante montre l’apparence d’un appel entrant à partir d’une file d’attente automatique standard ou un appel à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a8217-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Notification d’appel entrant](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="a8217-116">Une fois que la réponse à un appel de file d’attente automatique standard ou un appel, l’utilisateur peut traiter l’appel comme n’importe quel autre appel & #x 2014 ; ils peuvent ajouter ou conférence dans un autre utilisateur ou transférer l’appel vers une autre partie.</span><span class="sxs-lookup"><span data-stu-id="a8217-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="a8217-117">En outre, les appels standard automatique seront transférés en fonction de la configuration de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a8217-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="a8217-118">File d’attente d’appel n’est pas transférés en fonction de la configuration de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a8217-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="a8217-119">Afin de garantir les appelants restent dans la file d’attente jusqu'à ce qu’un agent peut répondre à l’appel et l’appelant n’est pas transféré de manière inattendue.</span><span class="sxs-lookup"><span data-stu-id="a8217-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="a8217-120">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="a8217-120">Supported clients</span></span>

<span data-ttu-id="a8217-121">Prise en charge pour les appels de file d’attente standard et appel automatique est disponible dans les clients suivants :</span><span class="sxs-lookup"><span data-stu-id="a8217-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="a8217-122">Client Microsoft équipes Windows (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="a8217-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="a8217-123">Client Microsoft équipes Mac</span><span class="sxs-lookup"><span data-stu-id="a8217-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="a8217-124">Microsoft Teams iPhone application</span><span class="sxs-lookup"><span data-stu-id="a8217-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="a8217-125">Les équipes Microsoft pour Android</span><span class="sxs-lookup"><span data-stu-id="a8217-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="a8217-126">Configurer le support de file d’attente des standard et appel automatique pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8217-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="a8217-127">Pour recevoir le standard automatique et appels de file d’attente sur Microsoft Teams, vous devez configurer votre stratégie d’interopérabilité et mise à niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="a8217-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="a8217-128">Examinez la [Migration et interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="a8217-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="a8217-129">Si vous n’avez pas de standard automatique ou la file d’attente d’appel configuré et qu’il souhaite faire, voir [définir un standard automatique de nuage](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) et [créer une file d’attente des appels dans le nuage](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span><span class="sxs-lookup"><span data-stu-id="a8217-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) and [Create a Cloud call queue](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a8217-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8217-130">Related topics</span></span>

-   [<span data-ttu-id="a8217-131">Quel est le système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="a8217-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="a8217-132">Créer une file d’attente d’appels cloud</span><span class="sxs-lookup"><span data-stu-id="a8217-132">Create a Cloud call queue</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [<span data-ttu-id="a8217-133">Un standard Cloud automatique, qu’est-ce que c’est ?</span><span class="sxs-lookup"><span data-stu-id="a8217-133">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="a8217-134">Configurer un standard automatique dans le cloud</span><span class="sxs-lookup"><span data-stu-id="a8217-134">Set up a Cloud auto attendant</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

