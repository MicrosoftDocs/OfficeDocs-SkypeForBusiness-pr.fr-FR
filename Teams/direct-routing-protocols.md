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
description: Protocoles de routage directe
appliesto:
- Microsoft Teams
ms.openlocfilehash: a470c402ebfd4e70955f4e864d45dbaaca476dfd
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065624"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Itinéraires directs-définitions et normes RFC

Cet article décrit comment le routage direct du système Microsoft Phone implémente les protocoles standard RFC. Cet article est destiné aux administrateurs de voix qui sont responsables de la configuration de la connexion entre le contrôleur de bordure de session (SBC) local et le service proxy SIP (Session Initiation Protocol).

Les interfaces clientes SBC avec les composants suivants du serveur principal Microsoft teams : 

- **Le proxy SIP pour la** signalisation. Il s’agit du composant Internet du routage direct qui gère les connexions SIP (TLS) entre le routage SBCs et le routage direct.

- **Processeurs multimédias** pour médias. Il s’agit du composant Internet du routage direct qui gère le trafic multimédia. Ce composant utilise les protocoles SRTP et SRTCP.


Pour plus d’informations sur le routage direct, voir [routage direct du système téléphonique](direct-routing-landing-page.md).

Pour plus d’informations sur l’implémentation du protocole SIP par le routage direct, voir [routage direct-protocole SIP](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>Normes RFC

Le routage direct répond aux normes RFC.  Le SBC connecté au routage direct doit également respecter les RFC suivantes (ou leurs successeurs). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Normes applicables aux appareils qui prennent en charge le mode de contournement non multimédia 

Les normes suivantes s’appliquent aux appareils qui prennent en charge uniquement le mode de contournement non multimédia :

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): protocole d’initiation de session
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Extension privée du protocole d’initiation de session pour l’identité affirmée au sein de réseaux approuvés : sections sur la gestion de l’en-tête d’identité P-assertion. Le routage direct envoie l’identité P-assertion avec les en-têtes d’ID de confidentialité. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Extension du protocole SIP (Session Initiation Protocol) pour les informations d’historique requises. Voir aussi : description du protocole SIP de routage pour plus d’informations.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Mécanisme référencé par le protocole d’initiation de session
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) L’en-tête SIP (Session Initiation Protocol) "remplace" 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Utilisation SIP (Session Initiation Protocol) du modèle d’une proposition/réponse.
  Voir la section « déviations de RFC ».
- [Rfc 3711](https://tools.ietf.org/html/rfc3711) et [RFC 4771](https://tools.ietf.org/html/rfc4771). Protégez le trafic RTP à l’aide de SRTP. L’SBC doit être en mesure d’établir des clés avec SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Clarifications ou réponses du protocole SDP (session Description Protocol) pour multiplexage RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Normes applicables aux appareils prenant en charge le mode de contournement multimédia

Outre les normes répertoriées comme applicables au mode non-contournement, les normes suivantes sont utilisées pour le mode de contournement multimédia :

- [RFC 5245 interactive Connectivity Establishing (ICE) pour Bypass Media](https://tools.ietf.org/html/rfc5245).  L’SBC doit prendre en charge les éléments suivants :
  - ICE Lite : les clients teams sont des clients de glace complète
  - Les [redémarrages de glace](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Pour en savoir plus sur les redémarrages de glace, utilisez le cas et les exemples dans le redémarrage   
- [Contrôle du protocole SIP rfc 5589 (Session Initiation Protocol)-transfert](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 premiers médias et la génération de tonalités de sonnerie dans le protocole SIP (Session Initiation Protocol)](https://tools.ietf.org/html/rfc3960), voir les sections 3,1, fork et 3,2, Generation de sonnerie 
- [Utilitaires de traversée de session RFC 5389 pour NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 traversée à l’aide de relais sur NAT (TURN) : les extensions de relais aux utilitaires de traversée de session pour tar (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Normes applicables pour la prise en charge du transport d’informations d’emplacement vers les fournisseurs de E911

- [RFC 6442, le transport d’emplacement du protocole d’initiation de session](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Écarts par rapport aux RFC

Le tableau suivant répertorie les sections des RFC (s) dans lesquelles l’implémentation de la pile SIP ou multimédias de Microsoft s’écarte de la norme :

| RFC et sections | Description | Écart |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, section 5,3 attente et reprise de médias](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC autorise l’utilisation de « a = inactif », « a = sendonly », a = recvonly» pour mettre un appel en attente. |Le proxy SIP prend uniquement en charge « a = inactive » et ne comprend pas si l’SBC envoie « a = sendonly » ou « a = recvonly ».
| [RFC 6337, section 5,4 «comportement lors de la réception d’un SDP avec c = 0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) exige qu’un agent est en mesure de recevoir SDP avec une adresse de connexion de 0.0.0.0, auquel cas cela signifie qu’aucun RTP ou RTCP ne doit être envoyé à l’homologue. | Le proxy SIP ne prend pas en charge cette option. |

## <a name="operational-modes"></a>Modes opérationnels

Il existe deux modes opérationnels pour le routage direct :

- **Sans dérivation multimédia** dans laquelle le trafic RTP passe entre le client Teams, les processeurs multimédias et l’SBC.  

- **Avec une dérivation multimédia** dans laquelle tous les éléments MULTImédias RTP sont acheminés entre les points de terminaison d’équipes et SBC. 

Notez que le trafic SIP passe toujours par le proxy SIP.   
