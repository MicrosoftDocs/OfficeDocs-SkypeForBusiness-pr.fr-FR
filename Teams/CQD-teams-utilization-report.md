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
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Utilisez les rapports Power BI de Microsoft teams pour suivre l’utilisation de Microsoft teams au sein de votre organisation.
ms.openlocfilehash: efca39a89eecdf9d603a81a07d8529147f87698a
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978551"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>Afficher l’utilisation de Microsoft teams dans Power BI à l’aide de données bord

Nouveauté du 2020 mars, nous avons ajouté un rapport sur l’utilisation des équipes aux [modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 

Ce nouvel état d’utilisation de teams vous permet de déterminer la façon dont vos utilisateurs utilisent Microsoft Teams. Ces rapports sont destinés à être centralisés pour permettre à la fois aux administrateurs et aux leaders du marché d’avoir accès à ces données.

Le rapport taux d’utilisation de Microsoft Team BI comporte deux rapports principaux : **[Résumé des appels et synthèse](#call-count-summary-report)** des **[minutes audio](#audio-minutes-summary-report)**. L' [utilisation quotidienne](#daily-usage), les détails de l' [audio régional](#regional-audio-details), les détails de la [Conférence](#conference-details) et les rapports de [liste d’utilisateurs](#user-list) sont lus quand un utilisateur tire parti des rapports d’exploration, indiqués dans les descriptions ci-dessous.

> [!NOTE]
> Les données de bâtiment et de sous-réseau doivent être renseignées pour fournir des fonctionnalités de filtrage régionale et réseau.

## <a name="call-count-summary-report"></a>Rapport de synthèse sur le nombre d’appels

La page principale (Résumé du numéro d’appel) fournit immédiatement le nombre de sessions audio, vidéo et de partage d’écran au cours des 30 et 90 derniers jours, comme indiqué dans le titre de section. Les données affichées initialement s’affichent pour l’ensemble de l’organisation et peuvent être filtrées à l’aide des options de la liste déroulante des segments sur le côté gauche de la page.

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report1.png)

1. Dans la partie droite de la liste déroulante du segment, le nombre d’appels par type de média est scindé en affichage interne/externe au cours des 30 derniers jours. Dans la capture d’écran ci-dessus, nous pouvons voir plus d’appels à partir d’emplacements d’organisation extérieurs, ce qui est pertinent pour l’environnement global actuel.
  ![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report2.png)

1. À droite de la zone nombre de types de média, nous avons le nombre d’appels mensuels par type de média pour les derniers 90 jours. Chaque type de colonne et de média peut être pointé pour afficher le nombre d’un mois précédent ou du mois actuel jusqu’à ce jour, en fournissant des informations de tendance d’utilisation.
  ![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report3.png)
 

1. Le graphique au milieu ne fonctionne pas comme le graphique de jour de 90, mais il fournit un affichage d’utilisation journalière pour les 30 derniers jours, et permet à un utilisateur de cliquer avec le bouton droit sur les détails d’un jour spécifique.
  ![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report4.png)

Dans la section en bas à gauche de la page se trouve un tableau qui fournit des valeurs totales pour chaque type de média au cours de l’année écoulée. 
    ![Capture d’écran : rapports](media/CQD-teams-utilization-report5.png) ![d’utilisation des équipes : rapports d’utilisation des équipes](media/CQD-teams-utilization-report6.png)   

À droite du tableau, un graphique à barres affiche les clients les plus utilisés (appels/flux) au cours des 30 derniers jours.
   ![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report7.png)

Le dernier ensemble de graphiques pour cette page présente chaque type de média individuellement, avec une répartition indiquant une utilisation de conférences et de réseaux P2P. Les graphiques ci-dessous montrent qu’il existe un nombre nettement supérieur d’utilisation de conférences par rapport au P2P.
  ![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>Rapport de synthèse des minutes audio

Le rapport d’utilisation des minutes audio est fourni dans quelques affichages. 

Le résumé de l’utilisation de l’espace de 30 jours est affiché en regard des segments comme facile à utiliser pour les zones de texte. Le numéro supérieur correspond au total du trente jours, avec les répartitions internes et externes.

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report9.png)

Le graphique barre supérieure droite fournit une vue yearlong de l’utilisation de la fonction audio de conférence. Pointez sur le mois pour afficher les minutes audio de la Conférence.

Pour afficher la différence entre le son de votre interligne et celle de la conférence téléphonique, le graphique en bas à gauche tire tout le son de l’année dernière et le scinde entre les deux types.

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report10.png)

Le dernier graphique de la page minutes audio montre l’utilisation des minutes audio sur une façade de carte globale. Ce graphique ne fonctionnera que si les données de génération et de sous-réseau sont téléchargées vers le client. La superposition de graphique en secteurs sur la carte peut être percée, ce qui vous permet de fournir une utilisation audio régionale.

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>Fonctionnalités d’analyse approfondie

Comme indiqué précédemment, les utilisateurs peuvent explorer les rapports d’utilisation quotidienne et régionale.

### <a name="daily-usage"></a>Utilisation quotidienne

Le rapport d’utilisation quotidienne permet à un administrateur d’identifier les périodes de forte consommation au cours d’une journée. En plus de l’utilisation, nous sommes en mesure de capturer les informations et les commentaires globaux de chaque jour.

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report12.png)

Le rapport activité quotidienne affiche le nombre de partages audio, vidéo et d’écran du jour sélectionné, avec la possibilité de faire la différence entre les connexions internes et externes. Une composition de conférence et d’égal à égal (P2P) est à droite de la zone de total modalité. Le coin supérieur droit du rapport dresse la liste des conférences avec leur ID et leurs participants correspondants. La liste de conférences fournit également une analyse supplémentaire au rapport sur les détails de la Conférence. REMPLACER LE GRAPHIQUE

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report13.png)

Le graphique à barres dans la zone centrale permet à l’utilisateur d’identifier les périodes de consommation de pointe au cours d’une journée. Les utilisateurs peuvent descendre dans l’heure représentée sur le graphique qui présente le rapport de liste d’utilisateurs pour l’heure.

À droite du graphique à barres, le retour utilisateur est présenté dans un format visuel. Bien que l’utilisateur puisse être subjectif, il fournit une vision permettant d’identifier les problèmes potentiels.

Le tableau inférieur fournit une gamme de métriques pour le jour. Des pourcentages insuffisants, ainsi que les taux d’échec, peuvent offrir à un administrateur des zones d’amélioration potentielles. Chaque heure peut également être sélectionnée individuellement, comme illustré ci-dessous.

Ces données peuvent être utilisées pour identifier les régions rencontrant des problèmes en temps maximum de consommation.


Cliquez sur la colonne de ce jour pour afficher les métriques de cette heure.
![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report14.png)
  
  1.  Le tableau sous le graphique affiche les mesures pour cette heure. Vous pouvez trier ce critère par n’importe quel en-tête de colonne. Néanmoins, nous aimerions pouvoir Rechercher les zones problématiques.  
    ![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report15.png)
    
  2.  Nous voyons que la région de IND rencontre des performances vidéo médiocres pendant ce laps de temps. Par la suite, les rapports Microsoft bord QER peuvent être utilisés pour affiner l’emplacement problématique, car le cadre de la région et de l’heure a été identifié.

### <a name="conference-details"></a>Détails de la Conférence

Le rapport Détails de la Conférence fournit des informations supplémentaires pour les réunions, de la liste des participants aux types de médias utilisés lors de la session.

Cliquez avec le bouton droit sur la barre du participant sur le graphique d’ID de conférence sur la page utilisation quotidienne pour explorer les détails de la Conférence.

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report24.png)

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report25.png)
  

Nous pouvons voir les participants à la Conférence ainsi que les informations pertinentes en matière de perte de paquets et de gigue pour vous aider à résoudre les problèmes potentiels dans le tableau de base.

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>Détails audio régionaux

Les détails audio régionaux d’une analyse descendante montrent en particulier l’utilisation des minutes audio pour la région sélectionnée. Les utilisateurs disposant d’un accès à bord peuvent voir les tendances d’utilisation pour les appels audio et vidéo P2P au sein de la région sélectionnée.

1.  Dans la page Résumé du numéro d’appel, accédez à la zone de recherche en tant que région spécifique dans le tableau.
  ![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report16.png)

2.  Sélectionnez la ligne contenant les informations supplémentaires nécessaires pour la région.
  ![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report17.png)

3.  Les tendances des données indiquent un nombre considérable de minutes d’utilisation sur le réseau interne, avec une conférence bien plus longue.
  ![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report18.png)

La tendance régionale du son peut être utilisée pour illustrer la façon dont les utilisateurs sont affectés par des influences externes dans le monde. Pour l’instant, nous vous attendons d’avoir accès à l’utilisation externe des régions EMEA et APAC qui peuvent être utilisées par les personnes invitées à travailler à distance.


### <a name="user-list"></a>Liste d’utilisateurs

La liste des utilisateurs permet d’explorer les informations spécifiques à l’utilisateur pour une heure spécifique sélectionnée par la personne qui affiche le rapport. Le rapport sur la liste des utilisateurs est accessible par le biais d’une analyse approfondie du graphique tendances d’heures du rapport sur l’utilisation journalière. Il suffit de cliquer avec le bouton droit de l’heure pour accéder à des informations supplémentaires et sélectionner extraire vers l’aide d’une liste d’utilisateurs, comme illustré ci-dessous.

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report19.png)

Le rapport sur la liste des utilisateurs présente les connexions internes/externes par le biais du graphique en anneau dans le centre supérieur de la page. Nous pouvons voir qu’il existe un grand nombre de participations à partir de l’extérieur du réseau d’entreprise dans l’image ci-dessous.

Le coin supérieur droit du graphique indique le nombre d’appels passés par chaque utilisateur au cours de cette heure.

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report20.png)

Le tableau inférieur fournit des informations détaillées sur les sessions auxquelles un utilisateur a participé au cours de cette heure. La colonne type d’échec permet de déterminer le résultat d’un appel. Les colonnes d’appareil de capture et de rendu sont utiles dans l’identification de la raison pour laquelle un appel a été signalé d’une mauvaise qualité.


## <a name="related-topics"></a>Sujets associés

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md)

[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Tableau de bord Analyse des appels et Qualité des appels](difference-between-call-analytics-and-call-quality-dashboard.md)
 