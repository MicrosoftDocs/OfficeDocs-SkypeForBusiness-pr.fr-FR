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
ms.openlocfilehash: 0611684c79d92572ade41f2545096fe1d9bb4dd2
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159011"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="09520-103">Configurer le routage de la voix pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="09520-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="09520-104">Cet article décrit comment configurer le routage vocal pour le routage direct du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="09520-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="09520-105">Pour configurer le routage direct, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="09520-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="09520-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="09520-106">Step 1.</span></span> [<span data-ttu-id="09520-107">Connecter l’SBC avec un système Microsoft Phone et valider la connexion</span><span class="sxs-lookup"><span data-stu-id="09520-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="09520-108">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="09520-108">Step 2.</span></span> [<span data-ttu-id="09520-109">Permettre aux utilisateurs d’utiliser le routage direct, les appels vocaux et la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="09520-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="09520-110">**Étape 3. Configurer le routage** de la voix (cet article)</span><span class="sxs-lookup"><span data-stu-id="09520-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="09520-111">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="09520-111">Step 4.</span></span> [<span data-ttu-id="09520-112">Traduire des nombres dans un autre format</span><span class="sxs-lookup"><span data-stu-id="09520-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="09520-113">Pour plus d’informations sur la procédure de configuration du routage direct, voir [configurer le routage direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="09520-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="09520-114">Présentation du routage vocal</span><span class="sxs-lookup"><span data-stu-id="09520-114">Voice routing overview</span></span>

<span data-ttu-id="09520-115">Le système Microsoft Phone possède un mécanisme de routage qui permet d’envoyer un appel à un contrôleur de bordure de session spécifique (SBC) en fonction de :</span><span class="sxs-lookup"><span data-stu-id="09520-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="09520-116">Modèle de nombre appelé</span><span class="sxs-lookup"><span data-stu-id="09520-116">The called number pattern</span></span> 
- <span data-ttu-id="09520-117">Le modèle de numéro appelé et l’utilisateur spécifique qui effectue l’appel</span><span class="sxs-lookup"><span data-stu-id="09520-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="09520-118">SBCs peut être désignée comme active et Backup.</span><span class="sxs-lookup"><span data-stu-id="09520-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="09520-119">Lorsque l’SBC configuré comme étant actif n’est pas disponible pour un itinéraire d’appel spécifique, l’appel est acheminé vers un SBC de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="09520-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="09520-120">Le routage vocal est constitué des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="09520-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="09520-121">**Politique de routage** de la voix : conteneur des utilisations RTC qui peuvent être attribués à un utilisateur ou à plusieurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="09520-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="09520-122">**Usages PSTN** : conteneur pour les itinéraires vocaux et usages RTC, qui peuvent être partagés dans différentes politiques de routage vocal.</span><span class="sxs-lookup"><span data-stu-id="09520-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="09520-123">**Itinéraires vocaux** : un modèle numérique et un ensemble de passerelles RTC en ligne à utiliser pour les appels pour lesquels le numéro de téléphone correspond au modèle.</span><span class="sxs-lookup"><span data-stu-id="09520-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="09520-124">**Passerelle RTC en ligne** : pointeur vers une SBC qui stocke également la configuration appliquée lors du passage d’un appel par le biais de l’SBC, tel que l’envoi d’identité P-assertion (PAI) ou les codecs préférés. peuvent être ajoutés aux itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="09520-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="09520-125">Exemple 1 : routage de la voix avec une utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="09520-125">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="09520-126">Le schéma suivant montre deux exemples de stratégies de routage vocal dans un flux d’appels.</span><span class="sxs-lookup"><span data-stu-id="09520-126">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="09520-127">**Flux d’appels 1 (à gauche) :** Si un utilisateur effectue un appel vers + 1 425 XXX XX XX ou + 1 206 XXX XX XX, l’appel est acheminé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="09520-127">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="09520-128">Si les sbc1.contoso.biz et sbc2.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="09520-128">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="09520-129">**Flux d’appels 2 (sur la droite) :** Si un utilisateur effectue un appel vers + 1 425 XX XX XX ou + 1 206 XXX XX XX, l’appel est d’abord routé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="09520-129">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="09520-130">Si aucun SBC n’est disponible, l’itinéraire dont la priorité est faible est essayé (sbc3.contoso.biz et sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="09520-130">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="09520-131">Si aucune des SBCs n’est disponible, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="09520-131">If none of the SBCs are available, the call is dropped.</span></span> 

![Exemples de stratégies de routage vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="09520-133">Dans les deux exemples, si les priorités de l’itinéraire vocal sont affectées, les éléments SBCs dans les itinéraires sont essayés dans un ordre aléatoire.</span><span class="sxs-lookup"><span data-stu-id="09520-133">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="09520-134">À moins que l’utilisateur ne dispose d’une licence de plan d’appel Microsoft, les appels vers n’importe quel numéro, à l’exception des numéros correspondant aux modèles + 1 425 XXX XX XX ou + 1 206 XXX XX XX dans l’exemple de configuration sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="09520-134">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="09520-135">Si l’utilisateur dispose d’une licence de plan d’appel, l’appel est automatiquement acheminé conformément aux politiques du forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="09520-135">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="09520-136">Le plan d’appel Microsoft s’applique automatiquement en tant que dernier itinéraire à tous les utilisateurs dotés de la licence de plan d’appel Microsoft et ne nécessite pas de configuration du routage des appels supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="09520-136">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="09520-137">Dans l’exemple ci-dessous, un itinéraire est ajouté à l’adresse de l’expéditeur pour les appels vers tous les autres États-Unis et le Canada (appels vers un modèle de numéro + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="09520-137">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Affiche la politique de routage téléphonique avec un troisième itinéraire](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="09520-139">Pour tous les autres appels :</span><span class="sxs-lookup"><span data-stu-id="09520-139">For all other calls:</span></span>

- <span data-ttu-id="09520-140">Si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), le routage automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="09520-140">If a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> 
- <span data-ttu-id="09520-141">S’il n’y a aucun résultat correspondant aux modèles de nombre dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé par le biais du forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="09520-141">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span>
- <span data-ttu-id="09520-142">Si l’utilisateur dispose uniquement d’un système Microsoft Phone, l’appel est abandonné, car aucune règle correspondante n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="09520-142">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="09520-143">La valeur de priorité pour l’itinéraire « autres + 1 » n’a pas d’importance dans le cas du fait qu’il n’y a qu’un seul itinéraire qui correspond à la valeur du modèle + 1 XXX XX XX XX.</span><span class="sxs-lookup"><span data-stu-id="09520-143">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="09520-144">Si un utilisateur effectue un appel à + 1 324 567 89 89 et que les sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="09520-144">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="09520-145">Le tableau suivant résume la configuration à l’aide de trois itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="09520-145">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="09520-146">Dans cet exemple, les trois itinéraires font partie de la même utilisation PSTN, « États-Unis et Canada ».</span><span class="sxs-lookup"><span data-stu-id="09520-146">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="09520-147">Tous les itinéraires sont associés à l’utilisation RTC « États-Unis et Canada » et l’utilisation RTC est associée à la politique de routage téléphonique « États-Unis uniquement ».</span><span class="sxs-lookup"><span data-stu-id="09520-147">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="09520-148">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="09520-148">**PSTN usage**</span></span>|<span data-ttu-id="09520-149">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="09520-149">**Voice route**</span></span>|<span data-ttu-id="09520-150">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="09520-150">**Number pattern**</span></span>|<span data-ttu-id="09520-151">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="09520-151">**Priority**</span></span>|<span data-ttu-id="09520-152">**SBC**</span><span class="sxs-lookup"><span data-stu-id="09520-152">**SBC**</span></span>|<span data-ttu-id="09520-153">**Description**</span><span class="sxs-lookup"><span data-stu-id="09520-153">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09520-154">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="09520-154">US and Canada</span></span>|<span data-ttu-id="09520-155">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="09520-155">"Redmond 1"</span></span>|<span data-ttu-id="09520-156">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="09520-156">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="09520-157">1</span><span class="sxs-lookup"><span data-stu-id="09520-157">1</span></span>|<span data-ttu-id="09520-158">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-158">sbc1.contoso.biz</span></span><br/><span data-ttu-id="09520-159">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-159">sbc2.contoso.biz</span></span>|<span data-ttu-id="09520-160">Itinéraire actif pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="09520-160">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="09520-161">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="09520-161">US and Canada</span></span>|<span data-ttu-id="09520-162">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="09520-162">"Redmond 2"</span></span>|<span data-ttu-id="09520-163">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="09520-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="09520-164">2</span><span class="sxs-lookup"><span data-stu-id="09520-164">2</span></span>|<span data-ttu-id="09520-165">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-165">sbc3.contoso.biz</span></span><br/><span data-ttu-id="09520-166">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-166">sbc4.contoso.biz</span></span>|<span data-ttu-id="09520-167">Itinéraire de sauvegarde pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="09520-167">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="09520-168">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="09520-168">US and Canada</span></span>|<span data-ttu-id="09520-169">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="09520-169">"Other +1"</span></span>|<span data-ttu-id="09520-170">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="09520-170">^\\+1(\d{10})$</span></span>|<span data-ttu-id="09520-171">3</span><span class="sxs-lookup"><span data-stu-id="09520-171">3</span></span>|<span data-ttu-id="09520-172">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-172">sbc5.contoso.biz</span></span><br/><span data-ttu-id="09520-173">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-173">sbc6.contoso.biz</span></span>|<span data-ttu-id="09520-174">Itinéraire pour les numéros appelés + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="09520-174">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="09520-175">Exemple 1 : étapes de configuration</span><span class="sxs-lookup"><span data-stu-id="09520-175">Example 1: Configuration steps</span></span>

<span data-ttu-id="09520-176">L’exemple suivant montre comment :</span><span class="sxs-lookup"><span data-stu-id="09520-176">The following example shows how to:</span></span>

1. <span data-ttu-id="09520-177">Créez une utilisation PSTN unique.</span><span class="sxs-lookup"><span data-stu-id="09520-177">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="09520-178">Configurer trois itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="09520-178">Configure three voice routes.</span></span>
3. <span data-ttu-id="09520-179">Créer une stratégie de routage de la voix.</span><span class="sxs-lookup"><span data-stu-id="09520-179">Create a voice routing policy.</span></span>
4. <span data-ttu-id="09520-180">Affectez la stratégie à un utilisateur nommé Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="09520-180">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="09520-181">Vous pouvez utiliser le [Centre d’administration Microsoft teams](#admincenterexample1) ou [PowerShell](#powershellexample1) pour effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="09520-181">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="09520-182">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="09520-182">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="09520-183">Étape 1 : créer l’utilisation RTC des États-Unis et du Canada</span><span class="sxs-lookup"><span data-stu-id="09520-183">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="09520-184">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice** > **Teams, sélectionnez**gérer les enregistrements d' **utilisation RTC**dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="09520-184">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="09520-185">Cliquez sur **Ajouter**, tapez **États-Unis et Canada**, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="09520-185">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="09520-186">Étape 2 : créer trois itinéraires vocaux (Redmond 1, Redmond 2 et autres + 1)</span><span class="sxs-lookup"><span data-stu-id="09520-186">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="09520-187">Les étapes suivantes décrivent la création d’un itinéraire vocal.</span><span class="sxs-lookup"><span data-stu-id="09520-187">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="09520-188">Suivez ces étapes pour créer les trois itinéraires vocaux nommés Redmond 1, Redmond 2 et autres + 1 pour cet exemple en utilisant les paramètres définis dans le tableau précédent.</span><span class="sxs-lookup"><span data-stu-id="09520-188">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="09520-189">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**routage direct**de la **voix** > , puis sélectionnez l’onglet **itinéraires vocaux** .</span><span class="sxs-lookup"><span data-stu-id="09520-189">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="09520-190">Cliquez sur **Ajouter**, puis entrez le nom et la description de l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="09520-190">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="09520-191">Définissez la priorité et spécifiez le modèle de numéro numéroté.</span><span class="sxs-lookup"><span data-stu-id="09520-191">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="09520-192">Pour inscrire une SBC auprès de l’itinéraire de la voix, sous **SBCS inscrits (facultatif)**, cliquez sur **Ajouter SBCS**, sélectionnez le SBCS que vous voulez inscrire, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="09520-192">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="09520-193">Pour ajouter des enregistrements d’utilisation RTC, sous **enregistrements d’utilisation RTC (facultatif)**, cliquez sur **Ajouter une utilisation PSTN**, sélectionnez les enregistrements RTC que vous voulez ajouter, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="09520-193">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="09520-194">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="09520-194">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="09520-195">Étape 3 : créer une stratégie de routage de la voix nommée « États-Unis uniquement » et ajouter l’utilisation RTC « États-Unis et Canada » à la politique</span><span class="sxs-lookup"><span data-stu-id="09520-195">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="09520-196">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à** > **stratégies de routage de voix**vocales, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="09520-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="09520-197">Tapez **-nous uniquement** le nom et ajoutez une description.</span><span class="sxs-lookup"><span data-stu-id="09520-197">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="09520-198">Sous **rapports d’utilisation RTC**, cliquez sur **Ajouter une utilisation PSTN**, sélectionnez l’enregistrement d’utilisation RTC « États-Unis et Canada », puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="09520-198">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="09520-199">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="09520-199">Click **Save**.</span></span>

<span data-ttu-id="09520-200">Pour en savoir plus, voir [gérer les stratégies de routage de messagerie vocale](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="09520-200">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="09520-201">Étape 4 : affecter la stratégie de routage téléphonique à un utilisateur nommé Spencer Low</span><span class="sxs-lookup"><span data-stu-id="09520-201">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="09520-202">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="09520-202">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="09520-203">Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="09520-203">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="09520-204">Sous **politique de routage**de la voix, sélectionnez la stratégie « États-Unis uniquement », puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="09520-204">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="09520-205">Pour en savoir plus, voir [gérer les stratégies de routage de messagerie vocale](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="09520-205">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="09520-206">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="09520-206">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="09520-207">Étape 1 : créer l’utilisation RTC des États-Unis et du Canada</span><span class="sxs-lookup"><span data-stu-id="09520-207">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="09520-208">Dans une session PowerShell distante dans Skype entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="09520-208">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="09520-209">Vérifiez que l’utilisation a été créée en entrant :</span><span class="sxs-lookup"><span data-stu-id="09520-209">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="09520-210">Qui renvoie une liste de noms qui risquent d’être tronqués :</span><span class="sxs-lookup"><span data-stu-id="09520-210">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="09520-211">L’exemple suivant montre le résultat de l’exécution `(Get-CSOnlinePSTNUsage).usage` de la commande PowerShell pour afficher les noms complets (pas tronqués) :</span><span class="sxs-lookup"><span data-stu-id="09520-211">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="09520-212">Étape 2 : créer trois itinéraires vocaux (Redmond 1, Redmond 2 et autres + 1)</span><span class="sxs-lookup"><span data-stu-id="09520-212">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="09520-213">Pour créer l’itinéraire « Redmond 1 » dans une session PowerShell dans Skype entreprise Online, entrez :</span><span class="sxs-lookup"><span data-stu-id="09520-213">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="09520-214">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="09520-214">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="09520-215">Pour créer l’itinéraire de Redmond 2, entrez :</span><span class="sxs-lookup"><span data-stu-id="09520-215">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="09520-216">Pour créer l’autre itinéraire + 1, entrez :</span><span class="sxs-lookup"><span data-stu-id="09520-216">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="09520-217">Assurez-vous que votre expression régulière dans l’attribut NumberPattern est une expression valide.</span><span class="sxs-lookup"><span data-stu-id="09520-217">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="09520-218">Vous pouvez le tester à l’aide du site Web suivant :[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="09520-218">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="09520-219">Dans certains cas, il est nécessaire de router tous les appels vers le même SBC ; use-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="09520-219">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="09520-220">Acheminez tous les appels vers le même SBC.</span><span class="sxs-lookup"><span data-stu-id="09520-220">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="09520-221">Vérifiez que vous avez correctement configuré l’itinéraire en exécutant la `Get-CSOnlineVoiceRoute` commande PowerShell en utilisant les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="09520-221">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="09520-222">Qui doit retourner :</span><span class="sxs-lookup"><span data-stu-id="09520-222">Which should return:</span></span>
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

<span data-ttu-id="09520-223">Dans l’exemple, l’itinéraire « Other + 1 » a automatiquement la priorité 4.</span><span class="sxs-lookup"><span data-stu-id="09520-223">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="09520-224">Étape 3 : créer une stratégie de routage de la voix nommée « États-Unis uniquement » et ajouter l’utilisation RTC « États-Unis et Canada » à la politique</span><span class="sxs-lookup"><span data-stu-id="09520-224">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="09520-225">Dans une session PowerShell dans Skype entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="09520-225">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="09520-226">Le résultat est affiché dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="09520-226">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="09520-227">Étape 4 : affecter la stratégie de routage téléphonique à un utilisateur nommé Spencer Low</span><span class="sxs-lookup"><span data-stu-id="09520-227">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="09520-228">Dans une session PowerShell dans Skype entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="09520-228">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="09520-229">Validez l’affectation de stratégie en entrant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="09520-229">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="09520-230">La commande renvoie ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="09520-230">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="09520-231">Exemple 2 : routage de la voix avec plusieurs utilisations RTC</span><span class="sxs-lookup"><span data-stu-id="09520-231">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="09520-232">La politique de routage vocale créée dans l’exemple 1 autorise uniquement les appels vers les numéros de téléphone aux États-Unis et au Canada, sauf si la licence de plan d’appel Microsoft est également affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="09520-232">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="09520-233">Dans l’exemple qui suit, vous pouvez créer la stratégie de routage vocale « sans restrictions ».</span><span class="sxs-lookup"><span data-stu-id="09520-233">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="09520-234">La stratégie réutilise l’utilisation RTC « États-Unis et Canada » créée dans l’exemple 1, ainsi que la nouvelle utilisation RTC « internationale ».</span><span class="sxs-lookup"><span data-stu-id="09520-234">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="09520-235">Cette stratégie route tous les autres appels vers l’SBCs sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="09520-235">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="09520-236">Les exemples qui s’affichent affectent la politique américaine uniquement à l’utilisateur Beaune Low et la stratégie no restrictions à l’utilisateur Jean Martin de sorte que le routage se déroule comme suit :</span><span class="sxs-lookup"><span data-stu-id="09520-236">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="09520-237">Beaune : politique de niveau faible-américaine uniquement.</span><span class="sxs-lookup"><span data-stu-id="09520-237">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="09520-238">Les appels ne sont admis qu’aux États-Unis et au Canada.</span><span class="sxs-lookup"><span data-stu-id="09520-238">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="09520-239">Lorsque vous appelez la plage de numéros Redmond, l’ensemble spécifique de SBCs doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="09520-239">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="09520-240">Les numéros non US ne seront pas routés sauf si la licence de plan d’appel est affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="09520-240">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="09520-241">Jean bois-politique internationale.</span><span class="sxs-lookup"><span data-stu-id="09520-241">John Woods – International policy.</span></span>  <span data-ttu-id="09520-242">Les appels sont autorisés à n’importe quel numéro.</span><span class="sxs-lookup"><span data-stu-id="09520-242">Calls are allowed to any number.</span></span> <span data-ttu-id="09520-243">Lorsque vous appelez la plage de numéros Redmond, l’ensemble spécifique de SBCs doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="09520-243">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="09520-244">Les numéros non US seront routés à l’aide de sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="09520-244">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Affiche la politique de routage vocale affectée à l’utilisateur Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="09520-246">Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), un itinéraire automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="09520-246">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="09520-247">S’il n’y a aucun résultat correspondant aux modèles de chiffres dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé à l’aide d’un forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="09520-247">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="09520-248">Si l’utilisateur dispose uniquement du système Microsoft Phone, l’appel est abandonné, car aucune règle de correspondance n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="09520-248">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Politique de routage de la voix attribuée à l’utilisateur Jean bois](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="09520-250">Le tableau suivant récapitule les concepteurs d’utilisation et les itinéraires vocaux de la stratégie de routage « aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="09520-250">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="09520-251">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="09520-251">**PSTN usage**</span></span>|<span data-ttu-id="09520-252">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="09520-252">**Voice route**</span></span>|<span data-ttu-id="09520-253">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="09520-253">**Number pattern**</span></span>|<span data-ttu-id="09520-254">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="09520-254">**Priority**</span></span>|<span data-ttu-id="09520-255">**SBC**</span><span class="sxs-lookup"><span data-stu-id="09520-255">**SBC**</span></span>|<span data-ttu-id="09520-256">**Description**</span><span class="sxs-lookup"><span data-stu-id="09520-256">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09520-257">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="09520-257">US and Canada</span></span>|<span data-ttu-id="09520-258">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="09520-258">"Redmond 1"</span></span>|<span data-ttu-id="09520-259">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="09520-259">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="09520-260">1</span><span class="sxs-lookup"><span data-stu-id="09520-260">1</span></span>|<span data-ttu-id="09520-261">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-261">sbc1.contoso.biz</span></span><br/><span data-ttu-id="09520-262">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-262">sbc2.contoso.biz</span></span>|<span data-ttu-id="09520-263">Itinéraire actif pour les numéros d’appelant + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="09520-263">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="09520-264">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="09520-264">US and Canada</span></span>|<span data-ttu-id="09520-265">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="09520-265">"Redmond 2"</span></span>|<span data-ttu-id="09520-266">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="09520-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="09520-267">2</span><span class="sxs-lookup"><span data-stu-id="09520-267">2</span></span>|<span data-ttu-id="09520-268">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-268">sbc3.contoso.biz</span></span><br/><span data-ttu-id="09520-269">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-269">sbc4.contoso.biz</span></span>|<span data-ttu-id="09520-270">Itinéraire de sauvegarde pour les numéros des appelants + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="09520-270">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="09520-271">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="09520-271">US and Canada</span></span>|<span data-ttu-id="09520-272">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="09520-272">"Other +1"</span></span>|<span data-ttu-id="09520-273">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="09520-273">^\\+1(\d{10})$</span></span>|<span data-ttu-id="09520-274">3</span><span class="sxs-lookup"><span data-stu-id="09520-274">3</span></span>|<span data-ttu-id="09520-275">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-275">sbc5.contoso.biz</span></span><br/><span data-ttu-id="09520-276">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-276">sbc6.contoso.biz</span></span>|<span data-ttu-id="09520-277">Itinéraire pour les numéros d’appelant + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="09520-277">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="09520-278">International</span><span class="sxs-lookup"><span data-stu-id="09520-278">International</span></span>|<span data-ttu-id="09520-279">International</span><span class="sxs-lookup"><span data-stu-id="09520-279">International</span></span>|<span data-ttu-id="09520-280">\d +</span><span class="sxs-lookup"><span data-stu-id="09520-280">\d+</span></span>|<span data-ttu-id="09520-281">4</span><span class="sxs-lookup"><span data-stu-id="09520-281">4</span></span>|<span data-ttu-id="09520-282">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-282">sbc2.contoso.biz</span></span><br/><span data-ttu-id="09520-283">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="09520-283">sbc5.contoso.biz</span></span>|<span data-ttu-id="09520-284">Itinéraire pour n’importe quel modèle numérique</span><span class="sxs-lookup"><span data-stu-id="09520-284">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="09520-285">L’ordre des utilisations RTC dans les stratégies de routage vocale est essentiel.</span><span class="sxs-lookup"><span data-stu-id="09520-285">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="09520-286">Les utilisations sont appliquées dans l’ordre et, si une correspondance est trouvée dans la première utilisation, les autres utilisations ne sont jamais évaluées.</span><span class="sxs-lookup"><span data-stu-id="09520-286">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="09520-287">L’utilisation RTC internationale doit être placée après l’utilisation du RTC des États-Unis et du Canada.</span><span class="sxs-lookup"><span data-stu-id="09520-287">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="09520-288">Pour modifier l’ordre des utilisations RTC, exécutez la `Set-CSOnlineVoiceRoutingPolicy` commande.</span><span class="sxs-lookup"><span data-stu-id="09520-288">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="09520-289">Par exemple, pour passer de l’ordre « États-Unis et Canada » et inversement, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="09520-289">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="09520-290">Le niveau de priorité des itinéraires vocaux « Other + 1 » et « international » est automatiquement attribué.</span><span class="sxs-lookup"><span data-stu-id="09520-290">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="09520-291">Il n’y a pas d’importance tant qu’il dispose de priorités inférieures à « Redmond 1 » et « Redmond 2 ».</span><span class="sxs-lookup"><span data-stu-id="09520-291">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="09520-292">Exemple 2 : étapes de configuration</span><span class="sxs-lookup"><span data-stu-id="09520-292">Example 2: Configuration steps</span></span>

<span data-ttu-id="09520-293">L’exemple suivant montre comment :</span><span class="sxs-lookup"><span data-stu-id="09520-293">The following example shows how to:</span></span>

1. <span data-ttu-id="09520-294">Créer une nouvelle utilisation RTC appelée international.</span><span class="sxs-lookup"><span data-stu-id="09520-294">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="09520-295">Créer un nouvel itinéraire vocal appelé international.</span><span class="sxs-lookup"><span data-stu-id="09520-295">Create a new voice route called International.</span></span>
3. <span data-ttu-id="09520-296">Création d’une stratégie de routage de la voix sans restrictions.</span><span class="sxs-lookup"><span data-stu-id="09520-296">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="09520-297">Affectez la stratégie à l’utilisateur Jean bois.</span><span class="sxs-lookup"><span data-stu-id="09520-297">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="09520-298">Vous pouvez utiliser le [Centre d’administration Microsoft teams](#admincenterexample2) ou [PowerShell](#powershellexample2) pour effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="09520-298">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="09520-299">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="09520-299">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="09520-300">Étape 1 : créer une utilisation RTC internationale</span><span class="sxs-lookup"><span data-stu-id="09520-300">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="09520-301">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice** > **Teams, sélectionnez**gérer les enregistrements d' **utilisation RTC**dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="09520-301">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="09520-302">Cliquez sur **Ajouter**, tapez **international**, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="09520-302">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="09520-303">Étape 2 : créer l’itinéraire vocal « international »</span><span class="sxs-lookup"><span data-stu-id="09520-303">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="09520-304">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**routage direct**de la **voix** > , puis sélectionnez l’onglet **itinéraires vocaux** .</span><span class="sxs-lookup"><span data-stu-id="09520-304">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="09520-305">Cliquez sur **Ajouter**, entrez « international » comme nom, puis ajoutez la description.</span><span class="sxs-lookup"><span data-stu-id="09520-305">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="09520-306">Définissez la priorité sur 4, puis définissez le modèle de numérotation numérique sur \d +.</span><span class="sxs-lookup"><span data-stu-id="09520-306">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="09520-307">Sous **SBCS inscrits (facultatifs)**, cliquez sur **Ajouter sbcs**, sélectionnez sbc2.contoso.biz et sbc5.contoso.biz, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="09520-307">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="09520-308">Sous **enregistrements d’utilisation RTC (facultatif)**, cliquez sur **Ajouter l’utilisation RTC**, sélectionnez l’enregistrement d’utilisation RTC « international », puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="09520-308">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="09520-309">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="09520-309">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="09520-310">Étape 3 : création d’une stratégie de routage téléphonique nommée « aucune restriction » et ajout des utilisations RTC « États-Unis et Canada » et « internationales » à la politique</span><span class="sxs-lookup"><span data-stu-id="09520-310">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="09520-311">L’utilisation RTC « États-Unis et Canada » est réutilisée dans cette politique de routage vocal pour garantir une gestion spéciale des appels vers le numéro « + 1 425 XXX XX XX » et « + 1 206 XXX XX XX » en tant qu’appels locaux ou locaux.</span><span class="sxs-lookup"><span data-stu-id="09520-311">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="09520-312">Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à** > **stratégies de routage de voix**vocales, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="09520-312">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="09520-313">Tapez **aucune restriction** pour le nom et ajoutez une description.</span><span class="sxs-lookup"><span data-stu-id="09520-313">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="09520-314">Sous **rapports d’utilisation RTC**, cliquez sur **Ajouter une utilisation PSTN**, sélectionnez l’enregistrement d’utilisation RTC « États-Unis et Canada », puis sélectionnez l’enregistrement d’utilisation RTC « international ».</span><span class="sxs-lookup"><span data-stu-id="09520-314">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="09520-315">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="09520-315">Click **Apply**.</span></span>

    <span data-ttu-id="09520-316">Prenez note de l’ordre des utilisations RTC :</span><span class="sxs-lookup"><span data-stu-id="09520-316">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="09520-317">Si un appel a été effectué pour le numéro « + 1 425 XXX XX XX » avec les utilisations configurées comme dans cet exemple, l’appel suit le routage défini au niveau de l’utilisation des États-Unis et du Canada et la logique de routage spécial est appliquée.</span><span class="sxs-lookup"><span data-stu-id="09520-317">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="09520-318">C’est la première fois que l’appel est routé à l’aide de sbc1.contoso.biz et sbc2.contoso.biz, puis de sbc3.contoso.biz et d’sbc4.contoso.biz de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="09520-318">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="09520-319">S’il s’agit d’une utilisation PSTN « internationale », les appels vers + 1 425 XXX XX XX sont routés vers sbc2.contoso.biz et sbc5.contoso.biz dans le cadre de la logique de routage.</span><span class="sxs-lookup"><span data-stu-id="09520-319">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="09520-320">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="09520-320">Click **Save**.</span></span>

<span data-ttu-id="09520-321">Pour en savoir plus, voir [gérer les stratégies de routage de messagerie vocale](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="09520-321">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="09520-322">Étape 4 : affecter la politique de routage téléphonique à un utilisateur intitulé Jean bois</span><span class="sxs-lookup"><span data-stu-id="09520-322">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="09520-323">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="09520-323">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="09520-324">Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="09520-324">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="09520-325">Sous **politique de routage**de la voix, sélectionnez la stratégie « aucune restriction », puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="09520-325">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="09520-326">Le résultat est que la stratégie vocale appliquée aux appels de Jean-Martin n’est pas restreinte et qu’elle respecte la logique du routage des appels disponible aux États-Unis, au Canada et au service d’appels internationaux.</span><span class="sxs-lookup"><span data-stu-id="09520-326">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="09520-327">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="09520-327">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="09520-328">Étape 1 : créer une utilisation RTC internationale</span><span class="sxs-lookup"><span data-stu-id="09520-328">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="09520-329">Dans une session PowerShell distante dans Skype entreprise Online, entrez :</span><span class="sxs-lookup"><span data-stu-id="09520-329">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="09520-330">Étape 2 : créer un nouvel itinéraire vocal nommé « international »</span><span class="sxs-lookup"><span data-stu-id="09520-330">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="09520-331">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="09520-331">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="09520-332">Étape 3 : création d’une stratégie de routage téléphonique nommée « aucune restriction »</span><span class="sxs-lookup"><span data-stu-id="09520-332">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="09520-333">L’utilisation RTC « Redmond 1 » et « Redmond » sont réutilisées dans cette politique de routage vocale pour garantir une gestion spéciale des appels au numéro « + 1 425 XXX XX XX » et « + 1 206 XXX XX XX » en tant qu’appels locaux ou locaux.</span><span class="sxs-lookup"><span data-stu-id="09520-333">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="09520-334">Prenez note de l’ordre des utilisations RTC :</span><span class="sxs-lookup"><span data-stu-id="09520-334">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="09520-335">Si un appel a été effectué pour le numéro « + 1 425 XXX XX XX » avec les utilisations configurées comme dans l’exemple suivant, l’appel suit le routage défini dans utilisation des États-Unis et du Canada et la logique de routage spécial est appliquée.</span><span class="sxs-lookup"><span data-stu-id="09520-335">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="09520-336">C’est la première fois que l’appel est routé à l’aide de sbc1.contoso.biz et sbc2.contoso.biz, puis de sbc3.contoso.biz et d’sbc4.contoso.biz de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="09520-336">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="09520-337">S’il s’agit d’une utilisation PSTN « internationale », les appels vers + 1 425 XXX XX XX sont routés vers sbc2.contoso.biz et sbc5.contoso.biz dans le cadre de la logique de routage.</span><span class="sxs-lookup"><span data-stu-id="09520-337">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="09520-338">Entrez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="09520-338">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="09520-339">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="09520-339">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="09520-340">Étape 4 : affecter la politique de routage de voix à l’utilisateur nommé Jean bois</span><span class="sxs-lookup"><span data-stu-id="09520-340">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="09520-341">Vérifiez ensuite le devoir à l’aide de la commande :</span><span class="sxs-lookup"><span data-stu-id="09520-341">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="09520-342">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="09520-342">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="09520-343">Le résultat est que la stratégie vocale appliquée aux appels de Jean-Martin n’est pas restreinte et qu’elle respecte la logique du routage des appels disponible aux États-Unis, au Canada et au service d’appels internationaux.</span><span class="sxs-lookup"><span data-stu-id="09520-343">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="09520-344">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09520-344">See also</span></span>

[<span data-ttu-id="09520-345">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="09520-345">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="09520-346">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="09520-346">Configure Direct Routing</span></span>](direct-routing-configure.md)
