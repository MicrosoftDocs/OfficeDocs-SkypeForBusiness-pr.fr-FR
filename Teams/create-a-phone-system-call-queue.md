---
title: Créer une file d’attente d’appels dans Microsoft teams
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
description: Apprenez à configurer votre système téléphonique pour les files d’attente d’appels à l’aide de Microsoft Teams, qui fournit un message de bienvenue, de la musique, des appels et d’autres fonctionnalités.
ms.openlocfilehash: fb4510ce81b09569a8228916b7d05cc6697caac8
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49089323"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="f59ae-103">Créer une file d’attente d’appel</span><span class="sxs-lookup"><span data-stu-id="f59ae-103">Create a call queue</span></span>

<span data-ttu-id="f59ae-104">Les files d’attente d’appels constituent une méthode de routage des appelants vers des personnes de votre organisation qui peuvent vous aider avec un problème ou une question spécifique.</span><span class="sxs-lookup"><span data-stu-id="f59ae-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="f59ae-105">Les appels sont distribués un par un aux personnes de la file d’attente (qui sont appelés *agents*).</span><span class="sxs-lookup"><span data-stu-id="f59ae-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="f59ae-106">Les files d’attente d’appels fournissent :</span><span class="sxs-lookup"><span data-stu-id="f59ae-106">Call queues provide:</span></span>

- <span data-ttu-id="f59ae-107">Message d’accueil.</span><span class="sxs-lookup"><span data-stu-id="f59ae-107">A greeting message.</span></span>

- <span data-ttu-id="f59ae-108">De la musique pendant que les utilisateurs attendent dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f59ae-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="f59ae-109">Ordre d’acheminement des appels : pour les agents *, première et première sortie* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="f59ae-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="f59ae-110">Gestion des options de dépassement de capacité et de délai d’attente.</span><span class="sxs-lookup"><span data-stu-id="f59ae-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="f59ae-111">Vérifiez que vous disposez [d’un plan de lecture pour les standards automatiques d’équipe et les files d’attente d’appels](plan-auto-attendant-call-queue.md) , puis suivez les [étapes de mise](plan-auto-attendant-call-queue.md#getting-started) en route avant de suivre les procédures décrites dans cet article.</span><span class="sxs-lookup"><span data-stu-id="f59ae-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="f59ae-112">Pour configurer une file d’attente d’appels, dans le centre d’administration Teams, développez **voix**, cliquez sur **files d’attente d’appels**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f59ae-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="f59ae-113">Compte de ressources et langue</span><span class="sxs-lookup"><span data-stu-id="f59ae-113">Resource account and language</span></span>

![Capture d’écran du compte de ressources et des paramètres de langue](media/call-queue-name-language.png)

1. <span data-ttu-id="f59ae-115">Tapez un nom pour la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f59ae-115">Type a name for the call queue.</span></span> <span data-ttu-id="f59ae-116">Les agents verront ce nom lorsqu’ils recevront un appel entrant de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f59ae-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="f59ae-117">Cliquez sur **Ajouter** un compte, recherchez le compte de ressource que vous voulez utiliser avec cette file d’attente d’appels, cliquez sur **Ajouter**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f59ae-117">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="f59ae-118">Choisissez une langue.</span><span class="sxs-lookup"><span data-stu-id="f59ae-118">Choose a language.</span></span> <span data-ttu-id="f59ae-119">Ce langage sera utilisé pour les invites vocales générées par le système et la transcription de la boîte vocale (si vous les activez).</span><span class="sxs-lookup"><span data-stu-id="f59ae-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="f59ae-120">Salutation et musique en attente dans la file d’attente</span><span class="sxs-lookup"><span data-stu-id="f59ae-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="f59ae-121">Spécifiez si vous souhaitez lire un message d’accueil pour les appelants lorsqu’ils arrivent dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f59ae-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="f59ae-122">Vous devez charger un fichier MP3, WAV ou WMA contenant le message d’accueil que vous voulez lire.</span><span class="sxs-lookup"><span data-stu-id="f59ae-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="f59ae-123">Teams fournit une musique par défaut aux appelants alors qu’ils sont suspendus dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f59ae-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="f59ae-124">Si vous voulez lire un fichier audio spécifique, sélectionnez **lire un fichier audio** et télécharger un fichier mp3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="f59ae-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="f59ae-125">L’enregistrement téléchargé ne peut pas dépasser 5 Mo.</span><span class="sxs-lookup"><span data-stu-id="f59ae-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="f59ae-126">La musique par défaut fournie dans les files d’attente des appels d’équipes n’est disponible que pour les royalties imputables à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f59ae-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="f59ae-127">Agent d’appel</span><span class="sxs-lookup"><span data-stu-id="f59ae-127">Call agents</span></span>

<span data-ttu-id="f59ae-128">Pour pouvoir ajouter des agents à une file d’attente d’appels, reportez-vous aux [conditions préalables](plan-auto-attendant-call-queue.md#prerequisites) .</span><span class="sxs-lookup"><span data-stu-id="f59ae-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![Capture d’écran des paramètres des utilisateurs et des groupes pour les files d’attente d’appels](media/call-queue-users-groups.png)

<span data-ttu-id="f59ae-130">Vous pouvez ajouter jusqu’à 20 agents de manière individuelle et jusqu’à 200 agents via des groupes.</span><span class="sxs-lookup"><span data-stu-id="f59ae-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="f59ae-131">Pour ajouter un utilisateur à la file d’attente, cliquez sur **Ajouter des utilisateurs**, recherchez l’utilisateur, cliquez sur **Ajouter**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f59ae-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="f59ae-132">Pour ajouter un groupe à la file d’attente, cliquez sur **Ajouter des groupes**, recherchez le groupe, cliquez sur **Ajouter**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f59ae-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="f59ae-133">Vous pouvez utiliser des listes de distribution, des groupes de sécurité et des groupes Microsoft 365 ou des équipes Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f59ae-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="f59ae-134">Les nouveaux utilisateurs ajoutés à un groupe peuvent parfois prendre jusqu’à huit heures de réception.</span><span class="sxs-lookup"><span data-stu-id="f59ae-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="f59ae-135">Routage des appels</span><span class="sxs-lookup"><span data-stu-id="f59ae-135">Call routing</span></span>

![Capture d’écran du mode de conférence et des paramètres de méthode de routage](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="f59ae-137">Le **mode conférence** réduit considérablement la durée nécessaire à la connexion d’un appelant à un agent, une fois que l’agent a accepté l’appel.</span><span class="sxs-lookup"><span data-stu-id="f59ae-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="f59ae-138">Pour que le mode conférence fonctionne, les agents de la file d’attente d’appels doivent utiliser un des clients suivants :</span><span class="sxs-lookup"><span data-stu-id="f59ae-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="f59ae-139">Dernière version du client de bureau Microsoft Teams, de l’application Android ou de l’application iOS</span><span class="sxs-lookup"><span data-stu-id="f59ae-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="f59ae-140">Microsoft teams Phone version 1449/1.0.94.2020051601 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="f59ae-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="f59ae-141">Les comptes d’équipes des agents doivent être définis sur le mode équipes uniquement.</span><span class="sxs-lookup"><span data-stu-id="f59ae-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="f59ae-142">Les agents qui ne satisfont pas les exigences requises ne sont pas inclus dans la liste routage des appels.</span><span class="sxs-lookup"><span data-stu-id="f59ae-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="f59ae-143">Nous vous recommandons d’activer le mode Conférence pour vos files d’attente si vos agents utilisent tous des clients compatibles.</span><span class="sxs-lookup"><span data-stu-id="f59ae-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="f59ae-144">Occupé sur occupé n’est pas pris en charge par le mode conférence.</span><span class="sxs-lookup"><span data-stu-id="f59ae-144">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="f59ae-145">Les agents sur les appels hors file d’attente risquent de se présenter avec un appel de file d’attente d’appels si le routage basé sur la présence n’est pas activé.</span><span class="sxs-lookup"><span data-stu-id="f59ae-145">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="f59ae-146">La **méthode de routage** détermine l’ordre dans lequel les agents reçoivent des appels à partir de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f59ae-146">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="f59ae-147">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f59ae-147">Choose from these options:</span></span>

- <span data-ttu-id="f59ae-148">Le **routage en standard** sonne tous les agents de la file d’attente en même temps.</span><span class="sxs-lookup"><span data-stu-id="f59ae-148">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="f59ae-149">Le premier agent d’appel pour décrocher l’appel obtient l’appel.</span><span class="sxs-lookup"><span data-stu-id="f59ae-149">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="f59ae-150">Le **routage série** sonne tous les agents d’appel un par un dans l’ordre indiqué dans la liste des **agents d’appel** .</span><span class="sxs-lookup"><span data-stu-id="f59ae-150">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="f59ae-151">Si un agent est rejeté ou ne décroche aucun appel, l’appel sonnera sur l’agent suivant et tentera d’essayer tous les agents jusqu’à ce qu’il soit décroché.</span><span class="sxs-lookup"><span data-stu-id="f59ae-151">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="f59ae-152">La **répétition** alternée équilibre le routage des appels entrants de telle sorte que chaque agent d’appel obtient le même nombre d’appels à partir de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f59ae-152">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="f59ae-153">Cela pourrait être souhaitable dans un environnement de ventes entrantes pour garantir l’égalité des chances entre tous les agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="f59ae-153">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="f59ae-154">Temps **inactif** le plus long pour chaque appel de l’agent qui est resté inactif le plus longtemps.</span><span class="sxs-lookup"><span data-stu-id="f59ae-154">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="f59ae-155">Un agent est considéré comme inactif si son état de présence est disponible ou s’il est absent depuis moins de 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="f59ae-155">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="f59ae-156">Les agents dont l’état de présence est absent pendant plus de 10 minutes ne sont pas considérés comme inactifs et ne peuvent pas recevoir d’appels tant qu’ils n’ont pas changé leur présence en disponible.</span><span class="sxs-lookup"><span data-stu-id="f59ae-156">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Capture d’écran des paramètres de routage, de refus d’utilisation et d’alerte](media/call-queue-presence-agents-time.png)


<span data-ttu-id="f59ae-158">Le **routage basé sur la présence** utilise l’état de disponibilité des agents d’appel pour déterminer si un agent doit être inclus dans la liste de routage des appels pour la méthode de routage sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f59ae-158">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="f59ae-159">Les téléopérateurs pour lesquels l’état de disponibilité est défini sur **disponible** figurent dans la liste routage des appels et peuvent recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="f59ae-159">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="f59ae-160">Les agents dont l’état de disponibilité est défini sur tout autre statut sont exclus de la liste routage des appels et ne reçoivent aucun appel tant que leur état de disponibilité n’a pas été modifié en **disponible**.</span><span class="sxs-lookup"><span data-stu-id="f59ae-160">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="f59ae-161">Vous pouvez activer le routage des appels en fonction de la présence avec n’importe quelle méthode de routage.</span><span class="sxs-lookup"><span data-stu-id="f59ae-161">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="f59ae-162">Si un agent ne peut plus passer d’appel, il n’est pas inclus dans la liste routage des appels, quelle que soit la valeur de son statut de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f59ae-162">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="f59ae-163">Les agents qui utilisent le client Skype entreprise ne sont pas inclus dans la liste des itinéraires d’appel lorsque le routage basé sur la présence est activé.</span><span class="sxs-lookup"><span data-stu-id="f59ae-163">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="f59ae-164">Si vous avez des agents qui utilisent Skype entreprise, n’activez pas le routage des appels basée sur la présence.</span><span class="sxs-lookup"><span data-stu-id="f59ae-164">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="f59ae-165">**Durée** de l’alerte d’agent spécifie la durée pendant laquelle le téléphone de l’agent sonnera avant que la file d’attente ne redirige l’appel vers l’agent suivant.</span><span class="sxs-lookup"><span data-stu-id="f59ae-165">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="f59ae-166">Pour les files d’attente de volume élevé, nous vous recommandons d’utiliser les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f59ae-166">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="f59ae-167">**Mode** de conférence **automatique**</span><span class="sxs-lookup"><span data-stu-id="f59ae-167">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="f59ae-168">**Méthode de routage** pour le **routage en standard**</span><span class="sxs-lookup"><span data-stu-id="f59ae-168">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="f59ae-169">**Routage basé** sur la présence sur **activé**</span><span class="sxs-lookup"><span data-stu-id="f59ae-169">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="f59ae-170">**Durée de l’alerte agent :** **20 secondes**</span><span class="sxs-lookup"><span data-stu-id="f59ae-170">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="f59ae-171">Gestion du dépassement des appels</span><span class="sxs-lookup"><span data-stu-id="f59ae-171">Call overflow handling</span></span>

![Capture d’écran des paramètres de dépassement d’appel](media/call-queue-overflow-handling.png)

<span data-ttu-id="f59ae-173">Le nombre **maximal d’appels dans la file d’attente** spécifie le nombre maximal d’appels qui peuvent patienter dans la file d’attente à tout moment.</span><span class="sxs-lookup"><span data-stu-id="f59ae-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="f59ae-174">La valeur par défaut est 50, mais elle peut varier entre 0 et 200.</span><span class="sxs-lookup"><span data-stu-id="f59ae-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="f59ae-175">Lorsque cette limite est atteinte, l’appel est géré conformément au paramètre **lorsque le nombre maximal d’appels est atteint** .</span><span class="sxs-lookup"><span data-stu-id="f59ae-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="f59ae-176">Vous pouvez choisir de déconnecter l’appel ou de le rediriger vers une destination de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="f59ae-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="f59ae-177">Par exemple, vous pouvez demander à l’appelant de laisser une boîte vocale pour les agents dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f59ae-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="f59ae-178">Pour les transferts externes, reportez-vous aux [conditions préalables](plan-auto-attendant-call-queue.md#prerequisites) et aux [numéros de téléphone externes-détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour la mise en forme des nombres.</span><span class="sxs-lookup"><span data-stu-id="f59ae-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="f59ae-179">Si le nombre maximum d’appels est défini sur 0, le message d’accueil n’est pas lu.</span><span class="sxs-lookup"><span data-stu-id="f59ae-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="f59ae-180">Gestion des délais d’appel</span><span class="sxs-lookup"><span data-stu-id="f59ae-180">Call timeout handling</span></span>

![Capture d’écran des paramètres de délai d’appel](media/call-queue-timeout-handling.png)

<span data-ttu-id="f59ae-182">**Délai d’appel : délai d’attente maximum** spécifie la durée maximale pendant laquelle un appel peut être mis en attente dans la file d’attente avant qu’elle ne soit redirigée ou déconnectée.</span><span class="sxs-lookup"><span data-stu-id="f59ae-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="f59ae-183">Vous pouvez spécifier une valeur comprise entre 0 et 45 minutes.</span><span class="sxs-lookup"><span data-stu-id="f59ae-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="f59ae-184">Vous pouvez choisir de déconnecter l’appel ou de le rediriger vers l’une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="f59ae-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="f59ae-185">Par exemple, vous pouvez demander à l’appelant de laisser une boîte vocale pour les agents dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f59ae-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="f59ae-186">Pour les transferts externes, reportez-vous aux [conditions préalables](plan-auto-attendant-call-queue.md#prerequisites) et aux [numéros de téléphone externes-détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour la mise en forme des nombres.</span><span class="sxs-lookup"><span data-stu-id="f59ae-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="f59ae-187">Lorsque vous avez sélectionné les options de temporisation de l’appel, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f59ae-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="f59ae-188">ID de l’appelant pour les appels sortants</span><span class="sxs-lookup"><span data-stu-id="f59ae-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="f59ae-189">Dans la mesure où les agents d’une file d’attente d’appels risquent de composer un appel client, envisagez de définir l’identification de l’appelant pour les membres d’une file d’attente pour le numéro de service d’un standard automatique approprié.</span><span class="sxs-lookup"><span data-stu-id="f59ae-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="f59ae-190">Pour plus d’informations, voir [gérer les stratégies d’identification d’appelant dans Microsoft teams](caller-id-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="f59ae-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="f59ae-191">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="f59ae-191">Supported clients</span></span>

- <span data-ttu-id="f59ae-192">Les clients suivants sont pris en charge pour les téléopérateurs dans une file d’attente des appels :</span><span class="sxs-lookup"><span data-stu-id="f59ae-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="f59ae-193">Client de bureau Skype entreprise 2016 (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="f59ae-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="f59ae-194">Client de bureau Lync 2013 (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="f59ae-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="f59ae-195">Tous les modèles de téléphone IP pris en charge par Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f59ae-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="f59ae-196">Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="f59ae-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="f59ae-197">Client Skype entreprise pour Mac (version 16.8.196 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="f59ae-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="f59ae-198">Client Skype entreprise Android (version 6.16.0.9 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="f59ae-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="f59ae-199">Client Skype entreprise pour iPhone (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="f59ae-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="f59ae-200">Client Skype entreprise pour iPad (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="f59ae-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="f59ae-201">Client Microsoft Teams (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="f59ae-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="f59ae-202">Client Microsoft teams Mac</span><span class="sxs-lookup"><span data-stu-id="f59ae-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="f59ae-203">Application Microsoft teams pour iPhone</span><span class="sxs-lookup"><span data-stu-id="f59ae-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="f59ae-204">Application Android Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="f59ae-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="f59ae-205">Les files d’attente d’appels disposant d’un numéro de routage direct ne prennent pas en charge les clients Skype entreprise, les clients Lync ou les téléphones IP Skype entreprise en tant qu’agents.</span><span class="sxs-lookup"><span data-stu-id="f59ae-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="f59ae-206">Cmdlets de files d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="f59ae-206">Call queue cmdlets</span></span>

<span data-ttu-id="f59ae-207">Vous pouvez également utiliser Windows PowerShell pour créer et configurer des files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f59ae-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="f59ae-208">Voici les applets de passe que vous utilisez pour gérer une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f59ae-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="f59ae-209">Nouveau-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f59ae-209">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="f59ae-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f59ae-210">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="f59ae-211">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f59ae-211">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="f59ae-212">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f59ae-212">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="f59ae-213">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f59ae-213">Related topics</span></span>

[<span data-ttu-id="f59ae-214">Voici les avantages du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="f59ae-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="f59ae-215">Obtention de numéros de téléphone de service</span><span class="sxs-lookup"><span data-stu-id="f59ae-215">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="f59ae-216">Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="f59ae-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="f59ae-217">Nouveau-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="f59ae-217">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="f59ae-218">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f59ae-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
