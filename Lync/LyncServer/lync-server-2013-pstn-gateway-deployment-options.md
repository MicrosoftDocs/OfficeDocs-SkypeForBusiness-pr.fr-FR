---
title: 'Lync Server 2013 : Options de déploiement de passerelle RTC'
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
ms.openlocfilehash: 5b2f3cd153a6dc8d101f44a3f087f0ccedfa9bf7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="f2218-102">Options de déploiement de passerelle RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2218-102">PSTN gateway deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2218-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f2218-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="f2218-104">Passerelles RTC</span><span class="sxs-lookup"><span data-stu-id="f2218-104">PSTN Gateways</span></span>

<span data-ttu-id="f2218-105">Les passerelles de réseau téléphonique commuté (PSTN) sont des composants matériels tiers qui convertissent le signalement et le contenu multimédia entre l’infrastructure vocale d’entreprise et le RTC, directement ou par le biais d’une connexion de lignes SIP.</span><span class="sxs-lookup"><span data-stu-id="f2218-105">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="f2218-106">Dans chaque topologie, la passerelle arrête le RTC.</span><span class="sxs-lookup"><span data-stu-id="f2218-106">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="f2218-107">La passerelle est isolée dans son propre sous-réseau et est connectée au réseau d’entreprise par le biais du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="f2218-107">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="f2218-108">En règle générale, une entreprise avec plusieurs sites déploie une ou plusieurs passerelles sur chaque site.</span><span class="sxs-lookup"><span data-stu-id="f2218-108">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="f2218-109">Les sites de succursale peuvent se connecter au RTC par le biais d’une passerelle ou d’une unité de branchement survivant qui combine les passerelles et les serveurs dans une seule boîte.</span><span class="sxs-lookup"><span data-stu-id="f2218-109">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="f2218-110">Si les sites de succursales utilisent une passerelle, un serveur d’inscription et de médiation sont requis sur le site, sauf si la liaison WAN est résiliente.</span><span class="sxs-lookup"><span data-stu-id="f2218-110">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="f2218-111">Un ou plusieurs serveurs de médiation, qui sont colocalisés sur des serveurs frontaux, peuvent router les appels pour les passerelles d’une ou plusieurs sur chaque site.</span><span class="sxs-lookup"><span data-stu-id="f2218-111">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="f2218-112">Nous vous recommandons d’utiliser le Bureau d’enregistrement, le serveur de médiation et la passerelle requis sur le site comme une unité de branchement Survivable.</span><span class="sxs-lookup"><span data-stu-id="f2218-112">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="f2218-113">Le nombre, la taille et l’emplacement des passerelles RTC est peut-être la décision la plus importante et onéreuse lors de la planification de l’infrastructure vocale de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="f2218-113">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="f2218-114">Voici les principales questions à prendre en considération.</span><span class="sxs-lookup"><span data-stu-id="f2218-114">Here are the main questions to consider.</span></span> <span data-ttu-id="f2218-115">Gardez à l’esprit que les réponses à ces questions sont interdépendantes.</span><span class="sxs-lookup"><span data-stu-id="f2218-115">Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="f2218-116">Combien de passerelles RTC sont-elles nécessaires ?</span><span class="sxs-lookup"><span data-stu-id="f2218-116">How many PSTN gateways are needed?</span></span> <span data-ttu-id="f2218-117">La réponse dépend du nombre d’utilisateurs, du nombre d’appels simultanés (chargement du trafic) et du nombre de sites (chaque site en nécessite une).</span><span class="sxs-lookup"><span data-stu-id="f2218-117">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="f2218-118">Quelle est la taille des passerelles ?</span><span class="sxs-lookup"><span data-stu-id="f2218-118">What size should the gateways be?</span></span> <span data-ttu-id="f2218-119">La réponse dépend du nombre d’utilisateurs au niveau du site et du chargement du trafic.</span><span class="sxs-lookup"><span data-stu-id="f2218-119">The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="f2218-120">Où se trouvent les passerelles ?</span><span class="sxs-lookup"><span data-stu-id="f2218-120">Where should the gateways be located?</span></span> <span data-ttu-id="f2218-121">La réponse dépend en partie de la topologie et en partie de la distribution géographique de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f2218-121">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="f2218-122">Vous devez également tenir compte des options de topologie de votre passerelle (pour plus de détails, voir topologies de passerelle plus loin dans cette rubrique).</span><span class="sxs-lookup"><span data-stu-id="f2218-122">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="f2218-123">M:N Prise en charge des jonctions</span><span class="sxs-lookup"><span data-stu-id="f2218-123">M:N Trunk Support</span></span>

<span data-ttu-id="f2218-124">Les serveurs de médiation peuvent acheminer les appels par le biais de plusieurs passerelles, contrôleurs de frontière de session (SBCs) fournis par des fournisseurs de services de téléphonie Internet ou d’une combinaison des deux.</span><span class="sxs-lookup"><span data-stu-id="f2218-124">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="f2218-125">Par ailleurs, plusieurs serveurs de médiation du pool peuvent interagir avec plusieurs passerelles.</span><span class="sxs-lookup"><span data-stu-id="f2218-125">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="f2218-126">L’itinéraire logique défini entre un serveur de médiation et une passerelle est appelé *Trunk*.</span><span class="sxs-lookup"><span data-stu-id="f2218-126">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="f2218-127">Lorsqu’un utilisateur interne place un appel RTC, la logique de routage sortante du pool frontal détermine le Trunk à transférer au-delà de toutes les combinaisons possibles qui peuvent être disponibles pour le routage d’un appel particulier.</span><span class="sxs-lookup"><span data-stu-id="f2218-127">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="f2218-128">En cas d’équilibrage de la charge DNS, si un appel ne parvient pas à accéder à une passerelle en raison d’un problème lié à un serveur de médiation particulier dans le pool, l’appel est répété vers un autre serveur de médiation du pool.</span><span class="sxs-lookup"><span data-stu-id="f2218-128">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="f2218-129">Pour plus d’informations sur la planification de plusieurs passerelles, voir [M :N Trunk dans Lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="f2218-129">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="f2218-130">Pour plus d’informations sur les autres améliorations du routage sortant, voir [itinéraires vocaux dans Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="f2218-130">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="f2218-131">Topologies de passerelle</span><span class="sxs-lookup"><span data-stu-id="f2218-131">Gateway Topologies</span></span>

<span data-ttu-id="f2218-132">Lorsque vous prenez en considération les questions fondamentales du déploiement de la passerelle, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f2218-132">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="f2218-133">Déterminez les sites pour lesquels vous souhaitez fournir une connectivité PSTN en utilisant Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f2218-133">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="f2218-134">Évaluez le trafic sur chaque site (nombre d’utilisateurs et nombre moyen d’appels par heure par utilisateur).</span><span class="sxs-lookup"><span data-stu-id="f2218-134">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="f2218-135">Déploiement d’une ou plusieurs passerelles sur chaque site pour gérer le trafic anticipé.</span><span class="sxs-lookup"><span data-stu-id="f2218-135">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="f2218-136">La topologie de passerelle distribuée qui en résulte est illustrée dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="f2218-136">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="f2218-137">**Topologie de passerelle distribuée**</span><span class="sxs-lookup"><span data-stu-id="f2218-137">**Distributed gateway topology**</span></span>

<span data-ttu-id="f2218-138">![Diagramme de topologie de passerelle distribuée](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagramme de topologie de passerelle distribuée")</span><span class="sxs-lookup"><span data-stu-id="f2218-138">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="f2218-139">Avec cette topologie, les appels entre les travailleurs sur chaque site et entre les sites sont tous routés par le biais de votre intranet.</span><span class="sxs-lookup"><span data-stu-id="f2218-139">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="f2218-140">Les appels vers le RTC sont routés via le réseau IP d’entreprise vers les passerelles les plus proches de l’emplacement des numéros de destination. Mais si votre organisation prend en charge des douzaines ou des centaines, voire des milliers de sites disséminés sur un ou plusieurs continents, le nombre d’institutions financières et d’autres grandes entreprises est important.</span><span class="sxs-lookup"><span data-stu-id="f2218-140">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="f2218-141">Dans ce cas, le déploiement d’une passerelle séparée sur chaque site n’est pas pratique.</span><span class="sxs-lookup"><span data-stu-id="f2218-141">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="f2218-142">Pour résoudre ce problème, de nombreuses entreprises de grande taille préfèrent le déploiement d’un ou de plusieurs sites centraux de téléphonie de grande taille, comme illustré dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f2218-142">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="f2218-143">**Topologie de site central de téléphonie**</span><span class="sxs-lookup"><span data-stu-id="f2218-143">**Telephony central site topology**</span></span>

<span data-ttu-id="f2218-144">![Topologie de la passerelle du centre de données](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topologie de la passerelle du centre de données")</span><span class="sxs-lookup"><span data-stu-id="f2218-144">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="f2218-145">Dans cette topologie, plusieurs passerelles de grande taille suffisantes pour s’adapter à la charge d’utilisateurs prévue sont déployées sur chaque site central.</span><span class="sxs-lookup"><span data-stu-id="f2218-145">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="f2218-146">Tous les appels vers des utilisateurs au sein de l’entreprise sont transférés par le fournisseur de services de téléphonie de l’entreprise à un site central.</span><span class="sxs-lookup"><span data-stu-id="f2218-146">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="f2218-147">La logique de routage sur le site central détermine si l’appel doit être routé par le biais de l’intranet ou du RTC.</span><span class="sxs-lookup"><span data-stu-id="f2218-147">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="f2218-148">Emplacement de la passerelle</span><span class="sxs-lookup"><span data-stu-id="f2218-148">Gateway Location</span></span>

<span data-ttu-id="f2218-149">L’emplacement de la passerelle détermine également les types de passerelles que vous choisissez et la manière dont ils sont configurés.</span><span class="sxs-lookup"><span data-stu-id="f2218-149">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="f2218-150">Il existe des dizaines de protocoles RTC qui ne constituent aucune norme internationale.</span><span class="sxs-lookup"><span data-stu-id="f2218-150">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="f2218-151">S’il ne s’agit pas de votre passerelle, il n’y a pas de problème, mais si vous trouvez des passerelles dans plusieurs pays/régions, chacune d’elles doit être configurée conformément aux normes RTC de ce pays/cette région.</span><span class="sxs-lookup"><span data-stu-id="f2218-151">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="f2218-152">Par ailleurs, les passerelles certifiées pour le fonctionnement, par exemple le Canada, peuvent ne pas être certifiées en Inde, au Brésil ou en Union européenne.</span><span class="sxs-lookup"><span data-stu-id="f2218-152">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="f2218-153">Taille et nombre de la passerelle</span><span class="sxs-lookup"><span data-stu-id="f2218-153">Gateway Size and Number</span></span>

<span data-ttu-id="f2218-154">Les passerelles RTC dont la plupart des organisations envisageront de déployer la plage de 2 à la taille des ports 960.</span><span class="sxs-lookup"><span data-stu-id="f2218-154">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="f2218-155">(Il y a encore plus de passerelles, mais elles sont principalement utilisées par les fournisseurs de services de téléphonie.) Lorsque vous évaluez le nombre de ports requis par votre organisation, vous devez suivre les instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="f2218-155">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="f2218-156">Les organisations ayant une utilisation du service de téléphonie léger (un appel RTC par utilisateur par heure) doivent allouer un port pour tous les 15 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f2218-156">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="f2218-157">Par exemple, si vous avez 20 utilisateurs, vous aurez besoin d’une passerelle avec deux ports.</span><span class="sxs-lookup"><span data-stu-id="f2218-157">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="f2218-158">Les organisations présentant une utilisation modérée de la téléphonie (deux appels RTC par utilisateur et par heure) doivent allouer un port pour chaque 10 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f2218-158">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="f2218-159">Par exemple, si vous avez des utilisateurs 100, vous aurez besoin d’un total de 10 ports alloués à une ou plusieurs passerelles.</span><span class="sxs-lookup"><span data-stu-id="f2218-159">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="f2218-160">Les organisations ayant une utilisation importante de la téléphonie (au moins trois appels RTC par utilisateur et par heure) doivent allouer un port pour chaque cinquième utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f2218-160">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="f2218-161">Par exemple, si vous avez des utilisateurs 47 000, vous aurez besoin d’un total de ports 9 400 alloués entre au moins 10 passerelles de grande taille.</span><span class="sxs-lookup"><span data-stu-id="f2218-161">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="f2218-162">Des ports supplémentaires peuvent être acquis au fur et à mesure de l’augmentation du nombre d’utilisateurs ou du volume de trafic au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f2218-162">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="f2218-163">Pour tout nombre d’utilisateurs que vous devez prendre en charge, vous avez le choix entre le déploiement de plus petit, de passerelles plus grandes ou plus petites.</span><span class="sxs-lookup"><span data-stu-id="f2218-163">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="f2218-164">En règle générale, un minimum de deux passerelles pour une organisation est recommandé pour garantir la disponibilité en cas d’échec d’une passerelle.</span><span class="sxs-lookup"><span data-stu-id="f2218-164">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="f2218-165">Chaque passerelle RTC que vous déployez doit avoir au moins un serveur de médiation correspondant.</span><span class="sxs-lookup"><span data-stu-id="f2218-165">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

