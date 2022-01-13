---
title: Surveiller des Salles Microsoft Teams appareils avec un moniteur Azure
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
description: Cet article explique comment surveiller Salles Microsoft Teams appareils de façon intégrée à l’aide d’Azure Monitor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c4d1a31946ed825ba89407fab4cf55b4460a30c6
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015024"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>Surveiller des Salles Microsoft Teams appareils avec un moniteur Azure

Cet article explique comment surveiller les Salles Microsoft Teams d’une manière intégrée à l’aide d’Azure Monitor.

Vous pouvez configurer un moniteur Azure pour fournir des données de télémétrie de base afin de vous aider à surveiller Microsoft Teams appareils des salles de réunion. Pour [plus d’Salles Microsoft Teams, consultez](azure-monitor-plan.md) La gestion des Salles Microsoft Teams de projet avec azure Monitor et Déployer Salles Microsoft Teams gestion des ressources avec [Azure Monitor.](azure-monitor-deploy.md) À mesure que votre solution de surveillance mature, vous pouvez utiliser des données supplémentaires et des fonctionnalités de surveillance pour créer une vue plus détaillée des performances de l’appareil.

## <a name="understand-the-log-entries"></a>Comprendre les entrées de journal

Les descriptions d’événement suivantes sont insérées dans le champ de description du journal des événements toutes les cinq minutes, lorsque l’application Salles Microsoft Teams enregistre les informations correspondantes dans le Windows événement. Le Microsoft Monitoring Agent passe ces enregistrements à l’analyse journal dans Azure Monitor, qui les analyse dans le tableau de bord que vous avez créé dans Déployer Salles Microsoft Teams surveillance avec [Azure Monitor.](azure-monitor-deploy.md) Le tableau de bord vous permet d’examiner les entrées de journal individuelles afin de déterminer les mesures à prendre si nécessaire.

Les ID d’événement 2000 et 3000 indiquent que le salles Teams fonctionne comme prévu. Les ID d’événement 2001 et 3001 indiquent qu’un problème a été trouvé. L’ID d’événement 4000 peut nécessiter une action plus souvent que prévu, par rapport à un point de comparaison que vous avez créé ou à d’autres appareils déployés dans votre organisation.

Comprendre ces descriptions d'événements vous permet d'être rapidement informé(e) des problèmes et de disposer d'un point de départ pour le dépannage.

| Niveau &nbsp; d’ID &nbsp; d’événement|Comportement des &nbsp; événements&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Description de &nbsp; l’événement&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Information | Il s'agit d'un événement de pulsation sain. Toutes les 5 minutes, Salles Microsoft Teams vérifie qu’il est Microsoft Teams ou Skype Entreprise et qu’il dispose d’Exchange réseau. <br> Si les 3 facteurs sont vrais, il écrit l’ID d’événement 2000 dans le journal des événements toutes les 5 minutes jusqu’à ce que l’appareil soit hors connexion ou qu’une ou plusieurs des conditions ne soient plus remplies. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> Dans cet exemple, toutes les conditions de pulsation ont été remplies et Salles Microsoft Teams appareil a été marqué comme sain. S'il y avait eu des erreurs, l'application aurait enregistré à la place l'ID d'événement 2001. |
| 2001  <br> Erreur | Il s'agit d'un événement d'erreur d'application. Toutes les 5 minutes, Salles Microsoft Teams vérifie qu’il est bien Microsoft Teams ou Skype Entreprise connexion avec le réseau et Exchange connexion. Si un ou plusieurs facteurs ne sont pas vrais, EventID 2001 est écrit dans le journal des événements toutes les 5 minutes jusqu’à ce que l’appareil soit hors connexion ou que toutes les conditions soient remplies à nouveau.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. ", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  Dans cet exemple, Salles Microsoft Teams a déterminé que la connexion réseau était saine et que l’application était connectée à Exchange, mais que la partie en gras indique que l’application n’est pas connectée. Il peut s'agir d'un problème de configuration au niveau de l'appareil ou de l'hôte.  <br> <br> L’état du réseau est sain ou défectueux. Si l’état n’est pas saine, il se peut que vous subissiez un problème réseau ou que l’appareil soit branché (mais il est probable que vous Exchange des erreurs Microsoft Teams et Skype Entreprise données).  <br><br> L’état Exchange indique soit Connecté, soit l’un des statuts suivants : Déconnecté, Connexion, AutodiscoveryError (l’erreur la plus fréquemment vue), GeneralError ou ServerVersionNotSupported. Si l’état se connecte, patientez jusqu’à ce que le message d’état d’santé suivant soit envoyé. Les autres erreurs renvoient le problème à un administrateur ayant de l’expérience en matière de résolution Exchange problèmes.  <br><br>  _L’état de la_ connectez-vous (indiquant que  l’application est signée) est sain _ou défectueux._ Si l'état est Défectueux, envoyez un technicien pour examiner le problème de plus près. |
| 3000  <br> Information | Cet événement vérifie qu’une vérification matérielle a été vérifiée et s’est trouvée saine. Toutes les 5 minutes Salles Microsoft Teams vérifie que les composants matériels configurés tels que l’affichage avant de la pièce, le microphone, le haut-parleur et la caméra sont connectés et fonctionnels. Si tous les composants sont sains, il écrit EventID 3000 dans le journal des événements. Cet événement est écrit toutes les 5 minutes, sauf s’il existe un problème avec un appareil connecté.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> Dans cet exemple, tous les contrôles du matériel ont réussi. En cas d’erreur, l’application enregistre à la place l’ID d’événement 3001. |
| 3001  <br> Événement d’erreur  | Il s'agit d'un événement d'erreur de matériel. L Salles Microsoft Teams’application dispose d’un processus qui vérifie l’intégrité des composants matériels connectés (avant la pièce, micro, haut-parleur, caméra) toutes les 5 minutes. Si un ou plusieurs des composants ne sont pas défectueux, eventID 3001 est écrit dans le journal des événements. Cet événement est écrit toutes les 5 minutes jusqu’à ce que le problème avec l’appareil soit résolu.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>   Les périphériques matériels sont indiqués comme étant sains ou défectueux.  <br> Dans cet exemple,  deux affichages avant de salle sont configurés et aucun d’eux n’est disponible actuellement. _L’état du microphone_ de conférence est _défectueux,_ ce qui peut avoir plusieurs causes possibles. Étant donné que la dernière ressource n'a pas réussi le contrôle, l'état de celle-ci est indiqué comme étant Défectueux. Envoyez un technicien pour examiner le problème de plus près. |
| 4000  <br> Information  <br> | Il s'agit d'un événement de redémarrage de l'application. À chaque redémarrage de l'application, elle enregistre cet événement dans le journal des événements Windows.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> Le redémarrage de l’application peut être pour diverses raisons. Comparez la fréquence de redémarrage des appareils situés dans le même bâtiment et dans des bâtiments différents. Gardez à l’esprit les problèmes connus tels que les fluctuations de puissance et les échecs, car cela peut fournir des indices sur les problèmes d’infrastructure.|

## <a name="related-topics"></a>Sujets associés
 

[Planifier l’Salles Microsoft Teams de l’analyse des données à l’aide d’Azure Monitor](azure-monitor-plan.md)

[Déployer l Salles Microsoft Teams de surveillance des données à l’Salles Microsoft Teams’Azure Monitor](azure-monitor-deploy.md)
