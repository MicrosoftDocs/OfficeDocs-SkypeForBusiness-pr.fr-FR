---
title: Surveiller les appareils Salles Microsoft Teams avec Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Cet article explique comment surveiller Salles Microsoft Teams appareils de manière intégrée à l’aide d’Azure Monitor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2f0878e7553e2d151f781c3f522a9b533b4b56d8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268969"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>Surveiller les appareils Salles Microsoft Teams avec Azure Monitor

Cet article explique comment surveiller les Salles Microsoft Teams de manière intégrée à l’aide d’Azure Monitor.

Vous pouvez configurer Azure Monitor pour fournir des données de télémétrie de base pour vous aider à surveiller les appareils des salles de réunion Microsoft Teams. Pour plus d’informations, consultez [Plan Salles Microsoft Teams management with Azure Monitor](azure-monitor-plan.md) et [Deploy Salles Microsoft Teams management with Azure Monitor](azure-monitor-deploy.md). À mesure que votre solution de supervision évolue, vous pouvez utiliser d’autres fonctionnalités de données et de surveillance pour créer une vue plus détaillée des performances des appareils.

## <a name="understand-the-log-entries"></a>Comprendre les entrées de journal

Les descriptions d’événements suivantes sont insérées dans le champ de description du journal des événements toutes les cinq minutes, lorsque l’application Salles Microsoft Teams enregistre les informations correspondantes dans le journal des événements Windows. Microsoft Monitoring Agent transmet ces enregistrements à Log Analytics dans Azure Monitor, qui les analyse dans le tableau de bord que vous avez créé dans [Déployer Salles Microsoft Teams surveillance avec Azure Monitor](azure-monitor-deploy.md). Avec le tableau de bord, vous pouvez examiner les entrées de journal individuelles pour déterminer les cours d’action si nécessaire.

Les ID d’événement 2000 et 3000 indiquent que salles Teams fonctionne comme prévu. Les ID d’événement 2001 et 3001 indiquent qu’un problème a été détecté. L’ID d’événement 4000 peut nécessiter une action si elle est observée plus souvent que prévu, par rapport à une base de référence que vous avez définie ou à d’autres appareils déployés dans votre organisation.

Comprendre ces descriptions d'événements vous permet d'être rapidement informé(e) des problèmes et de disposer d'un point de départ pour le dépannage.

| Niveau d’ID d’événement&nbsp;&nbsp;|Comportement des événements&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Description de l’événement&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Information | Il s'agit d'un événement de pulsation sain. Toutes les 5 minutes, Salles Microsoft Teams vérifie qu’il est connecté à Microsoft Teams ou à Skype Entreprise et qu’il dispose d’une connectivité réseau et Exchange. <br> Si les trois facteurs sont vrais, il écrit l’ID d’événement 2000 dans le journal des événements toutes les 5 minutes jusqu’à ce que l’appareil soit hors connexion ou qu’une ou plusieurs des conditions ne soient plus remplies. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> Dans cet exemple, toutes les conditions de pulsation ont été remplies et l’appareil Salles Microsoft Teams a été marqué comme sain. S'il y avait eu des erreurs, l'application aurait enregistré à la place l'ID d'événement 2001. |
| 2001  <br> Erreur | Il s'agit d'un événement d'erreur d'application. Toutes les 5 minutes, Salles Microsoft Teams vérifie qu’il est connecté à Microsoft Teams ou Skype Entreprise avec une connectivité réseau et Exchange. Si un ou plusieurs facteurs ne sont pas vrais, il écrit EventID 2001 dans le journal des événements toutes les 5 minutes jusqu’à ce que l’appareil soit hors connexion ou que toutes les conditions soient remplies à nouveau.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Sign in status: Unhealthy. Teams sign in status: Healthy.", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  Dans cet exemple, Salles Microsoft Teams déterminé que la connexion réseau était saine et que l’application était connectée à Exchange, mais la partie en gras indique que l’application n’est pas connectée. Il peut s'agir d'un problème de configuration au niveau de l'appareil ou de l'hôte.  <br> <br> L’état réseau s’affiche comme sain ou non sain. Si l’état n’est pas sain, il se peut que vous ayez un problème réseau ou que l’appareil ait été débranché (mais vous auriez probablement également des erreurs Exchange et Microsoft Teams ou Skype Entreprise).  <br><br> L’état Exchange est connecté ou l’un des éléments suivants : Disconnected, Connecting, AutodiscoveryError (erreur la plus courante), GeneralError ou ServerVersionNotSupported. Si l’état se connecte, attendez que le message d’intégrité suivant soit envoyé, car d’autres erreurs renvoient le problème à un administrateur ayant l’expérience de la résolution des problèmes Exchange.  <br><br>  _L’état_/ de connexion _Teams_ (indiquant que l’application est connectée à Skype Entreprise ou Teams) s’affiche comme _sain_ ou _non sain_. Si l'état est Défectueux, envoyez un technicien pour examiner le problème de plus près. |
| 3000  <br> Information | Cet événement vérifie qu’une vérification matérielle a été exécutée et qu’elle s’est avérée saine. Toutes les 5 minutes Salles Microsoft Teams vérifie que les composants matériels configurés, tels que l’écran avant de la pièce, le microphone, le haut-parleur et la caméra, sont connectés et fonctionnent. Si tous les composants sont intègres, il écrit EventID 3000 dans le journal des événements. Cet événement est écrit toutes les 5 minutes, sauf s’il existe un problème avec un appareil connecté.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> Dans cet exemple, tous les contrôles du matériel ont réussi. En cas d’erreur, l’application enregistrerait plutôt l’ID d’événement 3001. |
| 3001  <br> Événement d’erreur  | Il s'agit d'un événement d'erreur de matériel. L’application Salles Microsoft Teams a un processus qui vérifie l’intégrité des composants matériels connectés (devant de la pièce, microphone, haut-parleur, caméra) toutes les 5 minutes. Si un ou plusieurs des composants ne sont pas sains, il écrit EventID 3001 dans le journal des événements. Cet événement est écrit toutes les 5 minutes jusqu’à ce que le problème avec l’appareil soit résolu.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>   Les périphériques matériels sont indiqués comme étant sains ou défectueux.  <br> Dans cet exemple, deux écrans _de salle_ sont configurés et aucun d’entre eux n’est actuellement disponible. _L’état du microphone de conférence_ est _défectueux_, ce qui peut avoir plusieurs causes possibles. Étant donné que la dernière ressource n'a pas réussi le contrôle, l'état de celle-ci est indiqué comme étant Défectueux. Envoyez un technicien pour examiner le problème de plus près. |
| 4000  <br> Information  <br> | Il s'agit d'un événement de redémarrage de l'application. À chaque redémarrage de l'application, elle enregistre cet événement dans le journal des événements Windows.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> L’application peut redémarrer pour différentes raisons. Comparez la fréquence de redémarrage des appareils dans le même bâtiment et dans différents bâtiments. Gardez à l’esprit les problèmes connus tels que les fluctuations de puissance et les défaillances, car cela peut fournir des indices aux problèmes d’infrastructure.|

## <a name="related-topics"></a>Voir aussi
 

[Planifier la surveillance Salles Microsoft Teams avec Azure Monitor](azure-monitor-plan.md)

[Déployer Salles Microsoft Teams surveillance avec Azure Monitor](azure-monitor-deploy.md)
