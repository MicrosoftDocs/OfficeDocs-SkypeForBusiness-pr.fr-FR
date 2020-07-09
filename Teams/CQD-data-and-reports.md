---
title: Données et rapports dans le tableau de bord de qualité des appels (bord)
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: En savoir plus sur les données et les rapports disponibles dans le tableau de bord de qualité des appels Microsoft (bord).
ms.openlocfilehash: 02acff8cd423901c8959e94af664ffe4d43c0e51
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086017"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Données et rapports dans le tableau de bord de qualité des appels (bord)

Le tableau de bord de qualité des appels Microsoft (bord) utilise un flux de données en temps réel (NRT). Les enregistrements d’appels sont disponibles dans bord dans un délai de 30 minutes à compter de la fin d’un appel. Les enregistrements d’appels à partir du pipeline NRT sont uniquement disponibles pendant quelques mois avant d’être supprimés du jeu de données. 


> [!NOTE]
> Advanced bord (nouveauté du 2019 novembre) fusionne les données de l’ancien pipeline bord (qui rend les enregistrements disponibles dans environ 24 heures) avec les données NRT du pipeline bord avancé. Les requêtes sur les portails plus anciens et avancés pour les données de la période d’archivage produisent les mêmes résultats. Les requêtes sur l’un ou l’autre des portails pour les données de NRT et NRT données + EUII périodes seront différentes.

## <a name="many-ways-to-access-cqd-data"></a>Différentes façons d’accéder à des données bord

Vous pouvez accéder aux données de la bord à l’aide de plusieurs voies différentes. Sélectionnez celle qui correspond le mieux à vos besoins :

|  |  |
|---------|---------|
|Centre d’administration teams [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)    | Les données bord sont incluses dans la page **utilisateurs** du centre d’administration Teams, affichant les données les plus courantes dont vous avez besoin dans un format facile à lire. Vous ne pouvez pas personnaliser les données bord que vous trouvez sous **utilisateurs**.  |
|Portail bord [( https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)     | Rapports synthétiques et détaillés qui répondent à la plupart des besoins, grâce au filtrage approfondi. Vous pouvez également personnaliser les rapports dans le portail bord. <br><br>Obtenez deux [modèles de rapports bord](#import-the-cqd-report-templates) pour vous aider à analyser des données dans le portail bord.       |
|Power BI     | Utiliser des requêtes directes pour afficher vos données bord dans Power BI à l’aide de [modèles Power bi personnalisables](CQD-Power-BI-query-templates.md). [Téléchargez les modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).<br><br>Vous pouvez également [utiliser l’API REST pour accéder à des données bord](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) via Power bi. Utilisez cette méthode si vous souhaitez télécharger vos données bord pour pouvoir travailler dessus en mode hors connexion. L’avantage de l’utilisation de cette méthode est de meilleures performances, particulièrement utiles pour les jeux de données volumineux qui s’en trouvent dans Power BI lorsque vous êtes en ligne.       |
|API Graph     | Accédez vous-même aux données de qualité d’appel à l’aide de l' [API graphique](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta). Il s’agit de la méthode la plus complexe, mais elle vous permet d’analyser vos données de qualité d’appel avec le plus de contrôle et de flexibilité. Par exemple, si vous devez le joindre à d’autres données pour votre organisation, vous pouvez utiliser l’API de graphique pour créer un modèle de données et incorporer des données de qualité d’appel.        |

## <a name="import-the-cqd-report-templates"></a>Importer les modèles de rapports bord

Téléchargez [deux modèles de rapports bord](https://aka.ms/qertemplates) (tous les réseaux et réseaux gérés) pour vous aider à être rapidement opérationnel avec bord. Le modèle tous les réseaux, bien qu’optimisé pour fonctionner avec un fichier de données bâtiment, peut être utilisé lorsque vous travaillez dans le cadre de la collecte et du chargement d’informations de bâtiment dans bord, comme décrit dans la section suivante.

**Pour importer les modèles (. CQDX) dans bord**

1. Dans bord, sélectionnez **rapports détaillés** dans le menu en haut de la page.

2. Dans le volet gauche, sélectionnez **Importer**. Naviguez jusqu’au premier modèle CQDX et sélectionnez **Open (ouvrir**).

3. Une fois le modèle chargé, une fenêtre contextuelle affiche le message « l’importation du rapport a réussi ». 

4. Répétez les étapes 2 et 3 pour le deuxième modèle bord.

> [!NOTE]
> Chaque utilisateur doit importer les modèles bord dans son instance bord. 



## <a name="euii-data"></a>Données EUII

Pour des raisons de conformité, les données d’identification de l’utilisateur final (également appelées informations d’identification personnelle ou PII) sont conservées pendant 30 jours. Les données NRT qui se trouvent dans la marque de 30 jours, les champs qui contiennent EUII sont effacés, ce qui crée des données NRT EUII gratuites. Les champs qui contiennent des données EUII sont les suivants :

- Adresse IP complète
- Adresse de contrôle d’accès au média (MAC)
- Identificateur de l’ensemble de services standard (BSSID)
- URI SIP (Session Initiation Protocol) (Skype entreprise uniquement)
- Nom d’utilisateur principal (UPN)
- Nom du point de terminaison de l’ordinateur
- Commentaires textuels de l’utilisateur
- ID d’objet (ID d’objet Active Directory de l’utilisateur du point de terminaison);

### <a name="admin-roles-with-and-without-euii-access"></a>Rôles d’administrateur avec et sans accès EUII

Ces [RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) rôles RBAC **DO** disposent d’un accès EUII :
- Administrateur général
- Administrateur de service teams
- Administrateur de communications teams
- Ingénieur du support technique pour les communications Teams
- Lecteur global
- Administrateur Skype entreprise

Ces rôles RBAC **ne disposent pas** de l’accès EUII :
- Lecteur de rapports
- Spécialiste du support des communications teams


## <a name="date-controls"></a>Contrôles de date

BORD prend en charge les types de tendances de roulement suivants :

- 5 jours
- 7 jours
- 30 jours
- 60-jour
- 90-jour

Le paramètre de date URL accepte un champ Day. Rapports d’une journée à l’aide de dates spécifiées au format AAAA-MM-JJ comme dernier jour de la tendance. Le paramètre de date d’URL « 00 » indique « aujourd’hui ».

|URL| Date de fin de la tendance du jour de roulement|
|:---|:---|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /2019-02/</span>   |Jour actuel en février 2019|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /2019-02-15/</span>|15 février 2019|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /00/</span>        |Jour actuel|
|||

Par défaut, le jour du mois actuel est utilisé comme dernier jour de la tendance du jour de roulement.


## <a name="data-available-in-cqd-reports"></a>Données disponibles dans les rapports bord

Il est possible que vous deviez gérer la qualité de l’appel de votre organisation par défaut, résumé et bord détaillé. Le cas échéant, vous pouvez [créer des rapports personnalisés](#create-custom-detailed-reports). 

Si vous souhaitez utiliser Power BI pour analyser vos données bord, lisez [Utilisez Power bi pour analyser les données bord pour teams](CQD-Power-BI-query-templates.md).

|Fonctionnalité|Rapports de synthèse|Rapports détaillés|
|:--- |:--- |:--- |
|Métrique du partage d’application | Non | Oui |
|Support des informations sur le bâtiment du client | Oui | Oui  |
|Support technique des informations de point de terminaison client | Uniquement dans <span> CQD.Teams.Microsoft.com<span/> | Uniquement dans <span> CQD.Teams.Microsoft.com<span/> |
|Prise en charge de l’analyse approfondie   | Non   | Oui   |
|Mesures de fiabilité des médias   | Non   | Oui   |
|Rapports prêts à l’emploi   | Oui   | Oui    |
|Présentation des rapports   | Oui   | Oui    |
|Ensemble de rapports par utilisateur   | Non   | Oui   |
|Personnalisation d’un ensemble de rapports (ajout, suppression, modification des rapports)   | Non   | Oui   |
|Métriques de partage d’écran vidéo   | Non   | Oui   |
|Métriques vidéo   | Non   | Oui   |
|Volume de données disponible   | 12 derniers mois   | 12 derniers mois   |
|Données de Microsoft teams   | Oui   | Oui    |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a>Sélectionner des données de produits à afficher dans les rapports

Dans la liste déroulante des rapports de synthèse et de géolocalisation, vous pouvez utiliser la liste déroulante du **filtre produit** pour afficher toutes les données de produit, uniquement les données de Microsoft Teams, ou uniquement les données de Skype entreprise online.
  
![Capture d’écran : affiche les options de contrôle du filtre de produit](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Dans les rapports détaillés, vous pouvez utiliser la dimension **is teams** pour filtrer les données sur les données de Microsoft teams ou de Skype entreprise online.

## <a name="summary-reports"></a>Rapports de synthèse

Voici les rapports qui s’affichent dans le tableau de bord bord lorsque vous vous connectez pour la première fois à bord. Ils vous donnent une vue d’ensemble des tendances de qualité avec des rapports quotidiens, mensuels et de tableau pour vous aider à identifier les sous-réseaux présentant une qualité médiocre. 

|Délimité  |  |
|---------|---------|
|La qualité d’appel globale     | Agrégation d’autres trois onglets        |
|Serveur — client     |Détails des flux entre les points de terminaison serveur et client         |
|Client — client     |Détails des flux entre deux points de terminaison client         |
|SLA de qualité vocale     |Plus d’informations sur les appels inclus dans le [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) de qualité vocale de Skype entreprise         |

### <a name="overall-call-quality-tab"></a>Onglet qualité globale des appels

Utilisez les données de cet onglet pour évaluer l’État et les tendances de la qualité des appels en fonction du nombre de flux et de faibles pourcentages. La légende dans le coin supérieur droit montre la couleur et les éléments visuels qui représentent ces métriques.
  
![Capture d’écran : afficher l’onglet qualité des appels](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Les flux sont classés en trois groupes : bon, médiocre et non classés. Il existe également des valeurs de *pourcentage médiocres* calculées qui vous permettent d’obtenir le rapport entre les flux considérés *médiocres* et le nombre total de flux classés. Depuis un pourcentage médiocre de mauvaises *chaînes/(mauvais flux + Good Streams) * 100*, le *% médiocre* n’est pas affecté par la présence de plusieurs flux non *classés* . Pour déterminer le classement d’un flux comme médiocre ou satisfaisant, voir [Classification de flux dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md).
  
Utilisez l’échelle de gauche pour mesurer les valeurs de nombre de flux.
  
![Capture d’écran : affiche les valeurs de nombre de flux](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Servez-vous de l’échelle de droite pour mesurer les valeurs de pourcentage médiocres.
  
![Capture d’écran : affiche les valeurs% médiocres](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Vous pouvez également obtenir les valeurs numériques réelles en plaçant le pointeur de la souris sur une barre.
  
> [!NOTE]
> L’exemple suivant provient d’un jeu de données de très petite taille et les valeurs ne sont pas réalistes pour un déploiement réel.
  
![Capture d’écran : affiche le pointeur de la souris pour accéder aux données](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Le volume de flux global permet de déterminer le degré de pertinence des pourcentages médiocres. Plus le volume des flux globaux est faible, plus la fiabilité du pourcentage signalé est faible.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Onglets serveur-client et client-client

Ces deux onglets fournissent des détails sur les flux ayant eu lieu dans leurs scénarios de point de terminaison. L’onglet serveur-client comporte quatre sections pliantes qui représentent quatre scénarios dans lesquels les flux multimédias seront acheminés.
  
- Connecté (e)
- Câblé extérieur
- WiFi interne
- WiFi extérieur

De même, l’onglet client-client comporte cinq sections réductibles :

- Connecté (e), à l’intérieur
- Connecté (e), à l’extérieur
- Câblé extérieur-filaire
- Connecté (e) dans le WiFi
- Connecté (e), WiFi extérieur

#### <a name="inside-versus-outside"></a>Intérieur et extérieur

BORD classifie un flux comme *à l’intérieur* ou à l' *extérieur* en utilisant des informations de bâtiment s’il existe. Les points de terminaison de chaque flux sont associés à une adresse de sous-réseau. Si le sous-réseau figure dans la liste des sous-réseaux marqués dans l’entreprise dans les informations de bâtiment téléchargées, il est considéré comme *à l’intérieur*. Si les informations de bâtiment n’ont pas encore été chargées, le test interne les classifie toujours en tant qu' *extérieur*. 

Le test interne d’un scénario serveur-client considère uniquement le point de terminaison client. Étant donné que les serveurs sont toujours extérieurs du point de vue d’un utilisateur, ce n’est pas pris en compte dans le test.
  
#### <a name="wired-versus-wifi"></a>Câble filaire et WiFi

Étant donné que les noms indiquent, les critères de classification sont basés sur le type de connexions client. Le serveur est toujours câblé et n’est pas inclus dans le calcul. Dans un flux donné, si l’un des deux points de terminaison est connecté à un réseau WiFi, bord le considère comme WiFi.
> [!NOTE]
> À partir d’un flux, si l’un des deux points de terminaison est connecté à un réseau WiFi, il est considéré comme WiFi dans bord.
  
  
## <a name="tenant-data-information"></a>Informations de données client

Le tableau de bord des rapports de synthèse de bord inclut une page de **téléchargement de données de client** accessible en sélectionnant télécharger les **données client** dans le menu paramètres dans le coin supérieur droit. Cette page permet aux administrateurs de télécharger leurs propres informations, par exemple :

- Carte d’adresse IP et informations géographiques
- Carte de chaque point d’accès sans fil et son adresse MAC
- Carte de point de terminaison à marque/modèle/type de point de terminaison, etc.
  
Nous vous recommandons de télécharger vos données de client, de bâtiment et d’emplacement de sorte que bord puisse inclure ces informations dans vos rapports. Si vous n’avez pas encore téléchargé ces données, voir [Télécharger le client et générer des données](CQD-upload-tenant-building-data.md). 


## <a name="detailed-reports"></a>Rapports détaillés

|Nom  |  |
|---------|---------|
|Rapports d’emplacement améliorés     |Affiche des tendances en fonction de l’emplacement. Ce rapport s’affiche uniquement si vous avez [téléchargé les données de votre client](CQD-upload-tenant-building-data.md).        |
|Rapports de fiabilité     |Inclut des rapports audio, vidéo, de partage d’écran vidéo (VBSS) et de partage d’application         |
|Rapports sur la qualité des performances     |Qualité audio et fiabilité de tous les clients et appareils, y compris les salles de réunion. Ces rapports constituent une version « allégée » des [modèles bord](https://aka.ms/QERtemplates)téléchargeables, qui s’intéresse à l’analyse de la qualité et de la fiabilité du son.         |
|Rapports analyse qualité     | Explorer les niveaux inférieurs : date par région, emplacements, sous-réseaux, heure et utilisateurs         |
|Échec analyse approfondie des États     | Explorer les niveaux inférieurs : date par région, emplacements, sous-réseaux, heure et utilisateurs        |
|Évaluer mes rapports d’appel     |Analyser les évaluations des appels utilisateur par région, par emplacement ou par utilisateur. Inclut des commentaires à la fois.         |
|Rapports du support technique     |Rapports du support technique observez les données des appels et des réunions des utilisateurs individuels, des groupes d’utilisateurs ou de tout le monde. Grâce à l’intégration de données de bâtiment et de EUII, ces rapports permettent d’identifier les problèmes système possibles en fonction de l’emplacement du réseau, des détails de la Conférence, des appareils ou du microprogramme.         |
|Rapports sur la version du client     |Résumé de la version du client : afficher les sessions et les utilisateurs pour chaque version de l’application cliente<br><br>Version cliente par l’utilisateur : afficher les noms d’utilisateurs pour chaque version de l’application cliente <br><br>Les filtres prédéfinis pour le type produit et client permettent de focaliser les versions sur des clients spécifiques.         |
|Rapports de points de terminaison     |Affiche la qualité d’appel par les points de terminaison de l’ordinateur (marque et modèle de l’ordinateur). Ces rapports incluent la création de données, si vous les avez téléchargées.         |


## <a name="create-custom-detailed-reports"></a>Créer des rapports détaillés personnalisés

Si les rapports bord par défaut ne répondent pas à vos besoins, utilisez ces instructions pour créer un rapport personnalisé. Vous devez [utiliser les rapports Power bi pour bord ](cqd-power-bi-query-templates.md). 2020

Dans la liste déroulante des rapports en haut de l’écran qui s’affiche dans \( la **Summary Reports** fenêtre de connexion \) , sélectionnez **rapports détaillés** , puis **nouveau**. Cliquez sur **modifier** dans un rapport pour afficher l’éditeur de requête. Chaque rapport est complété par une requête effectuée dans le cube. Il s’agit de la visualisation des données renvoyées par la requête. L’éditeur de requête vous permet de modifier ces requêtes et les options d’affichage du rapport.
> [!IMPORTANT]
> La plage réseau peut être utilisée pour représenter un super-réseau (combinaison de plusieurs sous-réseaux avec un seul préfixe de routage). Les nouveaux chargements de construction seront examinés pour toutes les plages qui se chevauchent. Si vous avez déjà téléchargé un fichier de construction, vous devez télécharger le fichier actif et le télécharger à nouveau pour identifier les chevauchements et résoudre le problème avant de le télécharger à nouveau. Tout chevauchement dans les fichiers précédemment téléchargés risque de provoquer des mappages incorrects de sous-réseaux sur les bâtiments dans les rapports. Certaines implémentations de réseau privé virtuel n’indiquent pas exactement les informations de sous-réseau. Lorsque vous ajoutez un sous-réseau VPN au fichier de construction au lieu d’une entrée pour le sous-réseau, nous vous conseillons d’ajouter des entrées distinctes pour chaque adresse du sous-réseau VPN en tant que réseau 32 différent. Chaque ligne peut avoir les mêmes métadonnées de bâtiment. Par exemple, au lieu d’une ligne pour 172.16.18.0/24, vous devez disposer de lignes 256, avec une ligne pour chaque adresse entre 172.16.18.0/32 et 172.16.18.255/32, inclusive.
>
> La colonne RPV est facultative et utilise par défaut la valeur 0.  Si la valeur de la colonne VPN est définie sur 1, le sous-réseau représenté par cette ligne sera entièrement étendu pour correspondre à toutes les adresses IP au sein du sous-réseau.  N’hésitez pas à utiliser cette fonction et uniquement pour les sous-réseaux VPN dans la mesure où le développement complet de ces sous-réseaux aura un impact négatif sur les requêtes de création de données.

Pointez sur les graphiques à barres et les courbes de tendance dans le rapport pour afficher les valeurs détaillées. Le rapport sur lequel le focus est affiché affiche le menu d’action : **modifier**, **cloner**, **supprimer**, **Télécharger**et **exporter l’arborescence du rapport**.



## <a name="query-filters"></a>Filtres de requête

Les filtres de requête sont implémentés à l’aide de l’éditeur de requête dans bord. Ces filtres sont utilisés pour réduire le nombre d’enregistrements renvoyés par bord, ce qui a pour effet de limiter les temps d’exécution des requêtes et de la taille globale du rapport. Cela est particulièrement utile pour filtrer les réseaux non gérés. Les filtres répertoriés dans le tableau suivant utilisent des expressions régulières (RegEx).


| Filtre         | Description          | Exemple de filtre de requête bord      |
|----------------|----------------------|-------------------------------|
| Pas de valeurs non renseignées   | Certains filtres n’ont pas la possibilité de filtrer les valeurs vides. Pour filtrer les valeurs vides manuellement, utilisez l’expression vide et définissez le filtre sur égal à ou différent de selon vos besoins.      | Nom du deuxième bâtiment \<\> \^ \\\*\$                       |
| Exclure les sous-réseaux courants | Si vous n’avez pas de fichier de construction valide pour séparer la gestion de réseaux non gérés, les réseaux domestiques seront inclus dans les rapports. Ces sous-réseaux personnels se trouvent en dehors de la portée du contrôle et peuvent être rapidement exclus d’un rapport. Les sous-réseaux courants, tels que définis dans ce guide, sont 10.0.0.0, 192.168.1.0 et 192.168.0.0. | Deuxième sous-réseau \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Affichage intérieur uniquement  | Utilisé pour filtrer un rapport pour une gestion (interne) ou non gérée (à l’extérieur). Le modèle bord géré est déjà préconfiguré avec ces filtres.       | Deuxième dans l’entreprise = intérieur        |

## <a name="report-filters"></a>Filtres de rapport

Utilisez les filtres de rapport bord pour affiner votre investigation. Utilisez des filtres de rapport en ajoutant un filtre au rapport restitué dans l’éditeur de requête ou directement dans le rapport. Les filtres de rapport suivants sont utilisés dans les [modèles bord](https://aka.ms/QERtemplates).


| Filtre     | Description                            | Exemple de filtre de rapport bord         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Commencez par l’année, puis mois. | 2017-10                           |
| Alphabétique | Filtre tout caractère alphabétique. | [a-z]                             |
| Numériques    | Filtre tout caractère numérique.    | [0-9]                             |
| Pourcentage | Filtres pour un pourcentage.              | ([3-9] \\ .) \| ([3-9]) \| ([1-9] [0-9]) |


### <a name="drill-down-filters"></a>Filtres d’exploration

Les rapports bord disposent de plusieurs filtres d’exploration, qui sont des outils puissants pour affiner l’intérêt de vos enquêtes de qualité d’appel. Si vous sélectionnez un champ d’exploration, le rapport ouvre automatiquement l’onglet approprié et filtre sur la valeur sélectionnée. Si cet onglet dispose de ses propres champs d’exploration et qu’un de ceux-ci est sélectionné, les deux jeux de filtres sont appliqués, ce qui permet de réduire progressivement le jeu de données résultant.

![Diagramme illustrant le flux de rapport d’exploration](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a>Ajout et modification de champs d’exploration

Lorsque vous modifiez un rapport, vous avez la possibilité de spécifier les champs d’exploration de votre choix à l’aide de l’éditeur de requête.

Commencez par cliquer sur **...** pour le rapport que vous souhaitez modifier, puis sélectionnez **modifier**.

![Capture d’écran de la modification d’un champ d’exploration](media/qerguide-image-addeditdrilldownfields.png)

Sélectionnez une dimension dans la liste située dans la partie gauche de l’éditeur de requête. Cliquez ensuite sur la liste déroulante située sous la section **accéder à** l’étiquette et sélectionnez l’onglet et le groupe de extensionsurs pour lesquels vous souhaitez effectuer la recherche. Remarque : pour l’instant, la fonctionnalité d’exploration des niveaux inférieurs ne fonctionne que lorsque vous naviguez vers d’autres onglets. La prise en charge de l’extraction d’un développeur spécifique sera ajoutée ultérieurement. Enfin, cliquez sur **Fermer** pour enregistrer vos modifications dans la dimension, puis cliquez sur **Enregistrer** pour enregistrer et fermer l’éditeur de requête.

![Capture d’écran de la sélection d’une dimension dans l’éditeur de requête](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Filtres de sélection multiple

Outre la fonctionnalité d’exploration des niveaux inférieurs, bord prend également en charge la spécification de filtres avec plusieurs valeurs (ou filtres).

Pour sélectionner plusieurs valeurs de filtre, commencez par ajouter un nouveau filtre au rapport. Cliquez sur **+** l’étiquette **filtres** , entrez le nom de la dimension que vous voulez utiliser, puis cliquez sur **Ajouter**.

![Capture d’écran de l’ajout d’un filtre de sélection multiple](media/qerguide-image-addmultiselectfilter.png)

Ensuite, cliquez sur **recherche** (icône en forme de loupe en regard du nouveau filtre). Un champ de texte s’affiche, ainsi qu’un certain nombre d’options, notamment **tout sélectionner** et **inverser**. Entrez une valeur, puis cliquez sur **Rechercher** en regard de ce champ pour effectuer une recherche. Vous pouvez aussi laisser le champ de texte vide et cliquer sur **Rechercher** pour afficher les premières options 100.

```PowerShell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Example  

![Capture d’écran de l’ajout d’un filtre de requête](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filtres de niveau de tableau de bord
Certains rapports bord possèdent des filtres au niveau du tableau de bord, ce qui permet de les filtrer facilement selon les paramètres courants. Ces filtres s’affichent en dehors des onglets de rapport standard, juste en dessous du filtre produit, et s’appliquent à tous les filtres du tableau de bord.

![Capture d’écran d’un filtre de tableau de bord](media/qerguide-image-dashboardfilters.png)
```PowerShell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>Filtres d’URL

BORD prend en charge l’ajout de filtres à l’URL. Ainsi, il est facile de partager ou de marquer une requête bord. Vous pouvez définir des paramètres dans l’URL, tels que le mois de tendance, l’ID de locataire ou la langue. Vous pouvez également ajouter des filtres de produit ou de niveau de tableau de bord à l’URL.
L’exclusion des données fédérées des rapports bord est utile lorsque vous changez de bâtiment ou de réseau dans lequel les points de terminaison fédérés peuvent influencer vos rapports.

Pour ajouter un filtre, ajoutez ce qui suit à la fin de l’URL :

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Example  

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

Pour ajouter un filtre au niveau du tableau de bord à une URL, ce filtre doit exister dans bord en tant que filtre de produit ou de niveau de tableau de bord. Ajoutez ces filtres à l’URL après le mois de tendance et avant les paramètres d’URL :

```filter/DATA_MODEL_NAME|VALUE```

Par exemple, pour appliquer une valeur de filtre produit de Microsoft Teams, vous devez ajouter la commande suivante :

```filter/[AllStreams].[Is%20Teams]|[True]```

Tout votre URL ressemble à ceci :

```https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]```

Pour appliquer des filtres d’URL avec des valeurs à sélection multiple, séparez chaque valeur par un trait (|). Par exemple :

```filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]```

Si vous spécifiez un nom ou une valeur non valide, le filtre d’URL n’est pas appliqué.


Vous pouvez utiliser un filtre d’URL pour filtrer chaque rapport pour une dimension spécifique. Les filtres d’URL les plus courants permettent de filtrer les rapports de manière à exclure la télémétrie des participants fédérés ou à se concentrer sur les équipes ou Skype entreprise online. L’exclusion des données fédérées des rapports bord est utile lorsque vous changez de bâtiment ou de réseau dans lequel les points de terminaison fédérés peuvent influencer vos rapports.

| Filtre         | Description          | Exemple de filtre de requête bord      |
|----------------|----------------------|-------------------------------|
| Pas de valeurs non renseignées   | Certains filtres n’ont pas la possibilité de filtrer les valeurs vides. Pour filtrer les valeurs vides manuellement, utilisez l’expression vide et définissez le filtre sur égal à ou différent de selon vos besoins.      | Nom du deuxième bâtiment \<\> \^ \\\*\$                       |
| Exclure les sous-réseaux courants | Si vous n’avez pas de fichier de construction valide pour séparer la gestion de réseaux non gérés, les réseaux domestiques seront inclus dans les rapports. Ces sous-réseaux personnels se trouvent en dehors de la portée du contrôle et peuvent être rapidement exclus d’un rapport. Les sous-réseaux courants tels que définis dans cet article sont 10.0.0.0, 192.168.1.0 et 192.168.0.0. | Deuxième sous-réseau \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Affichage intérieur uniquement  | Utilisé pour filtrer un rapport pour une gestion (interne) ou non gérée (à l’extérieur). Le modèle bord géré est déjà préconfiguré avec ces filtres.       | Deuxième dans l’entreprise = intérieur        |


#### <a name="how-to-find-your-tenant-id"></a>Trouver votre ID de locataire

L’ID de locataire dans bord correspond à l’ID d’annuaire dans Azure. Si vous ne connaissez pas votre ID d’annuaire, vous pouvez le trouver dans le portail Azure :

1.  Connectez-vous au portail Microsoft Azure :<https://portal.azure.com>

2.  Sélectionnez **Azure Active Directory**.

3.  Sous **gérer**, sélectionnez **Propriétés**. Votre ID de locataire figure dans la zone ID de l' **Annuaire** .

Vous pouvez également trouver votre ID de locataire à l’aide de PowerShell : 
  ```
  Login-AzureRmAccount
  ```



## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Comparer des équipes et des données de Skype entreprise bord

Même au cours des dernières bord (cqd.teams.microsoft.com), vous verrez les différences de données entre teams et Skype entreprise. Voici quelques raisons pour lesquelles :
- Différences en matière de mécanismes permettant de garantir les performances et la fiabilité
  - Teams utilise la reconnexion automatique et l’itinérance rapide. Skype entreprise ne fonctionne pas.
  - Teams offre une gestion dynamique de la bande passante. Skype entreprise ne fonctionne pas.
- Différences de [plages d’adresses IP](Office-365-URLs-IP-address-ranges.md) entre les équipes et Skype entreprise. Les plages d’adresses IP d’équipes sont plus récentes, ce qui peut entraîner des problèmes de connectivité au pare-feu.

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a>Ouverture de bord à partir du portail hérité Skype entreprise

![Icône du logo Skype entreprise ](media/sfb-logo-30x30.png) **avec le portail hérité Skype entreprise**

1. Connectez-vous à votre organisation Office 365 à l’aide d’un compte d’administrateur, puis sélectionnez la vignette **administrateur** pour ouvrir le centre d’administration.
2. Dans le volet gauche, sous **centres d’administration**, sélectionnez **Microsoft teams** pour ouvrir le centre d’administration Teams.
3. Dans le centre d’administration Teams, sélectionnez **portail hérité** dans le volet gauche, sélectionnez **Outils**, puis cliquez sur **tableau de bord de qualité des appels de Skype entreprise Online**.

     ![Capture d’écran : sélectionner le tableau de bord de qualité des appels](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. Dans la page qui s’affiche, connectez-vous à l’aide de votre compte d’administrateur général, puis indiquez les informations d’identification du compte lorsque vous y êtes invité.

Lorsque vous vous connectez pour la première fois, bord commence à collecter et à traiter les données. 

> [!IMPORTANT]
> À compter du 2019 de décembre, vous pouvez toujours accéder à l’ancienne version de bord (cqd.lync.com), bien que le portail hérité vous donne un lien vers le dernier bord (cqd.teams.microsoft.com). Par la suite, l’ancienne version de bord sera mise hors service. À compter du 1er juillet 2020, l’ancienne version de bord accède aux données du nouveau bord ( https://CQD.teams.microsoft.com) et vous ne pouvez plus exporter les données de génération et de rapport. Dans 2020 au plus tard, nous désactivons l’ancien bord et vous ne pourrez plus y accéder.


## <a name="related-topics"></a>Voir aussi

[Améliorer et surveiller la qualité des appels pour teams](monitor-call-quality-qos.md)

[Qu’est-ce que bord ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels (bord)](turning-on-and-using-call-quality-dashboard.md)

[Télécharger le client et générer des données](CQD-upload-tenant-building-data.md)

[Utiliser bord pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans bord](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans bord](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser des données de bord](CQD-Power-BI-query-templates.md)
