---
title: Cadre de sécurité pour Lync Server 2013
TOCTitle: Cadre de sécurité pour Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59682864
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cadre de sécurité pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-08_

Cette section décrit les éléments fondamentaux du cadre de sécurité pour Microsoft Lync Server 2013. La compréhension du fonctionnement collectif de ces éléments est essentielle à la prise de décisions appropriées relativement à la sécurisation de votre déploiement particulier de Lync Server 2013.

Ces éléments sont les suivants :

  - services de domaine Active Directory (AD DS) fournit un référentiel principal approuvé unique pour les comptes d’utilisateur et les ressources réseau.

  - RBAC (Contrôle d’accès basé sur un rôle) vous permet de déléguer les tâches d’administration tout en maintenant des normes élevées en matière de sécurité.

  - L’infrastructure à clé publique (PKI, Public Key Infrastructure) utilise des certificats émis par des autorités de certification approuvées afin d’authentifier les serveurs et de garantir l’intégrité des données.

  - Le protocole de transport TLS (Transport Layer Security), HTTPS sur SSL (HTTPS) et MTLS (Mutual TLS) permettent l’authentification des points de terminaison et le chiffrement des messages instantanés. Les flux multimédias point à point sont chiffrés à l’aide du protocole SRTP (protocole de transport sécurisé en temps réel).

  - Protocoles standard d’authentification des utilisateurs, le cas échéant.

  - Windows PowerShell offre des fonctionnalités de sécurité activées par défaut, de sorte que les utilisateurs ne puissent pas exécuter des scripts facilement ou inconsciemment.

Ces éléments de sécurité fondamentaux fonctionnent conjointement pour définir les utilisateurs, serveurs, connexions et opérations fiables afin de garantir une base sûre pour Lync Server 2013.

## Dans cette section

Les rubriques de cette section décrivent comment chacun de ces éléments fondamentaux agit dans le but d’améliorer la sécurité de votre infrastructure Lync Server.

  - [Services de domaine Active Directory pour Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Contrôle d’accès basé sur un rôle (RBAC) pour Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

  - [Infrastructure à clé publique pour Lync Server 2013](lync-server-2013-public-key-infrastructure.md)

  - [TLS et MTLS pour Lync Server 2013](lync-server-2013-tls-and-mtls.md)

  - [Chiffrement pour Lync Server 2013](lync-server-2013-encryption.md)

  - [Authentification utilisateur et client pour Lync Server 2013](lync-server-2013-user-and-client-authentication.md)

  - [Outils de gestion de Windows PowerShell et Lync Server 2013](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

