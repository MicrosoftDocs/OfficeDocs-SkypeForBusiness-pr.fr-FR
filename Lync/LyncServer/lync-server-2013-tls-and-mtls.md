---
title: 'Lync Server 2013 : TLS et MTLS'
description: 'Lync Server 2013 : TLS et MTLS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ccee47e635435dd5f0d5eae03711c0cd5e517b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541790"
---
# <a name="tls-and-mtls-for-lync-server-2013"></a>TLS et MTLS pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Les protocoles TLS (Transport Layer Security) et MTLS (Mutual Transport Layer Security) fournissent des communications chiffrées et une authentification de point de terminaison sur Internet. Microsoft Lync Server 2013 utilise ces deux protocoles pour créer le réseau des serveurs approuvés et garantir que toutes les communications sur ce réseau sont chiffrées. Toutes les communications SIP entre les serveurs se produisent via MTLS. Les communications SIP de client à serveur ont lieu sur TLS.

TLS permet aux utilisateurs, via leur logiciel client, d’authentifier les serveurs Lync Server 2013 auxquels ils se connectent. Sur une connexion TLS, le client demande un certificat valide à partir du serveur. Pour être valide, le certificat doit avoir été émis par une autorité de certification qui est également approuvée par le client et le nom DNS du serveur doit correspondre au nom DNS du certificat. Si le certificat est valide, le client utilise la clé publique dans le certificat pour chiffrer les clés de chiffrement symétriques à utiliser pour la communication, de sorte que seul le propriétaire d’origine du certificat peut utiliser sa clé privée pour déchiffrer le contenu de la communication. La connexion obtenue est approuvée et, à partir de ce point, elle n’est pas contestée par d’autres serveurs ou clients approuvés. Dans ce contexte, le protocole SSL (Secure Sockets Layer) tel qu’il est utilisé avec les services Web peut être associé à TLS.

Les connexions de serveur à serveur s’appuient sur MTLS pour l’authentification mutuelle. Sur une connexion MTLS, le serveur à l’origine d’un message et le serveur qui le reçoit reçoivent des certificats d’une autorité de certification mutuellement approuvée. Les certificats prouvent l’identité de chaque serveur à l’autre. Dans les déploiements Lync Server 2013, les certificats émis par l’autorité de certification d’entreprise qui se trouvent pendant leur période de validité et qui ne sont pas révoqués par l’autorité de certification émettrice sont automatiquement considérés comme valides par tous les clients et serveurs internes car tous les membres d’un domaine Active Directory approuvent l’autorité de certification d’entreprise dans ce domaine. Dans les scénarios fédérés, l’autorité de certification émettrice doit être approuvée par les deux partenaires fédérés. Chaque partenaire peut utiliser une autorité de certification différente, si cela est souhaité, tant que cette autorité de certification est également approuvée par l’autre partenaire. Cette approbation est plus facile à accomplir par les serveurs Edge ayant le certificat d’autorité de certification racine du partenaire dans leurs autorités de certification racines de confiance, ou à l’aide d’une autorité de certification tierce approuvée par les deux parties.

TLS et MTLS permettent d’éviter les attaques par écoute clandestine et les attaques de l’intercepteur. Dans une attaque de type « Man-in-the-Middle », l’agresseur redirige les communications entre deux entités réseau via l’ordinateur de l’attaquant, sans que l’une des parties n’ait connaissance. La spécification TLS et Lync Server 2013 des serveurs approuvés (uniquement ceux qui sont spécifiés dans le générateur de topologie) atténue le risque d’une attaque de l’intercepteur en partie sur la couche d’application en utilisant le chiffrement de bout en bout coordonné à l’aide de la cryptographie à clé publique entre les deux points de terminaison, un attaquant doit disposer d’un certificat valide et approuvé avec la clé privée correspondante et être envoyé au nom du service auquel le client communique pour déchiffrer la communication. Toutefois, vous devez finalement suivre les meilleures pratiques en matière de sécurité avec votre infrastructure réseau (dans ce cas, DNS d’entreprise). Lync Server 2013 suppose que le serveur DNS est approuvé de la même manière que les contrôleurs de domaine et les catalogues globaux, mais le DNS offre un niveau de protection contre les attaques de détournement DNS en empêchant le serveur d’un agresseur de répondre correctement à une demande au nom usurpé.

La figure suivante illustre de façon générale comment Lync Server 2013 utilise MTLS pour créer un réseau de serveurs approuvés.

**Connexions approuvées dans un réseau Lync Server**

![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

