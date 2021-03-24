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
ms.openlocfilehash: 9bb33e5590df1af6b70dffecba64eb313838b228
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092712"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="f0cf0-103">Créer une file d’attente d’appel</span><span class="sxs-lookup"><span data-stu-id="f0cf0-103">Create a call queue</span></span>

<span data-ttu-id="f0cf0-104">Les files d’attente permettent de router les appelants vers des personnes de votre organisation qui peuvent vous aider à répondre à un problème ou une question spécifique.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="f0cf0-105">Les appels sont distribués un par un aux personnes dans la file d’attente (appelées *agents).*</span><span class="sxs-lookup"><span data-stu-id="f0cf0-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="f0cf0-106">Les files d’attente fournissent les services :</span><span class="sxs-lookup"><span data-stu-id="f0cf0-106">Call queues provide:</span></span>

- <span data-ttu-id="f0cf0-107">Message de salutation.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-107">A greeting message.</span></span>

- <span data-ttu-id="f0cf0-108">Musique pendant que des personnes sont en attente dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="f0cf0-109">Routage des appels *(dans l’ordre* Premier dans, Premier sorti (FIFO) - vers des agents.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="f0cf0-110">Options de gestion pour le dépassement de capacité et le délai d’attente.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="f0cf0-111">Assurez-vous de lire l’article Plan pour les [](plan-auto-attendant-call-queue.md#getting-started) standard [automatiques Teams](plan-auto-attendant-call-queue.md) et les files d’attente d’appels, et suivez les étapes de mise en place avant de suivre les procédures de cet article.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="f0cf0-112">Pour configurer une file d’attente d’appels, dans le Centre d’administration Teams, développez **Voix,** cliquez sur Files d’attente d’appels, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="f0cf0-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="f0cf0-113">Compte et langue des ressources</span><span class="sxs-lookup"><span data-stu-id="f0cf0-113">Resource account and language</span></span>

![Capture d’écran des paramètres de compte de ressource et de langue](media/call-queue-name-language.png)

1. <span data-ttu-id="f0cf0-115">Tapez un nom pour la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-115">Type a name for the call queue.</span></span>

2. <span data-ttu-id="f0cf0-116">Cliquez **sur Ajouter des comptes,** recherchez le compte de ressource à utiliser avec cette file d’attente d’appels, cliquez sur Ajouter, puis sur **Ajouter.** </span><span class="sxs-lookup"><span data-stu-id="f0cf0-116">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="f0cf0-117">(Les agents voient le nom du compte de ressource lorsqu’ils reçoivent un appel entrant.)</span><span class="sxs-lookup"><span data-stu-id="f0cf0-117">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="f0cf0-118">Choisissez une [langue prise en charge.](create-a-phone-system-call-queue-languages.md)</span><span class="sxs-lookup"><span data-stu-id="f0cf0-118">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="f0cf0-119">Cette langue sera utilisée pour les invites vocales générées par le système et la transcription des messages vocaux (si vous les activez).</span><span class="sxs-lookup"><span data-stu-id="f0cf0-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="f0cf0-120">Salutations et musique en attente dans la file d’attente</span><span class="sxs-lookup"><span data-stu-id="f0cf0-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="f0cf0-121">Indiquez si vous souhaitez lire un message d’accueil pour les appelants lorsqu’ils arrivent dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="f0cf0-122">Vous devez charger un fichier MP3, WAV ou WMA contenant le message d’accueil à lire.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="f0cf0-123">Teams fournit de la musique par défaut aux appelants lorsqu’ils sont en attente dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="f0cf0-124">Si vous souhaitez lire un fichier audio spécifique, sélectionnez Lire un fichier **audio** et téléchargez un fichier MP3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="f0cf0-125">L’enregistrement téléchargé ne peut pas avoir une taille supérieure à 5 Mo.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="f0cf0-126">La musique par défaut fournie dans les files d’attente d’appels de Teams est gratuite pour toutes les redevances payables par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="f0cf0-127">Appeler des agents</span><span class="sxs-lookup"><span data-stu-id="f0cf0-127">Call agents</span></span>

<span data-ttu-id="f0cf0-128">Reportez-vous aux [conditions préalables pour](plan-auto-attendant-call-queue.md#prerequisites) pouvoir ajouter des agents à une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![Capture d’écran des paramètres d’utilisateurs et de groupes pour les files d’attente d’appels](media/call-queue-users-groups.png)

<span data-ttu-id="f0cf0-130">Vous pouvez ajouter jusqu’à 20 agents individuellement et jusqu’à 200 agents par groupes.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="f0cf0-131">Pour ajouter un utilisateur à la file d’attente, cliquez sur Ajouter des utilisateurs, recherchez l’utilisateur, cliquez sur **Ajouter,** puis sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="f0cf0-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="f0cf0-132">Pour ajouter un groupe à la file d’attente, cliquez sur Ajouter des **groupes,** recherchez le groupe, cliquez sur **Ajouter,** puis sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="f0cf0-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="f0cf0-133">Vous pouvez utiliser des listes de distribution, des groupes de sécurité et des groupes Microsoft 365 ou des équipes Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="f0cf0-134">L’arrivée du premier appel peut prendre jusqu’à huit heures pour que les nouveaux utilisateurs ajoutés à un groupe arrivent.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="f0cf0-135">Routage des appels</span><span class="sxs-lookup"><span data-stu-id="f0cf0-135">Call routing</span></span>

![Capture d’écran des paramètres du mode de conférence et de la méthode de routage](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="f0cf0-137">**Le mode conférence** réduit considérablement le temps qu’il faut pour qu’un appelant se connecte à un agent une fois qu’il accepte l’appel.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="f0cf0-138">Pour que le mode conférence fonctionne, les agents dans la file d’attente d’appels doivent utiliser l’un des clients suivants :</span><span class="sxs-lookup"><span data-stu-id="f0cf0-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="f0cf0-139">Dernière version du client de bureau Microsoft Teams, de l’application Android ou de l’application iOS</span><span class="sxs-lookup"><span data-stu-id="f0cf0-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="f0cf0-140">Microsoft Teams phone version 1449/1.0.94.2020051601 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="f0cf0-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="f0cf0-141">Les comptes Teams des agents doivent être réglés en mode Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="f0cf0-142">Les agents qui ne répondent pas aux exigences ne figurent pas dans la liste de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="f0cf0-143">Nous vous recommandons d’activer le mode conférence pour vos files d’attente d’appels si vos agents utilisent tous des clients compatibles.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

<span data-ttu-id="f0cf0-144">**La méthode de routage** détermine l’ordre dans lequel les agents reçoivent les appels de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-144">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="f0cf0-145">Choisissez l’une des options ci-après :</span><span class="sxs-lookup"><span data-stu-id="f0cf0-145">Choose from these options:</span></span>

- <span data-ttu-id="f0cf0-146">**Le routage d’Attendant** sonne tous les agents dans la file d’attente en même temps.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-146">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="f0cf0-147">Le premier appelant à prendre l’appel reçoit l’appel.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-147">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="f0cf0-148">**Le routage en série** sonne tous les télét calleurs un par un dans l’ordre spécifié dans la liste **Des télé appelants.**</span><span class="sxs-lookup"><span data-stu-id="f0cf0-148">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="f0cf0-149">Si un agent le fait sans appel ou ne décroche pas, l’appel sonnera sur l’agent suivant et essaiera tous les agents jusqu’à ce qu’il soit choisi ou mis hors appel.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-149">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="f0cf0-150">**L’arrondi balance** le routage des appels entrants de sorte que chaque agent d’appel reçoie le même nombre d’appels depuis la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-150">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="f0cf0-151">Cela pourrait être souhaitable dans un environnement de vente entrante afin d’assurer la même opportunité entre tous les agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-151">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="f0cf0-152">**Les itinéraires inactifs** les plus longs à chaque appel à l’agent inactif la plus longue.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-152">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="f0cf0-153">Un agent est considéré comme inactif si son état de présence est disponible ou s’il est absent depuis moins de 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-153">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="f0cf0-154">Les agents dont l’état de présence est Absent depuis plus de 10 minutes ne sont pas considérés comme inactifs et ne peuvent pas recevoir d’appels tant qu’ils ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-154">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Capture d’écran des paramètres de routage, de désinspondage et d’heure d’alerte](media/call-queue-presence-agents-time.png)


<span data-ttu-id="f0cf0-156">**Le routage** basé sur la présence utilise le statut de disponibilité des agents d’appel pour déterminer si un agent doit être inclus dans la liste de routage des appels pour la méthode de routage sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-156">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="f0cf0-157">Les agents d’appel  dont le statut de disponibilité est Disponible sont inclus dans la liste de routage des appels et peuvent recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-157">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="f0cf0-158">Les agents dont le statut de disponibilité est définie sur tout autre statut sont exclus de la liste de routage des appels et ne reçoivent pas d’appels jusqu’à ce que leur statut de disponibilité soit de nouveau **disponible.**</span><span class="sxs-lookup"><span data-stu-id="f0cf0-158">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="f0cf0-159">Vous pouvez activer le routage des appels en fonction de la présence avec n’importe quelle méthode de routage.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-159">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="f0cf0-160">Si un agent choisit de ne plus recevoir d’appels, il ne sera pas inclus dans la liste de routage des appels, quel que soit son statut de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-160">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="f0cf0-161">Les agents qui utilisent le client Skype Entreprise ne figurent pas dans la liste de routage des appels lorsque le routage en fonction de la présence est activé.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-161">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="f0cf0-162">Si des agents utilisent Skype Entreprise, n’activez pas le routage des appels en fonction de la présence.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-162">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="f0cf0-163">**La durée d’alerte** de l’agent indique combien de temps le téléphone d’un agent sonnera avant que la file d’attente redirige l’appel vers le prochain agent.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-163">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="f0cf0-164">Les paramètres suivants sont recommandés :</span><span class="sxs-lookup"><span data-stu-id="f0cf0-164">The following settings are recommended:</span></span>

- <span data-ttu-id="f0cf0-165">**Mode conférence sur** **Automatique**</span><span class="sxs-lookup"><span data-stu-id="f0cf0-165">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="f0cf0-166">**Méthode de routage vers** **le rond rond** ou le plus long **inactif**</span><span class="sxs-lookup"><span data-stu-id="f0cf0-166">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="f0cf0-167">**Routage en fonction de la présence** vers **Le**</span><span class="sxs-lookup"><span data-stu-id="f0cf0-167">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="f0cf0-168">**Heure d’alerte de l’agent :** **à 20 secondes**</span><span class="sxs-lookup"><span data-stu-id="f0cf0-168">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="f0cf0-169">Si le routage en fonction de la présence n’est pas activé et que la file d’attente compte plusieurs appels, le système les présente simultanément aux agents, quel que soit leur statut de présence.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-169">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="f0cf0-170">Cela entraîne plusieurs notifications d’appel pour les agents, particulièrement si certains agents ne répondent pas à l’appel initial qui leur est présenté.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-170">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="f0cf0-171">Gestion des débordements d’appels</span><span class="sxs-lookup"><span data-stu-id="f0cf0-171">Call overflow handling</span></span>

![Capture d’écran des paramètres de dépassement de capacité d’appel](media/call-queue-overflow-handling.png)

<span data-ttu-id="f0cf0-173">**Le nombre maximal d’appels dans** la file d’attente indique le nombre maximal d’appels qui peuvent attendre dans la file d’attente à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="f0cf0-174">La valeur par défaut est 50, mais elle peut varier entre 0 et 200.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="f0cf0-175">Lorsque cette limite est atteinte, l’appel est traité comme spécifié par le paramètre Lorsque la limite maximale du nombre d’appels **est** atteinte.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="f0cf0-176">Vous pouvez choisir de déconnecter l’appel ou de le rediriger vers une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="f0cf0-177">Par exemple, l’appelant peut laisser un message vocal pour les agents dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="f0cf0-178">Pour les transferts externes, reportez-vous aux conditions [préalables](plan-auto-attendant-call-queue.md#prerequisites) et aux transferts de numéros de téléphone [externes ( détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour la mise en forme des numéros).</span><span class="sxs-lookup"><span data-stu-id="f0cf0-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="f0cf0-179">Si la valeur maximale du nombre d’appels est définie sur 0, le message d’accueil n’est pas l donné.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="f0cf0-180">Traitement des délais d’appel</span><span class="sxs-lookup"><span data-stu-id="f0cf0-180">Call timeout handling</span></span>

![Capture d’écran des paramètres de délai d’appel](media/call-queue-timeout-handling.png)

<span data-ttu-id="f0cf0-182">**Délai d’attente d’appel** : le temps d’attente maximal spécifie la durée maximale pendant quelle la file d’attente d’un appel peut être mis en attente avant d’être redirigé ou déconnecté.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="f0cf0-183">Vous pouvez spécifier une valeur de 0 seconde à 45 minutes.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="f0cf0-184">Vous pouvez choisir de déconnecter l’appel ou de le rediriger vers l’une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="f0cf0-185">Par exemple, l’appelant peut laisser un message vocal pour les agents dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="f0cf0-186">Pour les transferts externes, reportez-vous aux conditions [préalables](plan-auto-attendant-call-queue.md#prerequisites) et aux transferts de numéros de téléphone [externes ( détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour la mise en forme des numéros).</span><span class="sxs-lookup"><span data-stu-id="f0cf0-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="f0cf0-187">Une fois vos options de délai d’appel sélectionnées, cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="f0cf0-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="f0cf0-188">ID de l’appelant pour les appels sortants</span><span class="sxs-lookup"><span data-stu-id="f0cf0-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="f0cf0-189">Étant donné que des agents dans une file d’attente d’appels peuvent appeler pour renvoyer un appel client, envisagez de définir l’ID d’appelant pour les membres d’une file d’attente d’appels sur le numéro de service d’un fournisseur de service automatique approprié.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="f0cf0-190">Pour plus d’informations, voir Gérer les [stratégies d’ID](caller-id-policies.md) d’appelant dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="f0cf0-191">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="f0cf0-191">Supported clients</span></span>

<span data-ttu-id="f0cf0-192">Les clients suivants sont pris en charge pour les agents d’appel dans une file d’attente d’appels :</span><span class="sxs-lookup"><span data-stu-id="f0cf0-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="f0cf0-193">Client de bureau Skype Entreprise 2016 (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="f0cf0-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="f0cf0-194">Client de bureau Lync 2013 (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="f0cf0-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="f0cf0-195">Tous les modèles de téléphone IP pris en charge par Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="f0cf0-196">Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="f0cf0-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="f0cf0-197">Mac Skype Entreprise Client (version 16.8.196 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="f0cf0-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="f0cf0-198">Client Skype Entreprise Pour Android (version 6.16.0.9 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="f0cf0-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="f0cf0-199">iPhone client Skype Entreprise (version 6.16.0 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="f0cf0-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="f0cf0-200">Client Skype Entreprise pour iPad (version 6.16.0 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="f0cf0-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="f0cf0-201">Client Windows Microsoft Teams (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="f0cf0-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="f0cf0-202">Client Microsoft Teams Pour Mac</span><span class="sxs-lookup"><span data-stu-id="f0cf0-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="f0cf0-203">Application Microsoft Teams pour iPhone</span><span class="sxs-lookup"><span data-stu-id="f0cf0-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="f0cf0-204">Application Microsoft Teams pour Android</span><span class="sxs-lookup"><span data-stu-id="f0cf0-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="f0cf0-205">Les files d’attente à qui un numéro de routage direct est attribué ne peuvent pas être prise en charge par les clients Skype Entreprise, les clients Lync ou les téléphones IP Skype Entreprise en tant qu’agents.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="f0cf0-206">Cmdlets de file d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="f0cf0-206">Call queue cmdlets</span></span>

<span data-ttu-id="f0cf0-207">Vous pouvez également utiliser des Windows PowerShell pour créer et configurer des files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="f0cf0-208">Voici les cmdlets que vous utilisez pour gérer une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f0cf0-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="f0cf0-209">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f0cf0-209">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="f0cf0-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f0cf0-210">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="f0cf0-211">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f0cf0-211">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="f0cf0-212">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f0cf0-212">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="f0cf0-213">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="f0cf0-213">Related topics</span></span>

[<span data-ttu-id="f0cf0-214">Voici les avantages du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="f0cf0-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="f0cf0-215">Obtention de numéros de téléphone de service</span><span class="sxs-lookup"><span data-stu-id="f0cf0-215">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="f0cf0-216">Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="f0cf0-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="f0cf0-217">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="f0cf0-217">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="f0cf0-218">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f0cf0-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)