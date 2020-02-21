---
title: Configurer le routage de la voix pour le routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Apprenez à configurer le routage de la voix avec le routage direct du système Microsoft Phone.
ms.openlocfilehash: 8889475acda00cf1565f944c7925ba0fb5194ec5
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157956"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="43a21-103">Configurer le routage de la voix pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="43a21-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="43a21-104">Cet article décrit comment configurer le routage vocal pour le routage direct du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="43a21-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="43a21-105">Pour configurer le routage direct, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="43a21-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="43a21-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="43a21-106">Step 1.</span></span> [<span data-ttu-id="43a21-107">Connecter l’SBC avec un système Microsoft Phone et valider la connexion</span><span class="sxs-lookup"><span data-stu-id="43a21-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="43a21-108">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="43a21-108">Step 2.</span></span> [<span data-ttu-id="43a21-109">Permettre aux utilisateurs d’utiliser le routage direct, les appels vocaux et la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="43a21-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)    
- <span data-ttu-id="43a21-110">**Étape 3. Configurer le routage** de la voix (cet article)</span><span class="sxs-lookup"><span data-stu-id="43a21-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="43a21-111">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="43a21-111">Step 4.</span></span> [<span data-ttu-id="43a21-112">Traduire des nombres dans un autre format</span><span class="sxs-lookup"><span data-stu-id="43a21-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="43a21-113">Pour plus d’informations sur la procédure de configuration du routage direct, voir [configurer le routage direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="43a21-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="43a21-114">Présentation du routage vocal</span><span class="sxs-lookup"><span data-stu-id="43a21-114">Voice routing overview</span></span>

<span data-ttu-id="43a21-115">Le système Microsoft Phone possède un mécanisme de routage qui permet d’envoyer un appel à un contrôleur de bordure de session spécifique (SBC) en fonction de :</span><span class="sxs-lookup"><span data-stu-id="43a21-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="43a21-116">Modèle de nombre appelé</span><span class="sxs-lookup"><span data-stu-id="43a21-116">The called number pattern</span></span> 
- <span data-ttu-id="43a21-117">Le modèle de numéro appelé et l’utilisateur spécifique qui effectue l’appel</span><span class="sxs-lookup"><span data-stu-id="43a21-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="43a21-118">SBCs peut être désignée comme active et Backup.</span><span class="sxs-lookup"><span data-stu-id="43a21-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="43a21-119">Lorsque l’SBC configuré comme étant actif n’est pas disponible pour un itinéraire d’appel spécifique, l’appel est acheminé vers un SBC de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="43a21-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="43a21-120">Le routage vocal est constitué des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="43a21-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="43a21-121">**Politique de routage** de la voix : conteneur des utilisations RTC qui peuvent être attribués à un utilisateur ou à plusieurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="43a21-121">**Voice routing policy** – A container for PSTN Usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="43a21-122">**Usages PSTN** : conteneur pour les itinéraires vocaux et usages RTC, qui peuvent être partagés dans différentes politiques de routage vocal.</span><span class="sxs-lookup"><span data-stu-id="43a21-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="43a21-123">**Itinéraires vocaux** : un modèle numérique et un ensemble de passerelles RTC en ligne à utiliser pour les appels pour lesquels le numéro de téléphone correspond au modèle.</span><span class="sxs-lookup"><span data-stu-id="43a21-123">**Voice Routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="43a21-124">**Passerelle RTC en ligne** : pointeur vers une SBC qui stocke également la configuration appliquée lors du passage d’un appel par le biais de l’SBC, tel que l’envoi d’identité P-assertion (PAI) ou les codecs préférés. peuvent être ajoutés aux itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="43a21-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="43a21-125">Exemple 1 : routage de la voix avec une utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="43a21-125">Example 1: Voice routing with one PSTN Usage</span></span>

<span data-ttu-id="43a21-126">Le schéma suivant montre deux exemples de stratégies de routage vocal dans un flux d’appels.</span><span class="sxs-lookup"><span data-stu-id="43a21-126">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="43a21-127">**Flux d’appels 1 (à gauche) :** Si un utilisateur effectue un appel vers + 1 425 XXX XX XX ou + 1 206 XXX XX XX, l’appel est acheminé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="43a21-127">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="43a21-128">Si les sbc1.contoso.biz et sbc2.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="43a21-128">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="43a21-129">**Flux d’appels 2 (sur la droite) :** Si un utilisateur effectue un appel vers + 1 425 XX XX XX ou + 1 206 XXX XX XX, l’appel est d’abord routé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="43a21-129">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="43a21-130">Si aucun SBC n’est disponible, l’itinéraire dont la priorité est faible est essayé (sbc3.contoso.biz et sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="43a21-130">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="43a21-131">Si aucune des SBCs n’est disponible, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="43a21-131">If none of the SBCs are available, the call is dropped.</span></span> 

![Exemples de stratégies de routage vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="43a21-133">Dans les deux exemples, si les priorités de l’itinéraire vocal sont affectées, les éléments SBCs dans les itinéraires sont essayés dans un ordre aléatoire.</span><span class="sxs-lookup"><span data-stu-id="43a21-133">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="43a21-134">À moins que l’utilisateur ne dispose d’une licence de plan d’appel Microsoft, les appels vers n’importe quel numéro, à l’exception des numéros correspondant aux modèles + 1 425 XXX XX XX ou + 1 206 XXX XX XX dans l’exemple de configuration sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="43a21-134">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="43a21-135">Si l’utilisateur dispose d’une licence de plan d’appel, l’appel est automatiquement acheminé conformément aux politiques du forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43a21-135">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="43a21-136">Le plan d’appel Microsoft s’applique automatiquement en tant que dernier itinéraire à tous les utilisateurs dotés de la licence de plan d’appel Microsoft et ne nécessite pas de configuration du routage des appels supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="43a21-136">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="43a21-137">Dans l’exemple ci-dessous, un itinéraire est ajouté à l’adresse de l’expéditeur pour les appels vers tous les autres États-Unis et le Canada (appels vers un modèle de numéro + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="43a21-137">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Affiche la politique de routage téléphonique avec un troisième itinéraire](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="43a21-139">Pour tous les autres appels :</span><span class="sxs-lookup"><span data-stu-id="43a21-139">For all other calls:</span></span>

- <span data-ttu-id="43a21-140">Si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), le routage automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="43a21-140">If a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> 
- <span data-ttu-id="43a21-141">S’il n’y a aucun résultat correspondant aux modèles de nombre dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé par le biais du forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43a21-141">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span>
- <span data-ttu-id="43a21-142">Si l’utilisateur dispose uniquement d’un système Microsoft Phone, l’appel est abandonné, car aucune règle correspondante n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="43a21-142">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="43a21-143">La valeur de priorité pour l’itinéraire « autres + 1 » n’a pas d’importance dans le cas du fait qu’il n’y a qu’un seul itinéraire qui correspond à la valeur du modèle + 1 XXX XX XX XX.</span><span class="sxs-lookup"><span data-stu-id="43a21-143">The Priority value for route "Other +1" doesn’t matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="43a21-144">Si un utilisateur effectue un appel à + 1 324 567 89 89 et que les sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="43a21-144">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="43a21-145">Le tableau suivant résume la configuration à l’aide de trois itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="43a21-145">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="43a21-146">Dans cet exemple, les trois itinéraires font partie de la même utilisation PSTN « États-Unis et Canada ».</span><span class="sxs-lookup"><span data-stu-id="43a21-146">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>  <span data-ttu-id="43a21-147">Tous les itinéraires sont associés à l’utilisation RTC « États-Unis et Canada » et l’utilisation RTC est associée à la politique de routage de la voix « États-Unis uniquement ».</span><span class="sxs-lookup"><span data-stu-id="43a21-147">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> 

|<span data-ttu-id="43a21-148">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="43a21-148">**PSTN usage**</span></span>|<span data-ttu-id="43a21-149">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="43a21-149">**Voice route**</span></span>|<span data-ttu-id="43a21-150">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="43a21-150">**Number pattern**</span></span>|<span data-ttu-id="43a21-151">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="43a21-151">**Priority**</span></span>|<span data-ttu-id="43a21-152">**SBC**</span><span class="sxs-lookup"><span data-stu-id="43a21-152">**SBC**</span></span>|<span data-ttu-id="43a21-153">**Description**</span><span class="sxs-lookup"><span data-stu-id="43a21-153">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="43a21-154">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="43a21-154">US only</span></span>|<span data-ttu-id="43a21-155">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="43a21-155">"Redmond 1"</span></span>|<span data-ttu-id="43a21-156">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="43a21-156">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="43a21-157">1</span><span class="sxs-lookup"><span data-stu-id="43a21-157">1</span></span>|<span data-ttu-id="43a21-158">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-158">sbc1.contoso.biz</span></span><br/><span data-ttu-id="43a21-159">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-159">sbc2.contoso.biz</span></span>|<span data-ttu-id="43a21-160">Itinéraire actif pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="43a21-160">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="43a21-161">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="43a21-161">US only</span></span>|<span data-ttu-id="43a21-162">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="43a21-162">"Redmond 2"</span></span>|<span data-ttu-id="43a21-163">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="43a21-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="43a21-164">deuxième</span><span class="sxs-lookup"><span data-stu-id="43a21-164">2</span></span>|<span data-ttu-id="43a21-165">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-165">sbc3.contoso.biz</span></span><br/><span data-ttu-id="43a21-166">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-166">sbc4.contoso.biz</span></span>|<span data-ttu-id="43a21-167">Itinéraire de sauvegarde pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="43a21-167">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="43a21-168">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="43a21-168">US only</span></span>|<span data-ttu-id="43a21-169">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="43a21-169">"Other +1"</span></span>|<span data-ttu-id="43a21-170">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="43a21-170">^\\+1(\d{10})$</span></span>|<span data-ttu-id="43a21-171">3</span><span class="sxs-lookup"><span data-stu-id="43a21-171">3</span></span>|<span data-ttu-id="43a21-172">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-172">sbc5.contoso.biz</span></span><br/><span data-ttu-id="43a21-173">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-173">sbc6.contoso.biz</span></span>|<span data-ttu-id="43a21-174">Itinéraire pour les numéros appelés + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="43a21-174">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||


### <a name="example-1-configuration-steps"></a><span data-ttu-id="43a21-175">Exemple 1 : étapes de configuration</span><span class="sxs-lookup"><span data-stu-id="43a21-175">Example 1: Configuration steps</span></span>

<span data-ttu-id="43a21-176">L’exemple suivant montre comment :</span><span class="sxs-lookup"><span data-stu-id="43a21-176">The following example shows how to:</span></span>

- <span data-ttu-id="43a21-177">Créer une utilisation PSTN unique</span><span class="sxs-lookup"><span data-stu-id="43a21-177">Create a single PSTN Usage</span></span> 
- <span data-ttu-id="43a21-178">Configurer trois itinéraires vocaux</span><span class="sxs-lookup"><span data-stu-id="43a21-178">Configure three voice routes</span></span>
- <span data-ttu-id="43a21-179">Créer une stratégie de routage de la voix</span><span class="sxs-lookup"><span data-stu-id="43a21-179">Create a voice routing policy</span></span>
- <span data-ttu-id="43a21-180">Affectez la stratégie à user Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="43a21-180">Assign the policy to user Spencer Low</span></span>

<span data-ttu-id="43a21-181">**Étape 1 :** Créer l’utilisation RTC "États-Unis et Canada"</span><span class="sxs-lookup"><span data-stu-id="43a21-181">**Step 1:** Create the PSTN Usage "US and Canada"</span></span>

<span data-ttu-id="43a21-182">Dans une session PowerShell distante Skype entreprise, tapez :</span><span class="sxs-lookup"><span data-stu-id="43a21-182">In a Skype for Business Remote PowerShell session, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="43a21-183">Vérifiez que l’utilisation a été créée en entrant :</span><span class="sxs-lookup"><span data-stu-id="43a21-183">Validate that the usage was created by entering:</span></span> 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="43a21-184">Qui renvoie une liste de noms qui risquent d’être tronqués :</span><span class="sxs-lookup"><span data-stu-id="43a21-184">Which returns a list of names that may be truncated:</span></span>
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="43a21-185">L’exemple ci-dessous montre le résultat de l’exécution `(Get-CSOnlinePSTNUsage).usage` de la commande PowerShell pour afficher les noms complets (pas tronqués) :</span><span class="sxs-lookup"><span data-stu-id="43a21-185">The example below shows the result of  running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated):</span></span>

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

<span data-ttu-id="43a21-186">**Étape 2 :** Dans une session PowerShell dans Skype entreprise Online, créez trois itinéraires : Redmond 1, Redmond 2 et autres + 1, comme indiqué dans le tableau précédent.</span><span class="sxs-lookup"><span data-stu-id="43a21-186">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as shown in the previous table</span></span>

<span data-ttu-id="43a21-187">Pour créer l’itinéraire « Redmond 1 », entrez :</span><span class="sxs-lookup"><span data-stu-id="43a21-187">To create the "Redmond 1" route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="43a21-188">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="43a21-188">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="43a21-189">Pour créer l’itinéraire de Redmond 2, entrez :</span><span class="sxs-lookup"><span data-stu-id="43a21-189">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="43a21-190">Pour créer l’autre itinéraire + 1, entrez :</span><span class="sxs-lookup"><span data-stu-id="43a21-190">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="43a21-191">Assurez-vous que votre expression régulière dans l’attribut NumberPattern est une expression valide.</span><span class="sxs-lookup"><span data-stu-id="43a21-191">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="43a21-192">Vous pouvez le tester à l’aide du site Web suivant :[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="43a21-192">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="43a21-193">Dans certains cas, il est nécessaire de router tous les appels vers le même SBC ; use-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="43a21-193">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="43a21-194">Acheminez tous les appels vers le même SBC.</span><span class="sxs-lookup"><span data-stu-id="43a21-194">Route all calls to same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="43a21-195">Vérifiez que vous avez correctement configuré l’itinéraire en exécutant la `Get-CSOnlineVoiceRoute` commande PowerShell en utilisant les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="43a21-195">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="43a21-196">Qui doit retourner :</span><span class="sxs-lookup"><span data-stu-id="43a21-196">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="43a21-197">Dans l’exemple, l’itinéraire « Other + 1 » a automatiquement la priorité 4.</span><span class="sxs-lookup"><span data-stu-id="43a21-197">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="43a21-198">**Étape 3 :** Créez une stratégie de routage de la voix « États-Unis uniquement » et ajoutez-la à la politique « États-Unis et Canada ».</span><span class="sxs-lookup"><span data-stu-id="43a21-198">**Step 3:** Create a voice routing policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="43a21-199">Dans une session PowerShell dans Skype entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="43a21-199">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="43a21-200">Le résultat est affiché dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="43a21-200">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="43a21-201">**Étape 4 :** À l’aide de PowerShell, accordez la stratégie de routage vocale à l’utilisateur Spencer Low :</span><span class="sxs-lookup"><span data-stu-id="43a21-201">**Step 4:** By using PowerShell, grant the voice routing policy to the user Spencer Low:</span></span>

<span data-ttu-id="43a21-202">Dans une session PowerShell dans Skype entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="43a21-202">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="43a21-203">Validez l’affectation de stratégie en entrant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="43a21-203">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="43a21-204">La commande renvoie ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="43a21-204">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="43a21-205">Exemple 2 : routage de la voix avec plusieurs utilisations RTC</span><span class="sxs-lookup"><span data-stu-id="43a21-205">Example 2: Voice routing with multiple PSTN Usages</span></span>

<span data-ttu-id="43a21-206">La politique de routage vocale créée dans l’exemple 1 autorise uniquement les appels vers les numéros de téléphone aux États-Unis et au Canada, sauf si la licence de plan d’appel Microsoft est également affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="43a21-206">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="43a21-207">Dans l’exemple qui suit, vous pouvez créer la stratégie de routage téléphonique « aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="43a21-207">In the example that follows, you can create the voice routing policy "No Restrictions."</span></span> <span data-ttu-id="43a21-208">La stratégie réutilise l’utilisation RTC « États-Unis et Canada » créée dans l’exemple 1, ainsi que la nouvelle utilisation RTC « international ».</span><span class="sxs-lookup"><span data-stu-id="43a21-208">The policy reuses the PSTN Usage "US and Canada" created in Example 1, as well as the new PSTN Usage "International."</span></span>  <span data-ttu-id="43a21-209">Cette stratégie route tous les autres appels vers l’SBCs sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="43a21-209">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> 

<span data-ttu-id="43a21-210">Les exemples qui s’affichent affectent la politique américaine uniquement à l’utilisateur Beaune Low et la stratégie no restrictions à l’utilisateur Jean Martin de sorte que le routage se déroule comme suit :</span><span class="sxs-lookup"><span data-stu-id="43a21-210">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="43a21-211">Beaune : politique de niveau faible-américaine uniquement.</span><span class="sxs-lookup"><span data-stu-id="43a21-211">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="43a21-212">Les appels ne sont admis qu’aux États-Unis et au Canada.</span><span class="sxs-lookup"><span data-stu-id="43a21-212">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="43a21-213">Lorsque vous appelez la plage de numéros Redmond, l’ensemble spécifique de SBCs doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="43a21-213">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="43a21-214">Les numéros non US ne seront pas routés sauf si la licence de plan d’appel est affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="43a21-214">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="43a21-215">Jean bois-politique internationale.</span><span class="sxs-lookup"><span data-stu-id="43a21-215">John Woods – International policy.</span></span>  <span data-ttu-id="43a21-216">Les appels sont autorisés à n’importe quel numéro.</span><span class="sxs-lookup"><span data-stu-id="43a21-216">Calls are allowed to any number.</span></span> <span data-ttu-id="43a21-217">Lorsque vous appelez la plage de numéros Redmond, l’ensemble spécifique de SBCs doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="43a21-217">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="43a21-218">Les numéros non US seront routés à l’aide de sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="43a21-218">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Affiche la politique de routage vocale affectée à l’utilisateur Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="43a21-220">Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), un itinéraire automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="43a21-220">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="43a21-221">S’il n’y a aucun résultat correspondant aux modèles de chiffres dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé à l’aide d’un forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43a21-221">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="43a21-222">Si l’utilisateur dispose uniquement du système Microsoft Phone, l’appel est abandonné, car aucune règle de correspondance n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="43a21-222">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Politique de routage de la voix attribuée à l’utilisateur Jean bois](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="43a21-224">Le tableau suivant récapitule les concepteurs d’utilisation et les itinéraires vocaux de la stratégie de routage « aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="43a21-224">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="43a21-225">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="43a21-225">**PSTN usage**</span></span>|<span data-ttu-id="43a21-226">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="43a21-226">**Voice route**</span></span>|<span data-ttu-id="43a21-227">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="43a21-227">**Number pattern**</span></span>|<span data-ttu-id="43a21-228">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="43a21-228">**Priority**</span></span>|<span data-ttu-id="43a21-229">**SBC**</span><span class="sxs-lookup"><span data-stu-id="43a21-229">**SBC**</span></span>|<span data-ttu-id="43a21-230">**Description**</span><span class="sxs-lookup"><span data-stu-id="43a21-230">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="43a21-231">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="43a21-231">US Only</span></span>|<span data-ttu-id="43a21-232">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="43a21-232">"Redmond 1"</span></span>|<span data-ttu-id="43a21-233">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="43a21-233">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="43a21-234">1</span><span class="sxs-lookup"><span data-stu-id="43a21-234">1</span></span>|<span data-ttu-id="43a21-235">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-235">sbc1.contoso.biz</span></span><br/><span data-ttu-id="43a21-236">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-236">sbc2.contoso.biz</span></span>|<span data-ttu-id="43a21-237">Itinéraire actif pour les numéros d’appelant + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="43a21-237">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="43a21-238">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="43a21-238">US Only</span></span>|<span data-ttu-id="43a21-239">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="43a21-239">"Redmond 2"</span></span>|<span data-ttu-id="43a21-240">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="43a21-240">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="43a21-241">deuxième</span><span class="sxs-lookup"><span data-stu-id="43a21-241">2</span></span>|<span data-ttu-id="43a21-242">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-242">sbc3.contoso.biz</span></span><br/><span data-ttu-id="43a21-243">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-243">sbc4.contoso.biz</span></span>|<span data-ttu-id="43a21-244">Itinéraire de sauvegarde pour les numéros des appelants + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="43a21-244">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="43a21-245">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="43a21-245">US Only</span></span>|<span data-ttu-id="43a21-246">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="43a21-246">"Other +1"</span></span>|<span data-ttu-id="43a21-247">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="43a21-247">^\\+1(\d{10})$</span></span>|<span data-ttu-id="43a21-248">3</span><span class="sxs-lookup"><span data-stu-id="43a21-248">3</span></span>|<span data-ttu-id="43a21-249">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-249">sbc5.contoso.biz</span></span><br/><span data-ttu-id="43a21-250">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-250">sbc6>.contoso.biz</span></span>|<span data-ttu-id="43a21-251">Itinéraire pour les numéros d’appelant + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="43a21-251">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="43a21-252">International</span><span class="sxs-lookup"><span data-stu-id="43a21-252">International</span></span>|<span data-ttu-id="43a21-253">International</span><span class="sxs-lookup"><span data-stu-id="43a21-253">International</span></span>|<span data-ttu-id="43a21-254">\d +</span><span class="sxs-lookup"><span data-stu-id="43a21-254">\d+</span></span>|<span data-ttu-id="43a21-255">4</span><span class="sxs-lookup"><span data-stu-id="43a21-255">4</span></span>|<span data-ttu-id="43a21-256">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-256">sbc2.contoso.biz</span></span><br/><span data-ttu-id="43a21-257">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="43a21-257">sbc5.contoso.biz</span></span>|<span data-ttu-id="43a21-258">Itinéraire pour n’importe quel modèle numérique</span><span class="sxs-lookup"><span data-stu-id="43a21-258">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="43a21-259">L’ordre des utilisations RTC dans les stratégies de routage vocale est essentiel.</span><span class="sxs-lookup"><span data-stu-id="43a21-259">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="43a21-260">Les utilisations sont appliquées dans l’ordre et, si une correspondance est trouvée dans la première utilisation, les autres utilisations ne sont jamais évaluées.</span><span class="sxs-lookup"><span data-stu-id="43a21-260">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="43a21-261">L’utilisation RTC « international » doit être placée après l’utilisation RTC « États-Unis uniquement ».</span><span class="sxs-lookup"><span data-stu-id="43a21-261">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="43a21-262">Pour modifier l’ordre des utilisations RTC, exécutez la `Set-CSOnlineVoiceRoutingPolicy` commande.</span><span class="sxs-lookup"><span data-stu-id="43a21-262">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="43a21-263">Par exemple, pour passer de l’ordre « États-Unis et Canada » et inversement, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="43a21-263">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="43a21-264">Le niveau de priorité des itinéraires vocaux « Other + 1 » et « international » est automatiquement attribué.</span><span class="sxs-lookup"><span data-stu-id="43a21-264">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="43a21-265">Il n’y a pas d’importance tant qu’il dispose de priorités inférieures à « Redmond 1 » et « Redmond 2 ».</span><span class="sxs-lookup"><span data-stu-id="43a21-265">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>


### <a name="example-2-configuration-steps"></a><span data-ttu-id="43a21-266">Exemple 2 : étapes de configuration</span><span class="sxs-lookup"><span data-stu-id="43a21-266">Example 2: Configuration steps</span></span>

<span data-ttu-id="43a21-267">L’exemple suivant montre comment :</span><span class="sxs-lookup"><span data-stu-id="43a21-267">The following example shows how to:</span></span>

- <span data-ttu-id="43a21-268">Créer une nouvelle utilisation RTC appelée international</span><span class="sxs-lookup"><span data-stu-id="43a21-268">Create a new PSTN Usage called International</span></span>
- <span data-ttu-id="43a21-269">Créer un nouvel itinéraire vocal appelé international</span><span class="sxs-lookup"><span data-stu-id="43a21-269">Create a new voice route called International</span></span>
- <span data-ttu-id="43a21-270">Création d’une stratégie de routage de la voix sans restrictions</span><span class="sxs-lookup"><span data-stu-id="43a21-270">Create a voice routing policy called No Restrictions</span></span>
- <span data-ttu-id="43a21-271">Affecter la politique aux bois des utilisateurs Jean</span><span class="sxs-lookup"><span data-stu-id="43a21-271">Assign the policy to user John Woods</span></span>


<span data-ttu-id="43a21-272">**Étape 1**: créer une utilisation PSTN internationale.</span><span class="sxs-lookup"><span data-stu-id="43a21-272">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="43a21-273">Dans une session PowerShell distante dans Skype entreprise Online, entrez :</span><span class="sxs-lookup"><span data-stu-id="43a21-273">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="43a21-274">**Étape 2**: créer le nouvel itinéraire vocal « international »</span><span class="sxs-lookup"><span data-stu-id="43a21-274">**Step 2**:  Create the new voice route "International."</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="43a21-275">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="43a21-275">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="43a21-276">**Étape 3**: créer une stratégie de routage téléphonique « aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="43a21-276">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="43a21-277">L’utilisation RTC « Redmond 1 » et « Redmond » sont réutilisées dans cette politique de routage vocale pour garantir une gestion spéciale des appels au numéro « + 1 425 XXX XX XX » et « + 1 206 XXX XX XX » en tant qu’appels locaux ou locaux.</span><span class="sxs-lookup"><span data-stu-id="43a21-277">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="43a21-278">Prenez note de l’ordre des utilisations RTC :</span><span class="sxs-lookup"><span data-stu-id="43a21-278">Take note of the order of PSTN Usages:</span></span>

  <span data-ttu-id="43a21-279">a.</span><span class="sxs-lookup"><span data-stu-id="43a21-279">a.</span></span> <span data-ttu-id="43a21-280">Si un appel a été effectué pour le numéro « + 1 425 XXX XX XX » avec les utilisations configurées comme dans l’exemple suivant, l’appel suit le routage défini dans utilisation des États-Unis et du Canada et la logique de routage spécial est appliquée.</span><span class="sxs-lookup"><span data-stu-id="43a21-280">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="43a21-281">C’est la première fois que l’appel est routé à l’aide de sbc1.contoso.biz et sbc2.contoso.biz, puis de sbc3.contoso.biz et d’sbc4.contoso.biz de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="43a21-281">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  <span data-ttu-id="43a21-282">b.</span><span class="sxs-lookup"><span data-stu-id="43a21-282">b.</span></span> <span data-ttu-id="43a21-283">S’il s’agit d’une utilisation PSTN « internationale », les appels vers + 1 425 XXX XX XX sont routés vers sbc2.contoso.biz et sbc5.contoso.biz dans le cadre de la logique de routage.</span><span class="sxs-lookup"><span data-stu-id="43a21-283">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="43a21-284">Entrez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="43a21-284">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="43a21-285">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="43a21-285">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

<span data-ttu-id="43a21-286">**Étape 4**: affectez la stratégie de routage téléphonique à l’utilisateur « Jean bois » à l’aide de la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="43a21-286">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="43a21-287">Vérifiez ensuite le devoir à l’aide de la commande :</span><span class="sxs-lookup"><span data-stu-id="43a21-287">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="43a21-288">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="43a21-288">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="43a21-289">Le résultat est que la stratégie vocale appliquée aux appels de Jean-Martin n’est pas restreinte et qu’elle respecte la logique du routage des appels disponible aux États-Unis, au Canada et au service d’appels internationaux.</span><span class="sxs-lookup"><span data-stu-id="43a21-289">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>



## <a name="see-also"></a><span data-ttu-id="43a21-290">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43a21-290">See also</span></span>

[<span data-ttu-id="43a21-291">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="43a21-291">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="43a21-292">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="43a21-292">Configure Direct Routing</span></span>](direct-routing-configure.md)
