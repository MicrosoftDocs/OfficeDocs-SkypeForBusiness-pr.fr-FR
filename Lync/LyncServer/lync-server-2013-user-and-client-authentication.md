---
title: 'Lync Server 2013: authentification utilisateur et client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 052c65bad805dff0d993cbf8533593c1f12915a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="e5b9b-102">Authentification utilisateur et client pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5b9b-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5b9b-103">_**Dernière modification de la rubrique:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="e5b9b-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="e5b9b-104">Un utilisateur approuvé est une personne dont les informations d’identification ont été authentifiées par un serveur approuvé dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e5b9b-105">Il s’agit généralement d’un serveur frontal Standard Edition Server Enterprise Edition ou Director.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="e5b9b-106">Lync Server 2013 repose sur les services de domaine Active Directory comme le référentiel principal unique de confiance des informations d’identification de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="e5b9b-107">L’authentification consiste à fournir des informations d’identification d’utilisateur à un serveur approuvé.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="e5b9b-108">Lync Server 2013 utilise les protocoles d’authentification suivants, en fonction de l’État et de l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="e5b9b-109">**Protocole de sécurité MIT Kerberos version 5** pour les utilisateurs internes disposant d’informations d’identification Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-109">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="e5b9b-110">Kerberos nécessite une connectivité client aux services de domaine Active Directory (AD FS), ce qui explique pourquoi il ne peut pas être utilisé pour authentifier les clients extérieurs au pare-feu de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-110">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="e5b9b-111">**Protocole NTLM** pour les utilisateurs disposant d’informations d’identification Active Directory qui se connectent à partir d’un point de terminaison extérieur au pare-feu d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-111">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="e5b9b-112">Le service Edge d’accès transmet les demandes d’ouverture de session à un réalisateur, le cas échéant, ou à un serveur frontal pour l’authentification.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-112">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="e5b9b-113">Le service Edge d’accès n’effectue aucune authentification.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-113">The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5b9b-114">Le protocole NTLM offrant une protection plus faible que Kerberos contre les attaques, certaines organisations minimisent l’utilisation de NTLM.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="e5b9b-115">Par conséquent, l’accès à Lync Server 2013 peut être limité à un réseau interne ou à un client connecté par le biais d’une connexion VPN ou DirectAccess.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="e5b9b-p106">**Protocole Digest** pour utilisateurs anonymes. Les utilisateurs anonymes sont des utilisateurs externes qui ne disposent pas d’informations d’identification Active Directory reconnues mais qui ont été invités à une conférence sur site et qui possèdent une clé de conférence valide. L’authentification Digest n’est pas utilisée pour d’autres interactions clients.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-p106">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="e5b9b-119">L’authentification Lync Server 2013 comporte deux phases:</span><span class="sxs-lookup"><span data-stu-id="e5b9b-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="e5b9b-120">Une association de sécurité est établie entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="e5b9b-p107">Le client et le serveur utilisent l’association de sécurité existante pour signer les messages qu’ils envoient et vérifier les messages qu’ils reçoivent. Les messages non authentifiés d’un client ne sont pas acceptés lorsque l’authentification est activée sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-p107">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="e5b9b-p108">La confiance de l’utilisateur est associée à chaque message qui provient d’un utilisateur, et non à l’identité de l’utilisateur. Le serveur vérifie chaque message à la recherche d’informations d’identification d’utilisateur valides. Si les informations sont valides, le message est accepté non seulement par le premier serveur qui le reçoit mais par tous les autres serveurs dans le cloud de serveurs approuvés.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-p108">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="e5b9b-126">Les utilisateurs disposant d’informations d’identification valides émises par un partenaire fédéré sont approuvés mais peuvent éventuellement subir des contraintes supplémentaires les empêchant de profiter de la gamme complète de privilèges accordés aux utilisateurs internes.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="e5b9b-127">Les protocoles ICE et TURN utilisent également le défi Digest tel que décrit dans le RFC TURN de l’IETF.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="e5b9b-128">Les certificats clients fournissent aux utilisateurs un autre moyen d’authentification par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="e5b9b-129">Au lieu de fournir un nom d’utilisateur et un mot de passe, les utilisateurs disposent d’un certificat et d’une clé privée correspondant au certificat requis pour résoudre un défi cryptographique.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="e5b9b-130">(Ce certificat doit avoir un nom de sujet ou un autre nom d’objet identifiant l’utilisateur et doit être émis par une autorité de certification racine qui est approuvée par les serveurs qui exécutent Lync Server 2013, qu’il n’a pas été révoqué.) Pour être authentifié, les utilisateurs doivent uniquement saisir un code confidentiel (PIN).</span><span class="sxs-lookup"><span data-stu-id="e5b9b-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="e5b9b-131">Les certificats sont particulièrement utiles pour les téléphones et autres appareils exécutant Microsoft Lync 2013 Phone Edition où il est difficile d’entrer un nom d’utilisateur et/ou un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="e5b9b-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

