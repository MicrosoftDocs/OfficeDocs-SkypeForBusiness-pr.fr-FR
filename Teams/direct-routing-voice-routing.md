---
title: Configurer le routage vocal pour le routage direct
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
description: Découvrez comment configurer le routage vocal avec Téléphone Microsoft routage direct du système.
ms.openlocfilehash: 9330c3bf8200ed84fa9f7c534e794af887097b8d
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383978"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="b9846-103">Configurer le routage vocal pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="b9846-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="b9846-104">Cet article décrit comment configurer le routage vocal pour le Système téléphonique direct.</span><span class="sxs-lookup"><span data-stu-id="b9846-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="b9846-105">Voici l’étape 3 de la procédure de configuration du routage direct :</span><span class="sxs-lookup"><span data-stu-id="b9846-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="b9846-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="b9846-106">Step 1.</span></span> [<span data-ttu-id="b9846-107">Connecter SBC avec Téléphone Microsoft et valider la connexion</span><span class="sxs-lookup"><span data-stu-id="b9846-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="b9846-108">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="b9846-108">Step 2.</span></span> [<span data-ttu-id="b9846-109">Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="b9846-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="b9846-110">**Étape 3. Configurer le routage vocal** (cet article)</span><span class="sxs-lookup"><span data-stu-id="b9846-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="b9846-111">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="b9846-111">Step 4.</span></span> [<span data-ttu-id="b9846-112">Traduire des nombres dans un autre format</span><span class="sxs-lookup"><span data-stu-id="b9846-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="b9846-113">Pour plus d’informations sur les étapes requises pour configurer le routage direct, voir [Configurer le routage direct.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="b9846-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="b9846-114">Vue d’ensemble du routage vocal</span><span class="sxs-lookup"><span data-stu-id="b9846-114">Voice routing overview</span></span>

<span data-ttu-id="b9846-115">Téléphone Microsoft Le système possède un mécanisme de routage qui permet d’envoyer un appel vers un contrôleur de session en bordure spécifique (SBC) sur la base des données suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9846-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="b9846-116">Modèle de numéro appelé</span><span class="sxs-lookup"><span data-stu-id="b9846-116">The called number pattern</span></span> 
- <span data-ttu-id="b9846-117">Le schéma de numéro appelé ainsi que l’utilisateur spécifique qui effectue l’appel</span><span class="sxs-lookup"><span data-stu-id="b9846-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="b9846-118">Les SCS peuvent être désignés comme actifs et de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="b9846-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="b9846-119">Lorsque le SBC configuré comme actif n’est pas disponible pour un itinéraire d’appel spécifique, l’appel est alors acheminé vers un SBC de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="b9846-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="b9846-120">Le routage vocal est composé des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b9846-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="b9846-121">**Stratégie de routage voix** : conteneur pour les utilisations PSTN, qui peut être affecté à un utilisateur ou à plusieurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b9846-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="b9846-122">**Utilisations PSTN :** conteneur pour les itinéraires vocaux et les utilisations PSTN, qui peuvent être partagés dans différentes stratégies de routage voix.</span><span class="sxs-lookup"><span data-stu-id="b9846-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="b9846-123">**Itinéraires vocaux** : modèle de numéro et ensemble de passerelles RST en ligne à utiliser pour les appels pour lequel le numéro d’appel correspond à ce modèle.</span><span class="sxs-lookup"><span data-stu-id="b9846-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="b9846-124">Passerelle **RTC** en ligne : pointeur sur un SBC qui stocke également la configuration qui est appliquée lorsqu’un appel est passé via SBC, telle que le forward P-Ed-Identity (XX) ou les codecs préférés ; peuvent être ajoutés aux itinéraires vocux.</span><span class="sxs-lookup"><span data-stu-id="b9846-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="b9846-125">Considérations sur la stratégie de routage voix</span><span class="sxs-lookup"><span data-stu-id="b9846-125">Voice routing policy considerations</span></span>

<span data-ttu-id="b9846-126">Si un utilisateur dispose d’une licence Forfait d’appels, les appels sortants de cet utilisateur sont automatiquement acheminés via l’infrastructure PSTN du plan d’appels Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9846-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="b9846-127">Si vous configurez et affectez une stratégie de routage vocal en ligne à un utilisateur du plan d’appels, les appels sortants de cet utilisateur sont vérifiés pour déterminer si le numéro à composer correspond à un modèle de numéro défini dans la stratégie de routage vocal en ligne.</span><span class="sxs-lookup"><span data-stu-id="b9846-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="b9846-128">En cas de correspondance, l’appel est routant via le ligne de routage direct.</span><span class="sxs-lookup"><span data-stu-id="b9846-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="b9846-129">S’il n’y a pas de correspondance, l’appel est acheminé via l’infrastructure PSTN du plan d’appel.</span><span class="sxs-lookup"><span data-stu-id="b9846-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="b9846-130">Si vous configurez et appliquez la stratégie de routage voix en ligne globale (à l’échelle de l’organisation) et l’appliquez, tous les utilisateurs à commande vocale de votre organisation hériteront de cette stratégie, ce qui peut entraîner le routage par inadvertance d’appels PSTN des utilisateurs du plan d’appel vers une ligne de routage direct.</span><span class="sxs-lookup"><span data-stu-id="b9846-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="b9846-131">Si vous ne souhaitez pas que tous les utilisateurs utilisent la stratégie globale de routage voix en ligne, configurez une stratégie personnalisée de routage vocal en ligne et affectez-la à des utilisateurs individuels à commande vocale.</span><span class="sxs-lookup"><span data-stu-id="b9846-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="b9846-132">Exemple 1 : routage vocal avec une utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="b9846-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="b9846-133">Le diagramme suivant montre deux exemples de stratégies de routage vocal dans un flux d’appels.</span><span class="sxs-lookup"><span data-stu-id="b9846-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="b9846-134">**Appeler Flow 1 (sur la gauche) :** Si un utilisateur appelle le +1 425 XXX XX XX ou le +1 206 XXX XX XX, l’appel est acheminé vers le sbc1.contoso.biz SBC ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="b9846-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="b9846-135">Si ni votre sbc1.contoso.biz ni sbc2.contoso.biz disponibles, l’appel est supprimé.</span><span class="sxs-lookup"><span data-stu-id="b9846-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="b9846-136">**Appeler Flow 2 (sur la droite) :** Si un utilisateur appelle le +1 425 XXX XX XX ou le +1 206 XXX XX XX, l’appel est d’abord acheminé vers le sbc1.contoso.biz SBC ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="b9846-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="b9846-137">Si aucun SBC n’est disponible, l’itinéraire à priorité inférieure est essayé (sbc3.contoso.biz et sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="b9846-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="b9846-138">Si aucun des SBCs n’est disponible, l’appel est supprimé.</span><span class="sxs-lookup"><span data-stu-id="b9846-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Exemples de stratégie de routage vocal](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="b9846-140">Dans les deux exemples, bien que des priorités soient affectées à la route vocale, les SBCS sur les itinéraires sont essayés dans un ordre aléatoire.</span><span class="sxs-lookup"><span data-stu-id="b9846-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b9846-141">À moins que l’utilisateur ne dispose également d’une licence Plan d’appels Microsoft, les appels vers n’importe quel nombre sauf les nombres correspondant aux modèles +1 425 XXX XX XX ou +1 206 XXX XX dans l’exemple de configuration sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="b9846-141">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="b9846-142">Si l’utilisateur dispose d’une licence Forfait d’appels, l’appel est automatiquement acheminé conformément aux stratégies du plan d’appels Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9846-142">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="b9846-143">Le plan d’appels Microsoft s’applique automatiquement comme dernier itinéraire à tous les utilisateurs titulaires de la licence Microsoft Calling Plan et ne nécessite pas de configuration de routage d’appel supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="b9846-143">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="b9846-144">Dans l’exemple illustré dans le diagramme suivant, une route vocale est ajoutée pour envoyer des appels à tous les autres numéros des États-Unis et du Canada (appels appelés modèle de numéro +1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="b9846-144">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Affiche la stratégie de routage vocal avec un troisième itinéraire](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="b9846-146">Pour tous les autres appels, si un utilisateur dispose des deux licences (Téléphone Microsoft Système et Microsoft Calling Plan), l’itinéraire automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="b9846-146">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="b9846-147">Si rien ne correspond aux modèles de numéro dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé via le plan d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9846-147">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="b9846-148">Si l’utilisateur dispose uniquement Téléphone Microsoft système informatique, l’appel est supprimé, car aucune règle de correspondance n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="b9846-148">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b9846-149">La valeur Priorité pour l’itinéraire « Autres +1 » n’a pas d’importance dans ce cas, car il n’existe qu’un seul itinéraire qui correspond au modèle +1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="b9846-149">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="b9846-150">Si un utilisateur appelle le +1 324 567 89 89 et que sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est supprimé.</span><span class="sxs-lookup"><span data-stu-id="b9846-150">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="b9846-151">Le tableau suivant récapitule la configuration à l’aide de trois itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="b9846-151">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="b9846-152">Dans cet exemple, les trois itinéraires font partie de la même utilisation PSTN, « États-Unis et Canada ».</span><span class="sxs-lookup"><span data-stu-id="b9846-152">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="b9846-153">Tous les itinéraires sont associés à l’utilisation PSTN « États-Unis et Canada », et l’utilisation PSTN est associée à la stratégie de routage voix « États-Unis uniquement ».</span><span class="sxs-lookup"><span data-stu-id="b9846-153">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="b9846-154">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="b9846-154">**PSTN usage**</span></span>|<span data-ttu-id="b9846-155">**Itinéraire vocal**</span><span class="sxs-lookup"><span data-stu-id="b9846-155">**Voice route**</span></span>|<span data-ttu-id="b9846-156">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="b9846-156">**Number pattern**</span></span>|<span data-ttu-id="b9846-157">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="b9846-157">**Priority**</span></span>|<span data-ttu-id="b9846-158">**SBC**</span><span class="sxs-lookup"><span data-stu-id="b9846-158">**SBC**</span></span>|<span data-ttu-id="b9846-159">**Description**</span><span class="sxs-lookup"><span data-stu-id="b9846-159">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b9846-160">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="b9846-160">US and Canada</span></span>|<span data-ttu-id="b9846-161">« Redmond 1 »</span><span class="sxs-lookup"><span data-stu-id="b9846-161">"Redmond 1"</span></span>|<span data-ttu-id="b9846-162">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="b9846-162">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="b9846-163">1</span><span class="sxs-lookup"><span data-stu-id="b9846-163">1</span></span>|<span data-ttu-id="b9846-164">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-164">sbc1.contoso.biz</span></span><br/><span data-ttu-id="b9846-165">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-165">sbc2.contoso.biz</span></span>|<span data-ttu-id="b9846-166">Itinéraire actif pour les nombres +1 425 XXX XX XX ou +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="b9846-166">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="b9846-167">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="b9846-167">US and Canada</span></span>|<span data-ttu-id="b9846-168">« Redmond 2 »</span><span class="sxs-lookup"><span data-stu-id="b9846-168">"Redmond 2"</span></span>|<span data-ttu-id="b9846-169">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="b9846-169">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="b9846-170">2</span><span class="sxs-lookup"><span data-stu-id="b9846-170">2</span></span>|<span data-ttu-id="b9846-171">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-171">sbc3.contoso.biz</span></span><br/><span data-ttu-id="b9846-172">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-172">sbc4.contoso.biz</span></span>|<span data-ttu-id="b9846-173">Itinéraire de sauvegarde pour les numéros +1 425 XXX XX XX ou +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="b9846-173">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="b9846-174">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="b9846-174">US and Canada</span></span>|<span data-ttu-id="b9846-175">« Autre +1 »</span><span class="sxs-lookup"><span data-stu-id="b9846-175">"Other +1"</span></span>|<span data-ttu-id="b9846-176">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="b9846-176">^\\+1(\d{10})$</span></span>|<span data-ttu-id="b9846-177">3</span><span class="sxs-lookup"><span data-stu-id="b9846-177">3</span></span>|<span data-ttu-id="b9846-178">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-178">sbc5.contoso.biz</span></span><br/><span data-ttu-id="b9846-179">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-179">sbc6.contoso.biz</span></span>|<span data-ttu-id="b9846-180">Route pour les numéros appelés +1 XXX XXX XX XX (sauf +1 425 XXX XX XX ou +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="b9846-180">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="b9846-181">Exemple 1 : étapes de configuration</span><span class="sxs-lookup"><span data-stu-id="b9846-181">Example 1: Configuration steps</span></span>

<span data-ttu-id="b9846-182">L’exemple suivant montre comment :</span><span class="sxs-lookup"><span data-stu-id="b9846-182">The following example shows how to:</span></span>

1. <span data-ttu-id="b9846-183">Créez une utilisation PSTN unique.</span><span class="sxs-lookup"><span data-stu-id="b9846-183">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="b9846-184">Configurez trois itinéraires vocables.</span><span class="sxs-lookup"><span data-stu-id="b9846-184">Configure three voice routes.</span></span>
3. <span data-ttu-id="b9846-185">Créer une stratégie de routage vocal.</span><span class="sxs-lookup"><span data-stu-id="b9846-185">Create a voice routing policy.</span></span>
4. <span data-ttu-id="b9846-186">Attribuez la stratégie à un utilisateur nommé Base.</span><span class="sxs-lookup"><span data-stu-id="b9846-186">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="b9846-187">Vous pouvez utiliser le [Microsoft Teams d’administration](#admincenterexample1) de l’utilisateur ou [PowerShell](#powershellexample1) pour effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="b9846-187">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b9846-188">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9846-188">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="b9846-189">Étape 1 : créer l’utilisation PSTN « États-Unis et Canada »</span><span class="sxs-lookup"><span data-stu-id="b9846-189">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="b9846-190">Dans le panneau de navigation de gauche du Microsoft Teams d’administration, sélectionnez **Acheminement** direct de la voix, puis dans le coin supérieur droit, sélectionnez Gérer les enregistrements d’utilisation  >   **PSTN.**</span><span class="sxs-lookup"><span data-stu-id="b9846-190">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="b9846-191">Cliquez **sur Ajouter,** **tapez US et Canada,** puis cliquez **sur Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="b9846-191">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="b9846-192">Étape 2 : créer trois itinéraires vocux (Redmond 1, Redmond 2 et Autres +1)</span><span class="sxs-lookup"><span data-stu-id="b9846-192">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="b9846-193">Les étapes suivantes décrivent la création d’un itinéraire vocal.</span><span class="sxs-lookup"><span data-stu-id="b9846-193">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="b9846-194">Pour créer les trois itinéraires vocaux nommés Redmond 1, Redmond 2 et Autres +1 pour cet exemple, utilisez les paramètres indiqués dans la table précédente.</span><span class="sxs-lookup"><span data-stu-id="b9846-194">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="b9846-195">Dans le panneau de navigation de gauche Microsoft Teams d’administration, sélectionnez **l’onglet**  >  **Itinéraires** vocants. </span><span class="sxs-lookup"><span data-stu-id="b9846-195">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="b9846-196">Cliquez **sur** Ajouter, puis entrez un nom et une description pour l’itinéraire vocal.</span><span class="sxs-lookup"><span data-stu-id="b9846-196">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="b9846-197">Définissez la priorité et spécifiez le modèle de numérotation.</span><span class="sxs-lookup"><span data-stu-id="b9846-197">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="b9846-198">Pour inscrire un SBC sur l’itinéraire vocal, sous **SBCs inscrits (facultatif),** cliquez sur Ajouter des **SBC,** sélectionnez les SBC que vous voulez inscrire, puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="b9846-198">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="b9846-199">Pour ajouter des enregistrements d’utilisation PSTN, sous Enregistrements d’utilisation **PSTN (facultatif),** cliquez sur Ajouter une utilisation **PSTN,** sélectionnez les enregistrements PSTN que vous voulez ajouter, puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="b9846-199">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="b9846-200">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b9846-200">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="b9846-201">Étape 3 : créer une stratégie de routage vocal nommée « États-Unis uniquement » et ajouter l’utilisation PSTN « États-Unis et Canada » à la stratégie</span><span class="sxs-lookup"><span data-stu-id="b9846-201">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="b9846-202">Dans le panneau de navigation de gauche du Microsoft Teams d’administration, allez dans les stratégies de routage de **Voice**  >  **Voice,** puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="b9846-202">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="b9846-203">Tapez **US Only** as the name and add a description.</span><span class="sxs-lookup"><span data-stu-id="b9846-203">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="b9846-204">Sous **Enregistrements d’utilisation PSTN,** cliquez sur Ajouter une utilisation **PSTN,** sélectionnez l’enregistrement d’utilisation PSTN « États-Unis et Canada », puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="b9846-204">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="b9846-205">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b9846-205">Click **Save**.</span></span>

<span data-ttu-id="b9846-206">Pour plus d’informations, voir [Gérer les stratégies de routage vocal.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b9846-206">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="b9846-207">Étape 4 : attribuer la stratégie de routage vocal à un utilisateur nomméSSoin Low</span><span class="sxs-lookup"><span data-stu-id="b9846-207">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="b9846-208">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b9846-208">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="b9846-209">Cliquez **sur Stratégies,** puis, en côté **de Stratégies affectées,** cliquez **sur Modifier.**</span><span class="sxs-lookup"><span data-stu-id="b9846-209">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="b9846-210">Sous **La stratégie de routage voix,** sélectionnez la stratégie « États-Unis uniquement », puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="b9846-210">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="b9846-211">Pour plus d’informations, voir [Gérer les stratégies de routage vocal.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b9846-211">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b9846-212">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9846-212">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="b9846-213">Étape 1 : créer l’utilisation PSTN « États-Unis et Canada »</span><span class="sxs-lookup"><span data-stu-id="b9846-213">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="b9846-214">Dans une session PowerShell distante dans Skype Entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="b9846-214">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="b9846-215">Vérifiez que l’utilisation a été créée en entrant :</span><span class="sxs-lookup"><span data-stu-id="b9846-215">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="b9846-216">Ce qui renvoie une liste de noms qui peuvent être tronqués :</span><span class="sxs-lookup"><span data-stu-id="b9846-216">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="b9846-217">L’exemple suivant illustre le résultat de l’exécution de la commande PowerShell pour afficher des noms `(Get-CSOnlinePSTNUsage).usage` complets (non tronqués) :</span><span class="sxs-lookup"><span data-stu-id="b9846-217">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` PowerShell command to display full names (not truncated):</span></span>

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="b9846-218">Étape 2 : créer trois itinéraires vocux (Redmond 1, Redmond 2 et Autres +1)</span><span class="sxs-lookup"><span data-stu-id="b9846-218">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="b9846-219">Pour créer l’itinéraire « Redmond 1 », dans une session PowerShell Skype Entreprise Online, entrez :</span><span class="sxs-lookup"><span data-stu-id="b9846-219">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="b9846-220">Ce qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="b9846-220">Which returns:</span></span>

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

<span data-ttu-id="b9846-221">Pour créer l’itinéraire Redmond 2, entrez :</span><span class="sxs-lookup"><span data-stu-id="b9846-221">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="b9846-222">Pour créer l’itinéraire Autres +1, entrez :</span><span class="sxs-lookup"><span data-stu-id="b9846-222">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="b9846-223">Assurez-vous que votre expression régulière dans l’attribut NumberPattern est valide.</span><span class="sxs-lookup"><span data-stu-id="b9846-223">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="b9846-224">Vous pouvez la tester à l’aide de ce site web : [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="b9846-224">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="b9846-225">Dans certains cas, il est nécessaire de router tous les appels vers le même SBC. use -NumberPattern « .\* »</span><span class="sxs-lookup"><span data-stu-id="b9846-225">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="b9846-226">Routez tous les appels vers le même SBC.</span><span class="sxs-lookup"><span data-stu-id="b9846-226">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="b9846-227">Vérifiez que vous avez correctement configuré l’itinéraire en exécutant la commande PowerShell à l’aide des `Get-CSOnlineVoiceRoute` options présentées ci-après :</span><span class="sxs-lookup"><span data-stu-id="b9846-227">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="b9846-228">Ce qui doit renvoyer :</span><span class="sxs-lookup"><span data-stu-id="b9846-228">Which should return:</span></span>

```console
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
```

<span data-ttu-id="b9846-229">Dans l’exemple, la priorité 4 de l’itinéraire « Autres +1 » a été automatiquement attribuée.</span><span class="sxs-lookup"><span data-stu-id="b9846-229">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="b9846-230">Étape 3 : créer une stratégie de routage vocal nommée « États-Unis uniquement » et ajouter l’utilisation PSTN « États-Unis et Canada » à la stratégie</span><span class="sxs-lookup"><span data-stu-id="b9846-230">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="b9846-231">Dans une session PowerShell dans Skype Entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="b9846-231">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="b9846-232">Le résultat est affiché dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="b9846-232">The result is shown in this example:</span></span>

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="b9846-233">Étape 4 : attribuer la stratégie de routage vocal à un utilisateur nomméSSoin Low</span><span class="sxs-lookup"><span data-stu-id="b9846-233">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="b9846-234">Dans une session PowerShell dans Skype Entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="b9846-234">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="b9846-235">Validez l’affectation de stratégie en entrant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b9846-235">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="b9846-236">La commande renvoie les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9846-236">The command returns the following:</span></span>

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="b9846-237">Exemple 2 : routage vocal avec plusieurs utilisations PSTN</span><span class="sxs-lookup"><span data-stu-id="b9846-237">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="b9846-238">La stratégie de routage vocal créée dans l’exemple 1 autorise uniquement les appels vers des numéros de téléphone aux États-Unis et au Canada, sauf si la licence Du plan d’appels Microsoft est également affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b9846-238">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="b9846-239">Dans l’exemple suivant, vous pouvez créer la stratégie de routage vocal « Aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="b9846-239">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="b9846-240">La stratégie réutilise l’utilisation PSTN « États-Unis et Canada » créée dans l’exemple 1, ainsi que la nouvelle utilisation PSTN « international ».</span><span class="sxs-lookup"><span data-stu-id="b9846-240">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="b9846-241">Cette stratégie a route tous les autres appels vers les sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="b9846-241">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="b9846-242">Les exemples affichés attribuent la stratégie États-Unis uniquement à l’utilisateur Base Base et la stratégie Aucune restriction à l’utilisateur John Bois afin que le routage se produise comme suit :</span><span class="sxs-lookup"><span data-stu-id="b9846-242">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="b9846-243">Autant de choses dont le taux d’intérêt est faible pour les États-Unis uniquement.</span><span class="sxs-lookup"><span data-stu-id="b9846-243">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="b9846-244">Les appels sont autorisés uniquement vers les numéros des États-Unis et du Canada.</span><span class="sxs-lookup"><span data-stu-id="b9846-244">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="b9846-245">Lorsque vous appelez une plage de numéro de Redmond, l’ensemble spécifique de SBCs doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="b9846-245">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="b9846-246">Les numéros hors États-Unis ne seront acheminés que si la licence Forfait d’appels est affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b9846-246">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="b9846-247">John Bois – Politique internationale.</span><span class="sxs-lookup"><span data-stu-id="b9846-247">John Woods – International policy.</span></span>  <span data-ttu-id="b9846-248">Les appels sont autorisés sur n’importe quel numéro.</span><span class="sxs-lookup"><span data-stu-id="b9846-248">Calls are allowed to any number.</span></span> <span data-ttu-id="b9846-249">Lorsque vous appelez une plage de numéro de Redmond, l’ensemble spécifique de SBCs doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="b9846-249">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="b9846-250">Les numéros hors États-Unis seront acheminés à l’aide sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="b9846-250">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Affiche la stratégie de routage vocal attribuée à l’utilisateurSSoin Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="b9846-252">Pour tous les autres appels, si un utilisateur dispose des deux licences (Téléphone Microsoft Système et Microsoft Calling Plan), l’itinéraire automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="b9846-252">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="b9846-253">Si rien ne correspond aux modèles de numéro dans les itinéraires vocaux en ligne créés par l’administrateur, l’appel est acheminé à l’aide du plan d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9846-253">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="b9846-254">Si l’utilisateur n’Téléphone Microsoft système téléphonique, l’appel est supprimé, car aucune règle de correspondance n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="b9846-254">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Affiche la stratégie de routage vocal attribuée à l’utilisateur John Bois](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="b9846-256">Le tableau suivant récapitule les désignations d’utilisation et les itinéraires vocaux de la stratégie de routage « Aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="b9846-256">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

| <span data-ttu-id="b9846-257">Utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="b9846-257">PSTN usage</span></span> | <span data-ttu-id="b9846-258">Itinéraire vocal</span><span class="sxs-lookup"><span data-stu-id="b9846-258">Voice route</span></span> | <span data-ttu-id="b9846-259">Type de numéro</span><span class="sxs-lookup"><span data-stu-id="b9846-259">Number pattern</span></span> | <span data-ttu-id="b9846-260">Priority (Priorité)</span><span class="sxs-lookup"><span data-stu-id="b9846-260">Priority</span></span> | <span data-ttu-id="b9846-261">SBC</span><span class="sxs-lookup"><span data-stu-id="b9846-261">SBC</span></span> | <span data-ttu-id="b9846-262">Description</span><span class="sxs-lookup"><span data-stu-id="b9846-262">Description</span></span> |
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b9846-263">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="b9846-263">US and Canada</span></span>|<span data-ttu-id="b9846-264">« Redmond 1 »</span><span class="sxs-lookup"><span data-stu-id="b9846-264">"Redmond 1"</span></span>|<span data-ttu-id="b9846-265">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="b9846-265">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="b9846-266">1</span><span class="sxs-lookup"><span data-stu-id="b9846-266">1</span></span>|<span data-ttu-id="b9846-267">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-267">sbc1.contoso.biz</span></span><br/><span data-ttu-id="b9846-268">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-268">sbc2.contoso.biz</span></span>|<span data-ttu-id="b9846-269">Itinéraire actif pour les numéros de l’appelant +1 425 XXX XX XX ou +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="b9846-269">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="b9846-270">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="b9846-270">US and Canada</span></span>|<span data-ttu-id="b9846-271">« Redmond 2 »</span><span class="sxs-lookup"><span data-stu-id="b9846-271">"Redmond 2"</span></span>|<span data-ttu-id="b9846-272">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="b9846-272">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="b9846-273">2</span><span class="sxs-lookup"><span data-stu-id="b9846-273">2</span></span>|<span data-ttu-id="b9846-274">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-274">sbc3.contoso.biz</span></span><br/><span data-ttu-id="b9846-275">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-275">sbc4.contoso.biz</span></span>|<span data-ttu-id="b9846-276">Itinéraire de sauvegarde pour les numéros de l’appelant +1 425 XXX XX XX ou +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="b9846-276">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="b9846-277">États-Unis et Canada</span><span class="sxs-lookup"><span data-stu-id="b9846-277">US and Canada</span></span>|<span data-ttu-id="b9846-278">« Autre +1 »</span><span class="sxs-lookup"><span data-stu-id="b9846-278">"Other +1"</span></span>|<span data-ttu-id="b9846-279">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="b9846-279">^\\+1(\d{10})$</span></span>|<span data-ttu-id="b9846-280">3</span><span class="sxs-lookup"><span data-stu-id="b9846-280">3</span></span>|<span data-ttu-id="b9846-281">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-281">sbc5.contoso.biz</span></span><br/><span data-ttu-id="b9846-282">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-282">sbc6.contoso.biz</span></span>|<span data-ttu-id="b9846-283">Route pour les numéros de l’appelant +1 XXX XXX XX XX (sauf +1 425 XXX XX XX ou +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="b9846-283">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="b9846-284">International</span><span class="sxs-lookup"><span data-stu-id="b9846-284">International</span></span>|<span data-ttu-id="b9846-285">International</span><span class="sxs-lookup"><span data-stu-id="b9846-285">International</span></span>|<span data-ttu-id="b9846-286">\d+</span><span class="sxs-lookup"><span data-stu-id="b9846-286">\d+</span></span>|<span data-ttu-id="b9846-287">4</span><span class="sxs-lookup"><span data-stu-id="b9846-287">4</span></span>|<span data-ttu-id="b9846-288">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-288">sbc2.contoso.biz</span></span><br/><span data-ttu-id="b9846-289">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b9846-289">sbc5.contoso.biz</span></span>|<span data-ttu-id="b9846-290">Route pour n’importe quel modèle de numéro</span><span class="sxs-lookup"><span data-stu-id="b9846-290">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="b9846-291">L’ordre d’utilisation PSTN dans les stratégies de routage voix est essentiel.</span><span class="sxs-lookup"><span data-stu-id="b9846-291">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="b9846-292">Les utilisations sont appliquées dans l’ordre, et si une correspondance est trouvée lors de la première utilisation, les autres utilisations ne sont jamais évaluées.</span><span class="sxs-lookup"><span data-stu-id="b9846-292">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="b9846-293">L’utilisation PSTN « international » doit être placée après l’utilisation PSTN « États-Unis et Canada ».</span><span class="sxs-lookup"><span data-stu-id="b9846-293">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="b9846-294">Pour modifier l’ordre des utilisations PSTN, exécutez la `Set-CSOnlineVoiceRoutingPolicy` commande.</span><span class="sxs-lookup"><span data-stu-id="b9846-294">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="b9846-295">Par exemple, pour modifier la commande de « États-Unis et Canada » en premier et « International » en deuxième de la commande inverse, exécutez :</span><span class="sxs-lookup"><span data-stu-id="b9846-295">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="b9846-296">La priorité des itinéraires vocux « Autres +1 » et « Internationaux » est attribuée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="b9846-296">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="b9846-297">Peu importe s’ils ont des priorités inférieures à « Redmond 1 » et « Redmond 2 ».</span><span class="sxs-lookup"><span data-stu-id="b9846-297">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="b9846-298">Exemple 2 : étapes de configuration</span><span class="sxs-lookup"><span data-stu-id="b9846-298">Example 2: Configuration steps</span></span>

<span data-ttu-id="b9846-299">L’exemple suivant montre comment :</span><span class="sxs-lookup"><span data-stu-id="b9846-299">The following example shows how to:</span></span>

1. <span data-ttu-id="b9846-300">Créez une utilisation RSTN appelée International.</span><span class="sxs-lookup"><span data-stu-id="b9846-300">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="b9846-301">Créez une nouvelle ligne vocale appelée International.</span><span class="sxs-lookup"><span data-stu-id="b9846-301">Create a new voice route called International.</span></span>
3. <span data-ttu-id="b9846-302">Créez une stratégie de routage vocal nommée Aucune restriction.</span><span class="sxs-lookup"><span data-stu-id="b9846-302">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="b9846-303">Attribuez la stratégie à l’utilisateur John Boiss.</span><span class="sxs-lookup"><span data-stu-id="b9846-303">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="b9846-304">Vous pouvez utiliser le [Microsoft Teams d’administration](#admincenterexample2) de l’utilisateur ou [PowerShell](#powershellexample2) pour effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="b9846-304">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b9846-305">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9846-305">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="b9846-306">Étape 1 : créer l’utilisation PSTN « international »</span><span class="sxs-lookup"><span data-stu-id="b9846-306">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="b9846-307">Dans le panneau de navigation de gauche du Microsoft Teams d’administration, sélectionnez **Acheminement** direct de la voix, puis dans le coin supérieur droit, sélectionnez Gérer les enregistrements d’utilisation  >   **PSTN.**</span><span class="sxs-lookup"><span data-stu-id="b9846-307">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="b9846-308">Cliquez **sur Ajouter,** **tapez International,** puis cliquez **sur Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="b9846-308">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="b9846-309">Étape 2 : créer l’itinéraire vocal « International »</span><span class="sxs-lookup"><span data-stu-id="b9846-309">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="b9846-310">Dans le panneau de navigation de gauche Microsoft Teams d’administration, sélectionnez **l’onglet**  >  **Itinéraires** vocants. </span><span class="sxs-lookup"><span data-stu-id="b9846-310">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="b9846-311">Cliquez **sur** Ajouter, entrez « International » comme nom, puis ajoutez la description.</span><span class="sxs-lookup"><span data-stu-id="b9846-311">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="b9846-312">Définissez la priorité sur 4, puis définissez le modèle de numérotation sur \d+.</span><span class="sxs-lookup"><span data-stu-id="b9846-312">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="b9846-313">Sous **SBCs inscrits (facultatif),** cliquez sur Ajouter des **SCS,** sélectionnez sbc2.contoso.biz et sbc5.contoso.biz, puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="b9846-313">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="b9846-314">Sous **Enregistrements d’utilisation PSTN (facultatif),** cliquez sur Ajouter une utilisation **PSTN,** sélectionnez l’enregistrement d’utilisation PSTN « International », puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="b9846-314">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="b9846-315">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b9846-315">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="b9846-316">Étape 3 : créez une stratégie de routage vocal nommée « Aucune restriction » et ajoutez les utilisations PSTN « États-Unis et Canada » et « International » à la stratégie</span><span class="sxs-lookup"><span data-stu-id="b9846-316">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="b9846-317">L’utilisation PSTN « États-Unis et Canada » est réutilisée dans cette stratégie de routage vocal afin de préserver la gestion spéciale pour les appels au numéro « +1 425 XXX XX XX » et « +1 206 XXX XX XX » en tant qu’appels locaux ou locaux.</span><span class="sxs-lookup"><span data-stu-id="b9846-317">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="b9846-318">Dans le panneau de navigation de gauche du Microsoft Teams d’administration, allez dans les stratégies de routage de **Voice**  >  **Voice,** puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="b9846-318">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="b9846-319">Tapez **Le nom «** Aucune restriction » et ajoutez une description.</span><span class="sxs-lookup"><span data-stu-id="b9846-319">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="b9846-320">Sous **Enregistrements d’utilisation PSTN,** cliquez sur Ajouter une utilisation **PSTN,** sélectionnez l’enregistrement d’utilisation PSTN « États-Unis et Canada », puis sélectionnez l’enregistrement d’utilisation PSTN « International ».</span><span class="sxs-lookup"><span data-stu-id="b9846-320">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="b9846-321">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="b9846-321">Click **Apply**.</span></span>

    <span data-ttu-id="b9846-322">Prenez note de l’ordre d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="b9846-322">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="b9846-323">Si un appel a été effectué sur le numéro « +1 425 XXX XX XX » avec les utilisations configurées comme dans cet exemple, l’appel suit l’itinéraire tracé dans l’utilisation des « États-Unis et Canada » et la logique de routage spéciale est appliquée.</span><span class="sxs-lookup"><span data-stu-id="b9846-323">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="b9846-324">Autrement dit, l’appel est acheminé d’abord à l’aide d sbc1.contoso.biz sbc2.contoso.biz puis en utilisant les itinéraires sbc3.contoso.biz et sbc4.contoso.biz les itinéraires de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="b9846-324">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="b9846-325">Si l’utilisation PSTN « international » est avant « États-Unis et Canada », les appels vers le +1 425 XXX XX XX sont acheminés vers sbc2.contoso.biz et sbc5.contoso.biz dans le cadre de la logique de routage.</span><span class="sxs-lookup"><span data-stu-id="b9846-325">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="b9846-326">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b9846-326">Click **Save**.</span></span>

<span data-ttu-id="b9846-327">Pour plus d’informations, voir [Gérer les stratégies de routage vocal.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b9846-327">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="b9846-328">Étape 4 : affecter la stratégie de routage vocal à un utilisateur nommé John Boiss</span><span class="sxs-lookup"><span data-stu-id="b9846-328">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="b9846-329">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b9846-329">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="b9846-330">Cliquez **sur Stratégies,** puis, en côté **de Stratégies affectées,** cliquez **sur Modifier.**</span><span class="sxs-lookup"><span data-stu-id="b9846-330">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="b9846-331">Sous **Stratégie de routage voix,** sélectionnez la stratégie « Aucune restriction », puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="b9846-331">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="b9846-332">Par conséquent, la stratégie vocale appliquée aux appels de John Calls n’est pas restreinte et suit la logique du routage des appels disponibles pour les appels aux États-Unis, au Canada et à l’international.</span><span class="sxs-lookup"><span data-stu-id="b9846-332">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b9846-333">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9846-333">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="b9846-334">Étape 1 : créer l’utilisation PSTN « international »</span><span class="sxs-lookup"><span data-stu-id="b9846-334">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="b9846-335">Dans une session PowerShell distante dans Skype Entreprise Online, entrez :</span><span class="sxs-lookup"><span data-stu-id="b9846-335">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="b9846-336">Étape 2 : créer une nouvelle route vocale nommée « International »</span><span class="sxs-lookup"><span data-stu-id="b9846-336">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

<span data-ttu-id="b9846-337">Ce qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="b9846-337">Which returns:</span></span>

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="b9846-338">Étape 3 : créer une stratégie de routage vocal nommée « Aucune restriction »</span><span class="sxs-lookup"><span data-stu-id="b9846-338">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="b9846-339">L’utilisation PSTN « Redmond 1 » et « Redmond » est réutilisée dans cette stratégie de routage vocal afin de préserver la gestion spéciale des appels pour le numéro « +1 425 XXX XX XX » et « +1 206 XXX XX XX » en tant qu’appels locaux ou locaux.</span><span class="sxs-lookup"><span data-stu-id="b9846-339">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="b9846-340">Prenez note de l’ordre d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="b9846-340">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="b9846-341">Si un appel a été effectué sur le numéro « +1 425 XXX XX XX » avec les utilisations configurées comme dans l’exemple suivant, l’appel suit l’itinéraire tracé dans l’utilisation des « États-Unis et Canada » et la logique de routage spéciale est appliquée.</span><span class="sxs-lookup"><span data-stu-id="b9846-341">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="b9846-342">Autrement dit, l’appel est acheminé d’abord à l’aide d sbc1.contoso.biz sbc2.contoso.biz puis en utilisant les itinéraires sbc3.contoso.biz et sbc4.contoso.biz les itinéraires de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="b9846-342">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="b9846-343">Si l’utilisation PSTN « international » est avant « États-Unis et Canada », les appels vers le +1 425 XXX XX XX sont acheminés vers sbc2.contoso.biz et sbc5.contoso.biz dans le cadre de la logique de routage.</span><span class="sxs-lookup"><span data-stu-id="b9846-343">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="b9846-344">Entrez la commande :</span><span class="sxs-lookup"><span data-stu-id="b9846-344">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="b9846-345">Ce qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="b9846-345">Which returns:</span></span>

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="b9846-346">Étape 4 : affecter la stratégie de routage vocal à l’utilisateur John Boiss</span><span class="sxs-lookup"><span data-stu-id="b9846-346">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="b9846-347">Vérifiez ensuite le devoir à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b9846-347">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="b9846-348">Ce qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="b9846-348">Which returns:</span></span>

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

<span data-ttu-id="b9846-349">Par conséquent, la stratégie vocale appliquée aux appels de John Bois n’est pas restreinte et suit la logique du routage des appels disponibles pour les appels aux États-Unis, au Canada et à l’international.</span><span class="sxs-lookup"><span data-stu-id="b9846-349">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9846-350">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9846-350">See also</span></span>

[<span data-ttu-id="b9846-351">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="b9846-351">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="b9846-352">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="b9846-352">Configure Direct Routing</span></span>](direct-routing-configure.md)
