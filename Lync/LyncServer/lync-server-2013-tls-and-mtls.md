---
title: 'Lync Server 2013 : TLS et MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e22fcf910062df155bb62a9da183bbe6ad73e0f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503771"
---
# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="9edd7-102">TLS et MTLS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9edd7-102">TLS and MTLS for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9edd7-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="9edd7-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="9edd7-104">Les protocoles TLS (Transport Layer Security) et MTLS (Mutual Transport Layer Security) fournissent des communications chiffrées et une authentification de point de terminaison sur Internet.</span><span class="sxs-lookup"><span data-stu-id="9edd7-104">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="9edd7-105">Microsoft Lync Server 2013 utilise ces deux protocoles pour créer le réseau des serveurs approuvés et garantir que toutes les communications sur ce réseau sont chiffrées.</span><span class="sxs-lookup"><span data-stu-id="9edd7-105">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="9edd7-106">Toutes les communications SIP entre les serveurs se produisent via MTLS.</span><span class="sxs-lookup"><span data-stu-id="9edd7-106">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="9edd7-107">Les communications SIP de client à serveur ont lieu sur TLS.</span><span class="sxs-lookup"><span data-stu-id="9edd7-107">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="9edd7-108">TLS permet aux utilisateurs, via leur logiciel client, d’authentifier les serveurs Lync Server 2013 auxquels ils se connectent.</span><span class="sxs-lookup"><span data-stu-id="9edd7-108">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="9edd7-109">Sur une connexion TLS, le client demande un certificat valide à partir du serveur.</span><span class="sxs-lookup"><span data-stu-id="9edd7-109">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="9edd7-110">Pour être valide, le certificat doit avoir été émis par une autorité de certification qui est également approuvée par le client et le nom DNS du serveur doit correspondre au nom DNS du certificat.</span><span class="sxs-lookup"><span data-stu-id="9edd7-110">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="9edd7-111">Si le certificat est valide, le client utilise la clé publique dans le certificat pour chiffrer les clés de chiffrement symétriques à utiliser pour la communication, de sorte que seul le propriétaire d’origine du certificat peut utiliser sa clé privée pour déchiffrer le contenu de la communication.</span><span class="sxs-lookup"><span data-stu-id="9edd7-111">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="9edd7-112">La connexion obtenue est approuvée et, à partir de ce point, elle n’est pas contestée par d’autres serveurs ou clients approuvés.</span><span class="sxs-lookup"><span data-stu-id="9edd7-112">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="9edd7-113">Dans ce contexte, le protocole SSL (Secure Sockets Layer) tel qu’il est utilisé avec les services Web peut être associé à TLS.</span><span class="sxs-lookup"><span data-stu-id="9edd7-113">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="9edd7-114">Les connexions de serveur à serveur s’appuient sur MTLS pour l’authentification mutuelle.</span><span class="sxs-lookup"><span data-stu-id="9edd7-114">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="9edd7-115">Sur une connexion MTLS, le serveur à l’origine d’un message et le serveur qui le reçoit reçoivent des certificats d’une autorité de certification mutuellement approuvée.</span><span class="sxs-lookup"><span data-stu-id="9edd7-115">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="9edd7-116">Les certificats prouvent l’identité de chaque serveur à l’autre.</span><span class="sxs-lookup"><span data-stu-id="9edd7-116">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="9edd7-117">Dans les déploiements Lync Server 2013, les certificats émis par l’autorité de certification d’entreprise qui se trouvent pendant leur période de validité et qui ne sont pas révoqués par l’autorité de certification émettrice sont automatiquement considérés comme valides par tous les clients et serveurs internes car tous les membres d’un domaine Active Directory approuvent l’autorité de certification d’entreprise dans ce domaine.</span><span class="sxs-lookup"><span data-stu-id="9edd7-117">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="9edd7-118">Dans les scénarios fédérés, l’autorité de certification émettrice doit être approuvée par les deux partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="9edd7-118">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="9edd7-119">Chaque partenaire peut utiliser une autorité de certification différente, si cela est souhaité, tant que cette autorité de certification est également approuvée par l’autre partenaire.</span><span class="sxs-lookup"><span data-stu-id="9edd7-119">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="9edd7-120">Cette approbation est plus facile à accomplir par les serveurs Edge ayant le certificat d’autorité de certification racine du partenaire dans leurs autorités de certification racines de confiance, ou à l’aide d’une autorité de certification tierce approuvée par les deux parties.</span><span class="sxs-lookup"><span data-stu-id="9edd7-120">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="9edd7-121">TLS et MTLS permettent d’éviter les attaques par écoute clandestine et les attaques de l’intercepteur.</span><span class="sxs-lookup"><span data-stu-id="9edd7-121">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="9edd7-122">Dans une attaque de type « Man-in-the-Middle », l’agresseur redirige les communications entre deux entités réseau via l’ordinateur de l’attaquant, sans que l’une des parties n’ait connaissance.</span><span class="sxs-lookup"><span data-stu-id="9edd7-122">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="9edd7-123">La spécification TLS et Lync Server 2013 des serveurs approuvés (uniquement ceux qui sont spécifiés dans le générateur de topologie) atténue le risque d’une attaque de l’intercepteur en partie sur la couche d’application en utilisant le chiffrement de bout en bout coordonné à l’aide de la cryptographie à clé publique entre les deux points de terminaison, un attaquant doit disposer d’un certificat valide et approuvé avec la clé privée correspondante et être envoyé au nom du service auquel le client communique pour déchiffrer la communication.</span><span class="sxs-lookup"><span data-stu-id="9edd7-123">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="9edd7-124">Toutefois, vous devez finalement suivre les meilleures pratiques en matière de sécurité avec votre infrastructure réseau (dans ce cas, DNS d’entreprise).</span><span class="sxs-lookup"><span data-stu-id="9edd7-124">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="9edd7-125">Lync Server 2013 suppose que le serveur DNS est approuvé de la même manière que les contrôleurs de domaine et les catalogues globaux, mais le DNS offre un niveau de protection contre les attaques de détournement DNS en empêchant le serveur d’un agresseur de répondre correctement à une demande au nom usurpé.</span><span class="sxs-lookup"><span data-stu-id="9edd7-125">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="9edd7-126">La figure suivante illustre de façon générale comment Lync Server 2013 utilise MTLS pour créer un réseau de serveurs approuvés.</span><span class="sxs-lookup"><span data-stu-id="9edd7-126">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="9edd7-127">**Connexions approuvées dans un réseau Lync Server**</span><span class="sxs-lookup"><span data-stu-id="9edd7-127">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="9edd7-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="9edd7-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

