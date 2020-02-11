---
title: Routage direct via le système téléphonique
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
description: Protocoles de routage directe
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888573"
---
# <a name="overview"></a>Vue d’ensemble

Cet article décrit comment le routage direct prend en charge la dérivation multimédia avec un contrôleur de bordure de session (SBC) activé pour ICE Lite, comme décrit dans [RFC 5245](https://tools.ietf.org/html/rfc5245). Cet article est destiné aux administrateurs de voix qui sont responsables de la configuration de la connexion entre le SBC local et le service proxy SIP.

Cet article fournit une vue d’ensemble des scénarios et des exigences relatives à l’interopérabilité de glace Lite. Cet article décrit les formats des messages et les transitions de machine à États requises pour garantir la fiabilité des appels et du flux multimédia.

## <a name="terminology"></a>Liée

- Tout d’abord, Voici les premiers mots prononcés par l’appelant et l’appelé. Il est important de veiller à ce que toutes les tâches soient apportées pour s’assurer que les premiers paquets des points de terminaison sont remis de façon fiable dans la plupart des cas d’utilisation.

- Bifurcation : l’offre de l’appelant peut être fournie aux points de terminaison des appelants si l’appel est disponible sur plusieurs appareils (par exemple, un utilisateur de teams est peut-être connecté à teams pour Windows et Teams pour Android ou iPhone).

- Réponse provisoire (183) : les points de terminaison des appelants pour une configuration plus rapide des appels envoient une réponse avec les candidats et les clés nécessaires à la création du flux multimédia. Cette opération est réalisée en prévision de l’utilisateur qui peut éventuellement répondre à l’appel (200OK) de cette instance d’un appel. Avec la bifurcation, l’appelant doit être prêt à recevoir plusieurs réponses provisoires.

- Re-invitation : une proposition avec les candidats finaux sélectionnés par le point de terminaison de contrôle de glace. Cette opération a pour assembler l’attribut a = candidat à distance et résoudre les conditions de concurrence après la gestion de plusieurs branches.

- Point de terminaison d’équipes : il peut s’agir d’un serveur (processeur de média, relais de transport) ou du client Teams.

## <a name="message-format"></a>Format des messages

L’infrastructure teams suit le RFC 5245 pour glace-Lite. Cela implique que tous les messages STUN soient conformes à [RFC 5389](https://tools.ietf.org/html/rfc5389).

Le SBCs tel qu’il est requis par RFC 5389 doit ignorer tout attribut STUN qu’il ne reconnaît pas, et continuer de traiter les messages avec les attributs connus. 

En cas de réception de paquets incorrects, les paquets doivent être supprimés sans impact sur l’établissement de la session multimédia.

## <a name="ice-lite-requirements"></a>Configuration requise pour glace Lite

Cette section décrit brièvement la configuration requise pour ICE Lite.

### <a name="candidate-gathering"></a>Rassemblement des candidats

La SBC doit fournir un seul candidat qui est publiquement joignable. Pour l’instant, seuls les candidats IPV4 sont pris en charge.


#### <a name="connectivity-checks"></a>Vérification de la connectivité

L’implémentation de ICE Lite doit répondre aux vérifications de connectivité reçues. Le point de terminaison ICE Lite ne doit pas envoyer de demandes de vérification de connectivité. (Si des vérifications de connectivité sont envoyées en violation, l’implémentation complète répondra, ce qui peut entraîner la découverte d’candidats inattendus et provoquer potentiellement des échecs d’appel.)

#### <a name="nominations"></a>Candidatures

Le point de terminaison de l’implémentation complète de ICE sera toujours le point de terminaison de contrôle, et suivreez les désignations « standard » pour sélectionner les candidats finaux à utiliser pour le flux multimédia. Le point de terminaison Lite Lite peut utiliser les candidatures pour conclure le chemin à utiliser pour le média et l’établissement d’appel complet.

Remarque : dans le cas d’une bifurcation avec des points de terminaison d’homologues qui envoient des réponses provisoires 183, l’SBC doit être prêt à répondre aux contrôles de plusieurs points de terminaison et aux désignations de plusieurs points de terminaison si les candidatures se produisent avant 200OK. En fonction de la convergence de la machine à États de glace sur le chemin final et le minutage de la réponse de l’utilisateur, les candidatures peuvent se produire avant ou après 200OK. L’SBC doit être en mesure de gérer les deux cas.

#### <a name="converging-for-forking"></a>Convergence pour la bifurcation

S’il s’agit d’une proposition de branches SBC à plusieurs points de terminaison d’équipes, les points de terminaison d’équipes pourront répondre avec une réponse provisoire et démarrer des vérifications de connectivité. L’SBC doit être prêt à recevoir des vérifications de connectivité et à répondre aux vérifications de connectivité provenant de multiples points de terminaison d’homologues. Par exemple, l’utilisateur d’équipes peut être connecté à la fois à un bureau et un téléphone mobile. Les deux périphériques seront avertis de l’appel entrant et tenteront de vérifier la connectivité avec l’SBC.

Pour le moment, seul l’un des points de terminaison répond à l’appel (200OK). Lors de la réception de 200OK, l’SBC peut définir le contexte approprié pour le traitement des paquets multimédias.

## <a name="scenarios"></a>Scénarios

###  <a name="inbound-call-from-sbc"></a>Appel entrant d’SBC

Pour ce scénario, l’SBC doit gérer plusieurs points de terminaison homologues :

- Les points de terminaison du serveur répondent généralement directement à 200OK. Il s’agit de points de terminaison de glace complète qui sont généralement impliqués dans les scénarios de boîte vocale, de files d’attente d’appels et de standard automatique.

- Les points de terminaison client peuvent envoyer plusieurs réponses provisoires avec différentes balises (183) suivies d’une 200OK à partir du point de terminaison qui répond à l’appel. Il s’agit de points de terminaison de type glace complets qui représentent généralement les clients des utilisateurs finaux.

- Autres points de terminaison SBC. Il s’agit de points de terminaison ICE Lite habituellement liés au scénario de sonnerie simultanée de points de terminaison client et d’autres numéros de téléphone.

L’SBC doit répondre à toutes les demandes de vérification de connectivité valides reçues des points de terminaison de la glace complète. Par RFC, les points de terminaison de la glace complète sont en gestion des points de terminaison. Les points de terminaison Teams (client/serveur) effectuent des nominations « standard » pour vérifier la connectivité. Le 200Ok final peut être à partir d’un point de terminaison qui a envoyé des éléments multimédias en avance ou à partir d’un point de terminaison différent. Lors de la réception de 200Ok, l’SBC doit configurer le contexte approprié pour le flux multimédia. 

###  <a name="early-media"></a>Premiers éléments multimédias

S’il y a un flux de média précoce, l’SBC doit se verrouiller sur le premier point de terminaison qui démarre le média de diffusion. le flux multimédia peut commencer avant que les candidats soient désignés. L’SBC doit avoir une prise en charge pour l’envoi d’un DTMF dans le cadre de cette phase pour activer les scénarios IVR/vocaux. L’SBC doit utiliser le chemin de priorité le plus élevé sur lequel il a reçu des vérifications si la candidature n’est pas terminée.

### <a name="outbound-call-to-sbc"></a>Appel sortant vers SBC

Les points de terminaison d’équipes sont l’appelant pour ce scénario et seront le point de terminaison de contrôle. Lors de la réception d’une réponse provisoire (183) ou d’une réponse finale (200OK), le point de terminaison d’équipe démarre le contrôle de la connectivité et passe à l’étape « standard » pour terminer les vérifications de connectivité.

Remarque : si la SBC envoie une réponse provisoire (183), l’SBC doit être prêt à recevoir des requêtes de vérification de connectivité et peut éventuellement terminer les candidatures avant que le 200OK ne soit envoyé par l’SBC. Si les vérifications et/ou nominations sont achevées avant la réception de 200OK, les vérifications et/ou les nominations ne seront pas effectuées de nouveau après réception de 200OK. L’SBC ne doit pas modifier les candidatures de glace, le mot de passe et ufrag (fragment de nom d’utilisateur) entre 183 et 200.

Pour prendre en charge les contenus multimédias, les SBC peuvent commencer à diffuser en continu le contenu multimédia du candidat à la glace pair, avec la plus grande priorité en fonction des vérifications de connectivité reçues, même avant la fin de la nomination par le point de terminaison d’équipe. Les SBC doivent s’attendre à ce que le contenu multimédia d’équipes soit éligible jusqu’à ce que les candidatures soient terminées. Une fois qu’un candidat est désigné, l’élément SBC doit réinitialiser le contexte approprié pour envoyer et recevoir des paquets multimédias.

## <a name="srtp-support-requirements"></a>SRTP requises du support technique

L’SBC doit prendre en charge le chiffrement de chiffrement SRTP AES_CM_128_HMAC_SHA1_80 pour les propositions et répondez aux formats suivants :

```console
"inline:" <key||salt> ["|" lifetime]
```

Vous trouverez ci-dessous un exemple de l’attribut crypto de l’offrant SDP de l’SBC :

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

Les paramètres de MKI et de longueur ne sont pas obligatoires.

Pour plus d’informations, reportez-vous au [RFC 4568, section 6,1](https://tools.ietf.org/html/rfc4568#section-6.1).

## <a name="sdes-support-requirements"></a>Configuration requise pour le support SDES

L’appareil doit être en mesure d’afficher SDES dans le format décrit ci-dessous. Les processeurs multimédias Microsoft préfèrent toujours SDES.

- Dans le cas d’une dérivation non multimédia, même si un client prend uniquement en charge DTLS, les processeurs de médias sont convertis en SDES.

- Dans le cadre d’une dérivation de média, si un client est DTLS uniquement (État Google Chrome à venir), le routage direct insérera un MP dans le chemin d’accès, en convertissant l’appel à partir d’une dérivation média en non multimédia. Entre le composant SBC et le processeur multimédia du routage direct, SDES est toujours utilisé.

Pour le moment, il n’y a pas de client d’équipe qui propose uniquement DTLS ; Néanmoins, Google a annoncé qu’à un moment donné, il ne prend plus en charge SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Format de l’offrant proposée par SBC en mode contournement 

L’option doit contenir SDES et contenir DTLS facultatif dans le format suivant :

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Format de la réponse contenant SDES à SBC

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Mettre en forme les propositions d’équipes en SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Format de la présentation pour les services SBC uniquement

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

