---
title: TLS et MTLS pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/5/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Les protocoles de transport TLS (Transport Layer Security) et MTLS (Mutual TLS) fournissent des communications chiffrées et une authentification du point de terminaison sur Internet. Skype pour Business Server 2015 utilise ces deux protocoles pour créer le réseau de serveurs de confiance et pour s’assurer que toutes les communications sur ce réseau sont cryptées. Toutes les communications SIP entre les serveurs interviennent sur MTLS. Les communications SIP du client au serveur interviennent sur TLS.
ms.openlocfilehash: 1cc7554ab14e29fd85d2964d1323fccdfd4af604
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tls-and-mtls-for-skype-for-business-server-2015"></a>TLS et MTLS pour Skype Entreprise Server 2015
 
Les protocoles de transport TLS (Transport Layer Security) et MTLS (Mutual TLS) fournissent des communications chiffrées et une authentification du point de terminaison sur Internet. Skype pour Business Server 2015 utilise ces deux protocoles pour créer le réseau de serveurs de confiance et pour s’assurer que toutes les communications sur ce réseau sont cryptées. Toutes les communications SIP entre les serveurs interviennent sur MTLS. Les communications SIP du client au serveur interviennent sur TLS.
  
TLS permet aux utilisateurs, par l’intermédiaire de leur logiciel de client authentifier la Skype pour serveurs Business Server 2015 auquel ils se connectent. Sur une connexion TLS, le client demande un certificat valide à partir du serveur. Pour être valide, le certificat doit avoir été émis par une autorité de certification est également approuvée par le client et le nom DNS du serveur doit correspondre au nom DNS sur le certificat. Si le certificat est valide, le client utilise la clé publique dans le certificat pour crypter le chiffrement symétrique de clés à utiliser pour la communication, ainsi que le propriétaire d’origine du certificat peut utiliser sa clé privée pour décrypter le contenu de la communication. La connexion résultante est approuvée et à partir de ce point n’est pas contestée par d’autres clients ou serveurs de confiance. Dans ce contexte, la couche SSL (Secure Sockets) tel qu’utilisé avec les services Web peuvent être associés comme basée sur TLS.
  
Les connexions serveur à serveur s’appuient sur MTLS pour l’authentification mutuelle. Sur une connexion MTLS, le serveur à l’origine d’un message et le serveur le recevant échangent des certificats à partir d’une autorité de certification mutuellement approuvée. Les certificats prouvent l’identité d’un serveur à un autre. Dans Skype pour les déploiements d’entreprise serveur 2015, les certificats émis par l’autorité de certification d’entreprise qui sont pendant leur durée de validité période et non révoquée par l’autorité de certification émettrice sont automatiquement considérés comme valides par tous les serveurs et les clients internes, car tous les membres d’un actif Domaine de répertoire faire confiance à l’autorité de certification d’entreprise dans ce domaine. Dans les scénarios fédérés, l’autorité de certification émettrice doit être approuvée par les deux partenaires fédérés. Chaque partenaire peut utiliser une autorité différente s’il le souhaite, tant que cette autorité est également approuvée par l’autre partenaire. Cette approbation est facilement réalisable par les serveurs Edge ayant le certificat d’autorité de certification racine du partenaire dans leurs autorités de certification racines de confiance, ou par l’utilisation d’une autorité de certification tierce approuvée par les deux parties.
  
TLS et MTLS permettent d’empêcher les attaques par écoute et les attaques d’intercepteur. Dans une attaque man-in-the-middle, l’agresseur redirige les communications entre deux entités réseau par le biais de l’ordinateur pirate sans la connaissance de des parties. TLS et Skype pour la spécification de Business Server 2015 de serveurs de confiance (uniquement ceux spécifiés dans le Générateur de topologies) atténuer le risque d’une attaque d’intermédiaire manuel dans le partiellement sur la couche d’application en utilisant le cryptage de bout en bout de coordonnées à l’aide de la clé publique cryptographie entre deux points de terminaison et l’attaquant devra disposer d’un certificat valide et approuvé avec la clé privée correspondante et émis pour le nom du service pour lequel le client communique pour déchiffrer la communication. Enfin, vous devez toutefois respecter les meilleures pratiques de sécurité avec votre infrastructure réseau (dans ce cas, DNS d’entreprise). Skype pour Business Server 2015 suppose que le serveur DNS est approuvé de la même manière que les contrôleurs de domaine et les catalogues globaux sont approuvés, mais DNS fournit un niveau de protection contre les attaques de détournement DNS en empêchant le serveur de l’attaquant de répondre avec succès à une demande au nom usurpé.
  

