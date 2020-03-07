---
title: Utilisation du rapport de routage direct RTC bord
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Utilisez le rapport de routage direct RTC bord pour surveiller et résoudre les problèmes de la fonction d’appel RTC dans Microsoft Teams.
ms.openlocfilehash: 32d91d56e51c5706c3e460029312f3b6bb6948c3
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559421"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Utilisation du rapport de routage direct RTC bord

Nouveauté du 2020 mars, nous avons ajouté un rapport de routage direct RTC bord aux [modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 


Le rapport de routage direct RTC de bord aide les clients à comprendre les modèles d’utilisation et la qualité de leurs services RTC surveiller les informations relatives à votre SBC, au service de téléphonie, aux paramètres réseau et aux détails sur le taux d’efficacité du réseau et à l’utilisation de la fonction service. Ces informations peuvent vous aider à identifier les problèmes, notamment le motif des appels interrompus. Par exemple, vous serez en mesure de déterminer le nombre de chutes d’appels en fonction de la raison pour laquelle vous en avez le volume.

Le rapport de routage direct RTC de bord comporte quatre sections :

  - [Présentation RTC](#pstn-overview)

  - [Détails du service](#service-details)

  - [Taux d’efficacité du réseau](#network-effectiveness-ratio)

  - [Paramètres réseau](#network-parameters)

## <a name="pstn-overview"></a>Présentation RTC

Le rapport de routage direct RTC bord fournit les informations suivantes relatives à l’intégrité globale du service au cours des derniers jours 180.
![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report1.png)

Par exemple, si vous êtes intéressé par l’utilisation globale et l’intégrité de tous les appels entrants à l’aide de SBC abc.bca.adatum.biz en tant que pays interne :

| **Appel hors** | **Description**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Vous pouvez utiliser les filtres en haut pour descendre dans la direction et sélectionner ByotIn en tant que type d’appel, abc.bca.contoso.com en tant que contrôleur de tableau de bord, et vers les États-Unis comme pays interne. |
| deuxième            | Tendance d’utilisation pour les 180 derniers jours. Le rapport sur les détails d’utilisation est sur la page des détails du service.                                                                     |
| 3            | Envoyez un message de délai de numérotation, de latence, de gigue et de tendance de perte de paquets pour les 180 derniers jours. Vous trouverez le rapport détaillé sur la page Paramètres du réseau.                           |
| 4            | Tendance pour les appels simultanés et les utilisateurs actifs du jour au cours des 180 derniers jours. Ce graphique peut vous aider à comprendre le volume maximal du service.                            |
| 5            | Raison de la qualité de service affectée par le top des appels pour les 180 derniers jours. Pour plus d’informations sur l’état du service, consultez la page NER (Network effective ratio).                    |

## <a name="service-details"></a>Détails du service

Cette page vous permet d’obtenir des tendances d’utilisation du service par jour et de décomposition des commentaires des utilisateurs par géographie.

  - **Nombre total de tentatives d’appels –** Nombre total de tentatives d’appels dans cette plage de temps, y compris les appels réussis et failed

  - **Nombre total d’appels connectés** Nombre total d’appels connectés dans cet intervalle de temps

  - **Nombre total de minutes –** Utilisation du total des minutes dans cet intervalle de temps

  - **Utilisateurs actifs quotidiens (DAU) :** Nombre d’utilisateurs actifs du jour qui ont effectué au moins un appel connecté à ce jour

  - **Appels simultanés –** Maximum d’appels actifs simultanés en une minute

  - **Commentaires des utilisateurs –** Le score « évaluer mon appel » est fourni par l’utilisateur. 3-5 est considéré comme un bon appel. 1-2 est considéré comme un appel incorrect.

![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report2.png)

Par exemple :

1.  Si vous voyez que la durée moyenne des appels tombe à 0 sur 02/14/2020, vous pouvez commencer par vérifier si le volume de l’appel est normal et voir s’il y a une différence importante entre les appels de connexion et les appels de connexion au total. Puis accédez à la page taux d’efficience du réseau pour investir en raison de l’échec de l’appel.

2.  Si vous voyez l’augmentation du nombre de points rouges sur la carte de commentaires des utilisateurs, vous pouvez accéder à page du rapport d’efficacité réseau et au paramètre réseau pour voir s’il y a des anomalies et vous pouvez déclencher un ticket avec MS Service Desk.

## <a name="network-effectiveness-ratio"></a>Taux d’efficacité du réseau

Il s’agit de la même métrique qui s’affiche dans le tableau de bord global de l’État. Vous pouvez vérifier le numéro NER en fonction des appels en fonction du nombre d’appels (entrant/sortant) sur le taux d’efficacité du réseau horaire et sur le graphique raison de fin de l’appel ci-dessous.

  - **Ner** -la capacité (%) un réseau pour transmettre les appels en mesurant le nombre d’appels envoyés au destinataire.

  - **Code de réponse SIP**: un code de réponse numérique à trois chiffres affiche l’état de l’appel.

  - **Code de réponse Microsoft**: code de réponse envoyé par le composant Microsoft.

  - **Description** : la phase de raison correspondant au code de réponse SIP et au code de réponse Microsoft.

  - **Nombre d’appels concernés** : le nombre total d’appels a été affecté au cours de la période sélectionnée.

> ![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report3.png)
> 
Par exemple :

![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report4.png)

Si la NER quotidienne a une DIP sur 02/05/2020, vous pouvez cliquer sur la date et d’autres graphiques pour effectuer un zoom sur la date spécifique.

![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report5.png)

À partir du NER, vous pouvez trouver le DIP qui intervient dans 21:00. Cliquez de nouveau sur pour effectuer un zoom à l’heure 21, puis cochez la case Afficher les détails de l’appel pour voir le nombre d’appels ayant échoué pendant cette heure et les raisons de fin de l’appel. Si le problème n’est pas lié à SBC, vous pouvez démarrer avec l’auto-dépannage des problèmes de SBC ou d’État du service d’assistance technique.

## <a name="network-parameters"></a>Paramètres réseau

Tous les paramètres réseau sont mesurés à partir de l’interface de routage directe vers le contrôleur de bordure de session. Pour plus d’informations sur les valeurs recommandées, voir [préparer le réseau de votre organisation à Microsoft teams](prepare-network.md), et observez les valeurs recommandées par Microsoft Edge pour le client.

  - **Gigue** : il s’agit de la mesure de milliseconde de la variation du délai de propagation du réseau, calculée entre deux points de terminaison utilisant le protocole RTCP (protocole de contrôle RTP).

  - **Perte de paquets** – est une mesure de paquets qui n’ont pas pu arriver ; Il est calculé entre deux points de terminaison.

  - **Latence** -(également connue sous le nom de « durée de l’aller-retour) » est la durée de réception d’un signal et la durée de réception de ce signal. Ce délai se compose des temps de propagation entre les deux points d’un signal.

> ![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report6.png)

Par exemple :

Si vous voyez un pique-notes sur l’un des quatre graphiques (latence, instabilité, taux de perte de package, délai de numérotation après appel) pour une date spécifique (par exemple, latence sur 02/14/2020, cliquez sur le point de la date). Le graphique tendance en bas de la série est actualisé pour afficher le numéro horaire. Vous pouvez vérifier l’SBCs ou élever un ticket avec MS Service Desk.

![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Sujets associés

[Utiliser Power BI pour analyser des données bord pour Microsoft teams](CQD-PSTN-report.md)