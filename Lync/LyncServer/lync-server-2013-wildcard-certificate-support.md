---
title: Prise en charge des certificats comportant des caractères génériques Lync Server 2013
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
ms.openlocfilehash: 8a3e64dcfd16212e618a8ebe152bd2516a25b26d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="c9272-102">Prise en charge des certificats comportant des caractères génériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9272-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9272-103">_**Dernière modification de la rubrique :** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="c9272-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="c9272-104">Lync Server 2013 utilise des certificats pour le chiffrement des communications et l’authentification par identité du serveur.</span><span class="sxs-lookup"><span data-stu-id="c9272-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="c9272-105">Dans certains cas, par exemple, la publication sur le Web par le biais du proxy inverse, l’entrée de nouveau nom de l’élément de nom de domaine complet (FQDN) du serveur qui présente le service n’est pas requise.</span><span class="sxs-lookup"><span data-stu-id="c9272-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="c9272-106">Dans ces cas, vous pouvez utiliser des certificats à l’aide d’entrées génériques pour réduire le coût d’un certificat demandé auprès d’une autorité de certification publique et réduire la complexité du processus de planification des certificats. .</span><span class="sxs-lookup"><span data-stu-id="c9272-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c9272-107">Pour conserver la fonctionnalité de périphériques de communications unifiées (UC) (par exemple, les téléphones de bureau), vous devez tester soigneusement le certificat déployé pour vous assurer que les appareils fonctionnent correctement après l’implémentation d’un certificat générique.</span><span class="sxs-lookup"><span data-stu-id="c9272-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="c9272-108">Il n’y a pas de prise en charge d’une entrée de caractère générique comme nom de sujet (également appelé nom commun ou NC) pour n’importe quel rôle.</span><span class="sxs-lookup"><span data-stu-id="c9272-108">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role.</span></span> <span data-ttu-id="c9272-109">Les rôles de serveur suivants sont pris en charge lorsque vous utilisez des entrées de caractères génériques dans le SAN :</span><span class="sxs-lookup"><span data-stu-id="c9272-109">The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="c9272-110">**Proxy inverse.**    L’entrée San générique est prise en charge pour les certificats de publication d’URL simples (de conférence et de numérotation).</span><span class="sxs-lookup"><span data-stu-id="c9272-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="c9272-111">**Proxy inverse.**    L’entrée San générique est prise en charge pour les entrées du San pour LyncDiscover sur le certificat de publication.</span><span class="sxs-lookup"><span data-stu-id="c9272-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="c9272-112">**Director.**    L’entrée San générique est prise en charge pour les URL simples (réunion et numéro de téléphone) et pour les entrées San pour LyncDiscover et LyncDiscoverInternal dans les composants Web Director.</span><span class="sxs-lookup"><span data-stu-id="c9272-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="c9272-113">**Serveur frontal (édition standard) et liste frontale (Enterprise Edition).**</span><span class="sxs-lookup"><span data-stu-id="c9272-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="c9272-114">L’entrée SAN générique est prise en charge pour les URL simples (réunion et numéro de téléphone) et pour les entrées SAN pour LyncDiscover et LyncDiscoverInternal dans les composants webend Web.</span><span class="sxs-lookup"><span data-stu-id="c9272-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="c9272-115">**Exchange Unified Messaging (UM).**    Le serveur n’utilise pas d’entrées du San lorsqu’il est déployé en tant que serveur autonome.</span><span class="sxs-lookup"><span data-stu-id="c9272-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="c9272-116">**Serveur d’accès au client Microsoft Exchange Server.**    Les entrées génériques du San sont prises en charge pour les clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="c9272-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="c9272-117">**Exchange Unified Messaging (MU) et serveur d’accès au client Exchange Server sur le même serveur.**    Les entrées génériques du San sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="c9272-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="c9272-118">Rôles de serveur non mentionnés dans cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="c9272-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="c9272-119">Rôles de serveur internes (y compris, mais sans s’y limiter, le serveur de médiation, l’archivage et la surveillance du serveur, de l’unité de branchement survivant ou du serveur de succursales survivant)</span><span class="sxs-lookup"><span data-stu-id="c9272-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="c9272-120">Interfaces de serveur Edge externes</span><span class="sxs-lookup"><span data-stu-id="c9272-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="c9272-121">Serveur Edge interne</span><span class="sxs-lookup"><span data-stu-id="c9272-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c9272-122">Pour l’interface du serveur Edge interne, une entrée générique peut être affectée au SAN et est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c9272-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="c9272-123">Le SAN sur le serveur Edge interne n’est pas interrogé, et une entrée SAN générique a une valeur limitée.</span><span class="sxs-lookup"><span data-stu-id="c9272-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="c9272-124">Pour plus d’informations sur les configurations de certificats, y compris l’utilisation de caractères génériques dans les certificats, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="c9272-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="c9272-125">Exigences de certificat pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9272-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="c9272-126">Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9272-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="c9272-127">Résumé des certificats - Équilibrage de charge DNS et matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9272-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="c9272-128">Résumé des certificats - Directeur unique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9272-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="c9272-129">Résumé des certificats - Pool directeur mis à l’échelle, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9272-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="c9272-130">Résumé des certificats - Proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9272-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="c9272-131">Instructions d’intégration de la messagerie unifiée locale et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9272-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="c9272-132">Pour plus d’informations sur la configuration des certificats pour Exchange, y compris l’utilisation de caractères génériques, voir la documentation du produit Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c9272-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

