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
description: Un confiance est un utilisateur dont les références ont été authentifiées par un serveur de confiance dans Skype pour Business Server 2015. Ce serveur est généralement un serveur Standard Edition, Enterprise Edition serveur frontal ou directeur. Skype pour Business Server s’appuie sur les Services de domaine Active Directory comme référentiel principal unique et fiable des informations d’identification de l’utilisateur.
ms.openlocfilehash: d8fa9265a4c27432dd4c2dba6e15c07e39f348b8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="user-and-client-authentication-for-skype-for-business-server-2015"></a>Authentification utilisateur et client pour Skype Entreprise Server 2015
 
Un confiance est un utilisateur dont les références ont été authentifiées par un serveur de confiance dans Skype pour Business Server 2015. Ce serveur est généralement un serveur Standard Edition, Enterprise Edition serveur frontal ou directeur. Skype pour Business Server s’appuie sur les Services de domaine Active Directory comme référentiel principal unique et fiable des informations d’identification de l’utilisateur.
  
L’authentification consiste à fournir des informations d’identification d’utilisateur à un serveur approuvé. Skype pour Business Server utilise les protocoles d’authentification suivants, en fonction de l’état et l’emplacement de l’utilisateur.
  
- **Protocole de MIT Kerberos version 5 de sécurité** pour les utilisateurs internes avec des informations d’identification Active Directory. Kerberos nécessite une connectivité client Active Directory Domain Services, c’est pourquoi il ne peut pas être utilisé pour authentifier les clients à l’extérieur du pare-feu d’entreprise.
    
- **Protocole NTLM** pour les utilisateurs avec des informations d’identification Active Directory qui sont connectent à partir d’un point de terminaison à l’extérieur du pare-feu d’entreprise. Le service Edge d’accès transmet les demandes d’ouverture de session à un directeur, le cas échéant, ou à un serveur frontal pour l’authentification. Le service Edge d’accès lui-même n’effectue aucune authentification.
    
    > [!NOTE]
    > Le protocole NTLM offrant une protection plus faible que Kerberos contre les attaques, certaines organisations minimisent l’utilisation de NTLM. Par conséquent, peut restreindre l’accès aux Skype pour Business Server 2015 internes ou clients connectés via une connexion VPN ou de DirectAccess. 
  
- **Protocole Digest** pour utilisateurs anonymes. Les utilisateurs anonymes sont des utilisateurs externes qui ne disposent pas d’informations d’identification Active Directory reconnues mais qui ont été invités à une conférence sur site et qui possèdent une clé de conférence valide. L’authentification Digest n’est pas utilisée pour d’autres interactions clients.
    
Skype pour l’authentification de Business Server 2015 consiste en deux phases :
  
1. Une association de sécurité est établie entre le client et le serveur.
    
2. Le client et le serveur utilisent l’association de sécurité existante pour signer les messages qu’ils envoient et vérifier les messages qu’ils reçoivent. Les messages non authentifiés d’un client ne sont pas acceptés lorsque l’authentification est activée sur le serveur.
    
La confiance de l’utilisateur est associée à chaque message qui provient d’un utilisateur, et non à l’identité de l’utilisateur. Le serveur vérifie chaque message à la recherche d’informations d’identification d’utilisateur valides. Si les informations sont valides, le message est accepté non seulement par le premier serveur qui le reçoit mais par tous les autres serveurs dans le cloud de serveurs approuvés.
  
Les utilisateurs disposant d’informations d’identification valides émises par un partenaire fédéré sont approuvés mais peuvent éventuellement subir des contraintes supplémentaires les empêchant de profiter de la gamme complète de privilèges accordés aux utilisateurs internes.
  
Les protocoles ICE et TURN utilisent également le défi Digest tel que décrit dans le RFC TURN de l’IETF.
  
Les certificats clients fournissent un autre moyen pour les utilisateurs doivent être authentifiés par Skype pour Business Server 2015. Au lieu de fournir un nom d’utilisateur et un mot de passe, les utilisateurs disposent d’un certificat et d’une clé privée correspondant au certificat requis pour résoudre un défi cryptographique. (Ce certificat doit avoir un nom d’objet ou d’un autre nom du sujet qui identifie l’utilisateur et doit être délivré par une autorité de certification racine qui est approuvée par les serveurs exécutant Skype pour Business Server 2015 et se situer dans la période de validité du certificat ne peut pas avoir été révoqué.) Pour être authentifié, les utilisateurs doivent taper dans un numéro d’identification personnel (PIN). Les certificats s’avèrent particulièrement utiles pour les téléphones, les téléphones mobiles et autres appareils où il est difficile de saisir un nom d’utilisateur et un mot de passe.
  

