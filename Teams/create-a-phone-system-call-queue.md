---
title: Créer une file d’attente des appels dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Découvrez comment configurer des files d’attente d’appels pour les grandes organisations dans Microsoft Teams, qui fournit un message de salutation, des attentes musicales, la redirection d’appels et d’autres fonctionnalités.
ms.openlocfilehash: c07c5a42241a62f9ecfe90340cab473800469ca9
ms.sourcegitcommit: d77104d5606ff93a792e8712d6c7780ae247b536
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "53126890"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="c3219-103">Créer une file d’attente des appels</span><span class="sxs-lookup"><span data-stu-id="c3219-103">Create a call queue</span></span>

<span data-ttu-id="c3219-104">Les files d’attente des appels utilisent une méthode de routage des appelants, qui sont orientés vers les personnes de votre organisation qui pourront les aider à résoudre un problème ou répondre à une question.</span><span class="sxs-lookup"><span data-stu-id="c3219-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="c3219-105">Les appels sont distribués les uns après les autres aux personnes présentes dans la file d’attente (appelées *agents*).</span><span class="sxs-lookup"><span data-stu-id="c3219-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

> [!TIP]
> <span data-ttu-id="c3219-106">Cet article est pour les grandes organisations.</span><span class="sxs-lookup"><span data-stu-id="c3219-106">This article is for large organizations.</span></span> <span data-ttu-id="c3219-107">Si votre organisation est une petite entreprise, lisez plutôt Créer une file d’attente [d’appels - Didacticiel](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) sur les petites entreprises.</span><span class="sxs-lookup"><span data-stu-id="c3219-107">If your organization is a small business, read [Create a call queue - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) instead.</span></span>

<span data-ttu-id="c3219-108">Les files d’attente des appels fournissent :</span><span class="sxs-lookup"><span data-stu-id="c3219-108">Call queues provide:</span></span>

- <span data-ttu-id="c3219-109">un message d’accueil.</span><span class="sxs-lookup"><span data-stu-id="c3219-109">A greeting message.</span></span>

- <span data-ttu-id="c3219-110">une musique pour les personnes en attente dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c3219-110">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="c3219-111">un routage des appels vers les agents, en utilisant la méthode *Premier entré, premier sorti* (PEPS).</span><span class="sxs-lookup"><span data-stu-id="c3219-111">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="c3219-112">Gestion des options pour le débordement et la temporisation des files d’attente.</span><span class="sxs-lookup"><span data-stu-id="c3219-112">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="c3219-113">Veillez à lire l’article [Planifier les standards automatiques et les files d’attente des appels pour Teams](plan-auto-attendant-call-queue.md), puis à suivre les [étapes de démarrage](plan-auto-attendant-call-queue.md#getting-started) avant de suivre les procédures de cet article.</span><span class="sxs-lookup"><span data-stu-id="c3219-113">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="c3219-114">Démonstration vidéo</span><span class="sxs-lookup"><span data-stu-id="c3219-114">Video demonstration</span></span>

<span data-ttu-id="c3219-115">Cette vidéo montre un exemple de base de la création d’une file d’attente d’appels dans Teams.</span><span class="sxs-lookup"><span data-stu-id="c3219-115">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a><span data-ttu-id="c3219-116">Créer la file d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="c3219-116">Create the call queue</span></span>

<span data-ttu-id="c3219-117">Pour configurer une file d’attente des appels, dans le centre d’administration Teams, développez **Voix**, cliquez sur **Files d’attente d’appels**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c3219-117">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

<span data-ttu-id="c3219-118">Saisissez un nom pour la file d’attente des appels.</span><span class="sxs-lookup"><span data-stu-id="c3219-118">Type a name for the call queue.</span></span>

### <a name="resource-accounts"></a><span data-ttu-id="c3219-119">Comptes de ressources</span><span class="sxs-lookup"><span data-stu-id="c3219-119">Resource accounts</span></span>

![Capture d’écran des paramètres du compte de ressource](media/call-queue-name-language.png)

<span data-ttu-id="c3219-121">Cliquez sur **Ajouter des comptes**, recherchez le compte de ressource que vous souhaitez utiliser avec cette file d’attente des appels, cliquez sur **Ajouter**, puis de nouveau sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c3219-121">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="c3219-122">(Les agents verront le nom du compte de ressource lorsqu’ils recevront un appel entrant.)</span><span class="sxs-lookup"><span data-stu-id="c3219-122">(Agents will see the resource account name when they receive an incoming call.)</span></span>

### <a name="assign-calling-id"></a><span data-ttu-id="c3219-123">Affecter un ID d’appel</span><span class="sxs-lookup"><span data-stu-id="c3219-123">Assign calling ID</span></span>

![Capture d’écran des paramètres d’ID d’appel](media/call-queue-assign-calling-id.png)

<span data-ttu-id="c3219-125">Si vous envisagez d’utiliser un canal Teams pour vos téléphonés, vous pouvez leur attribuer un numéro d’ID d’appelant sortant en spécifiant un ou plusieurs comptes de ressources avec un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="c3219-125">If you plan to use a Teams channel for your call agents, you can assign an outbound caller ID number for the agents by specifying one or more resource accounts with a phone number.</span></span>

<span data-ttu-id="c3219-126">Cliquez **sur** Ajouter, recherchez les comptes de ressources que vous voulez autoriser les agents à appeler à des fins d’ID lors des appels sortants, cliquez sur **Ajouter,** puis sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="c3219-126">Click **Add**, search for the resource accounts that you want to allow agents to for calling ID purposes when making outbound calls, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="c3219-127">Si vous n’utilisez pas de canal Teams pour contrôler l’appartenance à un agent, vous pouvez définir directement l’ID d’appelant pour les membres de la file d’attente d’appels sur le numéro de service de la file d’attente d’appels ou le personnel automatique approprié.</span><span class="sxs-lookup"><span data-stu-id="c3219-127">If you are not using a Teams channel to control agent membership, consider directly setting the caller ID for members of the call queue to the service number of the call queue or appropriate auto attendant.</span></span> <span data-ttu-id="c3219-128">Consultez l’article [Gérer les stratégies d’identification de l’appelant dans Microsoft Teams](caller-id-policies.md) pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="c3219-128">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

### <a name="language"></a><span data-ttu-id="c3219-129">Langue</span><span class="sxs-lookup"><span data-stu-id="c3219-129">Language</span></span>

![Capture d’écran des paramètres de langue](media/call-queue-language.png)

<span data-ttu-id="c3219-131">Choisissez une [langue prise en charge](create-a-phone-system-call-queue-languages.md).</span><span class="sxs-lookup"><span data-stu-id="c3219-131">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="c3219-132">Nous utiliserons cette langue pour les invites vocales générées par le système et la transcription de la messagerie vocale (si vous les activez).</span><span class="sxs-lookup"><span data-stu-id="c3219-132">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

### <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="c3219-133">Message d’accueil et musique de mise en attente dans la file d’attente</span><span class="sxs-lookup"><span data-stu-id="c3219-133">Greetings and music on hold in queue</span></span>

![Capture d’écran des salutations et de la musique mise en attente dans les paramètres de file d’attente](media/call-queue-greetings-music.png)

<span data-ttu-id="c3219-135">Indiquez si vous souhaitez diffuser un message d’accueil aux appelants lorsqu’ils arrivent dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c3219-135">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="c3219-136">Vous devez télécharger un fichier MP3, WAV ou WMA contenant le message d’accueil que vous souhaitez diffuser.</span><span class="sxs-lookup"><span data-stu-id="c3219-136">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="c3219-137">Teams fournit une musique par défaut aux appelants lorsqu’ils sont en attente dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c3219-137">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="c3219-138">Si vous souhaitez diffuser un fichier audio spécifique, choisissez **Lire un fichier audio** et téléchargez un fichier MP3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="c3219-138">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="c3219-139">La taille maximale de l’enregistrement téléchargé est de 5 Mo.</span><span class="sxs-lookup"><span data-stu-id="c3219-139">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="c3219-140">La musique par défaut fournie dans les files d’attente des appels Teams est exempte de toute redevance payable par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c3219-140">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

### <a name="call-agents"></a><span data-ttu-id="c3219-141">Agents d’appel</span><span class="sxs-lookup"><span data-stu-id="c3219-141">Call agents</span></span>

<span data-ttu-id="c3219-142">Examinez les [conditions d’ajout des agents à une file d’attente ](plan-auto-attendant-call-queue.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="c3219-142">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![Capture d’écran des paramètres des utilisateurs et des groupes pour les files d’attente des appels](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="c3219-144">Canal Teams</span><span class="sxs-lookup"><span data-stu-id="c3219-144">Teams channel</span></span>

<span data-ttu-id="c3219-145">Vous pouvez ajouter jusqu’à 200 agents via un canal Teams.</span><span class="sxs-lookup"><span data-stu-id="c3219-145">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="c3219-146">Si vous voulez [utiliser un canal Teams pour gérer la file d’attente](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), sélectionnez l’option **Sélectionner une équipe**, puis cliquez sur **Ajouter un canal**.</span><span class="sxs-lookup"><span data-stu-id="c3219-146">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="c3219-147">Recherchez l’équipe à utiliser, sélectionnez-la, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c3219-147">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="c3219-148">Sélectionnez le canal à utiliser, puis cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="c3219-148">Select the channel that you want to use and click **Apply**.</span></span> <span data-ttu-id="c3219-149">Vous devez être membre de l’équipe, créateur ou propriétaire du canal.</span><span class="sxs-lookup"><span data-stu-id="c3219-149">You must be a member of the team or the creator of or an owner of the channel.</span></span>

<span data-ttu-id="c3219-150">Les clients suivants sont pris en charge lors de l’utilisation d Teams pour les files d’attente d’appels :</span><span class="sxs-lookup"><span data-stu-id="c3219-150">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="c3219-151">Microsoft Teams Windows client</span><span class="sxs-lookup"><span data-stu-id="c3219-151">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="c3219-152">Client Microsoft Teams pour Mac</span><span class="sxs-lookup"><span data-stu-id="c3219-152">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="c3219-153">Utilisateurs et groupes</span><span class="sxs-lookup"><span data-stu-id="c3219-153">Users and groups</span></span>

<span data-ttu-id="c3219-154">Vous pouvez ajouter jusqu’à 20 agents individuellement et jusqu’à 200 agents via des groupes.</span><span class="sxs-lookup"><span data-stu-id="c3219-154">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="c3219-155">Si vous voulez ajouter des utilisateurs individuels ou des groupes à la file d’attente, sélectionnez l’option **Choisir des utilisateurs et des groupes**.</span><span class="sxs-lookup"><span data-stu-id="c3219-155">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="c3219-156">Pour ajouter un utilisateur à la file d’attente, cliquez sur **Ajouter des utilisateurs**, recherchez l’utilisateur, cliquez sur **Ajouter**, puis de nouveau sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c3219-156">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="c3219-157">Pour ajouter un groupe à la file d’attente, cliquez sur **Ajouter des groupes**, recherchez le groupe, cliquez sur **Ajouter**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c3219-157">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="c3219-158">Vous pouvez utiliser des listes de distribution, des groupes de sécurité et des groupes Microsoft 365 ou des équipes Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c3219-158">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="c3219-159">L’arrivée du premier appel peut prendre jusqu’à huit heures pour les nouveaux utilisateurs ajoutés à un groupe.</span><span class="sxs-lookup"><span data-stu-id="c3219-159">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

### <a name="call-routing"></a><span data-ttu-id="c3219-160">Routage des appels</span><span class="sxs-lookup"><span data-stu-id="c3219-160">Call routing</span></span>

![Capture d’écran des paramètres du mode conférence et de la méthode de routage](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="c3219-162">Le **mode conférence** réduit considérablement le temps nécessaire à la mise en relation d’un appelant avec un agent, une fois que l’agent a accepté l’appel.</span><span class="sxs-lookup"><span data-stu-id="c3219-162">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="c3219-163">Pour que le mode conférence fonctionne, les agents de la file d’attente des appels doivent utiliser l’un des clients suivants :</span><span class="sxs-lookup"><span data-stu-id="c3219-163">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="c3219-164">la dernière version du client Microsoft Teams pour ordinateur de bureau, de l’application Android ou de l’application iOS</span><span class="sxs-lookup"><span data-stu-id="c3219-164">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="c3219-165">la version 1449/1.0.94.2020051601 ou une version ultérieure du téléphone Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3219-165">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="c3219-166">Les comptes Teams des agents doivent être définis sur le mode Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="c3219-166">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="c3219-167">Les agents qui ne répondent pas aux exigences ne sont pas inclus dans la liste de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="c3219-167">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="c3219-168">Nous vous recommandons d’activer le mode conférence pour vos files d’attente des appels si tous vos agents utilisent des clients compatibles.</span><span class="sxs-lookup"><span data-stu-id="c3219-168">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="c3219-169">Le mode conférence n’est pas pris en charge si les appels téléphoniques sont acheminés vers la file d’attente à partir d’une passerelle de routage direct activée pour le routage en fonction de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="c3219-169">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="c3219-170">La **méthode de routage** détermine l’ordre dans lequel les agents reçoivent les appels de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c3219-170">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="c3219-171">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3219-171">Choose from these options:</span></span>

- <span data-ttu-id="c3219-172">Le **routage du standard** appelle tous les agents de la file d’attente en même temps.</span><span class="sxs-lookup"><span data-stu-id="c3219-172">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="c3219-173">Le premier agent à prendre l’appel reçoit l’appel.</span><span class="sxs-lookup"><span data-stu-id="c3219-173">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="c3219-174">Le **routage en série** appelle tous les agents d’appel les uns après les autres, dans l’ordre spécifié dans la liste des **Agents d’appel**.</span><span class="sxs-lookup"><span data-stu-id="c3219-174">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="c3219-175">Si un agent rejette ou ne répond pas à un appel, l’appel sera transféré à l’agent suivant et à tous les agents jusqu’à ce que l’un deux réponde ou que le temps soit écoulé.</span><span class="sxs-lookup"><span data-stu-id="c3219-175">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="c3219-176">Le **tourniquet (round robin)** équilibre le routage des appels entrants afin que chaque agent d’appel reçoive le même nombre d’appels provenant de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c3219-176">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="c3219-177">Ceci peut être utile dans un environnement de ventes entrantes pour assurer l’égalité des chances entre tous les agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="c3219-177">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="c3219-178">L’**inactivité la plus longue** achemine chaque appel vers l’agent qui a été inactif le plus longtemps.</span><span class="sxs-lookup"><span data-stu-id="c3219-178">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="c3219-179">Un agent est considéré comme inactif si son état de présence est défini sur Disponible ou si son état de présence est défini sur Absent depuis moins de 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="c3219-179">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="c3219-180">Les agents dont l’état de présence est définie sur Absent depuis plus de 10 minutes ne sont pas considérés comme inactifs et ne pourront pas recevoir d’appels tant qu’ils n’auront pas changé leur présence en Disponible.</span><span class="sxs-lookup"><span data-stu-id="c3219-180">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Capture d’écran des paramètres de routage, de désactivation et d’alerte](media/call-queue-presence-agents-time.png)

<span data-ttu-id="c3219-182">Le **routage basé sur la présence** utilise le statut de disponibilité des agents d’appel pour déterminer si un agent doit être inclus dans la liste de routage des appels pour la méthode de routage sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c3219-182">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="c3219-183">Les agents d’appel dont le statut de disponibilité est défini sur **Disponible** sont inclus dans la liste de routage des appels et peuvent recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="c3219-183">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="c3219-184">Les agents dont le statut de disponibilité est défini sur un autre statut sont exclus de la liste de routage des appels et ne recevront pas d’appels tant que leur statut de disponibilité ne sera pas défini sur **Disponible**.</span><span class="sxs-lookup"><span data-stu-id="c3219-184">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="c3219-185">Vous pouvez activer le routage des appels basé sur la présence avec toutes les méthodes de routage.</span><span class="sxs-lookup"><span data-stu-id="c3219-185">You can enable presence-based call routing with any of the routing methods.</span></span>

> [!NOTE]
> <span data-ttu-id="c3219-186">Lorsque  l’inactivité la plus longue est sélectionnée comme méthode de routage, un routage basé sur la  présence est nécessaire et activé automatiquement, même si le basculement de routage en fonction de la présence est éteint et grisé.</span><span class="sxs-lookup"><span data-stu-id="c3219-186">When **Longest idle** is selected as the routing method, presence-based routing is required and automatically enabled even though the Presence-based routing toggle will be **Off** and grayed out.</span></span>

<span data-ttu-id="c3219-187">Si un agent refuse de recevoir des appels, il ne sera pas inclus dans la liste de routage des appels, quel que soit son statut de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c3219-187">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="c3219-188">Les agents qui utilisent le client Skype Entreprise ne sont pas inclus dans la liste de routage des appels lorsque le routage basé sur la présence est activé.</span><span class="sxs-lookup"><span data-stu-id="c3219-188">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="c3219-189">Si certains de vos agents utilisent Skype Entreprise, n’activez pas le routage des appels basé sur la présence.</span><span class="sxs-lookup"><span data-stu-id="c3219-189">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="c3219-190">La **durée de l’alerte pour un agent** spécifie la durée pendant laquelle le téléphone d’un agent sonnera avant que la file d’attente ne redirige l’appel vers l’agent suivant.</span><span class="sxs-lookup"><span data-stu-id="c3219-190">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="c3219-191">Les configurations ci-dessous sont recommandées :</span><span class="sxs-lookup"><span data-stu-id="c3219-191">The following settings are recommended:</span></span>

- <span data-ttu-id="c3219-192">**Mode conférence** sur **Auto**</span><span class="sxs-lookup"><span data-stu-id="c3219-192">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="c3219-193">**Méthode de routage** sur **Tourniquet (round robin)** ou **Inactivité la plus longue**</span><span class="sxs-lookup"><span data-stu-id="c3219-193">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="c3219-194">**Routage basé sur la présence** sur **Activé**</span><span class="sxs-lookup"><span data-stu-id="c3219-194">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="c3219-195">**Durée de l’alerte pour un agent :** sur **20 secondes**</span><span class="sxs-lookup"><span data-stu-id="c3219-195">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="c3219-196">Si le routage basé sur la présence n’est pas activé et qu’il y a plusieurs appels dans la file d’attente, le système présentera ces appels simultanément aux agents, quel que soit leur statut de présence.</span><span class="sxs-lookup"><span data-stu-id="c3219-196">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="c3219-197">Cela entraînera plusieurs notifications d’appels aux agents, en particulier si certains agents ne répondent pas à l’appel initial qui leur est présenté.</span><span class="sxs-lookup"><span data-stu-id="c3219-197">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

### <a name="call-overflow-handling"></a><span data-ttu-id="c3219-198">Gestion du débordement des appels</span><span class="sxs-lookup"><span data-stu-id="c3219-198">Call overflow handling</span></span>

![Capture d’écran des paramètres de débordement des appels](media/call-queue-overflow-handling.png)

<span data-ttu-id="c3219-200">Le **nombre maximal d’appels dans la file d’attente** spécifie le nombre maximal d’appels pouvant attendre dans la file d’attente à tout moment.</span><span class="sxs-lookup"><span data-stu-id="c3219-200">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="c3219-201">La valeur par défaut est de 50, mais elle peut être définie sur une valeur comprise entre 0 et 200.</span><span class="sxs-lookup"><span data-stu-id="c3219-201">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="c3219-202">Lorsque cette limite est atteinte, l’appel est géré comme cela est indiqué par le paramètre **Lorsque le nombre maximum d’appels est atteint**.</span><span class="sxs-lookup"><span data-stu-id="c3219-202">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="c3219-203">Vous pouvez choisir de mettre fin à l’appel ou de le rediriger vers l’une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="c3219-203">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="c3219-204">Par exemple, vous pouvez demander à l’appelant de laisser un message vocal pour les agents dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c3219-204">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="c3219-205">Pour les transferts externes, veuillez vous reporter aux rubriques [Conditions préalables](plan-auto-attendant-call-queue.md#prerequisites) et [Transferts de numéros de téléphone externes : détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour le formatage des numéros.</span><span class="sxs-lookup"><span data-stu-id="c3219-205">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="c3219-206">Si le nombre maximum d’appels est défini sur 0, le message d’accueil ne sera pas diffusé.</span><span class="sxs-lookup"><span data-stu-id="c3219-206">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

### <a name="call-timeout-handling"></a><span data-ttu-id="c3219-207">Gestion de la temporisation des appels</span><span class="sxs-lookup"><span data-stu-id="c3219-207">Call timeout handling</span></span>

![Capture d’écran des paramètres de temporisation des appels](media/call-queue-timeout-handling.png)

<span data-ttu-id="c3219-209">**Temporisation de l’appel : temps d’attente maximum** spécifie la durée maximum pendant laquelle un appel peut être mis en attente dans la file d’attente avant de le rediriger ou d’y mettre fin.</span><span class="sxs-lookup"><span data-stu-id="c3219-209">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="c3219-210">Vous pouvez spécifier une valeur comprise entre 0 seconde et 45 minutes.</span><span class="sxs-lookup"><span data-stu-id="c3219-210">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="c3219-211">Vous pouvez choisir de mettre fin à l’appel ou de le rediriger vers l’une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="c3219-211">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="c3219-212">Par exemple, vous pouvez demander à l’appelant de laisser un message vocal pour les agents dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c3219-212">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="c3219-213">Pour les transferts externes, veuillez vous reporter aux rubriques [Conditions préalables](plan-auto-attendant-call-queue.md#prerequisites) et [Transferts de numéros de téléphone externes : détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour le formatage des numéros.</span><span class="sxs-lookup"><span data-stu-id="c3219-213">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="c3219-214">Lorsque vous avez sélectionné vos options de temporisation des appels, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c3219-214">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="c3219-215">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="c3219-215">Supported clients</span></span>

<span data-ttu-id="c3219-216">Les clients suivants sont pris en charge pour les agents d’appel dans une file d’attente des appels :</span><span class="sxs-lookup"><span data-stu-id="c3219-216">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="c3219-217">Client Skype Entreprise 2016 pour ordinateur de bureau (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c3219-217">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="c3219-218">Client Lync 2013 pour ordinateur de bureau (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c3219-218">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="c3219-219">Tous les modèles de téléphone IP pris en charge pour Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c3219-219">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="c3219-220">Consultez l’article [Obtenir des téléphones pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="c3219-220">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="c3219-221">Client Skype Entreprise pour Mac (version 16.8.196 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="c3219-221">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="c3219-222">Client Skype Entreprise pour Android (version 6.16.0.9 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="c3219-222">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="c3219-223">Client Skype Entreprise pour iPhone (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="c3219-223">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="c3219-224">Client Skype Entreprise pour iPad (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="c3219-224">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="c3219-225">Client Windows Microsoft Teams (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c3219-225">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="c3219-226">Client Microsoft Teams pour Mac</span><span class="sxs-lookup"><span data-stu-id="c3219-226">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="c3219-227">Microsoft Teams [infrastructure de bureau virtualisé](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix et VMware)</span><span class="sxs-lookup"><span data-stu-id="c3219-227">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="c3219-228">Application Microsoft Teams pour iPhone</span><span class="sxs-lookup"><span data-stu-id="c3219-228">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="c3219-229">Application Microsoft Teams pour Android</span><span class="sxs-lookup"><span data-stu-id="c3219-229">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3219-230">Les files d’attente des appels auxquelles un numéro de routage direct est attribué ne prennent pas en charge les clients Skype Entreprise, les clients Lync ou les téléphones IP Skype Entreprise en tant qu’agents.</span><span class="sxs-lookup"><span data-stu-id="c3219-230">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="c3219-231">Cmdlets de files d’attente des appels</span><span class="sxs-lookup"><span data-stu-id="c3219-231">Call queue cmdlets</span></span>

<span data-ttu-id="c3219-232">Vous pouvez également utiliser Windows PowerShell pour créer et configurer des files d’attente des appels.</span><span class="sxs-lookup"><span data-stu-id="c3219-232">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="c3219-233">Voici les cmdlets utilisés pour gérer une file d’attente des appels.</span><span class="sxs-lookup"><span data-stu-id="c3219-233">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="c3219-234">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c3219-234">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="c3219-235">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c3219-235">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="c3219-236">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c3219-236">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="c3219-237">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c3219-237">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="c3219-238">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="c3219-238">Related topics</span></span>

[<span data-ttu-id="c3219-239">Les avantages du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="c3219-239">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c3219-240">Obtenir des numéros de téléphone de service</span><span class="sxs-lookup"><span data-stu-id="c3219-240">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="c3219-241">Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="c3219-241">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="c3219-242">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c3219-242">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="c3219-243">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c3219-243">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
