---
title: Sites Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2e5dc3323ad14f02a5b24258878512707f66f19
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="12f53-102">Sites Lync Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f53-102">Lync Server sites for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12f53-103">_**Dernière modification de la rubrique :** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="12f53-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="12f53-104">Dans Lync Server, vous définissez des *sites* sur votre réseau qui contiennent des composants serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="12f53-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="12f53-105">Un site désigne un ensemble d’ordinateurs connectés comme il se doit par un réseau haut débit à faible latence, par exemple, un réseau local unique (LAN) ou bien deux réseaux connectés via un réseau haut débit à fibre optique.</span><span class="sxs-lookup"><span data-stu-id="12f53-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="12f53-106">Notez que les sites serveur Lync constituent un concept distinct des sites services de domaine Active Directory et des sites Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="12f53-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="12f53-107">Les sites de votre serveur Lync n’ont pas besoin de correspondre à vos sites Active Directory.</span><span class="sxs-lookup"><span data-stu-id="12f53-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="12f53-108">Types de sites</span><span class="sxs-lookup"><span data-stu-id="12f53-108">Site Types</span></span>

<span data-ttu-id="12f53-109">Chaque site est un *site central*contenant au moins un pool frontal ou un serveur Standard Edition Server ou un *site de succursale*.</span><span class="sxs-lookup"><span data-stu-id="12f53-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="12f53-110">Chaque site de filiale est associé à un seul site central, et les utilisateurs du site de succursale obtiennent la plupart des fonctionnalités de Lync Server sur les serveurs du site central associé.</span><span class="sxs-lookup"><span data-stu-id="12f53-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="12f53-111">Chaque site de filiale contient l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="12f53-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="12f53-112">Un *appareil de branchement survivant (SBA)*, qui est un serveur de Blades standard avec un bureau d’enregistrement de serveurs Lync et un serveur de médiation exécuté sur Windows Server.</span><span class="sxs-lookup"><span data-stu-id="12f53-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="12f53-113">L’unité de branchement Survivable comporte également une passerelle RTC (réseau téléphonique commuté).</span><span class="sxs-lookup"><span data-stu-id="12f53-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="12f53-114">L’unité de branchement survivant est conçue pour les sites de succursale entre 25 et 1000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="12f53-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="12f53-115">Un *serveur de succursales survivant (SBS)*, qui est un serveur exécutant Windows Server qui répond à la configuration matérielle requise, et sur lequel sont installés le logiciel serveur du Bureau d’enregistrement et de médiation de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12f53-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="12f53-116">Il doit se connecter à une passerelle PSTN ou à une jonction SIP à un fournisseur de services téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="12f53-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="12f53-117">Le serveur de succursales survivant est conçu pour les sites de succursale entre les utilisateurs 1000 et 5000.</span><span class="sxs-lookup"><span data-stu-id="12f53-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="12f53-118">Passerelle RTC et, éventuellement, *serveur de médiation*.</span><span class="sxs-lookup"><span data-stu-id="12f53-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="12f53-119">Pour plus d’informations sur ces rôles de serveur, voir [rôles de serveur dans Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="12f53-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="12f53-120">Une succursale disposant d’une liaison réseau étendu (WAN) fiable vers un site central peut utiliser la troisième option : une passerelle RTC et éventuellement un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="12f53-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="12f53-121">Les sites de succursales dotés de liens moins résilients doivent utiliser un appareil de succursales ou un serveur de succursales Survivables, qui fournit la résilience en cas de panne du réseau étendu.</span><span class="sxs-lookup"><span data-stu-id="12f53-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="12f53-122">Par exemple, dans le cas d’un site disposant d’une unité de succursale ou d’un serveur de succursale survivant, les utilisateurs peuvent quand même passer et recevoir des appels voix d’entreprise si le WAN qui connecte le site de la succursale au site central est arrêté.</span><span class="sxs-lookup"><span data-stu-id="12f53-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="12f53-123">Pour plus d’informations sur l’appareil de succursale survivant, le serveur de succursales survivant et la résilience, voir [planification de la résilience vocale d’entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="12f53-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="12f53-124">Topologies de site</span><span class="sxs-lookup"><span data-stu-id="12f53-124">Site Topologies</span></span>

<span data-ttu-id="12f53-125">Votre déploiement doit inclure au moins un site central et peut inclure zéro sur plusieurs sites de succursales.</span><span class="sxs-lookup"><span data-stu-id="12f53-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="12f53-126">Chaque site de filiale est affilié à un site central.</span><span class="sxs-lookup"><span data-stu-id="12f53-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="12f53-127">Le site central fournit les services serveur Lync au site de succursale qui ne sont pas hébergés localement sur le site de la succursale, tels que la présence et la Conférence.</span><span class="sxs-lookup"><span data-stu-id="12f53-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="12f53-128">Si vous disposez de plusieurs sites, vous pouvez associer les pools front-end sur différents sites pour activer la fonction de reprise après sinistre.</span><span class="sxs-lookup"><span data-stu-id="12f53-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="12f53-129">Pour plus d’informations, voir [prise en charge de la haute disponibilité et de la reprise après sinistre dans Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span><span class="sxs-lookup"><span data-stu-id="12f53-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12f53-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="12f53-130">See Also</span></span>


[<span data-ttu-id="12f53-131">Rôles serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f53-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="12f53-132">Prise en charge de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f53-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="12f53-133">Planification de la résistance Voix Entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f53-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

