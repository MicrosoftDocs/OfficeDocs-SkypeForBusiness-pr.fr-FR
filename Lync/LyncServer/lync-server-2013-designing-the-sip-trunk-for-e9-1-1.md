---
title: 'Lync Server 2013: conception du Trunk SIP pour E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bee3985efd3510b62bfe43b3aa5742f63679093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="5eddc-102">Designing the SIP Trunk pour E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5eddc-102">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5eddc-103">_**Dernière modification de la rubrique:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="5eddc-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="5eddc-104">Lync Server utilise des lignes SIP pour connecter un appel d’urgence au fournisseur de services E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="5eddc-104">Lync Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="5eddc-105">Vous pouvez configurer des jonctions SIP de services d’urgence pour le service E9-1-1 au niveau d’un site central, de plusieurs sites centraux ou de chaque site de succursale.</span><span class="sxs-lookup"><span data-stu-id="5eddc-105">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="5eddc-106">Cependant, si la liaison de réseau étendu (WAN) entre le site de l’appelant et le site qui héberge la jonction SIP de service d’urgence n’est pas disponible, tout appel passé par un utilisateur au niveau du site déconnecté nécessitera un enregistrement d’utilisation téléphonique spécifique dans la stratégie de voix de l’utilisateur qui acheminera l’appel au centre d’intervention en cas d’appels d’urgence via la passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="5eddc-106">However, if the WAN link between the caller’s site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user’s voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="5eddc-107">Il en va de même si les limites relatives aux appels simultanés du service Contrôle d’admission des appels sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="5eddc-107">The same is true if call admission control concurrent call limits are in effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5eddc-108">Il existe deux façons d’implémenter une ligne SIP dans un environnement serveur Lync:</span><span class="sxs-lookup"><span data-stu-id="5eddc-108">There are two ways to implement a SIP trunk in a Lync Server environment:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="5eddc-109">Utiliser des serveurs de médiation multi-résidents qui utilisent leurs interfaces routées vers l’extérieur pour communiquer avec le fournisseur de Trunks SIP.</span><span class="sxs-lookup"><span data-stu-id="5eddc-109">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span></P>
> <LI>
> <P><span data-ttu-id="5eddc-110">Utilisez un contrôleur de bordure de session (SBC) local pour fournir un point de délimitation sécurisé entre les serveurs de médiation et les services du fournisseur de Trunks SIP.</span><span class="sxs-lookup"><span data-stu-id="5eddc-110">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider’s services.</span></span></P></LI></UL><span data-ttu-id="5eddc-111">Si vous choisissez cette dernière méthode, assurez-vous que la marque et le modèle du contrôleur SBC que vous choisissez ont été certifiés et que celui-ci prend en charge le transfert des données d’emplacement PIDF-LO (Presence Information Data Format Location Object) dans le cadre de sa requête SIP INVITE.</span><span class="sxs-lookup"><span data-stu-id="5eddc-111">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="5eddc-112">Dans le cas contraire, les appels parviennent au fournisseur de services d’urgence sans leurs informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="5eddc-112">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="5eddc-113">Pour plus d’informations sur la certification SBCs, voir la section «infrastructure qualifie <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>pour Microsoft Lync» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="5eddc-113">For details about certified SBCs, see "Infrastructure Qualified for Microsoft Lync" at <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>.</span></span><BR><span data-ttu-id="5eddc-114">Les fournisseurs de services E9-1-1 vous permettent d’accéder à une paire de contrôleurs SBC à des fins de redondance.</span><span class="sxs-lookup"><span data-stu-id="5eddc-114">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="5eddc-115">Vous devez prendre plusieurs décisions concernant la topologie du serveur de médiation et la configuration de l’acheminement des appels.</span><span class="sxs-lookup"><span data-stu-id="5eddc-115">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="5eddc-116">Allez-vous traiter les deux contrôleurs SBC comme des homologues égaux et utiliser le routage par tourniquet (round robin) pour les appels qu’ils s’échangent, ou allez-vous désigner l’un des contrôleurs SBC en tant que serveur principal et l’autre en tant que serveur secondaire ?</span><span class="sxs-lookup"><span data-stu-id="5eddc-116">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>



</div>

<span data-ttu-id="5eddc-117">Pour plus d’informations sur le déploiement d’une connexion SIP dans Lync Server, voir [comment implémenter le trunking SIP dans Lync server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="5eddc-117">For details about deploying a SIP trunk in Lync Server, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span> <span data-ttu-id="5eddc-118">Pour faciliter le déploiement de jonctions SIP pour E9-1-1, répondez d’abord aux questions suivantes.</span><span class="sxs-lookup"><span data-stu-id="5eddc-118">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>

  - <span data-ttu-id="5eddc-119">**Devez-vous déployer la jonction SIP sur une connexion en bail dédiée ou une connexion Internet partagée ?**</span><span class="sxs-lookup"><span data-stu-id="5eddc-119">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>  
    <span data-ttu-id="5eddc-p105">Il est important que les appels d’urgence se connectent en permanence. Une ligne dédiée fournit une connexion qui n’est pas préemptée par un autre trafic réseau. En outre, elle permet d’implémenter la qualité de service (QoS). N’oubliez pas que si vous vous connectez à des fournisseurs de services d’urgence via le réseau Internet public et si vous devez garantir la confidentialité des appels d’urgence, un chiffrement IPsec est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5eddc-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span>

<!-- end list -->

  - <span data-ttu-id="5eddc-123">**Votre déploiement E9-1-1 est-il conçu pour la tolérance au désastre?**</span><span class="sxs-lookup"><span data-stu-id="5eddc-123">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>  
    <span data-ttu-id="5eddc-124">Puisqu’il s’agit d’une solution d’urgence, la résistance est importante.</span><span class="sxs-lookup"><span data-stu-id="5eddc-124">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="5eddc-125">Déployez vos serveurs de médiation principaux et secondaires et les Trunks SIP dans les emplacements tolérants aux sinistres.</span><span class="sxs-lookup"><span data-stu-id="5eddc-125">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="5eddc-126">Il peut s’avérer utile de déployer votre serveur de médiation principal le plus proche des utilisateurs qu’il prend en charge, et d’acheminer les appels de basculement par le biais du serveur de médiation secondaire (situé dans un autre emplacement géographique).</span><span class="sxs-lookup"><span data-stu-id="5eddc-126">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span>

<!-- end list -->

  - <span data-ttu-id="5eddc-127">**Devez-vous déployer une jonction SIP (Session Initiation Protocol) distincte pour chaque succursale ?**</span><span class="sxs-lookup"><span data-stu-id="5eddc-127">**Should you deploy a separate SIP trunk for each branch office?**</span></span>  
    <span data-ttu-id="5eddc-128">Lync Server offre plusieurs stratégies de gestion de la résilience vocale dans les succursales, notamment: utilisation de réseaux de données résilients, déploiement d’une ligne SIP dans chaque succursale ou transfert d’appels vers la passerelle locale au cours des pannes.</span><span class="sxs-lookup"><span data-stu-id="5eddc-128">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="5eddc-129">Pour plus d’informations, voir [trunking SIP site dans Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="5eddc-129">For details, see [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="5eddc-130">**Le contrôle d’admission des appels est-il activé ?**</span><span class="sxs-lookup"><span data-stu-id="5eddc-130">**Is call admission control (CAC) enabled?**</span></span>  
    <span data-ttu-id="5eddc-131">Lync Server ne gère pas les appels d’urgence de la même manière que les appels ordinaires.</span><span class="sxs-lookup"><span data-stu-id="5eddc-131">Lync Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="5eddc-132">Pour cette raison, la gestion de la bande passante ou le service Contrôle d’admission des appels peut avoir un impact négatif sur une configuration E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="5eddc-132">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="5eddc-133">Les appels d’urgence sont bloqués ou acheminés vers la passerelle RTC locale si un service Contrôle d’admission des appels est activé et si la limite configurée est dépassée sur une liaison où les appels d’urgence sont acheminés.</span><span class="sxs-lookup"><span data-stu-id="5eddc-133">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="5eddc-134">Comme indiqué précédemment dans cette rubrique, ce type d’appel ne dispose pas de données d’emplacement et doit être acheminé manuellement vers le centre d’intervention en cas d’appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="5eddc-134">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

