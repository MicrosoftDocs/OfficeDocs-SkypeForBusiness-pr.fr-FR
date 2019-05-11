---
title: TLS et MTLS pour Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Les protocoles de transport TLS (Transport Layer Security) et MTLS (Mutual TLS) fournissent des communications chiffrées et une authentification du point de terminaison sur Internet. Skype pour Business Server utilise ces deux protocoles pour créer le réseau de serveurs approuvés et pour s’assurer que toutes les communications sur ce réseau sont chiffrées. Toutes les communications SIP entre les serveurs interviennent sur MTLS. Les communications SIP du client au serveur interviennent sur TLS.
ms.openlocfilehash: 995eb0b29e07d9224b2c7fa989eb96154267ac8f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929118"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS et MTLS pour Skype pour Business Server
 
Les protocoles de transport TLS (Transport Layer Security) et MTLS (Mutual TLS) fournissent des communications chiffrées et une authentification du point de terminaison sur Internet. Skype pour Business Server utilise ces deux protocoles pour créer le réseau de serveurs approuvés et pour s’assurer que toutes les communications sur ce réseau sont chiffrées. Toutes les communications SIP entre les serveurs interviennent sur MTLS. Les communications SIP du client au serveur interviennent sur TLS.
  
TLS permet aux utilisateurs, par le biais de leur logiciel client authentifier le Skype pour les serveurs Business Server auxquels ils se connectent. Sur une connexion TLS, le client demande un certificat valide du serveur. Pour être valide, le certificat doit avoir été émis par une autorité de certification qui est également approuvée par le client et le nom DNS du serveur doit correspondre au nom DNS dans le certificat. Si le certificat est valide, le client utilise la clé publique du certificat pour chiffrer les clés de chiffrement symétriques à utiliser pour la communication, de sorte que seul le propriétaire d’origine du certificat peut utiliser sa clé privée pour déchiffrer le contenu de la communication. La connexion résultante est approuvée et à partir de ce point n’est pas contestée par d’autres serveurs ou clients approuvés. Dans ce contexte, le protocole SSL (Secure Sockets Layer) utilisé avec les services Web peut être associé au protocole TLS.
  
Les connexions serveur à serveur s’appuient sur MTLS pour l’authentification mutuelle. Sur une connexion MTLS, le serveur à l’origine d’un message et le serveur le recevant échangent des certificats à partir d’une autorité de certification mutuellement approuvée. Les certificats prouvent l’identité d’un serveur à un autre. Dans Skype pour les déploiements de serveur d’entreprise, les certificats émis par l’autorité de certification d’entreprise pendant leur validité période et pas révoquée par l’autorité de certification émettrice sont automatiquement considérés comme valides par tous les serveurs et clients internes, car tous les membres de l’actif Domaine Directory approuver l’autorité de certification d’entreprise dans ce domaine. Dans les scénarios fédérés, l’autorité de certification émettrice doit être approuvée par les deux partenaires fédérés. Chaque partenaire peut utiliser une autorité différente s’il le souhaite, tant que cette autorité est également approuvée par l’autre partenaire. Cette relation d’approbation s’effectue plus facilement par les serveurs de périphérie ayant le certificat d’autorité de certification racine du partenaire dans leurs autorités de certification racines, ou par l’utilisation d’une autorité de certification tierce approuvée par les deux parties.
  
TLS et MTLS permettent d’empêcher les attaques par écoute et les attaques d’intercepteur. Dans une attaque man-in-the-middle, l’intrus redirige les communications entre deux entités du réseau par le biais d’ordinateur son propre l’insu des deux participants. TLS et Skype pour spécifier des serveurs approuvés (uniquement à ceux spécifiés dans le Générateur de topologie) Business Server réduire le risque d’une attaque man-in-the-partiellement sur la couche d’application à l’aide de coordonnées à l’aide de la clé publique de chiffrement de bout en bout chiffrement entre les deux points de terminaison et une personne malveillante aurait besoin d’un certificat valid et approuvé avec la clé privée correspondante et émis pour le nom du service pour lequel le client communique pour déchiffrer la communication. Enfin, vous devez toutefois respecter les meilleures pratiques de sécurité avec votre infrastructure réseau (dans ce cas, DNS d’entreprise). Skype pour Business Server part du principe que le serveur DNS est approuvé de la même manière que les contrôleurs de domaine et les catalogues globaux sont approuvés, mais DNS ne fournit pas un niveau de protection contre les attaques de détournement DNS en empêchant un serveur de répondre correctement à une demande pour le nom usurpé.
  

