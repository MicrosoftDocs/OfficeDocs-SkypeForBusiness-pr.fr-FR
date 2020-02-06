---
title: Authentification des utilisateurs et des clients pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Un utilisateur approuvé est une personne dont les informations d’identification ont été authentifiées par un serveur approuvé dans Skype entreprise Server. Il s’agit généralement d’un serveur frontal Standard Edition Server Enterprise Edition ou Director. Skype entreprise Server repose sur les services de domaine Active Directory comme le référentiel principal de confiance des informations d’identification de l’utilisateur.
ms.openlocfilehash: 2ffabce6546bf8b542503f8c80fe5cb2b952c568
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815582"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Authentification des utilisateurs et des clients pour Skype entreprise Server
 
Un utilisateur approuvé est une personne dont les informations d’identification ont été authentifiées par un serveur approuvé dans Skype entreprise Server. Il s’agit généralement d’un serveur frontal Standard Edition Server Enterprise Edition ou Director. Skype entreprise Server repose sur les services de domaine Active Directory comme le référentiel principal de confiance des informations d’identification de l’utilisateur.
  
L’authentification consiste à fournir des informations d’identification d’utilisateur à un serveur approuvé. Skype entreprise Server utilise les protocoles d’authentification suivants, en fonction de l’État et de l’emplacement de l’utilisateur.
  
- **Protocole de sécurité MIT Kerberos version 5** pour les utilisateurs internes disposant d’informations d’identification Active Directory. Kerberos nécessite une connectivité client aux services de domaine Active Directory (AD FS), ce qui explique pourquoi il ne peut pas être utilisé pour authentifier les clients extérieurs au pare-feu de l’entreprise.
    
- **Protocole NTLM** pour les utilisateurs disposant d’informations d’identification Active Directory qui se connectent à partir d’un point de terminaison extérieur au pare-feu d’entreprise. Le service Edge d’accès transmet les demandes d’ouverture de session à un réalisateur, le cas échéant, ou à un serveur frontal pour l’authentification. Le service Edge d’accès n’effectue aucune authentification.
    
    > [!NOTE]
    > Le protocole NTLM offrant une protection plus faible que Kerberos contre les attaques, certaines organisations minimisent l’utilisation de NTLM. Par conséquent, l’accès à Skype entreprise Server peut être limité à un réseau interne ou à un client connecté par le biais d’une connexion VPN ou DirectAccess. 
  
- **Protocole Digest** pour utilisateurs anonymes. Les utilisateurs anonymes sont des utilisateurs externes qui ne disposent pas d’informations d’identification Active Directory reconnues mais qui ont été invités à une conférence sur site et qui possèdent une clé de conférence valide. L’authentification Digest n’est pas utilisée pour d’autres interactions clients.
    
L’authentification de Skype entreprise Server comporte deux phases :
  
1. Une association de sécurité est établie entre le client et le serveur.
    
2. Le client et le serveur utilisent l’association de sécurité existante pour signer les messages qu’ils envoient et vérifier les messages qu’ils reçoivent. Les messages non authentifiés d’un client ne sont pas acceptés lorsque l’authentification est activée sur le serveur.
    
La confiance de l’utilisateur est associée à chaque message qui provient d’un utilisateur, et non à l’identité de l’utilisateur. Le serveur vérifie chaque message à la recherche d’informations d’identification d’utilisateur valides. Si les informations sont valides, le message est accepté non seulement par le premier serveur qui le reçoit mais par tous les autres serveurs dans le cloud de serveurs approuvés.
  
Les utilisateurs disposant d’informations d’identification valides émises par un partenaire fédéré sont approuvés mais peuvent éventuellement subir des contraintes supplémentaires les empêchant de profiter de la gamme complète de privilèges accordés aux utilisateurs internes.
  
Les protocoles ICE et TURN utilisent également le défi Digest tel que décrit dans le RFC TURN de l’IETF.
  
Les certificats clients permettent aux utilisateurs d’être authentifiés de manière alternative par Skype entreprise Server. Au lieu de fournir un nom d’utilisateur et un mot de passe, les utilisateurs disposent d’un certificat et d’une clé privée correspondant au certificat requis pour résoudre un défi cryptographique. (Ce certificat doit avoir un nom de sujet ou un autre nom d’objet identifiant l’utilisateur et doit être émis par une autorité de certification racine qui est approuvée par les serveurs exécutant Skype entreprise Server, qu’il n’ait pas été révoqué.) Pour être authentifié, les utilisateurs doivent uniquement saisir un code confidentiel (PIN). Les certificats s’avèrent particulièrement utiles pour les téléphones, les téléphones mobiles et autres appareils où il est difficile de saisir un nom d’utilisateur et un mot de passe.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Configuration requise pour la cryptographie en raison d’ASP .NET 4,5 

À partir de Skype entreprise Server 2015 CU5, AES n’est pas pris en charge pour ASP.NET 4,6 et cela peut entraîner le démarrage de l’application réunions Skype. Si un client utilise la valeur AES comme clé de validation de la clé d’ordinateur, vous devez redéfinir la valeur de la clé d’ordinateur sur SHA-1 ou un autre algorithme pris en charge sur le niveau du site de l’application réunions Skype sur IIS. Le cas échéant, voir [gestion des configurations d’IIS 8,0 ASP.net](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) pour obtenir des instructions.
  
Les autres valeurs prises en charge sont les suivantes :
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  Les valeurs AES, 3DES et MD5 ne sont plus autorisées, car elles se trouvaient auparavant dans ASP.NET 4. Pour plus d’informations, reportez-vous [à la ASP.NET 4,5, PT. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) .
  
