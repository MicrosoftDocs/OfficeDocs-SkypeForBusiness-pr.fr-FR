---
title: 'Lync Server 2013 : fonctionnalités de sécurité clés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a1ff88b11c7d0ce007fc3bac38e7e3618771fb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514021"
---
# <a name="key-security-features-in-lync-server-2013"></a>Principales fonctionnalités de sécurité dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-18_

Lync Server 2013 comprend plusieurs fonctionnalités de sécurité, notamment l’authentification de serveur à serveur, le contrôle d’accès basé sur un rôle et le stockage centralisé des données de configuration.

Cet article offre une vue d’ensemble de la sécurité de Lync Server 2013.

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Principales fonctionnalités de sécurité dans Lync Server 2013

La sécurité est un sujet très large. La sécurité atteint toutes les fonctionnalités de Lync Server 2013, ainsi que les bases de données, les services et le matériel qui constituent un écosystème Lync. Cet article décrit certaines fonctionnalités de Lync Server 2013, notamment celles conçues pour la sécurité.

<div>

## <a name="planning-and-design-tools"></a>Outils de planification et de conception

Lync Server 2013 fournit deux outils pour faciliter la planification et la conception et réduire le risque de configuration inpropre des composants de Lync Server.

  - L' **outil de planification** de la topologie automatise une grande partie du processus de conception de la topologie. Vous pouvez exporter les résultats de l’outil de planification vers le générateur de topologie, qui est l’outil requis pour installer chaque serveur exécutant Lync Server 2013.

  - Le **Générateur de topologies** stocke toutes les informations de configuration dans le magasin central de gestion.

Pour plus d’informations sur ces outils, reportez-vous à la rubrique [Planning for Lync Server 2013](lync-server-2013-planning.md).

</div>

<div>

## <a name="central-management-store"></a>Magasin central de gestion

Dans Lync Server 2013, les données de configuration relatives aux serveurs et services font partie du magasin central de gestion. Le magasin central de gestion fournit un stockage robuste et schématisées des données nécessaires pour définir, configurer, maintenir, administrer, décrire et exploiter un déploiement Lync Server. Il valide également les données afin de garantir la cohérence de la configuration. Toutes les modifications apportées à ces données de configuration se produisent dans le magasin central de gestion, ce qui élimine les problèmes de « désynchronisation ».

Les copies en lecture seule des données sont répliquées sur tous les serveurs au sein de la topologie, y compris les serveurs de périphérie. La réplication est gérée par un service qui, par défaut, s’exécute sous le contexte du service Réseau, réduisant ainsi les droits et autorisations à ceux d’un simple utilisateur sur l’ordinateur.

</div>

<div>

## <a name="server-to-server-authentication"></a>Authentification de serveur à serveur

Dans Lync Server 2013, l’authentification peut être configurée entre les serveurs à l’aide du protocole OAuth (Open Authorization). Par exemple, vous pouvez configurer Lync Server 2013 pour l’authentification auprès d’un serveur qui exécute Exchange Server 2013. À l’aide du protocole OAuth, le serveur Lync et le serveur Exchange peuvent se faire confiance les uns des autres. Cela permet d’intégrer les produits de manière transparente. Pour plus d’informations, reportez-vous à la rubrique [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Interface de gestion basée sur le Web et la gestion basée sur Windows PowerShell

Lync Server 2013 fournit une interface de gestion puissante, basée sur l’interface de ligne de commande Windows PowerShell. Elle comprend des applets de commande pour la gestion de la sécurité ; les fonctionnalités de sécurité Windows PowerShell sont activées par défaut, de sorte que les utilisateurs ne puissent pas exécuter de scripts facilement ou inconsciemment. Cela signifie que les paramètres par défaut des logiciels sont configurés de façon à optimiser la sécurité et à réduire les itinéraires d’agression. Pour plus d’informations sur la prise en charge de la gestion Windows PowerShell dans Lync Server 2013, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="role-based-access-control-rbac"></a>Contrôle d’accès basé sur un rôle

Microsoft Lync Server 2013 fournit un contrôle d’accès basé sur un rôle (RBAC) pour vous permettre de déléguer des tâches administratives tout en conservant des normes de sécurité élevées. Vous pouvez recourir au contrôle d’accès basé sur un rôle pour appliquer le principe du « privilège minimum » selon lequel les utilisateurs reçoivent uniquement les droits d’administration nécessaires à leur travail. Lync Server 2013 offre la possibilité de créer un nouveau rôle et de modifier un rôle existant. Pour plus d’informations, reportez-vous à la rubrique [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>Traduction d’adresses réseau (NAT)

Lync Server 2013 ne prend pas en charge l’utilisation de la traduction d’adresses réseau (NAT) sur l’interface interne du serveur Edge, mais il prend en charge la mise en place de l’interface externe du service Edge d’accès, du service Edge de conférence Web et du service Edge A/V derrière un routeur ou un pare Plusieurs serveurs Edge derrière un programme d’équilibrage de la charge matérielle ne peuvent pas utiliser le protocole NAT. Si plusieurs serveurs Edge utilisent la traduction d’adresses réseau sur leurs interfaces externes, l’équilibrage de charge DNS (Domain Name System) est requis. À son tour, l’utilisation de l’équilibrage de charge DNS vous permet de réduire le nombre d’adresses IP publiques par serveur Edge dans un pool de serveurs Edge. Pour plus d’informations, consultez la rubrique[planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

<div>


> [!NOTE]  
> Si vous vous fédérer avec des entreprises qui ont un déploiement de Microsoft Office Communications Server 2007 et que vous devez utiliser l’audio/vidéo entre votre entreprise et l’entreprise fédérée, les exigences de port seront celles de l’ancienne version des serveurs Edge déployés. Par exemple, les plages de ports requises pour ces anciennes versions doivent être ouvertes pour les deux entreprises jusqu’à ce que le partenaire fédéré mette à niveau ses serveurs Edge vers Lync Server 2013. Les exigences relatives aux ports peuvent alors être réévaluées et réduites, conformément à la nouvelle configuration.



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>Certificats simplifiés pour les serveurs Edge

L’Assistant Déploiement peut remplir automatiquement les noms du sujet et les autres noms du sujet, réduisant le risque d’inclusion d’entrées inutiles et éventuellement non sécurisées.

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Cycle de vie de développement de la sécurité informatique de confiance (SDL)

Lync Server 2013 est conçu et développé conformément au cycle de vie de développement de la sécurité Microsoft Trustworthy Computing (SDL), qui est décrit à l’adresse <https://go.microsoft.com/fwlink/?linkid=68761> .

  - **Fiabilité de la conception**     La première étape de la création d’un système de communications unifiées plus sécurisé consistait à concevoir des modèles de menaces et tester chaque fonctionnalité à mesure qu’elle a été conçue. De plus, Microsoft effectue des tests en dehors du comportement conçu afin de trouver des failles de sécurité résultant d’un comportement inattendu du produit. Plusieurs améliorations liées à la sécurité ont été intégrées dans le processus et les pratiques de codage. Au moment de la création, des outils détectent les dépassements de mémoire tampon et d’autres risques de sécurité potentiels avant l’archivage du code dans le produit final. Bien entendu, il est impossible de concevoir un produit capable de contrer toutes les menaces de sécurité encore inconnues. Aucun système ne saurait garantir une sécurité à toute épreuve. Toutefois, étant donné que le développement de produits a adopté des principes de conception sécurisée dès le départ, Lync Server 2013 incorpore des technologies de sécurité standard en tant que partie fondamentale de son architecture.

  - **Fiable par défaut**     Par défaut, les communications réseau dans Lync Server 2013 sont chiffrées. Étant donné que tous les serveurs utilisent des certificats et l’authentification Kerberos, TLS, Secure Real-Time Transport Protocol (SRTP) et d’autres techniques de chiffrement standard, notamment le chiffrement AES (Advanced Encryption Standard) 128 bits, pratiquement toutes les données Lync Server sont protégées sur le réseau. De plus, le contrôle d’accès basé sur les rôles permet de déployer des serveurs exécutant Lync Server 2013 de sorte que chaque rôle serveur n’exécute que les services, et ne dispose que des autorisations liées à ces services, qui sont appropriées pour le rôle serveur.

  - **Fiabilité par déploiement**     Toute la documentation Lync Server 2013 comprend les meilleures pratiques et les recommandations pour vous aider à déterminer et à configurer les niveaux de sécurité optimaux pour votre déploiement et à évaluer les risques de sécurité liés à l’activation d’options autres que celles par défaut.

</div>

</div>

<span> </span>

</div>

</div>

</div>

