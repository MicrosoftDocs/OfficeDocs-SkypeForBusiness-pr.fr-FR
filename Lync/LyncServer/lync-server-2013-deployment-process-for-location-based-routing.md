---
title: 'Lync Server 2013 : processus de déploiement du routage géodépendant'
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
ms.openlocfilehash: 93b26498593038231be527c98e62ee1f13865df1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="3e90f-102">Processus de déploiement pour le routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e90f-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e90f-103">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="3e90f-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="3e90f-104">Cette rubrique fournit une vue d’ensemble du processus de configuration du routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="3e90f-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="3e90f-105">Vous devez déployer Lync Server Enterprise Edition ou Standard Edition avec voix entreprise avant de configurer le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="3e90f-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="3e90f-106">Les composants requis par le routage géodépendant sont déjà installés et activés lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="3e90f-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="3e90f-107">Processus de déploiement de routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="3e90f-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e90f-108">Phase</span><span class="sxs-lookup"><span data-stu-id="3e90f-108">Phase</span></span></th>
<th><span data-ttu-id="3e90f-109">Étapes</span><span class="sxs-lookup"><span data-stu-id="3e90f-109">Steps</span></span></th>
<th><span data-ttu-id="3e90f-110">Groupes et rôles requis</span><span class="sxs-lookup"><span data-stu-id="3e90f-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="3e90f-111">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="3e90f-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e90f-112">Déployer voix entreprise</span><span class="sxs-lookup"><span data-stu-id="3e90f-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3e90f-113">Configuration des jonctions</span><span class="sxs-lookup"><span data-stu-id="3e90f-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="3e90f-114">Créer des stratégies de voix</span><span class="sxs-lookup"><span data-stu-id="3e90f-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="3e90f-115">Définir les itinéraires des communications vocales</span><span class="sxs-lookup"><span data-stu-id="3e90f-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e90f-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="3e90f-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="3e90f-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e90f-117">CsAdministrator</span></span><br />
<span data-ttu-id="3e90f-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e90f-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3e90f-119">Déploiement de Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="3e90f-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e90f-120">Vérifier le déploiement de voix entreprise</span><span class="sxs-lookup"><span data-stu-id="3e90f-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e90f-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="3e90f-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="3e90f-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e90f-122">CsAdministrator</span></span><br />
<span data-ttu-id="3e90f-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e90f-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e90f-124">Configurer des régions réseau, des sites et des sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="3e90f-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3e90f-125">Créer des régions réseau</span><span class="sxs-lookup"><span data-stu-id="3e90f-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="3e90f-126">Créer des sites réseau</span><span class="sxs-lookup"><span data-stu-id="3e90f-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="3e90f-127">Associe des sous-réseaux à des sites réseau</span><span class="sxs-lookup"><span data-stu-id="3e90f-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e90f-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="3e90f-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="3e90f-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e90f-129">CsAdministrator</span></span><br />
<span data-ttu-id="3e90f-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e90f-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3e90f-131">À propos des régions réseau, sites et sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="3e90f-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="3e90f-132">Créer ou modifier une région réseau</span><span class="sxs-lookup"><span data-stu-id="3e90f-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="3e90f-133">Créer ou modifier un site réseau</span><span class="sxs-lookup"><span data-stu-id="3e90f-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="3e90f-134">Associer un sous-réseau à un site réseau</span><span class="sxs-lookup"><span data-stu-id="3e90f-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e90f-135">Configurer le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="3e90f-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3e90f-136">Créer des stratégies de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="3e90f-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="3e90f-137">Définir une configuration de jonction distincte par jonction</span><span class="sxs-lookup"><span data-stu-id="3e90f-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="3e90f-138">Modifier des stratégies de voix</span><span class="sxs-lookup"><span data-stu-id="3e90f-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="3e90f-139">Activer la configuration du routage basé sur l’emplacement</span><span class="sxs-lookup"><span data-stu-id="3e90f-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e90f-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="3e90f-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="3e90f-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e90f-141">CsAdministrator</span></span><br />
<span data-ttu-id="3e90f-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e90f-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="3e90f-143">Exemple de déploiement</span><span class="sxs-lookup"><span data-stu-id="3e90f-143">Sample Deployment</span></span>

<span data-ttu-id="3e90f-144">Le déploiement suivant est utilisé pour illustrer les mécanismes activés par le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="3e90f-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="3e90f-145">![e1bd2230-44DA-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44DA-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="3e90f-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="3e90f-146">Appels RTC entrants</span><span class="sxs-lookup"><span data-stu-id="3e90f-146">Incoming PSTN calls</span></span>

<span data-ttu-id="3e90f-147">Un administrateur peut activer la jonction définie pour acheminer les appels vers « site 1 Gateway » pour le routage géodépendant et associer la passerelle « site 1 » au site 1.</span><span class="sxs-lookup"><span data-stu-id="3e90f-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="3e90f-148">Une fois activés, les appels routés via la passerelle « site 1 » seront acheminés uniquement vers les utilisateurs situés dans le site 1.</span><span class="sxs-lookup"><span data-stu-id="3e90f-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="3e90f-149">Tous les appels acheminés via la jonction « passerelle de site 1 » destiné aux utilisateurs dans un autre site, tel que le site 2, sont bloqués pour empêcher le contournement de numéro de téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="3e90f-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="3e90f-150">Tous les appels PSTN entrants via la passerelle « site 1 » seront uniquement autorisés à acheminer vers les points de terminaison situés dans le site 1.</span><span class="sxs-lookup"><span data-stu-id="3e90f-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="3e90f-151">Par exemple, lorsque « Lync User 1 » se déplace vers le site 2, tous les appels RTC entrants via « passerelle de site 1 » ne sont pas routés vers les points de terminaison « Lync User 1 » situés dans le site 2.</span><span class="sxs-lookup"><span data-stu-id="3e90f-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="3e90f-152">La règle de routage s’applique si « Lync User 1 » se déplace vers un site réseau inconnu où l’emplacement de l’utilisateur ne peut pas être déterminé.</span><span class="sxs-lookup"><span data-stu-id="3e90f-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="3e90f-153">Le tableau suivant décrit l’expérience utilisateur de « Lync User 1 » dans ce contexte.</span><span class="sxs-lookup"><span data-stu-id="3e90f-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="3e90f-154">Points de terminaison de Lync User 1 situés dans le site réseau 1</span><span class="sxs-lookup"><span data-stu-id="3e90f-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="3e90f-155">Points de terminaison de Lync User 1 situés dans le site réseau 2</span><span class="sxs-lookup"><span data-stu-id="3e90f-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="3e90f-156">Points de terminaison de Lync User 1 situés dans un site réseau inconnu</span><span class="sxs-lookup"><span data-stu-id="3e90f-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e90f-157">Appels RTC entrants vers Lync User 1</span><span class="sxs-lookup"><span data-stu-id="3e90f-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="3e90f-158">Les appels sont routés vers les points de terminaison à cet emplacement</span><span class="sxs-lookup"><span data-stu-id="3e90f-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="3e90f-159">Les appels ne sont pas routés vers les points de terminaison à cet emplacement</span><span class="sxs-lookup"><span data-stu-id="3e90f-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="3e90f-160">Les appels ne sont pas routés vers les points de terminaison à cet emplacement</span><span class="sxs-lookup"><span data-stu-id="3e90f-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="3e90f-161">Appels RTC sortants</span><span class="sxs-lookup"><span data-stu-id="3e90f-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="3e90f-162">Les itinéraires des communications vocales sont référencés dans les stratégies vocales attribuées directement aux utilisateurs, et les stratégies de routage des communications vocales affectées aux sites réseau.</span><span class="sxs-lookup"><span data-stu-id="3e90f-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="3e90f-163">Les deux stratégies contiennent des références à des itinéraires, qui peuvent être utilisées pour acheminer un appel différemment.</span><span class="sxs-lookup"><span data-stu-id="3e90f-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="3e90f-164">Par exemple, un administrateur peut définir une stratégie de routage des communications vocales pour tous les utilisateurs se trouvant dans le site réseau 1 pour acheminer tous les appels sortants via la passerelle « site 1 » tandis que la stratégie de voix de certains utilisateurs définit un itinéraire pour tous les appels sortants via la passerelle « site 2 ».</span><span class="sxs-lookup"><span data-stu-id="3e90f-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="3e90f-165">Bien que ces utilisateurs se trouvent dans le site réseau 1, leurs appels sortants sont acheminés via la passerelle « site 1 ».</span><span class="sxs-lookup"><span data-stu-id="3e90f-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="3e90f-166">Lorsqu’un utilisateur se trouve dans un site réseau configuré pour le routage géodépendant, l’itinéraire des stratégies de routage des communications vocales du site réseau remplace le chemin de la stratégie de voix de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e90f-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="3e90f-167">Cette règle est particulièrement utile pour les utilisateurs qui se déplacent temporairement sur un autre site.</span><span class="sxs-lookup"><span data-stu-id="3e90f-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="3e90f-168">Dans ce cas particulier, un utilisateur utilisera toujours une passerelle locale pour son emplacement ; Si « Lync User 3 » se trouve sur « site 2 », tous ses appels sortants sont acheminés via « site 2 Gateway », mais s’il transite sur le site 1, tous les appels sortants passés alors qu’il se trouve sur le site 1 sont acheminés via « passerelle de site 1 ».</span><span class="sxs-lookup"><span data-stu-id="3e90f-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="3e90f-169">Le tableau suivant illustre l’expérience utilisateur de Lync User 1 à effectuer un appel sortant à partir des sites réseau suivants.</span><span class="sxs-lookup"><span data-stu-id="3e90f-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="3e90f-170">Site réseau 1</span><span class="sxs-lookup"><span data-stu-id="3e90f-170">Network site 1</span></span></th>
<th><span data-ttu-id="3e90f-171">Site réseau 2</span><span class="sxs-lookup"><span data-stu-id="3e90f-171">Network site 2</span></span></th>
<th><span data-ttu-id="3e90f-172">Site réseau inconnu ou non activé pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="3e90f-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e90f-173">Autorisation des appels sortants</span><span class="sxs-lookup"><span data-stu-id="3e90f-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="3e90f-174">Stratégie de voix de Lync User 1</span><span class="sxs-lookup"><span data-stu-id="3e90f-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="3e90f-175">Stratégie de voix de Lync User 1</span><span class="sxs-lookup"><span data-stu-id="3e90f-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="3e90f-176">Stratégie de voix de Lync User 1</span><span class="sxs-lookup"><span data-stu-id="3e90f-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e90f-177">Routage des appels sortants</span><span class="sxs-lookup"><span data-stu-id="3e90f-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="3e90f-178">Stratégie de routage des communications vocales du site 1</span><span class="sxs-lookup"><span data-stu-id="3e90f-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="3e90f-179">Stratégie de routage des communications vocales du site 2</span><span class="sxs-lookup"><span data-stu-id="3e90f-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="3e90f-180">Stratégie de voix de l’utilisateur et uniquement aux systèmes non activés pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="3e90f-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="3e90f-181">Transferts et transferts d’appels</span><span class="sxs-lookup"><span data-stu-id="3e90f-181">Call transfers and forwards</span></span>

<span data-ttu-id="3e90f-182">Lorsque les appels sont transférés ou transférés, le routage des appels est affecté par le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="3e90f-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="3e90f-183">Le tableau suivant représente l’utilisateur Lync 1 qui transfère ou transfère un appel RTC à un autre utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="3e90f-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e90f-184">Envoi ou transfert d’appel par un utilisateur</span><span class="sxs-lookup"><span data-stu-id="3e90f-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="3e90f-185">Lync utilisateur 2</span><span class="sxs-lookup"><span data-stu-id="3e90f-185">Lync user 2</span></span></th>
<th><span data-ttu-id="3e90f-186">Lync User 4</span><span class="sxs-lookup"><span data-stu-id="3e90f-186">Lync user 4</span></span></th>
<th><span data-ttu-id="3e90f-187">Utilisateur Lync dans le site réseau non activé pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="3e90f-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e90f-188">Lync utilisateur 1</span><span class="sxs-lookup"><span data-stu-id="3e90f-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="3e90f-189">Le transfert d’appel ou le transfert est autorisé</span><span class="sxs-lookup"><span data-stu-id="3e90f-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="3e90f-190">Le transfert d’appel ou le transfert n’est pas autorisé</span><span class="sxs-lookup"><span data-stu-id="3e90f-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="3e90f-191">Le transfert d’appel ou le transfert n’est pas autorisé</span><span class="sxs-lookup"><span data-stu-id="3e90f-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="3e90f-192">Le tableau suivant illustre l’impact du routage géodépendant sur la façon dont l’appel est acheminé en fonction de l’emplacement de transfert de l’utilisateur Lync (Lync user 2, Lync User 4, etc.) vers un point de terminaison PSTN.</span><span class="sxs-lookup"><span data-stu-id="3e90f-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e90f-193">Point de terminaison où l’appel est transféré ou transféré vers</span><span class="sxs-lookup"><span data-stu-id="3e90f-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="3e90f-194">Lync utilisateur 2</span><span class="sxs-lookup"><span data-stu-id="3e90f-194">Lync user 2</span></span></th>
<th><span data-ttu-id="3e90f-195">Lync User 4</span><span class="sxs-lookup"><span data-stu-id="3e90f-195">Lync user 4</span></span></th>
<th><span data-ttu-id="3e90f-196">Utilisateur Lync dans le site réseau non activé pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="3e90f-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e90f-197">Point de terminaison PSTN</span><span class="sxs-lookup"><span data-stu-id="3e90f-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="3e90f-198">Le transfert d’appel ou le transfert est acheminé via le site 1 stratégie de routage des communications vocales et sortie via la passerelle site 1</span><span class="sxs-lookup"><span data-stu-id="3e90f-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="3e90f-199">Le transfert d’appel ou le transfert est acheminé via le site 2 stratégie de routage des communications vocales et sortie via la passerelle site 2</span><span class="sxs-lookup"><span data-stu-id="3e90f-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="3e90f-200">Le transfert d’appel ou le transfert est acheminé via la stratégie de voix de l’utilisateur Lync et la sortie via une passerelle non activée pour le routage géodépendant (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="3e90f-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="3e90f-201">Sonnerie simultanée</span><span class="sxs-lookup"><span data-stu-id="3e90f-201">Simultaneous ringing</span></span>

<span data-ttu-id="3e90f-202">Une fois le routage géodépendant configuré dans l’exemple de topologie, les interactions suivantes sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="3e90f-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="3e90f-203">Le tableau suivant indique si le routage géodépendant autorise la sonnerie simultanée pour différents utilisateurs Lync (par exemple, Lync user 2, Lync User 4, etc.).</span><span class="sxs-lookup"><span data-stu-id="3e90f-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e90f-204">Cible d’appel RTC entrant</span><span class="sxs-lookup"><span data-stu-id="3e90f-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="3e90f-205">Lync utilisateur 2</span><span class="sxs-lookup"><span data-stu-id="3e90f-205">Lync user 2</span></span></th>
<th><span data-ttu-id="3e90f-206">Lync User 4</span><span class="sxs-lookup"><span data-stu-id="3e90f-206">Lync user 4</span></span></th>
<th><span data-ttu-id="3e90f-207">Utilisateur Lync dans le site réseau non activé pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="3e90f-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e90f-208">Lync utilisateur 1</span><span class="sxs-lookup"><span data-stu-id="3e90f-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="3e90f-209">Sonnerie simultanée autorisée</span><span class="sxs-lookup"><span data-stu-id="3e90f-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="3e90f-210">Sonnerie simultanée non autorisée</span><span class="sxs-lookup"><span data-stu-id="3e90f-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="3e90f-211">Sonnerie simultanée non autorisée</span><span class="sxs-lookup"><span data-stu-id="3e90f-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="3e90f-212">Le tableau suivant indique si le routage géodépendant autorise la sonnerie simultanée à un point de terminaison PSTN à partir de différents utilisateurs Lync (par exemple, Lync user 2, Lync User 4, etc.).</span><span class="sxs-lookup"><span data-stu-id="3e90f-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e90f-213">Cible annulaire simultanée</span><span class="sxs-lookup"><span data-stu-id="3e90f-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="3e90f-214">Lync utilisateur 2</span><span class="sxs-lookup"><span data-stu-id="3e90f-214">Lync user 2</span></span></th>
<th><span data-ttu-id="3e90f-215">Lync User 4</span><span class="sxs-lookup"><span data-stu-id="3e90f-215">Lync user 4</span></span></th>
<th><span data-ttu-id="3e90f-216">Utilisateur Lync dans le site réseau non activé pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="3e90f-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e90f-217">Téléphone mobile Lync User 1 (point de terminaison PSTN)</span><span class="sxs-lookup"><span data-stu-id="3e90f-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="3e90f-218">Appel acheminé via la stratégie de routage des communications vocales du site réseau 1 et sortie via la passerelle site 1</span><span class="sxs-lookup"><span data-stu-id="3e90f-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="3e90f-219">Appel acheminé via la stratégie de routage des communications vocales du site Network 2 et sortie via la passerelle site 2</span><span class="sxs-lookup"><span data-stu-id="3e90f-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="3e90f-220">Appel acheminé via la stratégie de voix de l’appelant et sortie via une passerelle PSTN non activée pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="3e90f-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e90f-221">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e90f-221">See Also</span></span>


[<span data-ttu-id="3e90f-222">Planification du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e90f-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

