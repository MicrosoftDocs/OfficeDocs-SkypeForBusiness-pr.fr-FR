---
title: TLS et MTLS pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Les protocoles TLS (Transport Layer Security) et MTLS (Mutual Transport Layer Security) fournissent des communications chiffrées et l’authentification de point de terminaison sur Internet. Skype Entreprise Server utilise ces deux protocoles pour créer le réseau de serveurs de confiance et pour s’assurer que toutes les communications sur ce réseau sont chiffrées. Toutes les communications SIP entre les serveurs se produisent sur MTLS. Les communications SIP du client au serveur se produisent sur TLS.
ms.openlocfilehash: 05dbde5907831867e6dfba7cf6f26b83e3e1c60b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744050"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS et MTLS pour Skype Entreprise Server
 
Les protocoles TLS (Transport Layer Security) et MTLS (Mutual Transport Layer Security) fournissent des communications chiffrées et l’authentification de point de terminaison sur Internet. Skype Entreprise Server utilise ces deux protocoles pour créer le réseau de serveurs de confiance et pour s’assurer que toutes les communications sur ce réseau sont chiffrées. Toutes les communications SIP entre les serveurs se produisent sur MTLS. Les communications SIP du client au serveur se produisent sur TLS.
  
TLS permet aux utilisateurs, via leur logiciel client, d’authentifier les Skype Entreprise Server serveurs avec lesquels ils se connectent. Sur une connexion TLS, le client demande un certificat valide au serveur. Pour être valide, le certificat doit avoir été émis par une ac qui est également approuvé par le client et le nom DNS du serveur doit correspondre au nom DNS sur le certificat. Si le certificat est valide, le client utilise la clé publique dans le certificat pour chiffrer les clés de chiffrement symétriques à utiliser pour la communication, afin que seul le propriétaire d’origine du certificat puisse utiliser sa clé privée pour déchiffrer le contenu de la communication. La connexion qui en résulte est fiable et, à partir de ce stade, elle n’est pas remise en question par d’autres serveurs ou clients de confiance. Dans ce contexte, SSL (Secure Sockets Layer) tel qu’utilisé avec les services Web peut être associé en tant que TLS.
  
Les connexions de serveur à serveur reposent sur MTLS pour l’authentification mutuelle. Sur une connexion MTLS, le serveur d’origine d’un message et le serveur qui le reçoit échangent des certificats à partir d’une ca mutuellement fiable. Les certificats prouvent l’identité de chaque serveur à l’autre. Dans les déploiements Skype Entreprise Server, les certificats émis par l’autorité de certification d’entreprise qui sont pendant leur période de validité et qui ne sont pas révoqués par l’autorité de certification émettrice sont automatiquement considérés comme valides par tous les clients et serveurs internes, car tous les membres d’un domaine Active Directory font confiance à l’autorité de certification Enterprise dans ce domaine. Dans les scénarios fédérés, l’ac émettrice doit être fiable par les deux partenaires fédérés. Chaque partenaire peut utiliser une autre ac, si vous le souhaitez, tant que cette ca est également fiable par l’autre partenaire. Cette relation d’autorisation s’accomplit le plus facilement grâce au fait que les serveurs Edge ont le certificat d’ac racine du partenaire dans leurs ca racines de confiance, ou par l’utilisation d’une ca tierce qui est fiable par les deux parties.
  
TLS et MTLS permettent d’éviter les attaques d’écoute et les attaques de l’intermédiaire. Dans le cadre d’une attaque de l’intermédiaire, l’attaquant redirige les communications entre deux entités réseau via l’ordinateur de l’attaquant à l’insu de l’une ou l’autre des parties. Les spécifications TLS et Skype Entreprise Server des serveurs de confiance (uniquement ceux spécifiés dans le Générateur de topologie) atténuent le risque d’une attaque de l’entre-deux en partie sur la couche d’application à l’aide d’un chiffrement de bout en bout coordonné à l’aide du chiffrement à clé publique entre les deux points de terminaison, et un attaquant doit avoir un certificat valide et approuvé avec la clé privée correspondante et émis au nom du service vers laquelle le client communique pour déchiffrer la communication. En fin de compte, toutefois, vous devez suivre les meilleures pratiques de sécurité avec votre infrastructure réseau (dans ce cas, le DNS d’entreprise). Skype Entreprise Server suppose que le serveur DNS est approuvé de la même manière que les contrôleurs de domaine et les catalogues globaux, mais le DNS offre un niveau de protection contre les attaques par piratage DNS en empêchant le serveur d’une personne malveillante de répondre correctement à une demande au nom usurpé.
  

