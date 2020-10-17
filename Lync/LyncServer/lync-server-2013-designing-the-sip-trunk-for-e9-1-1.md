---
title: 'Lync Server 2013 : conception de la jonction SIP pour E9-1-1'
description: 'Lync Server 2013 : conception de la jonction SIP pour E9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ced3c92cb14739367c4e54da933a536cb66deb08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542600"
---
# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="55925-103">Conception de la jonction SIP pour E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55925-103">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55925-104">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="55925-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="55925-105">Lync Server utilise des jonctions SIP pour connecter un appel d’urgence au fournisseur de services E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="55925-105">Lync Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="55925-106">Vous pouvez configurer des jonctions SIP de services d’urgence pour le service E9-1-1 au niveau d’un site central, de plusieurs sites centraux ou de chaque site de succursale.</span><span class="sxs-lookup"><span data-stu-id="55925-106">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="55925-107">Toutefois, si la liaison de réseau étendu (WAN) entre le site de l’appelant et le site qui héberge la jonction SIP de service d’urgence n’est pas disponible, tout appel passé par un utilisateur au niveau du site déconnecté nécessitera un enregistrement d’utilisation téléphonique spécifique dans la stratégie de voix de l’utilisateur qui acheminera l’appel au centre d’intervention en cas d’appels d’urgence via la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="55925-107">However, if the WAN link between the caller’s site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user’s voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="55925-108">Il en va de même si les limites relatives aux appels simultanés du service Contrôle d’admission des appels sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="55925-108">The same is true if call admission control concurrent call limits are in effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55925-109">Il existe deux façons d’implémenter une jonction SIP dans un environnement Lync Server :</span><span class="sxs-lookup"><span data-stu-id="55925-109">There are two ways to implement a SIP trunk in a Lync Server environment:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="55925-110">Utilisez des serveurs de médiation multirésidents qui utilisent leurs interfaces routées publiquement vers l’extérieur pour communiquer avec le fournisseur de jonctions SIP.</span><span class="sxs-lookup"><span data-stu-id="55925-110">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span></P>
> <LI>
> <P><span data-ttu-id="55925-111">Utilisez un contrôleur de frontière de session (SBC) local pour fournir un point de démarcation sécurisé entre les serveurs de médiation et les services du fournisseur de jonctions SIP.</span><span class="sxs-lookup"><span data-stu-id="55925-111">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider’s services.</span></span></P></LI></UL><span data-ttu-id="55925-112">Si vous choisissez cette dernière méthode, assurez-vous que la marque et le modèle du contrôleur SBC que vous choisissez ont été certifiés et que celui-ci prend en charge le transfert des données d’emplacement PIDF-LO (Presence Information Data Format Location Object) dans le cadre de sa requête SIP INVITE.</span><span class="sxs-lookup"><span data-stu-id="55925-112">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="55925-113">Dans le cas contraire, les appels arrivent au fournisseur de services d’urgence sans leurs informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="55925-113">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="55925-114">Pour plus d’informations sur les contrôleurs SBC certifiés, voir « infrastructure Qualified for Microsoft Lync » à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A> .</span><span class="sxs-lookup"><span data-stu-id="55925-114">For details about certified SBCs, see "Infrastructure Qualified for Microsoft Lync" at <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>.</span></span><BR><span data-ttu-id="55925-115">Les fournisseurs de services E9-1-1 vous permettent d’accéder à une paire de contrôleurs SBC à des fins de redondance.</span><span class="sxs-lookup"><span data-stu-id="55925-115">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="55925-116">Vous devez prendre plusieurs décisions concernant la topologie du serveur de médiation et la configuration du routage des appels.</span><span class="sxs-lookup"><span data-stu-id="55925-116">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="55925-117">Allez-vous traiter les deux contrôleurs SBC comme des homologues égaux et utiliser le routage par tourniquet (round robin) pour les appels qu’ils s’échangent, ou allez-vous désigner l’un des contrôleurs SBC en tant que serveur principal et l’autre en tant que serveur secondaire ?</span><span class="sxs-lookup"><span data-stu-id="55925-117">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>



</div>

<span data-ttu-id="55925-118">Pour plus d’informations sur le déploiement d’une jonction SIP dans Lync Server, voir [comment implémenter la jonction SIP dans Lync server 2013 ?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="55925-118">For details about deploying a SIP trunk in Lync Server, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span> <span data-ttu-id="55925-119">Pour faciliter le déploiement de jonctions SIP pour E9-1-1, répondez d’abord aux questions suivantes.</span><span class="sxs-lookup"><span data-stu-id="55925-119">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>

  - <span data-ttu-id="55925-120">**Devez-vous déployer la jonction SIP sur une connexion en bail dédiée ou une connexion Internet partagée ?**</span><span class="sxs-lookup"><span data-stu-id="55925-120">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>  
    <span data-ttu-id="55925-p105">Il est important que les appels d’urgence se connectent en permanence. Une ligne dédiée fournit une connexion qui n’est pas préemptée par un autre trafic réseau. En outre, elle permet d’implémenter la qualité de service (QoS). N’oubliez pas que si vous vous connectez à des fournisseurs de services d’urgence via le réseau Internet public et si vous devez garantir la confidentialité des appels d’urgence, un chiffrement IPsec est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="55925-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span>

<!-- end list -->

  - <span data-ttu-id="55925-124">**Votre déploiement E9-1-1 est-il conçu pour la tolérance aux catastrophes ?**</span><span class="sxs-lookup"><span data-stu-id="55925-124">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>  
    <span data-ttu-id="55925-125">Puisqu’il s’agit d’une solution d’urgence, la résilience est importante.</span><span class="sxs-lookup"><span data-stu-id="55925-125">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="55925-126">Déployez vos serveurs de médiation principaux et secondaires et les jonctions SIP dans des emplacements tolérants aux sinistres.</span><span class="sxs-lookup"><span data-stu-id="55925-126">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="55925-127">Il est recommandé de déployer votre serveur de médiation le plus proche des utilisateurs pris en charge et d’acheminer les appels de basculement via le serveur de médiation secondaire (situé dans un autre emplacement géographique).</span><span class="sxs-lookup"><span data-stu-id="55925-127">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span>

<!-- end list -->

  - <span data-ttu-id="55925-128">**Devez-vous déployer une jonction SIP distincte pour chaque succursale ?**</span><span class="sxs-lookup"><span data-stu-id="55925-128">**Should you deploy a separate SIP trunk for each branch office?**</span></span>  
    <span data-ttu-id="55925-129">Lync Server offre plusieurs stratégies de gestion de la résistance des communications vocales dans les succursales, notamment : les réseaux de données résistants, le déploiement d’une jonction SIP au niveau de chaque succursale ou le transfert d’appels vers la passerelle locale pendant les pannes.</span><span class="sxs-lookup"><span data-stu-id="55925-129">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="55925-130">Pour plus d’informations, reportez-vous à la rubrique [Branch site SIP Trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="55925-130">For details, see [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="55925-131">**Le contrôle d’admission des appels (CAC) est-il activé ?**</span><span class="sxs-lookup"><span data-stu-id="55925-131">**Is call admission control (CAC) enabled?**</span></span>  
    <span data-ttu-id="55925-132">Lync Server ne gère pas les appels d’urgence de la même manière qu’un appel ordinaire.</span><span class="sxs-lookup"><span data-stu-id="55925-132">Lync Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="55925-133">Pour cette raison, la gestion de la bande passante ou le service Contrôle d’admission des appels peut avoir un impact négatif sur une configuration E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="55925-133">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="55925-134">Les appels d’urgence sont bloqués ou acheminés vers la passerelle PSTN locale si un service Contrôle d’admission des appels est activé et si la limite configurée est dépassée sur une liaison où les appels d’urgence sont acheminés.</span><span class="sxs-lookup"><span data-stu-id="55925-134">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="55925-135">Comme indiqué précédemment dans cette rubrique, ce type d’appel ne dispose pas de données d’emplacement et doit être acheminé manuellement vers le centre d’intervention en cas d’appels d’urgence.</span><span class="sxs-lookup"><span data-stu-id="55925-135">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

