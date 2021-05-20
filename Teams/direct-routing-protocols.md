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
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569202"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Routage direct - Définitions et normes RFC

Cet article décrit comment le Téléphone Microsoft système direct implémente les protocoles standard RFC. Cet article s’adresse aux administrateurs vocaux qui sont responsables de la configuration de la connexion entre le contrôleur des frontières de session (SBC) sur place et le service proxy du Protocole d’initiation de session (SIP).

Le client SBC interface avec les composants suivants dans le Microsoft Teams backend: 

- **Le proxy SIP** pour la signalisation. Il s’agit de la composante internet de Direct Routing qui gère les connexions SIP (TLS) entre les SBCs et le routage direct.

- **Les processeurs multimédias** pour les médias. Il s’agit de la composante internet de Direct Routing qui gère le trafic multimédia. Ce composant utilise les protocoles SRTP et SRTCP.


Pour plus d’informations sur le routage direct, [Système téléphonique le routage direct](direct-routing-landing-page.md).

Pour plus d’informations sur la façon dont Direct Routing implémente le protocole SIP, [voir Itinéraire direct - Protocole SIP](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>Normes RFC

Le routage direct est conforme aux normes RFC.  Le SBC connecté au routage direct doit également se conformer aux CRF suivants (ou à leurs successeurs). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Normes applicables aux appareils qui supporte le mode de contournement non médiatique 

Les normes suivantes s’appliquent aux appareils qui ne supporte que le mode de contournement non médiatique :

- [RFC 3261 SIP : Protocole d’initiation](https://tools.ietf.org/html/rfc3261)de session
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Extension privée du protocole d’initiation à la session pour l’identité affirmée au sein des réseaux de confiance -- Sections sur le traitement de l’en-tête P-Asserted-Identity. Le routage direct envoie p-asserted-identity avec des en-têtes privacy ID. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Une extension du Protocole d’initiation à la session (SIP) pour les informations historiques requises. Voir aussi : Routage de la description du protocole SIP pour plus d’informations.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Le Protocole d’initiation à la session Referred-By mécanisme
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Le Protocole d’initiation à la session (SIP) « remplace » l’en-tête 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Protocole d’initiation de session (SIP) Utilisation du modèle offre/réponse.
  Voir la section « Déviations par rapport au RFC ».
- [RFC 3711](https://tools.ietf.org/html/rfc3711) et [RFC 4771](https://tools.ietf.org/html/rfc4771). Protégez le trafic RTP à l’aide de SRTP. Le SBC doit être en mesure d’établir des clés à l’aide de SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Protocole de description de session (SDP) Offre/Clarifications de réponse pour le multiplexage RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Normes applicables aux appareils qui supporte le mode de contournement des médias

En plus des normes énumérées comme applicables au mode non-bypass, les normes suivantes sont utilisées pour le mode de contournement des médias :

- [RFC 5245 Interactive Connectivity Establishment (ICE) pour le contournement des médias](https://tools.ietf.org/html/rfc5245).  Le SBC doit prendre en charge les éléments suivants :
  - ICE Lite - les clients Teams clients sont des clients ICE complets
  - [ICE Redémarre](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). En savoir plus sur ICE redémarre l’utilisation de cas et d’exemples dans ICE Restart: Media bypass call transféré à un point final qui ne prend pas en charge le contournement des médias   
- [RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfert](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP),](https://tools.ietf.org/html/rfc3960)voir les sections 3.1, Forking, et 3.2, Ringing Tone Generation 
- [RFC 5389 Session Traversal Utilities pour NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN): Extensions relais à session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Normes applicables pour appuyer la transmission d’informations de localisation aux fournisseurs de L’E911

- [RFC 6442, Transport de localisation pour le protocole d’initiation à la session](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Déviations par rapport aux

Le tableau suivant énumère les sections du RFC(s) dans lesquelles la mise en œuvre par Microsoft du SIP ou de la pile multimédia s’écarte de la norme :

| RFC et sections | Description | déviation |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, section 5.3 Attente et curriculum vitae des médias](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC permet d’utiliser « a=inactif », « a=sendonly », a=recvonly » pour mettre un appel en attente. |Le proxy SIP ne prend en charge que « a=inactif » et ne comprend pas si le SBC envoie « a=sendonly » ou « a=recvonly ».
| [RFC 6337, section 5.4 « Comportement sur la réception du PDS avec c=0,0,0,0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264 exige](https://tools.ietf.org/html/rfc3264) qu’un agent soit capable de recevoir SDP avec une adresse de connexion de 0.0.0.0, auquel cas cela signifie que ni RTP ni RTCP ne doivent être envoyés au pair. | Le proxy SIP ne prend pas en charge cette option. |

## <a name="operational-modes"></a>Modes opérationnels

Il existe deux modes opérationnels pour le routage direct :

- **Sans contournement** médiatique dans lequel tout le trafic RTP circule entre Teams client, les processeurs multimédias et le SBC.  

- **Avec le contournement** des médias dans lequel tous les médias RTP circulent entre Teams points de terminaison et le SBC. 

Notez que le trafic SIP circule toujours via le proxy SIP. 

## <a name="dtmf"></a>Dtmf
Dans la bande DTMF n’est pas pris en charge par la pile de médias.
