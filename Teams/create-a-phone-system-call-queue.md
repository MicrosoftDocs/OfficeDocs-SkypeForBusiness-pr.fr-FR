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
ms.openlocfilehash: 9825c6ed1780efa78bfdbc86911e9b403be589f6
ms.sourcegitcommit: 273f231098799975dc4cf609a68c9944b8072ce1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2020
ms.locfileid: "48820033"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="f5492-103">Créer une file d’attente d’appel</span><span class="sxs-lookup"><span data-stu-id="f5492-103">Create a call queue</span></span>

<span data-ttu-id="f5492-104">Les files d’attente d’appels constituent une méthode de routage des appelants vers des personnes de votre organisation qui peuvent vous aider avec un problème ou une question spécifique.</span><span class="sxs-lookup"><span data-stu-id="f5492-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="f5492-105">Les appels sont distribués un par un aux personnes de la file d’attente (qui sont appelés *agents* ).</span><span class="sxs-lookup"><span data-stu-id="f5492-105">Calls are distributed one at a time to the people in the queue (who are known as *agents* ).</span></span> 

<span data-ttu-id="f5492-106">Les files d’attente d’appels fournissent :</span><span class="sxs-lookup"><span data-stu-id="f5492-106">Call queues provide:</span></span>

- <span data-ttu-id="f5492-107">Message d’accueil.</span><span class="sxs-lookup"><span data-stu-id="f5492-107">A greeting message.</span></span>

- <span data-ttu-id="f5492-108">De la musique pendant que les utilisateurs attendent dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f5492-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="f5492-109">Ordre d’acheminement des appels : pour les agents *, première et première sortie* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="f5492-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="f5492-110">Gestion des options de dépassement de capacité et de délai d’attente.</span><span class="sxs-lookup"><span data-stu-id="f5492-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="f5492-111">Vérifiez que vous disposez [d’un plan de lecture pour les standards automatiques d’équipe et les files d’attente d’appels](plan-auto-attendant-call-queue.md) , puis suivez les [étapes de mise](plan-auto-attendant-call-queue.md#getting-started) en route avant de suivre les procédures décrites dans cet article.</span><span class="sxs-lookup"><span data-stu-id="f5492-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="f5492-112">Pour configurer une file d’attente d’appels, dans le centre d’administration Teams, développez **voix** , cliquez sur **files d’attente d’appels** , puis cliquez sur **Ajouter** .</span><span class="sxs-lookup"><span data-stu-id="f5492-112">To set up a call queue, in the Teams admin center, expand **Voice** , click **Call queues** , and then click **Add** .</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="f5492-113">Compte de ressources et langue</span><span class="sxs-lookup"><span data-stu-id="f5492-113">Resource account and language</span></span>

![Capture d’écran du compte de ressources et des paramètres de langue](media/call-queue-name-language.png)

1. <span data-ttu-id="f5492-115">Tapez un nom pour la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f5492-115">Type a name for the call queue.</span></span> <span data-ttu-id="f5492-116">Les agents verront ce nom lorsqu’ils recevront un appel entrant de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f5492-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="f5492-117">Cliquez sur **Ajouter** un compte, recherchez le compte de ressource que vous voulez utiliser avec cette file d’attente d’appels, cliquez sur **Ajouter** , puis sur **Ajouter** .</span><span class="sxs-lookup"><span data-stu-id="f5492-117">Click **Add accounts** , search for the resource account that you want to use with this call queue, click **Add** , and then click **Add** .</span></span>

3. <span data-ttu-id="f5492-118">Choisissez une langue.</span><span class="sxs-lookup"><span data-stu-id="f5492-118">Choose a language.</span></span> <span data-ttu-id="f5492-119">Ce langage sera utilisé pour les invites vocales générées par le système et la transcription de la boîte vocale (si vous les activez).</span><span class="sxs-lookup"><span data-stu-id="f5492-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-hold-music"></a><span data-ttu-id="f5492-120">Faire des vœux et garder de la musique</span><span class="sxs-lookup"><span data-stu-id="f5492-120">Greetings and hold music</span></span>

<span data-ttu-id="f5492-121">Spécifiez si vous souhaitez lire un message d’accueil pour les appelants lorsqu’ils arrivent dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f5492-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="f5492-122">Vous devez charger un fichier MP3, WAV ou WMA contenant le message d’accueil que vous voulez lire.</span><span class="sxs-lookup"><span data-stu-id="f5492-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="f5492-123">Teams fournit une musique par défaut aux appelants alors qu’ils sont suspendus dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f5492-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="f5492-124">Si vous voulez lire un fichier audio spécifique, sélectionnez **lire un fichier audio** et télécharger un fichier mp3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="f5492-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="f5492-125">L’enregistrement téléchargé ne peut pas dépasser 5 Mo.</span><span class="sxs-lookup"><span data-stu-id="f5492-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="f5492-126">La musique par défaut fournie dans les files d’attente des appels d’équipes n’est disponible que pour les royalties imputables à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f5492-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="f5492-127">Agent d’appel</span><span class="sxs-lookup"><span data-stu-id="f5492-127">Call agents</span></span>

<span data-ttu-id="f5492-128">Les agents d’appel sélectionnés doivent être l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f5492-128">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="f5492-129">Utilisateurs en ligne avec une licence de système téléphonique et la voix entreprise activée</span><span class="sxs-lookup"><span data-stu-id="f5492-129">Online users with a Phone System license and Enterprise Voice enabled</span></span>
- <span data-ttu-id="f5492-130">Utilisateurs en ligne avec un plan d’appels</span><span class="sxs-lookup"><span data-stu-id="f5492-130">Online users with a Calling Plan</span></span>
- <span data-ttu-id="f5492-131">Utilisateurs de Skype entreprise sur site</span><span class="sxs-lookup"><span data-stu-id="f5492-131">On-premises Skype for Business Server users</span></span>
- <span data-ttu-id="f5492-132">Si vos agents utilisent l’application Microsoft teams pour appeler des files d’attente, elles doivent être en mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="f5492-132">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

![Capture d’écran des paramètres des utilisateurs et des groupes pour les files d’attente d’appels](media/call-queue-users-groups.png)

<span data-ttu-id="f5492-134">Vous pouvez ajouter jusqu’à 20 agents de manière individuelle et jusqu’à 200 agents via des groupes.</span><span class="sxs-lookup"><span data-stu-id="f5492-134">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="f5492-135">Pour ajouter un utilisateur à la file d’attente, cliquez sur **Ajouter des utilisateurs** , recherchez l’utilisateur, cliquez sur **Ajouter** , puis sur **Ajouter** .</span><span class="sxs-lookup"><span data-stu-id="f5492-135">To add a user to the queue, click **Add users** , search for the user, click **Add** , and then click **Add** .</span></span>

<span data-ttu-id="f5492-136">Pour ajouter un groupe à la file d’attente, cliquez sur **Ajouter des groupes** , recherchez le groupe, cliquez sur **Ajouter** , puis cliquez sur **Ajouter** .</span><span class="sxs-lookup"><span data-stu-id="f5492-136">To add a group to the queue, click **Add groups** , search for the group, click **Add** , and then click **Add** .</span></span> <span data-ttu-id="f5492-137">Vous pouvez utiliser des listes de distribution, des groupes de sécurité et des groupes Microsoft 365 ou des équipes Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f5492-137">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="f5492-138">Les nouveaux utilisateurs ajoutés à un groupe peuvent parfois prendre jusqu’à huit heures de réception.</span><span class="sxs-lookup"><span data-stu-id="f5492-138">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="f5492-139">Routage des appels</span><span class="sxs-lookup"><span data-stu-id="f5492-139">Call routing</span></span>

![Capture d’écran du mode de conférence et des paramètres de méthode de routage](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="f5492-141">Le **mode conférence** réduit considérablement la durée nécessaire à la connexion d’un appelant à un agent, une fois que l’agent a accepté l’appel.</span><span class="sxs-lookup"><span data-stu-id="f5492-141">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="f5492-142">Pour que le mode conférence fonctionne, les agents de la file d’attente d’appels doivent utiliser un des clients suivants :</span><span class="sxs-lookup"><span data-stu-id="f5492-142">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="f5492-143">Dernière version du client de bureau Microsoft Teams, de l’application Android ou de l’application iOS</span><span class="sxs-lookup"><span data-stu-id="f5492-143">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="f5492-144">Microsoft teams Phone version 1449/1.0.94.2020051601 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="f5492-144">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="f5492-145">Les comptes d’équipes des agents doivent être définis sur le mode équipes uniquement.</span><span class="sxs-lookup"><span data-stu-id="f5492-145">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="f5492-146">Les agents qui ne satisfont pas les exigences requises ne sont pas inclus dans la liste routage des appels.</span><span class="sxs-lookup"><span data-stu-id="f5492-146">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="f5492-147">Nous vous recommandons d’activer le mode Conférence pour vos files d’attente si vos agents utilisent tous des clients compatibles.</span><span class="sxs-lookup"><span data-stu-id="f5492-147">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="f5492-148">Occupé sur occupé n’est pas pris en charge par le mode conférence.</span><span class="sxs-lookup"><span data-stu-id="f5492-148">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="f5492-149">Les agents sur les appels hors file d’attente risquent de se présenter avec un appel de file d’attente d’appels si le routage basé sur la présence n’est pas activé.</span><span class="sxs-lookup"><span data-stu-id="f5492-149">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="f5492-150">La **méthode de routage** détermine l’ordre dans lequel les agents reçoivent des appels à partir de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f5492-150">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="f5492-151">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f5492-151">Choose from these options:</span></span>

- <span data-ttu-id="f5492-152">Le **routage en standard** sonne tous les agents de la file d’attente en même temps.</span><span class="sxs-lookup"><span data-stu-id="f5492-152">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="f5492-153">Le premier agent d’appel pour décrocher l’appel obtient l’appel.</span><span class="sxs-lookup"><span data-stu-id="f5492-153">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="f5492-154">Le **routage série** sonne tous les agents d’appel un par un dans l’ordre indiqué dans la liste des **agents d’appel** .</span><span class="sxs-lookup"><span data-stu-id="f5492-154">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="f5492-155">Si un agent est rejeté ou ne décroche aucun appel, l’appel sonnera sur l’agent suivant et tentera d’essayer tous les agents jusqu’à ce qu’il soit décroché.</span><span class="sxs-lookup"><span data-stu-id="f5492-155">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="f5492-156">La **répétition** alternée équilibre le routage des appels entrants de telle sorte que chaque agent d’appel obtient le même nombre d’appels à partir de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f5492-156">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="f5492-157">Cela pourrait être souhaitable dans un environnement de ventes entrantes pour garantir l’égalité des chances entre tous les agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="f5492-157">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="f5492-158">Temps **inactif** le plus long pour chaque appel de l’agent qui est resté inactif le plus longtemps.</span><span class="sxs-lookup"><span data-stu-id="f5492-158">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="f5492-159">Un agent est considéré comme inactif si son état de présence est disponible ou s’il est absent depuis moins de 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="f5492-159">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="f5492-160">Les agents dont l’état de présence est absent pendant plus de 10 minutes ne sont pas considérés comme inactifs et ne peuvent pas recevoir d’appels tant qu’ils n’ont pas changé leur présence en disponible.</span><span class="sxs-lookup"><span data-stu-id="f5492-160">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![Capture d’écran des paramètres de routage, de refus d’utilisation et d’alerte](media/call-queue-presence-agents-time.png)


<span data-ttu-id="f5492-162">Le **routage basé sur la présence** utilise l’état de disponibilité des agents d’appel pour déterminer si un agent doit être inclus dans la liste de routage des appels pour la méthode de routage sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f5492-162">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="f5492-163">Les téléopérateurs pour lesquels l’état de disponibilité est défini sur **disponible** figurent dans la liste routage des appels et peuvent recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="f5492-163">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="f5492-164">Les agents dont l’état de disponibilité est défini sur tout autre statut sont exclus de la liste routage des appels et ne reçoivent aucun appel tant que leur état de disponibilité n’a pas été modifié en **disponible** .</span><span class="sxs-lookup"><span data-stu-id="f5492-164">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available** .</span></span> 

<span data-ttu-id="f5492-165">Vous pouvez activer le routage des appels en fonction de la présence avec n’importe quelle méthode de routage.</span><span class="sxs-lookup"><span data-stu-id="f5492-165">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="f5492-166">Si un agent ne peut plus passer d’appel, il n’est pas inclus dans la liste routage des appels, quelle que soit la valeur de son statut de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f5492-166">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="f5492-167">Les agents qui utilisent le client Skype entreprise ne sont pas inclus dans la liste des itinéraires d’appel lorsque le routage basé sur la présence est activé.</span><span class="sxs-lookup"><span data-stu-id="f5492-167">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="f5492-168">Si vous avez des agents qui utilisent Skype entreprise, n’activez pas le routage des appels basée sur la présence.</span><span class="sxs-lookup"><span data-stu-id="f5492-168">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="f5492-169">**Durée** de l’alerte d’agent spécifie la durée pendant laquelle le téléphone de l’agent sonnera avant que la file d’attente ne redirige l’appel vers l’agent suivant.</span><span class="sxs-lookup"><span data-stu-id="f5492-169">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="f5492-170">Pour les files d’attente de volume élevé, nous vous recommandons d’utiliser les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f5492-170">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="f5492-171">**Mode** de conférence **automatique**</span><span class="sxs-lookup"><span data-stu-id="f5492-171">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="f5492-172">**Méthode de routage** pour le **routage en standard**</span><span class="sxs-lookup"><span data-stu-id="f5492-172">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="f5492-173">**Routage basé** sur la présence sur **activé**</span><span class="sxs-lookup"><span data-stu-id="f5492-173">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="f5492-174">**Durée de l’alerte agent :** **20 secondes**</span><span class="sxs-lookup"><span data-stu-id="f5492-174">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="f5492-175">Gestion du dépassement des appels</span><span class="sxs-lookup"><span data-stu-id="f5492-175">Call overflow handling</span></span>

![Capture d’écran des paramètres de dépassement d’appel](media/call-queue-overflow-handling.png)

<span data-ttu-id="f5492-177">Le nombre **maximal d’appels dans la file d’attente** spécifie le nombre maximal d’appels qui peuvent patienter dans la file d’attente à tout moment.</span><span class="sxs-lookup"><span data-stu-id="f5492-177">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="f5492-178">La valeur par défaut est 50, mais elle peut varier entre 0 et 200.</span><span class="sxs-lookup"><span data-stu-id="f5492-178">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="f5492-179">Lorsque cette limite est atteinte, l’appel est géré conformément au paramètre **lorsque le nombre maximal d’appels est atteint** .</span><span class="sxs-lookup"><span data-stu-id="f5492-179">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="f5492-180">Vous pouvez choisir de déconnecter l’appel ou de le rediriger vers l’une des [destinations de routage des appels](create-a-phone-system-auto-attendant.md#call-routing-options) , à l’exception de l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="f5492-180">You can choose to disconnect the call or redirect it to any of the [call routing destinations](create-a-phone-system-auto-attendant.md#call-routing-options) except the operator.</span></span> <span data-ttu-id="f5492-181">Par exemple, vous pouvez demander à l’appelant de laisser une boîte vocale pour les agents dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f5492-181">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="f5492-182">(Notez [ces détails](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#external-phone-number-transfers---technical-details) si vous effectuez un virement vers un numéro externe.)</span><span class="sxs-lookup"><span data-stu-id="f5492-182">(Note [these details](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#external-phone-number-transfers---technical-details) if you're transferring to an external number.)</span></span>

> [!NOTE]
> <span data-ttu-id="f5492-183">Si le nombre maximum d’appels est défini sur 0, le message d’accueil n’est pas lu.</span><span class="sxs-lookup"><span data-stu-id="f5492-183">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="f5492-184">Gestion des délais d’appel</span><span class="sxs-lookup"><span data-stu-id="f5492-184">Call timeout handling</span></span>

![Capture d’écran des paramètres de délai d’appel](media/call-queue-timeout-handling.png)

<span data-ttu-id="f5492-186">**Délai d’appel : délai d’attente maximum** spécifie la durée maximale pendant laquelle un appel peut être mis en attente dans la file d’attente avant qu’elle ne soit redirigée ou déconnectée.</span><span class="sxs-lookup"><span data-stu-id="f5492-186">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="f5492-187">Vous pouvez spécifier une valeur comprise entre 15 secondes et 45 minutes.</span><span class="sxs-lookup"><span data-stu-id="f5492-187">You can specify a value from 15 seconds to 45 minutes.</span></span>

<span data-ttu-id="f5492-188">Vous pouvez choisir de déconnecter l’appel ou de le rediriger vers l’une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="f5492-188">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="f5492-189">Par exemple, vous pouvez demander à l’appelant de laisser une boîte vocale pour les agents dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="f5492-189">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span>

<span data-ttu-id="f5492-190">Lorsque vous avez sélectionné les options de temporisation de l’appel, cliquez sur **Enregistrer** .</span><span class="sxs-lookup"><span data-stu-id="f5492-190">When you have selected your call timeout options, click **Save** .</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="f5492-191">ID de l’appelant pour les appels sortants</span><span class="sxs-lookup"><span data-stu-id="f5492-191">Caller ID for outbound calls</span></span>

<span data-ttu-id="f5492-192">Dans la mesure où les agents d’une file d’attente d’appels risquent de composer un appel client, envisagez de définir l’identification de l’appelant pour les membres d’une file d’attente pour le numéro de service d’un standard automatique approprié.</span><span class="sxs-lookup"><span data-stu-id="f5492-192">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="f5492-193">Pour plus d’informations, voir [gérer les stratégies d’identification d’appelant dans Microsoft teams](caller-id-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="f5492-193">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="f5492-194">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="f5492-194">Supported clients</span></span>

- <span data-ttu-id="f5492-195">Les clients suivants sont pris en charge pour les téléopérateurs dans une file d’attente des appels :</span><span class="sxs-lookup"><span data-stu-id="f5492-195">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="f5492-196">Client de bureau Skype entreprise 2016 (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="f5492-196">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="f5492-197">Client de bureau Lync 2013 (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="f5492-197">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="f5492-198">Tous les modèles de téléphone IP pris en charge par Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f5492-198">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="f5492-199">Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="f5492-199">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="f5492-200">Client Skype entreprise pour Mac (version 16.8.196 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="f5492-200">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="f5492-201">Client Skype entreprise Android (version 6.16.0.9 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="f5492-201">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="f5492-202">Client Skype entreprise pour iPhone (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="f5492-202">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="f5492-203">Client Skype entreprise pour iPad (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="f5492-203">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="f5492-204">Client Microsoft Teams (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="f5492-204">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="f5492-205">Client Microsoft teams Mac</span><span class="sxs-lookup"><span data-stu-id="f5492-205">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="f5492-206">Application Microsoft teams pour iPhone</span><span class="sxs-lookup"><span data-stu-id="f5492-206">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="f5492-207">Application Android Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="f5492-207">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="f5492-208">Les files d’attente d’appels disposant d’un numéro de routage direct ne prennent pas en charge les clients Skype entreprise, les clients Lync ou les téléphones IP Skype entreprise en tant qu’agents.</span><span class="sxs-lookup"><span data-stu-id="f5492-208">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="f5492-209">Cmdlets de files d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="f5492-209">Call queue cmdlets</span></span>

<span data-ttu-id="f5492-210">Vous pouvez également utiliser Windows PowerShell pour créer et configurer des files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f5492-210">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="f5492-211">Voici les applets de passe que vous utilisez pour gérer une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="f5492-211">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="f5492-212">Nouveau-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f5492-212">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="f5492-213">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f5492-213">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="f5492-214">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f5492-214">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="f5492-215">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="f5492-215">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="f5492-216">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="f5492-216">Related topics</span></span>

[<span data-ttu-id="f5492-217">Voici les avantages du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="f5492-217">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="f5492-218">Obtention de numéros de téléphone de service</span><span class="sxs-lookup"><span data-stu-id="f5492-218">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="f5492-219">Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="f5492-219">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="f5492-220">Nouveau-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="f5492-220">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="f5492-221">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f5492-221">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
