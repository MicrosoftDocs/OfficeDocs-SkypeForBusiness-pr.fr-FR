---
title: Rapports d’intégrité et d’utilisation
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 04/07/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Création de rapports de données de nœud pour l’intégrité et l’utilisation des rapports
f1keywords: ''
ms.openlocfilehash: 87a04860a69799bf00492691dc24498076bd4924
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271429"
---
# <a name="health-and-usage-reports"></a>Rapports d’intégrité et d’utilisation

Le nœud de création de rapports contient des données relatives à l’intégrité et à l’utilisation de vos salles gérées Microsoft et de vos insights de service. La **vue d’ensemble** présente les tendances d’intégrité à l’échelle du locataire de vos chambres. L’onglet **Intégrité** affiche une liste des salles avec leurs données d’intégrité correspondantes. L’utilisation de la salle basée sur les informations de calendrier et les données de qualité des appels est visible sous **l’onglet Utilisation** .

## <a name="navigating-reports"></a>Navigation dans les rapports

<!--![A screenshot of active tickets bar graph](../media/health-and-usage-002new.png)-->

La section Vue d’ensemble fournit des représentations graphiques des aspects importants de la gestion des salles de réunion. Les graphiques changeront en fonction de l’intervalle de temps sélectionné ou du groupe sélectionné. Pour modifier l’intervalle de temps, cliquez sur le menu déroulant.

<!--!![A screenshot of a menu to choose a day](../media/health-and-usage-004.png)-->

Pour modifier le groupe, cliquez sur le menu déroulant sélection du groupe dans la bannière.

<!--!![A screenshot of the banner menu auto-generated](../media/health-and-usage-005.png)-->
### <a name="tickets-by-category"></a>Billets par catégorie

L’anneau affiche le nombre total de tickets déclenchés pour l’intervalle de temps et le groupe sélectionnés (la valeur par défaut est sept jours, tous les groupes). Les tickets sont représentés dans leurs principales catégories : Audio, Affichage, Périphériques, Connectivité, Contrôle de version et Client signalés.

<!--!![A screenshot of pie chart tickets by category](../media/health-and-usage-006.png)-->

Un menu volant pour l’affichage détaillé des tickets de cette catégorie s’affiche lorsqu’il est sélectionné.

<!--!![A screenshot of tickets and versioning side by side](../media/health-and-usage-007.png)-->

Dans le menu volant, il est possible de filtrer la liste des tickets par sous-catégorie en sélectionnant la partie respective de l’anneau. 

<!--!![A screenshot tickets by subcategory automatically generated](../media/health-and-usage-008.png)-->

Pour revenir en arrière, cliquez sur l’anneau ou cliquez sur la barre de navigation en haut à gauche.

Pour accéder à un ticket spécifique dans cette vue de liste, cliquez sur le lien sous le **colum du ticket de support**.

### <a name="ticket-history"></a>Historique des tickets

Le graphique d’historique des tickets affiche une comparaison des incidents qui vous ont été attribués ou qui ont été attribués à Microsoft sur la période spécifiée.

> [!NOTE]
> Si un ticket change de propriétaire dans une journée, celui qui est propriétaire de l’affectation pour la majorité de cette journée aura le ticket compté pour eux. Par exemple, si vous attribuez le ticket à Microsoft tôt dans la journée, le ticket est comptabilisé dans **Affecté à Microsoft** pour la journée.

<!--![A screen shot of Tickets history by different periods](../media/health-and-usage-009.png)-->

### <a name="health-history"></a>Historique d’intégrité

Ce graphique montre l’intégrité moyenne (définition dans la section Intégrité) pour toutes les salles du locataire, ainsi que l’intégrité moyenne de tous les clients MMR au quotidien. Vous pouvez afficher l’intégrité moyenne pendant jusqu’à 90 jours.

<!--!![A screenshot of rooms health and average health](../media/health-and-usage-010.png)-->

### <a name="most-reliableleast-reliable-rooms"></a>Salles les plus fiables/les moins fiables

Deux tableaux montrent les salles les plus fiables et les moins fiables en fonction de la santé. Pour l’affichage liste complète, sélectionnez Intégrité, puis triez la liste en fonction de la colonne Intégrité.

### <a name="rooms-history"></a>Historique des salles

Fournit une vue historique des chambres inscrites dans le service et fournit une vue comparative des chambres qui étaient saines ou non surveillées dans la même période.

## <a name="health"></a>Intégrité

Pour accéder au rapport d’intégrité de toutes les salles, sélectionnez Rapports, puis  **Intégrité**.

<!--!![A screenshot of a Reports health percentage](../media/health-and-usage-001.png)-->

Le score d’intégrité est une métrique conçue pour exposer les salles qui sont les plus susceptibles de provoquer la frustration des utilisateurs finaux. Une chambre peut être saine ou non saine pour une journée donnée. Il est considéré comme défectueux si un ticket ou de nombreux billets ont impacté la salle pendant plus de 20 minutes au total pendant les heures de non-maintenance (5 h -21 h, heure locale de l’ordinateur). Par exemple, si un ticket est ouvert à 5h00 mais fermé à 5h15, la salle est toujours considérée comme saine. Mais, si un deuxième ticket s’est produit de 09h00 à 9h10, la chambre serait alors considérée comme non saine pour la journée. De même, si un ticket s’est produit de 5h00 à 5h21, il est considéré comme non sain pour la journée.

> [!NOTE]
> L’intégrité du jour est agrégée une fois par jour à 00:00 heure UTC. Pour les clients proches de la ligne de date internationale, l’agrégation d’intégrité peut se produire vers le milieu de la journée de travail.

> [!NOTE]
> Les salles qui sont intégrées sont masquées pour la liste des salles sous l’onglet Intégrité et ne sont pas comptabilisées dans l’intégrité moyenne du locataire.

Si vous cliquez sur une salle répertoriée dans cette vue, vous obtenez plus de détails.

Le graphique à barres affiche le nombre de tickets chaque jour. Les billets ouverts le jour même apparaissent en bleu. Les billets ouverts avant le jour correspondant apparaissent en orange. Cliquer sur un jour sur le graphique filtre le graphique à secteurs et le tableau sur les tickets appropriés. Pour inverser le filtre, naviguez avec la barre de navigation ou cliquez sur le graphique.

La catégorisation des tickets est représentée dans le graphique en anneau. L’interaction avec cette méthode filtre le graphique de chronologie et la table. Pour inverser le filtre, naviguez avec la barre de navigation ou cliquez sur le graphique.

<!--!![A screenshot of a Reports health bar graph](../media/health-and-usage-014.png)-->

L’affichage de l’impact de la réunion montre les réunions planifiées au cours desquelles un ticket avec la gravité « Important » ou « Critique » était ouvert. L’objectif de cette vue est de fournir une approximation des réunions où les participants auraient pu rencontrer des problèmes.

L’affichage de l’impact de la réunion montre les réunions planifiées au cours desquelles un ticket avec la gravité « Important » ou « Critique » était ouvert. L’objectif de cette vue est de fournir une approximation des réunions où les participants auraient pu rencontrer des problèmes.

<!--![A screenshot of a Reports meeting impact](../media/health-and-usage-015.png)-->

L’onglet Paramètres affiche les métadonnées de la salle, telles que les informations matérielles, les paramètres de l’appareil, les informations du BIOS, les paramètres d’application et l’emplacement.

## <a name="usage"></a>Utilisation

Pour afficher le rapport d’utilisation de toutes les salles, sélectionnez **Rapports->Utilisation**.

<!--!![A screenshot of all rooms' usage by health](../media/health-and-usage-011.png)-->

Les titres fournissent quelques insights :

- Nombre total de chambres dans votre locataire
- Combien n’ont pas de réunions réservées, hors connexion ou en ligne
- Pourcentage d’utilisation des salles dans le locataire
- Nombre total de réunions réservées par le biais de l’échange
- Pourcentage de réunions réservées incluant un lien Skype ou Teams
- Nombre total d’appels avec participation à la salle
- Agréger le score de performances des appels de tous les appels classés avec « Bonne » qualité pour tous les appels. 

Sous les métriques de titre se trouve une table de salles avec les métriques correspondantes. Sélectionnez une salle pour afficher plus de détails sur l’utilisation. Les métriques du tableau sont décrites dans le tableau suivant.

|Colonne|Description|
|---|---|
|Utilisation|Pourcentage de temps pendant lequel la chambre a été réservée pendant les heures d’ouverture au cours de la période sélectionnée. Ex. Période définie sur 7 jours. Utilisation de 80 % par rapport aux moyens de réservation de la chambre pendant 32/40 heures|
|Réservé en ligne|Parmi les réunions réservées, dont le pourcentage a été activé avec Teams. Ex. 10 réunions ont été réservées. De ce nombre, 8 avaient un lien Teams. Booked Online = 80%|
|Réunions planifiées|Nombre absolu de réunions planifiées dans la salle|
|Nombre total d’appels|Nombre absolu d’appels avec la salle en tant que participant.|
Performances des appels|Pourcentage d’appels avec une note « Bonne ». Chaque appel est évalué et reçoit une note Good, Poor, Unknown. Cette métrique est calculée à partir d’appels corrects/nombre total d’appels|

L’utilisation est calculée à la fin de chaque jour à minuit (00:00) heure locale de l’appareil de salle de réunion. L’utilisation est calculée en fonction du temps total réservé à la réunion pour ce jour divisé par 8 heures.

## <a name="usage-details-of-a-room"></a>Détails d’utilisation d’une salle

Le fait de cliquer sur une salle dans l’affichage liste vous invite à utiliser un menu volant contenant des informations plus détaillées. Sous l’onglet Utilisation du menu volant se trouve un graphique montrant les heures d’utilisation des cinq derniers jours ouvrés. Pour chaque jour, il y a deux barres : le bleu représente l’heure de la réunion réservée ; violet représente l’heure planifiée des réunions Teams/Skype activées. En bas, les réservations moyennes de réunions et la durée des cinq derniers jours ouvrables sont calculées.

<!--![A screenshot of utilization by hours per day](../media/health-and-usage-012.png)-->

Le tableau **Appels** présente les réunions auxquelles la salle a participé à un appel Teams. La qualité audio de la salle est évaluée uniquement pour la salle, pas tous les participants. Pour afficher la qualité des appels pour tous les participants d’un appel spécifique, sélectionnez un appel en cliquant sur l’heure de début.

<!--!![A screenshot of room audio quality](../media/health-and-usage-016.png)-->

Pour afficher les détails du flux de la salle, cliquez sur l’heure de début de la session.
