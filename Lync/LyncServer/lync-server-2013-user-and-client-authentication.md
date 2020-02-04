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
ms.openlocfilehash: 6c9c91f1b8355c95ceb3deae5f07e5c95710d036
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a>Authentification utilisateur et client pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-11_

Un utilisateur approuvé est une personne dont les informations d’identification ont été authentifiées par un serveur approuvé dans Microsoft Lync Server 2013. Il s’agit généralement d’un serveur frontal Standard Edition Server Enterprise Edition ou Director. Lync Server 2013 repose sur les services de domaine Active Directory comme le référentiel principal unique de confiance des informations d’identification de l’utilisateur.

L’authentification consiste à fournir des informations d’identification d’utilisateur à un serveur approuvé. Lync Server 2013 utilise les protocoles d’authentification suivants, en fonction de l’État et de l’emplacement de l’utilisateur.

  - **Protocole de sécurité MIT Kerberos version 5** pour les utilisateurs internes disposant d’informations d’identification Active Directory. Kerberos nécessite une connectivité client aux services de domaine Active Directory (AD FS), ce qui explique pourquoi il ne peut pas être utilisé pour authentifier les clients extérieurs au pare-feu de l’entreprise.

  - **Protocole NTLM** pour les utilisateurs disposant d’informations d’identification Active Directory qui se connectent à partir d’un point de terminaison extérieur au pare-feu d’entreprise. Le service Edge d’accès transmet les demandes d’ouverture de session à un réalisateur, le cas échéant, ou à un serveur frontal pour l’authentification. Le service Edge d’accès n’effectue aucune authentification.
    
    <div>
    

    > [!NOTE]  
    > Le protocole NTLM offrant une protection plus faible que Kerberos contre les attaques, certaines organisations minimisent l’utilisation de NTLM. Par conséquent, l’accès à Lync Server 2013 peut être limité à un réseau interne ou à un client connecté par le biais d’une connexion VPN ou DirectAccess.

    
    </div>

  - **Protocole Digest** pour utilisateurs anonymes. Les utilisateurs anonymes sont des utilisateurs externes qui ne disposent pas d’informations d’identification Active Directory reconnues mais qui ont été invités à une conférence sur site et qui possèdent une clé de conférence valide. L’authentification Digest n’est pas utilisée pour d’autres interactions clients.

L’authentification Lync Server 2013 comporte deux phases :

1.  Une association de sécurité est établie entre le client et le serveur.

2.  Le client et le serveur utilisent l’association de sécurité existante pour signer les messages qu’ils envoient et vérifier les messages qu’ils reçoivent. Les messages non authentifiés d’un client ne sont pas acceptés lorsque l’authentification est activée sur le serveur.

La confiance de l’utilisateur est associée à chaque message qui provient d’un utilisateur, et non à l’identité de l’utilisateur. Le serveur vérifie chaque message à la recherche d’informations d’identification d’utilisateur valides. Si les informations sont valides, le message est accepté non seulement par le premier serveur qui le reçoit mais par tous les autres serveurs dans le cloud de serveurs approuvés.

Les utilisateurs disposant d’informations d’identification valides émises par un partenaire fédéré sont approuvés mais peuvent éventuellement subir des contraintes supplémentaires les empêchant de profiter de la gamme complète de privilèges accordés aux utilisateurs internes.

Les protocoles ICE et TURN utilisent également le défi Digest tel que décrit dans le RFC TURN de l’IETF.

Les certificats clients fournissent aux utilisateurs un autre moyen d’authentification par Lync Server 2013. Au lieu de fournir un nom d’utilisateur et un mot de passe, les utilisateurs disposent d’un certificat et d’une clé privée correspondant au certificat requis pour résoudre un défi cryptographique. (Ce certificat doit avoir un nom de sujet ou un autre nom d’objet identifiant l’utilisateur et doit être émis par une autorité de certification racine qui est approuvée par les serveurs qui exécutent Lync Server 2013, qu’il n’a pas été révoqué.) Pour être authentifié, les utilisateurs doivent uniquement saisir un code confidentiel (PIN). Les certificats sont particulièrement utiles pour les téléphones et autres appareils exécutant Microsoft Lync 2013 Phone Edition où il est difficile d’entrer un nom d’utilisateur et/ou un mot de passe.

</div>

<span> </span>

</div>

</div>

</div>

