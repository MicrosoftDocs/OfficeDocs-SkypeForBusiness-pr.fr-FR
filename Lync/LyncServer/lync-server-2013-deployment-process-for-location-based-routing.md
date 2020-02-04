---
title: >
  Lync Server 2013 : Processus de déploiement du routage géodépendant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02e09106bc9d96fbfab2935aec07f3c472f49d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="bc289-102">Processus de déploiement du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc289-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc289-103">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="bc289-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="bc289-104">Cette rubrique fournit une vue d’ensemble du processus de configuration du routage par emplacement.</span><span class="sxs-lookup"><span data-stu-id="bc289-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="bc289-105">Vous devez déployer Lync Server Enterprise Edition ou Standard Edition avec Enterprise Voice avant de configurer le routage sur site.</span><span class="sxs-lookup"><span data-stu-id="bc289-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="bc289-106">Les composants requis par le routage de géolocalisation sont déjà installés et activés lors du déploiement d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="bc289-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="bc289-107">Processus de déploiement de routage en fonction de l’emplacement</span><span class="sxs-lookup"><span data-stu-id="bc289-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc289-108">Phase</span><span class="sxs-lookup"><span data-stu-id="bc289-108">Phase</span></span></th>
<th><span data-ttu-id="bc289-109">Étapes</span><span class="sxs-lookup"><span data-stu-id="bc289-109">Steps</span></span></th>
<th><span data-ttu-id="bc289-110">Groupes et rôles requis</span><span class="sxs-lookup"><span data-stu-id="bc289-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="bc289-111">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="bc289-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc289-112">Déploiement de Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="bc289-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bc289-113">Configurer des Trunks</span><span class="sxs-lookup"><span data-stu-id="bc289-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="bc289-114">Créer des stratégies vocales</span><span class="sxs-lookup"><span data-stu-id="bc289-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="bc289-115">Définir des itinéraires vocaux</span><span class="sxs-lookup"><span data-stu-id="bc289-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bc289-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="bc289-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="bc289-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc289-117">CsAdministrator</span></span><br />
<span data-ttu-id="bc289-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc289-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc289-119">Déploiement d’Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="bc289-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc289-120">Vérifier votre déploiement voix entreprise</span><span class="sxs-lookup"><span data-stu-id="bc289-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bc289-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="bc289-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="bc289-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc289-122">CsAdministrator</span></span><br />
<span data-ttu-id="bc289-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc289-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc289-124">Configurer des zones, des sites et des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="bc289-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bc289-125">Créer des régions réseau</span><span class="sxs-lookup"><span data-stu-id="bc289-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="bc289-126">Créer des sites réseau</span><span class="sxs-lookup"><span data-stu-id="bc289-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="bc289-127">Associe des sous-réseaux aux sites réseau</span><span class="sxs-lookup"><span data-stu-id="bc289-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bc289-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="bc289-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="bc289-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc289-129">CsAdministrator</span></span><br />
<span data-ttu-id="bc289-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc289-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc289-131">À propos des zones, des sites et des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="bc289-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="bc289-132">Créer ou modifier une région de réseau</span><span class="sxs-lookup"><span data-stu-id="bc289-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="bc289-133">Créer ou modifier un site réseau</span><span class="sxs-lookup"><span data-stu-id="bc289-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="bc289-134">Associer un sous-réseau à un site réseau</span><span class="sxs-lookup"><span data-stu-id="bc289-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc289-135">Configurer le routage par emplacement</span><span class="sxs-lookup"><span data-stu-id="bc289-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bc289-136">Créer des stratégies de routage de la voix</span><span class="sxs-lookup"><span data-stu-id="bc289-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="bc289-137">Définir une configuration de Trunk séparée par Trunk</span><span class="sxs-lookup"><span data-stu-id="bc289-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="bc289-138">Modifier les stratégies vocales</span><span class="sxs-lookup"><span data-stu-id="bc289-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="bc289-139">Activer la configuration de routage basée sur l’emplacement</span><span class="sxs-lookup"><span data-stu-id="bc289-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bc289-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="bc289-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="bc289-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc289-141">CsAdministrator</span></span><br />
<span data-ttu-id="bc289-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc289-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="bc289-143">Exemple de déploiement</span><span class="sxs-lookup"><span data-stu-id="bc289-143">Sample Deployment</span></span>

<span data-ttu-id="bc289-144">Le déploiement suivant est utilisé pour illustrer davantage les mécanismes activés par le routage géolocalisation.</span><span class="sxs-lookup"><span data-stu-id="bc289-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="bc289-145">![e1bd2230-44DA-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44DA-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="bc289-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="bc289-146">Appels RTC entrants</span><span class="sxs-lookup"><span data-stu-id="bc289-146">Incoming PSTN calls</span></span>

<span data-ttu-id="bc289-147">Un administrateur peut activer le Trunk défini pour acheminer les appels vers « passerelle site 1 » pour le routage de l’emplacement et associer la « passerelle site 1 » au site 1.</span><span class="sxs-lookup"><span data-stu-id="bc289-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="bc289-148">Lorsque l’option est activée, les appels routés par le biais de la passerelle « site 1 » ne seront routés qu’aux utilisateurs situés dans le site 1.</span><span class="sxs-lookup"><span data-stu-id="bc289-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="bc289-149">Tous les appels routés via le Trunk « site 1 passerelle » destinés aux utilisateurs d’un site différent, comme le site 2, seront bloqués pour empêcher les détournements d’appels RTC.</span><span class="sxs-lookup"><span data-stu-id="bc289-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="bc289-150">Tous les appels RTC entrants par le biais de la « passerelle du site 1 » ne seront autorisés à effectuer le routage qu’aux points de terminaison situés dans le site 1.</span><span class="sxs-lookup"><span data-stu-id="bc289-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="bc289-151">Par exemple, lorsque « Lync User 1 » voyage sur le site 2, tous les appels RTC entrants par le biais de « passerelle site 1 » ne seront pas routés aux points de terminaison « Lync User 1 » situés dans le site 2.</span><span class="sxs-lookup"><span data-stu-id="bc289-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="bc289-152">La même règle de routage s’applique si « Lync User 1 » voyage sur un site réseau inconnu où l’emplacement de l’utilisateur ne peut pas être déterminé.</span><span class="sxs-lookup"><span data-stu-id="bc289-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="bc289-153">Le tableau suivant décrit l’environnement utilisateur de « Lync User 1 » dans ce contexte.</span><span class="sxs-lookup"><span data-stu-id="bc289-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="bc289-154">Points de terminaison Lync User 1 situés dans le site réseau 1</span><span class="sxs-lookup"><span data-stu-id="bc289-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="bc289-155">Points de terminaison Lync User 1 situés dans le site réseau 2</span><span class="sxs-lookup"><span data-stu-id="bc289-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="bc289-156">Points de terminaison Lync User 1 situés dans un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="bc289-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc289-157">Appels RTC entrants vers l’utilisateur Lync 1</span><span class="sxs-lookup"><span data-stu-id="bc289-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="bc289-158">Les appels sont routés vers les points de terminaison dans cet emplacement</span><span class="sxs-lookup"><span data-stu-id="bc289-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="bc289-159">Les appels ne sont pas routés aux points de terminaison dans cet emplacement</span><span class="sxs-lookup"><span data-stu-id="bc289-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="bc289-160">Les appels ne sont pas routés aux points de terminaison dans cet emplacement</span><span class="sxs-lookup"><span data-stu-id="bc289-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="bc289-161">Appels RTC sortants</span><span class="sxs-lookup"><span data-stu-id="bc289-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="bc289-162">Les itinéraires vocaux sont référencés dans les stratégies vocales attribuées directement aux utilisateurs et les stratégies de routage vocal affectées aux sites réseau.</span><span class="sxs-lookup"><span data-stu-id="bc289-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="bc289-163">Les deux stratégies contiennent des références à des itinéraires qui peuvent être utilisées pour acheminer un appel différemment.</span><span class="sxs-lookup"><span data-stu-id="bc289-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="bc289-164">Par exemple, un administrateur peut définir une stratégie de routage vocale pour tous les utilisateurs situés dans le site réseau 1 pour acheminer tous les appels sortants par le biais de la « passerelle site 1 », tandis que la stratégie vocale de certains utilisateurs définit un itinéraire pour tous les appels sortants par le biais de la « passerelle site 2 ».</span><span class="sxs-lookup"><span data-stu-id="bc289-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="bc289-165">Même si ces utilisateurs se trouvent dans le site réseau 1, les appels sortants sont routés par le biais de la « passerelle du site 1 ».</span><span class="sxs-lookup"><span data-stu-id="bc289-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="bc289-166">Lorsqu’un utilisateur se trouve sur un site réseau configuré pour le routage sur la base de l’emplacement, l’itinéraire de la stratégie de routage de la voix du site réseau remplace l’itinéraire de la stratégie vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bc289-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="bc289-167">Cette règle est particulièrement utile pour les utilisateurs qui se déplacent temporairement sur un autre site.</span><span class="sxs-lookup"><span data-stu-id="bc289-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="bc289-168">Dans ce cas particulier, un utilisateur utilisera toujours une passerelle locale vers son emplacement. Si "Lync User 3" est situé sur "site 2", tous les appels sortants seront routés par le biais de la « passerelle site 2 », mais s’il est acheminé vers le site 1, tous les appels sortants placés alors qu’il se trouve sur le site 1 seront routés par le biais de « passerelle site 1 ».</span><span class="sxs-lookup"><span data-stu-id="bc289-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="bc289-169">Le tableau suivant illustre l’utilisation de l’utilisateur Lync 1 lors du placement d’un appel sortant sur les sites réseau suivants.</span><span class="sxs-lookup"><span data-stu-id="bc289-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="bc289-170">Site réseau 1</span><span class="sxs-lookup"><span data-stu-id="bc289-170">Network site 1</span></span></th>
<th><span data-ttu-id="bc289-171">Site réseau 2</span><span class="sxs-lookup"><span data-stu-id="bc289-171">Network site 2</span></span></th>
<th><span data-ttu-id="bc289-172">Site réseau inconnu ou non activé pour le routage par emplacement</span><span class="sxs-lookup"><span data-stu-id="bc289-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc289-173">Autorisation des appels sortants</span><span class="sxs-lookup"><span data-stu-id="bc289-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="bc289-174">Politique vocale utilisateur Lync 1</span><span class="sxs-lookup"><span data-stu-id="bc289-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="bc289-175">Politique vocale utilisateur Lync 1</span><span class="sxs-lookup"><span data-stu-id="bc289-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="bc289-176">Politique vocale utilisateur Lync 1</span><span class="sxs-lookup"><span data-stu-id="bc289-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc289-177">Routage des appels sortants</span><span class="sxs-lookup"><span data-stu-id="bc289-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="bc289-178">Site 1 politique de routage de la voix</span><span class="sxs-lookup"><span data-stu-id="bc289-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="bc289-179">Politique de routage téléphonique de site 2</span><span class="sxs-lookup"><span data-stu-id="bc289-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="bc289-180">Politique vocale de l’utilisateur et uniquement aux systèmes non activés pour le routage sur site</span><span class="sxs-lookup"><span data-stu-id="bc289-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="bc289-181">Transférer et transférer des appels</span><span class="sxs-lookup"><span data-stu-id="bc289-181">Call transfers and forwards</span></span>

<span data-ttu-id="bc289-182">Lorsque les appels sont transférés ou transférés, le routage des appels est affecté par le routage sur la base de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="bc289-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="bc289-183">Le tableau suivant décrit l’utilisateur Lync 1 qui transfère ou transfère un appel PSTN vers un autre utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="bc289-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc289-184">Utilisateur déclenchant ou transférant un appel</span><span class="sxs-lookup"><span data-stu-id="bc289-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="bc289-185">Utilisateur Lync 2</span><span class="sxs-lookup"><span data-stu-id="bc289-185">Lync user 2</span></span></th>
<th><span data-ttu-id="bc289-186">Utilisateur Lync 4</span><span class="sxs-lookup"><span data-stu-id="bc289-186">Lync user 4</span></span></th>
<th><span data-ttu-id="bc289-187">Utilisateur Lync dans le site réseau non activé pour le routage par emplacement</span><span class="sxs-lookup"><span data-stu-id="bc289-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc289-188">Utilisateur Lync 1</span><span class="sxs-lookup"><span data-stu-id="bc289-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="bc289-189">Le transfert ou renvoi de l’appel est autorisé</span><span class="sxs-lookup"><span data-stu-id="bc289-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="bc289-190">Le transfert ou renvoi de l’appel n’est pas autorisé</span><span class="sxs-lookup"><span data-stu-id="bc289-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="bc289-191">Le transfert ou renvoi de l’appel n’est pas autorisé</span><span class="sxs-lookup"><span data-stu-id="bc289-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="bc289-192">Le tableau suivant illustre la façon dont le routage basé sur l’emplacement affecte la façon dont l’appel est acheminé en fonction de l’emplacement du transfert de l’utilisateur Lync (utilisateur Lync 2, utilisateur Lync 4, etc.) vers un point de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="bc289-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc289-193">Point de terminaison pour lequel l’appel est transféré ou renvoyé vers</span><span class="sxs-lookup"><span data-stu-id="bc289-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="bc289-194">Utilisateur Lync 2</span><span class="sxs-lookup"><span data-stu-id="bc289-194">Lync user 2</span></span></th>
<th><span data-ttu-id="bc289-195">Utilisateur Lync 4</span><span class="sxs-lookup"><span data-stu-id="bc289-195">Lync user 4</span></span></th>
<th><span data-ttu-id="bc289-196">Utilisateur Lync dans le site réseau non activé pour le routage par emplacement</span><span class="sxs-lookup"><span data-stu-id="bc289-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc289-197">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="bc289-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="bc289-198">Le transfert d’appel est acheminé par le biais du site 1 politique de routage de la voix et sortie via la passerelle site 1</span><span class="sxs-lookup"><span data-stu-id="bc289-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="bc289-199">Le transfert d’appel ou le transfert est acheminé via la stratégie de routage de la voix site 2 et la sortie via la passerelle site 2</span><span class="sxs-lookup"><span data-stu-id="bc289-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="bc289-200">Le transfert d’appel est routé par le biais de la stratégie vocale et de la sortie de l’utilisateur Lync via une passerelle non activée pour le routage sur site (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="bc289-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="bc289-201">Sonnerie simultanée</span><span class="sxs-lookup"><span data-stu-id="bc289-201">Simultaneous ringing</span></span>

<span data-ttu-id="bc289-202">Lorsque le routage par emplacement est configuré dans l’exemple de topologie, les interactions suivantes sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="bc289-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="bc289-203">Le tableau suivant indique si le routage basé sur l’emplacement autorise une sonnerie simultanée pour différents utilisateurs de Lync (c’est-à-dire, utilisateur Lync 2, utilisateur Lync 4, etc.).</span><span class="sxs-lookup"><span data-stu-id="bc289-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc289-204">Destination de l’appel RTC entrant</span><span class="sxs-lookup"><span data-stu-id="bc289-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="bc289-205">Utilisateur Lync 2</span><span class="sxs-lookup"><span data-stu-id="bc289-205">Lync user 2</span></span></th>
<th><span data-ttu-id="bc289-206">Utilisateur Lync 4</span><span class="sxs-lookup"><span data-stu-id="bc289-206">Lync user 4</span></span></th>
<th><span data-ttu-id="bc289-207">Utilisateur Lync dans le site réseau non activé pour le routage par emplacement</span><span class="sxs-lookup"><span data-stu-id="bc289-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc289-208">Utilisateur Lync 1</span><span class="sxs-lookup"><span data-stu-id="bc289-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="bc289-209">Sonnerie simultanée autorisée</span><span class="sxs-lookup"><span data-stu-id="bc289-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="bc289-210">Sonnerie simultanée interdite</span><span class="sxs-lookup"><span data-stu-id="bc289-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="bc289-211">Sonnerie simultanée interdite</span><span class="sxs-lookup"><span data-stu-id="bc289-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="bc289-212">Le tableau suivant indique si le routage en fonction de l’emplacement autorise une sonnerie simultanée à un point de terminaison RTC provenant de différents utilisateurs de Lync (c’est-à-dire, utilisateur Lync 2, utilisateur Lync 4, etc.).</span><span class="sxs-lookup"><span data-stu-id="bc289-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc289-213">Cible de la sonnerie simultanée</span><span class="sxs-lookup"><span data-stu-id="bc289-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="bc289-214">Utilisateur Lync 2</span><span class="sxs-lookup"><span data-stu-id="bc289-214">Lync user 2</span></span></th>
<th><span data-ttu-id="bc289-215">Utilisateur Lync 4</span><span class="sxs-lookup"><span data-stu-id="bc289-215">Lync user 4</span></span></th>
<th><span data-ttu-id="bc289-216">Utilisateur Lync dans le site réseau non activé pour le routage par emplacement</span><span class="sxs-lookup"><span data-stu-id="bc289-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc289-217">Utilisateur Lync 1 téléphone mobile (point de terminaison PSTN)</span><span class="sxs-lookup"><span data-stu-id="bc289-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="bc289-218">Appels routés par le biais de la stratégie de routage vocale du site réseau 1 et de la sortie via le site 1 passerelle</span><span class="sxs-lookup"><span data-stu-id="bc289-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="bc289-219">Appels routés par le biais de la stratégie de routage de la voix du site Network 2 et de la sortie via la passerelle site 2</span><span class="sxs-lookup"><span data-stu-id="bc289-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="bc289-220">Appels routés par le biais de la stratégie vocale de l’appelant et sortie via une passerelle RTC non activée pour le routage par emplacement</span><span class="sxs-lookup"><span data-stu-id="bc289-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bc289-221">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc289-221">See Also</span></span>


[<span data-ttu-id="bc289-222">Planification du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc289-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

