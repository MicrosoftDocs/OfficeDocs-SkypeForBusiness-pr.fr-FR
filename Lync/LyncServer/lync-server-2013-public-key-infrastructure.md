---
title: 'Lync Server 2013 : infrastructure à clé publique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63ba5224d6663050295c5fddf9ea08e230f78506
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="9078c-102">Infrastructure de clé publique pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9078c-102">Public Key Infrastructure for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9078c-103">_**Dernière modification de la rubrique :** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="9078c-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="9078c-104">Microsoft Lync Server 2013 repose sur des certificats pour l’authentification du serveur et pour établir une chaîne de confiance entre les clients et les serveurs et entre les différents rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="9078c-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="9078c-105">L’infrastructure à clé publique (PKI) Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 et Windows Server 2003 fournit l’infrastructure permettant d’établir et de valider cette chaîne de confiance.</span><span class="sxs-lookup"><span data-stu-id="9078c-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="9078c-106">Les certificats sont des identifiants numériques.</span><span class="sxs-lookup"><span data-stu-id="9078c-106">Certificates are digital IDs.</span></span> <span data-ttu-id="9078c-107">Ils identifient un serveur à l’aide de son nom et spécifient ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="9078c-107">They identify a server by name and specify its properties.</span></span> <span data-ttu-id="9078c-108">Pour vous assurer que les informations sur un certificat sont valides, le certificat doit être émis par une autorité de certification approuvée par les clients ou d’autres serveurs qui se connectent au serveur.</span><span class="sxs-lookup"><span data-stu-id="9078c-108">To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server.</span></span> <span data-ttu-id="9078c-109">Si le serveur se connecte uniquement à d’autres clients et serveurs sur un réseau privé, l’autorité de certification peut être une autorité de certification d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="9078c-109">If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA.</span></span> <span data-ttu-id="9078c-110">Si le serveur communique avec des entités en dehors du réseau privé, une autorité de certification publique peut être nécessaire.</span><span class="sxs-lookup"><span data-stu-id="9078c-110">If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="9078c-p103">Même si les informations du certificat sont valides, il doit être possible de vérifier si le serveur soumettant le certificat est réellement celui qu’il représente. C’est à ce niveau qu’intervient l’infrastructure à clé publique Windows.</span><span class="sxs-lookup"><span data-stu-id="9078c-p103">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="9078c-p104">Chaque certificat est lié à une clé publique. Le serveur nommé dans le certificat détient une clé privée correspondante qu’il est le seul à connaître. Lorsqu’un client ou un serveur se connecte, il utilise la clé publique pour chiffrer une information aléatoire qu’il envoie au serveur. Si le serveur déchiffre les informations et les renvoie sous forme de texte simple, l’entité connectée est sûre que le serveur détient la clé privée du certificat et qu’il s’agit donc bien du serveur nommé dans le certificat.</span><span class="sxs-lookup"><span data-stu-id="9078c-p104">Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9078c-117">Toutes les autorités de certification publiques ne respectent pas les exigences des certificats Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9078c-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="9078c-118">Nous vous recommandons de vous reporter à la liste des fournisseurs d’autorités de certification publiques certifiées selon vos besoins de certificats publics.</span><span class="sxs-lookup"><span data-stu-id="9078c-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="9078c-119">Pour plus d’informations, consultez la page relative <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>aux partenaires de certificat de communications unifiées.</span><span class="sxs-lookup"><span data-stu-id="9078c-119">For details, see Unified Communications Certificate Partners at <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="9078c-120">Points de distribution de liste de révocation de certificats (CRL)</span><span class="sxs-lookup"><span data-stu-id="9078c-120">CRL Distribution Points</span></span>

<span data-ttu-id="9078c-121">Lync Server 2013 nécessite que tous les certificats de serveur contiennent un ou plusieurs points de distribution de liste de révocation de certificats (CRL).</span><span class="sxs-lookup"><span data-stu-id="9078c-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="9078c-122">Il s’agit d’emplacements à partir desquels il est possible de télécharger des listes de révocation de certificats afin de vérifier si un certificat a été révoqué depuis son émission et s’il est toujours dans sa période de validité.</span><span class="sxs-lookup"><span data-stu-id="9078c-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="9078c-123">Un point de distribution de liste de révocation de certificats figure dans les propriétés du certificat sous forme d’URL, généralement HTTP sécurisée.</span><span class="sxs-lookup"><span data-stu-id="9078c-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="9078c-124">Utilisation améliorée de la clé</span><span class="sxs-lookup"><span data-stu-id="9078c-124">Enhanced Key Usage</span></span>

<span data-ttu-id="9078c-125">Lync Server 2013 nécessite que tous les certificats de serveur prennent en charge l’utilisation améliorée de la clé (EKU) pour l’authentification du serveur.</span><span class="sxs-lookup"><span data-stu-id="9078c-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="9078c-126">La configuration du champ EKU pour l’authentification de serveurs signifie que le certificat est valide pour l’authentification des serveurs.</span><span class="sxs-lookup"><span data-stu-id="9078c-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="9078c-127">L’utilisation améliorée de la clé est essentielle pour MTLS.</span><span class="sxs-lookup"><span data-stu-id="9078c-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="9078c-128">Le champ EKU peut contenir plusieurs entrées, ce qui permet d’activer le certificat à plusieurs fins.</span><span class="sxs-lookup"><span data-stu-id="9078c-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9078c-p108">L’EKU d’authentification client était requis pour les connexions MTLS sortantes provenant de Live Communications Server 2003 et Live Communications Server 2005, mais il n’est plus nécessaire. Toutefois, cet EKU doit figurer sur les serveurs de périphérie qui se connectent à AOL par le biais de la solution PIC.</span><span class="sxs-lookup"><span data-stu-id="9078c-p108">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required. However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

