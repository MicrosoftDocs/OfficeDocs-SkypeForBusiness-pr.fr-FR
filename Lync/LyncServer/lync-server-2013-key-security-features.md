---
title: Principales fonctionnalités de sécurité dans Lync Server 2013
TOCTitle: Principales fonctionnalités de sécurité dans Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56269651
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Principales fonctionnalités de sécurité dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync Server 2013 inclut plusieurs fonctionnalités de sécurité (authentification serveur à serveur, contrôle d’accès basé sur un rôle, stockage centralisé des données de configuration, etc.).

Cet article décrit de façon générale la sécurité de Lync Server 2013.

## Principales fonctionnalités de sécurité dans Lync Server 2013

La sécurité est un sujet très large. Elle englobe toutes les fonctionnalités de Lync Server 2013, ainsi que les bases de données, les services et le matériel qui constituent un écosystème Lync. Cet article décrit certaines fonctionnalités de Lync Server 2013, notamment celles conçues pour la sécurité.

## Outils de planification et de conception

Lync Server 2013 inclut deux outils destinés à simplifier la planification et la conception et à réduire le risque d’erreur de configuration des composants Lync Server.

  - L’**outil de planification de la topologie** automatise la majeure partie du processus de conception de la topologie. Vous pouvez exporter les résultats de l’outil de planification vers le générateur de topologies (outil requis pour l’installation de chaque serveur exécutant Lync Server 2013).

  - Le **générateur de topologies** stocke toutes les informations de configuration dans le magasin central de gestion.

Pour plus d’informations sur ces outils, voir [Planification pour Lync Server 2013](lync-server-2013-planning.md).

## Magasin central de gestion

Dans Lync Server 2013, les données de configuration sur les serveurs et services font partie du magasin central de gestion. Celui-ci procure un stockage robuste et schématisé des données nécessaires pour définir, configurer, maintenir, décrire et exploiter un déploiement Lync Server. Il valide également les données afin de garantir la cohérence de la configuration. Toutes les modifications apportées aux données de configuration ont lieu dans le magasin central de gestion pour aider à éviter les problèmes de synchronisation.

Les copies en lecture seule des données sont répliquées sur tous les serveurs au sein de la topologie, y compris les serveurs Edge et les serveurs Survivable Branch Appliance. La réplication est gérée par un service exécuté par défaut dans le contexte du service réseau, ce qui limite les droits et autorisations à ceux d’un simple utilisateur sur l’ordinateur.

## Authentification serveur à serveur

Dans Lync Server 2013, l’authentification peut être configurée entre des serveurs à l’aide du protocole OAuth (Open Authorization). Par exemple, vous pouvez configurer Lync Server 2013 pour l’authentification auprès d’un serveur exécutant Exchange Server 2013. Le serveur Lync et le serveur Exchange peuvent s’approuver mutuellement à lֹ’aide du protocole OAuth. Ceci permet d’intégrer les produits de façon transparente. Pour plus d’informations, voir [Gestion de l’authentification serveur à serveur (Oauth) et des applications partenaires dans Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

## Interface de gestion Windows PowerShell et web

Lync Server 2013 offre une interface de gestion puissante, basée sur l’interface de ligne de commande Windows PowerShell. Il inclut des applets de commande pour la gestion de la sécurité. Les fonctionnalités de sécurité Windows PowerShell sont activées par défaut, de sorte que les utilisateurs ne puissent pas exécuter des scripts facilement ou inconsciemment. Cela signifie que les paramètres par défaut des logiciels sont configurés de façon à optimiser la sécurité et à réduire les itinéraires d’agression. Pour plus d’informations sur la prise en charge de la gestion Windows PowerShell dans Lync Server 2013, voir [Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md).

## Contrôle d’accès basé sur un rôle (RBAC)

Microsoft Lync Server 2013 inclut le contrôle d’accès basé sur un rôle (RBAC) pour vous permettre de déléguer les tâches d’administration tout en maintenant des normes élevées en matière de sécurité. Vous pouvez utiliser le contrôle d’accès basé sur un rôle pour suivre le principe du « privilège minimum » qui limitent les droits d’administration octroyés aux utilisateurs à ceux nécessaires à leur travail. Lync Server 2013 permet de créer des rôles et de modifier les rôles existants. Pour plus d’informations, voir [Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

## Traduction d’adresses réseau (NAT)

Lync Server 2013 ne prend pas en charge l’utilisation de la traduction d’adresses réseau sur l’interface interne du serveur Edge, mais autorise le placement de l’interface externe du service Edge d’accès, du service Edge de conférence web et du service Edge A/V derrière un routeur ou un pare-feu exécutant la traduction d’adresses réseau pour des topologies de serveur Edge uniques et consolidées mises à l’échelle à la fois. Plusieurs serveurs Edge derrière un programme d’équilibrage de la charge matérielle ne peuvent pas utiliser la traduction d’adresses réseau. Si plusieurs serveurs Edge utilisent la traduction d’adresses réseau sur leurs interfaces externes, l’équilibrage de la charge DNS (Domain Name System) est requise. L’utilisation de l’équilibrage de la charge DNS vous permet de réduire le nombre d’adresse IP publiques par serveur Edge dans un pool de serveurs Edge. Pour plus d’informations, voir [Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

> [!NOTE]  
> Si vous vous fédérez avec des entreprises qui ont un déploiement de Microsoft Office Communications Server 2007 et que vous devez utiliser l’audio et la vidéo entre votre entreprise et une entreprise fédérée, les ports utilisés seront ceux de l’ancienne version des serveurs Edge déployés. Par exemple, les plages de ports requises pour ces anciennes versions doivent être ouvertes pour les deux entreprises jusqu’à ce que le partenaire fédéré mette à niveau ses serveurs Edge vers Lync Server 2013. Les exigences relatives aux ports peuvent alors être réévaluées et réduites, conformément à la nouvelle configuration.

## Certificats simplifiés pour les serveurs Edge

L’Assistant Déploiement peut renseigner automatiquement les noms du sujet et les autres noms du sujet, et minimiser ainsi la possibilité d’inclure des entrées inutiles et éventuellement non sécurisées.

## Cycle de développement d’une sécurité informatique fiable

Lync Server 2013 a été conçu et développé conformément au cycle de développement d‘une sécurité informatique fiable décrit dans la page <http://go.microsoft.com/fwlink/?linkid=68761>.

  - **Fiable par conception**   Pour créer un système de communications unifiées plus sûr, la première étape était de concevoir des modèles de menace, puis de tester chaque nouvelle fonctionnalité durant sa conception. Par ailleurs, Microsoft effectue des tests en dehors du comportement prévu afin de détecter les failles de sécurité résultant d’un comportement inattendu du produit. Plusieurs améliorations liées à la sécurité ont été intégrées dans le processus et les pratiques de codage. Au moment de la création, des outils détectent les dépassements de mémoire tampon et d’autres risques de sécurité potentiels avant l’archivage du code dans le produit final. Bien entendu, il est impossible de concevoir un produit capable de contrer toutes les menaces de sécurité encore inconnues. Aucun système ne saurait garantir une sécurité à toute épreuve. Toutefois, dans la mesure où le développement du produit utilise des règles de conception prenant en compte la sécurité dès le départ, les technologies de sécurité standard font partie intégrante de l’architecture de Lync Server 2013.

  - **Fiable par défaut**   Les communications réseau dans Lync Server 2013 sont chiffrées par défaut. Tous les serveurs doivent utiliser des certificats et, en plus de l’authentification Kerberos, les protocoles TLS, SRTP (Secure Real-Time Transport Protocol) et d’autres techniques de chiffrement standard sont utilisés, notamment le chiffrement AES (Advanced Encryption Standard) 128 bits. Ces mesures permettent de protéger pratiquement l’ensemble des données de Lync Server sur le réseau. Par ailleurs, le contrôle d’accès basé sur un rôle rend possible le déploiement de serveurs exécutant Lync Server 2013 de sorte que chaque rôle de serveur exécute uniquement les services adaptés à ce rôle et dispose uniquement des autorisations associées à ces services.

  - **Fiable par déploiement**   Cette documentation relative à la sécurité, comme toute la documentation Lync Server 2013, inclut des meilleures pratiques et des recommandations destinées à vous aider à déterminer et configurer les niveaux de sécurité optimaux pour votre déploiement et à évaluer les risques de sécurité liés à l’activation d’options autres que les options par défaut.

