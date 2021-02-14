---
title: Routage direct via le système téléphonique
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Protocoles de routage direct
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835024"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Routage direct - Définitions et normes de mise en service desfc

Cet article décrit la façon dont le routage direct de Microsoft Phone System implémente les protocoles standard RFC. Cet article est destiné aux administrateurs vocaux qui sont responsables de la configuration de la connexion entre le contrôleur de session border controller (SBC) local et le service proxy SIP (Session Initiation Protocol).

Les interfaces SBC du client avec les composants suivants dans le composant principal de Microsoft Teams : 

- **Proxy SIP pour** le signalisation. Il s’agit du composant Internet du routage direct qui gère les connexions SIP (TLS) entre les SBCs et le routage direct.

- **Processeurs multimédias pour** le média. Il s’agit du composant Internet du routage direct qui gère le trafic de médias. Ce composant utilise les protocoles SRTP et SRTCP.


Pour plus d’informations sur le routage direct, voir [Routage direct du](direct-routing-landing-page.md)système téléphonique.

Pour plus d’informations sur la façon dont le routage direct implémente le protocole SIP, voir [Routage direct - Protocole SIP.](direct-routing-protocols-sip.md)

## <a name="rfc-standards"></a>Normes de RFC

Le routage direct est conforme aux normes de mise en conformité avec les normes de mise en route (RFC).  Le SBC connecté au routage direct doit également respecter les appels d’offre suivants (ou leurs successeurs). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Normes applicables aux appareils qui supportent le mode de contournement non multimédia 

Les normes suivantes s’appliquent aux appareils qui ne supportent que le mode de contournement non multimédia :

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocole d’initiation de session
- [RFC 3325.](https://www.ietf.org/rfc/rfc3325) Extension privée au protocole d’initiation de session pour l’identité identitaire au sein de réseaux de confiance-sections sur la gestion de l’en-tête Identité P-1. Le routage direct envoie une identité de personne avec ID de confidentialité. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Extension du protocole SIP (Session Initiation Protocol) pour les informations d’historique requises. Voir aussi : Description du protocole SIP de routage pour plus d’informations.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Protocole d’initiation de session Referred-By mécanisme d’initiation
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) En-tête « Remplace » l’en-tête SIP (Session Initiation Protocol) 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Utilisation du modèle d’offre/answer protocol (SIP) par le protocole SIP (Session Initiation Protocol).
  Consultez la section « Écarts par rapport à la mise en sureance de la mise en sureance de pc ».
- [RFC 3711](https://tools.ietf.org/html/rfc3711) et [RFC 4771.](https://tools.ietf.org/html/rfc4771) Protégez le trafic RTP à l’aide du SRTP. Le SBC doit être en mesure d’établir des clés à l’aide de SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Offre/clarifications de réponse au protocole SDP (Session Description Protocol) pour le multiplexage RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Normes applicables aux appareils qui supportent le mode de dérivation média

En plus des normes répertoriées comme applicables au mode sans contournement, les normes suivantes sont utilisées pour le mode de dérivation média :

- [RFC 5245 Connectivité interactive (ICE) pour la dérivation média.](https://tools.ietf.org/html/rfc5245)  Le SBC doit prendre en charge les états suivants :
  - ICE Lite - Les clients Teams sont des clients ICE complets
  - [Redémarrages DE LA GLACE.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1) En savoir plus sur le cas d’utilisation des redémarrages ICE et les exemples dans ice Restart : Appel de dérivation média transféré vers un point de terminaison qui ne prend pas en charge la dérivation média   
- [Contrôle d’appel DUP (RFC RFC RFC 5589 Session Initiation Protocol) – Transfert.](https://tools.ietf.org/html/rfc5589) 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP),](https://tools.ietf.org/html/rfc3960)voir les sections 3.1, Forking et 3.2, Ringing Tone Generation 
- [Utilitaires traversaux de session RFC 5389 pour NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN) : extensions de relais aux utilitaires traversaux de session pour NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Normes applicables à la prise en charge de la transmission des informations d’emplacement aux fournisseurs E911

- [RFC 6442, communication d’emplacement pour le protocole d’initiation à la session](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Écarts par rapport aux CTXT

Le tableau suivant répertorie les sections des RFC dans lesquelles l’implémentation du SIP ou de la pile multimédia par Microsoft est à partir de la norme :

| RFC et sections | Description | Écart |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, section 5.3 Hold and Resume of Media](https://tools.ietf.org/html/rfc6337#section-5.3) | La fonction RFC permet d’utiliser « a=inactive », « a=sendonly », a=recvonly » pour mettre un appel en attente. |Le proxy SIP prend uniquement en charge « a=inactive » et ne comprend pas si le SBC envoie « a=sendonly » ou « a=recvonly ».
| [RFC 6337, section 5.4 « Comportement lors de la réception de SDP avec c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | La mise à jour [RFC3264](https://tools.ietf.org/html/rfc3264) exige qu’un agent soit capable de recevoir le protocole SDP avec une adresse de connexion 0.0.0.0, dans ce cas, cela signifie que ni le RTP ni le RTCP ne doivent être envoyés à l’homologue. | Le proxy SIP ne prend pas en charge cette option. |

## <a name="operational-modes"></a>Modes opérationnels

Il existe deux modes opérationnels pour le routage direct :

- **Sans contournement multimédia** dans lequel tout le trafic RTP circule entre le client Teams, les processeurs de média et le SBC.  

- **Avec la dérivation** média dans laquelle tous les médias RTP circulent entre les points de terminaison Teams et le SBC. 

Notez que le trafic SIP est toujours flux via le proxy SIP.   
