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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
- ms.teamsadmincenter.directrouting.cqd
ms.custom:
- Reporting
description: 'Découvrez comment activer et utiliser le Skype pour Business Online Dashboard qualité des appels et obtenir des rapports de synthèse de la qualité des appels. '
ms.openlocfilehash: 51e49d786f421777116e5c1d28ff8fcb7a11bcc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920460"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Activation et à l’aide de tableau de bord qualité d’appel pour Microsoft Teams et Skype pour Business Online

Découvrez comment configurer votre organisation Office 365 pour utiliser le tableau de bord qualité des appels pour surveiller la qualité des appels.
  
Le tableau de bord de la qualité des appels (CQD) pour Microsoft Teams et Skype pour Business Online vous permet d’obtenir des informations sur la qualité des appels effectués à l’aide de Microsoft Teams et Skype pour les services. Cette rubrique décrit les étapes que vous devez effectuer pour commencer la collecte des données.
  
> [!NOTE]
> Le CQD détaillée les rapports sont actuellement disponible en tant qu’aperçu technique et à tous les clients. 
  
## <a name="latest-changes-and-updates"></a>Mises à jour et les dernières modifications

Les dernières modifications apportées aux CQD sont les suivantes :
  
- Inclut les données Teams Microsoft outre Skype pour les données métiers en ligne.
    
- Rapports de synthèse incluent un filtre produit pour sélectionner toutes les données, des données de Microsoft Teams ou Skype pour les données métiers en ligne.

- Logique de classement de qualité flux vidéo et VBSS a été mis à jour. Reportez-vous à la [Classification des flux de données dans le tableau de bord qualité des appels](stream-classification-in-call-quality-dashboard.md) pour les définitions de classifieur le plus récent.

Reportez-vous à cet article pour obtenir la liste des [Dimensions et mesures disponibles dans le tableau de bord qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Vous trouverez plus d’informations sur les mises à jour et les modifications apportées au tableau de bord en cliquant sur le lien dans la **bonne !** bannière lorsqu’il est affiché dans le tableau de bord.
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Activer les rapports de synthèse de tableau de bord (CQD) appel Microsoft qualité

Avant de pouvoir commencer à l’aide de la CQD, vous devez l’activer pour votre organisation Office 365.
 
![SFB-logo-30x30.png](media/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**
 
1. Connectez-vous à votre organisation Office 365 à l’aide d’un compte d’administration, puis sélectionnez la vignette **Admin** pour ouvrir le centre d’administration.
    
2. Dans le volet gauche, sous **Centre d’administration**, sélectionnez **Skype pour les entreprises** pour ouvrir le Skype entreprise centre d’administration.
    
3. Dans le volet gauche, sélectionnez **Outils** dans Skype entreprise centre d’administration et sélectionnez **Skype pour Business Online appeler qualité du tableau de bord**.
    
     ![Skype pour les outils](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. Dans la page qui s’ouvre, connectez-vous avec votre compte d’administrateur Global, puis fournissez les informations d’identification du compte lorsque vous y êtes invité.
    
     ![Connexion CQD](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Après que vous être connecté, une fois activée, la CQD commencera collecte et traitement des données.

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**
 
1. Connectez-vous à votre organisation Office 365 à l’aide du compte d’administrateur de service Microsoft Teams, puis sélectionnez la vignette **Admin** pour ouvrir le centre d’administration.
    
2. Dans le volet gauche, sous **Centre d’administration**, sélectionnez **Les équipes Microsoft** pour ouvrir le centre d’administration Microsoft Teams.
    
3. Dans le centre d’administration Microsoft Teams, sélectionnez **tableau de bord qualité des appels** dans le volet gauche.
    
  
4. Dans la page qui s’ouvre, connectez-vous avec votre compte d’administrateur Global ou le compte d’administrateur du Service Microsoft équipes, puis fournissez les informations d’identification du compte lorsque vous y êtes invité.
    
     ![Connexion CQD](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Après que vous être connecté, une fois activée, la CQD commencera collecte et traitement des données.  
> [!NOTE]
> Il peut prendre quelques heures à traiter suffisamment de données pour afficher des résultats pertinents dans les rapports. 
  
## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Fonctionnalités de l’appel qualité du tableau de bord pour les équipes Microsoft et Skype pour les entreprises en ligne 
<a name="BKMKFeaturesOfTheCQD"> </a>

Les rapports de synthèse CQD fournissent un sous-ensemble des fonctionnalités planifiées pour des rapports détaillés. Les différences entre les deux éditions sont résumées ici :
  
|**Fonctionnalité**|**Rapports de synthèse**|**Rapports détaillés**|
|:-----|:-----|:-----|
|Mesure de partage d’application  <br/> |Non  <br/> |Oui  <br/> |
|Prise en charge des informations de création de client  <br/> |Oui  <br/> |Oui  <br/> |
|Prise en charge des informations de point de terminaison client  <br/> |Qu’en cqd.teams.microsoft.com  <br/> |Qu’en cqd.teams.microsoft.com  <br/> |
|Prise en charge de l’analyse de l’exploration  <br/> |Non  <br/> |Oui  <br/> |
|Mesures de la fiabilité du média  <br/> |Non  <br/> |Oui  <br/> |
|Rapports out-of-the-box  <br/> |Oui  <br/> |Oui  <br/> |
|Vue d’ensemble des rapports  <br/> |Oui  <br/> |Oui  <br/> |
|Jeu de rapports par utilisateur  <br/> |Non  <br/> |Oui  <br/> |
|Rapport définie personnalisation (ajouter, supprimer, modifier des rapports)  <br/> |Non  <br/> |Oui  <br/> |
|Partage des mesures d’écran vidéo  <br/> |Non  <br/> |Oui  <br/> |
|Mesures vidéo  <br/> |Non  <br/> |Oui  <br/> |
|Quantité de données disponibles  <br/> |6 derniers mois  <br/> |6 derniers mois  <br/> |
|Données Microsoft Teams  <br/> |Oui  <br/> |Oui  <br/> |
   
### <a name="out-of-the-box-reports"></a>Rapports out-of-the-box

Les deux éditions de CQD offrent un out-of-the-box experience, ce qui vous appeler les mesures de qualité sans avoir besoin de créer les nouveaux rapports. Une fois que les données sont envoyées dans le serveur principal, vous pouvez commencer à voir les données de qualité des appels dans les rapports.
  
### <a name="overview-reports"></a>Vue d’ensemble des rapports

Les deux éditions de la CQD fournissent un point d’entrée de haut niveau pour les informations de la qualité des appels globale, mais la façon dont les informations sont présentées dans les rapports de synthèse est différente de celle des rapports détaillés.
  
Rapports de synthèse fournissent une vue de rapport page à onglets simplifiée qui permet aux utilisateurs de naviguer rapidement et de comprendre l’ensemble statut qualité des appels et les tendances.
  
Les quatre onglets sont les suivantes :
  
- **La qualité des appels globale** - fournit des informations sur tous les flux, qui est un regroupement de flux de données Client-serveur et flux Client Client, ainsi que Client-serveur distinct et flux Client Client, dans l’écran des tendances mensuels et quotidiens.
    
- **Serveur - Client** - fournit des détails supplémentaires pour les flux de données entre les systèmes d’extrémité Client et serveur.
    
- **Client - Client** - fournit des détails supplémentaires pour le flux de données entre deux points de terminaison Client.
    
- **SLA de qualité vocale** - fournit des informations sur les appels qui sont inclus dans le Skype pour SLA de qualité vocale en ligne Business.
    
### <a name="overall-call-quality-tab"></a>Onglet de la qualité des appels globale

Utiliser les données sous cet onglet pour évaluer le statut de la qualité des appels et les tendances en examinant les pourcentages d’une mauvaise le nombre de flux. La légende dans le coin supérieur droit indique les couleurs et les éléments visuels représentent ces mesures.
  
![Clé de données CQD](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Flux de données est classés dans trois groupes : une bonne et une mauvaise non classés. Il sont également calculées que médiocre valeurs *%* qui permettent de vous le rapport du flux classé comme *médiocre* au nombre total de flux classés. Dans la mesure où *mauvaise % = médiocres flux / (mauvaise flux + flux bonne) * 100* , ainsi la *mauvaise %* non affectés par la présence de plusieurs flux *Unclassified* . Pour ce qui est utilisé pour classer un flux de données en tant qu’une mauvaise ou bon, reportez-vous à la [Classification des flux de données dans le tableau de bord qualité des appels](stream-classification-in-call-quality-dashboard.md).
  
Utiliser l’échelle sur la gauche pour mesurer les valeurs de nombre de flux de données.
  
![Nombre de données CQD](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Utiliser l’échelle sur la droite pour mesurer les valeurs d’une mauvaise %.
  
![Données CQD pour cent](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Vous pouvez également obtenir les valeurs numériques en plaçant la souris sur une barre.
  
> [!NOTE]
> L’exemple suivant provient d’un jeu de données très petit exemple, et les valeurs ne sont pas réalistes pour un déploiement réel. 
  
![Numérique de données CQD](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Le volume de flux global est un facteur important pour déterminer quelle mesure les pourcentages d’une mauvaise calculés. Petit volume de flux globales, moins fiable les valeurs en pourcentage médiocre signalés sont.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Onglet serveur-Client et des onglets de Client-Client

Ces deux onglets fournissent des détails supplémentaires pour les flux qui a eu lieu dans les scénarios de point de terminaison au point de terminaison. Les onglets ont quatre sections réductibles, représentant les quatre scénarios sous lequel afficherait flux multimédias.
  
- Filaire à l’intérieur
    
- Filaire à l’extérieur
    
- Inside Wi-Fi
    
- Extérieur Wi-Fi
    
#### <a name="inside-test"></a>Test à l’intérieur

Lors du traitement, le serveur principal CQD classifie un flux de données en tant *qu’à l’intérieur* ou *extérieur* à l’aide des informations de création, si elle existe. Points de terminaison de chaque flux sont associés à une adresse de sous-réseau. Si le sous-réseau est dans la liste des sous-réseaux marqués InsideCorp dans les informations de construction téléchargées, il est considéré *à l’intérieur*. Si la création des informations n'a pas encore été téléchargé, à l’intérieur de Test sera toujours classer les flux comme *extérieur*. Notez qu’à l’intérieur de Test pour le scénario Client-serveur ne tient compte que le point de terminaison client. Étant donné que les serveurs sont toujours à l’extérieur du point de vue d’un utilisateur, il n’est pas pris en compte dans le test.
  
#### <a name="wired-vs-wifi"></a>Filaire et Wi-Fi

Comme les noms indiquent, il s’agit d’un critère de classement en fonction du type de connexions client. Là encore, serveur toujours filaire et il n’est pas inclus dans le calcul.
  
> [!NOTE]
> Étant donné un flux, si un des deux points de terminaison est connecté à un réseau Wi-Fi, puis il est considéré comme Wi-Fi dans CQD. 
  
## <a name="selecting-product-data-to-see-in-reports"></a>Sélection de données de produit à afficher dans les rapports
<a name="BKMKProductFilter"></a>

Dans le résumé et emplacement améliorée des rapports, vous pouvez utiliser la liste déroulante **Filtre de produits** pour afficher toutes les données de produit, seules les données Teams Microsoft ou uniquement Skype pour les données métiers en ligne.
  
![Capture d’écran montre le contrôle de filtre de produit avec les options pour tous les, Microsoft Teams et Skype pour les entreprises.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Dans des rapports détaillés, vous pouvez utiliser la dimension **Équipes est** pour filtrer les données à Microsoft Teams ou Skype pour les données métiers en ligne dans le cadre de la définition du rapport.
  
## <a name="upload-tenant-data-information"></a>Téléchargement de données client
<a name="BKMKTenantDataInformationUpload"></a>

Le tableau de bord des rapports de synthèse CQD comprend une page **De téléchargement de données client** , accédée en sélectionnant le **Téléchargement des données client** dans le menu Paramètres dans le coin supérieur droit. Cette page permet de télécharger leurs propres informations, telles que le mappage de l’adresse IP et les informations géographiques, le mappage de chaque point d’accès sans fil et son adresse MAC, mappage du point de terminaison au point de terminaison de création / / Type de modèle, etc. pour les administrateurs.
  
![Tableau de bord CQD](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Dans la page **De téléchargement de données client** , utilisez le menu déroulant pour choisir un type de fichier de données pour le téléchargement. Le type de données de fichier désigne le contenu du fichier (par exemple, « Building » fait référence à un mappage d’adresse IP et création ainsi que d’autres informations géographiques, « Endpoint » fait référence au mappage du nom du point de terminaison au point de terminaison création / / Type de modèle... informations). Actuellement nous prennent en charge les types de données « Building » et « Endpoint » de téléchargement pour cqd.teams.microsoft.com (dans la fenêtre Aperçu et ne pouvez pas officiellement encore), prend uniquement en charge cqd.lync.com télécharger un type de données « Création ». Quelques autres types de données seront ajoutées à des versions ultérieures.
    
2. Après avoir sélectionné le type de données de fichier, cliquez sur **Parcourir** pour choisir un fichier de données.
    
   - Le fichier de données doit être un fichier .tsv (valeurs séparées par des tabulations) ou .csv (valeurs séparées par des virgules). Si vous utilisez un fichier .csv, un champ qui contient une virgule doivent être entourées de guillemets ou que la virgule supprimée. Par exemple, si votre nom est NY, NY, dans le fichier .csv elle doit être saisie comme « NY, NY ».
    
   - Le fichier de données doit être non supérieur à 50 Mo.

   - Fichier téléchargé vers cqd.teams.microsoft.com a développé la limite des lignes de 1 000 000 pour accélérer les performances des requêtes. Nous pouvons imposer cette limite sur cqd.lync.com également.
    
   - Pour chaque fichier de données, chaque colonne dans le fichier doit correspondre à un type de données prédéfini, décrit plus loin dans cette rubrique.
    
3. Après avoir sélectionné un fichier de données, spécifiez la **date de début** et, éventuellement, **Spécifiez une date de fin**.
    
4. Après avoir sélectionné la **date de début**, sélectionnez **Télécharger** pour télécharger le fichier sur le serveur CQD.
    
    Avant que le fichier est téléchargé, il est tout d’abord validé. Une fois validée, elle est stockée dans un objet blob Azure. Si validation échoue ou que le fichier ne peut pas être stocké dans un objet blob Azure et un message d’erreur s’affiche et demande une correction au fichier. L’image suivante montre une erreur ne se produise lorsque le nombre de colonnes dans le fichier de données est incorrect.
    
     ![Erreur de validation de téléchargement CQD exemple](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Si aucune erreur ne se produire lors de la validation, le téléchargement du fichier réussit. Vous pouvez voir le fichier de données téléchargées dans la table **Mes téléchargements** , qui affiche la liste complète de tous les fichiers téléchargés pour le client au bas de la page actuels.
    
    Chaque enregistrement indique client téléchargé un fichier de données, avec un type de fichier, heure de la dernière mise à jour, période, description, une icône de suppression et une icône de téléchargement. Pour supprimer un fichier, sélectionnez l’icône de la Corbeille secondaire dans le tableau. Pour télécharger un fichier, sélectionnez l’icône de téléchargement dans la colonne de **téléchargement** de la table.
    
     ![Chargement de mes CQD de table](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-structure"></a>Structure et le format de fichier de données client
<a name="BKMKTenantDataFile"> </a>

### <a name="building-data-file"></a>Fichier de données de création
CQD utilise la création de fichier de données en premier dérivent de colonne sous-réseau développée réseau + NetworkRange colonne, puis rejoindre sous-réseau à la colonne du premier Subnet/Second sous-réseau de l’enregistrement d’appel pour afficher la construction/ville/pays/région... plus d’informations. Le format du fichier de données que vous téléchargez doit répondre à la commande suivante pour transmettre le contrôle de validation avant le téléchargement.
  
- Le fichier doit être un fichier .tsv, ce qui signifie, dans chaque ligne, les colonnes sont séparées par une tabulation, ou un fichier .csv avec chaque colonne séparé par une virgule.
    
- Le contenu du fichier de données n’inclut pas les en-têtes de tableau. Que signifie que la première ligne du fichier de données doit être des données réelles, pas d’en-têtes comme « Réseau », etc..
    
- Pour chaque colonne, le type de données peut uniquement être Bool, nombre ou chaîne. Si c’est le nombre, la valeur doit être une valeur numérique ; s’il est Bool, la valeur doit être 0 ou 1.
    
- Pour chaque colonne, si le type de données est la chaîne, les données ne peuvent être vides (mais doivent toujours être séparées par un séparateur approprié (autrement dit, un onglet ou une virgule). Cela affecte uniquement ce champ une valeur de chaîne vide.
    
- Il doit y avoir 14 colonnes pour chaque ligne, chaque colonne doit avoir les données suivantes type et les colonnes doivent être dans l’ordre indiqué dans le tableau suivant :
    
|**Nom de la colonne**|**Type de données**|**Exemple**|
|:-----|:-----|:-----|
|Réseau  <br/> |String  <br/> |192.168.1.0  <br/> |
|Nom_réseau  <br/> |String  <br/> |États-Unis/Seattle/SEATTLE-marin-1  <br/> |
|NetworkRange  <br/> |Numéro  <br/> |26  <br/> |
|BuildingName  <br/> |String  <br/> |SEATTLE-MARIN-1  <br/> |
|OwnershipType  <br/> |String  <br/> |Contoso  <br/> |
|BuildingType  <br/> |String  <br/> |Arrêt de l’informatique  <br/> |
|BuildingOfficeType  <br/> |String  <br/> |Ingénierie  <br/> |
|Ville  <br/> |String  <br/> |Seattle  <br/> |
|ZipCode  <br/> |String  <br/> |98001  <br/> |
|Pays  <br/> |String  <br/> |NOUS  <br/> |
|État  <br/> |String  <br/> |WA  <br/> |
|Région  <br/> |String  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |Bool  <br/> |1  <br/> |
|ExpressRoute  <br/> |Bool  <br/> |0  <br/> |
   
> [!IMPORTANT]
> La plage réseau peut être utilisée pour représenter un supernet (combinaison de plusieurs sous-réseaux avec un préfixe de routage unique). Tous les téléchargements de construction nouvelle seront vérifiées pour toutes les plages qui se chevauchent. Si vous avez déjà chargé un fichier de construction, téléchargez le fichier en cours et téléchargez de nouveau pour identifier les chevauchements et corriger le problème avant de le télécharger à nouveau. Les mappages de sous-réseaux aux bâtiments dans les rapports incorrectes peut entraîner un chevauchement des fichiers téléchargés précédemment. Certaines implémentations VPN ne signalent pas correctement les informations de sous-réseau. Il est recommandé que lors de l’ajout d’un sous-réseau de réseau privé virtuel pour la création du fichier, au lieu d’une entrée pour le sous-réseau, des entrées sont ajoutées pour chaque adresse de sous-réseau de réseau privé virtuel comme un réseau distinct de 32 bits. Chaque ligne peut avoir les mêmes métadonnées de construction. Par exemple, au lieu d’une ligne pour 172.16.18.0/24, vous devez disposer de 256 lignes, avec une ligne pour chaque adresse entre 172.16.18.0/32 et 172.16.18.255/32, inclus. 

### <a name="endpoint-data-file"></a>Fichier de données du point de terminaison
CQD utilise le fichier de données du point de terminaison en joignant sa colonne EndpointName à la colonne du nom du point de terminaison Client premier Client du point de terminaison Name/Second de l’enregistrement d’appel pour afficher les informations de point de terminaison création / / Type de modèle. Le format du fichier de données que vous téléchargez doit répondre à la commande suivante pour transmettre le contrôle de validation avant le téléchargement.

- Le fichier doit être un fichier .tsv, ce qui signifie, dans chaque ligne, les colonnes sont séparées par une tabulation, ou un fichier .csv avec chaque colonne séparé par une virgule.

- Le contenu du fichier de données n’inclut pas les en-têtes de tableau. Cela signifie que la première ligne du fichier de données doit être des données réelles, pas les en-têtes comme « EndpointName », etc..

- Pour chaque colonne, le type de données peut uniquement être chaîne et il doit avoir pas plus de 64 caractères, qui est maximal longueur autorisée.

- Pour chaque colonne, les données ne peuvent être vides (mais doivent toujours être séparées par un séparateur approprié (autrement dit, un onglet ou une virgule). Cela affecte uniquement ce champ une valeur de chaîne vide.

- Il doit y avoir 7 colonnes pour chaque ligne et les colonnes doivent être dans l’ordre indiqué dans le tableau suivant.

- EndpointName doit être unique dans le cas contraire le transfert échoue en raison d’une ligne en double dans la mesure où elle rejoindre incorrecte.

-  EndpointLabel1, EndpointLabel2, EndpointLable3 sont étiquettes personnalisable utilisateur, ils peuvent être des chaînes vides ou les utilisateurs de valeur préfèrent tel que « Informatique désigné 2018 portables », « étiquette 5678"... etc..

|**Nom de la colonne**|**Type de données**|**Exemple**|
|:-----|:-----|:-----|
|EndpointName  <br/> |String  <br/> |1409W3534  <br/> |
|EndpointMake  <br/> |String  <br/> |Fabrikam Inc  <br/> |
|EndpointModel  <br/> |String  <br/> |Modèle de Fabrikam 123  <br/> |
|EndpointType   <br/> |String  <br/> |Ordinateur portable  <br/> |
|EndpointLabel1  <br/> |String  <br/> |IT désigné 2018 portables  <br/> |
|EndpointLabel2  <br/> |String  <br/> |Numéro d’identification 5678  <br/> |
|EndpointLabel3  <br/> |String  <br/> |Achat 2018   <br/> |


## <a name="selecting-media-type-in-detailed-reports"></a>Sélection de type de média dans des rapports détaillés
<a name="BKMKMediaType"></a>

Les rapports détaillés prennent en charge la recherche au niveau de fiabilité de qualité et les médias pour l’audio, vidéo, partage d’application et types de supports de partage d’écran vidéo. Dimensions, mesures et des filtres qui sont spécifiques à un seul type de support ont « Audio », « Vidéos », « AppSharing » ou « VBSS » comme préfixe.
  
![Dimensions de tableau de bord de la qualité des appels.](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
Si vous souhaitez afficher les dimensions et les mesures à prendre pour un seul type de support, le filtre et la nouvelle dimension MediaType peuvent être nécessaires. Par exemple, pour un état qui affiche que la total des sessions compte entre les différents types de médias, vous devez inclure la dimension de MediaType.
  
![Nombre de flux Total du tableau de bord qualité des appels.](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a>Voir aussi
[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Permet de résoudre les problèmes de qualité médiocre appel Analytique d’appel](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Tableau de bord Analyse des appels et Qualité des appels](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
