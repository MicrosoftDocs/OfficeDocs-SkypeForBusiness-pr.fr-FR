---
title: Utiliser le tableau de bord de qualité des appels pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 'Résumé : Découvrez comment utiliser le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 61b20062925f59474d387a022a92663e0ffcd6ba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816663"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Utiliser le tableau de bord de qualité des appels pour Skype entreprise Server

**Résumé :** Apprenez-en davantage sur l’utilisation du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.

Le tableau de bord de qualité des appels (bord) permet aux professionnels de l’informatique d’utiliser des données agrégées pour identifier les problèmes de qualité de média en comparant les statistiques des groupes d’utilisateurs pour identifier les tendances et les modèles. BORD n’est pas axé sur la résolution des problèmes d’appels individuels, mais sur l’identification des problèmes et des solutions qui s’appliquent à de nombreux utilisateurs.

## <a name="call-quality-dashboard-user-guide"></a>Guide de l’utilisateur Qualité des appels

BORD est un portail Web permettant de créer et d’organiser rapidement des rapports en fonction de la qualité de vos données. BORD déploie un cube SSAS pour agréger les données dans la base de données de métriques QoE et permet aux administrateurs de créer et modifier des rapports ou d’effectuer des enquêtes en temps réel. Bien qu’il soit possible d’utiliser Excel pour se connecter directement au cube, le portail est optimisé pour différents flux de travail comprenant des données QoE. Les données incluent :

- Données de rapport mises en cache pour un accès rapide
- Liens en profondeur vers des pages de rapport pour le partage et la publication des informations
- Simplification de la modification et de la création de rapports et métadonnées modifiables pour les descriptions de rapport.

Par ailleurs, bord expose les API Web qui permettent aux utilisateurs d’accéder par programmation aux données du cube à utiliser dans les tableaux de bord personnalisés.

### <a name="feature-overview"></a>Présentation des fonctionnalités

Lorsque vous visitez le tableau de bord de qualité des appels, l’écran suivant apparaît :

![Utiliser CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. Le « volet de synthèse » est l’endroit où se trouve le contexte du « jeu de rapports » (à droite).
2. Cliquez sur « modifier » dans la PaneReport de synthèse pour définir les propriétés de niveau (y compris la hauteur de l’axe Y).
3. Le barre de navigation vous permet d’identifier votre emplacement actuel au sein de la hiérarchie de l’ensemble de rapports.
4. Les rapports avec des sous-États apparaissent avec un lien bleu. Cliquez sur le lien pour descendre dans la vue des rapports enfants.

Placez le pointeur de la souris au-dessus des graphiques à barres et des courbes de tendance pour afficher les valeurs détaillées. Le rapport ayant le focus affiche le menu d’action : « modifier », « Clone », « supprimer » et « télécharger ».

### <a name="default-reports"></a>Rapports par défaut

Lorsque vous accédez au portail de tableau de bord de qualité des appels pour la première fois, un ensemble de rapports par défaut est créé automatiquement. Ces rapports sont parfois désignés sous le nom de rapports système. Vous pouvez modifier ou supprimer librement ces rapports ou les étendre en créant des rapports frère et enfant.

Au niveau supérieur, le rapport « flux audio de Trend mois » montre la tendance mensuelle de tous les flux audio. Placez le pointeur de la souris au-dessus des barres d’un graphique à barres pour afficher une vue plus détaillée des données représentées par le graphique à barres. Cliquez sur le titre du rapport de tendance du flux audio pour accéder au rapport « géré et non géré en flux audio », où les rapports sont répartis entre les appels gérés et non gérés. Les appels gérés sont des appels passés depuis le réseau local filaire au travers d’un pare-feu. Les appels non gérés incluent les appels passés à partir du pare-feu de l’entreprise, ainsi que les appels passés via un réseau Wi-Fi.

L’autre rapport de niveau supérieur est appelé « histogramme de qualité des appels » signalé par l’utilisateur». Le taux de la qualité des appels est le numéro fourni par les utilisateurs de Skype entreprise à la fin de l’appel pour indiquer la qualité de l’appel. La plage des numéros de classement entre 1 et 5, 1 représente le pire et 5 la meilleure. L’histogramme indique le nombre d’appels audio ayant fait l’objet d’une notation dans un même mois.

Cliquez sur le titre de n’importe quel rapport pour naviguer dans les rapports comportant davantage de filtres sur les données. Dans les rapports système, chaque rapport enfant affiche un sous-ensemble des données disponibles dans le rapport parent. Le modèle de résolution des problèmes, c’est simple : Examinez le sous-état qui suggère un problème et déterminez progressivement l’espace problématique. La possibilité de créer des sous-rapports vous permet d’examiner vos propres hypothèses quant à la cause des tendances de données spécifiques.

### <a name="create-and-edit-reports"></a>Créer et modifier des rapports

Cliquez sur « modifier » dans le menu action d’un rapport pour afficher l’éditeur de rapport. Chaque rapport est complété par une requête effectuée dans le cube. Il s’agit de la visualisation des données renvoyées par la requête. L’éditeur de rapport vous permet de modifier ces requêtes et les options d’affichage du rapport. Lorsque vous ouvrez l’éditeur de rapport, vous voyez :

![Utiliser CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Les dimensions, les mesures et les filtres sont sélectionnés dans le volet gauche. Pointez sur l’une des valeurs existantes pour afficher un bouton « x » permettant de supprimer la valeur. Cliquez sur le bouton « plus » en regard d’un titre pour ouvrir la boîte de dialogue dans laquelle vous pouvez ajouter une nouvelle dimension, mesure ou filtre.
2. Les options de personnalisation de graphique figurent en haut.
3. L’Éditeur de rapport permet d’afficher un aperçu du rapport. 
4. Vous pouvez créer une description du rapport détaillé en bas de la fenêtre d’édition.

### <a name="sparklines-in-tables"></a>Graphiques sparkline dans les tableaux

Lorsque StartDate.Month est ajouté en tant que dimension et que les données sont représentées en tant que tendance dans un tableau, il est possible d’afficher des graphiques à barres et des graphiques sparkline dans les cellules du tableau. Positionnez le pointeur de la souris sur le graphique à barres et les graphiques sparkline pour afficher les valeurs des mois individuels.

![Utiliser CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

Pour que les graphiques à barres et les graphiques sparkline apparaissent, la case à cocher « Afficher les graphiques sparkline » en haut de l’éditeur de rapport doit être activée. Cette option permet de sélectionner l’option tendance et de décaler mois vers le bas en tant que dernière dimension, ce qui peut également être accompli en cliquant sur le mois et en utilisant les flèches vers le haut et le bas pour faire défiler date_début. mois vers le haut ou le bas.

### <a name="settings"></a>Paramètres

Le menu paramètres contient des liens vers des pages utiles telles que l’état du système et des pages, et se trouve dans le coin supérieur droit du tableau de bord.

![Utiliser CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

La possibilité d’afficher des descriptions et des horodatages dépend des utilisateurs individuels, et ces paramètres affectent uniquement la version individuelle du tableau de bord et ne le modifient pas. Le fait de vider le cache entraîne le rechargement de toutes les requêtes à partir du cube, tandis que la restauration des valeurs par défaut entraîne la suppression de tous les rapports créés par l’utilisateur ou modifiés, et le recréation du jeu de rapports système : ce qu’un utilisateur peut voir lorsqu’il se connecte pour la première fois.

Le lien Tableau de bord des utilisateurs présente une page contenant la liste des autres utilisateurs de CQD et permet de parcourir leurs rapports. Pour partager un jeu de rapports, copiez le lien dans la barre d’URL et partagez-le avec un autre utilisateur bord. Ce lien est le même que celui que les autres utilisateurs verront dans la page de liens du tableau de bord des utilisateurs sous le nom d’utilisateur de l’utilisateur.

### <a name="supplying-subnet-information"></a>Informations de sous-réseau

Des informations supplémentaires peuvent être révélées si des informations spécifiques au site sont entrées dans la base de données d’archivage afin de fournir des informations de mappage de sous-réseau (par exemple, la qualité d’appel filaire/sans fil par bâtiment).

Pour créer ces rapports, vous devrez au moins remplir les tableaux suivants :

- CqdBuilding
- CqdNetwork

Il est possible de fournir des informations supplémentaires dans les tables CqdBuildingType et CqdBuildingOwnershipType pour affiner le filtrage et l’exploration. 

Les données utilisées pour ces tables sont définies comme suit :

**CqdBuilding**

|Colonne|Type de données|Valeurs null autorisées ?|Détails|
|:-----|:-----|:-----|:-----|
|BuildingKey |int |Non |Clé primaire de la table CqdBuilding. |
|BuildingName |varchar(80) |Non |Nom du bâtiment. |
|BuildingShortName |varchar(10) |Non |Version courte du nom du bâtiment. |
|OwnershipTypeId |int |Non |Clé étrangère, correspond à l’une des entrées de la table CqdBuildingOwners. |
|BuildingTypeId |int |Non |Clé étrangère, correspond à l’une des entrées de la table CqdBuildingType. |
|Latitude |float |Oui |Latitude du bâtiment. |
|Longitude |float |Oui |Longitude du bâtiment. |
|CityName |varchar(30) |Oui |Nom de la localité du bâtiment. |
|ZipCode |varchar(25) |Oui |Code postal du bâtiment. |
|CountryShortCode |varchar(2) |Oui |Codes ISO 3166-1 alpha-2 du pays de résidence du bâtiment. |
|StateProvinceCode |varchar(3) |Oui |Abréviation en trois lettres de l’État ou de la région où se trouve le bâtiment. |
|InsideCorp |bit |Oui |Bit indique si le bâtiment fait partie du réseau d’entreprise. |
|BuildingOfficeType |nvarchar(150) |Oui |Description du type de bureau du bâtiment. |
|Région |varchar(25) |Oui |Région du bâtiment. |
|||||

**CqdNetwork**

|Colonne|Type de données|Valeurs null autorisées ?|Détails|
|:-----|:-----|:-----|:-----|
|Réseau |varchar(25) |Non |Adresse de sous-réseau. |
|NetworkRange |tinyint |Oui |Masque de sous-réseau. |
|NetworkNameID |int |Oui |Le cas échéant, pointe vers une ligne de la table CqdNetworkName. |
|BuildingKey |int |Oui |Clé étrangère, correspond à l’une des entrées de la table CqdBuilding. |
|UpdatedDate |DateHeure |Non |Valeur d’horodatage de la dernière mise à jour de l’entrée. |
||||||

Par défaut, la table suivante comporte une entrée (0, 'inconnu').

**CqdBuildingType**

|Colonne|Type de données|Valeurs null autorisées ?|Détails|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |int |Non |Clé primaire de la table CqdBuildingType. |
|BuildingTypeDesc |char(18) |Non |Description du type de bâtiment. |
|||||

Par défaut, la table suivante comporte une entrée (0, 'inconnu', 0, null).

**CqdBuildingOwnershipType**

|Colonne|Type de données|Valeurs null autorisées ?|Détails|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |int |Non |Clé primaire de la table CqdBuildingOwnershipType. |
|OwnershipTypeDesc |varchar(25) |Non |Description du type d’appartenance. |
|LeaseInd |tinyint |Oui |Index faisant référence à une autre ligne de la table CqdBuildingOwnershipType permettant d’identifier les bâtiments loués. |
|Propriétaire |varchar(50) |Oui |Propriétaire du bâtiment. |
|||||

Par défaut, la table suivante comporte une entrée (0, 'inconnu', 0, null).

**CqdBssid**

|Colonne|Type de données|Valeurs null autorisées ?|Détails|
|:-----|:-----|:-----|:-----|
|bss |nvarchar(50) |Non |Clé primaire de la table CqdBssid . Correspond au BSSID du point d’accès WiFi. |
|ess |nvarchar(50) |Oui |Informations du contrôleur du point d’accès Wi-Fi. |
|phy |nvarchar(50) |Oui |Informations sur Phy. |
|ap |nvarchar(50) |Oui |Nom du point d’accès Wi-Fi. |
|Bâtiment |nvarchar(500) |Oui |Le nom du bâtiment sur lequel se trouve le point d’accès WiFi. |
||||

## <a name="cqd-streams"></a>Flux CQD

Un flux bord est considéré comme bon, médiocre ou non classé. CQM 1.5 utilise désormais la définition CQD suivante :

- Un flux médiocre est une combinaison des métriques d’appels médiocres au-delà du seuil.
- Lorsque le flux d’un appel est médiocre, les deux flux de l’appel présentent un indicateur médiocre. Dans le cadre de conférences, chaque participant est considéré comme un appel unique et est signalé indépendamment de tous les autres.
- Les flux non classés sont des flux sans mesure de qualité (c’est-à-dire des transactions synthétiques ou des appels courts).
- Flux valides = clients non mobiles
- Le classificateur ne peut pas être modifié

**Définition/classificateur d’appel médiocre**

|Mesure|Seuil|
|:-----|:-----|
|DegradationAvg |Supérieur à 1.0 (-1 MOS réseau) |
|RoundTrip |Supérieur à 500  |
|PacketLossRate |Supérieure à 0,1 (10%) |
|JitterInterArrival |Supérieur à 30  |
|RatioConcealedSamplesAvg |Est supérieur à 0,07 |
|||

Définition JPDR = définition appel médiocre moins RatioConcealedSamplesAvg 

## <a name="where-is-callercallee"></a>Où est l’appelant/l’appelé ?

BORD n’utilise pas de champs d’appelant/appelé plutôt qu’il utilise des « premier » et « second », car il existe des étapes intermédiaires entre l’appelant et l’appelé.

 **Tout d’abord** Sera toujours le point de terminaison du serveur (par exemple, MCU AV ou serveur de médiation) si un serveur est impliqué dans le flux.

 **Second** sera toujours le point de terminaison client, sauf s’il s’agit d’un flux serveur-serveur. 

**Exemple de classement de Premier et Second**

|Point de terminaison 1 UAType |Point de terminaison 2 UUAType |Premier|Second|
|:-----|:-----|:-----|:-----|
|2 (AVMCU)  |4 (Skype Entreprise)  |Point de terminaison 1 |Point de terminaison 2 |
|2 (AVMCU)  |1 (mMediationServer)  |Point de terminaison 2 |Point de terminaison 1 |
|4 (Skype Entreprise) |4 (Skype Entreprise)  |Appelant dans MediaLine  |Appelé dans MMediaLine  |
|||||

Si les deux points de terminaison sont du même type, bord effectue d’abord l’entrée d’appelant et l’appelant en second. Pour plus d’informations sur les noms de points de terminaison, voir [ce blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx).

## <a name="accounting-for-vpn"></a>Représentation du réseau VPN

S’il s’agit de la solution VPN, il est possible de définir précisément l’indicateur VPN. Dans le cas contraire, utilisez l’une des méthodes suivantes :

- Créez un type de réseau appelé VPN (préféré), puis associez des sous-réseaux VPN à ce nouveau type.
- Créez un bâtiment appelé VPN, puis associez des sous-réseaux à ce bâtiment. 

## <a name="query-fundamentals"></a>Notions de base sur les requêtes

Une requête correctement formée contient les 3 paramètres suivants : 

- Mesure
- Dimension
- Filtre

Voici un exemple de requête correctement formée : « Afficher les flux médiocres [Mesure] par sous-réseau [Dimension] du bâtiment 6 [Filtre] ».

## <a name="what-does-union-do"></a>Quelles actions réalise UNION ?

Union vous permet de filtrer des conditions avec l’opérateur et. Dans certains cas, vous pouvez combiner plusieurs conditions de filtre pour obtenir un résultat similaire à une opération OR.

Exemple : pour obtenir tous les flux d’un immeuble, UNION fournit une vue distincte du jeu de données fusionné. Pour utiliser UNION, insérez du texte commun dans le champ UNION dans les 2 conditions de filtre souhaitées dans UNION.

## <a name="default-report-breakdown"></a>Répartition du rapport par défaut

Si la connexion sans fil est gérée en interne, vous pouvez recréer les rapports Wireless dans le paquet Managed. 

![Répartition du rapport de tableau de bord de qualité des appels](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>Processus opérationnels

Révisez et corrigez d’abord les flux géré. La qualité dans ce domaine doit être de 100 % dans le cadre de votre contrôle, la remédiation sera donc optimale.

### <a name="managed-streams"></a>Flux gérés 

Examinez et effectuez la remédiation des flux gérés dans l’ordre suivant : 

1. Serveur-serveur 
2.  Serveur-filaire-intérieur
3. Filaire-filaire-intérieur 

### <a name="unmanaged-streams"></a>Flux non gérés

Examinez et effectuez la remédiation des flux non gérés dans l’ordre suivant : 

1. Serveur-Wi-Fi-intérieur
2. Serveur-filaire-extérieur
3. Serveur-Wi-Fi-extérieur
4. Filaire-extérieur-direct
5. Filaire-extérieur-relais
6. Autres non gérés
