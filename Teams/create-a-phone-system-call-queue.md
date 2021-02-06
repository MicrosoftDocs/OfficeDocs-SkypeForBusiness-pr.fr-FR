---
title: Créer une file d’attente d’appels dans Microsoft Teams
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
description: Découvrez comment configurer phone system pour les files d’attente avec Microsoft Teams, qui fournissent un message de salutation, de la musique, la redirection d’appels et d’autres fonctionnalités.
ms.openlocfilehash: 17e15e270492c4105f79ead6b2ce34ca37165ec3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125787"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="20847-103">Créer une file d’attente d’appel</span><span class="sxs-lookup"><span data-stu-id="20847-103">Create a call queue</span></span>

<span data-ttu-id="20847-104">Les files d’attente permettent de router les appelants vers des personnes de votre organisation qui peuvent vous aider à répondre à un problème ou une question spécifique.</span><span class="sxs-lookup"><span data-stu-id="20847-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="20847-105">Les appels sont distribués un par un aux personnes dans la file d’attente (appelées *agents).*</span><span class="sxs-lookup"><span data-stu-id="20847-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="20847-106">Les files d’attente fournissent les services :</span><span class="sxs-lookup"><span data-stu-id="20847-106">Call queues provide:</span></span>

- <span data-ttu-id="20847-107">Message de salutation.</span><span class="sxs-lookup"><span data-stu-id="20847-107">A greeting message.</span></span>

- <span data-ttu-id="20847-108">Musique pendant que des personnes sont en attente dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="20847-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="20847-109">Routage des appels *(dans l’ordre* Premier dans, Premier sorti (FIFO) - vers des agents.</span><span class="sxs-lookup"><span data-stu-id="20847-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="20847-110">Options de gestion pour le dépassement de capacité et le délai d’attente.</span><span class="sxs-lookup"><span data-stu-id="20847-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="20847-111">Assurez-vous de lire l’article Plan pour les [](plan-auto-attendant-call-queue.md#getting-started) standard [automatiques Teams](plan-auto-attendant-call-queue.md) et les files d’attente d’appels, et suivez les étapes de mise en place avant de suivre les procédures de cet article.</span><span class="sxs-lookup"><span data-stu-id="20847-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="20847-112">Pour configurer une file d’attente d’appels, dans le Centre d’administration Teams, développez **Voix,** cliquez sur Files d’attente d’appels, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="20847-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="20847-113">Compte et langue des ressources</span><span class="sxs-lookup"><span data-stu-id="20847-113">Resource account and language</span></span>

![Capture d’écran des paramètres de compte de ressource et de langue](media/call-queue-name-language.png)

1. <span data-ttu-id="20847-115">Tapez un nom pour la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="20847-115">Type a name for the call queue.</span></span> <span data-ttu-id="20847-116">Les agents voient ce nom lorsqu’ils reçoivent un appel entrant de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="20847-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="20847-117">Cliquez **sur Ajouter des comptes,** recherchez le compte de ressource à utiliser avec cette file d’attente d’appels, cliquez sur Ajouter, puis sur **Ajouter.** </span><span class="sxs-lookup"><span data-stu-id="20847-117">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="20847-118">Choisissez une langue.</span><span class="sxs-lookup"><span data-stu-id="20847-118">Choose a language.</span></span> <span data-ttu-id="20847-119">Cette langue sera utilisée pour les invites vocales générées par le système et la transcription des messages vocaux (si vous les activez).</span><span class="sxs-lookup"><span data-stu-id="20847-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="20847-120">Salutations et musique en attente dans la file d’attente</span><span class="sxs-lookup"><span data-stu-id="20847-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="20847-121">Indiquez si vous souhaitez lire un message d’accueil pour les appelants lorsqu’ils arrivent dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="20847-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="20847-122">Vous devez charger un fichier MP3, WAV ou WMA contenant le message d’accueil à lire.</span><span class="sxs-lookup"><span data-stu-id="20847-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="20847-123">Teams fournit de la musique par défaut aux appelants lorsqu’ils sont en attente dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="20847-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="20847-124">Si vous souhaitez lire un fichier audio spécifique, sélectionnez Lire un fichier **audio** et téléchargez un fichier MP3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="20847-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="20847-125">L’enregistrement téléchargé ne peut pas avoir une taille supérieure à 5 Mo.</span><span class="sxs-lookup"><span data-stu-id="20847-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="20847-126">La musique par défaut fournie dans les files d’attente d’appels de Teams est gratuite pour toutes les redevances payables par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="20847-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="20847-127">Appeler des agents</span><span class="sxs-lookup"><span data-stu-id="20847-127">Call agents</span></span>

<span data-ttu-id="20847-128">Reportez-vous aux [conditions préalables pour](plan-auto-attendant-call-queue.md#prerequisites) pouvoir ajouter des agents à une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="20847-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![Capture d’écran des paramètres d’utilisateurs et de groupes pour les files d’attente d’appels](media/call-queue-users-groups.png)

<span data-ttu-id="20847-130">Vous pouvez ajouter jusqu’à 20 agents individuellement et jusqu’à 200 agents par groupes.</span><span class="sxs-lookup"><span data-stu-id="20847-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="20847-131">Pour ajouter un utilisateur à la file d’attente, cliquez sur Ajouter des utilisateurs, recherchez l’utilisateur, cliquez sur **Ajouter,** puis sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="20847-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="20847-132">Pour ajouter un groupe à la file d’attente, cliquez sur Ajouter des **groupes,** recherchez le groupe, cliquez sur **Ajouter,** puis sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="20847-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="20847-133">Vous pouvez utiliser des listes de distribution, des groupes de sécurité et des groupes Microsoft 365 ou des équipes Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="20847-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="20847-134">L’arrivée du premier appel peut prendre jusqu’à huit heures pour que les nouveaux utilisateurs ajoutés à un groupe arrivent.</span><span class="sxs-lookup"><span data-stu-id="20847-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="20847-135">Routage des appels</span><span class="sxs-lookup"><span data-stu-id="20847-135">Call routing</span></span>

![Capture d’écran des paramètres du mode de conférence et de la méthode de routage](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="20847-137">**Le mode conférence** réduit considérablement le temps qu’il faut pour qu’un appelant se connecte à un agent une fois qu’il accepte l’appel.</span><span class="sxs-lookup"><span data-stu-id="20847-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="20847-138">Pour que le mode conférence fonctionne, les agents dans la file d’attente d’appels doivent utiliser l’un des clients suivants :</span><span class="sxs-lookup"><span data-stu-id="20847-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="20847-139">Dernière version du client de bureau Microsoft Teams, de l’application Android ou de l’application iOS</span><span class="sxs-lookup"><span data-stu-id="20847-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="20847-140">Microsoft Teams Phone version 1449/1.0.94.2020051601 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="20847-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="20847-141">Les comptes Teams des agents doivent être réglés en mode Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="20847-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="20847-142">Les agents qui ne répondent pas aux exigences ne figurent pas dans la liste de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="20847-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="20847-143">Nous vous recommandons d’activer le mode conférence pour vos files d’attente d’appels si vos agents utilisent tous des clients compatibles.</span><span class="sxs-lookup"><span data-stu-id="20847-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

<span data-ttu-id="20847-144">**La méthode de routage** détermine l’ordre dans lequel les agents reçoivent les appels de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="20847-144">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="20847-145">Choisissez l’une des options ci-après :</span><span class="sxs-lookup"><span data-stu-id="20847-145">Choose from these options:</span></span>

- <span data-ttu-id="20847-146">**Le routage d’Attendant** sonne tous les agents dans la file d’attente en même temps.</span><span class="sxs-lookup"><span data-stu-id="20847-146">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="20847-147">Le premier appelant à prendre l’appel reçoit l’appel.</span><span class="sxs-lookup"><span data-stu-id="20847-147">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="20847-148">**Le routage en série** sonne tous les télét calleurs un par un dans l’ordre spécifié dans la liste **Des télé appelants.**</span><span class="sxs-lookup"><span data-stu-id="20847-148">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="20847-149">Si un agent le fait sans appel ou ne décroche pas, l’appel sonnera sur l’agent suivant et essaiera tous les agents jusqu’à ce qu’il soit choisi ou mis hors appel.</span><span class="sxs-lookup"><span data-stu-id="20847-149">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="20847-150">**L’arrondi balance** le routage des appels entrants de sorte que chaque agent d’appel reçoie le même nombre d’appels depuis la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="20847-150">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="20847-151">Cela pourrait être souhaitable dans un environnement de vente entrante afin d’assurer la même opportunité entre tous les agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="20847-151">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="20847-152">**Les itinéraires inactifs** les plus longs à chaque appel à l’agent inactif la plus longue.</span><span class="sxs-lookup"><span data-stu-id="20847-152">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="20847-153">Un agent est considéré comme inactif si son état de présence est disponible ou s’il est absent depuis moins de 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="20847-153">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="20847-154">Les agents dont l’état de présence est Absent depuis plus de 10 minutes ne sont pas considérés comme inactifs et ne peuvent pas recevoir d’appels tant qu’ils ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="20847-154">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Capture d’écran des paramètres de routage, de désinspondage et d’heure d’alerte](media/call-queue-presence-agents-time.png)


<span data-ttu-id="20847-156">**Le routage** basé sur la présence utilise le statut de disponibilité des agents d’appel pour déterminer si un agent doit être inclus dans la liste de routage des appels pour la méthode de routage sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="20847-156">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="20847-157">Les agents d’appel  dont le statut de disponibilité est Disponible sont inclus dans la liste de routage des appels et peuvent recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="20847-157">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="20847-158">Les agents dont le statut de disponibilité est définie sur tout autre statut sont exclus de la liste de routage des appels et ne reçoivent pas d’appels jusqu’à ce que leur statut de disponibilité soit de nouveau **disponible.**</span><span class="sxs-lookup"><span data-stu-id="20847-158">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="20847-159">Vous pouvez activer le routage des appels en fonction de la présence avec n’importe quelle méthode de routage.</span><span class="sxs-lookup"><span data-stu-id="20847-159">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="20847-160">Si un agent choisit de ne plus recevoir d’appels, il ne sera pas inclus dans la liste de routage des appels, quel que soit son statut de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="20847-160">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="20847-161">Les agents qui utilisent le client Skype Entreprise ne figurent pas dans la liste de routage des appels lorsque le routage en fonction de la présence est activé.</span><span class="sxs-lookup"><span data-stu-id="20847-161">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="20847-162">Si des agents utilisent Skype Entreprise, n’activez pas le routage des appels en fonction de la présence.</span><span class="sxs-lookup"><span data-stu-id="20847-162">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="20847-163">**La durée d’alerte** de l’agent indique combien de temps le téléphone d’un agent sonnera avant que la file d’attente redirige l’appel vers le prochain agent.</span><span class="sxs-lookup"><span data-stu-id="20847-163">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="20847-164">Pour les files d’attente à volume élevé, nous vous recommandons de définir les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="20847-164">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="20847-165">**Mode conférence sur** **Automatique**</span><span class="sxs-lookup"><span data-stu-id="20847-165">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="20847-166">**Méthode de routage vers** **un routage Attendant**</span><span class="sxs-lookup"><span data-stu-id="20847-166">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="20847-167">**Routage en fonction de la présence** vers **Le**</span><span class="sxs-lookup"><span data-stu-id="20847-167">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="20847-168">**Heure d’alerte de l’agent :** **à 20 secondes**</span><span class="sxs-lookup"><span data-stu-id="20847-168">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="20847-169">Gestion des débordements d’appels</span><span class="sxs-lookup"><span data-stu-id="20847-169">Call overflow handling</span></span>

![Capture d’écran des paramètres de dépassement de capacité d’appel](media/call-queue-overflow-handling.png)

<span data-ttu-id="20847-171">**Le nombre maximal d’appels dans** la file d’attente indique le nombre maximal d’appels qui peuvent attendre dans la file d’attente à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="20847-171">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="20847-172">La valeur par défaut est 50, mais elle peut varier entre 0 et 200.</span><span class="sxs-lookup"><span data-stu-id="20847-172">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="20847-173">Lorsque cette limite est atteinte, l’appel est traité comme spécifié par le paramètre Lorsque la limite maximale du nombre d’appels **est** atteinte.</span><span class="sxs-lookup"><span data-stu-id="20847-173">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="20847-174">Vous pouvez choisir de déconnecter l’appel ou de le rediriger vers une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="20847-174">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="20847-175">Par exemple, l’appelant peut laisser un message vocal pour les agents dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="20847-175">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="20847-176">Pour les transferts externes, reportez-vous aux conditions [préalables](plan-auto-attendant-call-queue.md#prerequisites) et aux transferts de numéros de téléphone [externes - détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour la mise en forme des numéros.</span><span class="sxs-lookup"><span data-stu-id="20847-176">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="20847-177">Si la valeur maximale du nombre d’appels est définie sur 0, le message d’accueil n’est pas l donné.</span><span class="sxs-lookup"><span data-stu-id="20847-177">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="20847-178">Traitement des délais d’appel</span><span class="sxs-lookup"><span data-stu-id="20847-178">Call timeout handling</span></span>

![Capture d’écran des paramètres de délai d’appel](media/call-queue-timeout-handling.png)

<span data-ttu-id="20847-180">**Délai d’attente d’appel** : le temps d’attente maximal spécifie la durée maximale pendant quelle la file d’attente d’un appel peut être mis en attente avant d’être redirigé ou déconnecté.</span><span class="sxs-lookup"><span data-stu-id="20847-180">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="20847-181">Vous pouvez spécifier une valeur de 0 seconde à 45 minutes.</span><span class="sxs-lookup"><span data-stu-id="20847-181">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="20847-182">Vous pouvez choisir de déconnecter l’appel ou de le rediriger vers l’une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="20847-182">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="20847-183">Par exemple, l’appelant peut laisser un message vocal pour les agents dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="20847-183">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="20847-184">Pour les transferts externes, reportez-vous aux conditions [préalables](plan-auto-attendant-call-queue.md#prerequisites) et aux transferts de numéros de téléphone [externes - détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour la mise en forme des numéros.</span><span class="sxs-lookup"><span data-stu-id="20847-184">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="20847-185">Une fois vos options de délai d’appel sélectionnées, cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="20847-185">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="20847-186">ID de l’appelant pour les appels sortants</span><span class="sxs-lookup"><span data-stu-id="20847-186">Caller ID for outbound calls</span></span>

<span data-ttu-id="20847-187">Étant donné que des agents dans une file d’attente d’appels peuvent appeler pour renvoyer un appel client, envisagez de définir l’ID d’appelant pour les membres d’une file d’attente d’appels sur le numéro de service d’un fournisseur de service automatique approprié.</span><span class="sxs-lookup"><span data-stu-id="20847-187">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="20847-188">Pour plus d’informations, voir Gérer les [stratégies d’ID](caller-id-policies.md) d’appelant dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="20847-188">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="20847-189">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="20847-189">Supported clients</span></span>

<span data-ttu-id="20847-190">Les clients suivants sont pris en charge pour les agents d’appel dans une file d’attente d’appels :</span><span class="sxs-lookup"><span data-stu-id="20847-190">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="20847-191">Client de bureau Skype Entreprise 2016 (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="20847-191">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="20847-192">Client de bureau Lync 2013 (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="20847-192">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="20847-193">Tous les modèles de téléphone IP pris en charge par Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="20847-193">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="20847-194">Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="20847-194">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="20847-195">Mac Skype Entreprise Client (version 16.8.196 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="20847-195">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="20847-196">Client Skype Entreprise Pour Android (version 6.16.0.9 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="20847-196">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="20847-197">iPhone client Skype Entreprise (version 6.16.0 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="20847-197">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="20847-198">Client Skype Entreprise pour iPad (version 6.16.0 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="20847-198">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="20847-199">Client Windows Microsoft Teams (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="20847-199">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="20847-200">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="20847-200">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="20847-201">Application Microsoft Teams pour iPhone</span><span class="sxs-lookup"><span data-stu-id="20847-201">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="20847-202">Application Microsoft Teams pour Android</span><span class="sxs-lookup"><span data-stu-id="20847-202">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="20847-203">Les files d’attente à qui un numéro de routage direct est affecté ne peuvent pas être prise en charge par les clients Skype Entreprise, les clients Lync ou les téléphones IP Skype Entreprise en tant qu’agents.</span><span class="sxs-lookup"><span data-stu-id="20847-203">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="20847-204">Cmdlets de file d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="20847-204">Call queue cmdlets</span></span>

<span data-ttu-id="20847-205">Vous pouvez également utiliser des Windows PowerShell pour créer et configurer des files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="20847-205">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="20847-206">Voici les cmdlets que vous utilisez pour gérer une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="20847-206">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="20847-207">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="20847-207">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="20847-208">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="20847-208">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="20847-209">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="20847-209">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="20847-210">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="20847-210">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="20847-211">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="20847-211">Related topics</span></span>

[<span data-ttu-id="20847-212">Voici les avantages du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="20847-212">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="20847-213">Obtention de numéros de téléphone de service</span><span class="sxs-lookup"><span data-stu-id="20847-213">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="20847-214">Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="20847-214">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="20847-215">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="20847-215">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="20847-216">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="20847-216">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
