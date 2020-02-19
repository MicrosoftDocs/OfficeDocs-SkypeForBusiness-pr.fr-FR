---
title: 'Lync Server 2013 : options de déploiement de la passerelle PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d90fdcb368bf6ed9d610f214122900add5b15547
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="627ce-102">Options de déploiement de passerelle PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="627ce-102">PSTN gateway deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="627ce-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="627ce-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="627ce-104">Passerelles PSTN</span><span class="sxs-lookup"><span data-stu-id="627ce-104">PSTN Gateways</span></span>

<span data-ttu-id="627ce-105">Les passerelles du réseau téléphonique commuté (PSTN) sont des composants matériels tiers qui convertissent la signalisation et les médias entre l’infrastructure Voix Entreprise et le réseau téléphonique commuté, directement ou via une connexion à des jonctions SIP.</span><span class="sxs-lookup"><span data-stu-id="627ce-105">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="627ce-106">Quelle que soit la topologie utilisée, la passerelle permet le raccordement au réseau téléphonique commuté.</span><span class="sxs-lookup"><span data-stu-id="627ce-106">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="627ce-107">La passerelle est isolée dans son propre sous-réseau et est connectée au réseau d’entreprise via le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="627ce-107">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="627ce-108">Une entreprise constituée de plusieurs sites déploie généralement une ou plusieurs passerelles sur chaque site.</span><span class="sxs-lookup"><span data-stu-id="627ce-108">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="627ce-109">Les sites de succursale peuvent se connecter au RTC par le biais d’une passerelle ou d’un Survivable Branch appliance qui combine passerelle et serveurs dans un seul et même boîtier.</span><span class="sxs-lookup"><span data-stu-id="627ce-109">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="627ce-110">Si les sites de succursale utilisent une passerelle, un serveur d’inscriptions et de médiation est requis sur le site, sauf si la liaison de réseau étendu est résiliente.</span><span class="sxs-lookup"><span data-stu-id="627ce-110">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="627ce-111">Un ou plusieurs serveurs de médiation, colocalisés sur des serveurs frontaux, peuvent acheminer les appels pour une ou plusieurs passerelles de chaque site.</span><span class="sxs-lookup"><span data-stu-id="627ce-111">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="627ce-112">Nous vous recommandons de déployer le serveur d’inscriptions, le serveur de médiation et la passerelle requis sur site sous la forme d’un Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="627ce-112">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="627ce-113">Il est peut-être nécessaire de déterminer le nombre, la taille et l’emplacement des passerelles PSTN lors de la planification de votre infrastructure voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="627ce-113">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="627ce-p103">Voici les principales questions à se poser. N’oubliez pas que les réponses à ces questions sont toutes interdépendantes.</span><span class="sxs-lookup"><span data-stu-id="627ce-p103">Here are the main questions to consider. Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="627ce-p104">Combien de passerelles PSTN sont nécessaires ? La réponse dépend du nombre d’utilisateurs, du nombre anticipé d’appels simultanés (charge du trafic) et du nombre de sites (chaque site a besoin d’une passerelle).</span><span class="sxs-lookup"><span data-stu-id="627ce-p104">How many PSTN gateways are needed? The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="627ce-p105">Quelle doit être la taille des passerelles ? La réponse dépend du nombre d’utilisateurs sur le site et de la charge du trafic.</span><span class="sxs-lookup"><span data-stu-id="627ce-p105">What size should the gateways be? The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="627ce-p106">Quel doit être l’emplacement des passerelles ? La réponse dépend en partie de la topologie et de la répartition géographique de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="627ce-p106">Where should the gateways be located? The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="627ce-122">Vous devriez également tenir compte des options au niveau de la topologie de votre passerelle (pour plus d’informations, voir la section Topologies de passerelles plus loin dans cette rubrique).</span><span class="sxs-lookup"><span data-stu-id="627ce-122">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="627ce-123">M:N Prise en charge des jonctions</span><span class="sxs-lookup"><span data-stu-id="627ce-123">M:N Trunk Support</span></span>

<span data-ttu-id="627ce-124">Les serveurs de médiation peuvent acheminer les appels via des passerelles multiples, des contrôleurs de frontière de session (SBC) fournis par des fournisseurs de services de téléphonie Internet ou une combinaison des deux.</span><span class="sxs-lookup"><span data-stu-id="627ce-124">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="627ce-125">De plus, plusieurs serveurs de médiation dans le pool peuvent interagir avec plusieurs passerelles.</span><span class="sxs-lookup"><span data-stu-id="627ce-125">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="627ce-126">L’itinéraire logique défini entre un serveur de médiation et une passerelle est appelé *jonction*.</span><span class="sxs-lookup"><span data-stu-id="627ce-126">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="627ce-127">Lorsqu’un utilisateur interne passe un appel RTC, la logique de routage sortant sur le pool frontal choisit la jonction à acheminer en dehors de toutes les combinaisons possibles pouvant être disponibles pour le routage de cet appel particulier.</span><span class="sxs-lookup"><span data-stu-id="627ce-127">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="627ce-128">Avec l’équilibrage de la charge DNS, si un appel ne parvient pas à joindre une passerelle en raison d’un problème avec un serveur de médiation particulier dans le pool, l’appel sera retenté sur un autre serveur de médiation du pool.</span><span class="sxs-lookup"><span data-stu-id="627ce-128">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="627ce-129">Pour plus d’informations sur la planification de plusieurs passerelles, voir [M :N jonction dans Lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="627ce-129">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="627ce-130">Pour plus d’informations sur les autres améliorations de routage sortant, consultez la rubrique [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="627ce-130">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="627ce-131">Topologies de passerelles</span><span class="sxs-lookup"><span data-stu-id="627ce-131">Gateway Topologies</span></span>

<span data-ttu-id="627ce-132">Quand vous examinez les questions fondamentales relatives au déploiement des passerelles, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="627ce-132">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="627ce-133">Comptez les sites à partir desquels vous souhaitez fournir la connectivité PSTN à l’aide de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="627ce-133">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="627ce-134">Évaluez le trafic sur chacun d’eux (nombre d’utilisateurs et nombre moyen d’appels par heure et par utilisateur).</span><span class="sxs-lookup"><span data-stu-id="627ce-134">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="627ce-135">Déployez une ou plusieurs passerelles sur chaque site pour gérer le trafic prévu.</span><span class="sxs-lookup"><span data-stu-id="627ce-135">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="627ce-136">La topologie de passerelles distribuées résultante est présentée à la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="627ce-136">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="627ce-137">**Topologie de passerelles distribuées**</span><span class="sxs-lookup"><span data-stu-id="627ce-137">**Distributed gateway topology**</span></span>

<span data-ttu-id="627ce-138">![Diagramme de topologie de passerelle distribuée](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagramme de topologie de passerelle distribuée")</span><span class="sxs-lookup"><span data-stu-id="627ce-138">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="627ce-p108">Avec cette topologie, les appels entre collaborateurs sur chaque site et entre les sites sont tous routés sur votre intranet. Les appels qui parviennent au réseau téléphonique commuté sont routés sur le réseau IP de l’entreprise vers les passerelles les plus proches de l’emplacement des numéros de destination. Mais que se passe-t-il si votre entreprise prend en charge des douzaines ou des centaines, voire des milliers de sites répartis sur plusieurs continents, comme c’est le cas de nombreuses institutions financières et grandes entreprises ? Dans ces cas, le déploiement d’une passerelle distincte sur chaque site n’est pas pratique.</span><span class="sxs-lookup"><span data-stu-id="627ce-p108">With this topology, calls among workers at each site and between sites are all routed over your intranet. Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do? In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="627ce-142">Pour résoudre ce problème, de nombreuses grandes entreprises préfèrent déployer un ou quelques grands sites centraux de téléphonie, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="627ce-142">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="627ce-143">**Topologie des sites centraux de téléphonie**</span><span class="sxs-lookup"><span data-stu-id="627ce-143">**Telephony central site topology**</span></span>

<span data-ttu-id="627ce-144">![Topologie de passerelle du centre de données](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topologie de passerelle du centre de données")</span><span class="sxs-lookup"><span data-stu-id="627ce-144">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="627ce-145">Dans cette topologie, plusieurs grandes passerelles sont suffisantes pour s’accommoder de la charge utilisateur prévue sont déployées sur chaque site central.</span><span class="sxs-lookup"><span data-stu-id="627ce-145">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="627ce-146">Tous les appels à destination des utilisateurs de l’entreprise sont transmis par le fournisseur de services téléphoniques de la société vers un site central.</span><span class="sxs-lookup"><span data-stu-id="627ce-146">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="627ce-147">La logique de routage sur le site central détermine si l’appel doit être acheminé via l’intranet ou le RTC.</span><span class="sxs-lookup"><span data-stu-id="627ce-147">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="627ce-148">Emplacement de la passerelle</span><span class="sxs-lookup"><span data-stu-id="627ce-148">Gateway Location</span></span>

<span data-ttu-id="627ce-p110">L’emplacement de la passerelle peut également déterminer les types de passerelles que vous choisissez et leur configuration. Il existe des douzaines de protocoles PSTN, dont aucun n’est un standard mondial. Si toutes vos passerelles se situent dans un seul pays ou une seule région, cela n’est pas un problème, mais si vous les placez dans plusieurs pays/régions, chacune d’elles doit être configurée en fonction des normes PSTN du pays ou de la région. De plus, les passerelles qui sont certifiées pour fonctionner, par exemple, au Canada, peuvent ne pas être certifiées en Inde, au Brésil ou dans l’Union européenne.</span><span class="sxs-lookup"><span data-stu-id="627ce-p110">Gateway location may also determine the types of gateways that you choose and how they are configured. There are dozens of PSTN protocols, none of which is a worldwide standard. If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region. Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="627ce-153">Taille et nombre des passerelles</span><span class="sxs-lookup"><span data-stu-id="627ce-153">Gateway Size and Number</span></span>

<span data-ttu-id="627ce-p111">La taille des passerelles PSTN que la plupart des entreprises envisagent de déployer peut aller de 2 et 960 ports. (Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.) Lors de l’estimation du nombre de ports requis dans votre entreprise, suivez les instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="627ce-p111">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports. (There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="627ce-p112">Les entreprises dont l’utilisation de la téléphonie est faible (un appel PSTN par utilisateur et par heure) doivent allouer un port pour 15 utilisateurs. Par exemple, si votre entreprise regroupe 20 utilisateurs, vous avez besoin d’une passerelle dotée de deux ports.</span><span class="sxs-lookup"><span data-stu-id="627ce-p112">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users. For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="627ce-p113">Les entreprises dont l’utilisation de la téléphonie est modérée (deux appels PSTN par utilisateur et par heure) doivent allouer un port pour 10 utilisateurs. Par exemple, si votre entreprise regroupe 100 utilisateurs, vous avez besoin d’un total de 10 ports alloués sur une ou plusieurs passerelles.</span><span class="sxs-lookup"><span data-stu-id="627ce-p113">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users. For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="627ce-p114">Les entreprises dont l’utilisation de la téléphonie est forte (trois appels PSTN ou plus par utilisateur et par heure) doivent allouer un port pour cinq utilisateurs. Par exemple, si votre entreprise regroupe 47 000 utilisateurs, vous avez besoin d’un total de 9 400 ports alloués sur au moins 10 passerelles de grande envergure.</span><span class="sxs-lookup"><span data-stu-id="627ce-p114">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users. For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="627ce-162">D’autres ports peuvent être acquis à mesure que le nombre d’utilisateurs ou la quantité de trafic augmente dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="627ce-162">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="627ce-p115">Pour un nombre donné d’utilisateurs à prendre en charge, vous pouvez choisir de déployer plusieurs passerelles de petite taille, ou bien un nombre inférieur de passerelles de grande taille. En règle générale, il est recommandé d’installer au moins deux passerelles dans l’entreprise pour garantir la disponibilité en cas de panne de l’une d’elles.</span><span class="sxs-lookup"><span data-stu-id="627ce-p115">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones. As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="627ce-165">Chaque passerelle PSTN que vous déployez doit disposer d’au moins un serveur de médiation correspondant.</span><span class="sxs-lookup"><span data-stu-id="627ce-165">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

