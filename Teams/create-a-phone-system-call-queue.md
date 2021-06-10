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
ms.openlocfilehash: fe0c2863c627f728f5418cfeb9b7b17c91d246fa
ms.sourcegitcommit: 17d0108fb4d36a3f56144460683f53d77a8a0a7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52777925"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="28966-103">Créer une file d’attente des appels</span><span class="sxs-lookup"><span data-stu-id="28966-103">Create a call queue</span></span>

<span data-ttu-id="28966-104">Les files d’attente des appels utilisent une méthode de routage des appelants, qui sont orientés vers les personnes de votre organisation qui pourront les aider à résoudre un problème ou répondre à une question.</span><span class="sxs-lookup"><span data-stu-id="28966-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="28966-105">Les appels sont distribués les uns après les autres aux personnes présentes dans la file d’attente (appelées *agents*).</span><span class="sxs-lookup"><span data-stu-id="28966-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

> [!TIP]
> <span data-ttu-id="28966-106">Cet article est pour les grandes organisations.</span><span class="sxs-lookup"><span data-stu-id="28966-106">This article is for large organizations.</span></span> <span data-ttu-id="28966-107">Si votre organisation est une petite entreprise, lisez plutôt Créer une file d’attente [d’appels - Didacticiel](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) sur les petites entreprises.</span><span class="sxs-lookup"><span data-stu-id="28966-107">If your organization is a small business, read [Create a call queue - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) instead.</span></span>

<span data-ttu-id="28966-108">Les files d’attente des appels fournissent :</span><span class="sxs-lookup"><span data-stu-id="28966-108">Call queues provide:</span></span>

- <span data-ttu-id="28966-109">un message d’accueil.</span><span class="sxs-lookup"><span data-stu-id="28966-109">A greeting message.</span></span>

- <span data-ttu-id="28966-110">une musique pour les personnes en attente dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="28966-110">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="28966-111">un routage des appels vers les agents, en utilisant la méthode *Premier entré, premier sorti* (PEPS).</span><span class="sxs-lookup"><span data-stu-id="28966-111">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="28966-112">Gestion des options pour le débordement et la temporisation des files d’attente.</span><span class="sxs-lookup"><span data-stu-id="28966-112">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="28966-113">Veillez à lire l’article [Planifier les standards automatiques et les files d’attente des appels pour Teams](plan-auto-attendant-call-queue.md), puis à suivre les [étapes de démarrage](plan-auto-attendant-call-queue.md#getting-started) avant de suivre les procédures de cet article.</span><span class="sxs-lookup"><span data-stu-id="28966-113">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="28966-114">Démonstration vidéo</span><span class="sxs-lookup"><span data-stu-id="28966-114">Video demonstration</span></span>

<span data-ttu-id="28966-115">Cette vidéo montre un exemple de base de la création d’une file d’attente d’appels dans Teams.</span><span class="sxs-lookup"><span data-stu-id="28966-115">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a><span data-ttu-id="28966-116">Créer la file d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="28966-116">Create the call queue</span></span>

<span data-ttu-id="28966-117">Pour configurer une file d’attente des appels, dans le centre d’administration Teams, développez **Voix**, cliquez sur **Files d’attente d’appels**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="28966-117">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

<span data-ttu-id="28966-118">Saisissez un nom pour la file d’attente des appels.</span><span class="sxs-lookup"><span data-stu-id="28966-118">Type a name for the call queue.</span></span>

### <a name="resource-accounts"></a><span data-ttu-id="28966-119">Comptes de ressources</span><span class="sxs-lookup"><span data-stu-id="28966-119">Resource accounts</span></span>

![Capture d’écran des paramètres du compte de ressource](media/call-queue-name-language.png)

<span data-ttu-id="28966-121">Cliquez sur **Ajouter des comptes**, recherchez le compte de ressource que vous souhaitez utiliser avec cette file d’attente des appels, cliquez sur **Ajouter**, puis de nouveau sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="28966-121">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="28966-122">(Les agents verront le nom du compte de ressource lorsqu’ils recevront un appel entrant.)</span><span class="sxs-lookup"><span data-stu-id="28966-122">(Agents will see the resource account name when they receive an incoming call.)</span></span>

### <a name="assign-calling-id"></a><span data-ttu-id="28966-123">Affecter un ID d’appel</span><span class="sxs-lookup"><span data-stu-id="28966-123">Assign calling ID</span></span>

![Capture d’écran des paramètres d’ID d’appel](media/call-queue-assign-calling-id.png)

<span data-ttu-id="28966-125">Si vous envisagez d’utiliser un canal Teams pour vos télétribueurs, vous pouvez leur attribuer un numéro d’ID d’appelant sortant en spécifiant un ou plusieurs comptes de ressources avec un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="28966-125">If you plan to use a Teams channel for your call agents, you can assign an outbound caller ID number for the agents by specifying one or more resource accounts with a phone number.</span></span>

<span data-ttu-id="28966-126">Cliquez **sur** Ajouter, recherchez les comptes de ressources que vous voulez autoriser les agents à appeler à des fins d’ID lors des appels sortants, cliquez sur **Ajouter,** puis sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="28966-126">Click **Add**, search for the resource accounts that you want to allow agents to for calling ID purposes when making outbound calls, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="28966-127">Si vous n’utilisez pas de canal Teams pour contrôler l’appartenance de l’agent, vous pouvez définir directement l’ID d’appelant pour les membres de la file d’attente d’appels sur le numéro de service de la file d’attente d’appels ou le personnel automatique approprié.</span><span class="sxs-lookup"><span data-stu-id="28966-127">If you are not using a Teams channel to control agent membership, consider directly setting the caller ID for members of the call queue to the service number of the call queue or appropriate auto attendant.</span></span> <span data-ttu-id="28966-128">Consultez l’article [Gérer les stratégies d’identification de l’appelant dans Microsoft Teams](caller-id-policies.md) pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="28966-128">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

### <a name="language"></a><span data-ttu-id="28966-129">Langue</span><span class="sxs-lookup"><span data-stu-id="28966-129">Language</span></span>

![Capture d’écran des paramètres linguistiques](media/call-queue-language.png)

<span data-ttu-id="28966-131">Choisissez une [langue prise en charge](create-a-phone-system-call-queue-languages.md).</span><span class="sxs-lookup"><span data-stu-id="28966-131">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="28966-132">Nous utiliserons cette langue pour les invites vocales générées par le système et la transcription de la messagerie vocale (si vous les activez).</span><span class="sxs-lookup"><span data-stu-id="28966-132">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

### <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="28966-133">Message d’accueil et musique de mise en attente dans la file d’attente</span><span class="sxs-lookup"><span data-stu-id="28966-133">Greetings and music on hold in queue</span></span>

![Capture d’écran des salutations et de la musique mise en attente dans les paramètres de file d’attente](media/call-queue-greetings-music.png)

<span data-ttu-id="28966-135">Indiquez si vous souhaitez diffuser un message d’accueil aux appelants lorsqu’ils arrivent dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="28966-135">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="28966-136">Vous devez télécharger un fichier MP3, WAV ou WMA contenant le message d’accueil que vous souhaitez diffuser.</span><span class="sxs-lookup"><span data-stu-id="28966-136">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="28966-137">Teams fournit une musique par défaut aux appelants lorsqu’ils sont en attente dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="28966-137">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="28966-138">Si vous souhaitez diffuser un fichier audio spécifique, choisissez **Lire un fichier audio** et téléchargez un fichier MP3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="28966-138">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="28966-139">La taille maximale de l’enregistrement téléchargé est de 5 Mo.</span><span class="sxs-lookup"><span data-stu-id="28966-139">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="28966-140">La musique par défaut fournie dans les files d’attente des appels Teams est exempte de toute redevance payable par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="28966-140">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

### <a name="call-agents"></a><span data-ttu-id="28966-141">Agents d’appel</span><span class="sxs-lookup"><span data-stu-id="28966-141">Call agents</span></span>

<span data-ttu-id="28966-142">Examinez les [conditions d’ajout des agents à une file d’attente ](plan-auto-attendant-call-queue.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="28966-142">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![Capture d’écran des paramètres des utilisateurs et des groupes pour les files d’attente des appels](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="28966-144">Canal Teams</span><span class="sxs-lookup"><span data-stu-id="28966-144">Teams channel</span></span>

<span data-ttu-id="28966-145">Vous pouvez ajouter jusqu’à 200 agents via un canal Teams.</span><span class="sxs-lookup"><span data-stu-id="28966-145">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="28966-146">Si vous voulez [utiliser un canal Teams pour gérer la file d’attente](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), sélectionnez l’option **Sélectionner une équipe**, puis cliquez sur **Ajouter un canal**.</span><span class="sxs-lookup"><span data-stu-id="28966-146">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="28966-147">Recherchez l’équipe à utiliser, sélectionnez-la, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="28966-147">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="28966-148">Sélectionnez le canal à utiliser, puis cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="28966-148">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="28966-149">Les clients suivants sont pris en charge lors de l’utilisation d Teams pour les files d’attente d’appels :</span><span class="sxs-lookup"><span data-stu-id="28966-149">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="28966-150">Microsoft Teams Windows client</span><span class="sxs-lookup"><span data-stu-id="28966-150">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="28966-151">Client Microsoft Teams pour Mac</span><span class="sxs-lookup"><span data-stu-id="28966-151">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="28966-152">Utilisateurs et groupes</span><span class="sxs-lookup"><span data-stu-id="28966-152">Users and groups</span></span>

<span data-ttu-id="28966-153">Vous pouvez ajouter jusqu’à 20 agents individuellement et jusqu’à 200 agents via des groupes.</span><span class="sxs-lookup"><span data-stu-id="28966-153">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="28966-154">Si vous voulez ajouter des utilisateurs individuels ou des groupes à la file d’attente, sélectionnez l’option **Choisir des utilisateurs et des groupes**.</span><span class="sxs-lookup"><span data-stu-id="28966-154">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="28966-155">Pour ajouter un utilisateur à la file d’attente, cliquez sur **Ajouter des utilisateurs**, recherchez l’utilisateur, cliquez sur **Ajouter**, puis de nouveau sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="28966-155">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="28966-156">Pour ajouter un groupe à la file d’attente, cliquez sur **Ajouter des groupes**, recherchez le groupe, cliquez sur **Ajouter**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="28966-156">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="28966-157">Vous pouvez utiliser des listes de distribution, des groupes de sécurité et des groupes Microsoft 365 ou des équipes Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="28966-157">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="28966-158">L’arrivée du premier appel peut prendre jusqu’à huit heures pour les nouveaux utilisateurs ajoutés à un groupe.</span><span class="sxs-lookup"><span data-stu-id="28966-158">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

### <a name="call-routing"></a><span data-ttu-id="28966-159">Routage des appels</span><span class="sxs-lookup"><span data-stu-id="28966-159">Call routing</span></span>

![Capture d’écran des paramètres du mode conférence et de la méthode de routage](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="28966-161">Le **mode conférence** réduit considérablement le temps nécessaire à la mise en relation d’un appelant avec un agent, une fois que l’agent a accepté l’appel.</span><span class="sxs-lookup"><span data-stu-id="28966-161">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="28966-162">Pour que le mode conférence fonctionne, les agents de la file d’attente des appels doivent utiliser l’un des clients suivants :</span><span class="sxs-lookup"><span data-stu-id="28966-162">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="28966-163">la dernière version du client Microsoft Teams pour ordinateur de bureau, de l’application Android ou de l’application iOS</span><span class="sxs-lookup"><span data-stu-id="28966-163">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="28966-164">la version 1449/1.0.94.2020051601 ou une version ultérieure du téléphone Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28966-164">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="28966-165">Les comptes Teams des agents doivent être définis sur le mode Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="28966-165">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="28966-166">Les agents qui ne répondent pas aux exigences ne sont pas inclus dans la liste de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="28966-166">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="28966-167">Nous vous recommandons d’activer le mode conférence pour vos files d’attente des appels si tous vos agents utilisent des clients compatibles.</span><span class="sxs-lookup"><span data-stu-id="28966-167">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="28966-168">Le mode conférence n’est pas pris en charge si les appels téléphoniques sont acheminés vers la file d’attente à partir d’une passerelle de routage direct activée pour le routage en fonction de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="28966-168">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="28966-169">La **méthode de routage** détermine l’ordre dans lequel les agents reçoivent les appels de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="28966-169">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="28966-170">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="28966-170">Choose from these options:</span></span>

- <span data-ttu-id="28966-171">Le **routage du standard** appelle tous les agents de la file d’attente en même temps.</span><span class="sxs-lookup"><span data-stu-id="28966-171">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="28966-172">Le premier agent à prendre l’appel reçoit l’appel.</span><span class="sxs-lookup"><span data-stu-id="28966-172">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="28966-173">Le **routage en série** appelle tous les agents d’appel les uns après les autres, dans l’ordre spécifié dans la liste des **Agents d’appel**.</span><span class="sxs-lookup"><span data-stu-id="28966-173">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="28966-174">Si un agent rejette ou ne répond pas à un appel, l’appel sera transféré à l’agent suivant et à tous les agents jusqu’à ce que l’un deux réponde ou que le temps soit écoulé.</span><span class="sxs-lookup"><span data-stu-id="28966-174">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="28966-175">Le **tourniquet (round robin)** équilibre le routage des appels entrants afin que chaque agent d’appel reçoive le même nombre d’appels provenant de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="28966-175">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="28966-176">Ceci peut être utile dans un environnement de ventes entrantes pour assurer l’égalité des chances entre tous les agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="28966-176">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="28966-177">L’**inactivité la plus longue** achemine chaque appel vers l’agent qui a été inactif le plus longtemps.</span><span class="sxs-lookup"><span data-stu-id="28966-177">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="28966-178">Un agent est considéré comme inactif si son état de présence est défini sur Disponible ou si son état de présence est défini sur Absent depuis moins de 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="28966-178">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="28966-179">Les agents dont l’état de présence est définie sur Absent depuis plus de 10 minutes ne sont pas considérés comme inactifs et ne pourront pas recevoir d’appels tant qu’ils n’auront pas changé leur présence en Disponible.</span><span class="sxs-lookup"><span data-stu-id="28966-179">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Capture d’écran des paramètres de routage, de désactivation et d’alerte](media/call-queue-presence-agents-time.png)

<span data-ttu-id="28966-181">Le **routage basé sur la présence** utilise le statut de disponibilité des agents d’appel pour déterminer si un agent doit être inclus dans la liste de routage des appels pour la méthode de routage sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="28966-181">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="28966-182">Les agents d’appel dont le statut de disponibilité est défini sur **Disponible** sont inclus dans la liste de routage des appels et peuvent recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="28966-182">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="28966-183">Les agents dont le statut de disponibilité est défini sur un autre statut sont exclus de la liste de routage des appels et ne recevront pas d’appels tant que leur statut de disponibilité ne sera pas défini sur **Disponible**.</span><span class="sxs-lookup"><span data-stu-id="28966-183">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="28966-184">Vous pouvez activer le routage des appels basé sur la présence avec toutes les méthodes de routage.</span><span class="sxs-lookup"><span data-stu-id="28966-184">You can enable presence-based call routing with any of the routing methods.</span></span>

> [!NOTE]
> <span data-ttu-id="28966-185">Lorsque  l’inactivité la plus longue est sélectionnée comme méthode de routage, un routage basé sur la  présence est nécessaire et activé automatiquement, même si le basculement de routage en fonction de la présence est éteint et grisé.</span><span class="sxs-lookup"><span data-stu-id="28966-185">When **Longest idle** is selected as the routing method, presence-based routing is required and automatically enabled even though the Presence-based routing toggle will be **Off** and grayed out.</span></span>

<span data-ttu-id="28966-186">Si un agent refuse de recevoir des appels, il ne sera pas inclus dans la liste de routage des appels, quel que soit son statut de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="28966-186">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="28966-187">Les agents qui utilisent le client Skype Entreprise ne sont pas inclus dans la liste de routage des appels lorsque le routage basé sur la présence est activé.</span><span class="sxs-lookup"><span data-stu-id="28966-187">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="28966-188">Si certains de vos agents utilisent Skype Entreprise, n’activez pas le routage des appels basé sur la présence.</span><span class="sxs-lookup"><span data-stu-id="28966-188">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="28966-189">La **durée de l’alerte pour un agent** spécifie la durée pendant laquelle le téléphone d’un agent sonnera avant que la file d’attente ne redirige l’appel vers l’agent suivant.</span><span class="sxs-lookup"><span data-stu-id="28966-189">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="28966-190">Les configurations ci-dessous sont recommandées :</span><span class="sxs-lookup"><span data-stu-id="28966-190">The following settings are recommended:</span></span>

- <span data-ttu-id="28966-191">**Mode conférence** sur **Auto**</span><span class="sxs-lookup"><span data-stu-id="28966-191">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="28966-192">**Méthode de routage** sur **Tourniquet (round robin)** ou **Inactivité la plus longue**</span><span class="sxs-lookup"><span data-stu-id="28966-192">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="28966-193">**Routage basé sur la présence** sur **Activé**</span><span class="sxs-lookup"><span data-stu-id="28966-193">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="28966-194">**Durée de l’alerte pour un agent :** sur **20 secondes**</span><span class="sxs-lookup"><span data-stu-id="28966-194">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="28966-195">Si le routage basé sur la présence n’est pas activé et qu’il y a plusieurs appels dans la file d’attente, le système présentera ces appels simultanément aux agents, quel que soit leur statut de présence.</span><span class="sxs-lookup"><span data-stu-id="28966-195">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="28966-196">Cela entraînera plusieurs notifications d’appels aux agents, en particulier si certains agents ne répondent pas à l’appel initial qui leur est présenté.</span><span class="sxs-lookup"><span data-stu-id="28966-196">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

### <a name="call-overflow-handling"></a><span data-ttu-id="28966-197">Gestion du débordement des appels</span><span class="sxs-lookup"><span data-stu-id="28966-197">Call overflow handling</span></span>

![Capture d’écran des paramètres de débordement des appels](media/call-queue-overflow-handling.png)

<span data-ttu-id="28966-199">Le **nombre maximal d’appels dans la file d’attente** spécifie le nombre maximal d’appels pouvant attendre dans la file d’attente à tout moment.</span><span class="sxs-lookup"><span data-stu-id="28966-199">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="28966-200">La valeur par défaut est de 50, mais elle peut être définie sur une valeur comprise entre 0 et 200.</span><span class="sxs-lookup"><span data-stu-id="28966-200">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="28966-201">Lorsque cette limite est atteinte, l’appel est géré comme cela est indiqué par le paramètre **Lorsque le nombre maximum d’appels est atteint**.</span><span class="sxs-lookup"><span data-stu-id="28966-201">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="28966-202">Vous pouvez choisir de mettre fin à l’appel ou de le rediriger vers l’une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="28966-202">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="28966-203">Par exemple, vous pouvez demander à l’appelant de laisser un message vocal pour les agents dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="28966-203">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="28966-204">Pour les transferts externes, veuillez vous reporter aux rubriques [Conditions préalables](plan-auto-attendant-call-queue.md#prerequisites) et [Transferts de numéros de téléphone externes : détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour le formatage des numéros.</span><span class="sxs-lookup"><span data-stu-id="28966-204">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="28966-205">Si le nombre maximum d’appels est défini sur 0, le message d’accueil ne sera pas diffusé.</span><span class="sxs-lookup"><span data-stu-id="28966-205">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

### <a name="call-timeout-handling"></a><span data-ttu-id="28966-206">Gestion de la temporisation des appels</span><span class="sxs-lookup"><span data-stu-id="28966-206">Call timeout handling</span></span>

![Capture d’écran des paramètres de temporisation des appels](media/call-queue-timeout-handling.png)

<span data-ttu-id="28966-208">**Temporisation de l’appel : temps d’attente maximum** spécifie la durée maximum pendant laquelle un appel peut être mis en attente dans la file d’attente avant de le rediriger ou d’y mettre fin.</span><span class="sxs-lookup"><span data-stu-id="28966-208">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="28966-209">Vous pouvez spécifier une valeur comprise entre 0 seconde et 45 minutes.</span><span class="sxs-lookup"><span data-stu-id="28966-209">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="28966-210">Vous pouvez choisir de mettre fin à l’appel ou de le rediriger vers l’une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="28966-210">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="28966-211">Par exemple, vous pouvez demander à l’appelant de laisser un message vocal pour les agents dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="28966-211">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="28966-212">Pour les transferts externes, veuillez vous reporter aux rubriques [Conditions préalables](plan-auto-attendant-call-queue.md#prerequisites) et [Transferts de numéros de téléphone externes : détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour le formatage des numéros.</span><span class="sxs-lookup"><span data-stu-id="28966-212">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="28966-213">Lorsque vous avez sélectionné vos options de temporisation des appels, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="28966-213">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="28966-214">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="28966-214">Supported clients</span></span>

<span data-ttu-id="28966-215">Les clients suivants sont pris en charge pour les agents d’appel dans une file d’attente des appels :</span><span class="sxs-lookup"><span data-stu-id="28966-215">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="28966-216">Client Skype Entreprise 2016 pour ordinateur de bureau (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="28966-216">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="28966-217">Client Lync 2013 pour ordinateur de bureau (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="28966-217">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="28966-218">Tous les modèles de téléphone IP pris en charge pour Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="28966-218">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="28966-219">Consultez l’article [Obtenir des téléphones pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="28966-219">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="28966-220">Client Skype Entreprise pour Mac (version 16.8.196 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="28966-220">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="28966-221">Client Skype Entreprise pour Android (version 6.16.0.9 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="28966-221">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="28966-222">Client Skype Entreprise pour iPhone (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="28966-222">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="28966-223">Client Skype Entreprise pour iPad (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="28966-223">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="28966-224">Client Windows Microsoft Teams (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="28966-224">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="28966-225">Client Microsoft Teams pour Mac</span><span class="sxs-lookup"><span data-stu-id="28966-225">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="28966-226">Microsoft Teams [infrastructure de bureau virtualisé](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix et VMware)</span><span class="sxs-lookup"><span data-stu-id="28966-226">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="28966-227">Application Microsoft Teams pour iPhone</span><span class="sxs-lookup"><span data-stu-id="28966-227">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="28966-228">Application Microsoft Teams pour Android</span><span class="sxs-lookup"><span data-stu-id="28966-228">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="28966-229">Les files d’attente des appels auxquelles un numéro de routage direct est attribué ne prennent pas en charge les clients Skype Entreprise, les clients Lync ou les téléphones IP Skype Entreprise en tant qu’agents.</span><span class="sxs-lookup"><span data-stu-id="28966-229">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="28966-230">Cmdlets de files d’attente des appels</span><span class="sxs-lookup"><span data-stu-id="28966-230">Call queue cmdlets</span></span>

<span data-ttu-id="28966-231">Vous pouvez également utiliser Windows PowerShell pour créer et configurer des files d’attente des appels.</span><span class="sxs-lookup"><span data-stu-id="28966-231">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="28966-232">Voici les cmdlets utilisés pour gérer une file d’attente des appels.</span><span class="sxs-lookup"><span data-stu-id="28966-232">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="28966-233">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="28966-233">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="28966-234">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="28966-234">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="28966-235">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="28966-235">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="28966-236">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="28966-236">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="28966-237">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="28966-237">Related topics</span></span>

[<span data-ttu-id="28966-238">Les avantages du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="28966-238">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="28966-239">Obtenir des numéros de téléphone de service</span><span class="sxs-lookup"><span data-stu-id="28966-239">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="28966-240">Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="28966-240">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="28966-241">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="28966-241">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="28966-242">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="28966-242">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
