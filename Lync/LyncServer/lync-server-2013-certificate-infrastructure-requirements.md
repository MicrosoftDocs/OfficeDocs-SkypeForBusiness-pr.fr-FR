---
title: Configuration requise pour l’infrastructure de certificat Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e8c96c6b4ad5e19abf2d1f41024932c710786cb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="c5983-102">Configuration requise pour l’infrastructure de certificat pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5983-102">Certificate infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5983-103">_**Dernière modification de la rubrique :** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="c5983-103">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="c5983-104">Lync Server 2013 nécessite une infrastructure à clé publique (PKI) pour prendre en charge les connexions TLS et Mutual TLS (MTLS).</span><span class="sxs-lookup"><span data-stu-id="c5983-104">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="c5983-105">Lync Server utilise des certificats aux fins suivantes :</span><span class="sxs-lookup"><span data-stu-id="c5983-105">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="c5983-106">Connexions TLS entre client et serveur</span><span class="sxs-lookup"><span data-stu-id="c5983-106">TLS connections between client and server</span></span>

  - <span data-ttu-id="c5983-107">Connexions MTLS entre serveurs</span><span class="sxs-lookup"><span data-stu-id="c5983-107">MTLS connections between servers</span></span>

  - <span data-ttu-id="c5983-108">Fédération à l’aide de la découverte automatique de partenaires via le DNS</span><span class="sxs-lookup"><span data-stu-id="c5983-108">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="c5983-109">Accès des utilisateurs distants à la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="c5983-109">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="c5983-110">Accès des utilisateurs externes aux sessions audio/vidéo (A/V), au partage d’application et aux conférences</span><span class="sxs-lookup"><span data-stu-id="c5983-110">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="c5983-111">Demandes mobiles utilisant la découverte automatique de services web</span><span class="sxs-lookup"><span data-stu-id="c5983-111">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="c5983-112">Pour Lync Server, les exigences communes suivantes s’appliquent :</span><span class="sxs-lookup"><span data-stu-id="c5983-112">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="c5983-113">Tous les certificats de serveur doivent prendre en charge l’autorisation serveur (utilisation améliorée de la clé du serveur).</span><span class="sxs-lookup"><span data-stu-id="c5983-113">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="c5983-114">Tous les certificats de serveur doivent contenir un point de distribution de liste de révocation de certificats (CDP).</span><span class="sxs-lookup"><span data-stu-id="c5983-114">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="c5983-115">Tous les certificats doivent être signés à l’aide d’un algorithme de signature pris en charge par le système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="c5983-115">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="c5983-116">Lync Server 2013 prend en charge la suite SHA-1 et SHA-2 de tailles de condensé (224, 256, 384 et 512 bits) et répond ou dépasse la configuration requise du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="c5983-116">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="c5983-117">Pour la prise en charge du [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002)système d’exploitation, voir.</span><span class="sxs-lookup"><span data-stu-id="c5983-117">For operating system support, see [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5983-118">L’utilisation de l’algorithme de signature RSASSA-PSS n’est pas prise en charge et peut entraîner des erreurs de connexion et de transfert d’appel, entre autres problèmes.</span><span class="sxs-lookup"><span data-stu-id="c5983-118">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="c5983-119">L’enregistrement automatique est pris en charge pour les serveurs internes exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c5983-119">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="c5983-120">L’enregistrement automatique n’est pas pris en charge pour les serveurs Edge Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c5983-120">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="c5983-121">Pour soumettre une demande de certificat web à une Autorité de certification Windows Server 2003, vous devez utiliser un ordinateur exécutant Windows Server 2003 avec SP2 ou Windows XP.</span><span class="sxs-lookup"><span data-stu-id="c5983-121">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="c5983-122">Notez que bien que l’article de la Base de connaissances Microsoft KB922706 indique comment résoudre les problèmes relatifs à l’inscription de certificats web lors d’une inscription avec les services de certificat Windows Server 2003, il n’est pas possible d’utiliser Windows Server 2008, Windows Vista ou Windows 7 pour demander un certificat auprès d’une Autorité de certification Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="c5983-122">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="c5983-123">Les longueurs de clés de chiffrement de 1024, 2048 et 4096 sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="c5983-123">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="c5983-124">Les longueurs de clé de 2048 et supérieures sont recommandées.</span><span class="sxs-lookup"><span data-stu-id="c5983-124">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="c5983-125">L’algorithme de chiffrement par défaut, ou signature de hachage, est RSA.</span><span class="sxs-lookup"><span data-stu-id="c5983-125">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="c5983-126">Les algorithmes ECDH\_P256\_, ECDH P384 et\_ECDH P521 sont également pris en charge.</span><span class="sxs-lookup"><span data-stu-id="c5983-126">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="c5983-127">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c5983-127">In This Section</span></span>

  - [<span data-ttu-id="c5983-128">Exigences de certificat pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5983-128">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="c5983-129">Conditions requises pour les certificats pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5983-129">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="c5983-130">Conditions requises pour le certificat pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5983-130">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="c5983-131">Exigences relatives aux certificats pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5983-131">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

