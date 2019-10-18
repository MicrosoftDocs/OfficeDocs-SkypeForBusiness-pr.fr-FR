---
title: Tableau de bord d’État pour le routage direct
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Découvrez comment utiliser le tableau de bord d’état d’intégrité pour contrôler la connexion entre votre contrôleur de bordure de session et le routage direct.
ms.openlocfilehash: 0424f24e323928f487e8b43ce72e51602f9eab52
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572200"
---
# <a name="health-dashboard-for-direct-routing"></a>Tableau de bord d’État pour le routage direct

Le tableau de bord d’intégrité pour le routage direct vous permet d’analyser la connexion entre votre contrôleur de bordure de session et l’interface de routage directe.  Le tableau de bord d’État vous permet d’surveiller les informations relatives à votre SBC, au service de téléphonie et aux paramètres réseau entre votre SBC et l’interface de routage directe. Ces informations peuvent vous aider à identifier les problèmes, notamment le motif des appels interrompus. Par exemple, l’SBC peut arrêter d’envoyer des appels si un certificat sur l’SBC a expiré ou s’il rencontre des problèmes de réseau.  

Le tableau de bord d’état de santé analyse deux niveaux d’information :

- Intégrité globale de l’SBCs connectée
- Informations détaillées sur la connexion SBCs connectée

Vous pouvez afficher le tableau de bord d’État dans le centre d’administration Microsoft teams et Skype entreprise.


## <a name="overall-health"></a>Intégrité globale

Le tableau de bord de santé fournit les informations suivantes relatives à l’intégrité globale de l’SBCs connectée :

 ![Statistiques de tableau de bord d’État](media/direct-routing-dashboard-stats1.png)

- **Résumé du routage direct** : affiche le nombre total d’inscriptions SBCS inscrites dans le système. L’enregistrement implique que l’administrateur client a ajouté une SBC en utilisant la commande New-CsOnlinePSTNGateway. Si l’SBC a été ajouté dans PowerShell, mais n’est jamais connecté, le tableau de bord d’état de l’affichage affiche son état d’intégrité.

- **SBC** -nom de domaine complet de l’SBC couplé.

- **Taux d’efficacité du réseau (ner)** : ner mesure la capacité d’un réseau à remettre des appels en mesurant le nombre d’appels envoyés par rapport au destinataire.  

   Le NER mesure la capacité des réseaux à délivrer les appels vers le terminal principal, à l’exception des actions des utilisateurs qui génèrent des rejets d’appel.  Si le destinataire a rejeté un appel ou a envoyé l’appel à la boîte vocale, l’appel est considéré comme une remise réussie. Cela signifie qu’un message de réponse, un signal occupé ou une sonnerie sans réponse sont tous considérés comme des appels réussis. 
  
   Par exemple, supposons que le routage direct envoie un appel au SBC et que le SBC renvoie le code SIP « 504 Server Time-Out-le serveur tente d’accéder à un autre serveur en essayant de traiter la demande sans recevoir de réponse d’invite ». Cette réponse indique qu’il y a un problème sur le côté de l’SBC et cela diminue le NER sur le tableau de bord d’état de cette SBC. 
  
   Dans la mesure où l’action que vous prenez peut dépendre du nombre d’appels concernés, le tableau de bord d’État du service indique le nombre d’appels analysés pour calculer un paramètre. Si le nombre d’appels est inférieur à 100, le NER peut être très faible, mais rester normal. 

   La formule utilisée pour calculer NER est la suivante :

   NER = appels à la demande + utilisateur occupé + sonne sans réponse + borne de rejet de borne x 100

 
- **Durée d’appel moyenne** : les informations relatives à la durée d’appel moyenne vous permettent de surveiller la qualité des appels. La durée moyenne d’un appel RTC 1:1 est de quatre à cinq minutes.  Toutefois, pour chaque société, cette moyenne peut varier.  Microsoft recommande d’établir un planning de référence pour la durée d’appel moyenne de votre entreprise. Si ce paramètre est largement inférieur au planning de référence, il est possible que vos utilisateurs rencontrent des problèmes de qualité d’appel ou de fiabilité et qu’ils raccrochent plus tôt que d’habitude. Si vous commencez à afficher une durée d’appel très basse moyenne, par exemple 15 secondes, les appelants peuvent se bloquer, car votre service ne fonctionne pas correctement. 

   Dans la mesure où l’action que vous prenez peut dépendre du nombre d’appels concernés, le tableau de bord d’État du service indique le nombre d’appels analysés pour calculer un paramètre.

- **État de la connectivité TLS** -la connectivité TLS (Transport Layer Security) indique l’état des connexions TLS entre le routage direct et l’SBC. Le tableau de bord d’État analyse également la date d’expiration du certificat et vous avertit si un certificat est configuré pour expirer dans les 30 jours, de sorte que les administrateurs puissent renouveler le certificat avant que le service ne soit interrompu.

   En cliquant sur le message d’avertissement, vous pouvez afficher une description détaillée du problème dans une fenêtre contextuelle sur la droite et des recommandations pour résoudre le problème.

- **État des options SIP** : par défaut, le SBC envoie les messages d’options toutes les minutes. Cette configuration peut varier selon les différents fournisseurs de SBC. Le routage direct avertit si les options SIP ne sont pas envoyées ou ne sont pas configurées. Pour plus d’informations sur la surveillance des options SIP et sur les conditions quand un SBC peut être marqué comme ne fonctionne pas, voir [surveiller et résoudre les problèmes de routage direct](direct-routing-monitor-and-troubleshoot.md).

- **État des options SIP détaillées** -en plus de montrer qu’il y a un problème avec le flux d’options SIP, le tableau de bord d’État fournit également une description détaillée des erreurs. Vous pouvez accéder à la description en cliquant sur le message « avertissement ». Une fenêtre contextuelle à droite affiche la description détaillée de l’erreur.

   Les valeurs possibles pour les messages d’état des options SIP sont les suivantes :

    - Actif – le SBC est actif--le service de routage direct Microsoft a accès aux options de flux régulier.

    - Avertissement, aucune option SIP : le contrôleur de bordure de session existe dans la base de données (votre administrateur l’a créée à l’aide de la commande New-CsOnlinePSTNGateway). Il est configuré pour envoyer les options SIP, mais le service de routage direct n’a pas vu les options SIP en retour de cet SBC.

    - Avertissement, les messages SIP ne sont pas configurés le contrôle de Trunking avec les options SIP n’est pas activé. Le système d’appel Microsoft utilise les options SIP et la surveillance du protocole TLS (Transport Layer Security) pour détecter l’état des contrôleurs de frontière de session connectés (SBCs) au niveau de l’application. Vous rencontrez des problèmes si ce Trunk peut être atteint au niveau réseau (par ping), mais que le certificat a expiré ou si la pile SIP ne fonctionne pas. Pour vous aider à identifier ces problèmes, Microsoft recommande l’activation de l’envoi d’options SIP. Consultez la documentation fournie par le fabricant de votre SBC pour configurer l’envoi d’options SIP. 

- **Capacité d’appels simultanés** : vous pouvez spécifier la limite d’appels simultanés qu’une SBC peut gérer en utilisant la commande New-or set-CsOnlinePSTNGateway avec le paramètre-MaxConcurrentSessions. Ce paramètre calcule le nombre d’appels envoyés ou reçus par le routage direct à l’aide d’un SBC spécifique et le compare avec la limite définie. Remarque : si l’SBC gère également les appels vers différents PBX, ce numéro ne montre pas les appels simultanés réels.


## <a name="detailed-information-for-each-sbc"></a>Informations détaillées pour chaque SBC

Vous pouvez également afficher les informations détaillées d’une SBC spécifique, comme illustré dans la capture d’écran suivante :

![Détails SBC du tableau de bord d’État](media/direct-routing-dashboard-SBC-detail1.png)


L’affichage détaillé affiche les paramètres supplémentaires suivants :

- **État de la connectivité TLS** : il s’agit de la même métrique que sur la page « état global ».

- **État** de la connexion TLS : indique le temps pendant lequel l’SBC a établi une connexion TLS au service de routage direct ;

- **État des options SIP** : le même indice que sur la page « état global ».

- **Dernière vérification des options SIP** : temps de réception des options SIP pour la dernière fois.

- **État SBC** – état global de l’SBC, en fonction de tous les paramètres surveillés.

- **Appels simultanés**-indique le nombre d’appels simultanés de l’SBC géré par le SBC. Ces informations sont utiles pour prévoir le nombre de canaux simultanés dont vous avez besoin et voir la tendance. Vous pouvez faire glisser les données à l’aide du nombre de jours et de la direction de l’appel (entrant/sortant/tous les flux).

- **Paramètres réseau** -tous les paramètres réseau sont mesurés à partir de l’interface de routage directe vers le contrôleur de bordure de session. Pour plus d’informations sur les valeurs recommandées, voir [préparer le réseau de votre organisation à Microsoft teams](https://docs.microsoft.com/en-us/microsoftteams/prepare-network), et observez les valeurs recommandées par Microsoft Edge pour le client.

   - Gigue : il s’agit de la mesure de milliseconde de la variation du délai de propagation du réseau, calculée entre deux points de terminaison utilisant le protocole RTCP (protocole de contrôle RTP).

   - Perte de paquets – est une mesure de paquets qui n’ont pas pu arriver ; Il est calculé entre deux points de terminaison.

   - Latence-(également connue sous le nom de « durée de l’aller-retour) » est la durée de réception d’un signal et la durée de réception de ce signal. Ce délai se compose des temps de propagation entre les deux points d’un signal.

   Vous pouvez faire glisser les données à l’aide du nombre de jours et de la direction de l’appel (entrant/sortant/tous les flux).

**Taux d’efficacité du réseau** -il s’agit du même paramètre qui s’affiche dans le tableau de bord d’État du service, mais avec la possibilité de segmenter les données par série de temps ou direction d’appel.




