---
title: Surveiller le routage direct
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
description: Découvrez comment surveiller et résoudre les problèmes de configuration du routage direct, notamment les contrôleurs de bordure de session, les composants de routage direct et les jonctions de télécommunications.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47a86e8dd98cdb86cd698b187b21453daa003b07
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657244"
---
# <a name="monitor-direct-routing"></a>Surveiller le routage direct

Cet article explique comment surveiller et résoudre les problèmes de configuration de votre routage direct. 

La possibilité d’effectuer et de recevoir des appels à l’aide du routage direct implique les composants suivants : 

- Contrôleurs de frontière de session (SBC) 
- Composants de routage direct dans le cloud Microsoft 
- Jonctions de télécommunications 

Si vous rencontrez des difficultés pour résoudre les problèmes, vous pouvez ouvrir un cas de support auprès de votre fournisseur SBC ou de Microsoft. 

Microsoft travaille à fournir d’autres outils pour la résolution des problèmes et la surveillance. Consultez régulièrement la documentation pour connaître les mises à jour. 

## <a name="troubleshoot-direct-routing"></a>Résoudre les problèmes de routage direct

Pour résoudre les problèmes de routage direct, consultez [Diagnostiquer les problèmes liés au routage direct](/MicrosoftTeams/troubleshoot/phone-system/direct-routing/diagnose-direct-routing-issues).

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a>Surveillance de la disponibilité des contrôleurs de bordure de session à l’aide des messages d’options SIP (Session Initiation Protocol)

Le routage direct utilise les options SIP envoyées par les contrôleurs de bordure de session pour surveiller l’intégrité de SBC. Aucune action n’est requise de la part de l’administrateur client pour activer la surveillance des options SIP. Les informations collectées sont prises en compte lors des décisions de routage. 

Par exemple, si, pour un utilisateur spécifique, plusieurs SBC sont disponibles pour acheminer un appel, le routage direct prend en compte les informations d’options SIP reçues de chaque SBC pour déterminer le routage. 

Le diagramme suivant montre un exemple de configuration : 

![Exemple de configuration des options SIP.](media/sip-options-config-example.png)

Lorsqu’un utilisateur effectue un appel au numéro +1 425 \<any seven digits>, le routage direct évalue l’itinéraire. Il y a deux SBC dans l’itinéraire : sbc1.contoso.com et sbc2.contoso.com. Les deux SBC ont une priorité égale dans l’itinéraire. Avant de choisir un SBC, le mécanisme de routage évalue l’intégrité des SBC en fonction du moment où le SBC a envoyé les options SIP la dernière fois. 

Un SBC est considéré comme sain si les statistiques au moment de l’envoi de l’appel indiquent que le SBC envoie des options toutes les minutes.  

Lorsqu’un appel est effectué, la logique suivante s’applique :

- Le SBC a été appairé à 11h00.  
- Le SBC envoie les options à 11h01, 11h02, et ainsi de suite.  
- À 11:15, un utilisateur effectue un appel et le mécanisme de routage sélectionne ce SBC. 

Le routage direct prend les options d’intervalles réguliers trois fois (l’intervalle régulier est d’une minute). Si des options ont été envoyées au cours des trois dernières minutes, le SBC est considéré comme sain.

Si le SBC dans l’exemple a envoyé des options à une période comprise entre 11h12 et 11h15 (heure à laquelle l’appel a été effectué), il est considéré comme sain. Si ce n’est pas le cas, le SBC est rétrogradé à partir de l’itinéraire. 

La rétrogradation signifie que le SBC ne sera pas essayé en premier. Par exemple, nous avons sbc1.contoso.com et sbc2.contoso.com avec une priorité égale.  

Si sbc1.contoso.com n’envoie pas d’options SIP à intervalles réguliers comme décrit précédemment, elle est rétrogradée. Ensuite, sbc2.contoso.com tente l’appel. Si sbc2.contoso.con ne peut pas remettre l’appel, le sbc1.contoso.com (rétrogradé) est réessayé avant qu’un échec ne soit généré. 

Si deux (ou plusieurs) SBC dans un itinéraire sont considérés comme sains et égaux, Fisher-Yates shuffle est appliqué pour distribuer les appels entre les SBC.

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a>Surveiller le tableau de bord Analyse de la qualité des appels et les journaux SBC 
 
Dans certains cas, en particulier pendant le jumelage initial, il peut y avoir des problèmes liés à une configuration incorrecte des SBC ou du service de routage direct. 

Vous pouvez utiliser les outils suivants pour surveiller votre configuration :  
 
- Tableau de bord de la qualité des appels 
- Journaux SBC 

Le service de routage direct contient des codes d’erreur descriptifs signalés à Call Analytics ou aux journaux SBC.

Le tableau de bord qualité des appels fournit des informations sur la qualité et la fiabilité des appels. Pour en savoir plus sur la résolution des problèmes à l’aide d’Call Analytics, consultez [Activer et utiliser le tableau de bord de qualité des appels pour Microsoft Teams et Skype Entreprise Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) et [Utiliser Call Analytics pour résoudre les problèmes de qualité des appels](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality). 

En cas d’échec d’appel, Call Analytics fournit des codes SIP standard pour vous aider à résoudre les problèmes. 

![Exemple de code SIP pour l’échec d’appel.](media/failed-response-code.png)

Toutefois, l’analytique des appels ne peut être utile que lorsque les appels atteignent les composants internes du routage direct et échouent. En cas de problèmes liés au jumelage SBC ou de problèmes où SIP « Invite » a été rejeté (par exemple, le nom du nom de domaine complet de jonction est mal configuré), Call Analytics n’aide pas. Dans ce cas, reportez-vous aux journaux SBC. Le routage direct envoie une description détaillée des problèmes aux SBC ; ces problèmes peuvent être lus à partir des journaux SBC.
