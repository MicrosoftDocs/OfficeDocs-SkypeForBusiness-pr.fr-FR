---
title: Téléphone vue d’ensemble du routage direct du système
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: HHw Direct Routing prend en charge la dérivation média avec un contrôleur de session Border Controller activé pour ICE Lite.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c32838d282d6f5fff5eb1e85c36d78eee8828d41
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234569"
---
# <a name="overview"></a>Vue d’ensemble

Cet article décrit la façon dont le routage direct prend en charge la dérivation média avec un contrôleur de session border controller (SBC) activé pour ICE Lite, comme décrit dans le [RFC 5245.](https://tools.ietf.org/html/rfc5245) Cet article est destiné aux administrateurs vocaux chargés de configurer la connexion entre le serveur SBC local et le service proxy SIP.

Cet article fournit une vue d’ensemble des scénarios ICE Lite et des conditions requises pour l’interopérabilité. Cet article décrit les formats des messages et les transitions de machine à état requises pour garantir la fiabilité du flux des appels et des médias.

## <a name="terminology"></a>Terminologie

- Tout d’abord Bonjour : les premiers mots prononcés par l’appelant et l’appelé. Il est important que tous les efforts soient déployés pour garantir la livraison fiable des premiers paquets à partir des points de terminaison dans la plupart des cas d’utilisation.

- Entrée de l’écran : l’offre de l’appelant peut être livrée à plusieurs points de terminaison si l’appelant est disponible sur plusieurs appareils (par exemple, un utilisateur Teams peut être connecté à Teams pour Windows et Teams pour Android ou iPhone).

- Réponse inversée (183) – Les points de terminaison des appelants pour une configuration d’appel plus rapide envoient une réponse avec les candidats et les clés nécessaires pour établir un flux multimédia. Cela est effectué dans l’attente de l’utilisateur pouvant répondre à l’appel (200OK) à partir de cette instance de l’appelant spécifique. L’appelant doit être prêt à recevoir les réponses de plusieurs personnes à l’aide de la forking.

- Re-Invite – Proposer aux candidats finux sélectionnés par le point de terminaison ICE de contrôle. L’attribut a=remote-candidate permet de résoudre les conditions de course qui seraient dues à la gestion de plusieurs bifurcations.

- Teams Point de terminaison : il peut s’agit soit d’un serveur (processeur multimédia, relais de transport) soit du client Teams client.

## <a name="message-format"></a>Format des messages

L Teams infrastructure de projets suit le RFC 5245 pour ICE-Lite. Cela implique que tous les messages STUN respectent la [norme RFC 5389.](https://tools.ietf.org/html/rfc5389)

Les STUN requis par la mise à jour RFC 5389 doivent ignorer les attributs STUN qu’ils ne reconnaissent pas et continuer à traiter les messages avec les attributs connus. 

Si des paquets malformés sont reçus, les paquets doivent être ignorés sans impact sur l’établissement de la session multimédia.

## <a name="ice-lite-requirements"></a>Conditions requises pour ICE Lite

Cette section présente brièvement les conditions requises pour ICE Lite.

### <a name="candidate-gathering"></a>Rassemblement des candidats

Le SBC doit offrir un seul candidat accessible publiquement. Pour l’instant, seuls les candidats IPV4 sont pris en charge.


#### <a name="connectivity-checks"></a>Vérifications de connectivité

L’implémentation ICE Lite doit répondre aux vérifications de connectivité reçues. Le point de terminaison ICE Lite ne doit pas envoyer de demandes de vérification de la connectivité. (Si des vérifications de connectivité sont envoyées en violation, l’implémentation complète répondra, ce qui peut entraîner la découverte de candidats dérivé par des pairs inattendus et potentiellement entraîner des échecs d’appel.)

#### <a name="nominations"></a>Tous les autres peuvent y avoir été nommé

Le point de terminaison d’implémentation complète ICE sera toujours le point de terminaison contrôle et suit les règles « Regular » pour la sélection des candidats finaux à utiliser pour le flux de médias. Le point de terminaison ICE Lite peut utiliser les contrôles pour conclure le chemin à utiliser pour établir un appel multimédia et complet.

Remarque : en cas d’utilisation d’une pliure avec des points de terminaison d’égal à égal envoyant 183 réponses différentes, le SBC doit être prêt à répondre aux vérifications de plusieurs points de terminaison et également à partir de plusieurs points de terminaison si les problèmes ont lieu avant 200OK. Selon la fusion de l’ordinateur de l’état ICE sur le chemin d’accès final et le minutage de la réponse de l’utilisateur, les choses peuvent se produire avant ou après 200OK. Le SBC doit être en mesure de gérer ces deux cas.

#### <a name="converging-for-forking"></a>Convergeant pour l’king

Si l’offre entre le test SBC et plusieurs points de terminaison Teams, les points de terminaison Teams peuvent répondre avec une réponse inexplique et démarrer des vérifications de connectivité. Le SBC doit être prêt à recevoir les vérifications de connectivité et à répondre aux vérifications de connectivité à partir de plusieurs points de terminaison d’égal à égal. Par exemple, l Teams un utilisateur peut être à la fois inscrit sur un ordinateur de bureau et un téléphone portable. Les deux appareils seront avertis de l’appel entrant et tenteront de vérifier la connectivité avec le SBC.

Finalement, un seul point de terminaison répondra à l’appel (200OK). Lors de la réception de la 200OK, le SBC peut configurer le contexte exact pour le traitement des paquets multimédias.

## <a name="scenarios"></a>Scénarios

###  <a name="inbound-call-from-sbc"></a>Appel entrant à partir de SBC

Dans ce scénario, le SBC doit gérer plusieurs points de terminaison pairs possibles :

- Les points de terminaison du serveur répondront généralement directement avec 200OK. Il s’agit de points de terminaison ICE complets qui sont généralement impliqués dans des scénarios de messagerie vocale, de file d’attente d’appels et de attendant automatique.

- Les points de terminaison du client peuvent envoyer plusieurs réponses avec différentes balises De/À (183) suivies d’un 200OK à partir du point de terminaison qui répond à l’appel. Il s’agit de points de terminaison ICE complets représentant généralement des clients d’utilisateurs finaux.

- Autres points de terminaison SBC. Il s’agit des points de terminaison ICE Lite généralement impliqués dans le scénario de sonnerie simultanée des points de terminaison du client et d’autres numéros de téléphone.

Le SBC doit répondre à toutes les demandes de vérification de connectivité valides reçues à partir des points de terminaison ICE complets. Selon la technologie RFC, les points de terminaison ICE complets deviendront des points de terminaison contrôlés. Les Teams points de terminaison (client/serveur) effectuent des vérifications de connectivité « régulières ». Le 200Ok final peut être soit à partir d’un point de terminaison qui a envoyé des médias précoces, soit d’un autre point de terminaison. Lors de la réception de la 200Ok, le SBC doit configurer le contexte pour le flux de médias. 

###  <a name="early-media"></a>Médias précoces

S’il existe un flux de médias précoce, le SBC doit être basé vers le premier point de terminaison qui démarre la diffusion en continu de médias. un flux de médias peut commencer avant les candidats. Le système SBC doit prendre en charge l’envoi de DTMF pendant cette phase afin d’activer les scénarios DVR/messagerie vocale. Le SBC doit utiliser le chemin d’accès de priorité le plus élevé sur lequel il a reçu les vérifications si l’examen n’est pas terminé.

### <a name="outbound-call-to-sbc"></a>Appel sortant vers SBC

Les Teams points de terminaison sont l’appelant pour ce scénario et seront les points de terminaison de contrôle. Lors de la réception d’une réponse complète (183) ou d’une réponse finale (200OK), le point de terminaison Teams démarre les vérifications de connectivité et passe aux vérifications « normales » pour effectuer les vérifications de connectivité.

Remarque : si la base de données SBC envoie une réponse complète (183), le SBC doit être prêt à recevoir les demandes de vérification de connectivité et potentiellement terminer les vérifications avant l’envoi du 200OK par le SBC. Si les vérifications et/ou contrôles sont effectués avant la réception de la mise à jour du 200OK, les vérifications et/ou les contrôles ne seront pas effectués à nouveau après la réception de 200OK. Le SBC ne doit pas changer les candidats ICE, le mot de passe et le fragment de nom d’utilisateur entre 183 et 200.

Pour prendre en charge les fichiers multimédias en avant-première, le SBC peut commencer à diffuser les médias vers le candidat ICE de l’pair, avec la priorité la plus élevée en fonction des vérifications de connectivité reçues, avant même que l’examen ne soit effectué par Teams point de terminaison. Le SBC doit s’attendre à ce que des médias Teams de tous les candidats jusqu’à ce que l’équipe soit terminée. Une fois qu’un candidat a été désigné, le contexte doit être réinitialisé pour envoyer et recevoir des paquets multimédias.

## <a name="srtp-support-requirements"></a>Conditions requises de prise en charge du SRTP

Le code SBC doit prendre en charge les données de chiffrement SRTP AES_CM_128_HMAC_SHA1_80'offre et de réponse dans le format suivant :

```console
"inline:" <key||salt> ["|" lifetime]
```

Voici un exemple d’attribut crypto dans l’offre SDP provenant du SBC :

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

Les paramètres MKI et Longueur ne sont pas obligatoires.

Pour plus d’informations, [voir RFC 4568, section 6.1.](https://tools.ietf.org/html/rfc4568#section-6.1)

## <a name="sdes-support-requirements"></a>Conditions requises pour la prise en charge de SDES

L’appareil doit pouvoir proposer SDES dans le format décrit ci-dessous. Les processeurs Microsoft Media préfèrent toujours SDES.

- Avec une dérivation non multimédia, même si un client prend uniquement en charge DTLS, les processeurs multimédias sont convertis en SDES.

- Avec la dérivation média, si un client est DTLS uniquement (état Google Chrome futur), un routage direct insère un mp dans le chemin, convertissant l’appel de la dérivation média en contournement non multimédia. Entre le composant SBC et le composant de processeur multimédia du routage direct, SDES est toujours utilisé.

Actuellement, aucun client de Teams n’offre de DTLS uniquement ; Google a toutefois annoncé qu’à un moment donné, il cessera de prise en charge de SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Format de l’offre SBC en mode contournement 

L’offre doit contenir SDES et peut contenir des contenus DTLS facultatifs au format suivant :

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Format de réponse contenant SDES à SBC

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Mise en forme de l’offre Teams SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Format de l’offre SDES uniquement sur SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

