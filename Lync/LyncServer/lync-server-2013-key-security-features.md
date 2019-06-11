---
title: 'Lync Server 2013: principales fonctionnalités de sécurité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53a6d9e23442cb127f0f08849e18f1d63bae76d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a>Principales fonctionnalités de sécurité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-07-18_

Lync Server 2013 inclut plusieurs fonctionnalités de sécurité, notamment l’authentification de serveur à serveur, le contrôle d’accès basé sur un rôle et le stockage centralisé des données de configuration.

Cet article fournit une vue d’ensemble de haut niveau de la sécurité de Lync Server 2013.

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Principales fonctionnalités de sécurité dans Lync Server 2013

La sécurité est un sujet très large. La sécurité s’étend à toutes les fonctionnalités de Lync Server 2013 ainsi qu’aux bases de données, services et matériels qui constituent un écosystème Lync. Cet article présente certaines des fonctionnalités de Lync Server 2013 en particulier qui sont conçues pour la sécurité.

<div>

## <a name="planning-and-design-tools"></a>Outils de planification et de conception

Lync Server 2013 fournit deux outils pour faciliter la planification et la conception, et limiter les risques de configuration des composants serveur Lync.

  - L' **outil de planification topologique** automatise une grande partie du processus de conception topologique. Vous pouvez exporter les résultats de l’outil de planification au générateur de topologie, qui est l’outil requis pour installer chaque serveur exécutant Lync Server 2013.

  - **Le générateur de topologie** stocke toutes les informations de configuration dans le magasin central de gestion.

Pour plus d’informations sur ces outils, voir [planification de Lync Server 2013](lync-server-2013-planning.md).

</div>

<div>

## <a name="central-management-store"></a>Magasin central de gestion

Dans Lync Server 2013, les données de configuration relatives aux serveurs et services font partie du magasin central de gestion. Le centre de gestion central fournit un stockage puissant et schematized des données nécessaires pour définir, configurer, gérer, gérer, décrire et utiliser un déploiement de Lync Server. Il valide également les données afin de garantir la cohérence de la configuration. Toutes les modifications apportées aux données de configuration ont lieu dans le magasin central de gestion, ce qui élimine les problèmes de synchronisation.

Les copies en lecture seule des données sont répliquées sur tous les serveurs au sein de la topologie, y compris les serveurs Edge et les serveurs Survivable Branch Appliance. La réplication est gérée par un service exécuté par défaut dans le contexte du service réseau, ce qui limite les droits et autorisations à ceux d’un simple utilisateur sur l’ordinateur.

</div>

<div>

## <a name="server-to-server-authentication"></a>Authentification serveur à serveur

Dans Lync Server 2013, il est possible de configurer l’authentification entre les serveurs à l’aide du protocole d’autorisation Open (OAuth). Par exemple, vous pouvez configurer Lync Server 2013 pour s’authentifier auprès d’un serveur exécutant Exchange Server 2013. À l’aide du protocole OAuth, le serveur Lync et le serveur Exchange peuvent être approuvés. Cela permet d’intégrer les produits de façon transparente. Pour plus d’informations, reportez-vous à [gestion des applications d’authentification de serveur à serveur (OAuth) et de partenaire dans Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Interface de gestion Windows PowerShell et web

Lync Server 2013 fournit une interface de gestion puissante, basée sur l’interface de ligne de commande Windows PowerShell. Il inclut des cmdlets de gestion de la sécurité et les fonctionnalités de sécurité de Windows PowerShell sont activées par défaut, de sorte que les utilisateurs ne peuvent pas facilement exécuter des scripts. Cela signifie que les logiciels par défaut sont configurés pour renforcer la sécurité et réduire les possibilités d’attaque. Pour plus d’informations sur la prise en charge de Windows PowerShell Management dans Lync Server 2013, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="role-based-access-control-rbac"></a>Contrôle d’accès basé sur un rôle (RBAC)

Microsoft Lync Server 2013 fournit un contrôle d’accès basé sur les rôles (RBAC) pour vous permettre de déléguer des tâches administratives tout en préservant la sécurité des normes. You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require. Lync Server 2013 introduit la possibilité de créer un nouveau rôle et de modifier un rôle existant. Pour plus d’informations, reportez-vous à [planification du contrôle d’accès basé sur les rôles dans Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>Traduction d’adresses réseau (NAT)

Lync Server 2013 ne prend pas en charge l’utilisation de la traduction d’adresses réseau (NAT) sur l’interface interne du serveur Edge, mais il prend en charge le placement de l’interface externe du service Edge d’accès, du service Edge de conférence Web et du service Edge A/V derrière un routeur ou pare-feu qui exécute la traduction d’adresses réseau (NAT) pour les topologies de serveur de périphérie unique et à l’échelle. S’il y a plusieurs serveurs Edge utilisant un programme d’équilibrage de la charge matérielle, ils ne peuvent pas utiliser la traduction d’adresses réseau. Si plusieurs serveurs Edge utilisent la traduction d’adresses réseau sur leurs interfaces externes, l’équilibrage de la charge DNS (Domain Name System) est requise. L’utilisation de l’équilibrage de la charge DNS vous permet de réduire le nombre d’adresses IP publiques par serveur Edge dans un pool de serveurs Edge. Pour plus d’informations, reportez-vous à la[planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

<div>


> [!NOTE]  
> Si vous vous fédérez avec des entreprises qui ont un déploiement de Microsoft Office Communications Server 2007 et que vous devez utiliser l’audio et la vidéo entre votre entreprise et une entreprise fédérée, les ports utilisés seront ceux de l’ancienne version des serveurs Edge déployés. Par exemple, les plages de ports requises pour ces versions antérieures doivent être ouvertes pour les deux entreprises tant que le partenaire fédéré a mis à niveau ses serveurs Edge vers Lync Server 2013. Les exigences relatives aux ports peuvent alors être réévaluées et réduites, conformément à la nouvelle configuration.



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>Certificats simplifiés pour les serveurs Edge

L’Assistant Déploiement peut renseigner automatiquement les noms du sujet et les autres noms du sujet, et minimiser ainsi la possibilité d’inclure des entrées inutiles et éventuellement non sécurisées.

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Cycle de développement d’une sécurité informatique fiable

Lync Server 2013 est conçu et développé conformément au cycle de vie de développement de la sécurité Microsoft Trustworthy Computing (SDL), <http://go.microsoft.com/fwlink/?linkid=68761>qui est décrit à la section.

  - **Digne de confiance en concevant**   la première étape de la création d’un système de communication unifiée plus sécurisé consistait à concevoir des modèles de menaces et à tester chaque fonctionnalité au moment de la conception. De plus, Microsoft effectue des tests sur des comportements anormaux afin de détecter les failles de sécurité résultant d’un comportement inattendu du produit. Plusieurs améliorations liées à la sécurité ont été intégrées dans le processus et les pratiques de codage. Au moment de la création, des outils détectent les dépassements de mémoire tampon et d’autres risques de sécurité potentiels avant l’archivage du code dans le produit final. Bien entendu, il est impossible de concevoir un produit capable de contrer toutes les menaces de sécurité encore inconnues. Aucun système ne saurait garantir une sécurité à toute épreuve. Toutefois, étant donné que le développement de produits a adopté des principes de conception sécurisés depuis le début, Lync Server 2013 inclut les technologies de sécurité standard de l’industrie comme partie fondamentales de son architecture.

  - **Digne de confiance**par défaut, les communications réseau dans Lync Server 2013 sont chiffrées.    Dans la mesure où tous les serveurs utilisent des certificats et l’authentification Kerberos, TLS, Secure Real-Time Transport Protocol (SRTP) et d’autres techniques de cryptage standard de l’industrie, y compris le chiffrement AES (Advanced Encryption Standard) 128 bits, tout en Lync Les données du serveur sont protégées sur le réseau. De plus, le contrôle d’accès basé sur les rôles permet de déployer des serveurs exécutant Lync Server 2013 de sorte que chaque rôle de serveur exécute uniquement les services et que seules les autorisations associées à ces services soient appropriées pour le rôle serveur.

  - **Fiable par le déploiement**   toutes les informations de la documentation Lync Server 2013 incluent des pratiques recommandées et des recommandations pour vous aider à déterminer et à configurer les niveaux de sécurité optimaux pour votre déploiement et évaluer les risques liés à l’activation de la sécurité par défaut. Options.

</div>

</div>

<span> </span>

</div>

</div>

</div>

