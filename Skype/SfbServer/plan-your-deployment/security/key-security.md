---
title: Principales fonctionnalités de sécurité dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype entreprise Server inclut plusieurs fonctionnalités de sécurité, notamment l’authentification de serveur à serveur, le contrôle d’accès basé sur les rôles et le stockage centralisé des données de configuration.
ms.openlocfilehash: cd86d1ac404cd2fe487f6f9369cc73df0d72c52f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296888"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Principales fonctionnalités de sécurité dans Skype entreprise Server
 
Skype entreprise Server inclut plusieurs fonctionnalités de sécurité, notamment l’authentification de serveur à serveur, le contrôle d’accès basé sur les rôles et le stockage centralisé des données de configuration. 
  
Cet article fournit une vue d’ensemble de la sécurité de Skype entreprise Server. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Principales fonctionnalités de sécurité dans Skype entreprise Server

La sécurité est un sujet très large. La sécurité s’étend à toutes les fonctionnalités de Skype entreprise Server ainsi qu’aux bases de données, services et matériels qui constituent un écosystème Skype entreprise Server. Cet article présente certaines des fonctions de Skype entreprise Server en particulier qui sont conçues pour la sécurité.
  
### <a name="planning-and-design-tools"></a>Outils de planification et de conception

Skype entreprise Server est doté de deux outils pour faciliter la planification et la conception et réduire le risque de configuration de composants Skype entreprise Server. 
  
- L' **outil de planification topologique** automatise une grande partie du processus de conception topologique. Vous pouvez exporter les résultats de l’outil de planification au générateur de topologie, qui est l’outil requis pour installer chaque serveur exécutant Skype entreprise Server.
    
- **Le générateur de topologie** stocke toutes les informations de configuration dans le magasin central de gestion.
    
Pour plus d’informations sur ces outils, reportez-vous à la rubrique [outils de gestion de Skype entreprise Server](../../management-tools/management-tools.md).
  
### <a name="central-management-store"></a>Magasin central de gestion

Dans Skype entreprise Server, les données de configuration relatives aux serveurs et services font partie du magasin central de gestion. Le centre de gestion central fournit un stockage fiable schematized des données nécessaires pour définir, configurer, gérer, gérer, décrire et utiliser un déploiement de Skype entreprise Server. Il valide également les données afin de garantir la cohérence de la configuration. Toutes les modifications apportées aux données de configuration se produisent dans le magasin de gestion central, ce qui élimine les problèmes liés à la synchronisation. 
  
Les copies en lecture seule des données sont répliquées sur tous les serveurs au sein de la topologie, y compris les serveurs Edge et les serveurs Survivable Branch Appliance. La réplication est gérée par un service exécuté par défaut dans le contexte du service réseau, ce qui limite les droits et autorisations à ceux d’un simple utilisateur sur l’ordinateur. 
  
### <a name="server-to-server-authentication"></a>Authentification serveur à serveur

Dans Skype entreprise Server, il est possible de configurer l’authentification entre les serveurs à l’aide du protocole d’autorisation Open (OAuth). Par exemple, vous pouvez configurer Skype entreprise Server pour s’authentifier auprès d’un serveur exécutant Microsoft Exchange Server 2016. À l’aide du protocole OAuth, Skype entreprise Server et Microsoft Exchange Server peuvent être approuvés. Cela permet d’intégrer les produits de façon transparente. Pour plus d’informations, reportez-vous à [gérer l’authentification de serveur à serveur (OAuth) et aux applications partenaires dans Skype entreprise Server](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Interface de gestion Windows PowerShell et web

Skype entreprise Server fournit une interface de gestion puissante, basée sur l’interface de ligne de commande Windows PowerShell. Il inclut des cmdlets de gestion de la sécurité et les fonctionnalités de sécurité de Windows PowerShell sont activées par défaut, de sorte que les utilisateurs ne peuvent pas facilement exécuter des scripts. Cela signifie que les logiciels par défaut sont configurés pour renforcer la sécurité et réduire les possibilités d’attaque. Pour plus d’informations sur la prise en charge de Windows PowerShell Management dans Skype entreprise Server, reportez-vous à la rubrique [Skype entreprise Server Management Shell](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Contrôle d’accès basé sur un rôle (RBAC)

Skype entreprise Server fournit un contrôle d’accès basé sur les rôles (RBAC) pour vous permettre de déléguer des tâches administratives tout en préservant la sécurité. You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require. Skype entreprise Server vous permet de créer un nouveau rôle et de modifier un rôle existant. 
  
## <a name="network-address-translation-nat"></a>Traduction d’adresses réseau (NAT)

Skype entreprise Server ne prend pas en charge l’utilisation de la traduction d’adresses réseau (NAT) sur l’interface interne du serveur Edge, mais prend en charge le placement de l’interface externe du service Edge d’accès, du service Edge de conférence Web et du service Edge A/V. derrière un routeur ou un pare-feu qui exécute la traduction d’adresses réseau (NAT) pour les topologies de serveur de périphérie unique et à l’échelle. S’il y a plusieurs serveurs Edge utilisant un programme d’équilibrage de la charge matérielle, ils ne peuvent pas utiliser la traduction d’adresses réseau. Si plusieurs serveurs Edge utilisent la traduction d’adresses réseau sur leurs interfaces externes, l’équilibrage de la charge DNS (Domain Name System) est requise. L’utilisation de l’équilibrage de la charge DNS vous permet de réduire le nombre d’adresses IP publiques par serveur Edge dans un pool de serveurs Edge. Pour plus d’informations, reportez-vous à la rubrique [scénarios de serveur Edge dans Skype entreprise Server](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Si vous vous fédérez avec des entreprises qui ont un déploiement de Microsoft Office Communications Server 2007 et que vous devez utiliser l’audio et la vidéo entre votre entreprise et une entreprise fédérée, les ports utilisés seront ceux de l’ancienne version des serveurs Edge déployés. Par exemple, les plages de ports requises pour ces versions antérieures doivent être ouvertes pour les deux entreprises tant que le partenaire fédéré a mis à niveau ses serveurs Edge vers Skype entreprise Server. Les exigences relatives aux ports peuvent alors être réévaluées et réduites, conformément à la nouvelle configuration. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Certificats simplifiés pour les serveurs Edge

L’Assistant Déploiement peut renseigner automatiquement les noms du sujet et les autres noms du sujet, et minimiser ainsi la possibilité d’inclure des entrées inutiles et éventuellement non sécurisées.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Cycle de développement d’une sécurité informatique fiable

Skype entreprise Server est conçu et développé conformément à la politique de [développement de la sécurité de Microsoft Trustworthy Computing](https://go.microsoft.com/fwlink/p/?linkid=68761) (SDL).
  
- **Fiabilité par conception** La première étape de la création d’un système de communication unifiée est de concevoir des modèles de menace et de tester chaque fonctionnalité à mesure qu’elle a été conçue. De plus, Microsoft effectue des tests sur des comportements anormaux afin de détecter les failles de sécurité résultant d’un comportement inattendu du produit. Plusieurs améliorations liées à la sécurité ont été intégrées dans le processus et les pratiques de codage. Au moment de la création, des outils détectent les dépassements de mémoire tampon et d’autres risques de sécurité potentiels avant l’archivage du code dans le produit final. Bien entendu, il est impossible de concevoir un produit capable de contrer toutes les menaces de sécurité encore inconnues. Aucun système ne saurait garantir une sécurité à toute épreuve. Toutefois, dans la mesure où le développement de produits a adopté des principes de conception sécurisés depuis le début, Skype entreprise Server incorpore les technologies de sécurité standard de l’industrie dans le cadre de son architecture.
    
- **Digne de confiance par défaut** Par défaut, les communications réseau dans Skype entreprise Server sont chiffrées. Dans la mesure où tous les serveurs utilisent des certificats et l’authentification Kerberos, TLS, Secure Real-Time Transport Protocol (SRTP) et d’autres techniques de cryptage standard de l’industrie, y compris le chiffrement AES (Advanced Encryption Standard) 128 bits, pratiquement tous les Les données de Business Server sont protégées sur le réseau. De plus, le contrôle d’accès basé sur les rôles rend possible le déploiement de serveurs exécutant Skype entreprise Server de sorte que chaque rôle de serveur ne exécute que les services et que seules les autorisations liées à ces services soient appropriées pour le rôle serveur.
    
- **Fiabilité du déploiement** Toute la documentation de Skype entreprise Server comporte des recommandations et des recommandations pour vous aider à déterminer et configurer les niveaux de sécurité optimaux pour votre déploiement et à évaluer les risques liés à l’activation des options non par défaut.
    

