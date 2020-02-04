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
ms.openlocfilehash: 9b205699e9efd896a157654f5c1fb200e34087fc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="8ad5a-102">Infrastructure à clé publique pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ad5a-102">Public Key Infrastructure for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ad5a-103">_**Dernière modification de la rubrique :** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="8ad5a-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="8ad5a-104">Microsoft Lync Server 2013 repose sur des certificats pour l’authentification du serveur et établit une chaîne de confiance entre les clients et les serveurs et entre les différents rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="8ad5a-105">Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 et Windows Server 2003 infrastructure à clé publique (PKI) fournit l’infrastructure permettant d’établir et de valider cette chaîne de confiance.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="8ad5a-p102">Les certificats sont des ID numériques. Ils identifient un serveur par son nom et indiquent ses propriétés. Afin de garantir que les informations d’un certificat sont valides, celui-ci doit être émis par une autorité de certification (CA) approuvée par les clients ou d’autres serveurs qui se connectent au serveur. Si le serveur se connecte uniquement avec d’autres clients et serveurs sur un réseau privé, la CA peut être une CA d’entreprise. Si le serveur interagit avec des entités en dehors du réseau privé, une CA publique peut être requise.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-p102">Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="8ad5a-p103">Même si les informations du certificat sont valides, il doit exister un moyen de vérifier que le serveur présentant le certificat est en fait celui représenté par le certificat. C’est ici que le PKI de Windows entre en jeu.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-p103">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="8ad5a-p104">Chaque certificat est lié à une clé publique. Le serveur nommé sur le certificat contient une clé privée correspondante que lui seul connaît. Un client ou serveur se connectant utilise la clé publique pour chiffrer une information aléatoire et l’envoie au serveur. Si le serveur déchiffre l’information et la retourne sous forme de texte simple, l’entité se connectant peut ainsi être sûre que le serveur contient la clé privée du certificat et qu’il s’agit donc du serveur nommé sur le certificat.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-p104">Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ad5a-117">Toutes les autorités de certification publiques ne respectent pas les exigences des certificats Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="8ad5a-118">Nous vous conseillons de vous reporter à la liste des autorités de certification publiques approuvées pour vos besoins de certificats publics.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="8ad5a-119">Pour plus d’informations, reportez- <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>vous à la rubrique partenaires de certification de communications unifiées</span><span class="sxs-lookup"><span data-stu-id="8ad5a-119">For details, see Unified Communications Certificate Partners at <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="8ad5a-120">Points de distribution de liste de révocation de certificats</span><span class="sxs-lookup"><span data-stu-id="8ad5a-120">CRL Distribution Points</span></span>

<span data-ttu-id="8ad5a-121">Lync Server 2013 nécessite que tous les certificats serveur contiennent un ou plusieurs points de distribution de la liste de révocation de certificats.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="8ad5a-122">Les points de distribution CRL (CDP) sont des emplacements à partir desquels les CRL peuvent être téléchargés en vue de vérifier que le certificat n’a pas été révoqué depuis son émission et qu’il est toujours dans sa période de validité.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="8ad5a-123">Un point de distribution CRL est indiqué dans les propriétés du certificat sous forme d’URL et il s’agit généralement d’une adresse HTTP sécurisée.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="8ad5a-124">Utilisation améliorée de la clé</span><span class="sxs-lookup"><span data-stu-id="8ad5a-124">Enhanced Key Usage</span></span>

<span data-ttu-id="8ad5a-125">Lync Server 2013 nécessite que tous les certificats serveur prennent en charge l’utilisation améliorée de l’utilisation de la clé pour l’utilisation de l’authentification du serveur.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="8ad5a-126">La configuration du champ EKU pour l’authentification du serveur signifie que le certificat est valide pour l’authentification des serveurs.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="8ad5a-127">Cette EKU est essentielle pour MTLS.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="8ad5a-128">Il est possible d’avoir plusieurs entrées dans l’EKU, ce qui permet au certificat d’avoir plusieurs rôles.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ad5a-129">L’utilisation améliorée de l’authentification du client est requise pour les connexions MTLS sortantes à partir de Live Communications Server 2003 et de Live Communications Server 2005, mais elle n’est plus nécessaire.</span><span class="sxs-lookup"><span data-stu-id="8ad5a-129">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required.</span></span> <span data-ttu-id="8ad5a-130">Toutefois, cette utilisation de l’utilisation améliorée doit être présente sur les serveurs Edge qui se connectent à AOL au moyen de la connectivité PIC (Public IM Connectivity).</span><span class="sxs-lookup"><span data-stu-id="8ad5a-130">However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

