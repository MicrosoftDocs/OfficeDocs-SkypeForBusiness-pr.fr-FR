---
title: 'Lync Server 2013 : options de déploiement SIP direct'
description: 'Lync Server 2013 : options de déploiement SIP direct.'
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
ms.openlocfilehash: 5afe361a5522ee4869bbdb572e5016437d5580d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568240"
---
# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="1f757-103">Options de déploiement SIP direct dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f757-103">Direct SIP deployment options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f757-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1f757-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1f757-105">Cette rubrique fournit des exemples de topologies pour le déploiement de connexions SIP directes.</span><span class="sxs-lookup"><span data-stu-id="1f757-105">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="1f757-106">Lync Server Stand-Alone</span><span class="sxs-lookup"><span data-stu-id="1f757-106">Lync Server Stand-Alone</span></span>

<span data-ttu-id="1f757-107">Si votre organisation utilise l’un des déploiements décrits dans cette section, vous pouvez utiliser Lync Server 2013 comme solution de téléphonie unique pour tout ou partie d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="1f757-107">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="1f757-108">Cette section décrit en détail les déploiements suivants :</span><span class="sxs-lookup"><span data-stu-id="1f757-108">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="1f757-109">**Déploiement incrémentiel :** Cette option suppose que vous disposez d’une infrastructure PBX (Private Branch Exchange) existante et que vous envisagez d’introduire une voix entreprise incrémentielle pour des groupes ou équipes plus petits au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1f757-109">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="1f757-110">**Déploiement Lync Server VoIP uniquement :** cette option suppose que vous envisagez de déployer la voix entreprise sur un site qui ne dispose pas d’une infrastructure de téléphonie traditionnelle.</span><span class="sxs-lookup"><span data-stu-id="1f757-110">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="1f757-111">Déploiement incrémentiel</span><span class="sxs-lookup"><span data-stu-id="1f757-111">Incremental Deployment</span></span>

<span data-ttu-id="1f757-112">Dans un déploiement incrémentiel, Lync Server 2013 est la seule solution de téléphonie pour des équipes ou des services individuels, tandis que les autres utilisateurs d’une organisation continuent à utiliser un PBX.</span><span class="sxs-lookup"><span data-stu-id="1f757-112">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="1f757-113">Cette stratégie de déploiement incrémentiel offre un moyen d’introduire la téléphonie IP dans votre entreprise par le biais de programmes pilotes contrôlés.</span><span class="sxs-lookup"><span data-stu-id="1f757-113">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="1f757-114">Les groupes de travail dont les besoins en matière de communication sont les plus utilisés par les communications unifiées de Microsoft sont déplacés vers voix entreprise, tandis que d’autres utilisateurs demeurent sur le PBX existant.</span><span class="sxs-lookup"><span data-stu-id="1f757-114">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="1f757-115">D’autres groupes de travail peuvent être migrés vers voix entreprise, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="1f757-115">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="1f757-116">L’option incrémentielle est recommandée si vous avez clairement défini des groupes d’utilisateurs ayant des exigences de communication en commun et qui se prêtent à la gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="1f757-116">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="1f757-117">Cette option est également efficace si vous avez des équipes ou des services qui sont répartis sur des zones géographiques larges, où les économies de longue distance peuvent être importantes.</span><span class="sxs-lookup"><span data-stu-id="1f757-117">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="1f757-118">En fait, cette option est utile pour créer des équipes virtuelles dont les membres peuvent être dispersés dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="1f757-118">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="1f757-119">Vous pouvez créer, modifier ou DISBAND des équipes en réponse rapide aux besoins de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1f757-119">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="1f757-120">La figure suivante illustre la topologie générique pour le déploiement de voix entreprise derrière un PBX.</span><span class="sxs-lookup"><span data-stu-id="1f757-120">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="1f757-121">Il s’agit de la topologie recommandée pour le déploiement incrémentiel.</span><span class="sxs-lookup"><span data-stu-id="1f757-121">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="1f757-122">**Option de déploiement incrémentiel**</span><span class="sxs-lookup"><span data-stu-id="1f757-122">**Incremental deployment option**</span></span>

<span data-ttu-id="1f757-123">![Diagramme d’option de migration départementale](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagramme d’option de migration départementale")</span><span class="sxs-lookup"><span data-stu-id="1f757-123">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f757-124">Si vous connectez votre déploiement Lync Server à un partenaire SIP direct certifié, il n’est pas nécessaire d’avoir une passerelle de réseau téléphonique commuté (PSTN) entre le serveur de médiation et le PBX.</span><span class="sxs-lookup"><span data-stu-id="1f757-124">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="1f757-125">Pour obtenir la liste des partenaires SIP directs certifiés, consultez le site Web Microsoft Unified Communications Open Interoperability Program à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A> .</span><span class="sxs-lookup"><span data-stu-id="1f757-125">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1f757-126">Le chemin d’accès multimédia indiqué dans cette figure a une déviation du trafic multimédia activé (configuration recommandée).</span><span class="sxs-lookup"><span data-stu-id="1f757-126">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="1f757-127">Si vous choisissez de désactiver la déviation du trafic multimédia, le chemin d’accès multimédia est routé via le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1f757-127">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="1f757-128">Dans cette topologie, les services ou groupes de travail sélectionnés sont activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="1f757-128">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="1f757-129">Une passerelle PSTN relie le groupe de travail compatible VoIP (Voice over Internet Protocol) au PBX.</span><span class="sxs-lookup"><span data-stu-id="1f757-129">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="1f757-130">Les utilisateurs qui sont activés pour voix entreprise, y compris les travailleurs distants, communiquent sur le réseau IP.</span><span class="sxs-lookup"><span data-stu-id="1f757-130">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="1f757-131">Les appels émis par les utilisateurs voix entreprise vers le RTC et les collègues qui ne sont pas activés pour voix entreprise sont acheminés vers la passerelle PSTN appropriée.</span><span class="sxs-lookup"><span data-stu-id="1f757-131">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="1f757-132">Les appels provenant de collègues qui sont toujours sur le système PBX ou des appelants sur le réseau téléphonique commuté (RTC) sont acheminés vers la passerelle PSTN, qui transfère les appels vers Lync Server pour le routage.</span><span class="sxs-lookup"><span data-stu-id="1f757-132">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="1f757-133">Il existe deux configurations recommandées pour la connexion de voix entreprise à une infrastructure PBX existante pour l’interopérabilité : voix entreprise derrière le PBX et voix entreprise devant le PBX.</span><span class="sxs-lookup"><span data-stu-id="1f757-133">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="1f757-134">Voix entreprise derrière le PBX</span><span class="sxs-lookup"><span data-stu-id="1f757-134">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="1f757-135">Quand Enterprise Voice est déployé derrière le PBX, tous les appels provenant du RTC arrivent sur le PBX, qui achemine les appels vers une passerelle PSTN pour les utilisateurs de voix entreprise et les appels vers le PBX pour les utilisateurs PBX.</span><span class="sxs-lookup"><span data-stu-id="1f757-135">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="1f757-136">Voix entreprise devant le PBX</span><span class="sxs-lookup"><span data-stu-id="1f757-136">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="1f757-137">Quand Enterprise Voice est déployé devant le PBX, tous les appels arrivent à la passerelle PSTN, qui achemine les appels pour les utilisateurs voix entreprise vers Lync Server et appelle les utilisateurs PBX vers le PBX.</span><span class="sxs-lookup"><span data-stu-id="1f757-137">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="1f757-138">Les appels vers le RTC provenant des utilisateurs de voix entreprise et PBX sont acheminés via le réseau IP vers la passerelle PSTN la plus économique.</span><span class="sxs-lookup"><span data-stu-id="1f757-138">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="1f757-139">Le tableau suivant présente les avantages et les inconvénients de cette configuration.</span><span class="sxs-lookup"><span data-stu-id="1f757-139">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="1f757-140">Avantages et inconvénients du déploiement de voix entreprise devant le PBX</span><span class="sxs-lookup"><span data-stu-id="1f757-140">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f757-141">Avantages</span><span class="sxs-lookup"><span data-stu-id="1f757-141">Advantages</span></span></th>
<th><span data-ttu-id="1f757-142">Inconvénients</span><span class="sxs-lookup"><span data-stu-id="1f757-142">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f757-143">Le PBX sert toujours les utilisateurs non activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="1f757-143">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="1f757-144">Il se peut que les passerelles existantes ne prennent pas en charge les fonctionnalités ou la capacité de votre choix.</span><span class="sxs-lookup"><span data-stu-id="1f757-144">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f757-145">PBX gère tous les appareils antérieurs.</span><span class="sxs-lookup"><span data-stu-id="1f757-145">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="1f757-146">Nécessite une jonction de la passerelle vers le PBX et de la passerelle vers le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1f757-146">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="1f757-147">Vous aurez peut-être besoin de plus de jonctions à partir du fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="1f757-147">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f757-148">Les utilisateurs de voix entreprise conservent les mêmes numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="1f757-148">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="1f757-149">Déploiement de Lync Server VoIP-Only</span><span class="sxs-lookup"><span data-stu-id="1f757-149">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="1f757-150">Voix entreprise fournit de nouvelles entreprises, ainsi que de nouveaux sites Office pour les entreprises existantes, avec la possibilité de mettre en œuvre une solution VoIP complète sans avoir à se préoccuper de l’intégration de PBX ou d’impliquer des coûts substantiels de déploiement et de maintenance d’une infrastructure IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="1f757-150">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="1f757-151">Cette solution prend en charge les travailleurs à la fois sur site et distants.</span><span class="sxs-lookup"><span data-stu-id="1f757-151">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="1f757-152">Dans ce déploiement, tous les appels sont routés sur le réseau IP.</span><span class="sxs-lookup"><span data-stu-id="1f757-152">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="1f757-153">Les appels vers le RTC sont acheminés vers la passerelle PSTN appropriée.</span><span class="sxs-lookup"><span data-stu-id="1f757-153">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="1f757-154">Lync 2013 ou Lync Phone Edition sert de téléphone.</span><span class="sxs-lookup"><span data-stu-id="1f757-154">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="1f757-155">Le contrôle d’appel distant n’est pas disponible et n’est pas nécessaire, car il n’existe aucun téléphone PBX que les utilisateurs peuvent contrôler.</span><span class="sxs-lookup"><span data-stu-id="1f757-155">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="1f757-156">Les services de messagerie vocale et de standard automatique sont disponibles via le déploiement facultatif de la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="1f757-156">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f757-157">En plus de l’infrastructure réseau requise pour prendre en charge Lync Server 2013, un déploiement VoIP uniquement peut utiliser une petite passerelle qualifiée pour prendre en charge les télécopieurs et les appareils analogiques.</span><span class="sxs-lookup"><span data-stu-id="1f757-157">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="1f757-158">La figure suivante illustre une topologie classique pour un déploiement VoIP uniquement.</span><span class="sxs-lookup"><span data-stu-id="1f757-158">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="1f757-159">**Option de déploiement VoIP uniquement**</span><span class="sxs-lookup"><span data-stu-id="1f757-159">**VoIP-only deployment option**</span></span>

<span data-ttu-id="1f757-160">![Option de déploiement Greenfidle](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Option de déploiement Greenfidle")</span><span class="sxs-lookup"><span data-stu-id="1f757-160">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f757-161">Le chemin d’accès multimédia indiqué dans cette figure a une déviation du trafic multimédia activé (configuration recommandée).</span><span class="sxs-lookup"><span data-stu-id="1f757-161">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="1f757-162">Si vous choisissez de désactiver la déviation du trafic multimédia, le chemin d’accès multimédia est routé via le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="1f757-162">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

