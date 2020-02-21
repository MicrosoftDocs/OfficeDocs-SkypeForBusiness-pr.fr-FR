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
ms.openlocfilehash: 7871d662d76f47685a58384804dfc6dee3b7b1d2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a>Infrastructure de sécurité pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-08_

Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité pour Microsoft Lync Server 2013. Il est essentiel de comprendre comment ces éléments interagissent pour prendre des décisions éclairées concernant la sécurisation de votre déploiement de Lync Server 2013 particulier.

Ces éléments sont les suivants :

  - Les services de domaine Active Directory offrent un référentiel centralisé, unique et fiable aux comptes d’utilisateurs et aux ressources réseau.

  - Le contrôle d’accès basé sur un rôle (RBAC) vous permet de déléguer des tâches administratives tout en conservant des normes de sécurité élevées.

  - L’infrastructure à clé publique (PKI) utilise des certificats émis par des autorités de certification approuvées pour authentifier les serveurs et garantir l’intégrité des données.

  - Les protocoles TLS (Transport Layer Security), HTTPS sur SSL (HTTPS) et Mutual TLS (MTLS) permettent l’authentification des systèmes d’extrémité et le chiffrement des communications par messagerie instantanée. Les flux audio, vidéo et de partage d’application point à point sont chiffrés à l’aide du protocole SRTP (Secure Real Time Transport Protocol).

  - Des protocoles standard sont utilisés pour l’authentification des utilisateurs, lorsque cela est possible.

  - Windows PowerShell propose des fonctionnalités de sécurité activées par défaut afin que les utilisateurs ne puissent pas exécuter des scripts facilement ou sans le savoir.

Ces éléments de sécurité fondamentaux fonctionnent ensemble pour définir des utilisateurs, des serveurs, des connexions et des opérations approuvés afin de garantir une base sécurisée pour Lync Server 2013.

<div>

## <a name="in-this-section"></a>Dans cette section

Les rubriques de cette section décrivent le fonctionnement de chacun de ces éléments fondamentaux afin d’améliorer la sécurité de votre infrastructure Lync Server.

  - [Services de domaine Active Directory pour Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Contrôle d’accès basé sur un rôle (RBAC) pour Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

  - [Infrastructure de clé publique pour Lync Server 2013](lync-server-2013-public-key-infrastructure.md)

  - [TLS et MTLS pour Lync Server 2013](lync-server-2013-tls-and-mtls.md)

  - [Chiffrement pour Lync Server 2013](lync-server-2013-encryption.md)

  - [Authentification utilisateur et client pour Lync Server 2013](lync-server-2013-user-and-client-authentication.md)

  - [Outils de gestion Windows PowerShell et Lync Server 2013](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

