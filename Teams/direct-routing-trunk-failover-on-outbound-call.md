---
title: Basculement de jonction sur les appels sortants
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Apprenez-en davantage sur la gestion des basculements de Trunk pour les appels sortants de teams vers le contrôleur de bordure de session (SBC).
ms.openlocfilehash: a5462de971fed32a0618800b257b9c6e37b462af
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572123"
---
# <a name="trunk-failover-on-outbound-calls"></a>Basculement de jonction sur les appels sortants

Cette rubrique explique comment éviter le basculement de Trunk sur les appels sortants à partir d’équipes vers le contrôleur de bordure de session (SBC).

## <a name="failover-on-network-errors"></a>Basculement sur erreur réseau

Si un Trunk ne peut pas être connecté pour une raison quelconque, la connexion au même Trunk sera tentée à partir d’un autre centre de donnée Microsoft. Un Trunk n’est peut-être pas connecté, par exemple, si une connexion est refusée, s’il y a un délai de connexion TLS ou s’il existe d’autres problèmes liés au réseau.
Par exemple, une connexion peut échouer si un administrateur limite l’accès à l’SBC uniquement à partir d’adresses IP bien connues, mais oublie de placer les adresses IP de tous les centres de distribution de routage direct Microsoft dans la liste de contrôle d’accès (ACL) de l’SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Basculement de codes SIP spécifiques reçus du contrôleur de bordure de session (SBC)

Si le routage direct reçoit des codes d’erreur SIP 4xx ou 6xx en réponse à une invitation sortante, l’appel est considéré comme complet par défaut. Sortant désigne un appel d’un client teams vers le réseau téléphonique public commuté (RTC) avec le flux de trafic suivant : le client teams > le routage direct-> le réseau de téléphonie de l’SBC->.

La liste des codes SIP est disponible dans le [RFC SIP (Session Initiation Protocol)](https://tools.ietf.org/html/rfc3261).

Dans le cas contraire, une colonie a répondu à une invitation entrante avec le code «408 de demande d’expiration : le serveur n’a pas pu produire de réponse dans un délai approprié, par exemple, s’il n’a pas pu déterminer l’emplacement de l’utilisateur dans le temps. Le client risque de reproduire la demande sans modification ultérieurement.»

Ce SBC particulier peut rencontrer des difficultés à se connecter à l’appelé, peut-être en raison d’un problème de configuration du réseau ou d’une autre erreur. Néanmoins, il existe une plus grande colonie dans l’itinéraire qui peut être en mesure de joindre l’appelant.

Dans le diagramme suivant, lorsqu’un utilisateur effectue un appel vers un numéro de téléphone, il y a deux éléments SBCs dans l’itinéraire qui peut éventuellement répondre à cet appel. Au départ, SBC1.contoso.com est sélectionné pour l’appel, mais SBC1.contoso.com ne peut pas accéder à un réseau PTSN en raison d’un problème de réseau.
Par défaut, l’appel est effectué pour le moment. 
 
![Diagramme montrant que les SBC ne peuvent pas joindre PSTN en raison d’un problème de réseau](media/direct-routing-failover-response-codes1.png)

Mais il existe une plus grande SBC dans l’itinéraire, qui peut éventuellement répondre à l’appel.
Si vous configurez `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`le paramètre, le second SBC sera essayé--SBC2.contoso.com dans le schéma suivant :

![Diagramme montrant le routage vers le second SBC](media/direct-routing-failover-response-codes2.png)

Le fait de définir le paramètre-FailoverResponseCodes et de spécifier les codes vous permet d’optimiser le routage et d’éviter les problèmes potentiels lorsqu’un SBC ne peut pas faire un appel en raison de problèmes réseau ou d’autres problèmes.

Valeurs par défaut : 408, 503, 504

