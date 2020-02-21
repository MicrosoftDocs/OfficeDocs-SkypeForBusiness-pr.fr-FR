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
ms.openlocfilehash: 37843e85f5da250b3cb3d8e0fa4cdccdf506176d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="f0936-102">Sites Lync Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0936-102">Lync Server sites for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0936-103">_**Dernière modification de la rubrique :** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="f0936-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="f0936-104">Dans Lync Server, vous définissez des *sites* sur votre réseau qui contiennent des composants Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0936-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="f0936-105">Un site désigne un ensemble d’ordinateurs connectés comme il se doit par un réseau haut débit à faible latence, par exemple, un réseau local unique (LAN) ou bien deux réseaux connectés via un réseau haut débit à fibre optique.</span><span class="sxs-lookup"><span data-stu-id="f0936-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="f0936-106">Notez que les sites Lync Server constituent un concept distinct des sites des services de domaine Active Directory et des sites Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="f0936-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="f0936-107">Vos sites Lync Server n’ont pas besoin de correspondre à vos sites Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f0936-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="f0936-108">Types de site</span><span class="sxs-lookup"><span data-stu-id="f0936-108">Site Types</span></span>

<span data-ttu-id="f0936-109">Chaque site est soit un *site central*, qui contient au moins un pool frontal ou un serveur Standard Edition, soit un *site de succursale*.</span><span class="sxs-lookup"><span data-stu-id="f0936-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="f0936-110">Chaque site de succursale est associé à un site central exactement et les utilisateurs du site de succursale bénéficient de la plupart de leurs fonctionnalités Lync Server à partir des serveurs sur le site central associé.</span><span class="sxs-lookup"><span data-stu-id="f0936-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="f0936-111">Chaque site de succursale contient l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f0936-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="f0936-112">*Survivable Branch Appliance (SBA)*, qui est un serveur lame standard avec un serveur d’inscriptions Lync Server et un serveur de médiation s’exécutant sur Windows Server.</span><span class="sxs-lookup"><span data-stu-id="f0936-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="f0936-113">Le Survivable Branch Appliance contient également une passerelle RTC (réseau téléphonique commuté).</span><span class="sxs-lookup"><span data-stu-id="f0936-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="f0936-114">Le Survivable Branch Appliance est conçu pour les sites de succursale comportant entre 25 et 1000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f0936-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="f0936-115">Un *serveur Survivable Branch Server (SBS)*, qui est un serveur exécutant Windows Server qui répond à la configuration matérielle requise et sur lequel le logiciel de serveur d’inscriptions et de médiation Lync Server est installé.</span><span class="sxs-lookup"><span data-stu-id="f0936-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="f0936-116">Il doit se connecter à une passerelle PSTN ou à une jonction SIP à un fournisseur de service téléphonique.</span><span class="sxs-lookup"><span data-stu-id="f0936-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="f0936-117">Le serveur Survivable Branch Server est conçu pour les sites de succursale comptant entre 1 000 et 5 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f0936-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="f0936-118">Une passerelle PSTN et, éventuellement, un *serveur de médiation*.</span><span class="sxs-lookup"><span data-stu-id="f0936-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="f0936-119">Pour plus d’informations sur ce rôle et sur d’autres rôles serveur, voir [rôles serveur dans Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f0936-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="f0936-120">Une succursale avec une liaison de réseau étendu (WAN) résistante vers un site central peut utiliser la troisième option, à savoir une passerelle PSTN et éventuellement un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="f0936-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="f0936-121">Les sites de succursale avec des liens moins résistants doivent utiliser un Survivable Branch Appliance ou un serveur Survivable Branch Server, qui assure la résilience en cas de défaillance du réseau étendu.</span><span class="sxs-lookup"><span data-stu-id="f0936-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="f0936-122">Par exemple, dans un site disposant d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server déployé, les utilisateurs peuvent toujours effectuer et recevoir des appels voix entreprise si le réseau étendu qui connecte le site de succursale au site central est inactif.</span><span class="sxs-lookup"><span data-stu-id="f0936-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="f0936-123">Pour plus d’informations sur le Survivable Branch appliance, le serveur Survivable Branch Server et la résilience, voir [Planning for Enterprise Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="f0936-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="f0936-124">Topologies de site</span><span class="sxs-lookup"><span data-stu-id="f0936-124">Site Topologies</span></span>

<span data-ttu-id="f0936-125">Le déploiement doit comprendre au moins un site central et peut inclure aucun ou plusieurs sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="f0936-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="f0936-126">Chaque site de succursale est affilié à un site central.</span><span class="sxs-lookup"><span data-stu-id="f0936-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="f0936-127">Le site central fournit les services Lync Server au site de succursale qui ne sont pas hébergés localement sur le site de succursale, comme la présence et la Conférence.</span><span class="sxs-lookup"><span data-stu-id="f0936-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="f0936-128">Si vous disposez de plusieurs sites, vous pouvez regrouper par paires les pools frontaux sur différents sites pour activer les fonctionnalités de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f0936-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="f0936-129">Pour plus d’informations, consultez la rubrique [prise en charge de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span><span class="sxs-lookup"><span data-stu-id="f0936-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0936-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f0936-130">See Also</span></span>


[<span data-ttu-id="f0936-131">Rôles serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0936-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="f0936-132">Prise en charge de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0936-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="f0936-133">Planification de la résistance voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0936-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

