---
title: Cadre de sécurité pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent la structure de sécurité de Skype pour Business Server 2015. Il est essentiel de prendre des décisions informées sur la sécurisation de votre Skype particulier pour le déploiement de Business Server 2015 de comprendre comment ces éléments fonctionnent ensemble.
ms.openlocfilehash: c29941a3e903b6318db2de0453589b5017e6f51b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="security-framework-for-skype-for-business-server-2015"></a>Cadre de sécurité pour Skype Entreprise Server 2015
 
Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent la structure de sécurité de Skype pour Business Server 2015. Il est essentiel de prendre des décisions informées sur la sécurisation de votre Skype particulier pour le déploiement de Business Server 2015 de comprendre comment ces éléments fonctionnent ensemble.
  
Ces éléments sont les suivants :
  
- Les Services de domaine Active Directory (AD DS) fournit un seul référentiel back-end de confiance pour les comptes d’utilisateurs et les ressources réseau.
    
- RBAC (Contrôle d’accès basé sur un rôle) vous permet de déléguer les tâches d’administration tout en maintenant des normes élevées en matière de sécurité.
    
- L’infrastructure à clé publique (PKI, Public Key Infrastructure) utilise des certificats émis par des autorités de certification approuvées afin d’authentifier les serveurs et de garantir l’intégrité des données.
    
- Le protocole de transport TLS (Transport Layer Security), HTTPS sur SSL (HTTPS) et MTLS (Mutual TLS) permettent l’authentification des points de terminaison et le chiffrement des messages instantanés. Les flux multimédias point à point sont chiffrés à l’aide du protocole SRTP (protocole de transport sécurisé en temps réel).
    
- Protocoles standard d’authentification des utilisateurs, le cas échéant.
    
- Windows PowerShell fournit des fonctionnalités de sécurité qui sont activées par défaut afin que les utilisateurs ne peuvent pas facilement ou non exécuter les scripts.
    
Ces éléments fondamentaux de la sécurité collaborent pour définir les utilisateurs approuvés, les serveurs, les connexions et les opérations afin de garantir une fondation sécurisée pour Skype pour Business Server 2015.
  
## <a name="in-this-section"></a>Contenu de cette section

Les rubriques de cette section décrivent le fonctionne de chacun de ces éléments fondamentaux pour améliorer la sécurité de votre Skype pour infrastructure de serveur d’entreprise.
  
- [Services de domaine Active Directory pour Skype pour Business Server 2015](active-directory-domain-services.md)
    
- [Contrôle d’accès basé sur les rôles (RBAC) pour Skype pour Business Server 2015](role-based-access-control-rbac.md)
    
- [Infrastructure à clé publique pour Skype pour Business Server 2015](public-key-infrastructure-for-skype.md)
    
- [TLS et MTLS pour Skype pour Business Server 2015](tls-and-mtls.md)
    
- [Cryptage pour Skype pour Business Server 2015](encryption.md)
    
- [Authentification des utilisateurs et des clients de Skype pour Business Server 2015](user-and-client-authentication.md)
    
- [Windows PowerShell et Skype pour les outils de gestion Business Server 2015](management-tools.md)
    

