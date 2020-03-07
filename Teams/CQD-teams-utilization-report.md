---
title: Afficher l’utilisation de Microsoft teams dans Power BI à l’aide de données bord
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
description: Utilisez les rapports Power BI de Microsoft teams pour suivre l’utilisation de Microsoft teams au sein de votre organisation.
ms.openlocfilehash: d22f37bb230ecbaa3cf6c33c2ba43f5ea92afaad
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559420"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>Afficher l’utilisation de Microsoft teams dans Power BI à l’aide de données bord

Nouveauté du 2020 mars, nous avons ajouté un rapport sur l’utilisation des équipes aux [modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 

Ce nouvel état d’utilisation de teams vous permet de déterminer la façon dont vos utilisateurs utilisent Microsoft Teams. Ces rapports sont destinés à être centralisés pour permettre à la fois aux administrateurs et aux leaders du marché d’avoir accès à ces données.

Le rapport taux d’utilisation de Microsoft Team BI comporte deux rapports principaux : **[Résumé des appels et synthèse](#call-count-summary-report)** des **[minutes audio](#audio-minutes-summary-report)**. Les rapports sur l' [utilisation quotidienne](#daily-usage) et les [Détails audio régionaux](#regional-audio-details) sont disponibles lorsqu’un utilisateur tire parti des rapports d’exploration, indiqués dans les descriptions ci-dessous.

> [!NOTE]
> Les données de bâtiment et de sous-réseau doivent être renseignées pour fournir des fonctionnalités de filtrage régionale et réseau.

## <a name="call-count-summary-report"></a>Rapport de synthèse sur le nombre d’appels

La page principale (Résumé du numéro d’appel) fournit immédiatement le nombre de sessions audio, vidéo et de partage d’écran au cours des 30 et 90 derniers jours, comme indiqué dans le titre de section. Les données affichées initialement s’affichent pour l’ensemble de l’organisation et peuvent être filtrées à l’aide des options de la liste déroulante des segments sur le côté gauche de la page.

![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report1.png)

1. Dans la partie droite de la liste déroulante du segment, le nombre d’appels par type de média est scindé en affichage interne/externe au cours des 30 derniers jours. Dans la capture d’écran ci-dessus, nous pouvons voir plus d’appels à partir d’emplacements d’organisation extérieurs, ce qui est pertinent pour l’environnement global actuel.
  ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report2.png)

1. À droite de la zone nombre de types de média, nous avons le nombre d’appels mensuels par type de média pour les derniers 90 jours. Chaque type de colonne et de média peut être pointé pour afficher le nombre d’un mois précédent ou du mois actuel jusqu’à ce jour, en fournissant des informations de tendance d’utilisation.
  ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report3.png)

1. Le graphique au milieu ne fonctionne pas comme le graphique de jour de 90, mais il fournit un affichage d’utilisation journalière pour les 30 derniers jours, et permet à un utilisateur de cliquer avec le bouton droit sur les détails d’un jour spécifique.
  ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report4.png)

Dans la section en bas à gauche de la page se trouve un tableau qui fournit des valeurs totales pour chaque type de média au cours de l’année écoulée. 
    ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report5.png)
  
Ce tableau inclut également une analyse approfondie pour vous permettre de voir une répartition des données régionale.
    ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report6.png)

À droite du tableau, un graphique à barres affiche les clients les plus utilisés (appels/flux) au cours des 30 derniers jours.
   ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report7.png)


Le dernier ensemble de graphiques pour cette page présente chaque type de média individuellement, avec une répartition indiquant une utilisation de conférences et de réseaux P2P. Les graphiques ci-dessous montrent qu’il existe un nombre nettement supérieur d’utilisation de conférences par rapport au P2P.
  ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>Rapport de synthèse des minutes audio

Le rapport d’utilisation des minutes audio est fourni dans quelques affichages. 

Le résumé de l’utilisation de l’espace de 30 jours est affiché en regard des segments comme facile à utiliser pour les zones de texte. Le numéro supérieur correspond au total du trente jours, avec les répartitions internes et externes.

![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report9.png)

Le graphique barre supérieure droite fournit une vue yearlong de l’utilisation de la fonction audio de conférence. Pointez sur le mois pour afficher les minutes audio de la Conférence.

Pour afficher la différence entre le son de votre interligne et celle de la conférence téléphonique, le graphique en bas à gauche tire tout le son de l’année dernière et le scinde entre les deux types.

![Capture d’écran : rapport](media/CQD-teams-utilization-report10.png) de synthèse sur le pays d’appel le dernier graphique pour la page minutes audio montre l’utilisation des minutes audio sur une façade de carte globale. Ce graphique ne fonctionnera que si les données de génération et de sous-réseau sont téléchargées vers le client. La superposition de graphique en secteurs sur la carte peut être percée, ce qui vous permet de fournir une utilisation audio régionale.

![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report11.png)

## <a name="drill-through-capabilities"></a>Fonctionnalités d’analyse approfondie

Comme indiqué précédemment, les utilisateurs peuvent explorer les rapports d’utilisation quotidienne et régionale.

### <a name="daily-usage"></a>Utilisation quotidienne

Le rapport d’utilisation quotidienne permet à un administrateur d’identifier les périodes de forte consommation au cours d’une journée. En plus de l’utilisation, nous sommes en mesure de capturer les informations et les commentaires globaux de chaque jour.

![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report12.png)

Ces données peuvent être utilisées pour identifier les régions rencontrant des problèmes en temps maximum de consommation.

1.  Sur la page Résumé du numéro d’appel, accédez à une date spécifique. Regardez la tendance horaire du jour pour trouver le taux d’utilisation maximal.
  ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report13.png)

2.  Cliquez sur la colonne de ce jour pour afficher les métriques de cette heure.
  ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report14.png)
    
    1.  Le tableau sous le graphique affiche les mesures pour cette heure. Vous pouvez trier ce critère par n’importe quel en-tête de colonne. Néanmoins, nous aimerions pouvoir Rechercher les zones problématiques.  
        ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report15.png)
    
    2.  Nous voyons que la région de IND rencontre des performances vidéo médiocres pendant ce laps de temps. Par la suite, les rapports Microsoft bord QER peuvent être utilisés pour affiner l’emplacement problématique, car le cadre de la région et de l’heure a été identifié.

### <a name="regional-audio-details"></a>Détails audio régionaux

Les détails audio régionaux d’une analyse descendante montrent en particulier l’utilisation des minutes audio pour la région sélectionnée. Les utilisateurs disposant d’un accès à bord peuvent voir les tendances d’utilisation pour les appels audio et vidéo P2P au sein de la région sélectionnée.

1.  Dans la page Résumé du numéro d’appel, accédez à la zone de recherche en tant que région spécifique dans le tableau.
  ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report16.png)

2.  Sélectionnez la ligne contenant les informations supplémentaires nécessaires pour la région.
  ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report17.png)

3.  Les tendances des données indiquent un nombre considérable de minutes d’utilisation sur le réseau interne, avec une conférence bien plus longue.
  ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report18.png)

La tendance régionale du son peut être utilisée pour illustrer la façon dont les utilisateurs sont affectés par des influences externes dans le monde. Pour l’instant, nous vous attendons d’avoir accès à l’utilisation externe des régions EMEA et APAC qui peuvent être utilisées par les personnes invitées à travailler à distance.



## <a name="related-topics"></a>Sujets associés

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md)

[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Tableau de bord Analyse des appels et Qualité des appels](difference-between-call-analytics-and-call-quality-dashboard.md)
 