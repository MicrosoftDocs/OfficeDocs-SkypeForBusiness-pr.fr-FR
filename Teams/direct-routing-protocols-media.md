---
title: Vue d’ensemble du routage direct du système téléphonique
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: hHw Direct Routing prend en charge le contournement multimédia avec un contrôleur de bordure de session activé pour ICE Lite.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6f9715ee410116a66c572522a910cd16ef27154
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614417"
---
# <a name="overview"></a>Vue d’ensemble

Cet article décrit comment le routage direct prend en charge le contournement multimédia avec un contrôleur de bordure de session (SBC) activé pour ICE Lite, comme décrit dans [RFC 5245](https://tools.ietf.org/html/rfc5245). Cet article s’adresse aux administrateurs vocaux responsables de la configuration de la connexion entre le SBC local et le service proxy SIP.

Cet article fournit une vue d’ensemble des scénarios ice Lite et des exigences en matière d’interopérabilité. L’article décrit les formats de message et les transitions de machine à états requises pour garantir un flux d’appel et de média fiable.

## <a name="terminology"></a>Terminologie

- First Hello : les premiers mots prononcés par l’appelant et l’appelé. Il est important que tous les efforts soient déployés pour s’assurer que les premiers paquets des points de terminaison sont remis de manière fiable pour la plupart des cas d’usage.

- Forking : l’offre de l’appelant peut être remise à plusieurs points de terminaison d’appelés si l’appelé est disponible sur plusieurs appareils (par exemple, un utilisateur Teams peut être connecté à Teams pour Windows et Teams pour Android ou iPhone).

- Réponse provisoire (183) : les points de terminaison de l’appelé pour une configuration d’appel plus rapide envoient une réponse avec les candidats et les clés nécessaires pour établir le flux multimédia. Cette opération est effectuée en prévision de la réponse potentielle de l’utilisateur à l’appel (200OK) à partir de cette instance d’appelé spécifique. Avec la duplication, l’appelant doit être prêt à recevoir plusieurs réponses provisoires.

- Re-Invite : offre avec les candidats finaux sélectionnés par le point de terminaison de contrôle ICE. Cela aura l’attribut a=remote-candidate pour résoudre toutes les conditions de concurrence de la gestion de plusieurs duplications.

- Point de terminaison Teams : il peut s’agir d’un serveur (processeur multimédia, relais de transport) ou du client Teams.

## <a name="message-format"></a>Format du message

L’infrastructure Teams suit RFC 5245 pour ICE-Lite. Cela implique que tous les messages STUN seront conformes à [RFC 5389](https://tools.ietf.org/html/rfc5389).

Les SBC requis par RFC 5389 doivent ignorer les attributs STUN qu’ils ne reconnaissent pas et continuer à traiter les messages avec les attributs connus. 

Si des paquets mal formés sont reçus, les paquets doivent être ignorés sans impact sur l’établissement de la session multimédia.

## <a name="ice-lite-requirements"></a>Configuration requise pour ICE Lite

Cette section décrit brièvement les conditions requises pour ICE Lite.

### <a name="candidate-gathering"></a>Rassemblement des candidats

Le SBC ne doit offrir qu’un seul candidat. Actuellement, seuls les candidats IPV4 sont pris en charge.


#### <a name="connectivity-checks"></a>Vérifications de connectivité

L’implémentation ICE Lite doit répondre aux vérifications de connectivité reçues. Le point de terminaison ICE Lite ne doit pas envoyer de demandes de vérification de connectivité. (Si des vérifications de connectivité sont envoyées en violation, l’implémentation complète répond, ce qui peut entraîner la découverte de candidats dérivés d’homologue inattendus et potentiellement des échecs d’appel.)

#### <a name="nominations"></a>Nominations

Le point de terminaison d’implémentation complète ICE sera toujours le point de terminaison de contrôle et suivra les nominations « régulières » pour sélectionner les candidats finaux à utiliser pour le flux multimédia. Le point de terminaison ICE Lite peut utiliser les candidatures pour conclure le chemin d’accès à utiliser pour les médias et l’établissement complet des appels.

Remarque : Dans le cas d’une saisie manuscrite avec des points de terminaison homologues qui envoient 183 réponses provisoires, le SBC doit être prêt à répondre aux vérifications de plusieurs points de terminaison et également aux candidatures de plusieurs points de terminaison si les candidatures se produisent avant 200OK. Selon la convergence de l’ordinateur d’état ICE sur le chemin final et le moment où l’utilisateur répond, les nominations peuvent se produire avant ou après 200OK. Le SBC doit être en mesure de gérer les deux cas.

#### <a name="converging-for-forking"></a>Convergation pour la duplication manuscrite

Si l’offre de la duplication SBC à plusieurs points de terminaison Teams, les points de terminaison Teams peuvent répondre avec une réponse provisoire et démarrer des vérifications de connectivité. Le SBC doit être prêt à recevoir des vérifications de connectivité et à répondre aux vérifications de connectivité de plusieurs points de terminaison homologues. Par exemple, l’utilisateur Teams peut être connecté à la fois à un bureau et à un téléphone portable. Les deux appareils seront avertis de l’appel entrant et tenteront des vérifications de connectivité avec le SBC.

Finalement, un seul des points de terminaison répondra à l’appel (200OK). Lors de la réception du 200OK, le SBC peut configurer le contexte approprié pour le traitement des paquets multimédias.

## <a name="scenarios"></a>Scénarios

###  <a name="inbound-call-from-sbc"></a>Appel entrant à partir de SBC

Pour ce scénario, il existe plusieurs points de terminaison d’homologue possibles que le SBC doit gérer :

- Les points de terminaison de serveur répondent généralement directement avec 200OK. Il s’agit de points de terminaison ICE complets qui sont généralement impliqués dans les scénarios de messagerie vocale, de file d’attente d’appels et de standard automatique.

- Les points de terminaison clients peuvent envoyer plusieurs réponses provisoires avec différentes balises From/To (183) suivies d’un 200OK à partir du point de terminaison qui répond à l’appel. Il s’agit de points de terminaison ICE complets qui représentent généralement des clients d’utilisateur final.

- Autres points de terminaison SBC. Il s’agit de points de terminaison ICE Lite généralement impliqués dans le scénario de sonnerie simultanée des points de terminaison client et d’un autre ou plusieurs numéros de téléphone.

Le SBC doit répondre à toutes les demandes de vérification de connectivité valides reçues des points de terminaison ICE complets. Par RFC, les points de terminaison ICE complets deviendront des points de terminaison de contrôle. Les points de terminaison Teams (client/serveur) effectuent des nominations « régulières » pour effectuer des vérifications de connectivité. Le 200Ok final peut être à partir d’un point de terminaison qui a envoyé un média précoce ou d’un autre point de terminaison. Lors de la réception du 200Ok, le SBC doit configurer le contexte approprié pour le flux multimédia. 

###  <a name="early-media"></a>Médias précoces

S’il existe un flux multimédia précoce, le SBC doit se verrouiller vers le premier point de terminaison qui démarre le streaming multimédia ; le flux multimédia peut commencer avant que les candidats soient nommés. Le SBC doit prendre en charge l’envoi de DTMF pendant cette phase pour activer les scénarios de messagerie vocale/IVR. Le SBC doit utiliser le chemin d’accès prioritaire le plus élevé sur lequel il a reçu des vérifications si les candidatures ne sont pas terminées.

### <a name="outbound-call-to-sbc"></a>Appel sortant à SBC

Les points de terminaison Teams sont l’appelant de ce scénario et seront le point de terminaison de contrôle. Lors de la réception d’une réponse provisoire (183) ou d’une réponse finale (200OK), le point de terminaison Teams démarre les vérifications de connectivité et passe aux nominations « régulières » pour effectuer les vérifications de connectivité.

Remarque : si le SBC envoie une réponse provisoire (183), le SBC doit être prêt à recevoir des demandes de vérification de connectivité et potentiellement terminer les candidatures avant que le 200OK soit envoyé par le SBC. Si les vérifications et/ou les nominations sont terminées avant la réception du 200OK, les vérifications et/ou les nominations ne seront plus effectuées après la réception de 200OK. Le SBC ne doit pas modifier les candidats ICE, le mot de passe et l’ufrag (fragment de nom d’utilisateur) entre 183 et 200.

Pour prendre en charge les médias précoces, le SBC peut commencer à diffuser le média en continu vers le candidat ICE pair, avec la priorité la plus élevée en fonction des vérifications de connectivité reçues, même avant que les candidatures ne soient terminées par le point de terminaison Teams. Le SBC doit attendre des médias de Teams sur n’importe quel candidat jusqu’à ce que les candidatures soient terminées. Une fois qu’un candidat est nommé, le SBC doit rétablir le contexte approprié pour envoyer et recevoir des paquets multimédias.

## <a name="srtp-support-requirements"></a>Exigences de prise en charge de SRTP

Le SBC doit prise en charge des AES_CM_128_HMAC_SHA1_80 de chiffrement de chiffrement SRTP pour l’offre et la réponse au format suivant :

```console
"inline:" <key||salt> ["|" lifetime]
```

Voici un exemple d’attribut de chiffrement dans l’offre SDP du SBC :

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

Les paramètres MKI et Length ne sont pas requis.

Pour plus d’informations, voir [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).

## <a name="sdes-support-requirements"></a>Exigences de prise en charge de SDES

L’appareil doit être en mesure d’offrir SDES au format décrit ci-dessous. Les processeurs multimédias Microsoft préfèrent toujours SDES.

- Avec la déviation non multimédia, même si un client prend uniquement en charge DTLS, les processeurs multimédias sont convertis en SDES.

- Avec la déviation du trafic multimédia, si un client est DTLS uniquement (futur état Google Chrome), le routage direct insère un mp dans le chemin d’accès, convertissant l’appel du contournement multimédia en contournement non multimédia. Entre le composant SBC et le composant processeur multimédia du routage direct, SDES est toujours utilisé.

Actuellement, il n’existe aucun client Teams qui offre uniquement DTLS ; Toutefois, Google a annoncé qu’à un moment donné, ils cesseront de soutenir SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Format de l’offre de SBC en mode contournement 

L’offre doit contenir SDES et peut contenir DTLS facultatif au format suivant :

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Format de réponse contenant SDES vers SBC

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Format de l’offre de Teams vers SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Format de l’offre SDES uniquement pour SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

