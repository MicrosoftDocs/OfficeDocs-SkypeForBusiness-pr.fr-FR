---
title: 'Lync Server 2013 : authentification utilisateur et client'
description: 'Lync Server 2013 : authentification utilisateur et client.'
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
ms.openlocfilehash: ef545dda38e9ab4236e93df769ead393648194cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569810"
---
# <a name="user-and-client-authentication-for-lync-server-2013"></a>Authentification utilisateur et client pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-11_

Un utilisateur approuvé est un utilisateur dont les informations d’identification ont été authentifiées par un serveur approuvé dans Microsoft Lync Server 2013. Il s’agit généralement d’un serveur Standard Edition, d’un serveur frontal Enterprise Edition ou d’un directeur. Lync Server 2013 repose sur les services de domaine Active Directory en tant que référentiel principal unique approuvé des informations d’identification de l’utilisateur.

L’authentification consiste à donner des informations d’identification des utilisateurs à un serveur approuvé. Lync Server 2013 utilise les protocoles d’authentification suivants, en fonction de l’État et de l’emplacement de l’utilisateur.

  - Le **protocole MIT Kerberos, version 5** pour les utilisateurs internes disposant d’informations d’identification Active Directory. Kerberos nécessite la connectivité du client aux services de domaine Active Directory, raison pour laquelle il ne peut pas être utilisé pour authentifier des clients situés en dehors du pare-feu de l’entreprise.

  - Le **protocole NTLM** pour les utilisateurs disposant d’informations d’identification Active Directory qui se connectent à partir d’un système d’extrémité situé à l’extérieur du pare-feu de l’entreprise. Le service Edge d’accès transmet les demandes de connexion à un directeur, s’il existe, ou à un serveur frontal à des fins d’authentification. Le service lui-même ne procède pas à l’authentification.
    
    <div>
    

    > [!NOTE]  
    > Le protocole NTLM offre une protection contre les attaques plus faible que Kerberos, c’est pourquoi certaines organisations limitent son utilisation. Par conséquent, l’accès à Lync Server 2013 peut être limité à des clients ou à des clients connectés via une connexion VPN ou DirectAccess.

    
    </div>

  - Le **protocole Digest** pour les utilisateurs dits « anonymes ». Les utilisateurs anonymes sont des utilisateurs externes qui n’ont pas d’informations d’identification Active Directory reconnues, mais qui ont été invités à une conférence sur site pour laquelle ils disposent d’une clé de conférence valide. L’authentification Digest n’est pas utilisée pour les autres interactions avec les clients.

L’authentification Lync Server 2013 se compose de deux phases :

1.  Une association de sécurité est établie entre le client et le serveur.

2.  Le client et le serveur utilisent l’association de sécurité existante pour signer les messages envoyés et pour vérifier les messages reçus. Les messages non authentifiés d’un client sont refusés lorsque l’authentification est activée sur le serveur.

L’approbation d’un utilisateur est attachée à chaque message envoyé par l’utilisateur, et non à l’identité de l’utilisateur proprement dite. Le serveur vérifie la validité des informations d’identification de l’utilisateur pour chaque message. Si les informations d’identification de l’utilisateur sont valides, le message n’est vérifié ni par le premier serveur qui le reçoit, ni par tous les serveurs du nuage de serveurs approuvés.

Vous pouvez utiliser d’autres contraintes, si nécessaire, pour empêcher les utilisateurs disposant d’informations d’identification valides délivrées par un partenaire fédéré d’accéder à l’ensemble des privilèges accordés aux utilisateurs internes.

Les protocoles ICE et TURN utilisent également l’authentification Digest, comme décrit dans le document RFC TURN de l’IETF.

Les certificats clients offrent un moyen alternatif aux utilisateurs d’être authentifiés par Lync Server 2013. Au lieu de fournir un nom d’utilisateur et un mot de passe, les utilisateurs disposent d’un certificat et de la clé privée correspondant au certificat nécessaire pour résoudre un défi de chiffrement. (Ce certificat doit avoir un nom d’objet ou un autre nom de sujet qui identifie l’utilisateur et doit être émis par une autorité de certification racine approuvée par les serveurs exécutant Lync Server 2013, se situer dans la période de validité du certificat et ne pas avoir été révoqué.) Pour être authentifié, les utilisateurs doivent uniquement taper un code confidentiel (PIN). Les certificats sont particulièrement utiles pour les téléphones et autres appareils exécutant Microsoft Lync 2013 Phone Edition où il est difficile d’entrer un nom d’utilisateur et/ou un mot de passe.

</div>

<span> </span>

</div>

</div>

</div>

