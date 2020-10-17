---
title: 'Lync Server 2013 : instructions de déploiement pour voix entreprise'
description: 'Lync Server 2013 : instructions de déploiement pour voix entreprise.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cd847f674ad4b04698be0f54f8fbd490b13d689
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562120"
---
# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="85aa9-103">Instructions de déploiement de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85aa9-103">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85aa9-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="85aa9-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="85aa9-105">Cette rubrique décrit les conditions préalables et les autres instructions à prendre en compte lorsque vous envisagez de déployer Lync Server 2013 et la charge de travail voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="85aa9-105">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="85aa9-106">Conditions préalables du déploiement</span><span class="sxs-lookup"><span data-stu-id="85aa9-106">Deployment Prerequisites</span></span>

<span data-ttu-id="85aa9-107">Pour une expérience optimale lors du déploiement de voix entreprise, assurez-vous que votre infrastructure, votre réseau et vos systèmes informatiques remplissent les conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="85aa9-107">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="85aa9-108">Lync Server 2013 Standard Edition ou Enterprise Edition est installé et opérationnel sur votre réseau.</span><span class="sxs-lookup"><span data-stu-id="85aa9-108">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="85aa9-109">Tous les serveurs Edge sont déployés et opérationnels dans votre réseau de périmètre, y compris les serveurs Edge avec le service Edge d’accès, le service Edge A/V, le service Edge de conférence Web et un proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="85aa9-109">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="85aa9-110">Un ou plusieurs utilisateurs ont été créés et activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85aa9-110">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="85aa9-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) ou le Service Pack le plus récent, ou Microsoft Exchange Server 2010 est installé.</span><span class="sxs-lookup"><span data-stu-id="85aa9-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="85aa9-112">L’une d’entre elles est requise pour l’intégration de la messagerie unifiée Exchange avec Lync Server et pour fournir des notifications enrichies et des informations de journal des appels aux points de terminaison du client.</span><span class="sxs-lookup"><span data-stu-id="85aa9-112">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="85aa9-113">Un numéro de téléphone principal unique a été désigné, normalisé et copié dans l’attribut **msRTCSIP-Line** pour chaque utilisateur à activer pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="85aa9-113">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85aa9-114">Lync Server prend en charge les numéros E. 164 et les numéros DID (non directs).</span><span class="sxs-lookup"><span data-stu-id="85aa9-114">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="85aa9-115">Les nombres non DID peuvent être représentés au format <STRONG> &lt; E. 164 &gt; ; ext = &lt; extension &gt; </STRONG> ou en tant que chaîne de chiffres, avec la nécessité que l’extension privée soit unique dans l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="85aa9-115">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="85aa9-116">Par exemple, le numéro privé 1 001 peut être représenté comme suit : <STRONG>+1425550100;ext=1001</STRONG> ou <STRONG>1001</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="85aa9-116">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="85aa9-117">S’il est représenté comme <STRONG>1001</STRONG>, ce numéro privé doit être unique dans l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="85aa9-117">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="85aa9-118">Les administrateurs qui déploient voix entreprise doivent être membres du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="85aa9-118">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="85aa9-119">Au minimum, Office Communicator 2007 est déployé avec succès.</span><span class="sxs-lookup"><span data-stu-id="85aa9-119">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="85aa9-120">Pour utiliser les nouvelles fonctionnalités de cette version, Lync 2013 est déployé.</span><span class="sxs-lookup"><span data-stu-id="85aa9-120">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="85aa9-121">L’infrastructure MKI (Managed key infrastructure) est déployée et configurée, à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.</span><span class="sxs-lookup"><span data-stu-id="85aa9-121">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="85aa9-122">Chaque ordinateur sur lequel vous installez un serveur de médiation doit :</span><span class="sxs-lookup"><span data-stu-id="85aa9-122">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="85aa9-123">Un serveur membre d’un domaine et préparé pour les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85aa9-123">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="85aa9-124">Pour connaître les procédures de préparation des services de domaine Active Directory, voir [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="85aa9-124">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="85aa9-125">Exécuter l’un des systèmes d’exploitation suivants :</span><span class="sxs-lookup"><span data-stu-id="85aa9-125">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="85aa9-126">Édition 64 bits du système d’exploitation Windows Server 2008 Standard</span><span class="sxs-lookup"><span data-stu-id="85aa9-126">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="85aa9-127">Édition 64 bits du système d’exploitation Windows Server 2008 Enterprise</span><span class="sxs-lookup"><span data-stu-id="85aa9-127">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="85aa9-p105">Si la connexion au réseau téléphonique commuté (PSTN) ou à l’autocommutateur privé (PBX) s’effectue au moyen d’une connexion TDM (multiplexage temporel), une ou plusieurs passerelles PSTN sont disponibles pour le déploiement. (Si la connexion s’effectue via une jonction SIP, une passerelle PSTN n’est pas nécessaire.)</span><span class="sxs-lookup"><span data-stu-id="85aa9-p105">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment. (If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="85aa9-130">Coupure de courant, interruption du réseau ou du service téléphonique</span><span class="sxs-lookup"><span data-stu-id="85aa9-130">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="85aa9-131">En cas de panne, de perturbation ou d’autres dégradations des services d’alimentation, de réseau ou de téléphonie sur votre site, la voix, la messagerie instantanée, la présence et d’autres fonctionnalités de Lync Server et tout périphérique connecté à Lync Server peuvent ne pas fonctionner correctement.</span><span class="sxs-lookup"><span data-stu-id="85aa9-131">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="85aa9-132">Voix Entreprise dépend de la disponibilité du serveur et de l’opérabilité du client et du matériel vocal</span><span class="sxs-lookup"><span data-stu-id="85aa9-132">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="85aa9-133">Les communications vocales avec Lync Server dépendent de la disponibilité du logiciel serveur et du bon fonctionnement des clients vocaux ou des périphériques de téléphonie matériel se connectant au logiciel serveur.</span><span class="sxs-lookup"><span data-stu-id="85aa9-133">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="85aa9-134">Méthode alternative d’accès aux services d’urgence</span><span class="sxs-lookup"><span data-stu-id="85aa9-134">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="85aa9-135">Pour les emplacements où vous installez un client vocal (par exemple, un PC exécutant un client Lync ou un appareil Lync Phone Edition), nous vous recommandons de conserver une option de sauvegarde pour les utilisateurs qui appellent des services d’urgence (par exemple, 911 ou 999) en cas de panne de courant, de connectivité réseau, de service téléphonique ou autre problème susceptible d’empêcher le fonctionnement de Lync Server. , Lync ou Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="85aa9-135">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="85aa9-136">Une telle alternative peut consister en un téléphone connecté à une ligne de réseau téléphonique commuté (RTC) standard ou un téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="85aa9-136">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="85aa9-137">Appels d’urgence et systèmes téléphoniques multilignes</span><span class="sxs-lookup"><span data-stu-id="85aa9-137">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="85aa9-138">L’utilisation d’un système téléphonique multiligne (MLTS) peut être sujette à une réglementation d’état et/ou fédérale des États-Unis et à une réglementation étrangère relative aux systèmes téléphoniques multilignes exigeant du système qu’il fournisse le numéro de téléphone ou de poste et/ou l’emplacement physique de l’appelant aux services d’urgence appropriés lorsqu’un appel est effectué (par exemple, lorsque le numéro d’un service d’urgence, tel que le 18 ou le 112, est composé).</span><span class="sxs-lookup"><span data-stu-id="85aa9-138">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="85aa9-139">Dans cette version, Lync Server peut être configuré pour fournir l’emplacement physique d’un appelant à un fournisseur de services d’urgence, comme décrit dans la rubrique [planification des services d’urgence (E9-1-1) dans Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="85aa9-139">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="85aa9-140">La conformité avec les lois MLTS est la seule responsabilité de l’acheteur de Lync Server, du client Lync et des appareils Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="85aa9-140">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

