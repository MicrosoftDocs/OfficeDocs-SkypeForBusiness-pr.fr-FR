---
title: Activation et utilisation du tableau de bord de qualité des appels
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
- ms.teamsadmincenter.directrouting.cqd
ms.custom:
- Reporting
description: 'Découvrez comment activer et utiliser le tableau de bord de qualité des appels de Skype entreprise Online et obtenez des rapports de synthèse sur la qualité des appels. '
ms.openlocfilehash: eaadd80030b04d5fb10fd8f29d656fe07e24a1db
ms.sourcegitcommit: ab259764dc50bdd52efed3abb1d065ee19486946
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2019
ms.locfileid: "36393492"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Activation et utilisation du tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online

Apprenez à configurer votre organisation Office 365 pour utiliser le tableau de bord de qualité des appels pour surveiller la qualité des appels.
  
Le tableau de bord de qualité des appels (bord) de Microsoft teams et de Skype entreprise Online vous permet d’accéder à des informations sur la qualité des appels passés à l’aide de Microsoft teams et des services Skype entreprise. Cette rubrique décrit les étapes que vous devez effectuer pour commencer à collecter des données.
  
  
## <a name="latest-changes-and-updates"></a>Dernières modifications et mises à jour

Les modifications les plus récentes apportées à bord sont les suivantes:
  
- Inclut les données de Microsoft teams en plus de celles de Skype entreprise online.
    
- Les rapports de synthèse incluent un filtre produit permettant de sélectionner toutes les données, les données de Microsoft teams ou les données de Skype entreprise online.

- La logique de classification de la qualité du flux vidéo et VBSS a été mise à jour. Consultez [classification des flux dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md) pour obtenir les dernières définitions de classificateur.

Consultez cet article pour obtenir la liste des [dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Pour plus d’informations sur les mises à jour et les modifications apportées au tableau de bord, cliquez sur le lien dans la **bonne nouvelle.** bannière affichée sur le tableau de bord.
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Activer les rapports de synthèse sur le tableau de bord de qualité d’appel Microsoft (bord)

Pour pouvoir commencer à utiliser le bord, vous devez l’activer pour votre organisation Office 365.

![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams à l' **aide du centre d’administration Microsoft teams**
 
1. Pour ouvrir le centre d’administration, connectez-vous à votre organisation 365 à l’aide du compte d’administrateur du service Microsoft Teams, puis sélectionnez la vignette **administrateur** .
    
2. Dans le volet gauche, sous **centres d’administration**, sélectionnez **Microsoft teams** pour ouvrir le centre d’administration Microsoft Teams.
    
3. Dans le centre d’administration de Microsoft Teams, sélectionnez **tableau de bord de qualité des appels** dans le volet gauche.
    
  
4. Dans la page qui s’affiche, connectez-vous à l’aide de votre compte d’administrateur général ou du compte d’administrateur du service Microsoft Teams, puis fournissez les informations d’identification du compte lorsque vous y êtes invité.
    
     ![Capture d’écran montrant l’invite informations d’identification](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Après vous être connecté, une fois activé, le bord commence la collecte et le traitement des données.  
> [!NOTE]
> Le traitement d’une quantité suffisante de données pour afficher des résultats significatifs dans les rapports risque de nécessiter quelques heures. 

![Icône illustrant le logo](media/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**
 
1. Connectez-vous à votre organisation Office 365 à l’aide d’un compte d’administrateur, puis sélectionnez la vignette **administrateur** pour ouvrir le centre d’administration.
    
2. Dans le volet gauche, sous **centres d’administration**, sélectionnez **Skype entreprise** pour ouvrir le centre d’administration Skype entreprise.
    
3. Dans le centre d’administration de Skype entreprise, sélectionnez **Outils** dans le volet de gauche, puis sélectionnez **tableau de bord de qualité des appels de Skype entreprise Online**.
    
     ![Capture d’écran montrant la sélection du tableau de bord de qualité des appels](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. Dans la page qui s’affiche, connectez-vous à l’aide de votre compte d’administrateur général, puis indiquez les informations d’identification du compte lorsque vous y êtes invité.
    
     ![Capture d’écran montrant l’invite informations d’identification](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Après vous être connecté, une fois activé, le bord commence la collecte et le traitement des données.


  
## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Fonctionnalités du tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online 
<a name="BKMKFeaturesOfTheCQD"> </a>

BORD-XX XXXXXXX XXXXXXX XXXXXXX XXXXXXX xxxxxxxxx XXXXXXXXX. Les différences entre les deux éditions sont résumées ici:
  
|**Fonctionnalité**|**Rapports de synthèse**|**Rapports détaillés**|
|:-----|:-----|:-----|
|Métrique du partage d’application  <br/> |Non  <br/> |Oui  <br/> |
|Support des informations sur le bâtiment du client  <br/> |Oui  <br/> |Oui  <br/> |
|Support technique des informations de point de terminaison client  <br/> |Uniquement dans cqd.teams.microsoft.com  <br/> |Uniquement dans cqd.teams.microsoft.com  <br/> |
|Prise en charge de l’analyse approfondie  <br/> |Non  <br/> |Oui  <br/> |
|Mesures de fiabilité des médias  <br/> |Non  <br/> |Oui  <br/> |
|Rapports prêts à l’emploi  <br/> |Oui  <br/> |Oui  <br/> |
|Présentation des rapports  <br/> |Oui  <br/> |Oui  <br/> |
|Ensemble de rapports par utilisateur  <br/> |Non  <br/> |Oui  <br/> |
|Personnalisation d’un ensemble de rapports (ajout, suppression, modification des rapports)  <br/> |Non  <br/> |Oui  <br/> |
|Métriques de partage d’écran vidéo  <br/> |Non  <br/> |Oui  <br/> |
|Métriques vidéo  <br/> |Non  <br/> |Oui  <br/> |
|Volume de données disponible  <br/> |6 derniers mois  <br/> |6 derniers mois  <br/> |
|Données de Microsoft teams  <br/> |Oui  <br/> |Oui  <br/> |
   
### <a name="out-of-the-box-reports"></a>Rapports prêts à l’emploi

Les deux éditions de bord fournissent une connaissance prédéfinie, ce qui vous permet d’effectuer des mesures de qualité d’appel sans avoir à créer de nouveaux rapports. Lorsque les données sont traitées au principal, vous pouvez commencer à voir les données de qualité d’appel dans les rapports.
  
### <a name="overview-reports"></a>Présentation des rapports

Les deux éditions de bord fournissent un point d’entrée de haut niveau aux informations générales relatives à la qualité des appels, mais la façon dont les informations sont présentées dans les rapports de synthèse est différente de celle des rapports détaillés.
  
Les rapports de synthèse offrent un affichage simplifié des rapports de pages à onglets, qui permet aux utilisateurs de parcourir et de comprendre rapidement l’État et les tendances de la qualité globale des appels.
  
Les quatre onglets sont les suivants:
  
- La **qualité d’appel globale** : fournit des informations sur tous les flux, qui est une agrégation des flux client-client et des flux client-client, ainsi que des flux client-client et client distincts, sous la forme d’une tendance mensuelle et quotidienne.
    
- **Serveur-client** : fournit des informations supplémentaires pour les flux transitant entre les points de terminaison serveur et client.
    
- **Client-client** : fournit des informations supplémentaires pour les flux transitant entre deux points de terminaison client.
    
- **SLA de qualité vocale** : fournit des informations sur les appels inclus dans le contrat SLA de qualité vocale de Skype entreprise online.
    
### <a name="overall-call-quality-tab"></a>Onglet qualité globale des appels

Utilisez les données de cet onglet pour évaluer l’État et les tendances de la qualité des appels en observant le nombre de flux et de mauvaises pourcentages. La légende dans le coin supérieur droit montre la couleur et les éléments visuels qui représentent ces métriques.
  
![Capture d’écran montrant l’onglet qualité des appels](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Les flux sont classés en trois groupes: bon, médiocre et non classés. Il existe également des valeurs de *pourcentage médiocres* calculées qui vous permettent d’obtenir ** le rapport entre les flux considérés médiocres et le nombre total de flux classés. En raison de *mauvaises% = flux médiocres/(mauvaises chaînes + Good Streams) * 100* , cela rend le *pourcentage médiocre* de la présence avec plusieurs flux non *classés* . Pour savoir quels sont les points à considérer pour classer un flux comme médiocre ou satisfaisant, voir [Classification de flux dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md).
  
Utilisez l’échelle de gauche pour mesurer les valeurs de nombre de flux.
  
![Capture d’écran montrant les valeurs de nombre de flux](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Servez-vous de l’échelle de droite pour mesurer les valeurs de pourcentage médiocres.
  
![Capture d’écran montrant des valeurs de% médiocres](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Vous pouvez également obtenir les valeurs numériques réelles en plaçant le pointeur de la souris sur une barre.
  
> [!NOTE]
> L’exemple suivant provient d’un jeu de données de très petite taille et les valeurs ne sont pas réalistes pour un déploiement réel. 
  
![Capture d’écran montrant l’utilisation de la souris pour accéder aux données](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Le volume de flux global est un facteur important pour déterminer le degré de pertinence des pourcentages médiocres. Plus le volume des flux globaux est faible, plus la fiabilité du pourcentage signalé est faible.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Onglets serveur-client et client-client

Ces deux onglets fournissent des informations supplémentaires pour les flux ayant eu lieu dans leurs scénarios de point de terminaison. L’onglet serveur-client comporte quatre sections réductibles, qui représentent quatre scénarios dans lesquels les flux multimédias seront acheminés.
  
- Connecté (e)
    
- Câblé extérieur
    
- WiFi interne
    
- WiFi extérieur

De même, l’onglet client-client comporte cinq sections réductibles:

- Connexion câblée interne

- Connecté à l’intérieur-filaire extérieur

- Câble filaire externe-filaire extérieur

- Connexion filaire interne

- Connecté à un réseau WiFi extérieur
    
    
#### <a name="inside-test"></a>Test interne

Lors du traitement, le serveur principal bord classifie un flux comme *à l’intérieur* ou à l' *extérieur* en utilisant des informations de bâtiment, le cas échéant. Les points de terminaison de chaque flux sont associés à une adresse de sous-réseau. Si le sous-réseau figure dans la liste des sous-réseaux marqués dans l’entreprise dans les informations de bâtiment téléchargées, il est considéré comme *à l’intérieur*. Si les informations de bâtiment n’ont pas encore été téléchargées, l’intérieur du test classifie toujours les flux comme *extérieur*. Veuillez noter que le test interne du scénario serveur-client ne considère que le point de terminaison client. Étant donné que les serveurs sont toujours extérieurs du point de vue d’un utilisateur, ce n’est pas pris en compte dans le test.
  
#### <a name="wired-vs-wifi"></a>Connexion filaire et WiFi

Les noms indiquent qu’il s’agit d’un critère de classification en fonction du type de connexions client. Là encore, le serveur est toujours câblé et n’est pas inclus dans le calcul.
  
> [!NOTE]
> À partir d’un flux, si l’un des deux points de terminaison est connecté à un réseau WiFi, il est considéré comme WiFi dans bord. 
  
## <a name="selecting-product-data-to-see-in-reports"></a>Sélection des données de produits à afficher dans les rapports
<a name="BKMKProductFilter"></a>

Dans la liste déroulante du filtre produit, vous pouvez utiliser la liste déroulante du **filtre produit** pour afficher toutes les données de produit, uniquement les données de Microsoft Teams, ou uniquement les données de Skype entreprise online.
  
![Capture d’écran montrant les options de contrôle du filtre de produit](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Dans les rapports détaillés, vous pouvez utiliser la dimension **is teams** pour filtrer les données en tant que données de Microsoft teams ou Skype entreprise Online dans le cadre de la définition du rapport.
  
## <a name="upload-tenant-data-information"></a>Télécharger les informations sur les données de client
<a name="BKMKTenantDataInformationUpload"></a>

Le tableau de bord des rapports de synthèse de bord inclut une page de **téléchargement de données de client** accessible en sélectionnant télécharger les **données client** dans le menu paramètres dans le coin supérieur droit. Cette page est utilisée pour permettre aux administrateurs de télécharger leurs propres informations, telles que le mappage de l’adresse IP et des informations géographiques, le mappage de chaque point d’accès sans fil et son adresse MAC, le mappage de point de terminaison à un point de terminaison, un modèle/type, etc.
  
![Capture d’écran montrant le tableau de bord de qualité des appels](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Dans la page **téléchargement de données du client** , utilisez le menu déroulant pour choisir un type de fichier de données à télécharger. Le type de données fichier indique le contenu du fichier (par exemple, «bâtiment» désigne le mappage d’une adresse IP et le bâtiment ainsi que d’autres informations géographiques, «point de terminaison» fait référence au mappage du nom du point de terminaison au point de terminaison/modèle/type... informations). Pour le moment, nous prenons en charge le téléchargement de types de données de «bâtiment» et de «point de terminaison» pour cqd.teams.microsoft.com (en mode Aperçu et non officiellement disponible), cqd.lync.com prend uniquement en charge le chargement de type de données «bâtiment». Quelques autres types de données seront ajoutés dans les versions suivantes.
    
2. Après avoir sélectionné le type de données du fichier, cliquez sur **Parcourir** pour choisir un fichier de données.
    
   - Le fichier de données doit être au format. TSV (valeurs séparées par des tabulations) ou. csv (valeurs séparées par des virgules). Si vous utilisez un fichier. csv, les champs qui contiennent une virgule doivent être entourés de guillemets ou être supprimés. Par exemple, si le nom de votre bâtiment est NY, NY, dans le fichier. csv, vous devez entrer «NY, NY».
    
   - La taille du fichier de données ne doit pas dépasser 50 Mo.

   - Les fichiers téléchargés sur cqd.teams.microsoft.com ont une limite de lignes étendue de 1 million afin de garantir une performance rapide des requêtes. Il est possible que nous puissions imposer cette limite sur cqd.lync.com également.
    
   - Pour chaque fichier de données, chaque colonne du fichier doit correspondre à un type de données prédéfini, abordé plus loin dans cette rubrique.
    
3. Après avoir sélectionné un fichier de données, spécifiez la **Date de début** et, éventuellement, **Spécifiez une date de fin**.
    
4. Après avoir sélectionné la **Date de début**, sélectionnez **charger** pour télécharger le fichier sur le serveur bord.
    
    Avant de télécharger le fichier, il est d’abord validé. Une fois validée, elle est stockée dans un blob Azure. Si la validation échoue ou que le fichier ne peut pas être stocké dans un objet BLOB Azure, un message d’erreur s’affiche et demande une correction du fichier. L’image ci-après illustre une erreur qui se produit lorsque le nombre de colonnes dans le fichier de données est incorrect.
    
     ![Capture d’écran montrant une erreur de validation de téléchargement](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. S’il n’y a aucune erreur lors de la validation, le chargement du fichier réussit. Vous pouvez ensuite voir le fichier de données chargé dans la table **Mes téléchargements** , qui affiche la liste complète des fichiers téléchargés pour le client actuel en bas de cette page.
    
    Chaque enregistrement affiche un fichier de données client téléchargé, avec le type de fichier, l’heure de la dernière mise à jour, la période, la description, une icône de suppression et une icône de téléchargement. Pour supprimer un fichier, sélectionnez l’icône de corbeille dans le tableau. Pour télécharger un fichier, sélectionnez l’icône de téléchargement dans la colonne **Télécharger** du tableau.
    
     ![Capture d’écran montrant la table Mes téléchargements](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. Notez que si vous optez pour l’utilisation de plusieurs fichiers de données bâtiment ou de plusieurs fichiers de données de point de terminaison, la vitesse d’opération de certains rapports sera plus lente.

### <a name="tenant-data-file-format-and-structure"></a>Format et structure du fichier de données client
<a name="BKMKTenantDataFile"> </a>

### <a name="building-data-file"></a>Création d’un fichier de données
BORD utilise le fichier de données bâtiment en dérivant d’abord la colonne de sous-réseau du développement de la colonne réseau + plage du réseau, puis en reliant la colonne de sous-réseau à la première colonne de sous-réseau/deuxième sous-réseau de l’enregistrement d’appel pour afficher la création/la ville/le pays/la région... concernant. Pour que le format du fichier de données réussisse le contrôle de validation avant téléchargement, il doit respecter les conditions suivantes.
  
- Il doit s’agir d’un fichier. tsv, ce qui signifie que sur chaque ligne, les colonnes sont séparées par une tabulation-ou d’un fichier. csv dont chaque colonne est séparée par une virgule.
    
- Le contenu du fichier de données ne comporte pas d’en-têtes de tableau. En d’autres termes, la première ligne du fichier de données doit être de véritables données, pas d’en-têtes comme «réseau», etc.
    
- Pour chaque colonne, le type de données peut uniquement être chaîne, nombre ou bool. S’il s’agit d’un nombre, la valeur doit être une valeur numérique; s’il s’agit de bool, la valeur doit être égale à 0 ou 1.
    
- Pour chaque colonne, si le type de données est String, les données peuvent être vides (mais doivent toujours être séparées par un délimiteur approprié (par exemple, un taquet de tabulation ou une virgule). Cela affecte simplement le champ à une valeur de chaîne vide.
    
- Chaque ligne doit comporter 14 colonnes, chaque colonne doit avoir le type de données suivant et les colonnes doivent être dans l’ordre indiqué dans le tableau suivant:
    
|**Nom de la colonne**|**Type de données**|**Exemple**|
|:-----|:-----|:-----|
|Réseau  <br/> |String  <br/> |192.168.1.0  <br/> |
|Nom réseau  <br/> |String  <br/> |États-Unis/Seattle/SEATTLE-SEA-1  <br/> |
|NetworkRange  <br/> |Numéro  <br/> |26/08/03  <br/> |
|BuildingName  <br/> |String  <br/> |SEATTLE-SEA-1  <br/> |
|Type de propriété  <br/> |String  <br/> |Chez  <br/> |
|Type de bâtiment  <br/> |String  <br/> |Arrêt  <br/> |
|BuildingOfficeType  <br/> |String  <br/> |Ingénieur  <br/> |
|Ville  <br/> |String  <br/> |Seattle  <br/> |
|ZipCode  <br/> |String  <br/> |98001  <br/> |
|Pays  <br/> |String  <br/> |Nous  <br/> |
|État  <br/> |String  <br/> |WA  <br/> |
|Région  <br/> |String  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |Bool  <br/> |1  <br/> |
|ExpressRoute  <br/> |Bool  <br/> |0,4  <br/> |
   
> [!IMPORTANT]
> La plage réseau peut être utilisée pour représenter un super-réseau (combinaison de plusieurs sous-réseaux avec un seul préfixe de routage). Les nouveaux chargements de construction seront examinés pour toutes les plages qui se chevauchent. Si vous avez déjà téléchargé un fichier de construction, vous devez télécharger le fichier actif et le télécharger à nouveau pour identifier les chevauchements et résoudre le problème avant de le télécharger à nouveau. Tout chevauchement dans les fichiers précédemment téléchargés risque de provoquer des mappages incorrects de sous-réseaux sur les bâtiments dans les rapports. Certaines implémentations de réseau privé virtuel n’indiquent pas exactement les informations de sous-réseau. Lorsque vous ajoutez un sous-réseau VPN au fichier de construction au lieu d’une entrée pour le sous-réseau, nous vous conseillons d’ajouter des entrées distinctes pour chaque adresse du sous-réseau VPN en tant que réseau 32 différent. Chaque ligne peut avoir les mêmes métadonnées de bâtiment. Par exemple, au lieu d’une ligne pour 172.16.18.0/24, vous devez disposer de lignes 256, avec une ligne pour chaque adresse entre 172.16.18.0/32 et 172.16.18.255/32, inclusive. 

### <a name="endpoint-data-file"></a>Fichier de données du point de terminaison
BORD utilise le fichier de données de point de terminaison en rejoignant sa colonne EndpointName à la première colonne nom du point de terminaison du client/deuxième nom du point de terminaison du client pour afficher les informations sur la création/le modèle de point de terminaison. Pour que le format du fichier de données réussisse le contrôle de validation avant téléchargement, il doit respecter les conditions suivantes.

- Il doit s’agir d’un fichier. tsv, ce qui signifie que sur chaque ligne, les colonnes sont séparées par une tabulation-ou d’un fichier. csv dont chaque colonne est séparée par une virgule.

- Le contenu du fichier de données ne comporte pas d’en-têtes de tableau. En d’autres termes, la première ligne du fichier de données doit être de véritables données, pas des en-têtes comme «EndpointName», etc.

- Pour chaque colonne, le type de données peut uniquement être de type chaîne et ne peut pas contenir plus de 64 caractères, ce qui représente une longueur maximale autorisée.

- Pour chaque colonne, il est possible de vider les données (tout en les séparant par un séparateur approprié (par exemple, un taquet de tabulation ou une virgule). Cela affecte simplement le champ à une valeur de chaîne vide.

- Il doit y avoir 7 colonnes pour chaque ligne et les colonnes doivent être dans l’ordre indiqué dans le tableau suivant.

- EndpointName doit être unique dans la mesure où l’opération de chargement échoue en raison de la ligne dupliquée, car elle provoquera une jointure incorrecte.

-  EndpointLabel1, EndpointLabel2, EndpointLable3 sont des étiquettes personnalisables par l’utilisateur, qui peuvent être des chaînes vides ou être des utilisateurs de valeurs, par exemple, un ordinateur portable 2018 désigné par le service informatique, «indicateur de ressources 5678»... etc.

|**Nom de la colonne**|**Type de données**|**Exemple**|
|:-----|:-----|:-----|
|EndpointName  <br/> |String  <br/> |1409W3534  <br/> |
|EndpointMake  <br/> |String  <br/> |Fabrikam Inc  <br/> |
|EndpointModel  <br/> |String  <br/> |Modèle Fabrikam 123  <br/> |
|EndpointType   <br/> |String  <br/> |Port  <br/> |
|EndpointLabel1  <br/> |String  <br/> |Ordinateur portable 2018 désigné  <br/> |
|EndpointLabel2  <br/> |String  <br/> |Indicateur de ressource 5678  <br/> |
|EndpointLabel3  <br/> |String  <br/> |Achat de 2018   <br/> |


## <a name="selecting-media-type-in-detailed-reports"></a>Sélection du type de média dans les rapports détaillés
<a name="BKMKMediaType"></a>

Les rapports détaillés prennent en charge l’affichage de la qualité et de la fiabilité des médias pour les types de média audio, vidéo, de partage d’application et vidéo. Le préfixe «audio», «Video», «partage» ou «VBSS» sont des dimensions, mesures et filtres qui sont propres à un type de média unique.
  
![Capture d’écran montrant les dimensions du tableau de bord de qualité des appels.](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
Si vous voulez afficher les dimensions et les mesures d’un type de média unique, il est possible que la nouvelle dimension du type de média et le filtre soient nécessaires. Par exemple, pour qu’un rapport affiche le nombre total de sessions sur différents types de médias, incluez la dimension MediaType.
  
![Capture d’écran montrant le nombre total de flux de tableau de bord de qualité d’appel.](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a>Voir aussi
[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de mauvaise qualité d’appel](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Tableau de bord Analyse des appels et Qualité des appels](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
