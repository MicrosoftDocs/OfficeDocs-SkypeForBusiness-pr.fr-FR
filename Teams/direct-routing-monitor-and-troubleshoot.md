---
title: Contrôler et dépanner le routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Cet article décrit comment analyser et résoudre les problèmes de votre configuration de routage Direct.
ms.openlocfilehash: e21d3e020f477fd1518017e0d6fc484e7ea10344
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298659"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Contrôler et dépanner le routage direct

Cet article décrit comment analyser et résoudre les problèmes de votre configuration de routage Direct. 

La possibilité d’émettre et recevoir des appels à l’aide de routage Direct implique les éléments suivants : 

- Contrôleurs de frontière de session (SBC) 
- Diriger les composants de routage dans le Cloud Microsoft 
- Jonctions de télécommunications 

Si vous avez des problèmes de la résolution des problèmes, ouvrez une demande de support avec votre fournisseur SBC ou Microsoft. 

Microsoft travaille sur plusieurs outils de dépannage et d’analyse. Consultez la documentation régulièrement des mises à jour. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Analyse de la disponibilité des contrôleurs de frontière de Session à l’aide de messages de protocole SIP (Session Initiation) Options

Routage direct utilise Options SIP envoyés par les contrôleurs de frontière de Session pour surveiller l’intégrité SBC. Il n’existe aucune action requise à partir de l’administrateur de clients pour activer la surveillance des Options SIP. Les informations collectées sont prises en considération lors des décisions de routage. 

Par exemple, si, pour un utilisateur spécifique, il existe plusieurs SBCs disponibles pour un routage des appels, routage Direct considère que les informations d’Options SIP provenance de chaque SBC pour déterminer le routage. 

Le diagramme suivant illustre un exemple de la configuration : 

![Exemple de configuration des options SIP](media/sip-options-config-example.png)

Lorsqu’un utilisateur effectue un appel vers le numéro +1 425 \<les sept digits>, routage Direct évalue l’itinéraire. Il existe deux SBCs dans l’itinéraire : sbc1.contoso.com et sbc2.contoso.com. Les deux SBCs ont une priorité équivalente dans l’itinéraire. Avant de choisir un contrôleur SBC, le mécanisme d’acheminement évalue l’intégrité des SBCs basé sur lorsque le contrôleur SBC envoyé les Options SIP heure de la dernière. 

Un contrôleur SBC est considéré comme sain si statistiques au moment de l’envoi de l’appel indique que le contrôleur SBC envoie les Options à intervalles réguliers.  

Routage direct calcule des intervalles réguliers par deux fois la moyenne lorsque le contrôleur SBC envoie des Options avant l’appel et d’ajouter les cinq minutes. 

Par exemple, supposons que les éléments suivants : 

- Un contrôleur SBC est configuré pour envoyer les Options de toutes les minutes. 
- Le contrôleur SBC a été associé à 11 h 00.  
- Le contrôleur SBC envoie options 11.01 AM, 11.02 AM, et ainsi de suite.  
- 11.15, un utilisateur effectue un appel et le mécanisme de routage sélectionne cet SBC. 

La logique suivante est appliquée : deux fois l’intervalle moyen lorsque le contrôleur SBC envoie Options (une minute plus une minute = deux minutes) plus de cinq minutes = sept minutes. Il s’agit de la valeur de l’intervalle régulier pour le contrôleur SBC.
 
Si le contrôleur SBC dans notre exemple envoyé options à tout délai entre 11 h 08 et 11 h 15 (l’heure de l’appel a été effectué), il est considéré comme sain. Si ce n’est pas le cas, le contrôleur SBC sera rétrogradé à partir de l’itinéraire. 

La rétrogradation des propriétés signifie que le contrôleur SBC ne sera pas essayé en premier. Par exemple, nous avons sbc1.contoso.com et sbc2.contoso.com avec une priorité équivalente.  

Si sbc1.contoso.com n’envoie pas les Options de SIP à intervalles réguliers comme décrit plus haut, il est rétrogradé. Ensuite, sbc2.contoso.com tente de l’appel. Si sbc2.contoso.con ne peut pas remettre l’appel, le sbc1.contoso.com (rétrogradé) est tentée de nouveau avant qu’une défaillance est générée. 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Surveiller le tableau de bord Analytique de qualité des appels et des journaux SBC 
 
Dans certains cas, en particulier pendant l’appariement initiale, il peut exister des problèmes liés à une mauvaise configuration des SBCs et/ou le service de routage Direct. 

Vous pouvez utiliser les outils suivants pour analyser votre configuration :  
 
- Tableau de bord de la qualité des appels 
- Journaux SBC 

Le service de routage Direct a des codes d’erreur descriptif très signalés Analytique appeler ou les journaux SBC. 

Le tableau de bord qualité d’appel fournit des informations sur la qualité des appels et la fiabilité. Pour savoir comment résoudre les problèmes à l’aide d’appel d’Analytique, voir [activation et à l’aide d’appels de tableau de bord qualité pour les équipes Microsoft et Skype pour Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) et [Utiliser appel Analytique pour résoudre les problèmes d’appel de mauvaise qualité](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

En cas d’échec de l’appel, Analytique appel fournit des codes SIP standard pour vous aider à résoudre. 

![Exemple de code SIP de l’échec d’appel](media/failed-response-code.png)

Toutefois, Analytique appel peuvent aider à uniquement quand les appels atteint les composants internes du routage Direct échouent. En cas de problèmes liés au jumelage SBC ou où SIP « Inviter » a été rejeté (par exemple, le nom de la jonction de que nom de domaine complet est mal configuré), appelez l’Analytique ne permettra pas. Dans ce cas, consultez les journaux SBC. Routage direct envoie une description détaillée des problèmes à le SBCs ; Ces problèmes peuvent être lus à partir des journaux SBC. 
