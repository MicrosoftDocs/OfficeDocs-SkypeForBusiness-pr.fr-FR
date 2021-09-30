---
title: Données et rapports dans le tableau de bord de qualité des appels
ms.author: serdars
author: SerdarSoysal
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: En savoir plus sur les données et rapports disponibles dans le tableau de bord de qualité des appels de Microsoft.
ms.openlocfilehash: 0f54b6c3c69d65b12aa248f7180dec3617273857
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014618"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Données et rapports dans le tableau de bord de qualité des appels

Le tableau de bord de qualité des appels de Microsoft utilise un flux de données en temps quasi réel (NRT). Les enregistrements d’appel sont disponibles dans le groupe de qualité des appels dans un délai de 30 minutes après la fin de l’appel. Les enregistrements d’appel du pipeline NRT ne sont disponibles que pendant quelques mois avant d’être supprimés du jeu de données. 


## <a name="many-ways-to-access-cqd-data"></a>Plusieurs façons d’accéder aux données du CQD

Vous pouvez accéder aux données du CQD par différentes façons. Choisissez celui qui répond le mieux à vos besoins :

|&nbsp;|&nbsp;|
|---------|---------|
|Teams d’administration [de https://admin.teams.microsoft.com) l’administration (](https://admin.teams.microsoft.com)    | Les données du CQD sont incluses dans la **page** Utilisateurs du Centre d’administration Teams. Elles affichent les données les plus courantes dont vous avez besoin dans un format facile à lire. Vous ne pouvez pas personnaliser les données de CQD disponibles sous **Utilisateurs.**  |
|Portail du CQD [( https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)     | Synthèse robuste et rapports détaillés qui répondent à la plupart des besoins, avec un filtrage détaillé. Vous pouvez également personnaliser les rapports dans le portail du CQD. <br><br>Obtenez deux [modèles de rapport du CQD](#import-the-cqd-report-templates) pour vous aider à analyser les données dans le portail du deQD.       |
|Power BI     | Utilisez des requêtes directes pour afficher les données de votre Power BI à l’aide de modèles [Power BI personnalisés.](CQD-Power-BI-query-templates.md) [Téléchargez Power BI modèles de requête pour le CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)<br><br>Vous pouvez également [utiliser l’API REST pour accéder aux données du CQD via](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) Power BI. Utilisez cette méthode si vous voulez télécharger vos données de qualité des fichiers CQD afin de pouvoir travailler dessus en mode hors connexion. L’avantage de cette méthode est d’obtenir de meilleures performances, particulièrement utiles pour les jeux de données de grande taille qui se Power BI lorsque vous êtes en ligne.       |
|API Graph     | Accédez aux données de qualité des appels vous-même à [l’aide de Graph API.](/graph/api/resources/callrecords-api-overview?view=graph-rest-beta) Il s’agit de la méthode la plus complexe, mais elle vous offre un contrôle et une flexibilité accrues pour analyser vos données de qualité des appels. Par exemple, si vous devez la joindre à d’autres données pour votre organisation, vous pouvez utiliser l’API Graph pour créer un modèle de données et incorporer des données de qualité des appels.        |

## <a name="import-the-cqd-report-templates"></a>Importer les modèles de rapport du CQD

Téléchargez deux modèles de rapports [de CQD organisés](https://aka.ms/qertemplates) (Tous les réseaux et réseaux gérés) pour vous aider à prendre rapidement en compte le CQD. Bien qu’optimisé pour utiliser un fichier de données de bâtiment, le modèle All Networks peut être utilisé tandis que vous collectez et chargez les informations de bâtiment dans le CQD, comme décrit dans la section suivante.

**Pour importer les modèles (. CQDX) dans le CQD**

1. Dans le CQD, sélectionnez **Rapports détaillés** dans le menu en haut de la page.

2. Dans le panneau de gauche, sélectionnez **Importer.** Accédez au premier modèle CQDX et sélectionnez **Ouvrir.**

3. Une fois le modèle chargé, une fenêtre pop-up affiche le message « L’importation du rapport a réussi ». 

4. Répétez les étapes 2 et 3 pour le deuxième modèle de DQD.

   > [!NOTE]
   > Chaque utilisateur doit importer les modèles de DQD dans son instance de CQD. 



## <a name="euii-data"></a>Données EUII

Pour des raisons de conformité, les données d’identification de l’utilisateur final (EUII) (également appelées informations d’identification personnelle ou PII) ne sont conservées que 28 jours. Étant donné que les données NRT croisent la marque de 28 jours, les champs qui contiennent EUII sont effacés, ce qui entraîne des données NRT sans EUII. Les champs qui contiennent des données EUII sont :

- Adresse IP complète
- Adresse de Media Access Control (MAC)
- Identificateur de l’ensemble de services simple (BSSID)
- URI SIP (session Initiation Protocol) (Skype Entreprise uniquement)
- Nom d’utilisateur principal (UPN)
- Nom du point de terminaison d’ordinateur
- Commentaires de l’utilisateur Verbatim
- ID d’objet (ID d’objet Active Directory de l’utilisateur du point de terminaison)

### <a name="admin-roles-with-and-without-euii-access"></a>Rôles d’administrateur avec et sans accès EUII

Ces [rôles de](/azure/role-based-access-control/overview) contrôle **d’accès rapide ont** accès à la fonction EUII :
- Administrateur global
- Teams Administrateur de service
- Teams Administrateur des communications
- Ingénieur du support technique pour les communications Teams
- Lecteur global
- Skype Entreprise Administrateur

Ces rôles DE CONTRÔLE **D’ACCÈS N’ont pas** accès à la fonction EUII :
- Lecteur de rapports
- Teams Spécialiste du support pour les communications


## <a name="date-controls"></a>Contrôles de date

Le tableau de recherche et la recherche de données (CQD) prend en charge les types de tendance rolling suivants :

- 5 jours
- 7 jours
- 30 jours
- 60 jours
- 90 jours

Le paramètre Date de l’URL accepte un champ Day. Les rapports jour après jour utilisent les dates spécifiées au format AAA-MM-JD comme dernier jour de la tendance. Le paramètre Date d’URL « 00 » indique « aujourd’hui ».

|URL| Date de fin de la tendance jour en mouvement|
|:---|:---|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02/</span>   |Jour actuel du mois de février 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02-15/</span>|15 février 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /00/</span>        |Jour actuel|
|||

Par défaut, le jour en cours du mois est utilisé comme dernier jour de la tendance jour consécutif.


## <a name="data-available-in-cqd-reports"></a>Données disponibles dans les rapports du DQD

Le résumé par défaut et les rapports détaillés du tableau de qualité des appels peuvent vous aider à gérer la qualité des appels pour votre organisation. Si nécessaire, vous pouvez créer [des rapports personnalisés.](#create-custom-detailed-reports) 

Si vous voulez utiliser des Power BI pour analyser vos données de CQD, lisez Utiliser Power BI pour analyser les données du même [Teams.](CQD-Power-BI-query-templates.md)

|Fonctionnalité|Rapports de synthèse|Rapports détaillés|
|:--- |:--- |:--- |
|Métrique de partage d’application | Non | Oui |
|Prise en charge des informations sur le bâtiment du client | Oui | Oui |
|Prise en charge des informations sur le point de terminaison du client | Uniquement en <span> cqd.teams.microsoft.com<span/> | Uniquement en <span> cqd.teams.microsoft.com<span/> |
|Prise en charge de l’analyse approfondie   | Non   | Oui   |
|Mesures de fiabilité des médias   | Non   | Oui   |
|Rapports pré-pré-prél   | Oui   | Oui   |
|Présentation des rapports   | Oui   | Oui   |
|Ensemble de rapports par utilisateur   | Non   | Oui   |
|Personnalisation de l’ensemble de rapports (ajout, suppression, modification des rapports)   | Non   | Oui   |
|Mesures de partage d’écran vidéo   | Non   | Oui   |
|Mesures vidéo   | Non   | Oui   |
|Volume de données disponible   | 12 derniers mois   | 12 derniers mois   |
|Microsoft Teams données   | Oui   | Oui   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a>Sélectionner les données de produit à voir dans les rapports

Dans les rapports de synthèse et de Location-Enhanced, vous pouvez utiliser la Skype Entreprise de filtre de produit pour afficher toutes les données de produit, uniquement Microsoft Teams ou uniquement Skype Entreprise données En ligne. 

> [!div class="mx-imgBorder"]
> ![Capture d’écran : affiche les options de contrôle du filtre de produit.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Dans les rapports détaillés, vous pouvez utiliser la dimension est **Teams** pour filtrer les données sur des Microsoft Teams ou Skype Entreprise Online.

## <a name="summary-reports"></a>Rapports de synthèse

Il s’agit des rapports qui s’afficheront dans le tableau de bord du tableau de bord du tableau de bord lorsque vous vous connectez pour la première fois au tableau de bord de tableau de bord. Ils vous donnent un aperçu rapide des tendances de qualité à l’aide de rapports quotidiens, mensuels et de tableaux pour vous aider à identifier les sous-réseaux de mauvaise qualité. 

| Tabulation | Description |
|---------|---------|
|Qualité globale des appels     | Agrégation des 3 autres onglets.       |
|Serveur - Client     |Détails des flux entre les points de terminaison serveur et client.        |
|Client-client     |Détails des flux entre deux points de terminaison clients.        |
|Voice Quality SLA     |Informations sur les appels inclus dans Skype Entreprise [SLA de qualité vocale.](https://go.microsoft.com/fwlink/p/?linkid=846252)        |

### <a name="overall-call-quality-tab"></a>Onglet Qualité globale des appels

Utilisez les données de cet onglet pour évaluer le statut et les tendances de qualité des appels sur la base du nombre de flux et de pourcentages d’appels médiocres. La légende dans le coin supérieur droit indique les couleurs et les éléments visuels qui représentent ces indicateurs.

> [!div class="mx-imgBorder"]
> ![Capture d’écran : afficher l’onglet Qualité des appels.](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Flux sont classés en trois groupes : Bon, Médiocre et Non classé. Il existe également des valeurs de *pourcentage* de  flux médiocres calculées qui vous donnent le rapport entre les flux classés comme médiocres et le nombre total de flux classés. Étant donné que % médiocre = flux médiocres/ (flux  médiocres + flux *bons) * 100*, le pourcentage de médiocres n’est pas affecté par la présence de plusieurs flux *non* classés. Pour voir ce qui classe un flux comme médiocre ou bon, reportez-vous à la classification de flux dans le [tableau de bord de qualité des appels.](stream-classification-in-call-quality-dashboard.md)
  
Utilisez l’échelle de gauche pour mesurer les valeurs du nombre de flux.

> [!div class="mx-imgBorder"]
> ![Capture d’écran : affiche les valeurs du nombre de flux.](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Utilisez l’échelle de droite pour mesurer les valeurs % médiocres.

> [!div class="mx-imgBorder"]
> ![Capture d’écran : affiche les valeurs % médiocres.](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Vous pouvez également obtenir les valeurs numériques réelles en pointant la souris sur une barre.
  
> [!NOTE]
> L’exemple suivant est issu d’un très petit échantillon de jeu de données, et les valeurs ne sont pas réaliste pour un déploiement réel.

> [!div class="mx-imgBorder"]
> ![Capture d’écran : montre la souris utilisée pour accéder aux données.](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Le volume global de flux aide à déterminer le niveau de pertinence des pourcentages de flux médiocres calculés. Plus le volume de flux globaux est faible, moins les valeurs de pourcentage de flux médiocres sont fiables.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Server-Client et Client-Client onglets

Ces deux onglets fournissent des détails sur les flux qui ont eu lieu dans leurs scénarios de point de terminaison à point de terminaison. LServer-Client onglet a quatre sections réductibles qui représentent quatre scénarios selon lesquels les flux de données multimédias circuleraient.
  
- Câblé à l’intérieur
- Filé à l’extérieur
- WiFi interne
- WiFi extérieur

De même, l’onglet Client-Client'onglet a cinq sections réductibles :

- Filé à l’intérieur — filé à l’intérieur
- Filé à l’intérieur — filé à l’extérieur
- Wired Outside — Wired Outside
- Connexion filée interne — WiFi Interne
- Connexion filée interne — WiFi externe

#### <a name="inside-versus-outside"></a>Intérieur et Extérieur

Le CQD classe un  flux  comme interne ou externe à l’aide d’informations sur le bâtiment, le cas où il existe. Les points de terminaison de chaque flux sont associés à une adresse de sous-réseau. Si le sous-réseau figure dans la liste des sous-réseaux marqués dans InsideCorp dans les informations sur le bâtiment téléchargées, il est considéré comme *interne.* Si les informations sur le bâtiment n’ont pas encore été téléchargées, le test interne classe toujours les flux comme *externes.* 

Le test interne pour un scénario Server-Client considère uniquement le point de terminaison du client. Étant donné que les serveurs sont toujours extérieurs du point de vue de l’utilisateur, cela n’est pas expliqué dans le test.
  
#### <a name="wired-versus-wifi"></a>Connexion câblé et WiFi

Comme l’indique le nom, les critères de classification sont basés sur le type de connexions client. Le serveur est toujours câblé et n’est pas inclus dans le calcul. Dans un flux donné, si l’un des deux points de terminaison est connecté à un réseau WiFi, le CQD le classe en WiFi.

> [!NOTE]
> À cause d’un flux, si l’un des deux points de terminaison est connecté à un réseau WiFi, il est classé comme Étant en WiFi dans le réseau de qualité des documents.
  
  
## <a name="tenant-data-information"></a>Informations sur les données client

Le tableau de bord des rapports de synthèse du tableau de bord de qualité des Télécharger comporte une **page** Données client accessible en sélectionnant Client Data **Télécharger dans** le menu Paramètres dans le coin supérieur droit. Cette page permet aux administrateurs de télécharger leurs propres informations, telles que :

- Une carte d’adresses IP et d’informations géographiques.
- Une carte de chaque AP sans fil et de son adresse MAC.
- A map of Endpoint to Endpoint Make/Model/Type, etc.
  
Nous vous recommandons de charger les données de votre client, bâtiment et emplacement afin que le CQD puisse inclure ces informations dans vos rapports. Si vous n’avez pas encore chargé ces données, lisez Télécharger [client et les données bâtiment.](CQD-upload-tenant-building-data.md) 


## <a name="detailed-reports"></a>Rapports détaillés

| Nom | Description |
|---------|---------|
|Location-Enhanced rapports d’équipe     |Affiche les tendances de qualité sur la base des informations d’emplacement. Ce rapport s’affiche uniquement si vous avez [téléchargé vos données client.](CQD-upload-tenant-building-data.md)        |
|Rapports de fiabilité     |Inclut l’audio, la vidéo, le partage d’écran vidéo (VBSS) et les rapports de partage d’application.        |
|Rapports de qualité de l’expérience     |Qualité audio et fiabilité de tous les clients et appareils, y compris les salles de réunion. Ces rapports sont une version « slimmed » des [modèles téléchargeables](https://aka.ms/QERtemplates)de qualité des documents. Ils se concentrent sur des aspects clés pour l’analyse de la qualité audio et de la fiabilité.         |
|Rapports d’amélioration de la qualité     | Drill downs: Date by region, locations, subnets, hour, and users.        |
|Échec de l’drill down reports     | Drill downs: Date by region, locations, subnets, hour, and users.        |
|Évaluer mes rapports d’appel     |Analysez les évaluations des appels par région, emplacement ou par utilisateur. Inclut des commentaires verbatim.         |
|Rapports du service d’aide     |Les rapports du service d’aide utilisent les données relatives aux appels et aux réunions pour les utilisateurs individuels, les groupes d’utilisateurs ou tout le monde. L’intégration des données de création et de la fonction EUII permet d’identifier les problèmes système possibles en fonction de l’emplacement réseau, des détails des conférences, des appareils ou du microprogramme.         |
|Rapports sur les versions des clients     |Résumé de la version du client : afficher le nombre de sessions et d’utilisateurs pour chaque version de l’application cliente<br><br>Version client par utilisateur : afficher les noms d’utilisateur pour chaque version de l’application client <br><br>Les filtres pré-intégrés pour les produits et les types de clients aident à axer les versions sur des clients spécifiques.         |
|Rapports sur les points de terminaison     |Affiche la qualité des appels par point de terminaison d’ordinateur (produit et modèle d’ordinateur). Ces rapports incluent les données de bâtiment, si vous les avez téléchargées.         |


## <a name="create-custom-detailed-reports"></a>Créer des rapports détaillés personnalisés

Si les rapports de DQD par défaut ne répondent pas à vos besoins, utilisez ces instructions pour créer un rapport personnalisé. Vous pouvez également (à partir de janvier 2020) utiliser Power BI pour les rapports du [CQD. ](cqd-power-bi-query-templates.md)

From the pull-down list of reports at the top of the screen displayed at login \( the **Summary Reports** screen \) Select **Detailed Reports** and then **New.** Cliquez **sur** Modifier dans un état pour voir l’Éditeur de requête. Chaque rapport est complété par une requête effectuée dans le cube. Il s’agit de la visualisation des données renvoyées par la requête. L’Éditeur de requête vous aide à modifier ces requêtes et les options d’affichage de l’état.

> [!IMPORTANT]
> La plage réseau peut être utilisée pour représenter un supernet (combinaison de plusieurs sous-réseaux avec un préfixe de routage unique). Tous les téléchargements du nouveau bâtiment seront vérifiés pour toutes les plages superposées. Si vous avez précédemment téléchargé un fichier de bâtiment, vous devez télécharger le fichier actuel et le charger à nouveau pour identifier les chevauchements et résoudre le problème avant de le charger à nouveau. Tout chevauchement dans des fichiers précédemment chargés peut entraîner le mappage erroné des sous-réseaux vers les bâtiments dans les rapports. Certaines implémentations VPN n’indiquent pas précisément les informations sur le sous-réseau. Lors de l’ajout d’un sous-réseau VPN au fichier du bâtiment, au lieu d’une entrée pour le sous-réseau, il est recommandé d’ajouter des entrées distinctes pour chaque adresse du sous-réseau VPN en tant que réseau 32 bits distinct. Chaque ligne peut avoir les mêmes métadonnées de bâtiment. Par exemple, au lieu d’avoir une ligne pour 172.16.18.0/24, vous devez avoir 256 lignes, avec une ligne pour chaque adresse entre 172.16.18.0/32 et 172.16.18.255/32 incluses.
>
> La colonne VPN est facultative et utilise la valeur 0 par défaut.  Si la valeur de la colonne VPN est définie sur 1, le sous-réseau représenté par cette ligne sera entièrement développé pour correspondre à toutes les adresses IP au sein du sous-réseau.  Utilisez-la avec parcimonie et uniquement pour les sous-réseaux VPN, car le développement complet de ces sous-réseaux aura un impact négatif sur les temps de requête pour les requêtes impliquant la création de données.

Pointez sur les graphiques à barres et les courbes de tendance dans le rapport pour afficher des valeurs détaillées. Le rapport avec le focus affiche le menu d’actions : **Modifier,** **Cloner,** **Supprimer,** **Télécharger** et Exporter l’arborescence **de rapport.**



## <a name="query-filters"></a>Filtres de requête

Les filtres de requête sont implémentés à l’aide de l’Éditeur de requête dans le CQD. Ces filtres permettent de réduire le nombre d’enregistrements renvoyés par le rapport de qualité des requêtes, réduisant ainsi la taille globale de l’état et les temps de requête. Ceci est particulièrement utile pour filtrer les réseaux nonmanagés. Les filtres répertoriés dans le tableau suivant utilisent des expressions régulières (RegEx).


| Filtre         | Description          | Exemple de filtre de requête du CQD      |
|----------------|----------------------|-------------------------------|
| Aucune valeur vide   | Certains filtres ne permettent pas de filtrer les valeurs vides. Pour filtrer manuellement les valeurs vides, utilisez l’expression vide et définissez le filtre sur Égal ou Pas égal, selon vos besoins.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Exclure les sous-réseaux communs | S’il n’y a pas de fichier de bâtiment valide à séparer les réseaux gérés des réseaux non gérés, les réseaux à domicile seront inclus dans les rapports. Ces sous-réseaux d’accueil ne sont pas dans le cadre du contrôle de l’it et peuvent être rapidement exclus d’un rapport. Les sous-réseaux communs, tels que définis dans ce guide, sont 10.0.0.0, 192.168.1.0 et 192.168.0.0. | Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Afficher dans le seul  | Permet de filtrer un rapport pour géré (à l’intérieur) ou non géré (à l’extérieur). Le modèle de DQD géré est déjà préconfiguré avec ces filtres.       | Second Inside Corp = Inside        |

## <a name="report-filters"></a>Filtres de rapport

Utilisez les filtres des rapports du CQD pour concentrer l’attention sur vos enquêtes. Utilisez les filtres de rapport en ajoutant un filtre au rapport rendu dans l’Éditeur de requête ou directement dans l’état. Les filtres de rapport suivants sont utilisés dans les [modèles de tableau de qualité des rapports.](https://aka.ms/QERtemplates)


| Filtre     | Description                            | Exemple de filtre de rapport du CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Commencez par l’année, d’abord, puis par le mois. | 2017-10                           |
| Alphabetic | Filtre les caractères alphabéiques. | [a-z]                             |
| Numérique    | Filtre les caractères numériques.    | [0-9]                             |
| Pourcentage | Filtres pour un pourcentage.              | ([3-9] \\ .) \| ([3-9]) \| ([1-9][0-9]) |


### <a name="drill-down-filters"></a>Filtres d’drill-down

Les rapports du CQD permettent d’utiliser plusieurs filtres d’analyse approfondie, qui sont des outils puissants pour affiner vos enquêtes sur la qualité des appels. Si vous sélectionnez un champ d’drill-down, le rapport ouvre automatiquement l’onglet et les filtres appropriés sur la valeur sélectionnée. Si cet onglet possède ses propres champs d’analyse et que l’un d’eux est sélectionné, les deux ensembles de filtres sont appliqués, ce qui a pour effet de réduire progressivement le jeu de données résultant.

![Diagramme illustrant le flux de rapport d’drill-down.](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a>Ajout et modification de champs d’une drill-down

Lorsque vous modifiez un état, vous avez la possibilité de spécifier des champs d’drill-down de votre choix à l’aide de l’Éditeur de requête.

Commencez par cliquer **sur ...** pour le rapport que vous voulez modifier, puis sélectionnez **Modifier.**

![Capture d’écran de la modification d’un champ d’drill-down.](media/qerguide-image-addeditdrilldownfields.png)

Sélectionnez une dimension dans la liste sur le côté gauche de l’Éditeur de requête. Cliquez ensuite sur la  barre de niveau inférieur sous l’étiquette Accéder à, puis sélectionnez l’onglet et le groupe de développement vers qui vous souhaitez que la dimension explorera. Remarque : Actuellement, la fonctionnalité d’drill-down fonctionne uniquement en naviguant vers différents onglets. La prise en charge de l’exploration d’un expandeur spécifique sera ajoutée ultérieurement. Pour finir, cliquez **sur Fermer** pour enregistrer  les modifications apportées à la dimension, puis cliquez sur Enregistrer pour enregistrer et fermer l’Éditeur de requête.

![Capture d’écran de la sélection d’une dimension dans l’Éditeur de requête.](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Sélectionner plusieurs filtres

Outre la fonctionnalité d’drill-down, CQD prend également en charge la spécification de filtres avec plusieurs valeurs (ou filtres).

Pour sélectionner plusieurs valeurs de filtre, commencez par ajouter un nouveau filtre au rapport. Cliquez **+** à côté de **l’étiquette Filtres,** entrez le nom de la dimension que vous voulez utiliser, puis cliquez sur **Ajouter.**

![Capture d’écran de l’ajout d’un filtre à sélection multiple.](media/qerguide-image-addmultiselectfilter.png)

Cliquez ensuite sur **Recherche** (icône de loupe à côté du nouveau filtre). Un champ de texte et plusieurs options s’offrent à vous, notamment Sélectionner **tout** **et Inverser.** Entrez une valeur, puis cliquez **sur Rechercher en** côté de ce champ pour effectuer une recherche. Vous pouvez également laisser le champ de texte vide et cliquer **sur Rechercher** pour afficher les 100 premières options.

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Exemple :  

![Capture d’écran de l’ajout d’un filtre de requête.](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filtres au niveau du tableau de bord
Certains rapports de tableau de bord de qualité des tableaux de bord ont été ajoutés à des filtres au niveau du tableau de bord, ce qui permet de filtrer aisé sur la partir de paramètres courants. Ces filtres apparaissent en dehors des onglets de rapport ordinaires et directement sous le filtre Produit, et ils s’appliquent à tous les filtres du tableau de bord.

![Capture d’écran d’un filtre de tableau de bord.](media/qerguide-image-dashboardfilters.png)
```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>Filtres d’URL

Le CQD prend en charge l’ajout de filtres à l’URL. Cela facilite le partage ou le signet d’une requête de CQD. Vous pouvez définir des paramètres dans l’URL, tels que le mois tendance, l’ID de client ou la langue. Vous pouvez également ajouter des filtres au niveau du produit ou du tableau de bord à l’URL.
L’exclusion des données fédérées des rapports du CQD est utile lorsque vous résupédiez des bâtiments gérés ou des réseaux dans lequel des points de terminaison fédérés peuvent influencer vos rapports.

Pour ajouter un filtre, ajoutez ce qui suit à la fin de l’URL :

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Exemple :  

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

Pour ajouter un filtre au niveau du tableau de bord à une URL, ce filtre doit exister dans le tableau de bord comme filtre au niveau du produit ou du tableau de bord. Ajoutez ces filtres à l’URL après le mois de tendance et avant les paramètres d’URL :

`filter/DATA_MODEL_NAME|VALUE`

Par exemple, pour appliquer une valeur de filtre Produit Microsoft Teams, vous devez ajouter ce qui suit :

`filter/[AllStreams].[Is%20Teams]|[True]`

L’URL entière ressemblerait à ceci :

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

Pour appliquer des filtres d’URL avec des valeurs à sélection multiple, séparez-les par un caractère de |. Par exemple :

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

Si vous spécifiez un nom ou une valeur non valide, le filtre d’URL n’est pas appliqué.


Vous pouvez utiliser un filtre d’URL pour filtrer chaque rapport pour une dimension spécifique. Les filtres d’URL les plus courants permettent de filtrer les rapports afin d’exclure la télémétrie des participants fédérés, ou de se concentrer sur Teams ou Skype Entreprise Online. L’exclusion des données fédérées des rapports du CQD est utile lorsque vous résupédiez des bâtiments gérés ou des réseaux dans lequel des points de terminaison fédérés peuvent influencer vos rapports.

| Filtre         | Description          | Exemple de filtre de requête du CQD      |
|----------------|----------------------|-------------------------------|
| Aucune valeur vide   | Certains filtres ne permettent pas de filtrer les valeurs vides. Pour filtrer manuellement les valeurs vides, utilisez l’expression vide et définissez le filtre sur Égal ou Pas égal, selon vos besoins.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Exclure les sous-réseaux communs | S’il n’y a pas de fichier de bâtiment valide à séparer les réseaux gérés des réseaux non gérés, les réseaux à domicile seront inclus dans les rapports. Ces sous-réseaux d’accueil ne sont pas dans le cadre du contrôle de l’it et peuvent être rapidement exclus d’un rapport. Les sous-réseaux communs, tels que définis dans cet article, sont 10.0.0.0, 192.168.1.0 et 192.168.0.0. | Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Afficher dans le seul  | Permet de filtrer un rapport pour géré (à l’intérieur) ou non géré (à l’extérieur). Le modèle de DQD géré est déjà préconfiguré avec ces filtres.       | Second Inside Corp = Inside        |


#### <a name="how-to-find-your-tenant-id"></a>Comment trouver votre ID de locataire

L’ID de client dans le DQD correspond à l’ID d’annuaire dans Azure. Si vous ne le connaissez pas, vous pouvez le trouver dans le portail Azure :

1.  Connectez-vous au portail Microsoft Azure de l’entreprise :<https://portal.azure.com>

2.  Sélectionnez **Azure Active Directory.**

3.  Sous **Gérer,** sélectionnez **Propriétés.** Votre ID de client se trouve dans la zone **ID d’annuaire.**

Vous pouvez également trouver votre ID de locataire à l’aide de PowerShell : 

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Comparaison des Teams du Skype Entreprise et des données du CQD

Lors de l’examen de vos données, vous pouvez constater des différences entre les Teams et Skype Entreprise. Voici quelques raisons :
- Différences entre les mécanismes permettant de garantir les performances et la fiabilité :
  - Teams a la reconnexion automatique et l’itinérance rapide. Skype Entreprise non.
  - Teams de gestion de la bande passante dynamique. Skype Entreprise non.
- Différences entre les [plages d’adresses IP](Office-365-URLs-IP-address-ranges.md) Teams et Skype Entreprise. Les Teams d’adresses IP sont plus nouvelles, ce qui peut entraîner des problèmes de connectivité au niveau du pare-feu.



## <a name="related-topics"></a>Voir aussi

[Améliorer et surveiller la qualité des appels pour les Teams](monitor-call-quality-qos.md)

[Qu’est-ce que le CQD ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels](turning-on-and-using-call-quality-dashboard.md)

[Télécharger données de bâtiment et de client](CQD-upload-tenant-building-data.md)

[Utiliser le CQD pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans le DQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans le CQD](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données du CQD](CQD-Power-BI-query-templates.md)
