---
title: TLS et MTLS pour Lync Server 2013
TOCTitle: TLS et MTLS pour Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59679143
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# TLS et MTLS pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-07_

Les protocoles de transport TLS (Transport Layer Security) et MTLS (Mutual TLS) fournissent des communications chiffrées et une authentification du point de terminaison sur Internet. Microsoft Lync Server 2013 utilise ces deux protocoles pour créer le réseau de serveurs approuvés et pour garantir que toutes les communications sur ce réseau sont chiffrées. Toutes les communications SIP entre les serveurs interviennent sur MTLS. Les communications SIP du client au serveur interviennent sur TLS.

TLS permet aux utilisateurs, via leur logiciel client, d’authentifier les serveurs Lync Server 2013 auxquels ils se connectent. Sur une connexion TLS, le client demande un certificat valide au serveur. Pour être valide, le certificat doit avoir été émis par une autorité de certification également approuvée par le client et le nom DNS du serveur doit correspondre au nom DNS sur le certificat. Si le certificat est valide, le client utilise la clé publique dans le certificat pour chiffrer les clés de chiffrement symétriques à utiliser pour la communication. Par conséquent, seul le propriétaire d’origine du certificat peut utiliser sa clé privée pour déchiffrer le contenu de la communication. La connexion résultante est approuvée et, à partir de là, n’est pas remise en cause par d’autres serveurs ou clients approuvés. Dans ce contexte, le protocole SSL (Secure Sockets Layer) tel qu’utilisé avec les services Web peut être associé comme étant basé sur TLS.

Les connexions serveur à serveur s’appuient sur MTLS pour l’authentification mutuelle. Sur une connexion MTLS, le serveur à l’origine d’un message et le serveur le recevant échangent des certificats à partir d’une autorité de certification mutuellement approuvée. Les certificats prouvent l’identité d’un serveur à un autre. Dans les déploiements Lync Server 2013, les certificats émis par l’autorité de certification d’entreprise qui se trouvent dans leur période de validité et qui ne sont pas révoqués par l’autorité de certification émettrice sont automatiquement considérés comme valides par tous les clients et serveurs internes car tous les membres d’un domaine Active Directory approuvent l’autorité de certification d’entreprise dans ce domaine. Dans les scénarios fédérés, l’autorité de certification émettrice doit être approuvée par les deux partenaires fédérés. Chaque partenaire peut utiliser une autorité différente s’il le souhaite, tant que cette autorité est également approuvée par l’autre partenaire. Cette approbation est plus facilement obtenue par les serveurs Edge qui disposent d’un certificat de l’autorité de certification racine du partenaire parmi leurs autorités de certification racines de confiance, ou bien en utilisant une autorité tierce qui est approuvée par les deux parties.

TLS et MTLS permettent d’empêcher les attaques par écoute et les attaques d’intercepteur. Dans le cas d’une attaque d’intercepteur, l’attaquant réachemine les communications entre deux entités de réseau via l’ordinateur de l’attaquant sans que l’autre partie n’en ait connaissance. TLS et la spécification Lync Server 2013 des serveurs approuvés (uniquement ceux spécifiés dans Générateur de topologie) limitent partiellement le risque d’une attaque d’intercepteur sur la couche de l’application en utilisant un chiffrement de bout en bout coordonné à l’aide du chiffrement de clé publique entre les deux points de terminaison ; un attaquant devrait disposer d’un certificat valide et approuvé avec la clé privée correspondante et émise au nom du service sur lequel le client communique pour déchiffrer la communication. Enfin, vous devez toutefois respecter les meilleures pratiques de sécurité avec votre infrastructure réseau (dans ce cas, DNS d’entreprise). Lync Server 2013 suppose que le serveur DNS est approuvé de la même manière que les contrôleurs de domaine et les catalogues globaux, mais DNS offre un niveau de sécurité contre les attaques de détournement de DNS en empêchant le serveur d’un attaquant de répondre à une demande du nom usurpé.

Le schéma suivant montre à un niveau élevé comment Lync Server 2013 utilise MTLS pour créer un réseau de serveurs approuvés.

**Connexions approuvées dans un réseau Lync Server**

![Utilisation de MTLS](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "Utilisation de MTLS")

