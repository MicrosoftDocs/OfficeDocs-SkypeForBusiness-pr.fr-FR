---
title: Authentification des utilisateurs et des clients pour Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Un utilisateur approuvé est un utilisateur dont les informations d’identification ont été authentifiées par un serveur approuvé dans Skype Entreprise Server. Il s’agit généralement d’un serveur Standard Edition, d’un serveur frontal Enterprise Edition ou d’un directeur. Skype Entreprise Server s’appuie sur les services de domaine Active Directory comme référentiel unique et approuvé des informations d’identification de l’utilisateur.
ms.openlocfilehash: b18d07a8cb0b427cf7cceb0fd81c8d657c98b7a1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401708"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Authentification des utilisateurs et des clients pour Skype Entreprise Server
 
Un utilisateur approuvé est un utilisateur dont les informations d’identification ont été authentifiées par un serveur approuvé dans Skype Entreprise Server. Il s’agit généralement d’un serveur Standard Edition, d’un serveur frontal Enterprise Edition ou d’un directeur. Skype Entreprise Server s’appuie sur les services de domaine Active Directory comme référentiel unique et approuvé des informations d’identification de l’utilisateur.
  
L’authentification consiste à donner des informations d’identification des utilisateurs à un serveur approuvé. Skype Entreprise Server utilise les protocoles d’authentification suivants, en fonction de l’état et de l’emplacement de l’utilisateur.
  
- Le **protocole MIT Kerberos, version 5** pour les utilisateurs internes disposant d’informations d’identification Active Directory. Kerberos nécessite la connectivité du client aux services de domaine Active Directory, raison pour laquelle il ne peut pas être utilisé pour authentifier des clients situés en dehors du pare-feu de l’entreprise.
    
- Le **protocole NTLM** pour les utilisateurs disposant d’informations d’identification Active Directory qui se connectent à partir d’un système d’extrémité situé à l’extérieur du pare-feu de l’entreprise. Le service Edge d’accès transmet les demandes de connexion à un directeur, s’il existe, ou à un serveur frontal à des fins d’authentification. Le service lui-même ne procède pas à l’authentification.
    
    > [!NOTE]
    > Le protocole NTLM offre une protection contre les attaques plus faible que Kerberos, c’est pourquoi certaines organisations limitent son utilisation. Par conséquent, l’accès aux Skype Entreprise Server peut être limité aux clients internes ou connectés via une connexion VPN ou DirectAccess. 
  
- Le **protocole Digest** pour les utilisateurs dits « anonymes ». Les utilisateurs anonymes sont des utilisateurs externes qui n’ont pas d’informations d’identification Active Directory reconnues, mais qui ont été invités à une conférence sur site pour laquelle ils disposent d’une clé de conférence valide. L’authentification Digest n’est pas utilisée pour les autres interactions avec les clients.
    
Skype Entreprise Server’authentification se compose de deux phases :
  
1. Une association de sécurité est établie entre le client et le serveur.
    
2. Le client et le serveur utilisent l’association de sécurité existante pour signer les messages envoyés et pour vérifier les messages reçus. Les messages non authentifiés d’un client sont refusés lorsque l’authentification est activée sur le serveur.
    
L’approbation d’un utilisateur est attachée à chaque message envoyé par l’utilisateur, et non à l’identité de l’utilisateur proprement dite. Le serveur vérifie la validité des informations d’identification de l’utilisateur pour chaque message. Si les informations d’identification de l’utilisateur sont valides, le message n’est vérifié ni par le premier serveur qui le reçoit, ni par tous les serveurs du nuage de serveurs approuvés.
  
Vous pouvez utiliser d’autres contraintes, si nécessaire, pour empêcher les utilisateurs disposant d’informations d’identification valides délivrées par un partenaire fédéré d’accéder à l’ensemble des privilèges accordés aux utilisateurs internes.
  
Les protocoles ICE et TURN utilisent également l’authentification Digest, comme décrit dans le document RFC TURN de l’IETF.
  
Les certificats clients offrent aux utilisateurs un autre moyen d’être authentifiés par Skype Entreprise Server. Au lieu de fournir un nom d’utilisateur et un mot de passe, les utilisateurs disposent d’un certificat et de la clé privée correspondant au certificat nécessaire pour résoudre un défi de chiffrement. (Ce certificat doit avoir un nom d’objet ou un autre nom de sujet qui identifie l’utilisateur et doit être émis par une autorité de certification racine qui est fiable par les serveurs exécutant Skype Entreprise Server, qui se trouve dans la période de validité du certificat et qui n’a pas été révoqué.) Pour être authentifiés, les utilisateurs doivent uniquement taper un code confidentiel. Les certificats sont particulièrement utiles pour les téléphones, téléphones mobiles et autres appareils sur lequel il est difficile d’entrer un nom d’utilisateur et un mot de passe.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Exigences de chiffrement en raison ASP.NET 4.5 

Depuis Skype Entreprise Server CU5 2015, AES n’est pas pris en charge pour ASP.NET 4.6, ce qui peut entraîner l’échec du démarrage de Skype Meetings App. Si un client utilise AES comme valeur de validation de clé d’ordinateur, vous devrez réinitialiser la valeur de la clé d’ordinateur sur SHA-1 ou un autre algorithme pris en charge au niveau du site d’application Skype Meetings sur IIS. Si nécessaire, voir [IIS 8.0 ASP.NET configuration management](/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) pour obtenir des instructions.
  
Les autres valeurs pris en charge sont les autres :
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  Les valeurs AES, 3DES et MD5 ne sont plus autorisées, car elles étaient une fois ASP.NET 4. [Les améliorations du chiffrement ASP.NET 4,5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) ont plus de détails.
