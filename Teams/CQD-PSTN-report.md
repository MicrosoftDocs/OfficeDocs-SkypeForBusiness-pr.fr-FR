---
title: Utilisation du rapport de routage direct rtc CQD
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Utilisez le rapport de routage direct rtc (CQD) du tableau de bord de qualité des appels Microsoft Teams pour surveiller et résoudre les problèmes liés aux appels RTC dans Microsoft Teams.
ms.openlocfilehash: 8d6e971adc3cd7e4ec9b4038356e744d4451146f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789889"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Utilisation du rapport de routage direct rtc CQD

Nouveau en mars 2020, nous avons ajouté un rapport de routage direct RTC (Call Quality Dashboard) Microsoft Teams à nos [modèles de requête Power BI téléchargeables pour CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 


Le rapport de routage direct RTC CQD (CQD PSTN Direct Routing Report.pbit) vous aide à comprendre les modèles d’utilisation et la qualité de vos services RTC. Utilisez ce rapport pour surveiller l’utilisation du service, les informations sur votre contrôleur de frontière de session (SBC), le service de téléphonie, les paramètres réseau et les détails du ratio d’efficacité réseau. Ces informations peuvent vous aider à identifier les problèmes, y compris la raison des appels supprimés. Par exemple, vous serez en mesure de voir quand le volume diminue, ou combien d’appels sont affectés et pour quelle raison.


Le rapport de routage direct rtc CQD comporte quatre sections :

  - [Vue d’ensemble de PSTN](#pstn-overview)

  - [Détails du service](#service-details)

  - [Ratio d’efficacité du réseau](#network-effectiveness-ratio)

  - [Paramètres réseau](#network-parameters)

## <a name="highlights"></a>Faits saillants

1. Analyser par type d’appel, SBC, appelant et pays d’appelé

   Le rapport de routage direct RTC CQD agrège les métriques de fiabilité et d’utilisation de tous les SBC sur votre locataire au cours des 7, 30 ou 180 derniers jours (6 mois). Vous pouvez analyser les données par type d’appel, SBC, appelant et pays d’appel. Si vous êtes intéressé par un SBC ou un pays particulier, vous serez en mesure d’identifier les changements de tendances sur l’intervalle de temps sélectionné.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Capture d’écran des filtres disponibles dans le rapport de routage direct rtc CQD.":::
   
2. Suivre les tendances

    L’analyse des tendances est essentielle pour comprendre l’utilisation et la fiabilité du service. Les tendances horaires fournissent un examen attentif des performances quotidiennes, ce qui permet d’identifier les incidents en temps réel. Les tendances quotidiennes vous permettent de voir l’intégrité de votre service d’un point de vue à long terme. Il est important de pouvoir basculer entre ces deux modes avec une granularité de données appropriée. Le rapport de routage direct RTC CQD fournit une vue d’ensemble des tendances de 6 mois, des tendances quotidiennes de 7 et 30 jours, ainsi que des tendances horaires pour vous permettre d’analyser les performances à chaque niveau.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Capture d’écran des graphiques de tendances dans le rapport de routage direct rtc CQD.":::

3. Explorer jusqu’au niveau du SBC ou de l’utilisateur

   Nous avons créé des fonctionnalités d’extraction sur de nombreuses catégories de données dans CQD, ce qui vous permet de comprendre rapidement la distribution de l’utilisation ou de la fiabilité au niveau du SBC ou de l’utilisateur. À l’aide de l’extraction, vous pouvez rapidement résoudre les problèmes de point de terminaison et comprendre l’impact réel de l’utilisateur. Le rapport de routage direct RTC CQD présente les métriques Détails du service et Ratio d’efficacité réseau. Cliquez sur le point de données qui vous intéresse pour accéder aux détails au niveau du SBC ou de l’utilisateur.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Capture d’écran montrant la fonctionnalité d’extraction sur un point de données.":::


## <a name="pstn-overview"></a>Vue d’ensemble de PSTN

Le rapport de routage direct rtc CQD fournit les informations suivantes relatives à l’intégrité globale du service au cours des 180 derniers jours.
![Capture d’écran : rapport CQD RTC.](media/CQD-PSTN-report1.png)

Par exemple, si vous êtes intéressé par l’utilisation globale et l’intégrité de tous les appels entrants qui passent par SBC abc.bca.adatum.biz avec les États-Unis comme pays interne :

| **Appel sortant** | **Description**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Vous pouvez utiliser les filtres en haut pour explorer et sélectionner ByotIn comme type d’appel, abc.bca.contoso.com en tant que contrôleur session Boarder et ÉTATS-UNIS en tant que pays interne. |
| 2            | Tendance d’utilisation des 180 derniers jours. Vous trouverez le rapport détaillé sur l’utilisation dans la page Détails du service.                                                                     |
| 3            | Tendance après retard de numérotation, latence, gigue et perte de paquets au cours des 180 derniers jours. Vous trouverez un rapport détaillé sur la page Paramètres réseau.                           |
| 4            | Tendance des appels simultanés et des utilisateurs actifs quotidiens au cours des 180 derniers jours. Ce graphique peut vous aider à comprendre le volume maximal du service.                            |
| 5            | La principale raison de fin d’appel a affecté la qualité du service au cours des 180 derniers jours. Vous trouverez des détails sur l’intégrité du service dans la page Network Effective Ratio (NER).                    |

## <a name="service-details"></a>Détails du service

Cette page fournit les tendances d’utilisation du service par jour et la répartition des commentaires des utilisateurs par zone géographique.

  - **Nombre total d’appels de tentative :** Nombre total d’appels de tentative dans cet intervalle de temps, y compris les appels réussis et ayant échoué

  - **Nombre total d’appels connectés -** Nombre total d’appels connectés dans cet intervalle de temps

  - **Nombre total de minutes :** Utilisation totale des minutes dans cet intervalle de temps

  - **Utilisateurs actifs quotidiens (DAU) –** Nombre d’utilisateurs actifs quotidiens ayant effectué au moins un appel connecté ce jour-là

  - **Appels simultanés :** Nombre maximal d’appels actifs simultanés en une minute

  - **Commentaires de l’utilisateur :** Le score « Évaluer mon appel » provient de l’utilisateur. 3-5 est considéré comme un bon appel. 1-2 est considéré comme un mauvais appel.

![Capture d’écran : rapport CQD RTC.](media/CQD-PSTN-report2.png)

Par exemple :

1.  Si la durée moyenne des appels passe à 0 au 14/02/2020, vous pouvez d’abord vérifier si le volume d’appels semble normal et voir s’il existe une différence importante entre le nombre total d’appels de connexion et le nombre total d’appels de tentative. Accédez ensuite à la page Ratio d’efficacité réseau pour investir sur les raisons de l’échec des appels.

2.  Si vous voyez une augmentation des points rouges sur la carte de commentaires des utilisateurs, vous pouvez accéder à la page Rapport d’efficacité réseau et au paramètre réseau pour voir s’il existe des anomalies et si vous pouvez déclencher un ticket à l’aide de MS Service Desk.

## <a name="network-effectiveness-ratio"></a>Ratio d’efficacité du réseau

Il s’agit de la même métrique que celle qui apparaît dans le tableau de bord Intégrité globale. Vous pouvez vérifier le numéro NER horaire avec les détails des appels affectés pour les deux directions d’appel (entrant/sortant) sur le rapport d’efficacité du réseau horaire et le graphique de raison de fin d’appel ci-dessous.

  - **NER** : capacité (%) d’un réseau à passer des appels en mesurant le nombre d’appels envoyés par rapport au nombre d’appels passés à un destinataire.

  - **Code de réponse SIP** : un code de réponse entier à trois chiffres affiche l’état de l’appel.

  - **Code de réponse Microsoft** - Code de réponse A envoyé à partir du composant Microsoft.

  - **Description** : phase de raison correspondant au code de réponse SIP et au code de réponse Microsoft.

  - **Nombre d’appels affectés** : nombre total d’appels affectés pendant l’intervalle de temps sélectionné.

> ![Capture d’écran : rapport CQD RTC.](media/CQD-PSTN-report3.png)
> 
Par exemple :

![Capture d’écran : rapport CQD RTC.](media/CQD-PSTN-report4.png)

Si la valeur NER quotidienne a un creux le 05/02/2020, vous pouvez cliquer sur la date et d’autres graphiques zoomeront sur cette date spécifique.

![Capture d’écran : rapport CQD RTC.](media/CQD-PSTN-report5.png)

À partir de la tendance horaire ner bon pourcentage, vous pouvez trouver la baisse se produit vers 21:00. Ensuite, cliquez à nouveau pour zoomer sur l’heure 21 et vérifiez les détails de l’appel effectué pour voir le nombre d’appels ayant échoué dans cette heure et quelles sont les raisons de la fin de l’appel. Vous pouvez commencer par tirer automatiquement sur les problèmes SBC ou signaler à Service Desk si le problème n’est pas lié à SBC.

## <a name="network-parameters"></a>Paramètres réseau

Tous les paramètres réseau sont mesurés à partir de l’interface de routage direct vers le contrôleur de bordure de session. Pour plus d’informations sur les valeurs recommandées, consultez [Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md) et examinez les valeurs recommandées de Customer Edge vers Microsoft Edge.

  - **Jitter** : mesure en millisecondes de la variation du délai de propagation réseau calculée entre deux points de terminaison à l’aide de RTCP (The RTP Control Protocol).

  - **Perte de paquets** : mesure du paquet qui n’a pas pu arriver ; il est calculé entre deux points de terminaison.

  - **Latence** ( également appelée temps aller-retour) est la durée nécessaire à l’envoi d’un signal, ainsi que la durée nécessaire à la réception de l’accusé de réception de ce signal. Ce délai se compose des temps de propagation entre les deux points d’un signal.

> ![Capture d’écran : rapport CQD RTC.](media/CQD-PSTN-report6.png)

Par exemple :

Si vous voyez un pic sur l’un des quatre graphiques (latence, gigue, taux de perte de package, délai de publication de la numérotation) pour une date spécifique, par exemple, latence le 14/02/2020, cliquez sur le point de date. Et le graphique de tendance horaire en bas s’actualise pour afficher le nombre horaire. Vous pouvez vérifier les SBC ou lever un ticket auprès de MS Service Desk.

![Capture d’écran : rapport CQD RTC.](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Sujets associés

[Utiliser Power BI pour analyser les données de CQD pour Microsoft Teams](CQD-PSTN-report.md)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)