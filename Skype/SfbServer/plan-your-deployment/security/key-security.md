---
title: Fonctionnalités de sécurité clés dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: 'Skype Entreprise Server comprend plusieurs fonctionnalités de sécurité, notamment l’authentification de serveur à serveur, le contrôle d’accès basé sur les rôles et le stockage centralisé des données de configuration.'
---

# <a name="key-security-features-in-skype-for-business-server"></a>Fonctionnalités de sécurité clés dans Skype Entreprise Server
 
Skype Entreprise Server comprend plusieurs fonctionnalités de sécurité, notamment l’authentification de serveur à serveur, le contrôle d’accès basé sur les rôles et le stockage centralisé des données de configuration. 
  
Cet article fournit une vue d’ensemble de la sécurité Skype Entreprise Server niveau supérieur. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Fonctionnalités de sécurité clés dans Skype Entreprise Server

La sécurité est un sujet très large. La sécurité touche toutes les fonctionnalités de Skype Entreprise Server ainsi que les bases de données, les services et le matériel qui font partie d Skype Entreprise Server écosystème. Cet article décrit certaines fonctionnalités de Skype Entreprise Server en particulier conçues pour la sécurité.
  
### <a name="planning-and-design-tools"></a>Outils de planification et de conception

Skype Entreprise Server fournit deux outils pour faciliter la planification et la conception et pour réduire le risque d’erreur de configuration Skype Entreprise Server composants. 
  
- **L’outil de planification de** topologie automatise une grande partie du processus de conception de topologie. Vous pouvez exporter les résultats de l’outil de planification vers le Générateur de topologie, qui est l’outil requis pour installer chaque serveur exécutant Skype Entreprise Server.
    
- **Le Générateur de topologie** stocke toutes les informations de configuration dans le magasin central de gestion.
    
Pour plus d’informations sur ces outils, [voir Skype Entreprise Server Management Tools](../../management-tools/management-tools.md).
  
### <a name="central-management-store"></a>Magasin central de gestion

Dans Skype Entreprise Server, les données de configuration relatives aux serveurs et aux services font partie du magasin central de gestion. Le magasin central de gestion fournit un stockage robuste et schématisé des données nécessaires pour définir, configurer, gérer, administrer, décrire et exploiter un déploiement Skype Entreprise Server de données. Il valide également les données afin de garantir la cohérence de la configuration. Toutes les modifications apportées à ces données de configuration se produisent dans le magasin central de gestion, ce qui élimine les problèmes « non synchronisés ». 
  
Les copies en lecture seule des données sont répliquées sur tous les serveurs au sein de la topologie, y compris les serveurs de périphérie. La réplication est gérée par un service qui, par défaut, s’exécute sous le contexte du service Réseau, réduisant ainsi les droits et autorisations à ceux d’un simple utilisateur sur l’ordinateur. 
  
### <a name="server-to-server-authentication"></a>Authentification de serveur à serveur

Dans Skype Entreprise Server, l’authentification peut être configurée entre les serveurs à l’aide du protocole Open Authorization (OAuth). Par exemple, vous pouvez configurer Skype Entreprise Server s’authentifier auprès d’un serveur exécutant Microsoft Exchange Server 2016. À l’aide du protocole OAuth, les Skype Entreprise Server et les Microsoft Exchange Server peuvent s’confiancer mutuellement. Cela permet d’intégrer les produits de manière transparente. Pour plus d’informations, [voir Gérer l’authentification de serveur à serveur (OAuth) et les applications partenaires dans Skype Entreprise Server](../../manage/authentication/server-to-server-and-partner-applications.md).
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell gestion basée sur le web et l’interface de gestion web

Skype Entreprise Server fournit une interface de gestion puissante, qui s’Windows PowerShell interface de ligne de commande. Elle comprend des applets de commande pour la gestion de la sécurité ; les fonctionnalités de sécurité Windows PowerShell sont activées par défaut, de sorte que les utilisateurs ne puissent pas exécuter de scripts facilement ou inconsciemment. Cela signifie que les paramètres par défaut des logiciels sont configurés de façon à optimiser la sécurité et à réduire les itinéraires d’agression. Pour plus d’informations Windows PowerShell la prise en charge de la gestion dans Skype Entreprise Server, voir [Skype Entreprise Server Management Shell](../../manage/management-shell.md). 
  
### <a name="role-based-access-control-rbac"></a>Contrôle d’accès basé sur un rôle

Skype Entreprise Server fournit un contrôle d’accès basé sur un rôle (RBAC) qui vous permet de déléguer des tâches administratives tout en maintenant des normes élevées en matière de sécurité. Vous pouvez recourir au contrôle d’accès basé sur un rôle pour appliquer le principe du « privilège minimum » selon lequel les utilisateurs reçoivent uniquement les droits d’administration nécessaires à leur travail. Skype Entreprise Server permet de créer un rôle et de modifier un rôle existant. 
  
## <a name="network-address-translation-nat"></a>Traduction d’adresses réseau (NAT)

Skype Entreprise Server ne prend pas en charge l’utilisation de la traduction d’adresses réseau (NAT) sur l’interface interne du serveur Edge, mais elle prend en charge le placement de l’interface externe du service Edge d’accès, du service Edge de conférence Web et du service Edge A/V derrière un routeur ou un pare-feu qui effectue la traduction d’adresses réseau (NAT) pour les topologies de serveur Edge consolidées et consolidées à l’échelle. Plusieurs serveurs Edge derrière un équilibreur de charge matérielle ne peuvent pas utiliser nat. Si plusieurs serveurs Edge utilisent nat sur leurs interfaces externes, l’équilibrage de charge DNS (Domain Name System) est requis. À son tour, l’utilisation de l’équilibrage de charge DNS vous permet de réduire le nombre d’adresses IP publiques par serveur Edge dans un pool de serveurs Edge. Pour plus d’informations, [voir scénarios de serveur Edge Skype Entreprise Server](../../plan-your-deployment/edge-server-deployments/scenarios.md).
  
> [!NOTE]
> Si vous vous fédérer avec des entreprises qui ont un déploiement Microsoft Office Communications Server 2007 et que vous devez utiliser l’audio/vidéo entre votre entreprise et l’entreprise fédérée, les ports requis sont ceux de l’ancienne version des serveurs Edge déployés. Par exemple, les plages de ports requises pour ces versions antérieures doivent être ouvertes pour les deux entreprises jusqu’à ce que le partenaire fédéré upgrade ses serveurs Edge vers Skype Entreprise Server. Les exigences relatives aux ports peuvent alors être réévaluées et réduites, conformément à la nouvelle configuration. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Certificats simplifiés pour les serveurs Edge

L’Assistant Déploiement peut remplir automatiquement les noms du sujet et les autres noms du sujet, réduisant le risque d’inclusion d’entrées inutiles et éventuellement non sécurisées.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>SDL (Trustworthy Computing Security Development Lifecycle)

Skype Entreprise Server est conçu et développé conformément au cycle de développement SDL ([Microsoft Trustworthy Computing Security Development Lifecycle](/previous-versions/ms995349(v=msdn.10))).
  
- **Fiable par conception** La première étape de la création d’un système de communications unifiées plus sécurisé consiste à concevoir des modèles de menace et à tester chaque fonctionnalité telle qu’elle a été conçue. En outre, Microsoft effectue des tests en dehors du comportement conçu afin de rechercher les vulnérabilités de sécurité résultant d’un comportement inattendu du produit. Plusieurs améliorations liées à la sécurité ont été intégrées dans le processus et les pratiques de codage. Au moment de la création, des outils détectent les dépassements de mémoire tampon et d’autres risques de sécurité potentiels avant l’archivage du code dans le produit final. Bien entendu, il est impossible de concevoir un produit capable de contrer toutes les menaces de sécurité encore inconnues. Aucun système ne saurait garantir une sécurité à toute épreuve. Toutefois, étant donné que le développement de produits a adopté les principes de conception sécurisée dès le début, Skype Entreprise Server intègre les technologies de sécurité standard du secteur comme élément fondamental de son architecture.
    
- **Fiable par défaut** Par défaut, les communications réseau Skype Entreprise Server sont chiffrées. Étant donné que tous les serveurs utilisent des certificats et l’authentification Kerberos, le protocole TLS, le protocole SRTP (Secure Real-Time Transport Protocol) et d’autres techniques de chiffrement standard, notamment le chiffrement AES (Advanced Encryption Standard) 128 bits, pratiquement toutes les données Skype Entreprise Server sont protégées sur le réseau. En outre, le contrôle d’accès basé sur un rôle permet de déployer des serveurs exécutant des Skype Entreprise Server afin que chaque rôle serveur n’exécute que les services et dispose uniquement des autorisations associées à ces services, qui sont appropriées pour le rôle serveur.
    
- **Fiable par déploiement** La documentation Skype Entreprise Server comprend les meilleures pratiques et les recommandations pour vous aider à déterminer et configurer les niveaux de sécurité optimaux pour votre déploiement et à évaluer les risques de sécurité liés à l’activation d’options autres que les options par défaut.
