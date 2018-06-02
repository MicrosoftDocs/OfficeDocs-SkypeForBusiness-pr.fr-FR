---
title: Authentification utilisateur et client pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Un utilisateur approuvé est un dont les informations d’identification ont été authentifiées par un serveur approuvé dans Skype pour Business Server 2015. Ce serveur est généralement un serveur Standard Edition, Enterprise Edition serveur frontal ou un directeur. Skype pour Business Server s’appuie sur les Services de domaine Active Directory comme référentiel principal unique approuvé, des informations d’identification de l’utilisateur.
ms.openlocfilehash: 0cdf51da260c8251ca5abbb3ce0834e196a8d51b
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2018
ms.locfileid: "19546522"
---
# <a name="user-and-client-authentication-for-skype-for-business-server-2015"></a>Authentification utilisateur et client pour Skype Entreprise Server 2015
 
Un utilisateur approuvé est un dont les informations d’identification ont été authentifiées par un serveur approuvé dans Skype pour Business Server 2015. Ce serveur est généralement un serveur Standard Edition, Enterprise Edition serveur frontal ou un directeur. Skype pour Business Server s’appuie sur les Services de domaine Active Directory comme référentiel principal unique approuvé, des informations d’identification de l’utilisateur.
  
L’authentification consiste à fournir des informations d’identification d’utilisateur à un serveur approuvé. Skype pour Business Server utilise les protocoles d’authentification suivants, selon l’état et l’emplacement de l’utilisateur.
  
- **Protocole de MIT Kerberos version 5 de sécurité** pour les utilisateurs internes avec des informations d’identification Active Directory. Kerberos nécessite une connexion de client à Active Directory Domain Services, c’est pourquoi il ne peut pas être utilisé pour authentifier les clients à l’extérieur du pare-feu d’entreprise.
    
- **Protocole NTLM** pour les utilisateurs avec des informations d’identification Active Directory qui sont connectent à partir d’un point de terminaison à l’extérieur du pare-feu d’entreprise. Le service Edge d’accès transmet les demandes de connexion à un directeur, s’il est présent, ou un serveur frontal pour l’authentification. Le service Edge d’accès lui-même n’effectue aucune authentification.
    
    > [!NOTE]
    > Le protocole NTLM offrant une protection plus faible que Kerberos contre les attaques, certaines organisations minimisent l’utilisation de NTLM. Par conséquent, peuvent restreindre l’accès aux Skype pour Business Server 2015 interne ou clients connectés via une connexion VPN ou DirectAccess. 
  
- **Protocole Digest** pour utilisateurs anonymes. Les utilisateurs anonymes sont des utilisateurs externes qui ne disposent pas d’informations d’identification Active Directory reconnues mais qui ont été invités à une conférence sur site et qui possèdent une clé de conférence valide. L’authentification Digest n’est pas utilisée pour d’autres interactions clients.
    
Skype pour l’authentification de Business Server 2015 se compose de deux phases :
  
1. Une association de sécurité est établie entre le client et le serveur.
    
2. Le client et le serveur utilisent l’association de sécurité existante pour signer les messages qu’ils envoient et vérifier les messages qu’ils reçoivent. Les messages non authentifiés d’un client ne sont pas acceptés lorsque l’authentification est activée sur le serveur.
    
La confiance de l’utilisateur est associée à chaque message qui provient d’un utilisateur, et non à l’identité de l’utilisateur. Le serveur vérifie chaque message à la recherche d’informations d’identification d’utilisateur valides. Si les informations sont valides, le message est accepté non seulement par le premier serveur qui le reçoit mais par tous les autres serveurs dans le cloud de serveurs approuvés.
  
Les utilisateurs disposant d’informations d’identification valides émises par un partenaire fédéré sont approuvés mais peuvent éventuellement subir des contraintes supplémentaires les empêchant de profiter de la gamme complète de privilèges accordés aux utilisateurs internes.
  
Les protocoles ICE et TURN utilisent également le défi Digest tel que décrit dans le RFC TURN de l’IETF.
  
Les certificats clients permettent également aux utilisateurs d’être authentifiés par Skype pour Business Server 2015. Au lieu de fournir un nom d’utilisateur et un mot de passe, les utilisateurs disposent d’un certificat et d’une clé privée correspondant au certificat requis pour résoudre un défi cryptographique. (Ce certificat doit avoir un nom du sujet ou le nom du sujet qui identifie l’utilisateur doit être émis par une autorité de certification racine approuvée par les serveurs exécutant Skype pour Business Server 2015, se trouver dans la période de validité du certificat et ne peut pas amène été révoqué). Pour être authentifié, les utilisateurs doivent taper dans un code confidentiel (PIN). Les certificats s’avèrent particulièrement utiles pour les téléphones, les téléphones mobiles et autres appareils où il est difficile de saisir un nom d’utilisateur et un mot de passe.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Exigences de chiffrement en raison d’ASP .NET 4.5 

À compter de Skype pour Business Server 2015 CU5, AES n’est pas pris en charge pour ASP.NET 4.6 et cela peut entraîner Skype réunions application Échec de démarrage. Si un client utilise AES en tant que la valeur de validation de la clé d’ordinateur, vous devrez rétablir la valeur de clé d’ordinateur SHA-1 ou un autre algorithme pris en charge au niveau du site d’application de réunions Skype sur IIS. Si nécessaire, consultez [Gestion de la Configuration IIS 8.0 ASP.NET](https://docs.microsoft.com/en-us/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) pour obtenir des instructions.
  
Autres valeurs prises en charge sont :
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
 Les valeurs MD5, 3DES et AES ne sont plus autorisées, comme une seule fois dans ASP.NET 4. [Améliorations de chiffrement dans ASP.NET 4.5, pt 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) a plus de détails.
  
