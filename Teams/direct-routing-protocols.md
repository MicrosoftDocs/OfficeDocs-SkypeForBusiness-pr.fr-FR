---
title: 'Routage direct du système téléphonique Teams : définitions et normes RFC'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Comment le routage direct du système téléphonique Microsoft implémente les protocoles RFC standard.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01dbd61748d14ef21a600b2e4f44a306517e46d9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271239"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Routage direct - définitions et normes RFC

Cet article décrit comment le routage direct du système téléphonique Microsoft implémente les protocoles RFC standard. Cet article s’adresse aux administrateurs vocaux responsables de la configuration de la connexion entre le contrôleur de frontière de session local (SBC) et le service proxy SIP (Session Initiation Protocol).

Le client SBC interface avec les composants suivants dans le backend Microsoft Teams : 

- **Proxy SIP** pour la signalisation. Il s’agit du composant Internet du routage direct qui gère les connexions SIP (TLS) entre les SBC et le routage direct.

- **Processeurs multimédias** pour le média. Il s’agit du composant Internet du routage direct qui gère le trafic multimédia. Ce composant utilise des protocoles SRTP et SRTCP.


Pour plus d’informations sur le routage direct, consultez Le [routage direct du système téléphonique](direct-routing-landing-page.md).

Pour plus d’informations sur la façon dont le routage direct implémente le protocole SIP, consultez [Routage direct - Protocole SIP](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>Normes RFC

Le routage direct est conforme aux normes RFC.  Le SBC connecté au routage direct doit également respecter les RFC suivants (ou leurs successeurs). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Normes applicables aux appareils qui prennent en charge le mode de contournement non multimédia 

Les normes suivantes s’appliquent aux appareils qui prennent uniquement en charge le mode de contournement non multimédia :

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261) : Protocole d’initiation de session
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Extension privée au protocole d’initiation de session pour l’identité déclarée dans les réseaux approuvés : sections sur la gestion de l’en-tête P-Asserted-Identity. Le routage direct envoie P-Asserted-Identity avec des en-têtes d’ID de confidentialité. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Extension au protocole SIP (Session Initiation Protocol) pour les informations d’historique requises. Voir aussi : Description du protocole SIP de routage pour plus d’informations.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Mécanisme de Referred-By du protocole d’initiation de session
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) En-tête « Remplace » le protocole SIP (Session Initiation Protocol) 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Utilisation du protocole SIP (Session Initiation Protocol) du modèle d’offre/réponse.
  Consultez la section « Écarts par rapport à RFC ».
- [RFC 3711](https://tools.ietf.org/html/rfc3711) et [RFC 4771](https://tools.ietf.org/html/rfc4771). Protégez le trafic RTP à l’aide de SRTP. Le SBC doit être en mesure d’établir des clés à l’aide de SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Clarifications de l’offre/des réponses du protocole SDP (Session Description Protocol) pour le multiplexage RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Normes applicables aux appareils qui prennent en charge le mode de contournement du média

Outre les normes répertoriées comme applicables au mode sans contournement, les normes suivantes sont utilisées pour le mode de contournement multimédia :

- [RFC 5245 Interactive Connectivity Establishment (ICE) pour la déviation du trafic multimédia](https://tools.ietf.org/html/rfc5245).  Le SBC doit prend en charge les éléments suivants :
  - ICE Lite : les clients Teams sont des clients ICE complets
  - [Redémarrages ICE](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Pour plus d’informations sur le cas d’utilisation des redémarrages ICE et les exemples de redémarrage ICE : Appel de contournement multimédia transféré vers un point de terminaison qui ne prend pas en charge le contournement du média   
- [RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), consultez les sections 3.1, Forking et 3.2, Génération de sonneries 
- [Utilitaires de traversée de session RFC 5389 pour NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Normes applicables à la prise en charge de la transmission d’informations de localisation aux fournisseurs E911

- [RFC 6442, Transfert d’emplacement pour le protocole d’initiation de session](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Écarts par rapport aux écarts du RFC

Le tableau suivant répertorie les sections des RFC dans lesquelles l’implémentation du sip ou de la pile multimédia par Microsoft s’écarte de la norme :

| RFC et sections | Description | Déviation |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, section 5.3 Conservation et reprise des supports](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC permet d’utiliser « a=inactive », « a=sendonly », a=recvonly » pour mettre un appel en attente. |Le proxy SIP prend uniquement en charge « a=inactive » et ne comprend pas si le SBC envoie « a=sendonly » ou « a=recvonly ».
| [RFC 6337, section 5.4 « Comportement lors de la réception du protocole SDP avec c=0.0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) nécessite qu’un agent soit capable de recevoir le protocole SDP avec une adresse de connexion 0.0.0.0, auquel cas cela signifie que ni RTP ni RTCP ne doivent être envoyés à l’homologue. | Le proxy SIP ne prend pas en charge cette option. |

## <a name="operational-modes"></a>Modes opérationnels

Il existe deux modes opérationnels pour le routage direct :

- **Sans contournement multimédia** dans lequel tout le trafic RTP circule entre le client Teams, les processeurs multimédias et le SBC.  

- **Avec le contournement multimédia** dans lequel tous les médias RTP circulent entre les points de terminaison Teams et le SBC. 

Notez que le trafic SIP circule toujours via le proxy SIP. 

## <a name="dtmf"></a>DTMF
DTMF dans la bande n’est pas pris en charge par la pile multimédia.
