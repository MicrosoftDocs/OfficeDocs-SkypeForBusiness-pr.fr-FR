---
title: 'Lync Server 2013 : authentification utilisateur et client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 397b17e83d566248117baf917c24fd3100f402d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="c0653-102">Authentification utilisateur et client pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0653-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0653-103">_**Dernière modification de la rubrique :** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="c0653-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="c0653-104">Un utilisateur approuvé est un utilisateur dont les informations d’identification ont été authentifiées par un serveur approuvé dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0653-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="c0653-105">Il s’agit généralement d’un serveur Standard Edition, d’un serveur frontal Enterprise Edition ou d’un directeur.</span><span class="sxs-lookup"><span data-stu-id="c0653-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="c0653-106">Lync Server 2013 repose sur les services de domaine Active Directory en tant que référentiel principal unique approuvé des informations d’identification de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c0653-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="c0653-107">L’authentification consiste à donner des informations d’identification des utilisateurs à un serveur approuvé.</span><span class="sxs-lookup"><span data-stu-id="c0653-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="c0653-108">Lync Server 2013 utilise les protocoles d’authentification suivants, en fonction de l’État et de l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c0653-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="c0653-p103">Le **protocole MIT Kerberos, version 5** pour les utilisateurs internes disposant d’informations d’identification Active Directory. Kerberos nécessite la connectivité du client aux services de domaine Active Directory, raison pour laquelle il ne peut pas être utilisé pour authentifier des clients situés en dehors du pare-feu de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c0653-p103">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials. Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="c0653-p104">Le **protocole NTLM** pour les utilisateurs disposant d’informations d’identification Active Directory qui se connectent à partir d’un système d’extrémité situé à l’extérieur du pare-feu de l’entreprise. Le service Edge d’accès transmet les demandes de connexion à un directeur, s’il existe, ou à un serveur frontal à des fins d’authentification. Le service lui-même ne procède pas à l’authentification.</span><span class="sxs-lookup"><span data-stu-id="c0653-p104">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall. The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication. The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0653-114">Le protocole NTLM offre une protection contre les attaques plus faible que Kerberos, c’est pourquoi certaines organisations limitent son utilisation.</span><span class="sxs-lookup"><span data-stu-id="c0653-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="c0653-115">Par conséquent, l’accès à Lync Server 2013 peut être limité à des clients ou à des clients connectés via une connexion VPN ou DirectAccess.</span><span class="sxs-lookup"><span data-stu-id="c0653-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="c0653-p106">Le **protocole Digest** pour les utilisateurs dits « anonymes ». Les utilisateurs anonymes sont des utilisateurs externes qui n’ont pas d’informations d’identification Active Directory reconnues, mais qui ont été invités à une conférence sur site pour laquelle ils disposent d’une clé de conférence valide. L’authentification Digest n’est pas utilisée pour les autres interactions avec les clients.</span><span class="sxs-lookup"><span data-stu-id="c0653-p106">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="c0653-119">L’authentification Lync Server 2013 se compose de deux phases :</span><span class="sxs-lookup"><span data-stu-id="c0653-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="c0653-120">Une association de sécurité est établie entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="c0653-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="c0653-p107">Le client et le serveur utilisent l’association de sécurité existante pour signer les messages envoyés et pour vérifier les messages reçus. Les messages non authentifiés d’un client sont refusés lorsque l’authentification est activée sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c0653-p107">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="c0653-p108">L’approbation d’un utilisateur est attachée à chaque message envoyé par l’utilisateur, et non à l’identité de l’utilisateur proprement dite. Le serveur vérifie la validité des informations d’identification de l’utilisateur pour chaque message. Si les informations d’identification de l’utilisateur sont valides, le message n’est vérifié ni par le premier serveur qui le reçoit, ni par tous les serveurs du nuage de serveurs approuvés.</span><span class="sxs-lookup"><span data-stu-id="c0653-p108">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="c0653-126">Vous pouvez utiliser d’autres contraintes, si nécessaire, pour empêcher les utilisateurs disposant d’informations d’identification valides délivrées par un partenaire fédéré d’accéder à l’ensemble des privilèges accordés aux utilisateurs internes.</span><span class="sxs-lookup"><span data-stu-id="c0653-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="c0653-127">Les protocoles ICE et TURN utilisent également l’authentification Digest, comme décrit dans le document RFC TURN de l’IETF.</span><span class="sxs-lookup"><span data-stu-id="c0653-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="c0653-128">Les certificats clients offrent un moyen alternatif aux utilisateurs d’être authentifiés par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0653-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="c0653-129">Au lieu de fournir un nom d’utilisateur et un mot de passe, les utilisateurs disposent d’un certificat et de la clé privée correspondant au certificat nécessaire pour résoudre un défi de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="c0653-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="c0653-130">(Ce certificat doit avoir un nom d’objet ou un autre nom de sujet qui identifie l’utilisateur et doit être émis par une autorité de certification racine approuvée par les serveurs exécutant Lync Server 2013, se situer dans la période de validité du certificat et ne pas avoir été révoqué.) Pour être authentifié, les utilisateurs doivent uniquement taper un code confidentiel (PIN).</span><span class="sxs-lookup"><span data-stu-id="c0653-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="c0653-131">Les certificats sont particulièrement utiles pour les téléphones et autres appareils exécutant Microsoft Lync 2013 Phone Edition où il est difficile d’entrer un nom d’utilisateur et/ou un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="c0653-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

