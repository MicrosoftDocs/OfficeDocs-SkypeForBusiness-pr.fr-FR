---
title: 'Lync Server 2013 : Instructions de déploiement de Voix Entreprise'
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
ms.openlocfilehash: 221c09fc5dadda267baad35f4784c22cc4f3c9c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="d027d-102">Instructions de déploiement de Voix Entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d027d-102">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d027d-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d027d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d027d-104">Cette rubrique décrit les conditions préalables et d’autres recommandations à prendre en compte lors de la planification du déploiement de Lync Server 2013 et de la charge de travail voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="d027d-104">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="d027d-105">Prérequis de déploiement</span><span class="sxs-lookup"><span data-stu-id="d027d-105">Deployment Prerequisites</span></span>

<span data-ttu-id="d027d-106">Pour une qualité optimale lors du déploiement d’Enterprise Voice, assurez-vous que votre infrastructure, réseau et systèmes informatiques répondent aux conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="d027d-106">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="d027d-107">Lync Server 2013 Standard Edition ou Enterprise Edition est installé et opérationnel sur votre réseau.</span><span class="sxs-lookup"><span data-stu-id="d027d-107">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="d027d-108">Tous les serveurs Edge sont déployés et opérationnels dans votre réseau de périmètre, notamment les serveurs Edge avec service Edge d’accès, service Edge A/V, service Edge de conférence Web et un proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="d027d-108">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="d027d-109">Un ou plusieurs utilisateurs ont été créés et activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d027d-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="d027d-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) ou le dernier Service Pack ou Microsoft Exchange Server 2010 est installé.</span><span class="sxs-lookup"><span data-stu-id="d027d-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="d027d-111">L’une de ces fonctionnalités est nécessaire pour l’intégration de la messagerie unifiée Exchange avec Lync Server et pour fournir des notifications complètes et des informations de journalisation d’appels aux points de terminaison clients.</span><span class="sxs-lookup"><span data-stu-id="d027d-111">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="d027d-112">Un numéro de téléphone principal unique a été désigné, normalisé et copié sur l’attribut **msRTCSIP-Line** pour chaque utilisateur qui doit être activé pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="d027d-112">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d027d-113">Lync Server prend en charge les numéros E. 164 et les numéros de numérotation à l’intérieur non directs.</span><span class="sxs-lookup"><span data-stu-id="d027d-113">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="d027d-114">Les nombres non-did peuvent être représentés au format <STRONG> &lt;E. 164&gt;; ext =&lt;extension&gt; </STRONG> ou sous la forme d’une chaîne de chiffres, ce qui exige que l’extension privée soit unique dans l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="d027d-114">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="d027d-115">Par exemple, un nombre privé d' 1001 peut être représenté sous la forme <STRONG>+ 1425550100 ; ext = 1001</STRONG>ou As <STRONG>1001</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d027d-115">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="d027d-116">S’il est représenté en tant que <STRONG>1001</STRONG>, il est possible que ce numéro privé soit unique au sein de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="d027d-116">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="d027d-117">Les administrateurs qui déploient Enterprise Voice doivent être membres du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d027d-117">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="d027d-118">Le déploiement d’Office Communicator 2007 est au minimum effectué.</span><span class="sxs-lookup"><span data-stu-id="d027d-118">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="d027d-119">Pour utiliser les nouvelles fonctionnalités de cette version, Lync 2013 est déployé.</span><span class="sxs-lookup"><span data-stu-id="d027d-119">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="d027d-120">Le déploiement et la configuration de l’infrastructure à clé managée (MKI) s’effectue à l’aide d’une infrastructure de certification (CA) Microsoft ou tierce.</span><span class="sxs-lookup"><span data-stu-id="d027d-120">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="d027d-121">Chaque ordinateur sur lequel vous installez le serveur de médiation doit être :</span><span class="sxs-lookup"><span data-stu-id="d027d-121">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="d027d-122">Serveur membre d’un domaine et préparé pour les services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="d027d-122">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="d027d-123">Pour les procédures de préparation des services de domaine Active Directory, voir [préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d027d-123">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="d027d-124">Exécutant l’un des systèmes d’exploitation suivants :</span><span class="sxs-lookup"><span data-stu-id="d027d-124">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="d027d-125">Version 64 bits du système d’exploitation Windows Server 2008 standard</span><span class="sxs-lookup"><span data-stu-id="d027d-125">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="d027d-126">Version 64 bits du système d’exploitation Windows Server 2008 entreprise</span><span class="sxs-lookup"><span data-stu-id="d027d-126">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="d027d-127">S’il s’agit d’une connexion de réseau téléphonique commuté (PSTN) ou d’échange de succursale privée (PBX) par le biais d’une connexion de multiplexage par répartition du temps, une ou plusieurs passerelles RTC sont disponibles pour le déploiement.</span><span class="sxs-lookup"><span data-stu-id="d027d-127">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment.</span></span> <span data-ttu-id="d027d-128">(S’il s’agit d’une connexion SIP par le biais d’une connexion SIP, une passerelle RTC n’est pas nécessaire.)</span><span class="sxs-lookup"><span data-stu-id="d027d-128">(If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="d027d-129">Pannes d’alimentation, de réseau ou de service téléphonique</span><span class="sxs-lookup"><span data-stu-id="d027d-129">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="d027d-130">En cas de panne, de perturbation ou d’autres dégradations des services d’alimentation, de réseau ou de téléphone dans votre emplacement, la voix, la messagerie instantanée, la présence et d’autres fonctionnalités de Lync Server et de n’importe quel appareil connecté à Lync Server peut ne pas fonctionner correctement.</span><span class="sxs-lookup"><span data-stu-id="d027d-130">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="d027d-131">Voix entreprise dépend de la disponibilité du serveur et du client vocal et de l’organisation matérielle</span><span class="sxs-lookup"><span data-stu-id="d027d-131">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="d027d-132">Les communications vocales avec Lync Server dépendent de la disponibilité du logiciel serveur et du fonctionnement approprié des clients vocaux ou des appareils de téléphone matériel qui se connectent au logiciel serveur.</span><span class="sxs-lookup"><span data-stu-id="d027d-132">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="d027d-133">Autres moyens d’accès aux services d’urgence</span><span class="sxs-lookup"><span data-stu-id="d027d-133">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="d027d-134">Pour les emplacements où vous installez un client vocal (par exemple, un PC exécutant un client Lync ou un appareil Lync Phone Edition), nous vous recommandons de conserver une option de sauvegarde pour les utilisateurs pour appeler des services d’urgence (par exemple, 911 ou 999) en cas de panne de courant. , de la dégradation de la connectivité réseau, du service de téléphone ou d’autres problèmes qui risquent d’empêcher le fonctionnement des appareils Lync Server, Lync ou Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="d027d-134">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="d027d-135">Par exemple, il peut s’agir d’un téléphone relié à une ligne réseau téléphonique commutée standard ou à un téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="d027d-135">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="d027d-136">Appels d’urgence et systèmes téléphoniques multilignes</span><span class="sxs-lookup"><span data-stu-id="d027d-136">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="d027d-137">L’utilisation d’un système téléphonique multiligne (MLTS) peut être soumise à une loi américaine ou fédérale des États-Unis ou aux lois d’autres pays/régions qui requièrent que le MLTS fournisse le numéro de téléphone, l’extension et/ou l’emplacement physique d’un appelant aux services d’urgence en vigueur lors de la mise en place d’un appelant aux services d’urgence (par exemple, 999 911 lorsque</span><span class="sxs-lookup"><span data-stu-id="d027d-137">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="d027d-138">Dans cette version, Lync Server peut être configuré pour fournir l’emplacement physique d’un appelant à un fournisseur de services d’urgence, comme décrit dans la rubrique [planification des services d’urgence (E9-1-1) dans Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="d027d-138">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="d027d-139">La conformité avec la législation MLTS est la seule responsabilité de l’acquéreur de périphériques Lync Server, Lync et Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="d027d-139">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

