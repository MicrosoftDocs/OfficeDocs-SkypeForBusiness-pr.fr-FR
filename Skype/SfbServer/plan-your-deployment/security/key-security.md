---
title: Fonctionnalités de sécurité clés dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype pour Business Server inclut plusieurs fonctionnalités de sécurité, notamment l’authentification serveur à serveur, le contrôle d’accès basé sur un rôle et le stockage centralisé des données de configuration.
ms.openlocfilehash: 5a0a82800be8158b6d54e4e01e7609d3e6b3714d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894279"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Fonctionnalités de sécurité clés dans Skype pour Business Server
 
Skype pour Business Server inclut plusieurs fonctionnalités de sécurité, notamment l’authentification serveur à serveur, le contrôle d’accès basé sur un rôle et le stockage centralisé des données de configuration. 
  
Cet article fournit une présentation de haut niveau de Skype pour la sécurité du serveur d’entreprise. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Fonctionnalités de sécurité clés dans Skype pour Business Server

La sécurité est un sujet très large. Sécurité atteint parmi toutes les fonctionnalités de Skype pour Business Server ainsi que les bases de données, les services et les matériel qui constituent un Skype pour écosystème Business Server. Cet article décrit certaines des fonctionnalités de Skype pour Business Server en particulier qui sont conçues pour la sécurité.
  
### <a name="planning-and-design-tools"></a>Outils de planification et de conception

Skype pour Business Server fournit deux outils pour faciliter la planification et la conception et à réduire le risque de mal configuration Skype pour les composants du serveur d’entreprise. 
  
- **Outil de planification de la topologie** automatise une grande partie du processus de conception de topologie. Vous pouvez exporter les résultats à partir de l’outil de planification pour le Générateur de topologie, qui est un outil qui est requis pour installer chaque serveur exécutant Skype pour Business Server.
    
- **Le générateur de topologie** stocke toutes les informations de configuration dans le magasin central de gestion.
    
Pour plus d’informations sur ces outils, voir [Skype Business Server des outils de gestion](../../management-tools/management-tools.md).
  
### <a name="central-management-store"></a>Magasin central de gestion

Dans Skype pour Business Server, les données de configuration sur les serveurs et services fait partie du magasin Central de gestion. Magasin Central de gestion fournit un stockage fiable, schématisé des données nécessaires pour définir, configurer, gérer, administrer, décrivent et utiliser un Skype pour le déploiement de serveur d’entreprise. Il valide également les données afin de garantir la cohérence de la configuration. Toutes les modifications apportées à ces données de configuration se produire dans le magasin Central de gestion, élimination des problèmes « de désynchronisation ». 
  
Les copies en lecture seule des données sont répliquées sur tous les serveurs au sein de la topologie, y compris les serveurs Edge et les serveurs Survivable Branch Appliance. La réplication est gérée par un service exécuté par défaut dans le contexte du service réseau, ce qui limite les droits et autorisations à ceux d’un simple utilisateur sur l’ordinateur. 
  
### <a name="server-to-server-authentication"></a>Authentification serveur à serveur

Dans Skype pour Business Server, l’authentification peut être configurée entre les serveurs à l’aide du protocole Open Authorization (OAuth). Par exemple, vous pouvez configurer Skype pour s’authentifier auprès d’un serveur qui exécute Microsoft Exchange Server 2016 Business Server. À l’aide du protocole OAuth, le Skype pour Business Server et Microsoft Exchange Server permettre s’approuvent mutuellement. Cela permet d’intégrer les produits de façon transparente. Pour plus d’informations, voir [gérer l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Skype pour Business Server](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Interface de gestion Windows PowerShell et web

Skype pour Business Server fournit une interface de gestion puissants, basée sur l’interface de ligne de commande Windows PowerShell. Il inclut les applets de commande pour la gestion de la sécurité et les fonctionnalités de sécurité de Windows PowerShell sont activées par défaut afin que les utilisateurs ne peuvent pas facilement ou sans le savoir exécuter les scripts. Cela signifie que les valeurs par défaut du logiciel sont configurés pour aider à optimiser la sécurité et de réduire les possibilités d’attaque automatiquement. Pour plus d’informations sur le support de gestion de Windows PowerShell dans Skype pour Business Server, consultez la rubrique [Skype pour Business Server Management Shell](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Contrôle d’accès basé sur un rôle (RBAC)

Skype pour Business Server fournit le contrôle d’accès basé sur un rôle (RBAC) vous permet de déléguer des tâches administratives tout en conservant les normes de sécurité strictes. You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require. Skype pour Business Server offre la possibilité de créer un nouveau rôle et également la possibilité de modifier un rôle existant. 
  
## <a name="network-address-translation-nat"></a>Traduction d’adresses réseau (NAT)

Skype pour Business Server ne prend pas en charge l’utilisation de la traduction d’adresses réseau (NAT) sur l’interface interne du serveur Edge, mais il ne prend pas en charge la placer l’interface externe du service Edge d’accès, service Edge de conférence Web et A / V Edge service derrière un routeur ou un pare-feu qui effectue la traduction d’adresses réseau (NAT) pour unique et à l’échelle consolidée topologies de serveur Edge. S’il y a plusieurs serveurs Edge utilisant un programme d’équilibrage de la charge matérielle, ils ne peuvent pas utiliser la traduction d’adresses réseau. Si plusieurs serveurs Edge utilisent la traduction d’adresses réseau sur leurs interfaces externes, l’équilibrage de la charge DNS (Domain Name System) est requise. L’utilisation de l’équilibrage de la charge DNS vous permet de réduire le nombre d’adresses IP publiques par serveur Edge dans un pool de serveurs Edge. Pour plus d’informations, voir [les scénarios de serveur de transport Edge dans Skype pour Business Server](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Si vous vous fédérez avec des entreprises qui ont un déploiement de Microsoft Office Communications Server 2007 et que vous devez utiliser l’audio et la vidéo entre votre entreprise et une entreprise fédérée, les ports utilisés seront ceux de l’ancienne version des serveurs Edge déployés. Par exemple, les plages de ports requis pour les anciennes versions doivent être ouvert pour les deux entreprises jusqu'à ce que le partenaire fédéré met à niveau les serveurs de périphérie Skype pour Business Server. Les exigences relatives aux ports peuvent alors être réévaluées et réduites, conformément à la nouvelle configuration. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Certificats simplifiés pour les serveurs Edge

L’Assistant Déploiement peut renseigner automatiquement les noms du sujet et les autres noms du sujet, et minimiser ainsi la possibilité d’inclure des entrées inutiles et éventuellement non sécurisées.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Cycle de développement d’une sécurité informatique fiable

Skype pour Business Server est conçu et développé conformément à la [Microsoft Trustworthy Computing Security Development Lifecycle](https://go.microsoft.com/fwlink/p/?linkid=68761) (SDL).
  
- **Fiable par conception** La première étape de création d’un système de communications unifiées plus sûr était de concevoir des modèles de menace et tester chaque fonctionnalité qu’il a été conçu. De plus, Microsoft effectue des tests sur des comportements anormaux afin de détecter les failles de sécurité résultant d’un comportement inattendu du produit. Plusieurs améliorations liées à la sécurité ont été intégrées dans le processus et les pratiques de codage. Au moment de la création, des outils détectent les dépassements de mémoire tampon et d’autres risques de sécurité potentiels avant l’archivage du code dans le produit final. Bien entendu, il est impossible de concevoir un produit capable de contrer toutes les menaces de sécurité encore inconnues. Aucun système ne saurait garantir une sécurité à toute épreuve. Toutefois, étant donné que le développement de produits adopté les principes de conception sécurisée à partir du début, Skype pour Business Server intègre les technologies de sécurité standard en tant que partie de son architecture.
    
- **Fiable par défaut** Par défaut, les communications réseau dans Skype pour Business Server sont chiffrées. Étant donné que tous les serveurs utilisent des certificats et l’authentification Kerberos, TLS, Secure Real-Time Transport Protocol (SRTP) et autres techniques de chiffrement standard, y compris le chiffrement 128 bits Standard AES (Advanced Encryption) pratiquement tous les Skype pour Données métiers du serveur sont protégées sur le réseau. En outre, le contrôle d’accès basé sur un rôle rend possible de déployer des serveurs exécutant Skype pour Business Server afin que chaque rôle de serveur s’exécute uniquement les services et possède les autorisations liées à ces services, qui sont appropriés pour le rôle de serveur.
    
- **Fiable par déploiement** Tous les Skype pour la documentation sur Business Server inclut les meilleures pratiques et recommandations pour vous aider à déterminer et configurer les niveaux de sécurité optimal pour votre déploiement et évaluer les risques de sécurité de l’activation des options par défaut.
    

