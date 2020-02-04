---
title: 'Lync Server 2013 : Options de déploiement SIP direct'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e88dd5a576e467fbca25e9f467bd168fd6401d17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="0ea22-102">Options de déploiement SIP direct dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ea22-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ea22-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0ea22-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0ea22-104">Cette rubrique fournit des exemples de topologies pour le déploiement de connexions SIP directes.</span><span class="sxs-lookup"><span data-stu-id="0ea22-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="0ea22-105">Serveur Lync autonome</span><span class="sxs-lookup"><span data-stu-id="0ea22-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="0ea22-106">Si votre organisation utilise l’un des déploiements décrits dans cette section, vous pouvez utiliser Lync Server 2013 comme seule solution de téléphonie pour une partie ou l’ensemble d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="0ea22-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="0ea22-107">Cette section décrit en détail les déploiements suivants :</span><span class="sxs-lookup"><span data-stu-id="0ea22-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="0ea22-108">**Déploiement incrémentiel :** Cette option part du principe que vous disposez d’une infrastructure PBX (Private Branch Exchange) existante et que vous envisagez d’introduire une voix entreprise de façon incrémentielle pour des groupes ou équipes plus petits au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0ea22-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="0ea22-109">**Déploiement de Lync Server VoIP uniquement :** cette option suppose que vous envisagez le déploiement d’Enterprise Voice sur un site ne disposant pas d’une infrastructure de téléphonie classique.</span><span class="sxs-lookup"><span data-stu-id="0ea22-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="0ea22-110">Déploiement incrémental</span><span class="sxs-lookup"><span data-stu-id="0ea22-110">Incremental Deployment</span></span>

<span data-ttu-id="0ea22-111">Dans le cadre du déploiement incrémentiel, Lync Server 2013 est la seule solution de téléphonie pour les équipes ou services individuels, tandis que les autres utilisateurs d’une organisation continuent à utiliser un PBX.</span><span class="sxs-lookup"><span data-stu-id="0ea22-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="0ea22-112">Cette stratégie de déploiement incrémental fournit un moyen d’introduire la téléphonie IP dans votre entreprise par le biais de programmes pilotes contrôlés.</span><span class="sxs-lookup"><span data-stu-id="0ea22-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="0ea22-113">Les groupes de travail dont les besoins en matière de communication sont les plus appropriés par le biais de communications unifiées Microsoft sont déplacés vers voix entreprise, tandis que d’autres utilisateurs restent sur le système PBX existant.</span><span class="sxs-lookup"><span data-stu-id="0ea22-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="0ea22-114">Vous pouvez migrer des groupes de travail supplémentaires vers Enterprise Voice, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="0ea22-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="0ea22-115">L’option incrémental est recommandée si vous avez clairement défini des groupes d’utilisateurs présentant des exigences de communication en commun et qui se prêtent à une gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="0ea22-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="0ea22-116">Cette option est également utile si vous avez des équipes ou des services qui se propagent sur des zones géographiques larges, pour lesquelles l’économie des tarifs de grande distance peut être importante.</span><span class="sxs-lookup"><span data-stu-id="0ea22-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="0ea22-117">En fait, cette option est utile pour créer des équipes virtuelles dont les membres pourront être disséminés dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="0ea22-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="0ea22-118">Vous pouvez créer, modifier ou disperser le de telles équipes en réponse rapide au changement de configuration de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="0ea22-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="0ea22-119">La figure suivante illustre la topologie générique pour le déploiement de la voix entreprise derrière un PBX.</span><span class="sxs-lookup"><span data-stu-id="0ea22-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="0ea22-120">Il s’agit de la topologie recommandée pour le déploiement incrémentiel.</span><span class="sxs-lookup"><span data-stu-id="0ea22-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="0ea22-121">**Option de déploiement incrémental**</span><span class="sxs-lookup"><span data-stu-id="0ea22-121">**Incremental deployment option**</span></span>

<span data-ttu-id="0ea22-122">![Diagramme d’option de migration départementale](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagramme d’option de migration départementale")</span><span class="sxs-lookup"><span data-stu-id="0ea22-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ea22-123">Si vous connectez votre déploiement de Lync Server à un partenaire SIP direct certifié, une passerelle RTC (réseau téléphonique commuté) entre le serveur de médiation et le PBX n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="0ea22-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="0ea22-124">Pour obtenir la liste des partenaires SIP directs certifiés, voir le site Web Microsoft Unified Communications Open <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>Interoperability du programme à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="0ea22-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0ea22-125">Le chemin d’accès multimédia indiqué dans cette figure est associé au contournement de média activé (configuration recommandée).</span><span class="sxs-lookup"><span data-stu-id="0ea22-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="0ea22-126">Si vous choisissez de désactiver le contournement multimédia, le chemin multimédia est routé par le biais du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="0ea22-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="0ea22-127">Dans cette topologie, les services ou groupes de travail sélectionnés sont activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="0ea22-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="0ea22-128">Une passerelle RTC relie le groupe de travail VoIP au système PBX.</span><span class="sxs-lookup"><span data-stu-id="0ea22-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="0ea22-129">Les utilisateurs qui sont activés pour voix entreprise, y compris les travailleurs distants, communiquent sur le réseau IP.</span><span class="sxs-lookup"><span data-stu-id="0ea22-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="0ea22-130">Les appels d’utilisateurs vocaux d’entreprise vers le RTC et aux collègues qui ne sont pas activés pour voix entreprise sont routés vers la passerelle RTC appropriée.</span><span class="sxs-lookup"><span data-stu-id="0ea22-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="0ea22-131">Les appels provenant de collègues qui se trouvent toujours sur le système PBX ou à partir des appelants sur le RTC sont routés vers la passerelle RTC, qui transfère les appels vers Lync Server pour le routage.</span><span class="sxs-lookup"><span data-stu-id="0ea22-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="0ea22-132">Il existe deux configurations recommandées pour la connexion de voix entreprise à une infrastructure PBX existante pour l’interopérabilité : voix entreprise derrière le PBX et voix entreprise en face du PBX.</span><span class="sxs-lookup"><span data-stu-id="0ea22-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="0ea22-133">Voix entreprise à l’arrière-plan PBX</span><span class="sxs-lookup"><span data-stu-id="0ea22-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="0ea22-134">Lorsque Enterprise Voice est déployé derrière le système PBX, tous les appels à partir du RTC arrivent au PBX, ce qui achemine les appels vers une passerelle RTC et les appels vers des utilisateurs PBX vers le PBX.</span><span class="sxs-lookup"><span data-stu-id="0ea22-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="0ea22-135">Voix entreprise en face du PBX</span><span class="sxs-lookup"><span data-stu-id="0ea22-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="0ea22-136">Lorsque Enterprise Voice est déployé devant le PBX, tous les appels arrivent sur la passerelle RTC, qui achemine les appels pour les utilisateurs voix entreprise vers Lync Server et les appels aux utilisateurs PBX vers le PBX.</span><span class="sxs-lookup"><span data-stu-id="0ea22-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="0ea22-137">Les appels vers le RTC provenant des utilisateurs de voix et de PBX entreprise sont routés via le réseau IP vers la passerelle RTC la plus économique.</span><span class="sxs-lookup"><span data-stu-id="0ea22-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="0ea22-138">Le tableau suivant répertorie les avantages et inconvénients de cette configuration.</span><span class="sxs-lookup"><span data-stu-id="0ea22-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="0ea22-139">Avantages et inconvénients du déploiement d’Enterprise Voice en face du PBX</span><span class="sxs-lookup"><span data-stu-id="0ea22-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ea22-140">Inconvénients</span><span class="sxs-lookup"><span data-stu-id="0ea22-140">Advantages</span></span></th>
<th><span data-ttu-id="0ea22-141">Liés</span><span class="sxs-lookup"><span data-stu-id="0ea22-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ea22-142">Le système PBX répond toujours aux utilisateurs non activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="0ea22-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="0ea22-143">Les passerelles existantes risquent de ne pas prendre en charge les fonctionnalités ou capacités de votre choix.</span><span class="sxs-lookup"><span data-stu-id="0ea22-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ea22-144">Le système PBX gère tous les appareils antérieurs.</span><span class="sxs-lookup"><span data-stu-id="0ea22-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="0ea22-145">Il est nécessaire de disposer d’un Trunk de la passerelle au PBX et de la passerelle au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="0ea22-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="0ea22-146">Il est possible que vous ayez besoin de plus de circuits auprès du prestataire de services.</span><span class="sxs-lookup"><span data-stu-id="0ea22-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ea22-147">Les utilisateurs voix entreprise conservent les mêmes numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="0ea22-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="0ea22-148">Déploiement VoIP de Lync Server uniquement</span><span class="sxs-lookup"><span data-stu-id="0ea22-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="0ea22-149">Enterprise Voice offre de nouvelles entreprises ainsi que de nouveaux sites Office pour les entreprises existantes, avec la possibilité d’implémenter une solution VoIP complète sans avoir à vous soucier de l’intégration PBX ou induire le déploiement et la maintenance importants. coûts d’une infrastructure PBX IP.</span><span class="sxs-lookup"><span data-stu-id="0ea22-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="0ea22-150">Cette solution prend en charge les travailleurs sur site et distants.</span><span class="sxs-lookup"><span data-stu-id="0ea22-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="0ea22-151">Dans ce déploiement, tous les appels sont routés via le réseau IP.</span><span class="sxs-lookup"><span data-stu-id="0ea22-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="0ea22-152">Les appels vers le RTC sont routés vers la passerelle RTC appropriée.</span><span class="sxs-lookup"><span data-stu-id="0ea22-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="0ea22-153">Lync 2013 ou Lync Phone Edition sert de téléphone téléphonique.</span><span class="sxs-lookup"><span data-stu-id="0ea22-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="0ea22-154">Le contrôle d’appel distant n’est pas disponible et n’est pas nécessaire, car il n’y a pas de téléphone PBX pour le contrôle des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0ea22-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="0ea22-155">Les services de messagerie vocale et de standard automatique sont disponibles par le biais du déploiement facultatif de la messagerie unifiée Exchange (UM).</span><span class="sxs-lookup"><span data-stu-id="0ea22-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ea22-156">Outre l’infrastructure réseau qui est requise pour la prise en charge de Lync Server 2013, un déploiement VoIP uniquement peut utiliser une petite passerelle qualifiée pour prendre en charge les télécopieurs et les appareils analogiques.</span><span class="sxs-lookup"><span data-stu-id="0ea22-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="0ea22-157">La figure suivante illustre une topologie classique pour un déploiement VoIP uniquement.</span><span class="sxs-lookup"><span data-stu-id="0ea22-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="0ea22-158">**Option de déploiement VoIP uniquement**</span><span class="sxs-lookup"><span data-stu-id="0ea22-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="0ea22-159">![Option de déploiement dans un environnement vierge](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Option de déploiement dans un environnement vierge")</span><span class="sxs-lookup"><span data-stu-id="0ea22-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ea22-160">Le chemin d’accès multimédia indiqué dans cette figure est associé au contournement de média activé (configuration recommandée).</span><span class="sxs-lookup"><span data-stu-id="0ea22-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="0ea22-161">Si vous choisissez de désactiver le contournement multimédia, le chemin multimédia est routé par le biais du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="0ea22-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

