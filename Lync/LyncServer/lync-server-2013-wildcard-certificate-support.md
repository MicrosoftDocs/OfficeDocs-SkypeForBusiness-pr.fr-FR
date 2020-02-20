---
title: Prise en charge de certificat générique Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d48ba92ffd18e385be95d6218357303a67f892c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="65d45-102">Prise en charge de certificat générique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65d45-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65d45-103">_**Dernière modification de la rubrique :** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="65d45-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="65d45-104">Lync Server 2013 utilise des certificats pour le chiffrement des communications et l’authentification de l’identité du serveur.</span><span class="sxs-lookup"><span data-stu-id="65d45-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="65d45-105">Dans certains cas, notamment la publication web via le proxy inverse, la saisie d’un autre nom de sujet (SAN) fort correspondant au nom de domaine complet (FQDN) du serveur hébergeant le service n’est pas requise.</span><span class="sxs-lookup"><span data-stu-id="65d45-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="65d45-106">Dans de tels cas, il est possible d’utiliser des certificats avec des entrées SAN génériques (appelés également certificats génériques) pour réduire le coût d’un certificat exigé par une autorité de certification publique afin de réduire la complexité du processus de planification pour les certificats.</span><span class="sxs-lookup"><span data-stu-id="65d45-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="65d45-107">Pour conserver les fonctionnalités des périphériques de communications unifiées (UC) tels que les téléphones de bureaux, il est important de tester avec soin le certificat déployé pour garantir le bon fonctionnement des périphériques après avoir implémenté un certificat générique.</span><span class="sxs-lookup"><span data-stu-id="65d45-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="65d45-p102">Une entrée de certificat n’est pas prise en charge en tant que nom d’objet (aussi appelé nom commun ou CN) pour un rôle donné. Les rôles serveur suivants sont pris en charge lors de l’utilisation d’entrées génériques dans le SAN :</span><span class="sxs-lookup"><span data-stu-id="65d45-p102">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role. The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="65d45-110">**Proxy inverse.**    L’entrée San générique est prise en charge pour les certificats de publication d’URL simples (de réunion et de numérotation).</span><span class="sxs-lookup"><span data-stu-id="65d45-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="65d45-111">**Proxy inverse.**    L’entrée San générique est prise en charge pour les entrées San pour LyncDiscover sur le certificat de publication.</span><span class="sxs-lookup"><span data-stu-id="65d45-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="65d45-112">**Directeur.**    L’entrée San générique est prise en charge pour les URL simples (de réunion et de numérotation) et pour les entrées San pour LyncDiscover et LyncDiscoverInternal dans les composants Web Director.</span><span class="sxs-lookup"><span data-stu-id="65d45-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="65d45-113">**Serveur frontal (Standard Edition) et pool frontal (Enterprise Edition).**</span><span class="sxs-lookup"><span data-stu-id="65d45-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="65d45-114">L’entrée SAN générique est prise en charge pour les URL simples (de réunion et de numérotation) et pour les entrées SAN pour LyncDiscover et LyncDiscoverInternal dans les composants Web frontaux.</span><span class="sxs-lookup"><span data-stu-id="65d45-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="65d45-115">**Messagerie unifiée Exchange.**    Le serveur n’utilise pas les entrées San lorsqu’il est déployé en tant que serveur autonome.</span><span class="sxs-lookup"><span data-stu-id="65d45-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="65d45-116">**Serveur d’accès au client Microsoft Exchange Server.**    Les entrées de caractères génériques dans le San sont prises en charge pour les clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="65d45-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="65d45-117">**Messagerie unifiée Exchange et serveur d’accès au client Microsoft Exchange Server sur le même serveur.**    Les entrées San génériques sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="65d45-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="65d45-118">Rôles serveur non traités dans ce chapitre :</span><span class="sxs-lookup"><span data-stu-id="65d45-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="65d45-119">Rôles serveur internes (y compris, mais sans s’y limiter, le serveur de médiation, le serveur d’archivage et de surveillance, le Survivable Branch Appliance ou le serveur Survivable Branch Server)</span><span class="sxs-lookup"><span data-stu-id="65d45-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="65d45-120">Interfaces de serveur Edge externe</span><span class="sxs-lookup"><span data-stu-id="65d45-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="65d45-121">Serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="65d45-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65d45-122">Pour l’interface de serveur Edge interne, une entrée générique peut être affectée au SAN et est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="65d45-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="65d45-123">Le SAN sur le serveur Edge interne n’est pas interrogé et une entrée SAN générique a une valeur limitée.</span><span class="sxs-lookup"><span data-stu-id="65d45-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="65d45-124">Pour plus d’informations sur les configurations de certificats, y compris l’utilisation de caractères génériques dans les certificats, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="65d45-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="65d45-125">Exigences de certificat pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65d45-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="65d45-126">Conditions requises pour les certificats pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65d45-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="65d45-127">Résumé des certificats-charge DNS et charge matérielle équilibrée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65d45-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="65d45-128">Résumé des certificats-directeur unique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65d45-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="65d45-129">Résumé des certificats-pool directeur mis à l’ampleur, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65d45-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="65d45-130">Résumé des certificats-proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65d45-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="65d45-131">Instructions pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65d45-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="65d45-132">Pour plus d’informations sur la configuration des certificats pour Exchange, y compris l’utilisation de caractères génériques, voir la documentation du produit Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="65d45-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

