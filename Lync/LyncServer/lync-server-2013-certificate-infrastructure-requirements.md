---
title: Configuration requise pour les infrastructures de certificat Lync Server 2013
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
ms.openlocfilehash: 61205cf4ecdac8eac78820442264286f414095ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="d8bb3-102">Configuration requise pour les infrastructures de certificat pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8bb3-102">Certificate infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8bb3-103">_**Dernière modification de la rubrique :** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="d8bb3-103">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="d8bb3-104">Lync Server 2013 a besoin d’une infrastructure à clé publique (PKI) pour prendre en charge les connexions TLS et Mutual TLS (MTLS).</span><span class="sxs-lookup"><span data-stu-id="d8bb3-104">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="d8bb3-105">Lync Server utilise des certificats aux fins suivantes :</span><span class="sxs-lookup"><span data-stu-id="d8bb3-105">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="d8bb3-106">Connexions TLS entre le client et le serveur</span><span class="sxs-lookup"><span data-stu-id="d8bb3-106">TLS connections between client and server</span></span>

  - <span data-ttu-id="d8bb3-107">Connexions MTLS entre serveurs</span><span class="sxs-lookup"><span data-stu-id="d8bb3-107">MTLS connections between servers</span></span>

  - <span data-ttu-id="d8bb3-108">Fédération utilisant une découverte automatique de DNS des partenaires</span><span class="sxs-lookup"><span data-stu-id="d8bb3-108">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="d8bb3-109">Accès des utilisateurs distants à la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="d8bb3-109">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="d8bb3-110">Accès des utilisateurs externes aux sessions audio/vidéo (A/V), au partage d’application et aux conférences</span><span class="sxs-lookup"><span data-stu-id="d8bb3-110">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="d8bb3-111">Demandes mobiles utilisant la découverte automatique des services Web</span><span class="sxs-lookup"><span data-stu-id="d8bb3-111">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="d8bb3-112">Pour Lync Server, les exigences courantes suivantes s’appliquent :</span><span class="sxs-lookup"><span data-stu-id="d8bb3-112">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="d8bb3-113">Tous les certificats de serveur doivent prendre en charge l’autorisation serveur (utilisation améliorée de la clé du serveur).</span><span class="sxs-lookup"><span data-stu-id="d8bb3-113">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="d8bb3-114">Tous les certificats de serveur doivent contenir un point de distribution de liste de révocation de certificats (CDP).</span><span class="sxs-lookup"><span data-stu-id="d8bb3-114">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="d8bb3-115">Tous les certificats doivent être signés à l’aide de l’algorithme de signature pris en charge par le système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="d8bb3-115">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="d8bb3-116">Lync Server 2013 prend en charge la suite SHA-1 et SHA-2 de tailles synthétiques (224, 256, 384 et 512 bits) et répond ou dépasse la configuration requise du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="d8bb3-116">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="d8bb3-117">Pour la prise en charge du [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)système d’exploitation, voir.</span><span class="sxs-lookup"><span data-stu-id="d8bb3-117">For operating system support, see [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d8bb3-118">L’algorithme de signature RSASSA-PSS n’est pas pris en charge et peut entraîner entre autres des erreurs de connexion et de transfert d’appels. </span><span class="sxs-lookup"><span data-stu-id="d8bb3-118">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="d8bb3-119">L’inscription automatique est prise en charge pour les serveurs internes exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d8bb3-119">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="d8bb3-120">L’enregistrement automatique n’est pas pris en charge pour les serveurs Edge Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d8bb3-120">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="d8bb3-121">Lorsque vous envoyez une demande de certification basée sur le Web à une autorité de certification Windows Server 2003, vous devez la transmettre à partir d’un ordinateur exécutant Windows Server 2003 SP2 ou Windows XP.</span><span class="sxs-lookup"><span data-stu-id="d8bb3-121">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="d8bb3-122">Notez que, même si KB922706 fournit une prise en charge de la résolution des problèmes liés à l’inscription de certificats Web sur un serveur de certification Windows Server 2003, il ne peut pas être utilisé Windows Server 2008, Windows Vista ou Windows 7 pour demander une certificat d’une autorité de certification Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="d8bb3-122">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="d8bb3-123">Les longueurs de clé de chiffrement 1024, 2048 et 4096 sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="d8bb3-123">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="d8bb3-124">Les longueurs de clé supérieures ou égales à 2048 sont recommandées.</span><span class="sxs-lookup"><span data-stu-id="d8bb3-124">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="d8bb3-125">L’algorithme digest, ou de signature de hachage, par défaut est RSA.</span><span class="sxs-lookup"><span data-stu-id="d8bb3-125">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="d8bb3-126">Les algorithmes ECDH\_P256\_, ECDH P384 et\_ECDH P521 sont également pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d8bb3-126">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="d8bb3-127">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d8bb3-127">In This Section</span></span>

  - [<span data-ttu-id="d8bb3-128">Exigences de certificat pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8bb3-128">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="d8bb3-129">Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8bb3-129">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="d8bb3-130">Certificats requis pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8bb3-130">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="d8bb3-131">Exigences relatives aux certificats pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8bb3-131">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

