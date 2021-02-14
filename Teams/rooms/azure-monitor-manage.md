---
title: Gérer les appareils salles Microsoft Teams avec Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: Cet article explique comment gérer les appareils des salles Microsoft Teams de manière intégrée à l’aide d’Azure Monitor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16105e77c8e66afa00f089d1337984b7e7d9a502
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662049"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Gérer les appareils salles Microsoft Teams avec Azure Monitor

Cet article explique comment gérer les appareils des salles Microsoft Teams de manière intégrée à l’aide d’Azure Monitor.

Vous pouvez configurer un moniteur Azure pour fournir la télémétrie de base afin de vous aider à gérer les appareils des salles de réunion Skype. Pour [plus d’informations,](azure-monitor-plan.md) consultez la gestion des salles Microsoft Teams avec Azure Monitor et déployez la gestion des salles Microsoft Teams avec [Azure Monitor.](azure-monitor-deploy.md) À mesure que votre solution de gestion arrive à échéance, vous pouvez utiliser des fonctionnalités de gestion et de données supplémentaires pour créer une vue plus détaillée des performances des appareils.

## <a name="understand-the-log-entries"></a>Comprendre les entrées de journal

Les descriptions d’événement suivantes sont insérées dans le champ de description du journal des événements toutes les cinq minutes, lorsque l’application Salles Microsoft Teams enregistre les informations correspondantes dans le journal des événements Windows. L’Agent de surveillance Microsoft transmet ces enregistrements aux données d’analyse journal dans Azure Monitor, qui les analyse dans le tableau de bord que vous avez créé dans la gestion des salles Microsoft Teams avec [Azure Monitor.](azure-monitor-deploy.md) Le tableau de bord vous permet d’examiner les entrées de journal individuelles afin de déterminer les mesures à prendre si nécessaire.

Les ID d’événement 2000 et 3000 indiquent que l’appareil en question fonctionne comme prévu. Les ID d’événement 2001 et 3001 indiquent qu’un problème a été trouvé. L’ID d’événement 4000 peut nécessiter une action plus souvent que prévu, par rapport à un point de comparaison que vous avez créé ou à d’autres appareils déployés dans votre organisation.

Comprendre ces descriptions d'événements vous permet d'être rapidement informé(e) des problèmes et de disposer d'un point de départ pour le dépannage.

| Niveau &nbsp; d’ID &nbsp; d’événement|Comportement des &nbsp; événements&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Description de &nbsp; l’événement&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Information | Il s'agit d'un événement de pulsation sain. Toutes les 5 minutes, les salles Microsoft Teams vérifient qu’elles sont bien inscrites à Microsoft Teams ou à Skype Entreprise et qu’elles disposent d’une connectivité réseau et Exchange. <br> Si les 3 facteurs sont vrais, il écrit l’ID d’événement 2000 dans le journal des événements toutes les 5 minutes jusqu’à ce que l’appareil soit hors connexion ou qu’une ou plusieurs des conditions ne soient plus remplies. | {"Description »:"Heartbeat is healthy. », « ResourceState »:"Healthy », « OperationName »:"Heartbeat », « OperationResult »:"Pass », « OS »:"Windows 10 », « OSVersion »:"10.0.14393.693 », « Alias »:"alias <span></span> @contoso.com », « DisplayName »:"Display Name », « AppVersion »:"1.0.38.0 », « IPv4Address »:"10.10.10.10 », « IPv6Address »:"IP v6 address"} <br><br> Dans cet exemple, toutes les conditions de pulsation ont été remplies et l’appareil Salles Microsoft Teams a été marqué comme sain. S'il y avait eu des erreurs, l'application aurait enregistré à la place l'ID d'événement 2001. |
| 2001  <br> Erreur | Il s'agit d'un événement d'erreur d'application. Toutes les 5 minutes, les salles Microsoft Teams vérifient qu’elles sont bien signées avec Microsoft Teams ou Skype Entreprise avec la connectivité réseau et Exchange. Si un ou plusieurs facteurs ne sont pas vrais, EventID 2001 est écrit dans le journal des événements toutes les 5 minutes jusqu’à ce que l’appareil soit hors connexion ou que toutes les conditions soient remplies à nouveau.  | {"Description" :"Network status : Healthy. Exchange status : Connected. **Signin status: Unhealthy.** « , « ResourceState »:"Unhealthy », « OperationName »:"Heartbeat », « OperationResult »:"Fail », « OS »:"Windows 10 », « OSVersion »:"10.0.14393.693 », « Alias »: », « DisplayName »:"Display Name », « AppVersion »:"1.0.38.0 », « IPv4Address »:"10.10.10.10 », « IPv6Address »:"ip v6 address"} <br><br>  Dans cet exemple, les salles Microsoft Teams ont déterminé que la connexion réseau était saine et que l’application était connectée à Exchange, mais que la partie en gras indique que l’application n’est pas connectée. Il peut s'agir d'un problème de configuration au niveau de l'appareil ou de l'hôte.  <br> <br> L’état du réseau est sain ou défectueux. Si l’état n’est pas bon, il se peut que vous subissiez un problème réseau ou que l’appareil soit branché (mais il est probable que vous deiez également avoir des erreurs d’Exchange et de Microsoft Teams ou de Skype Entreprise).  <br><br> L’état Exchange indique soit Connecté, soit l’une des informations suivantes : Déconnecté, Connexion, Découverte automatiqueErreur (l’erreur la plus fréquemment vue), GeneralError ou ServerVersionNotSupported. Si l’état se connecte, patientez jusqu’à ce que le message d’état suivant soit envoyé. Les autres erreurs renvoient le problème à un administrateur ayant de l’expérience en matière de résolution des problèmes Exchange.  <br><br>  L’état de la connectez-vous (indiquant que l’application est signée) est sain ou défectueux. Si l'état est Défectueux, envoyez un technicien pour examiner le problème de plus près. |
| 3000  <br> Information | Cet événement vérifie qu’une vérification matérielle a été vérifiée et s’est trouvée saine. Toutes les 5 minutes Les salles Microsoft Teams vérifient que les composants matériels configurés tels que l’affichage avant de la salle, le microphone, le haut-parleur et la caméra sont connectés et fonctionnels. Si tous les composants sont sains, il écrit EventID 3000 dans le journal des événements. Cet événement est écrit toutes les 5 minutes, sauf s’il existe un problème avec un appareil connecté.  <br> | {"Description »:"HardwareCheckEngine is healthy », « ResourceState »:"Healthy », « OperationName »:"HardwareCheckEngine », « OperationResult »:"Pass », « OS »:"Windows 10 », « OSVersion »:"10.0.14393.693 », « Alias »:"alias <span></span> @contoso.com », « DisplayName »:"Display Name », « AppVersion »:"1.0.38.0 », « IPv4Address »:"10.10.10.10 », « IPv6Address »:"ip v6 address"}  <br><br> Dans cet exemple, tous les contrôles du matériel ont réussi. En cas d’erreur, l’application enregistre à la place l’ID d’événement 3001. |
| 3001  <br> Événement d’erreur  | Il s'agit d'un événement d'erreur de matériel. L’application Salles Microsoft Teams dispose d’un processus qui vérifie l’intégrité des composants matériels connectés (avant la salle, micro, haut-parleur, caméra) toutes les 5 minutes. Si un ou plusieurs des composants ne sont pas défectueux, eventID 3001 est écrit dans le journal des événements. Cet événement est écrit toutes les 5 minutes jusqu’à ce que le problème avec l’appareil soit résolu.   | {"Description »: » **État d’affichage avant de la salle : défectueux.** Configured display count is 2. Real display count is 0. **Conference Microphone status : Unhealthy.** Conference Speaker status : Healthy. Default Speaker status : Healthy. État de la caméra : Bon état . » , « ÉtatRe resource » :« Défectueux », « OperationName » :"HardwareCheckEngine », « OperationResult »:"Fail », « OS »:"Windows 10 », « OSVersion »:"10.0.14393.1198 », « Alias »:"alias <span></span> @contoso.com », « DisplayName »:"Yosemite conference room », « AppVersion »:"2.0.58.0 », « IPv4Address »:"10.10.10.10 », « IPv6Address »:"IPv6Address », « IPv4Address2 »:"10.10.10.10"} <br><br>  Les périphériques matériels sont indiqués comme étant sains ou défectueux. <br> Dans cet exemple, deux écrans à l'avant de la salle sont connectés et aucun des deux n'est disponible actuellement. L’état du microphone de conférence est défectueux, ce qui peut avoir plusieurs causes possibles. Étant donné que la dernière ressource n'a pas réussi le contrôle, l'état de celle-ci est indiqué comme étant Défectueux. Envoyez un technicien pour examiner le problème de plus près. |
| 4000  <br> Information  <br> | Il s'agit d'un événement de redémarrage de l'application. À chaque redémarrage de l'application, elle enregistre cet événement dans le journal des événements Windows.  <br> | {"Description »:"App restarts », « ResourceState »:"Healthy », « OperationName »:"Restart », « OperationResult »:"Pass », « OS »:"Windows 10 », « OSVersion »:"10.0.14393.693 », « Alias »:"alias <span></span> @domain.com », « DisplayName »:"Display Name », « AppVersion »:"1.0.38.0 », « IPv4Address »:"10.10.10.10 », « IPv6Address »:"ip v6 address"} <br><br> Le redémarrage de l’application peut être pour diverses raisons. Comparez la fréquence de redémarrage des appareils situés dans le même bâtiment et dans des bâtiments différents. Gardez à l’esprit les problèmes connus tels que les fluctuations de puissance et les échecs, car cela peut fournir des indices sur les problèmes d’infrastructure.|

## <a name="related-topics"></a>Sujets associés
 

[Planifier la gestion des salles Microsoft Teams à l’aide d’Azure Monitor](azure-monitor-plan.md)

[Déployer la gestion des salles Microsoft Teams avec Azure Monitor](azure-monitor-deploy.md)
