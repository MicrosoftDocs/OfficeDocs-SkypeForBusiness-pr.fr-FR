---
title: Infrastructure de sécurité pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité de Skype entreprise Server. Le fait de comprendre le fonctionnement de ces éléments est essentiel pour prendre des décisions éclairées sur la sécurisation de votre déploiement de Skype entreprise Server particulier.
ms.openlocfilehash: 8b82b09a8220139abe62ac4503ad8a7eddc28e99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296874"
---
# <a name="security-framework-for-skype-for-business-server"></a>Infrastructure de sécurité pour Skype entreprise Server
 
Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité de Skype entreprise Server. Le fait de comprendre le fonctionnement de ces éléments est essentiel pour prendre des décisions éclairées sur la sécurisation de votre déploiement de Skype entreprise Server particulier.
  
Ces éléments sont les suivants :
  
- Les services de domaine Active Directory (AD DS) fournissent un référentiel principal approuvé unique pour les comptes d’utilisateurs et les ressources réseau.
    
- RBAC (Contrôle d’accès basé sur un rôle) vous permet de déléguer les tâches d’administration tout en maintenant des normes élevées en matière de sécurité.
    
- L’infrastructure à clé publique (PKI, Public Key Infrastructure) utilise des certificats émis par des autorités de certification approuvées afin d’authentifier les serveurs et de garantir l’intégrité des données.
    
- Le protocole de transport TLS (Transport Layer Security), HTTPS sur SSL (HTTPS) et MTLS (Mutual TLS) permettent l’authentification des points de terminaison et le chiffrement des messages instantanés. Les flux multimédias point à point sont chiffrés à l’aide du protocole SRTP (protocole de transport sécurisé en temps réel).
    
- Protocoles standard d’authentification des utilisateurs, le cas échéant.
    
- Windows PowerShell fournit des fonctionnalités de sécurité qui sont activées par défaut, de sorte que les utilisateurs ne peuvent pas facilement exécuter des scripts.
    
Ces éléments de sécurité fondamentaux collaborent pour définir des utilisateurs, des serveurs, des connexions et des opérations de confiance pour garantir une base sécurisée pour Skype entreprise Server.
  
## <a name="in-this-section"></a>Contenu de cette section

Les rubriques de cette section expliquent comment chacun de ces éléments fondamentaux fonctionne pour renforcer la sécurité de votre infrastructure serveur Skype entreprise.
  
- [Services de domaine Active Directory pour Skype entreprise Server](active-directory-domain-services.md)
    
- [Contrôle d’accès basé sur les rôles (RBAC) pour Skype entreprise Server](role-based-access-control-rbac.md)
    
- [Infrastructure à clé publique pour Skype entreprise Server](public-key-infrastructure-for-skype.md)
    
- [TLS et MTLS pour Skype entreprise Server](tls-and-mtls.md)
    
- [Chiffrement pour Skype entreprise Server](encryption.md)
    
- [Authentification des utilisateurs et des clients pour Skype entreprise Server](user-and-client-authentication.md)
    
- [Outils de gestion de Windows PowerShell et de Skype entreprise Server](management-tools.md)
    

