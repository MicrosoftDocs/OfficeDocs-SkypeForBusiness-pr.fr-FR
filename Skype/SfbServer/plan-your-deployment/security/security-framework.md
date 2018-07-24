---
title: Infrastructure de sécurité pour Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité de Skype pour Business Server. Il est essentiel pour les décisions adéquates sur la sécurisation de votre Skype particulier pour le déploiement de serveur d’entreprise de comprendre comment ces éléments fonctionnent ensemble.
ms.openlocfilehash: 487b3ea7f57c1a008327be2b9b31664a160e8425
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983615"
---
# <a name="security-framework-for-skype-for-business-server"></a>Infrastructure de sécurité pour Skype pour Business Server
 
Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité de Skype pour Business Server. Il est essentiel pour les décisions adéquates sur la sécurisation de votre Skype particulier pour le déploiement de serveur d’entreprise de comprendre comment ces éléments fonctionnent ensemble.
  
Ces éléments sont les suivants :
  
- Services de domaine Active Directory (AD DS) fournit un référentiel centralisé approuvé unique pour les comptes d’utilisateurs et les ressources réseau.
    
- RBAC (Contrôle d’accès basé sur un rôle) vous permet de déléguer les tâches d’administration tout en maintenant des normes élevées en matière de sécurité.
    
- L’infrastructure à clé publique (PKI, Public Key Infrastructure) utilise des certificats émis par des autorités de certification approuvées afin d’authentifier les serveurs et de garantir l’intégrité des données.
    
- Le protocole de transport TLS (Transport Layer Security), HTTPS sur SSL (HTTPS) et MTLS (Mutual TLS) permettent l’authentification des points de terminaison et le chiffrement des messages instantanés. Les flux multimédias point à point sont chiffrés à l’aide du protocole SRTP (protocole de transport sécurisé en temps réel).
    
- Protocoles standard d’authentification des utilisateurs, le cas échéant.
    
- Windows PowerShell propose des fonctionnalités de sécurité qui sont activées par défaut afin que les utilisateurs ne peuvent pas facilement ou sans le savoir exécuter les scripts.
    
Ces éléments fondamentaux de la sécurité fonctionnent ensemble pour définir les utilisateurs approuvés, serveurs, connexions et opérations pour garantir sécurisées pour Skype pour Business Server.
  
## <a name="in-this-section"></a>Contenu de cette section

Les rubriques de cette section décrivent comment chacun de ces éléments fondamentaux pour améliorer la sécurité de votre Skype pour l’infrastructure de serveur d’entreprise.
  
- [Services de domaine Active Directory pour Skype pour Business Server](active-directory-domain-services.md)
    
- [Contrôle d’accès basé sur un rôle (RBAC) pour Skype pour Business Server](role-based-access-control-rbac.md)
    
- [Infrastructure à clé publique pour Skype pour Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS et MTLS pour Skype pour Business Server](tls-and-mtls.md)
    
- [Chiffrement pour Skype pour Business Server](encryption.md)
    
- [Authentification utilisateur et client pour Skype pour Business Server](user-and-client-authentication.md)
    
- [Windows PowerShell et Skype pour les outils de gestion de serveur d’entreprise](management-tools.md)
    

