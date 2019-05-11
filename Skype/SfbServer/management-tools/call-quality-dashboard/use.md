---
title: Utiliser le tableau de bord appel qualité pour Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 'Résumé : Découvrez comment utiliser le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 91df986e985a9ccfafd17d3fc082e6786ad52657
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915009"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Utiliser le tableau de bord appel qualité pour Skype pour Business Server
 
**Résumé :** Découvrez comment utiliser le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.
  
Le Tableau de bord de la qualité des appels permet aux professionnels de l’informatique d’utiliser des données agrégées pour identifier des secteurs cibles dans leur environnement rencontrant des problèmes de qualité multimédia. Il permet à un professionnel de l’informatique de comparer des statistiques de différents groupes d’utilisateurs et d’identifier des tendances et modèles. Le tableau n’est pas utilisé pour résoudre des problèmes d’appel spécifiques, mais pour identifier les problèmes et les solutions qui concernent de nombreux utilisateurs dans un environnement donné.
  
## <a name="call-quality-dashboard-user-guide"></a>Guide de l’utilisateur Qualité des appels

Le Tableau de bord de la qualité des appels (CQD) est un portail Web qui permet de créer et d’organiser rapidement des rapports basés sur les données de la qualité de l’expérience (QoE). Le CQD déploie un cube SSAS afin de regrouper les données dans la base de données des mesures Qualité de l’expérience (QoE). Cela permet aux utilisateurs de créer et de modifier des rapports, ainsi que d’effectuer des recherches en temps réel. Bien qu’il soit possible d’utiliser Excel pour se connecter directement au cube, le portail est optimisé pour différents flux de travail comprenant des données QoE. Ces données inclut la mise en cache de données de rapport afin de vous faire bénéficier d’un accès rapide aux informations, mais également des liens imbriqués pour le partage et la publication d’informations, des fonctions de création et de modification simplifiées des rapports de données, ainsi que des métadonnées modifiables pour les descriptions de rapport. En outre, CQD propose des API web pour le développement d’accès aux données du cube dans les tableaux de bord personnalisés.  
  
### <a name="feature-overview"></a>Présentation des fonctionnalités

Lorsqu’un utilisateur visite le Tableau de bord de la qualité des appels, voici ce qu’il voit :
  
![Utiliser CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)
  
1. Le volet « Résumé » est où se trouve le contexte de la « rapport définir » (à droite). 
    
2. Propriétés de niveau de jeu de rapport (y compris la hauteur de l’axe des y) peuvent être définies en cliquant sur « Modifier » dans le volet Résumé.
    
3. La Barre de navigation aide les utilisateurs à identifier leur emplacement actuel dans la hiérarchie des rapports.  
    
4. Les rapports possédant des sous-rapports sont indiqués par un lien bleu. Cliquer sur ces liens permet de dérouler la structure des rapports enfants.  
    
Déplacer la souris sur les graphiques à barres et les lignes de tendance permet d’afficher les valeurs détaillées. L’état qui a le focus affiche le menu action : « Modifier », « Clone », « Supprimer » et « Télécharger ». 
  
### <a name="default-reports"></a>Rapports par défaut

Lorsqu’un utilisateur accède au portail CQD pour la première fois, un ensemble de rapports par défaut est créé automatiquement. Ces rapports sont parfois désignés sous le nom de rapports système. L’utilisateur peut librement les modifier ou les supprimer. Généralement, ils servent de base de création de rapports parents ou enfants.  
  
Au niveau supérieur, l’état « Tendance mensuel flux Audio » indique la tendance mensuelle pour tous les flux audio. Déplacer la souris sur les barres d’un graphique affiche une vue plus détaillée des données correspondantes. Cliquez sur le titre du rapport de tendance mensuel du flux Audio atteindre l’état « Géré par rapport à des flux Audio non managé », où les rapports sont divisées entre gérés et non gérés. Les appels gérés sont des appels passés depuis le réseau local filaire au travers d’un pare-feu. Les appels non gérés comprennent les appels passés à l’extérieur du pare-feu et les appels passés sur la connexion Wi-Fi.
  
L’autre rapport de niveau supérieur est appelé le « signalés par les utilisateurs appel qualité évaluation histogramme. » Les classements de la qualité des appels sont des valeurs que les utilisateurs Skype Entreprise attribuent à la fin d’un appel pour indiquer la qualité de celui-ci. Les valeurs attribuées vont de 1 à 5, 1 correspondant à la qualité minimale, et 5 correspondant à la qualité maximale. L’histogramme indique le nombre d’appels audio ayant fait l’objet d’une notation dans un même mois. 
  
En général, cliquer sur le titre d’un des rapports permet d’accéder à des rapports comprenant des filtres supplémentaires appliqués aux données. Dans les rapports système, chaque rapport enfant affiche un sous-ensemble des données disponibles dans le rapport parent. Cette approche de diagnostic simple vise à étendre la recherche des données et tendances posant problème aux sous-rapports pour une efficacité maximale. En créant des sous-rapports, les utilisateurs peuvent vérifier leurs hypothèses en s’appuyant sur des tendances de données propres.
  
### <a name="creating-and-editing-reports"></a>Création et modification de rapports

Lorsque vous cliquez sur « Modifier » dans le menu action d’un état, les utilisateurs voient l’éditeur de rapport. Chaque rapport est complété par une requête effectuée dans le cube. Il s’agit de la visualisation des données renvoyées par la requête. L’Éditeur de rapport est une interface utilisateur permettant de modifier ces requêtes ainsi que les options d’affichage du rapport. Lorsqu’un utilisateur ouvre l’Éditeur de rapport, voici ce qu’il voit :
  
![Utiliser CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)
  
1. Les dimensions, les mesures et les filtres sont sélectionnés dans le volet gauche. Pointant sur une des valeurs existantes affiche un bouton « x » qui permet à la valeur à supprimer. Cliquez sur le bouton « plus » en regard d’un titre s’ouvre la boîte de dialogue pour ajouter une nouvelle dimension, mesure ou un filtre. 
    
2. Les options de personnalisation de graphique figurent en haut.
    
3. L’Éditeur de rapport permet d’afficher un aperçu du rapport.  
    
4. Une description détaillée du rapport peut être créée dans la zone de modification en bas.  
    
### <a name="sparklines-in-tables"></a>Graphiques sparkline dans les tableaux

Lorsque StartDate.Month est ajouté en tant que dimension et que les données sont représentées en tant que tendance dans un tableau, il est possible d’afficher des graphiques à barres et des graphiques sparkline dans les cellules du tableau. Déplacer le pointeur de la souris sur le graphique et les sparklines permet d’afficher les valeurs des mois correspondants.  
  
![Utiliser CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)
  
Pour les graphiques à barres et les graphiques sparkline puisse s’affichent, la case à cocher « Afficher les graphiques sparkline » en haut de l’éditeur de rapport doit être vérifiée. L’option Tendance est alors sélectionnée et le mois devient la dernière dimension, ce qui peut également être effectué manuellement en cliquant sur Mois et en utilisant les flèches vers le haut et vers le bas pour déplacer StartDate.Month dans la direction souhaitée. 
  
### <a name="settings"></a>Paramètres

Dans l’angle supérieur droit du tableau de bord, le menu des paramètres contient des liens vers des pages utiles telles que les pages Intégrité du système et À propos de.
  
![Utiliser CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)
  
Pour afficher les descriptions et horodatage dépend des utilisateurs individuels, et ces paramètres affectent uniquement la version de la personne du tableau de bord, pas ne modifie pas définie le rapport ou voient d’autres utilisateurs. Le vidage du cache entraîne le rechargement des données du cube par les requêtes, tandis que la restauration du paramétrage par défaut supprime les rapports créés ou modifiés par les utilisateurs et recrée les rapports système, c’est-à-dire les ressources qui sont proposées à l’utilisateur lors de la connexion initiale.
  
Le lien Tableau de bord des utilisateurs présente une page contenant la liste des autres utilisateurs de CQD et permet de parcourir leurs rapports. Pour partager un ensemble de rapports avec un utilisateur, il suffit de copier le lien dans une barre d’URL. Ce lien sera la même que celui autres que les utilisateurs se voir dans la page lien de tableau de bord d’utilisateurs sous le nom d’utilisateur.
  
### <a name="supplying-subnet-information"></a>Informations de sous-réseau

L’injection d’informations mettant en correspondance le sous-réseau et les bâtiments dans la base de données Archive permet d’apporter des éclairages supplémentaires (par ex. la qualité des appels filaires/sans fil selon les bâtiments du site).  
  
La création de ces rapports implique le remplissage des tables suivantes :
  
- CqdBuilding
    
- CqdNetwork
    
Il est possible de fournir des informations supplémentaires dans les tables CqdBuildingType et CqdBuildingOwnershipType pour affiner le filtrage et l’exploration.  
  
Le schéma de ces tables se présente ainsi :
  
**CqdBuilding**

|**Colonne**|**Type de données**|**Valeurs null autorisées ?**|**Détails**|
|:-----|:-----|:-----|:-----|
|BuildingKey  <br/> |int  <br/> |Non  <br/> |Clé primaire de la table CqdBuilding.  <br/> |
|BuildingName  <br/> |varchar(80)  <br/> |Non  <br/> |Nom du bâtiment.  <br/> |
|BuildingShortName  <br/> |varchar(10)  <br/> |Non  <br/> |Version courte du nom du bâtiment.  <br/> |
|OwnershipTypeId  <br/> |int  <br/> |Non  <br/> |Clé étrangère qui doit correspondre à l’une des entrées de la table CqdBuildingOwners.  <br/> |
|BuildingTypeId  <br/> |int  <br/> |Non  <br/> |Clé étrangère qui doit correspondre à l’une des entrées de la table CqdBuildingType.  <br/> |
|Latitude  <br/> |float  <br/> |Oui  <br/> |Latitude du bâtiment.  <br/> |
|Longitude  <br/> |float  <br/> |Oui  <br/> |Longitude du bâtiment.  <br/> |
|CityName  <br/> |varchar(30)  <br/> |Oui  <br/> |Nom de la localité du bâtiment.  <br/> |
|ZipCode  <br/> |varchar(25)  <br/> |Oui  <br/> |Code postal du bâtiment.  <br/> |
|CountryShortCode  <br/> |varchar(2)  <br/> |Oui  <br/> |Codes ISO 3166-1 alpha-2 du pays de résidence du bâtiment.  <br/> |
|StateProvinceCode  <br/> |varchar(3)  <br/> |Oui  <br/> |Abréviation de trois lettres correspondant à l’État ou à la province du bâtiment.  <br/> |
|InsideCorp  <br/> |bit  <br/> |Oui  <br/> |Bit indiquant si le bâtiment fait partie d’un réseau d’entreprise.  <br/> |
|BuildingOfficeType  <br/> |nvarchar(150)  <br/> |Oui  <br/> |Description du type de bureau du bâtiment.  <br/> |
|Région  <br/> |varchar(25)  <br/> |Oui  <br/> |Région du bâtiment.  <br/> |
   
**CqdNetwork**

|**Colonne**|**Type de données**|**Valeurs null autorisées ?**|**Détails**|
|:-----|:-----|:-----|:-----|
|Réseau  <br/> |varchar(25)  <br/> |Non  <br/> |Adresse de sous-réseau.  <br/> |
|NetworkRange  <br/> |tinyint  <br/> |Oui  <br/> |Masque de sous-réseau.  <br/> |
|NetworkNameID  <br/> |int  <br/> |Oui  <br/> |Le cas échéant, pointe vers une ligne de la table CqdNetworkName.  <br/> |
|BuildingKey  <br/> |int  <br/> |Oui  <br/> |Clé étrangère qui doit correspondre à l’une des entrées de la table CqdBuilding.  <br/> |
|UpdatedDate  <br/> |DateHeure  <br/> |Non  <br/> |Valeur d’horodatage de la dernière mise à jour de l’entrée.  <br/> |
   
Par défaut, le tableau suivant a une entrée ('Inconnu' 0).
  
**CqdBuildingType**

|**Colonne**|**Type de données**|**Valeurs null autorisées ?**|**Détails**|
|:-----|:-----|:-----|:-----|
|BuildingTypeId  <br/> |int  <br/> |Non  <br/> |Clé primaire de la table CqdBuildingType.  <br/> |
|BuildingTypeDesc  <br/> |char(18)  <br/> |Non  <br/> |Description du type de bâtiment.  <br/> |
   
Par défaut, le tableau suivant avec une seule entrée (0, 'inconnu', 0, null).
  
**CqdBuildingOwnershipType**

|**Colonne**|**Type de données**|**Valeurs null autorisées ?**|**Détails**|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId  <br/> |int  <br/> |Non  <br/> |Clé primaire de la table CqdBuildingOwnershipType.  <br/> |
|OwnershipTypeDesc  <br/> |varchar(25)  <br/> |Non  <br/> |Description du type d’appartenance.  <br/> |
|LeaseInd  <br/> |tinyint  <br/> |Oui  <br/> |Index faisant référence à une autre ligne de la table CqdBuildingOwnershipType permettant d’identifier les bâtiments loués.  <br/> |
|Propriétaire  <br/> |varchar(50)  <br/> |Oui  <br/> |Propriétaire du bâtiment.  <br/> |
   
Par défaut, le tableau suivant avec une seule entrée (0, 'inconnu', 0, null).
  
**CqdBssid**

|**Colonne**|**Type de données**|**Valeurs null autorisées ?**|**Détails**|
|:-----|:-----|:-----|:-----|
|bss  <br/> |nvarchar(50)  <br/> |Non  <br/> |Clé primaire de la table CqdBssid . BSSID du point d’accès Wi-FI.  <br/> |
|ess  <br/> |nvarchar(50)  <br/> |Oui  <br/> |Informations du contrôleur du point d’accès Wi-Fi.  <br/> |
|phy  <br/> |nvarchar(50)  <br/> |Oui  <br/> |Informations sur Phy.  <br/> |
|ap  <br/> |nvarchar(50)  <br/> |Oui  <br/> |Nom du point d’accès Wi-Fi.  <br/> |
|Bâtiment  <br/> |nvarchar(500)  <br/> |Oui  <br/> |Nom du bâtiment dans lequel est situé le point d’accès Wi-Fi.  <br/> |
   
## <a name="cqd-streams"></a>Flux CQD

Un flux CQD peut être satisfaisant, médiocre ou non classé. CQM 1.5 utilise désormais la définition CQD suivante :  
  
- Un flux médiocre correspond à une combinaison de mesures d’appel médiocre dépassant un seuil.
    
- Lorsqu’un flux dans un appel est médiocre, les deux flux de l’appel est médiocres avec indicateur. Dans les conférences, chaque participant est considérée comme un appel unique et est indiqué sur indépendamment de tous les autres.
    
- Les flux non classés ne comprennent aucune mesure de qualité (transactions synthétiques, appels de courte durée).
    
- Flux valides = clients non mobiles
    
- Le classificateur ne peut pas être modifié
    
**Définition/classificateur d’appel médiocre**

|**Mesure**|**Seuil**|
|:-----|:-----|
|DDegradationAvg  <br/> |Supérieur à 1.0 (-1 MOS réseau)  <br/> |
|RoundTrip  <br/> |Supérieur à 500   <br/> |
|PacketLossRate  <br/> |Supérieur à .1 (10 %)   <br/> |
|JitterInterArrival  <br/> |Supérieur à 30   <br/> |
|RRatioConcealedSamplesAvg  <br/> |Supérieur à .07   <br/> |
   
Définition JPDR = définition appel médiocre moins RatioConcealedSamplesAvg  
  
## <a name="where-is-callercallee"></a>Où est l’appelant/l’appelé ?

CQD n’utilise pas les champs de l’appelant/appelé. Ces ont été renommées « Premier » et « Seconde », car il existe des étapes intermédiaires entre l’appelant et l’appelé.
  
 **Premier** sera toujours le point de terminaison du serveur (par ex. : AV MCU ; serveur de médiation) si un serveur est impliqué dans le flux.
  
 **Second** sera toujours le point de terminaison client, sauf s’il s’agit d’un flux serveur-serveur. 
  
**Exemple de classement de Premier et Second**

|**Point de terminaison 1 UAType **|**Point de terminaison 2 UUAType **|**Premier** sera toujours le point de terminaison du serveur (par ex.|**Second**|
|:-----|:-----|:-----|:-----|
|2 (AVMCU)   <br/> |4 (Skype Entreprise)   <br/> |Point de terminaison 1  <br/> |Point de terminaison 2  <br/> |
|2 (AVMCU)   <br/> |1 (mMediationServer)   <br/> |Point de terminaison 2  <br/> |Point de terminaison 1  <br/> |
|4 (Skype Entreprise)  <br/> |4 (Skype Entreprise)   <br/> |Appelant dans MediaLine   <br/> |Appelé dans MMediaLine  <br/> |
   
Si les deux points de terminaison sont de même type, CQD convertira l’entrée Appelant en Premier et l’Appelé deviendra Second. Consultez [ce blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx) pour plus d’informations.
  
## <a name="accounting-for-vpn"></a>Représentation du réseau VPN

Si la solution VPN est connue pour définir correctement indicateur VPN, vous pouvez commencer. Si ce n’est pas le cas, utilisez l’une des méthodes ci-dessous :
  
- Créez un type de réseau appelé VPN (préféré), puis associez des sous-réseaux VPN à ce nouveau type.
    
- Créez un bâtiment appelé VPN, puis associez des sous-réseaux à ce bâtiment.  
    
## <a name="query-fundamentals"></a>Notions de base sur les requêtes

Une requête correctement formée contient les 3 paramètres suivants :  
  
- Mesure
    
- Dimension
    
- Filtre
    
Voici un exemple de requête correctement formée : « Afficher les flux médiocres [Mesure] par sous-réseau [Dimension] du bâtiment 6 [Filtre] ».
  
## <a name="what-does-union-do"></a>Quelles actions réalise UNION ?

Union vous permet de filtrer des conditions à l’aide de l’opérateur ET. Vous devez parfois combiner plusieurs conditions de filtre pour obtenir un résultat de type OU.
  
Par exemple : si vous devez obtenir tous les flux d’un bâtiment, UNION fournira une vue différente de l’ensemble de données fusionnées. Pour utiliser UNION, insérez du texte commun dans le champ UNION dans les 2 conditions de filtre souhaitées dans UNION.  
  
## <a name="default-report-breakdown"></a>Répartition du rapport par défaut

Si la connexion sans fil est gérée en interne, vous pouvez recréer les rapports Wireless dans le paquet Managed.  
  
![Répartition du rapport de tableau de bord de qualité des appels](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)
  
## <a name="operational-processes"></a>Processus opérationnels

Commencez par examiner les flux gérés et effectuer leur remédiation. La qualité dans ce domaine doit être de 100 % dans le cadre de votre contrôle, la remédiation sera donc optimale.  
  
### <a name="managed-streams"></a>Flux gérés 

Examinez et effectuez la remédiation des flux gérés dans l’ordre suivant :  
  
1. Serveur-serveur  
    
2.   Serveur-filaire-intérieur
    
3. Filaire-filaire-intérieur  
    
### <a name="unmanaged-streams"></a>Flux non gérés

Examinez et effectuez la remédiation des flux non gérés dans l’ordre suivant :  
  
1. Serveur-Wi-Fi-intérieur
    
2. Serveur-filaire-extérieur
    
3. Serveur-Wi-Fi-extérieur
    
4. Filaire-extérieur-direct
    
5. Filaire-extérieur-relais
    
6. Autres non gérés
    

