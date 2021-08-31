---
title: Tableau de bord d’état pour le routage direct
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment utiliser le tableau de bord d’état pour surveiller la connexion entre votre contrôleur de session border controller et le routage direct.
ms.openlocfilehash: 4927f6473e74a6fc14add9105022fc8efbade260
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728213"
---
# <a name="health-dashboard-for-direct-routing"></a>Tableau de bord d’état pour le routage direct

Le tableau de bord d’état du routage direct vous permet de surveiller la connexion entre votre contrôleur de session border Controller (SBC) et l’interface de routage directe.  Le tableau de bord d’état d’état vous permet de surveiller des informations sur votre SBC, le service téléphonique et les paramètres réseau entre votre SBC et l’interface de routage directe. Ces informations peuvent vous aider à identifier les problèmes, y compris la raison de l’abandon d’appels. Par exemple, il se peut que SBC cesse d’envoyer des appels si un certificat sur le SBC a expiré ou s’il existe des problèmes de réseau. Consultez les [rôles d’administrateur](using-admin-roles.md) pour savoir qui a accès au tableau de bord d’état d’état.

Le tableau de bord d’état surveille deux niveaux d’informations :

- État global des SBCS connectés
- Informations détaillées sur les SCS connectés

Vous pouvez afficher le tableau de bord d’état d’Microsoft Teams et Skype Entreprise Centre d’administration.

## <a name="overall-health"></a>État global

Le tableau de bord d’état fournit les informations suivantes relatives à l’état global des pc SBE connectés :

 ![Affiche les statistiques du tableau de bord d’état d’état.](media/direct-routing-dashboard-stats1.png)

- **Résumé du routage direct** : affiche le nombre total de PCB inscrits dans le système. L’inscription signifie que l’administrateur client a ajouté un SBC à l’aide de New-CsOnlinePSTNGateway client. Si le SBC a été ajouté dans PowerShell mais n’a jamais été connecté, le tableau de bord d’état le montre dans un état défectueux.

- **SBC** - FQDN du SBC couplé.

- Rapport d’efficacité du réseau **(NER)** - Cette taux mesure la capacité d’un réseau à fournir des appels en mesurant le nombre d’appels envoyés par rapport au nombre d’appels remis à un destinataire.  

   La lettre NER mesure la capacité des réseaux à fournir des appels au terminal final, à l’exception des actions des utilisateurs qui entraînent des refus d’appel.  Si le destinataire a rejeté un appel ou envoyé l’appel vers la messagerie vocale, l’appel est comptabilisé comme une remise réussie. Cela signifie qu’un message de réponse, un signal occupé ou une sonnerie sans réponse sont considérés comme des appels réussis.
  
   Par exemple, supposons que le routage direct a envoyé un appel au SBC et que celui-ci renvoie le code SIP « 504 Server Time-out - The server attempted to access another server in attempting to process the request and did not receive a prompt response ». Cette réponse indique qu’il existe un problème côté SBC, ce qui diminuera la réponse neR sur le tableau de bord d’état d’santé pour ce tableau de bord SBC.
  
   Étant donné que l’action que vous prenez peut dépendre du nombre d’appels concernés, le Tableau de bord d’état d’état indique le nombre d’appels analysés pour calculer un paramètre. Si le nombre d’appels est inférieur à 100, la ner est peut-être assez faible, mais reste normale.

   La formule utilisée pour calculer LA VALEUR.NER est la formule la plus simple :

   NER = 100 x (appels répondus + Occupé(e) + Sonnerie sans réponse + Refus de terminal)/Nombre total d’appels

- **Durée moyenne des appels** : les informations sur la durée moyenne des appels peuvent vous aider à surveiller la qualité des appels. La durée moyenne d’un appel RSTN en 1:1 est de 4 à 5 minutes.  Cependant, pour chaque entreprise, cette moyenne peut différer.  Microsoft recommande d’établir un point de comparaison pour la durée moyenne des appels pour votre entreprise. Si ce paramètre passe nettement en dessous du point de comparaison, il peut indiquer que vos utilisateurs ont des problèmes de qualité ou de fiabilité des appels et sont raccrochants plus tôt que d’habitude. Si vous commencez à voir une durée moyenne d’appel extrêmement faible (par exemple, 15 secondes), il se peut que les appelants raccrochent parce que votre service ne fonctionne pas de manière fiable.

   Étant donné que l’action que vous prenez peut dépendre du nombre d’appels concernés, le Tableau de bord d’état d’état indique le nombre d’appels analysés pour calculer un paramètre.

- État de la connectivité **TLS** - La connectivité TLS (Transport Layer Security) indique l’état des connexions TLS entre le routage direct et le SBC. Le tableau de bord d’état analyse également la date d’expiration du certificat et avertit si un certificat est prêt à expirer dans les 30 jours de sorte que les administrateurs peuvent renouveler le certificat avant que le service ne soit interrompu.

   En cliquant sur le message d’avertissement, vous pouvez voir une description détaillée du problème dans une fenêtre pop-up sur la droite et des recommandations pour la façon de résoudre le problème.

- **État des options SIP** : par défaut, le SBC envoie des messages d’options toutes les minutes. Cette configuration peut varier pour différents fournisseurs SBC. Le routage direct vous avertit si les options SIP ne sont pas envoyées ou ne sont pas configurées. Pour plus d’informations sur la surveillance des options SIP et les conditions dans les cas où un SBC peut être marqué comme non fonctionnel, voir Surveiller et dépanner le [routage direct.](direct-routing-monitor-and-troubleshoot.md)

- État détaillé des options SIP : outre l’affichage d’un problème avec le flux des options **SIP,** le tableau de bord d’état fournit des descriptions détaillées des erreurs. Vous pouvez accéder à la description en cliquant sur le message « Avertissement ». Une fenêtre pop-up à droite affiche la description détaillée de l’erreur.

   Les valeurs possibles pour les messages d’état des options SIP sont les suivantes :

    - Actif : le service de routage SBC est actif--Microsoft Direct Routing voit les options s’écoulent à intervalles réguliers.

    - Avertissement : aucune option SIP n’existe dans la base de données (votre administrateur l’a créée à l’aide de la commande New-CsOnlinePSTNGateway). Il est configuré pour envoyer les options SIP, mais le service de routage direct n’a jamais vu les options SIP revenir de ce SBC.

    - Avertissement : les messages SIP ne sont pas configurés - La surveillance de ligne à l’aide des options SIP n’est pas désactivée. Microsoft Calling System utilise les options SIP et la surveillance de la négociation TLS (Transport Layer Security) pour détecter l’état des contrôleurs de session connectés en bordure (SBCS) au niveau de l’application. Vous aurez des problèmes si cette ligne peut être atteinte au niveau du réseau (par commande ping), mais le certificat a expiré ou la pile SIP ne fonctionne pas. Pour vous aider à identifier précocement de tels problèmes, Microsoft recommande d’activer l’envoi des options SIP. Consultez la documentation du fabricant SBC pour configurer les options SIP d’envoi.

- **Capacité des** appels simultanés : vous pouvez spécifier la limite des appels simultanés qu’un SBC peut gérer à l’aide de la commande Nouveau ou Set-CsOnlinePSTNGateway avec le paramètre -MaxConcurrentSessions. Ce paramètre calcule le nombre d’appels envoyés ou reçus par routage direct à l’aide d’un SBC spécifique et le compare à la limite définie. Remarque : si le SBC gère également les appels vers différents PBX, ce numéro n’affiche pas les appels simultanés réels.

## <a name="detailed-information-for-each-sbc"></a>Informations détaillées pour chaque SBC

Vous pouvez également afficher les informations détaillées d’un SBC spécifique, comme illustré dans la capture d’écran suivante :

![Détails SBC du tableau de bord d’état d’état.](media/direct-routing-dashboard-SBC-detail1.png)

La vue détaillée affiche les paramètres supplémentaires suivants :

- État de la connectivité **TLS** : cette valeur est identique à celle de la page « État global » ;

- Dernier état de la connectivité **TLS** : indique l’heure à partir de quel moment SBC a établir une connexion TLS au service de routage direct.

- **État des options SIP** – identique à celui de la page « État global ».

- **Les options SIP ont été cochées** pour la dernière fois (heure de réception des options SIP).

- **État SBC** – état global du SBC, en fonction de tous les paramètres surveillés.

- **Appel simultané**- Indique le nombre d’appels simultanés gérés par le SBC. Ces informations sont utiles pour prévoir le nombre de canaux simultanés dont vous avez besoin et voir la tendance. Vous pouvez faire glisser les données selon le nombre de jours et l’orientation des appels (flux entrant/sortant/Tous).

- **Paramètres réseau** : tous les paramètres réseau sont mesurés à partir de l’interface de routage direct vers le contrôleur de session en bordure. Pour plus [d’informations](./prepare-network.md)sur les valeurs recommandées, voir Préparer le réseau de votre organisation pour Microsoft Teams et examiner le bord du client pour Microsoft Edge valeurs recommandées.

   - Gigue – Mesure en millisecondes du retard de propagation réseau calculée entre deux points de terminaison à l’aide du protocole RTCP (protocole de contrôle RTP).

   - Perte de paquets – mesure du nombre de paquets qui n’ont pas réussi à arriver ; elle est calculée entre deux points de terminaison.

   - Latence - (également appelée durée des allers-retours) est la durée de l’envoi d’un signal, plus la durée de réception de l’accusé de réception de ce signal. Ce délai est constitué des heures de propagation entre les deux points d’un signal.

   Vous pouvez faire glisser les données selon le nombre de jours et l’orientation des appels (flux entrant/sortant/Tous).

**Rapport d’efficacité** du réseau : il s’agit du même paramètre qui apparaît dans le tableau de bord État global, mais avec la possibilité de découper les données par série de temps ou par direction d’appel.