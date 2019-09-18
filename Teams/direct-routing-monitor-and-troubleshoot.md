---
title: Contrôler et dépanner le routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Cet article décrit comment surveiller et résoudre les problèmes de votre configuration de routage direct.
ms.openlocfilehash: e236a5cecb190d10082e06de24655bd722a410e5
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018822"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a>Contrôler et dépanner le routage direct

Cet article décrit comment surveiller et résoudre les problèmes de votre configuration de routage direct. 

La possibilité de passer et de recevoir des appels à l’aide du routage direct implique les composants suivants : 

- Contrôleurs de frontière de session (SBCs) 
- Composants de routage directs dans Microsoft Cloud 
- Circuits de télécoms 

Si vous éprouvez des difficultés à résoudre le problème, vous pouvez ouvrir un dossier de support auprès de votre fournisseur SBC ou Microsoft. 

Microsoft travaille actuellement à la fourniture de plus d’outils de résolution des problèmes et de surveillance. Consultez régulièrement la documentation pour les mises à jour. 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Surveiller la disponibilité des contrôleurs de bordure de session à l’aide de messages d’options SIP (Session Initiation Protocol)

Le routage direct utilise les options SIP envoyées par les contrôleurs en bordure de session pour contrôler l’intégrité des SBC. Aucune action n’est requise de la part de l’administrateur client pour activer la surveillance des options SIP. Les informations collectées sont prises en compte lors de la prise de décisions de routage. 

Par exemple, si pour un utilisateur spécifique, il existe plusieurs SBCs disponibles pour diriger un appel, le routage direct considère les informations d’options SIP reçues de chaque SBC pour déterminer le routage. 

Le schéma suivant illustre un exemple de configuration : 

![Exemple de configuration des options SIP](media/sip-options-config-example.png)

Lorsqu’un utilisateur effectue un appel vers le numéro + \<1 425 de sept chiffres>, le routage direct évalue l’itinéraire. Il existe deux éléments SBCs dans l’itinéraire : sbc1.contoso.com et sbc2.contoso.com. Les deux SBCs ont une priorité égale dans l’itinéraire. Avant de sélectionner un SBC, le mécanisme de routage évalue l’état de l’SBCs en fonction du moment où l’SBC a envoyé les options SIP pour la dernière fois. 

Un SBC est considéré comme sain si les statistiques lors de l’envoi de l’appel indiquent que le SBC envoie les options toutes les minutes.  

Lorsqu’un appel est effectué, la logique suivante s’applique :

- L’SBC a été couplé à 11:00 AM.  
- Les options d’envoi de SBC envoient à 11:01 AM, 11:02 AM, et ainsi de suite.  
- Dans 11:15, un utilisateur effectue un appel et le mécanisme de routage sélectionne cet SBC. 

Le routage direct prend les options d’intervalle normales trois fois (l’intervalle régulier est d’une minute). Si les options étaient envoyées au cours des trois dernières minutes, l’SBC est considéré comme sain.

Si l’SBC dans l’exemple a envoyé des options à n’importe quelle période entre 11:12 AM et 11:15 AM (l’heure de l’appel), il est considéré comme sain. Si ce n’est pas le cas, l’SBC sera abaissé de l’itinéraire. 

La rétrogradation signifie que l’SBC ne sera pas essayé en premier. Par exemple, nous avons sbc1.contoso.com et sbc2.contoso.com avec une priorité égale.  

Si sbc1.contoso.com n’envoie pas d’options SIP à un intervalle régulier comme décrit précédemment, il est abaissé. Ensuite, sbc2.contoso.com tente d’appeler. Si sbc2. contoso. con ne peut pas répondre à l’appel, le sbc1.contoso.com (rétrogradé) est essayé de nouveau avant la génération d’une erreur. 

Si deux (ou plusieurs) SBCs dans une même route sont considérés comme sains et égaux, Fisher-Yates est appliqué pour répartir les appels entre le SBCs.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Surveiller les journaux de tableau de bord d’analyse de la qualité des appels 
 
Dans certains cas, en particulier lors du jumelage initial, il est possible qu’il y ait des problèmes liés à la configuration du service de routage SBCs ou du service de routage direct. 

Vous pouvez utiliser les outils suivants pour contrôler votre configuration :  
 
- Tableau de bord de la qualité des appels 
- Journaux de SBC 

Le service de routage direct possède des codes d’erreur très descriptifs signalés aux analyses d’appel ou aux journaux de SBC. 

Le tableau de bord de qualité des appels fournit des informations sur la qualité et la fiabilité des appels. Pour en savoir plus sur la résolution des problèmes d’analyse des appels, reportez-vous à [activation et utilisation du tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) et [utilisation de l’analyse des appels pour résoudre les problèmes de mauvaise qualité des appels](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

En cas d’échecs d’appel, l’analyse des appels fournit des codes SIP standard pour vous aider à résoudre les problèmes. 

![Exemple de code SIP pour l’échec d’un appel](media/failed-response-code.png)

Toutefois, l’analyse des appels ne peut vous aider qu’à accéder aux composants internes du routage direct et à l’échec. En cas de problème avec le jumelage de SBC ou les problèmes liés à un rejet de « invitation » SIP (par exemple, le nom du nom de domaine complet du Trunk est mal configuré), l’analyse des appels ne vous aide pas. Dans ce cas, reportez-vous aux journaux de SBC. Le routage direct envoie une description détaillée des problèmes à l’SBCs ; ces problèmes peuvent être lus dans les journaux de SBC. 
