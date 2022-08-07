---
title: Afficher l’utilisation de Microsoft Teams dans Power BI à l’aide de données CQD
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
description: Utilisez les rapports Power BI d’utilisation de Teams pour accéder aux données du tableau de bord de qualité des appels (CQD) Microsoft Teams afin de suivre l’utilisation de Microsoft Teams dans votre organisation.
ms.openlocfilehash: bd579fa3f57c6e3b50a363eb77523f577c750efb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270689"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>Afficher l’utilisation de Microsoft Teams dans Power BI à l’aide de données CQD

Le rapport d’utilisation teams est disponible dans le cadre de nos [modèles de requête Power BI téléchargeables pour CQD](https://www.microsoft.com/download/details.aspx?id=102291). 

Ce rapport vous permet de voir comment (et combien) vos utilisateurs utilisent Microsoft Teams en accédant aux données du tableau de bord de qualité des appels (CQD) Teams. Ces rapports sont destinés à être un emplacement centralisé auquel les administrateurs et les dirigeants d’entreprise peuvent accéder rapidement pour ces données. Notez que nous vous conseillons de [ne pas nous appuyer sur ces données pour des nombres concrets en raison de la nature des données de télémétrie de qualité des appels](CQD-frequently-asked-questions.md#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that).

Le rapport Power BI d’utilisation de Teams se compose de deux rapports principaux : **[Le résumé du nombre d’appels](#call-count-summary-report)** et le **[résumé des minutes audio](#audio-minutes-summary-report)**. [L’utilisation quotidienne](#daily-usage), [les détails audio régionaux](#regional-audio-details), [les détails de conférence et les](#conference-details) rapports de [liste](#user-list) d’utilisateurs entrent en jeu lorsqu’un utilisateur tire parti des rapports d’exploration, indiqués dans les descriptions ci-dessous.

> [!NOTE]
> Les données de génération et de sous-réseau doivent être remplies pour fournir des fonctionnalités de filtrage régional et réseau.

## <a name="call-count-summary-report"></a>Rapport récapitulatif du nombre d’appels

La page principale (Résumé du nombre d’appels) fournit immédiatement le nombre de sessions de partage audio, vidéo et d’écran au cours des 30 et 90 derniers jours, comme indiqué dans le titre de la section. Les données initialement affichées sont destinées à l’ensemble de l’organisation et peuvent être filtrées à l’aide des options de liste déroulante du segment sur le côté gauche de la page.

![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report1.png)

1. À droite des listes déroulantes de segments, le nombre d’appels par type de média est divisé en vue interne/externe au cours des trente derniers jours. Nous pouvons voir à travers la capture d’écran ci-dessus qu’il y a plus d’appels qui se produisent à partir d’emplacements extérieurs à l’organisation, ce qui est logique compte tenu de l’environnement global actuel.
  ![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report2.png)

1. À droite de la zone de comptage du type de média, nous avons le nombre d’appels mensuels par type de média pour les 90 derniers jours. Chaque type de colonne et de média peut être survolé pour afficher le nombre pour un mois précédent ou le mois en cours jusqu’à ce jour, en fournissant des informations sur les tendances d’utilisation.
  ![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report3.png)
 

1. Le graphique intermédiaire fonctionne comme le graphe de 90 jours, mais il fournit une vue d’utilisation quotidienne pour les 30 derniers jours et permet à un utilisateur de cliquer avec le bouton droit et d’explorer les détails d’un jour spécifique.
  ![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report4.png)

Dans la section inférieure gauche de la page, vous trouverez une table qui fournit des valeurs totales pour chaque type de média au cours de la dernière année. 
    ![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report5.png)
    ![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report6.png)   

À droite du tableau, un graphique à barres affiche les clients les plus utilisés (appels/flux) au cours des 30 derniers jours.
   ![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report7.png)

Le dernier ensemble de graphiques de cette page affiche chaque type de média individuellement, avec une répartition montrant l’utilisation de la conférence et P2P. Les graphiques ci-dessous montrent qu’il existe un nombre beaucoup plus élevé d’utilisation des conférences par rapport à P2P.
  ![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>Rapport récapitulatif des minutes audio

Dans le rapport d’utilisation des minutes audio, l’utilisation totale des minutes est fournie par le biais de différentes vues. 

Nous avons le résumé de l’utilisation de 30 jours affiché en regard des segments aussi facile à utiliser que les zones de texte. Le numéro supérieur affiche le total de trente jours, avec des répartitions internes et externes en dessous.

![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report9.png)

Le graphique à barres en haut à droite fournit une vue d’ensemble de l’utilisation de l’audio de conférence tout au long de l’année. Pointez sur le mois pour afficher les minutes audio de la conférence.

Pour montrer la différence entre P2P et l’audio de conférence, le graphique en bas à gauche prend tout l’audio de l’année écoulée et le décompose entre les deux types.

![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report10.png)

Le dernier graphique de la page Minutes audio affiche l’utilisation des minutes audio sur une superposition de carte globale. Ce graphique fonctionne uniquement si les données de génération et de sous-réseau sont chargées sur le locataire. La superposition de graphique à secteurs sur la carte peut être approfondie, ce qui fournit par la suite une utilisation audio régionale.

![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>Fonctionnalités d’exploration

Comme indiqué précédemment, les utilisateurs peuvent explorer les rapports d’utilisation quotidiens et régionaux.

### <a name="daily-usage"></a>Utilisation quotidienne

Le rapport Utilisation quotidienne permet à un administrateur d’identifier les périodes de pointe de consommation au cours d’une journée. En plus de l’utilisation, nous sommes également en mesure de capturer les sentiments et commentaires de l’utilisateur global pour cette journée.

![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report12.png)

Le rapport d’utilisation quotidienne affiche le nombre de partages audio, vidéo et d’écran pour le jour sélectionné, avec la possibilité supplémentaire de différencier la connectivité interne et externe. Une répartition de conférence et pair à pair se trouve à droite immédiate de la zone de total de modalité. Le coin supérieur droit du rapport fournit une liste des conférences avec leur ID et les participants associés pour la journée. La liste des conférences fournit également une exploration supplémentaire du rapport Détails de la conférence. REMPLACER LE GRAPHIQUE

![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report13.png)

Le graphique à barres dans la zone centrale permet à l’utilisateur d’identifier les périodes de pointe de consommation au cours d’une journée. Les utilisateurs peuvent explorer l’heure représentée sur le graphique qui présente le rapport liste d’utilisateurs pour l’heure.

À droite du graphique à barres, les commentaires des utilisateurs sont présentés dans un format visuel. Bien que le sentiment de l’utilisateur puisse être subjectif, il fournit des insights qui peuvent être utilisés pour identifier les problèmes potentiels.

Le tableau inférieur fournit une plage de métriques pour la journée. Les pourcentages faibles et les taux d’échec peuvent fournir à un administrateur des domaines d’amélioration potentiels. Chaque heure peut également être sélectionnée individuellement, comme indiqué ci-dessous.

Ces données peuvent être utilisées pour identifier les régions qui rencontrent des problèmes pendant les heures de pointe de la consommation.


Cliquez sur la colonne de ce jour pour afficher les métriques de cette heure.
![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report14.png)
  
  1.  Le tableau sous le graphique affiche les métriques de cette heure. Cela peut être trié par n’importe quel en-tête de colonne ; toutefois, nous serions intéressés à trouver des domaines problématiques.  
    ![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report15.png)
    
  2.  Nous constatons que la région IND connaît des performances vidéo médiocres dans les conférences au cours de cette période. Par la suite, les rapports Microsoft QER CQD peuvent être utilisés pour affiner l’emplacement problématique à mesure que la région et l’intervalle de temps ont été identifiés.

### <a name="conference-details"></a>Détails de la conférence

Le rapport Détails de la conférence fournit des informations supplémentaires sur les réunions, à partir d’une liste de participants, aux types de médias utilisés pendant la session.

Cliquez avec le bouton droit sur une conférence dans la barre des participants dans le graphique d’ID de conférence de la page Utilisation quotidienne pour explorer les détails de la conférence.

![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report24.png)

![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report25.png)
  

Nous pouvons voir les participants à la conférence ainsi que toutes les informations pertinentes jusqu’à la perte de paquets et la gigue pour aider à résoudre les problèmes potentiels dans le tableau inférieur.

![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>Détails audio régionaux

L’exploration des détails audio régionaux montre spécifiquement l’utilisation des minutes audio pour la région sélectionnée. Les utilisateurs ayant accès à CQD peuvent voir les tendances d’utilisation de l’audio P2P et de conférence dans la région sélectionnée.

1.  Dans la page Résumé du nombre d’appels, effectuez une exploration jusqu’à une région spécifique dans la table.
  ![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report16.png)

2.  Sélectionnez la ligne pour laquelle des informations supplémentaires sont nécessaires.
  ![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report17.png)

3.  Les tendances de données indiquent un nombre significatif de minutes utilisées sur le réseau interne, avec des conférences bien supérieures à l’utilisation de P2P.
  ![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report18.png)

La tendance audio régionale peut être utilisée pour montrer comment les utilisateurs sont impactés par des influences externes dans le monde. Plus précisément, à l’heure actuelle, nous nous attendons à ce que l’utilisation externe des régions EMEA et APAC augmente, les personnes étant invitées à travailler à distance.


### <a name="user-list"></a>Liste d’utilisateurs

L’exploration de liste d’utilisateurs fournit, comme on peut s’y attendre, des informations spécifiques à l’utilisateur pour une heure spécifique sélectionnée par la personne qui affiche le rapport. Le rapport liste d’utilisateurs est accessible via une exploration dans le graphique Tendances horaires du rapport Utilisation quotidienne. Cliquez avec le bouton droit sur l’heure nécessaire pour obtenir des informations supplémentaires, puis sélectionnez Explorer et liste d’utilisateurs, comme indiqué ci-dessous.

![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report19.png)

Le rapport liste d’utilisateurs affiche la connectivité interne/externe via le graphique en anneau dans le centre supérieur de la page. Nous pouvons voir qu’il y a une grande participation de l’extérieur du réseau d’entreprise dans l’image ci-dessous.

Le haut à droite du graphique affiche le nombre d’appels effectués par chaque utilisateur au cours de cette heure.

![Capture d’écran : Rapports d’utilisation teams.](media/CQD-teams-utilization-report20.png)

Le tableau inférieur fournit des informations détaillées sur les sessions auxquelles chaque utilisateur a participé au cours de cette heure. La colonne Type d’échec est utile pour déterminer ce qui a provoqué la suppression d’un appel. Les colonnes Capture et Render Device sont utiles pour identifier la raison pour laquelle un appel a été signalé comme ayant une qualité médiocre.


## <a name="related-topics"></a>Voir aussi

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md)

[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Tableau de bord Analyse des appels et Qualité des appels](./monitor-call-quality-qos.md)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
