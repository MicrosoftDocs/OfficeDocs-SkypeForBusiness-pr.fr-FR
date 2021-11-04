---
title: Infrastructure de sécurité pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité pour Skype Entreprise Server. Il est essentiel de comprendre comment ces éléments fonctionnent ensemble pour prendre des décisions éclairées sur la sécurisation de Skype Entreprise Server déploiement.
ms.openlocfilehash: a560d903b2a08e6444e561cb0fcdd9da978edb0c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740340"
---
# <a name="security-framework-for-skype-for-business-server"></a>Infrastructure de sécurité pour Skype Entreprise Server
 
Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité pour Skype Entreprise Server. Il est essentiel de comprendre comment ces éléments fonctionnent ensemble pour prendre des décisions éclairées sur la sécurisation de Skype Entreprise Server déploiement.
  
Ces éléments sont les suivants :
  
- Les services de domaine Active Directory offrent un référentiel centralisé, unique et fiable aux comptes d’utilisateurs et aux ressources réseau.
    
- Role-Based contrôle d’accès (RBAC) vous permet de déléguer des tâches administratives tout en maintenant des normes de sécurité élevées.
    
- L’infrastructure à clé publique (PKI) utilise des certificats émis par des autorités de certification (CA) pour authentifier les serveurs et garantir l’intégrité des données.
    
- Les protocoles TLS (Transport Layer Security), HTTPS sur SSL (HTTPS) et Mutual TLS (MTLS) permettent l’authentification des systèmes d’extrémité et le chiffrement des communications par messagerie instantanée. Les flux audio, vidéo et de partage d’application point à point sont chiffrés à l’aide du protocole SRTP (Secure Real Time Transport Protocol).
    
- Des protocoles standard sont utilisés pour l’authentification des utilisateurs, lorsque cela est possible.
    
- Windows PowerShell propose des fonctionnalités de sécurité activées par défaut afin que les utilisateurs ne puissent pas exécuter des scripts facilement ou sans le savoir.
    
Ces éléments de sécurité fondamentaux fonctionnent ensemble pour définir des utilisateurs, des serveurs, des connexions et des opérations de confiance afin de garantir une base sécurisée pour Skype Entreprise Server.
  
## <a name="in-this-section"></a>Dans cette section

Les rubriques de cette section décrivent le fonctionnement de chacun de ces éléments fondamentaux pour améliorer la sécurité de Skype Entreprise Server infrastructure.
  
- [Services de domaine Active Directory pour Skype Entreprise Server](active-directory-domain-services.md)
    
- [Contrôle d’accès basé sur un rôle (RBAC) pour Skype Entreprise Server](role-based-access-control-rbac.md)
    
- [Infrastructure à clé publique pour Skype Entreprise Server](public-key-infrastructure-for-skype.md)
    
- [TLS et MTLS pour Skype Entreprise Server](tls-and-mtls.md)
    
- [Chiffrement pour Skype Entreprise Server](encryption.md)
    
- [Authentification des utilisateurs et des clients pour Skype Entreprise Server](user-and-client-authentication.md)
    
- [Windows PowerShell et Skype Entreprise Server gestion des données](management-tools.md)
    

