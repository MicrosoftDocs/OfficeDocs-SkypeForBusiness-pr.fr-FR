---
title: TLS et MTLS pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Les protocoles de transport TLS (Transport Layer Security) et MTLS (Mutual TLS) fournissent des communications chiffrées et une authentification du point de terminaison sur Internet. Skype entreprise Server utilise ces deux protocoles pour créer le réseau des serveurs de confiance et garantir le chiffrement de toutes les communications sur ce réseau. Toutes les communications SIP entre les serveurs interviennent sur MTLS. Les communications SIP du client au serveur interviennent sur TLS.
ms.openlocfilehash: fe8619dd499388472612c67ddf1801a027ed1e5d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296846"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS et MTLS pour Skype entreprise Server
 
Les protocoles de transport TLS (Transport Layer Security) et MTLS (Mutual TLS) fournissent des communications chiffrées et une authentification du point de terminaison sur Internet. Skype entreprise Server utilise ces deux protocoles pour créer le réseau des serveurs de confiance et garantir le chiffrement de toutes les communications sur ce réseau. Toutes les communications SIP entre les serveurs interviennent sur MTLS. Les communications SIP du client au serveur interviennent sur TLS.
  
Le protocole TLS permet aux utilisateurs, par le biais de leur logiciel client, d’authentifier les serveurs Skype entreprise Server auxquels ils se connectent. Sur une connexion TLS, le client demande un certificat valide du serveur. Pour être valide, le certificat doit avoir été émis par une autorité de certification qui est également approuvée par le client et le nom DNS du serveur doit correspondre au nom DNS dans le certificat. Si le certificat est valide, le client utilise la clé publique du certificat pour chiffrer les clés de chiffrement symétriques à utiliser pour la communication, de sorte que seul le propriétaire d’origine du certificat peut utiliser sa clé privée pour déchiffrer le contenu de la communication. La connexion résultante est approuvée et à partir de ce point n’est pas contestée par d’autres serveurs ou clients approuvés. Dans ce contexte, le protocole SSL (Secure Sockets Layer) utilisé avec les services Web peut être associé au protocole TLS.
  
Les connexions serveur à serveur s’appuient sur MTLS pour l’authentification mutuelle. Sur une connexion MTLS, le serveur à l’origine d’un message et le serveur le recevant échangent des certificats à partir d’une autorité de certification mutuellement approuvée. Les certificats prouvent l’identité d’un serveur à un autre. Dans les déploiements de Skype entreprise Server, les certificats émis par une autorité de certification d’entreprise qui sont au cours de leur période de validité et qui ne sont pas révoqués par l’autorité de certification sont automatiquement considérés comme valides par tous les clients et serveurs internes, car tous les membres d’un compte actif Domain Directory-approbation de l’autorité de certification de l’entreprise dans ce domaine. Dans les scénarios fédérés, l’autorité de certification émettrice doit être approuvée par les deux partenaires fédérés. Chaque partenaire peut utiliser une autorité différente s’il le souhaite, tant que cette autorité est également approuvée par l’autre partenaire. Ce type d’approbation est surtout accompli par les serveurs de périphérie possédant le certificat d’autorité de certification racine du partenaire dans leurs autorités de certification racines de confiance, ou à l’aide d’une autorité de certification tierce digne de confiance par les deux parties.
  
TLS et MTLS permettent d’empêcher les attaques par écoute et les attaques d’intercepteur. Dans le cadre d’une attaque par le biais du milieu, l’attaquant redirige les communications entre deux entités réseau via l’ordinateur de l’agresseur sans avoir connaissance de l’une des parties. La spécification de TLS et de Skype entreprise Server sur les serveurs de confiance (uniquement celles spécifiées dans le générateur de topologie) atténue le risque d’une attaque intermédiaire partielle sur la couche d’application en utilisant le chiffrement de bout en bout coordonné à l’aide de la clé publique. le chiffrement entre les deux points de terminaison et un attaquant doivent disposer d’un certificat valide et approuvé avec la clé privée correspondante et émis au nom du service auquel le client communique pour déchiffrer la communication. Enfin, vous devez toutefois respecter les meilleures pratiques de sécurité avec votre infrastructure réseau (dans ce cas, DNS d’entreprise). Skype entreprise Server suppose que le serveur DNS est digne de confiance de la même façon que les contrôleurs de domaine et les catalogues globaux sont approuvés, mais le DNS offre un niveau de protection contre les attaques de détournement de DNS en empêchant un serveur malveillant réussite d’une demande de nom usurpé.
  

