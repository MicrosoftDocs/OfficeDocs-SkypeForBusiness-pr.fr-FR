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
description: Lisez cette rubrique pour découvrir comment gérer les basculements de jonction sur les appels sortants de Teams vers le contrôleur de frontière de session (SBC).
ms.openlocfilehash: 0fa0d452a2611874be570f4e80a746bb07da0163
ms.sourcegitcommit: d7a86b3a72005764c18acb60eedf5163523ffae3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/29/2022
ms.locfileid: "67457134"
---
# <a name="trunk-failover-on-outbound-calls"></a>Basculement de jonction sur les appels sortants

Cette rubrique explique comment éviter les basculements de jonction sur les appels sortants , de Teams vers le contrôleur de frontière de session (SBC).

## <a name="failover-on-network-errors"></a>Basculement sur les erreurs réseau

Si une jonction ne peut pas être connectée pour une raison quelconque, la connexion à la même jonction est tentée à partir d’un autre centre de données Microsoft. Le centre de données peut se trouver dans une autre région géographique, en dehors de votre région actuelle. Une jonction peut ne pas être connectée si une connexion est refusée, s’il existe un délai d’expiration TLS ou s’il existe d’autres problèmes au niveau du réseau.

Par exemple, une connexion peut échouer si un administrateur limite l’accès au SBC uniquement à partir d’adresses IP connues, mais oublie de placer les adresses IP de tous les centres de données de routage direct Microsoft sur la liste Access Control (ACL) du SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Basculement de codes SIP spécifiques reçus du contrôleur de frontière de session (SBC)

Si le routage direct reçoit des codes d’erreur SIP 4xx ou 6xx en réponse à une invitation sortante, l’appel est considéré comme terminé par défaut. Sortant signifie un appel d’un client Teams au réseau téléphonique commuté public (RTC) avec le flux de trafic suivant : Client Teams -> Routage direct -> SBC -> réseau de téléphonie.

La liste des codes SIP se trouve dans le [RFC SIP (Session Initiation Protocol](https://tools.ietf.org/html/rfc3261)).

Supposons qu’un SBC ait répondu à une invitation entrante avec le code « Délai d’expiration de la demande 408 : le serveur n’a pas pu produire de réponse dans un délai approprié, par exemple, s’il n’a pas pu déterminer l’emplacement de l’utilisateur dans le temps. Le client peut répéter la demande sans modification ultérieurement. »

Ce SBC particulier peut avoir des difficultés à se connecter à l’appelé, peut-être en raison d’une configuration réseau incorrecte ou d’une autre erreur. Toutefois, il existe un autre SBC dans l’itinéraire qui peut être en mesure d’atteindre l’appelé.

Dans le diagramme suivant, lorsqu’un utilisateur passe un appel à un numéro de téléphone, il existe deux SBC dans l’itinéraire qui peuvent potentiellement fournir cet appel. Initialement, SBC1.contoso.com est sélectionné pour l’appel, mais SBC1.contoso.com n’est pas en mesure d’atteindre un réseau PTSN en raison d’un problème réseau.
Par défaut, l’appel est terminé à ce stade. 
 
![Diagramme montrant que SBC ne parvient pas à atteindre PSTN en raison d’un problème réseau.](media/direct-routing-failover-response-codes1.png)

Il existe un SBC de plus dans l’itinéraire qui peut potentiellement fournir l’appel.
Si vous configurez le paramètre `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, le deuxième SBC est essayé (SBC2.contoso.com dans le diagramme suivant) :

![Diagramme montrant le routage vers le deuxième SBC.](media/direct-routing-failover-response-codes2.png)

La définition du paramètre -FailoverResponseCodes et la spécification des codes vous permettent d’affiner votre routage et d’éviter les problèmes potentiels lorsqu’un SBC ne peut pas passer d’appel en raison de problèmes réseau ou autres.

Valeurs par défaut : 408, 503, 504

