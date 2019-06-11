---
title: 'Lync Server 2013: TLS et MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 066612f08c61ad1df342b4f2dd9b61ff5a5cc286
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a>TLS et MTLS pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-07_

Les protocoles de transport TLS (Transport Layer Security) et MTLS (Mutual TLS) fournissent des communications chiffrées et une authentification du point de terminaison sur Internet. Microsoft Lync Server 2013 utilise ces deux protocoles pour créer le réseau des serveurs de confiance et garantir que toutes les communications réseau sont chiffrées. Toutes les communications SIP entre les serveurs interviennent sur MTLS. Les communications SIP du client au serveur interviennent sur TLS.

TLS permet aux utilisateurs, par le biais de leur logiciel client, d’authentifier les serveurs Lync Server 2013 auxquels ils se connectent. Sur une connexion TLS, le client demande un certificat valide du serveur. Pour être valide, le certificat doit avoir été émis par une autorité de certification qui est également approuvée par le client et le nom DNS du serveur doit correspondre au nom DNS dans le certificat. Si le certificat est valide, le client utilise la clé publique du certificat pour chiffrer les clés de chiffrement symétriques à utiliser pour la communication, de sorte que seul le propriétaire d’origine du certificat peut utiliser sa clé privée pour déchiffrer le contenu de la communication. La connexion résultante est approuvée et à partir de ce point n’est pas contestée par d’autres serveurs ou clients approuvés. Dans ce contexte, le protocole SSL (Secure Sockets Layer) utilisé avec les services Web peut être associé au protocole TLS.

Les connexions serveur à serveur s’appuient sur MTLS pour l’authentification mutuelle. Sur une connexion MTLS, le serveur à l’origine d’un message et le serveur le recevant échangent des certificats à partir d’une autorité de certification mutuellement approuvée. Les certificats prouvent l’identité d’un serveur à un autre. Dans les déploiements de Lync Server 2013, les certificats émis par une autorité de certification d’entreprise qui se trouvent au cours de leur période de validité et ne sont pas révoqués par l’autorité de certification émettrice sont automatiquement considérés comme valides par tous les clients et serveurs internes dans la mesure où tous les membres d’un domaine Active Directory Faites confiance à l’autorité de certification d’entreprise dans ce domaine. Dans les scénarios fédérés, l’autorité de certification émettrice doit être approuvée par les deux partenaires fédérés. Chaque partenaire peut utiliser une autorité différente s’il le souhaite, tant que cette autorité est également approuvée par l’autre partenaire. Cette approbation est plus facilement obtenue par les serveurs Edge qui disposent d’un certificat de l’autorité de certification racine du partenaire parmi leurs autorités de certification racines de confiance, ou bien en utilisant une autorité tierce qui est approuvée par les deux parties.

TLS et MTLS permettent d’empêcher les attaques par écoute et les attaques d’intercepteur. Dans le cas d’une attaque d’intercepteur, l’attaquant réachemine les communications entre deux entités de réseau via l’ordinateur de l’attaquant sans que l’autre partie n’en ait connaissance. La spécification de protocoles TLS et Lync Server 2013 des serveurs de confiance (uniquement celles spécifiées dans le générateur de topologie) atténue le risque d’une attaque intermédiaire partielle sur la couche d’application en utilisant le chiffrement de bout en bout coordonné à l’aide du chiffrement à clé publique. entre les deux points de terminaison, un attaquant doit disposer d’un certificat valide et approuvé avec la clé privée correspondante et est délivré au nom du service sur lequel le client communique pour déchiffrer la communication. Enfin, vous devez toutefois respecter les meilleures pratiques de sécurité avec votre infrastructure réseau (dans ce cas, DNS d’entreprise). Lync Server 2013 suppose que le serveur DNS est digne de confiance de la même façon que les contrôleurs de domaine et les catalogues globaux sont approuvés, mais le service DNS fournit un niveau de protection contre les attaques de détournement de DNS en empêchant le serveur d’un attaquant de répondre Demandez-lui le nom usurpé.

La figure suivante montre à un niveau élevé la façon dont Lync Server 2013 utilise MTLS pour créer un réseau de serveurs approuvés.

**Connexions approuvées dans un réseau Lync Server**

![437749da-C372-4f0d-AC72-ccfd5191696b] (images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-C372-4f0d-AC72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

