---
title: Basculement de jonction sur les appels sortants
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lisez cette rubrique pour découvrir comment gérer les failovers de ligne lors des appels sortants d’un Teams vers le contrôleur de session border Controller (SBC).
ms.openlocfilehash: 83320e93df7cbf476d71b3b9165d50ca387292b9
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727863"
---
# <a name="trunk-failover-on-outbound-calls"></a>Basculement de jonction sur les appels sortants

Cette rubrique explique comment éviter les failovers de ligne lors des appels sortants, du Teams au contrôleur de session en bordure (SBC).

## <a name="failover-on-network-errors"></a>Failover on network errors

Si aucune ligne ne peut être connectée pour une raison quelconque, la connexion à la même ligne est essayée à partir d’un autre centre de données Microsoft. Par exemple, une ligne n’est peut-être pas connectée si une connexion est refusée, s’il y a un délai d’émission du TLS ou s’il existe d’autres problèmes au niveau du réseau.
Par exemple, une connexion peut échouer si un administrateur limite l’accès au SBC uniquement à partir d’adresses IP connues, mais oublie de placer les adresses IP de tous les centres de données de routage Microsoft Direct sur la liste de contrôle d’accès (ACL) du SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Over de codes SIP spécifiques reçus du contrôleur de bordure de session (SBC)

Si le routage direct reçoit des codes d’erreur 4xx ou 6xx SIP en réponse à une invitation sortante, l’appel est considéré comme terminé par défaut. Sortant signifie un appel entre un client Teams et le réseau téléphonique commuté (RST) avec le flux de trafic suivant : client Teams -> Routage direct -> SBC -> réseau téléphonique.

La liste des codes SIP est également répertoriée dans le protocole [SIP (Session Initiation Protocol).](https://tools.ietf.org/html/rfc3261)

Supposons qu’un SBC a répondu à une invitation entrante avec le code « Délai d’appel 408 : le serveur ne pouvait pas produire de réponse dans un délai approprié, par exemple, s’il ne pouvait pas déterminer l’emplacement de l’utilisateur à temps. Le client PEUT répéter la demande sans modification ultérieurement ».

Ce SBC particulier peut avoir des difficultés de connexion au contact de l’appelant, peut-être en raison d’une configuration réseau mal configurée ou d’une autre erreur. Toutefois, il existe un autre SBC dans l’itinéraire, qui pourra peut-être joindre l’appelé.

Dans le diagramme suivant, lorsqu’un utilisateur appelle un numéro de téléphone, deux SCS peuvent potentiellement remettre cet appel dans l’itinéraire. Au début, SBC1.contoso.com est sélectionné pour l’appel, mais SBC1.contoso.com n’est pas en mesure d’accéder à un réseau PTSN en raison d’un problème de réseau.
Par défaut, l’appel sera effectué à ce moment-là. 
 
![Diagramme montrant SBC ne parvient pas à joindre PSTN en raison d’un problème de réseau.](media/direct-routing-failover-response-codes1.png)

Mais il existe un autre SBC dans l’itinéraire, qui peut potentiellement donner l’appel.
Si vous configurez le paramètre, le deuxième SBC sera essayé, comme SBC2.contoso.com `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` dans le diagramme suivant :

![Diagramme montrant le routage vers le deuxième SBC.](media/direct-routing-failover-response-codes2.png)

La définition du paramètre -FailoverResponseCodes et la spécification des codes vous permettent d’affiner votre routage et d’éviter les problèmes potentiels lorsqu’un SBC ne peut pas passer d’appel en raison de problèmes de réseau ou autres.

Valeurs par défaut : 408, 503, 504

