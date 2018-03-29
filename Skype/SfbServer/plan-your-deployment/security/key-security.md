---
title: Principales fonctionnalités de sécurité dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype pour Business Server 2015 inclut plusieurs fonctionnalités de sécurité, y compris le stockage centralisé des données de configuration, contrôle d’accès basé sur les rôles et d’authentification de serveur à serveur.
ms.openlocfilehash: 629444f4490022bb9f37f5c67f72f393345ec1a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="key-security-features-in-skype-for-business-server-2015"></a>Principales fonctionnalités de sécurité dans Skype Entreprise Server 2015
 
Skype pour Business Server 2015 inclut plusieurs fonctionnalités de sécurité, y compris le stockage centralisé des données de configuration, contrôle d’accès basé sur les rôles et d’authentification de serveur à serveur. 
  
Cet article fournit une vue d’ensemble détaillée de Skype pour la sécurité de Business Server 2015. 
  
## <a name="key-security-features-in-skype-for-business-server-2015"></a>Fonctions de sécurité essentielles dans Skype pour Business Server 2015

La sécurité est un sujet très large. Sécurité atteint sur toutes les fonctionnalités de Skype pour Business Server 2015 ainsi que des bases de données, des services et des matériel qui composent un Skype pour l’écosystème serveur d’entreprise. Cet article décrit certaines des fonctionnalités de Skype pour Business Server 2015 notamment qui sont conçus pour la sécurité.
  
### <a name="planning-and-design-tools"></a>Outils de planification et de conception

Skype pour Business Server 2015 fournit deux outils pour faciliter la planification et la conception et à réduire le risque de mal configurer Skype pour les composants serveur de l’entreprise. 
  
- **Outil de planification de topologie** automatise une grande partie du processus de conception de topologie. Vous pouvez exporter les résultats de l’outil de planification au Générateur de topologie, qui est l’outil qui est requis pour installer chaque serveur exécutant Skype pour Business Server 2015.
    
- **Le générateur de topologie** stocke toutes les informations de configuration dans le magasin central de gestion.
    
Pour plus d’informations sur ces outils, reportez-vous à la section [Skype Business Server 2015 des outils de gestion](../../management-tools/management-tools.md) et de [planifier votre Skype pour le déploiement de Business Server 2015](../../plan-your-deployment/plan-your-deployment.md).
  
### <a name="central-management-store"></a>Magasin central de gestion

Dans Skype pour Business Server 2015, les données de configuration sur les serveurs et les services fait partie du magasin Central de gestion. Le magasin Central de gestion fournit un stockage robuste, schématisé des données nécessaires pour définir, configurer, mettre à jour, administrer, décrire et opérer un Skype pour le déploiement du serveur de l’entreprise. Il valide également les données afin de garantir la cohérence de la configuration. Toutes les modifications apportées à ces données de configuration se produisent dans le magasin Central de gestion, éliminant les problèmes de « de désynchronisation ». 
  
Les copies en lecture seule des données sont répliquées sur tous les serveurs au sein de la topologie, y compris les serveurs Edge et les serveurs Survivable Branch Appliance. La réplication est gérée par un service exécuté par défaut dans le contexte du service réseau, ce qui limite les droits et autorisations à ceux d’un simple utilisateur sur l’ordinateur. 
  
### <a name="server-to-server-authentication"></a>Authentification serveur à serveur

Dans Skype pour Business Server 2015, l’authentification peut être configurée entre les serveurs en utilisant le protocole d’autorisation ouverte (OAuth). Par exemple, vous pouvez configurer Skype pour 2015 de serveur d’entreprise s’authentifier auprès d’un serveur qui exécute Microsoft Exchange Server 2016. À l’aide du protocole OAuth, le Skype pour Business Server et le Microsoft Exchange Server peut s’approuvent mutuellement. Cela permet d’intégrer les produits de façon transparente. Pour plus d’informations, consultez [authentification de serveur à gérer (OAuth) et les applications partenaires dans Skype pour Business Server 2015](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Interface de gestion Windows PowerShell et web

Skype pour Business Server 2015 fournit une interface de gestion puissante basée sur l’interface de ligne de commande de Windows PowerShell. Il contient des applets de commande pour la gestion de la sécurité et les fonctionnalités de sécurité de Windows PowerShell sont activées par défaut afin que les utilisateurs ne peuvent pas facilement ou non exécuter les scripts. Cela signifie que les paramètres par défaut du logiciel sont définies pour aider à optimiser la sécurité et de réduire les occasions d’attaques automatiquement. Pour plus d’informations sur le support de gestion de Windows PowerShell dans Skype pour Business Server 2015, consultez [Skype pour Business Server 2015 Management Shell](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Contrôle d’accès basé sur un rôle (RBAC)

Skype pour Business Server 2015 fournit un contrôle d’accès basé sur les rôles (RBAC) vous permet de déléguer des tâches administratives tout en conservant un niveau élevé de sécurité. Vous pouvez utiliser RBAC à suivre le principe du « moindre privilège », dans quels utilisateurs bénéficient uniquement des droits d’administration exigent de leurs tâches. Skype pour Business Server 2015 offre la possibilité de créer un nouveau rôle, ainsi que la possibilité de modifier un rôle existant. 
  
## <a name="network-address-translation-nat"></a>Traduction d’adresses réseau (NAT)

Skype pour Business Server 2015 ne prend pas en charge l’utilisation de la traduction d’adresses réseau (NAT) sur l’interface interne du serveur Edge, mais il ne prend pas en charge la mise de l’interface externe du service Edge d’accès, le service Web Conferencing Edge et A / V Edge service derrière un routeur ou un pare-feu qui effectue la traduction d’adresses réseau (NAT) pour à la fois unique et mise à l’échelle de consolider les topologies de serveur de transport Edge. S’il y a plusieurs serveurs Edge utilisant un programme d’équilibrage de la charge matérielle, ils ne peuvent pas utiliser la traduction d’adresses réseau. Si plusieurs serveurs Edge utilisent la traduction d’adresses réseau sur leurs interfaces externes, l’équilibrage de la charge DNS (Domain Name System) est requise. L’utilisation de l’équilibrage de la charge DNS vous permet de réduire le nombre d’adresses IP publiques par serveur Edge dans un pool de serveurs Edge. Pour plus d’informations, consultez [scénarios de serveur de transport Edge dans Skype pour Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Si vous vous fédérez avec des entreprises qui ont un déploiement de Microsoft Office Communications Server 2007 et que vous devez utiliser l’audio et la vidéo entre votre entreprise et une entreprise fédérée, les ports utilisés seront ceux de l’ancienne version des serveurs Edge déployés. Par exemple, les plages de ports requis pour les anciennes versions doivent être ouverte pour les deux entreprises jusqu'à ce que le partenaire fédéré met à niveau ses serveurs Edge à Skype pour Business Server 2015. Les exigences relatives aux ports peuvent alors être réévaluées et réduites, conformément à la nouvelle configuration. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Certificats simplifiés pour les serveurs Edge

L’Assistant Déploiement peut renseigner automatiquement les noms du sujet et les autres noms du sujet, et minimiser ainsi la possibilité d’inclure des entrées inutiles et éventuellement non sécurisées.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Cycle de développement d’une sécurité informatique fiable

Skype pour Business Server 2015 est conçu et développé dans le respect du [Microsoft Trustworthy Computing Security Development Lifecycle](https://go.microsoft.com/fwlink/p/?linkid=68761) (SDL).
  
- **Digne de confiance par défaut** La première étape dans la création d’un système de communications unifiées plus sûr était de concevoir des modèles de menace et de tester chaque fonction, qu’il a été conçu. De plus, Microsoft effectue des tests sur des comportements anormaux afin de détecter les failles de sécurité résultant d’un comportement inattendu du produit. Plusieurs améliorations liées à la sécurité ont été intégrées dans le processus et les pratiques de codage. Au moment de la création, des outils détectent les dépassements de mémoire tampon et d’autres risques de sécurité potentiels avant l’archivage du code dans le produit final. Bien entendu, il est impossible de concevoir un produit capable de contrer toutes les menaces de sécurité encore inconnues. Aucun système ne saurait garantir une sécurité à toute épreuve. Toutefois, parce que le développement de produits ont adopté les principes de conception sécurisée dès le début, Skype pour Business Server 2015 intègre les technologies de sécurité standard de secteur sous la forme d’un élément fondamental de son architecture.
    
- **Digne de confiance par défaut** Par défaut, les communications réseau dans Skype pour Business Server 2015 sont cryptées. Étant donné que tous les serveurs utilisent des certificats et l’authentification Kerberos, TLS, Secure Real-Time Transport Protocol (SRTP) et autres techniques de chiffrement standard, y compris le chiffrement Advanced Encryption Standard (AES) 128 bits pratiquement tous les Skype pour Données de serveur d’entreprise sont protégées sur le réseau. En outre, contrôle d’accès basé sur les rôles permet à déployer des serveurs Skype pour Business Server 2015 afin que chaque rôle de serveur s’exécute uniquement sur les services et qu’il possède les autorisations liées à ces services, qui sont appropriés pour le rôle de serveur.
    
- **Digne de confiance par le déploiement** Tous les Skype pour obtenir une documentation Business Server 2015 comprend les meilleures pratiques et recommandations pour vous aider à déterminer et configurer les niveaux de sécurité optimale pour votre déploiement et évaluer les risques de sécurité de l’activation des options de celle par défaut.
    

