---
title: Basculement de jonction sur les appels sortants
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Lisez cette rubrique pour savoir comment gérer les basculements de jonction pour les appels sortants à partir des équipes pour le contrôleur de Session en périphérie (SBC).
ms.openlocfilehash: 1f8e7dfd5064b9c3d857165a9a4e2d39565dfeef
ms.sourcegitcommit: a3181bc3707b09c1e3f87c343b38259fdc6dabd2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2018
ms.locfileid: "27271148"
---
# <a name="trunk-failover-on-outbound-calls"></a>Basculement de jonction pour les appels sortants

Cette rubrique explique comment éviter les basculements de jonction pour les appels sortants--des équipes pour le contrôleur de Session en périphérie (SBC).

## <a name="failover-on-network-errors"></a>Basculement sur les erreurs de réseau

Si une jonction ne peut pas être connectée pour une raison quelconque, la connexion à la jonction même tentative sera effectuée à partir d’une autre Microsoft Datacenter. Une jonction ne pas être connectée, par exemple, si une connexion est refusée, s’il existe un délai d’attente TLS ou s’il existe des problèmes de niveau réseau.
Par exemple, une connexion peut échouer si une limite l’accès administrateur pour le contrôleur SBC, uniquement à partir des adresses IP connues, mais oublie placer les adresses IP de tous les centres de données de routage Direct Microsoft sur la liste de contrôle d’accès (ACL) de la SBC. 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a>Basculement de codes SIP spécifiques reçu à partir du contrôleur de Session en périphérie (SBC)

Si le routage Direct reçoit les codes d’erreur 4xx ou 6xx SIP en réponse à une invitation sortante, l’appel est considérée comme terminée par défaut. Sortant signifie qu’un appel à partir d’un client équipes pour le Public téléphone réseau commuté (RTC) avec le flux de trafic suivants : Client équipes -> routage Direct -> SBC -> réseau téléphonique.

Vous trouverez la liste des Codes SIP dans le [Protocole SIP (Session Initiation) RFC](https://tools.ietf.org/html/rfc3261).

Supposent une situation où un contrôleur SBC une réponse sur une invitation entrante par le code « expiration de délai 408 demande : le serveur ne peut pas fournir une réponse au sein d’une durée appropriée, par exemple, si elle a pas pu déterminer l’emplacement de l’utilisateur dans le temps. Le client peut répéter de la demande sans modifications ultérieurement. »

Cette SBC spécifique peut être confronté à des difficultés pour connecter à l’appelé, par exemple en raison d’une configuration réseau incorrecte ou une autre erreur. Toutefois, un SBC plus est dans l’itinéraire peut être en mesure d’atteindre l’appelé.

Dans le diagramme suivant, lorsqu’un utilisateur effectue un appel vers un numéro de téléphone, il existe deux SBCs dans l’itinéraire que peut transmettre potentiellement cet appel. À l’origine, SBC1.contoso.com est activée pour l’appel, mais SBC1.contoso.com n’est pas en mesure d’atteindre un réseau PTSN en raison d’un problème de réseau.
Par défaut, l’appel réussira pour l’instant. 
 
![Montre SBC Impossible d’atteindre PSTN en raison de problèmes de réseau](media/direct-routing-failover-response-codes1.png)

Mais il existe un SBC plus dans l’itinéraire potentiellement capable de fournir l’appel.
Si vous configurez le paramètre Set-CSOnlinePSTNGateway-Identity sbc1.contoso.com - ReinviteResponceCode « 408 », la deuxième SBC sera essayé--SBC2.contoso.com dans le diagramme suivant :

![Indique le routage vers le deuxième SBC](media/direct-routing-failover-response-codes2.png)

Le paramètre - FailoverResponceCodes et en spécifiant les codes vous aide à bien paramétrer votre routage et éviter les éventuels problèmes lors d’un contrôleur SBC ne peut pas émettre un appel en raison de réseau ou d’autres problèmes.

Valeurs par défaut : 408, 503, 504

