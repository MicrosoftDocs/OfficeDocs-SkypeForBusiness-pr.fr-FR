---
title: 'Lync Server 2013 : infrastructure de sécurité pour Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a2b58d34c1ed1f899e0daac8c1bb0132b1a22d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a>Infrastructure de sécurité pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-08_

Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité de Microsoft Lync Server 2013. Il est essentiel de comprendre la façon dont ces éléments collaborent pour prendre des décisions éclairées sur la sécurisation de votre déploiement de Lync Server 2013 particulier.

Ces éléments sont les suivants :

  - Les services de domaine Active Directory (AD DS) fournissent un référentiel principal approuvé unique pour les comptes d’utilisateurs et les ressources réseau.

  - RBAC (Contrôle d’accès basé sur un rôle) vous permet de déléguer les tâches d’administration tout en maintenant des normes élevées en matière de sécurité.

  - L’infrastructure à clé publique (PKI, Public Key Infrastructure) utilise des certificats émis par des autorités de certification approuvées afin d’authentifier les serveurs et de garantir l’intégrité des données.

  - Le protocole de transport TLS (Transport Layer Security), HTTPS sur SSL (HTTPS) et MTLS (Mutual TLS) permettent l’authentification des points de terminaison et le chiffrement des messages instantanés. Les flux multimédias point à point sont chiffrés à l’aide du protocole SRTP (protocole de transport sécurisé en temps réel).

  - Protocoles standard d’authentification des utilisateurs, le cas échéant.

  - Windows PowerShell fournit des fonctionnalités de sécurité qui sont activées par défaut, de sorte que les utilisateurs ne peuvent pas facilement exécuter des scripts.

Ces éléments de sécurité fondamentaux collaborent pour définir des utilisateurs, des serveurs, des connexions et des opérations de confiance pour garantir une base sécurisée pour Lync Server 2013.

<div>

## <a name="in-this-section"></a>Dans cette section

Les rubriques de cette section expliquent comment chacun de ces éléments fondamentaux fonctionne pour renforcer la sécurité de votre infrastructure serveur Lync.

  - [Services de domaine Active Directory pour Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Contrôle d’accès basé sur les rôles (RBAC) pour Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

  - [Infrastructure à clé publique pour Lync Server 2013](lync-server-2013-public-key-infrastructure.md)

  - [TLS et MTLS pour Lync Server 2013](lync-server-2013-tls-and-mtls.md)

  - [Chiffrement pour Lync Server 2013](lync-server-2013-encryption.md)

  - [Authentification utilisateur et client pour Lync Server 2013](lync-server-2013-user-and-client-authentication.md)

  - [Outils de gestion de Windows PowerShell et Lync Server 2013](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

