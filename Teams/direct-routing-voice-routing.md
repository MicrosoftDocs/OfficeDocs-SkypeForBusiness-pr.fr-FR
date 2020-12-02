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
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530991"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="85676-103">Configurer le routage de la voix pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="85676-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="85676-104">Cet article décrit comment configurer le routage vocal pour le routage direct du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="85676-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="85676-105">Pour configurer le routage direct, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="85676-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="85676-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="85676-106">Step 1.</span></span> [<span data-ttu-id="85676-107">Connecter l’SBC avec un système Microsoft Phone et valider la connexion</span><span class="sxs-lookup"><span data-stu-id="85676-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="85676-108">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="85676-108">Step 2.</span></span> [<span data-ttu-id="85676-109">Permettre aux utilisateurs d’utiliser le routage direct, les appels vocaux et la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="85676-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="85676-110">**Étape 3. Configurer le routage** de la voix (cet article)</span><span class="sxs-lookup"><span data-stu-id="85676-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="85676-111">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="85676-111">Step 4.</span></span> [<span data-ttu-id="85676-112">Traduire des nombres dans un autre format</span><span class="sxs-lookup"><span data-stu-id="85676-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="85676-113">Pour plus d’informations sur la procédure de configuration du routage direct, voir [configurer le routage direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="85676-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="85676-114">Présentation du routage vocal</span><span class="sxs-lookup"><span data-stu-id="85676-114">Voice routing overview</span></span>

<span data-ttu-id="85676-115">Le système Microsoft Phone possède un mécanisme de routage qui permet d’envoyer un appel à un contrôleur de bordure de session spécifique (SBC) en fonction de :</span><span class="sxs-lookup"><span data-stu-id="85676-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="85676-116">Modèle de nombre appelé</span><span class="sxs-lookup"><span data-stu-id="85676-116">The called number pattern</span></span> 
- <span data-ttu-id="85676-117">Le modèle de numéro appelé et l’utilisateur spécifique qui effectue l’appel</span><span class="sxs-lookup"><span data-stu-id="85676-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="85676-118">SBCs peut être désignée comme active et Backup.</span><span class="sxs-lookup"><span data-stu-id="85676-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="85676-119">Lorsque l’SBC configuré comme étant actif n’est pas disponible pour un itinéraire d’appel spécifique, l’appel est acheminé vers un SBC de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="85676-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="85676-120">Le routage vocal est constitué des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="85676-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="85676-121">**Politique de routage** de la voix : conteneur des utilisations RTC qui peuvent être attribués à un utilisateur ou à plusieurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="85676-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="85676-122">**Usages PSTN** : conteneur pour les itinéraires vocaux et usages RTC, qui peuvent être partagés dans différentes politiques de routage vocal.</span><span class="sxs-lookup"><span data-stu-id="85676-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="85676-123">**Itinéraires vocaux** : un modèle numérique et un ensemble de passerelles RTC en ligne à utiliser pour les appels pour lesquels le numéro de téléphone correspond au modèle.</span><span class="sxs-lookup"><span data-stu-id="85676-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="85676-124">**Passerelle RTC en ligne** : pointeur vers une SBC qui stocke également la configuration appliquée lors du passage d’un appel par le biais de l’SBC, tel que l’envoi d’identité P-assertion (PAI) ou les codecs préférés. peuvent être ajoutés aux itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="85676-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="85676-125">Considérations relatives à la politique de routage vocale</span><span class="sxs-lookup"><span data-stu-id="85676-125">Voice routing policy considerations</span></span>

<span data-ttu-id="85676-126">Si un utilisateur dispose d’une licence de plan d’appel, les appels sortants de cet utilisateur sont automatiquement routés par le biais de l’infrastructure PSTN du plan d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85676-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="85676-127">Si vous configurez et attribuez une stratégie de routage téléphonique en ligne à un utilisateur de plan d’appel, les appels sortants de cet utilisateur sont examinés pour déterminer si le numéro numéroté correspond à un modèle défini dans la stratégie de routage de la voix en ligne.</span><span class="sxs-lookup"><span data-stu-id="85676-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="85676-128">S’il existe une correspondance, l’appel est acheminé via le Trunk de routage direct.</span><span class="sxs-lookup"><span data-stu-id="85676-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="85676-129">S’il n’y a aucune correspondance, l’appel est acheminé via l’infrastructure PSTN du plan d’appel.</span><span class="sxs-lookup"><span data-stu-id="85676-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="85676-130">Si vous configurez et appliquez la stratégie globale de routage téléphonique en ligne par défaut de l’organisation, tous les utilisateurs à extension vocale de votre organisation hériteront de cette stratégie, ce qui peut entraîner des appels RTC involontairement routés vers un Trunk de routage direct.</span><span class="sxs-lookup"><span data-stu-id="85676-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="85676-131">Si vous ne souhaitez pas que tous les utilisateurs utilisent la stratégie de routage de la voix en ligne globale, configurez une stratégie de routage de la voix en ligne personnalisée et attribuez-la à des utilisateurs vocaux individuels.</span><span class="sxs-lookup"><span data-stu-id="85676-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="85676-132">Exemple 1 : routage de la voix avec une utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="85676-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="85676-133">Le schéma suivant montre deux exemples de stratégies de routage vocal dans un flux d’appels.</span><span class="sxs-lookup"><span data-stu-id="85676-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="85676-134">**Flux d’appels 1 (à gauche) :** Si un utilisateur effectue un appel vers + 1 425 XXX XX XX ou + 1 206 XXX XX XX, l’appel est acheminé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="85676-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="85676-135">Si les sbc1.contoso.biz et sbc2.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="85676-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="85676-136">**Flux d’appels 2 (sur la droite) :** Si un utilisateur effectue un appel vers + 1 425 XX XX XX ou + 1 206 XXX XX XX, l’appel est d’abord routé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="85676-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="85676-137">Si aucun SBC n’est disponible, l’itinéraire dont la priorité est faible est essayé (sbc3.contoso.biz et sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="85676-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="85676-138">Si aucune des SBCs n’est disponible, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="85676-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Exemples de stratégies de routage vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="85676-140">Dans les deux exemples, si les priorités de l’itinéraire vocal sont affectées, les éléments SBCs dans les itinéraires sont essayés dans un ordre aléatoire.</span><span class="sxs-lookup"><span data-stu-id="85676-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span> <span data-ttu-id="85676-141">Lorsque deux SBC sont configurés dans une seule route, le trafic réseau doit être routable entre les SBC ou les médias ne peut pas être établi sur les transferts, car il est possible que la nouvelle invitation pour le transfert soit envoyée à un autre SBC dans l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="85676-141">When two SBC's are configured in one route, network traffic must be routable between both SBC's or media will fail to be established on transfers as it is possible that the new invite for the transfer will be sent to a different SBC in the route.</span></span>

  > [!NOTE]
  > <span data-ttu-id="85676-142">À moins que l’utilisateur ne dispose d’une licence de plan d’appel Microsoft, les appels vers n’importe quel numéro, à l’exception des numéros correspondant aux modèles + 1 425 XXX XX XX ou + 1 206 XXX XX XX dans l’exemple de configuration sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="85676-142">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="85676-143">Si l’utilisateur dispose d’une licence de plan d’appel, l’appel est automatiquement acheminé conformément aux politiques du forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85676-143">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="85676-144">Le plan d’appel Microsoft s’applique automatiquement en tant que dernier itinéraire à tous les utilisateurs dotés de la licence de plan d’appel Microsoft et ne nécessite pas de configuration du routage des appels supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="85676-144">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="85676-145">Dans l’exemple ci-dessous, un itinéraire est ajouté à l’adresse de l’expéditeur pour les appels vers tous les autres États-Unis et le Canada (appels vers un modèle de numéro + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="85676-145">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Affiche la politique de routage téléphonique avec un troisième itinéraire](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="85676-147">Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), l’itinéraire automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="85676-147">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="85676-148">S’il n’y a aucun résultat correspondant aux modèles de nombre dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé par le biais du forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85676-148">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="85676-149">Si l’utilisateur dispose uniquement d’un système Microsoft Phone, l’appel est abandonné, car aucune règle correspondante n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="85676-149">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="85676-150">La valeur de priorité pour l’itinéraire « autres + 1 » n’a pas d’importance dans le cas du fait qu’il n’y a qu’un seul itinéraire qui correspond à la valeur du modèle + 1 XXX XX XX XX.</span><span class="sxs-lookup"><span data-stu-id="85676-150">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="85676-151">Si un utilisateur effectue un appel à + 1 324 567 89 89 et que les sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="85676-151">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="85676-152">Le tableau suivant résume la configuration à l’aide de trois itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="85676-152">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="85676-153">Dans cet exemple, les trois itinéraires font partie de la même utilisation PSTN, « États-Unis et Canada ».</span><span class="sxs-lookup"><span data-stu-id="85676-153">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="85676-154">Tous les itinéraires sont associés à l’utilisation RTC « États-Unis et Canada » et l’utilisation RTC est associée à la politique de routage téléphonique « États-Unis uniquement ».</span><span class="sxs-lookup"><span data-stu-id="85676-154">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="85676-155">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="85676-155">**PSTN usage**</span></span>|<span data-ttu-id="85676-156">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="85676-156">**Voice route**</span></span>|<span data-ttu-id="85676-157">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="85676-157">**Number pattern**</span></span>|<span data-ttu-id="85676-158">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="85676-158">**Priority**</span></span>|<span data-ttu-id="85676-159">**SBC**</span><span class="sxs-lookup"><span data-stu-id="85676-159">**SBC**</span></span>|<span data-ttu-id="85676-160">**Description**</span><span class="sxs-lookup"><span data-stu-id="85676-160">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="85676-161">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="85676-161">US and Canada</span></span>|<span data-ttu-id="85676-162">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="85676-162">"Redmond 1"</span></span>|<span data-ttu-id="85676-163">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="85676-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="85676-164">1</span><span class="sxs-lookup"><span data-stu-id="85676-164">1</span></span>|<span data-ttu-id="85676-165">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-165">sbc1.contoso.biz</span></span><br/><span data-ttu-id="85676-166">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-166">sbc2.contoso.biz</span></span>|<span data-ttu-id="85676-167">Itinéraire actif pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="85676-167">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="85676-168">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="85676-168">US and Canada</span></span>|<span data-ttu-id="85676-169">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="85676-169">"Redmond 2"</span></span>|<span data-ttu-id="85676-170">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="85676-170">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="85676-171">2</span><span class="sxs-lookup"><span data-stu-id="85676-171">2</span></span>|<span data-ttu-id="85676-172">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-172">sbc3.contoso.biz</span></span><br/><span data-ttu-id="85676-173">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-173">sbc4.contoso.biz</span></span>|<span data-ttu-id="85676-174">Itinéraire de sauvegarde pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="85676-174">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="85676-175">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="85676-175">US and Canada</span></span>|<span data-ttu-id="85676-176">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="85676-176">"Other +1"</span></span>|<span data-ttu-id="85676-177">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="85676-177">^\\+1(\d{10})$</span></span>|<span data-ttu-id="85676-178">3</span><span class="sxs-lookup"><span data-stu-id="85676-178">3</span></span>|<span data-ttu-id="85676-179">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-179">sbc5.contoso.biz</span></span><br/><span data-ttu-id="85676-180">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-180">sbc6.contoso.biz</span></span>|<span data-ttu-id="85676-181">Itinéraire pour les numéros appelés + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="85676-181">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="85676-182">Exemple 1 : étapes de configuration</span><span class="sxs-lookup"><span data-stu-id="85676-182">Example 1: Configuration steps</span></span>

<span data-ttu-id="85676-183">L’exemple suivant montre comment :</span><span class="sxs-lookup"><span data-stu-id="85676-183">The following example shows how to:</span></span>

1. <span data-ttu-id="85676-184">Créez une utilisation PSTN unique.</span><span class="sxs-lookup"><span data-stu-id="85676-184">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="85676-185">Configurer trois itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="85676-185">Configure three voice routes.</span></span>
3. <span data-ttu-id="85676-186">Créer une stratégie de routage de la voix.</span><span class="sxs-lookup"><span data-stu-id="85676-186">Create a voice routing policy.</span></span>
4. <span data-ttu-id="85676-187">Affectez la stratégie à un utilisateur nommé Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="85676-187">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="85676-188">Vous pouvez utiliser le [Centre d’administration Microsoft teams](#admincenterexample1) ou [PowerShell](#powershellexample1) pour effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="85676-188">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="85676-189">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85676-189">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="85676-190">Étape 1 : créer l’utilisation RTC des États-Unis et du Canada</span><span class="sxs-lookup"><span data-stu-id="85676-190">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="85676-191">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice** Teams,  >  **Direct Routing** sélectionnez **gérer les enregistrements d’utilisation RTC** dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="85676-191">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="85676-192">Cliquez sur **Ajouter**, tapez **États-Unis et Canada**, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="85676-192">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="85676-193">Étape 2 : créer trois itinéraires vocaux (Redmond 1, Redmond 2 et autres + 1)</span><span class="sxs-lookup"><span data-stu-id="85676-193">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="85676-194">Les étapes suivantes décrivent la création d’un itinéraire vocal.</span><span class="sxs-lookup"><span data-stu-id="85676-194">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="85676-195">Suivez ces étapes pour créer les trois itinéraires vocaux nommés Redmond 1, Redmond 2 et autres + 1 pour cet exemple en utilisant les paramètres définis dans le tableau précédent.</span><span class="sxs-lookup"><span data-stu-id="85676-195">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="85676-196">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice** Teams, accédez à  >  **routage direct** de la voix, puis sélectionnez l’onglet **itinéraires vocaux** .</span><span class="sxs-lookup"><span data-stu-id="85676-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="85676-197">Cliquez sur **Ajouter**, puis entrez le nom et la description de l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="85676-197">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="85676-198">Définissez la priorité et spécifiez le modèle de numéro numéroté.</span><span class="sxs-lookup"><span data-stu-id="85676-198">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="85676-199">Pour inscrire une SBC auprès de l’itinéraire de la voix, sous **SBCS inscrits (facultatif)**, cliquez sur **Ajouter SBCS**, sélectionnez le SBCS que vous voulez inscrire, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="85676-199">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="85676-200">Pour ajouter des enregistrements d’utilisation RTC, sous **enregistrements d’utilisation RTC (facultatif)**, cliquez sur **Ajouter une utilisation PSTN**, sélectionnez les enregistrements RTC que vous voulez ajouter, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="85676-200">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="85676-201">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="85676-201">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="85676-202">Étape 3 : créer une stratégie de routage de la voix nommée « États-Unis uniquement » et ajouter l’utilisation RTC « États-Unis et Canada » à la politique</span><span class="sxs-lookup"><span data-stu-id="85676-202">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="85676-203">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à** stratégies de routage de voix vocales, puis  >  **Voice routing policies** cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="85676-203">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="85676-204">Tapez **-nous uniquement** le nom et ajoutez une description.</span><span class="sxs-lookup"><span data-stu-id="85676-204">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="85676-205">Sous **rapports d’utilisation RTC**, cliquez sur **Ajouter une utilisation PSTN**, sélectionnez l’enregistrement d’utilisation RTC « États-Unis et Canada », puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="85676-205">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="85676-206">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="85676-206">Click **Save**.</span></span>

<span data-ttu-id="85676-207">Pour en savoir plus, voir [gérer les stratégies de routage de messagerie vocale](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="85676-207">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="85676-208">Étape 4 : affecter la stratégie de routage téléphonique à un utilisateur nommé Spencer Low</span><span class="sxs-lookup"><span data-stu-id="85676-208">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="85676-209">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="85676-209">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="85676-210">Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="85676-210">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="85676-211">Sous **politique de routage** de la voix, sélectionnez la stratégie « États-Unis uniquement », puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="85676-211">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="85676-212">Pour en savoir plus, voir [gérer les stratégies de routage de messagerie vocale](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="85676-212">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="85676-213">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="85676-213">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="85676-214">Étape 1 : créer l’utilisation RTC des États-Unis et du Canada</span><span class="sxs-lookup"><span data-stu-id="85676-214">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="85676-215">Dans une session PowerShell distante dans Skype entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="85676-215">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="85676-216">Vérifiez que l’utilisation a été créée en entrant :</span><span class="sxs-lookup"><span data-stu-id="85676-216">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="85676-217">Qui renvoie une liste de noms qui risquent d’être tronqués :</span><span class="sxs-lookup"><span data-stu-id="85676-217">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="85676-218">L’exemple suivant montre le résultat de l’exécution de la `(Get-CSOnlinePSTNUsage).usage` commande PowerShell pour afficher les noms complets (pas tronqués) :</span><span class="sxs-lookup"><span data-stu-id="85676-218">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="85676-219">Étape 2 : créer trois itinéraires vocaux (Redmond 1, Redmond 2 et autres + 1)</span><span class="sxs-lookup"><span data-stu-id="85676-219">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="85676-220">Pour créer l’itinéraire « Redmond 1 » dans une session PowerShell dans Skype entreprise Online, entrez :</span><span class="sxs-lookup"><span data-stu-id="85676-220">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="85676-221">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="85676-221">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="85676-222">Pour créer l’itinéraire de Redmond 2, entrez :</span><span class="sxs-lookup"><span data-stu-id="85676-222">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="85676-223">Pour créer l’autre itinéraire + 1, entrez :</span><span class="sxs-lookup"><span data-stu-id="85676-223">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="85676-224">Assurez-vous que votre expression régulière dans l’attribut NumberPattern est une expression valide.</span><span class="sxs-lookup"><span data-stu-id="85676-224">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="85676-225">Vous pouvez le tester à l’aide du site Web suivant : [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="85676-225">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="85676-226">Dans certains cas, il est nécessaire de router tous les appels vers le même SBC ; use-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="85676-226">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="85676-227">Acheminez tous les appels vers le même SBC.</span><span class="sxs-lookup"><span data-stu-id="85676-227">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="85676-228">Vérifiez que vous avez correctement configuré l’itinéraire en exécutant la `Get-CSOnlineVoiceRoute` commande PowerShell en utilisant les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="85676-228">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="85676-229">Qui doit retourner :</span><span class="sxs-lookup"><span data-stu-id="85676-229">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
</pre>

<span data-ttu-id="85676-230">Dans l’exemple, l’itinéraire « Other + 1 » a automatiquement la priorité 4.</span><span class="sxs-lookup"><span data-stu-id="85676-230">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="85676-231">Étape 3 : créer une stratégie de routage de la voix nommée « États-Unis uniquement » et ajouter l’utilisation RTC « États-Unis et Canada » à la politique</span><span class="sxs-lookup"><span data-stu-id="85676-231">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="85676-232">Dans une session PowerShell dans Skype entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="85676-232">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="85676-233">Le résultat est affiché dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="85676-233">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="85676-234">Étape 4 : affecter la stratégie de routage téléphonique à un utilisateur nommé Spencer Low</span><span class="sxs-lookup"><span data-stu-id="85676-234">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="85676-235">Dans une session PowerShell dans Skype entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="85676-235">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="85676-236">Validez l’affectation de stratégie en entrant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="85676-236">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="85676-237">La commande renvoie ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="85676-237">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="85676-238">Exemple 2 : routage de la voix avec plusieurs utilisations RTC</span><span class="sxs-lookup"><span data-stu-id="85676-238">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="85676-239">La politique de routage vocale créée dans l’exemple 1 autorise uniquement les appels vers les numéros de téléphone aux États-Unis et au Canada, sauf si la licence de plan d’appel Microsoft est également affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="85676-239">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="85676-240">Dans l’exemple qui suit, vous pouvez créer la stratégie de routage vocale « sans restrictions ».</span><span class="sxs-lookup"><span data-stu-id="85676-240">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="85676-241">La stratégie réutilise l’utilisation RTC « États-Unis et Canada » créée dans l’exemple 1, ainsi que la nouvelle utilisation RTC « internationale ».</span><span class="sxs-lookup"><span data-stu-id="85676-241">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="85676-242">Cette stratégie route tous les autres appels vers l’SBCs sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="85676-242">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="85676-243">Les exemples qui s’affichent affectent la politique américaine uniquement à l’utilisateur Beaune Low et la stratégie no restrictions à l’utilisateur Jean Martin de sorte que le routage se déroule comme suit :</span><span class="sxs-lookup"><span data-stu-id="85676-243">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="85676-244">Beaune : politique de niveau faible-américaine uniquement.</span><span class="sxs-lookup"><span data-stu-id="85676-244">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="85676-245">Les appels ne sont admis qu’aux États-Unis et au Canada.</span><span class="sxs-lookup"><span data-stu-id="85676-245">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="85676-246">Lorsque vous appelez la plage de numéros Redmond, l’ensemble spécifique de SBCs doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="85676-246">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="85676-247">Les numéros non US ne seront pas routés sauf si la licence de plan d’appel est affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="85676-247">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="85676-248">Jean bois-politique internationale.</span><span class="sxs-lookup"><span data-stu-id="85676-248">John Woods – International policy.</span></span>  <span data-ttu-id="85676-249">Les appels sont autorisés à n’importe quel numéro.</span><span class="sxs-lookup"><span data-stu-id="85676-249">Calls are allowed to any number.</span></span> <span data-ttu-id="85676-250">Lorsque vous appelez la plage de numéros Redmond, l’ensemble spécifique de SBCs doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="85676-250">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="85676-251">Les numéros non US seront routés à l’aide de sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="85676-251">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Affiche la politique de routage vocale affectée à l’utilisateur Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="85676-253">Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), un itinéraire automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="85676-253">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="85676-254">S’il n’y a aucun résultat correspondant aux modèles de chiffres dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé à l’aide d’un forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85676-254">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="85676-255">Si l’utilisateur dispose uniquement du système Microsoft Phone, l’appel est abandonné, car aucune règle de correspondance n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="85676-255">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Politique de routage de la voix attribuée à l’utilisateur Jean bois](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="85676-257">Le tableau suivant récapitule les concepteurs d’utilisation et les itinéraires vocaux de la stratégie de routage « aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="85676-257">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="85676-258">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="85676-258">**PSTN usage**</span></span>|<span data-ttu-id="85676-259">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="85676-259">**Voice route**</span></span>|<span data-ttu-id="85676-260">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="85676-260">**Number pattern**</span></span>|<span data-ttu-id="85676-261">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="85676-261">**Priority**</span></span>|<span data-ttu-id="85676-262">**SBC**</span><span class="sxs-lookup"><span data-stu-id="85676-262">**SBC**</span></span>|<span data-ttu-id="85676-263">**Description**</span><span class="sxs-lookup"><span data-stu-id="85676-263">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="85676-264">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="85676-264">US and Canada</span></span>|<span data-ttu-id="85676-265">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="85676-265">"Redmond 1"</span></span>|<span data-ttu-id="85676-266">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="85676-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="85676-267">1</span><span class="sxs-lookup"><span data-stu-id="85676-267">1</span></span>|<span data-ttu-id="85676-268">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-268">sbc1.contoso.biz</span></span><br/><span data-ttu-id="85676-269">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-269">sbc2.contoso.biz</span></span>|<span data-ttu-id="85676-270">Itinéraire actif pour les numéros d’appelant + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="85676-270">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="85676-271">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="85676-271">US and Canada</span></span>|<span data-ttu-id="85676-272">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="85676-272">"Redmond 2"</span></span>|<span data-ttu-id="85676-273">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="85676-273">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="85676-274">2</span><span class="sxs-lookup"><span data-stu-id="85676-274">2</span></span>|<span data-ttu-id="85676-275">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-275">sbc3.contoso.biz</span></span><br/><span data-ttu-id="85676-276">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-276">sbc4.contoso.biz</span></span>|<span data-ttu-id="85676-277">Itinéraire de sauvegarde pour les numéros des appelants + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="85676-277">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="85676-278">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="85676-278">US and Canada</span></span>|<span data-ttu-id="85676-279">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="85676-279">"Other +1"</span></span>|<span data-ttu-id="85676-280">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="85676-280">^\\+1(\d{10})$</span></span>|<span data-ttu-id="85676-281">3</span><span class="sxs-lookup"><span data-stu-id="85676-281">3</span></span>|<span data-ttu-id="85676-282">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-282">sbc5.contoso.biz</span></span><br/><span data-ttu-id="85676-283">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-283">sbc6.contoso.biz</span></span>|<span data-ttu-id="85676-284">Itinéraire pour les numéros d’appelant + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="85676-284">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="85676-285">International</span><span class="sxs-lookup"><span data-stu-id="85676-285">International</span></span>|<span data-ttu-id="85676-286">International</span><span class="sxs-lookup"><span data-stu-id="85676-286">International</span></span>|<span data-ttu-id="85676-287">\d +</span><span class="sxs-lookup"><span data-stu-id="85676-287">\d+</span></span>|<span data-ttu-id="85676-288">4</span><span class="sxs-lookup"><span data-stu-id="85676-288">4</span></span>|<span data-ttu-id="85676-289">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-289">sbc2.contoso.biz</span></span><br/><span data-ttu-id="85676-290">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="85676-290">sbc5.contoso.biz</span></span>|<span data-ttu-id="85676-291">Itinéraire pour n’importe quel modèle numérique</span><span class="sxs-lookup"><span data-stu-id="85676-291">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="85676-292">L’ordre des utilisations RTC dans les stratégies de routage vocale est essentiel.</span><span class="sxs-lookup"><span data-stu-id="85676-292">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="85676-293">Les utilisations sont appliquées dans l’ordre et, si une correspondance est trouvée dans la première utilisation, les autres utilisations ne sont jamais évaluées.</span><span class="sxs-lookup"><span data-stu-id="85676-293">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="85676-294">L’utilisation RTC internationale doit être placée après l’utilisation du RTC des États-Unis et du Canada.</span><span class="sxs-lookup"><span data-stu-id="85676-294">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="85676-295">Pour modifier l’ordre des utilisations RTC, exécutez la `Set-CSOnlineVoiceRoutingPolicy` commande.</span><span class="sxs-lookup"><span data-stu-id="85676-295">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="85676-296">Par exemple, pour passer de l’ordre « États-Unis et Canada » et inversement, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="85676-296">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="85676-297">Le niveau de priorité des itinéraires vocaux « Other + 1 » et « international » est automatiquement attribué.</span><span class="sxs-lookup"><span data-stu-id="85676-297">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="85676-298">Il n’y a pas d’importance tant qu’il dispose de priorités inférieures à « Redmond 1 » et « Redmond 2 ».</span><span class="sxs-lookup"><span data-stu-id="85676-298">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="85676-299">Exemple 2 : étapes de configuration</span><span class="sxs-lookup"><span data-stu-id="85676-299">Example 2: Configuration steps</span></span>

<span data-ttu-id="85676-300">L’exemple suivant montre comment :</span><span class="sxs-lookup"><span data-stu-id="85676-300">The following example shows how to:</span></span>

1. <span data-ttu-id="85676-301">Créer une nouvelle utilisation RTC appelée international.</span><span class="sxs-lookup"><span data-stu-id="85676-301">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="85676-302">Créer un nouvel itinéraire vocal appelé international.</span><span class="sxs-lookup"><span data-stu-id="85676-302">Create a new voice route called International.</span></span>
3. <span data-ttu-id="85676-303">Création d’une stratégie de routage de la voix sans restrictions.</span><span class="sxs-lookup"><span data-stu-id="85676-303">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="85676-304">Affectez la stratégie à l’utilisateur Jean bois.</span><span class="sxs-lookup"><span data-stu-id="85676-304">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="85676-305">Vous pouvez utiliser le [Centre d’administration Microsoft teams](#admincenterexample2) ou [PowerShell](#powershellexample2) pour effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="85676-305">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="85676-306">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85676-306">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="85676-307">Étape 1 : créer une utilisation RTC internationale</span><span class="sxs-lookup"><span data-stu-id="85676-307">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="85676-308">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice** Teams,  >  **Direct Routing** sélectionnez **gérer les enregistrements d’utilisation RTC** dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="85676-308">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="85676-309">Cliquez sur **Ajouter**, tapez **international**, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="85676-309">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="85676-310">Étape 2 : créer l’itinéraire vocal « international »</span><span class="sxs-lookup"><span data-stu-id="85676-310">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="85676-311">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice** Teams, accédez à  >  **routage direct** de la voix, puis sélectionnez l’onglet **itinéraires vocaux** .</span><span class="sxs-lookup"><span data-stu-id="85676-311">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="85676-312">Cliquez sur **Ajouter**, entrez « international » comme nom, puis ajoutez la description.</span><span class="sxs-lookup"><span data-stu-id="85676-312">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="85676-313">Définissez la priorité sur 4, puis définissez le modèle de numérotation numérique sur \d +.</span><span class="sxs-lookup"><span data-stu-id="85676-313">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="85676-314">Sous **SBCS inscrits (facultatifs)**, cliquez sur **Ajouter sbcs**, sélectionnez sbc2.contoso.biz et sbc5.contoso.biz, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="85676-314">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="85676-315">Sous **enregistrements d’utilisation RTC (facultatif)**, cliquez sur **Ajouter l’utilisation RTC**, sélectionnez l’enregistrement d’utilisation RTC « international », puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="85676-315">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="85676-316">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="85676-316">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="85676-317">Étape 3 : création d’une stratégie de routage téléphonique nommée « aucune restriction » et ajout des utilisations RTC « États-Unis et Canada » et « internationales » à la politique</span><span class="sxs-lookup"><span data-stu-id="85676-317">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="85676-318">L’utilisation RTC « États-Unis et Canada » est réutilisée dans cette politique de routage vocal pour garantir une gestion spéciale des appels vers le numéro « + 1 425 XXX XX XX » et « + 1 206 XXX XX XX » en tant qu’appels locaux ou locaux.</span><span class="sxs-lookup"><span data-stu-id="85676-318">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="85676-319">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à** stratégies de routage de voix vocales, puis  >  **Voice routing policies** cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="85676-319">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="85676-320">Tapez **aucune restriction** pour le nom et ajoutez une description.</span><span class="sxs-lookup"><span data-stu-id="85676-320">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="85676-321">Sous **rapports d’utilisation RTC**, cliquez sur **Ajouter une utilisation PSTN**, sélectionnez l’enregistrement d’utilisation RTC « États-Unis et Canada », puis sélectionnez l’enregistrement d’utilisation RTC « international ».</span><span class="sxs-lookup"><span data-stu-id="85676-321">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="85676-322">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="85676-322">Click **Apply**.</span></span>

    <span data-ttu-id="85676-323">Prenez note de l’ordre des utilisations RTC :</span><span class="sxs-lookup"><span data-stu-id="85676-323">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="85676-324">Si un appel a été effectué pour le numéro « + 1 425 XXX XX XX » avec les utilisations configurées comme dans cet exemple, l’appel suit le routage défini au niveau de l’utilisation des États-Unis et du Canada et la logique de routage spécial est appliquée.</span><span class="sxs-lookup"><span data-stu-id="85676-324">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="85676-325">C’est la première fois que l’appel est routé à l’aide de sbc1.contoso.biz et sbc2.contoso.biz, puis de sbc3.contoso.biz et d’sbc4.contoso.biz de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="85676-325">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="85676-326">S’il s’agit d’une utilisation PSTN « internationale », les appels vers + 1 425 XXX XX XX sont routés vers sbc2.contoso.biz et sbc5.contoso.biz dans le cadre de la logique de routage.</span><span class="sxs-lookup"><span data-stu-id="85676-326">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="85676-327">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="85676-327">Click **Save**.</span></span>

<span data-ttu-id="85676-328">Pour en savoir plus, voir [gérer les stratégies de routage de messagerie vocale](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="85676-328">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="85676-329">Étape 4 : affecter la politique de routage téléphonique à un utilisateur intitulé Jean bois</span><span class="sxs-lookup"><span data-stu-id="85676-329">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="85676-330">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="85676-330">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="85676-331">Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="85676-331">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="85676-332">Sous **politique de routage** de la voix, sélectionnez la stratégie « aucune restriction », puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="85676-332">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="85676-333">Le résultat est que la stratégie vocale appliquée aux appels de Jean-Martin n’est pas restreinte et qu’elle respecte la logique du routage des appels disponible aux États-Unis, au Canada et au service d’appels internationaux.</span><span class="sxs-lookup"><span data-stu-id="85676-333">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="85676-334">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="85676-334">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="85676-335">Étape 1 : créer une utilisation RTC internationale</span><span class="sxs-lookup"><span data-stu-id="85676-335">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="85676-336">Dans une session PowerShell distante dans Skype entreprise Online, entrez :</span><span class="sxs-lookup"><span data-stu-id="85676-336">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="85676-337">Étape 2 : créer un nouvel itinéraire vocal nommé « international »</span><span class="sxs-lookup"><span data-stu-id="85676-337">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="85676-338">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="85676-338">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="85676-339">Étape 3 : création d’une stratégie de routage téléphonique nommée « aucune restriction »</span><span class="sxs-lookup"><span data-stu-id="85676-339">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="85676-340">L’utilisation RTC « Redmond 1 » et « Redmond » sont réutilisées dans cette politique de routage vocale pour garantir une gestion spéciale des appels au numéro « + 1 425 XXX XX XX » et « + 1 206 XXX XX XX » en tant qu’appels locaux ou locaux.</span><span class="sxs-lookup"><span data-stu-id="85676-340">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="85676-341">Prenez note de l’ordre des utilisations RTC :</span><span class="sxs-lookup"><span data-stu-id="85676-341">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="85676-342">Si un appel a été effectué pour le numéro « + 1 425 XXX XX XX » avec les utilisations configurées comme dans l’exemple suivant, l’appel suit le routage défini dans utilisation des États-Unis et du Canada et la logique de routage spécial est appliquée.</span><span class="sxs-lookup"><span data-stu-id="85676-342">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="85676-343">C’est la première fois que l’appel est routé à l’aide de sbc1.contoso.biz et sbc2.contoso.biz, puis de sbc3.contoso.biz et d’sbc4.contoso.biz de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="85676-343">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="85676-344">S’il s’agit d’une utilisation PSTN « internationale », les appels vers + 1 425 XXX XX XX sont routés vers sbc2.contoso.biz et sbc5.contoso.biz dans le cadre de la logique de routage.</span><span class="sxs-lookup"><span data-stu-id="85676-344">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="85676-345">Entrez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="85676-345">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="85676-346">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="85676-346">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="85676-347">Étape 4 : affecter la politique de routage de voix à l’utilisateur nommé Jean bois</span><span class="sxs-lookup"><span data-stu-id="85676-347">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="85676-348">Vérifiez ensuite le devoir à l’aide de la commande :</span><span class="sxs-lookup"><span data-stu-id="85676-348">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="85676-349">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="85676-349">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="85676-350">Le résultat est que la stratégie vocale appliquée aux appels de Jean-Martin n’est pas restreinte et qu’elle respecte la logique du routage des appels disponible aux États-Unis, au Canada et au service d’appels internationaux.</span><span class="sxs-lookup"><span data-stu-id="85676-350">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="85676-351">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85676-351">See also</span></span>

[<span data-ttu-id="85676-352">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="85676-352">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="85676-353">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="85676-353">Configure Direct Routing</span></span>](direct-routing-configure.md)
