---
title: Contrôler et dépanner le routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment surveiller et résoudre les problèmes de configuration du routage direct, notamment les contrôleurs de bordure de session, les composants de routage direct et les ligne de télécommunications.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aeff22bf3558c64111f0d1b66c2fd76288f81477
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726883"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Contrôler et dépanner le routage direct

Cet article explique comment surveiller et dépanner votre configuration de routage direct. 

La possibilité d’effectuer et de recevoir des appels à l’aide du routage direct implique les composants suivants : 

- Contrôleurs de session en bordure 
- Composants de routage direct dans Microsoft Cloud 
- Telecom trunks 

Si vous avez des difficultés à résoudre des problèmes, vous pouvez ouvrir un cas de support auprès de votre fournisseur SBC ou de Microsoft. 

Microsoft travaille à la fourniture d’autres outils pour la résolution des problèmes et la surveillance. Consultez régulièrement la documentation pour les mises à jour. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Surveillance de la disponibilité des contrôleurs de session en bordure à l’aide des messages d’options SIP (Session Initiation Protocol)

Le routage direct utilise les options SIP envoyées par les contrôleurs de session border pour surveiller l’état du SBC. Aucune action n’est requise de la part de l’administrateur client pour activer la surveillance des options SIP. Les informations collectées sont prises en compte lors des décisions de routage. 

Par exemple, si, pour un utilisateur spécifique, plusieurs SBC sont disponibles pour router un appel, le routage direct examine les informations d’options SIP reçues de chaque SBC pour déterminer le routage. 

Le diagramme suivant montre un exemple de configuration : 

![Exemple de configuration des options SIP.](media/sip-options-config-example.png)

Lorsqu’un utilisateur appelle le numéro +1 425, le \<any seven digits> routage direct évalue l’itinéraire. Il existe deux SBCS dans l’itinéraire : sbc1.contoso.com et sbc2.contoso.com. Les deux SBCS ont la même priorité dans l’itinéraire. Avant de choisir un SBC, le mécanisme de routage évalue l’état des SBC en fonction de la dernière fois que le SBC a envoyé les options SIP. 

Un SBC est considéré comme sain si les statistiques au moment de l’envoi de l’appel indiquent que le SBC envoie des options toutes les minutes.  

Lorsqu’un appel est effectué, la logique suivante s’applique :

- Le SBC a été couplé à 11:00.  
- Le SBC envoie des options à 11:01, 11:02, etc.  
- À 23:15, un utilisateur effectue un appel et le mécanisme de routage sélectionne ce SBC. 

Le routage direct prend les options d’intervalle régulier trois fois (l’intervalle régulier est d’une minute). Si des options ont été envoyés au cours des trois dernières minutes, le SBC est considéré comme étant sain.

Si la donnée SBC de l’exemple a été envoyée à n’importe quel moment entre 11:12 et 11:15 (heure à l’heure de l’appel), elle est considérée comme saine. Si ce n’est pas le cas, le SBC est rétrogradé de l’itinéraire. 

Demotion signifie que le SBC ne sera pas tenté en premier. Par exemple, nous avons des sbc1.contoso.com et sbc2.contoso.com priorité égale.  

Si sbc1.contoso.com n’envoie pas les options SIP à intervalles réguliers comme décrit précédemment, elle est rétrogradée. Ensuite, sbc2.contoso.com pour l’appel. Si sbc2.contoso.con ne peut pas donner l’appel, l’sbc1.contoso.com (rétrogradé) fait l’appel à nouveau avant qu’un échec ne soit généré. 

Si deux (ou plusieurs) SBCs dans un même itinéraire sont considérés comme sains et égaux, un mélange Fisher-Yates est appliqué pour distribuer les appels entre les SBCs.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Surveiller le tableau de bord d’analyse de la qualité des appels et les journaux SBC 
 
Dans certains cas, en particulier lors du coupage initial, des problèmes peuvent se trouver liés à une configuration mal configurée des SCS ou du service de routage direct. 

Vous pouvez utiliser les outils suivants pour surveiller votre configuration :  
 
- Tableau de bord de la qualité des appels 
- Journaux SBC 

Les codes d’erreur très descriptifs du service de routage direct sont signalés aux journaux d’analyse des appels ou SBC. 

Le tableau de bord de qualité des appels fournit des informations sur la qualité et la fiabilité des appels. Pour en savoir plus sur la résolution des problèmes à l’aide de l’analyse des appels, voir Mise en place et utilisation du tableau de bord de qualité des appels pour Microsoft Teams et [Skype Entreprise Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) et Utiliser l’analyse des appels pour résoudre les problèmes de qualité des [appels.](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) 

En cas d’échec d’appel, l’analyse des appels fournit des codes SIP standard pour vous aider à résoudre les problèmes. 

![Exemple de code SIP pour l’échec de l’appel.](media/failed-response-code.png)

Toutefois, l’analyse des appels ne peut être utile que lorsque les appels atteignent les composants internes du routage direct et échouent. En cas de problèmes de jumelage SBC ou de problèmes de rejet de l’invitation siP (par exemple, le nom de la ligne de nom de domaine complet n’est pas configuré de façon configurée), l’analyse des appels n’est pas utile. Dans ce cas, consultez les journaux SBC. Le routage direct envoie une description détaillée des problèmes aux SCS. ces problèmes peuvent être lus à partir des journaux SBC.