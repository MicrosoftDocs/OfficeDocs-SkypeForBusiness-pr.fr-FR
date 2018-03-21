---
title: "Mise sous tension et à l’aide du tableau de bord qualité appeler"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: "Découvrez comment activer et utiliser le Skype pour entreprise en ligne appeler tableau de bord qualité et obtenir des rapports de synthèse de la qualité des appels. "
ms.openlocfilehash: d2cbcf0a7acdfebd3ba3fb1a2cc109d32f4213a9
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Mise sous tension et à l’aide d’appeler le tableau de bord qualité pour Microsoft Teams et Skype pour professionnels en ligne

Découvrez comment configurer votre organisation d’Office 365 pour utiliser le tableau de bord qualité appeler pour surveiller la qualité des appels.
  
Le tableau de bord de qualité appeler (CQD) pour Teams de Microsoft et Skype pour Business Online vous permet d’obtenir des informations sur la qualité des appels effectués à l’aide de Microsoft Teams et Skype pour les services. Cette rubrique décrit les étapes que vous aurez besoin pour lancer la collecte de données.
  
> [!NOTE]
> Le CQD détaillée les rapports sont actuellement disponibles en tant que Tech Preview mais disponible à tous les clients. 
  
## <a name="latest-changes-and-updates"></a>Mises à jour et les modifications les plus récentes

Les modifications les plus récentes pour CQD sont les suivantes :
  
- Inclut des données de Microsoft Teams en plus Skype pour les données d’entreprise en ligne.
    
- Rapports récapitulatifs comprennent un filtre produit pour sélectionner toutes les données, les données de Microsoft Teams ou Skype pour les données métiers en ligne.
    
Reportez-vous à cet article pour obtenir la liste des [Dimensions et mesures disponibles dans l’appel de tableau de bord qualité pour les équipes Microsoft et Skype pour l’activité en ligne](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Vous pouvez trouver des informations sur les mises à jour et modifications apportées au tableau de bord en cliquant sur **bonne nouvelle !** dans le tableau de bord. Vous pouvez accéder au [tableau de bord qualité d’appel](https://aka.ms/CQDOnline). 
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Activer les rapports de synthèse de tableau de bord (CQD) appel Microsoft qualité

Avant de commencer à l’aide de la CQD, vous devez l’activer pour votre organisation d’Office 365.
  
1. Connectez-vous à votre organisation d’Office 365 à l’aide d’un compte d’administrateur et sélectionnez la mosaïque **Admin** pour ouvrir le centre d’administration.
    
2. Dans le volet gauche, sous **Centre d’administration**, sélectionnez **Skype pour les entreprises** à ouvrir le Skype pour le centre d’administration Business.
    
3. Dans le Skype pour le centre d’administration Business, dans le volet gauche, sélectionnez **Outils** , puis sélectionnez **Skype pour entreprise en ligne appeler tableau de bord qualité**.
    
     ![Skype pour outils professionnels](../images/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. Sur la page qui s’ouvre, connectez-vous avec votre compte d’administrateur Global et ensuite fournir les informations d’identification du compte lorsque vous y êtes invité.
    
     ![CQD connexion](../images/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Une fois que vous êtes connecté, une fois activé, le CQD commencera collecte et traitement des données.
  
> [!NOTE]
> Il peut prendre quelques heures pour traiter suffisamment de données pour afficher des résultats significatifs dans les rapports. 
  
## <a name="features-of-the-call-quality-dashboard-for-skype-for-business-online"></a>Fonctionnalités du tableau de bord qualité appel de Skype pour les entreprises en ligne
<a name="BKMKFeaturesOfTheCQD"> </a>

Rapports de synthèse de CQD fournit un sous-ensemble des fonctionnalités planifiées pour des rapports détaillés. Les différences entre les deux éditions sont résumées ici :
  
|**Fonctionnalité**|**Rapports de synthèse**|**Rapports détaillés.**|
|:-----|:-----|:-----|
|Métrique de partage d’application  <br/> |Non  <br/> |Oui  <br/> |
|Prise en charge des informations de création de client  <br/> |Oui  <br/> |Oui  <br/> |
|Prise en charge de l’analyse descendante  <br/> |Non  <br/> |Oui  <br/> |
|Mesures de fiabilité multimédia  <br/> |Non  <br/> |Oui  <br/> |
|L’emploi de rapports  <br/> |Oui  <br/> |Oui  <br/> |
|Vue d’ensemble des rapports  <br/> |Oui  <br/> |Oui  <br/> |
|Jeu de rapports par utilisateur  <br/> |Non  <br/> |Oui  <br/> |
|État défini de personnalisation (ajouter, supprimer, modifier des rapports)  <br/> |Non  <br/> |Oui  <br/> |
|Écran vidéo-partage de mesures  <br/> |Non  <br/> |Oui  <br/> |
|Mesures de graphique  <br/> |Non  <br/> |Oui  <br/> |
|Quantité de données disponibles  <br/> |6 derniers mois  <br/> |6 derniers mois  <br/> |
|Données de Microsoft Teams  <br/> |Oui  <br/> |Oui  <br/> |
   
### <a name="out-of-the-box-reports"></a>L’emploi de rapports

Les deux éditions de CQD fournissent un-de-l’emploi expérience, vous donnant ainsi appeler des mesures de qualité sans avoir à créer de tout nouveaux rapports. Une fois que les données sont traitées dans le back-end, vous pouvez commencer à voir des appels des données de qualité dans les rapports.
  
### <a name="overview-reports"></a>Vue d’ensemble des rapports

Les deux éditions de le CQD fournissent un point d’entrée de haut niveau pour les informations de qualité globale appel, mais la présentation des informations dans les rapports de résumé est différente de celle des rapports détaillés.
  
Rapports récapitulatifs fournissent un mode d’état de page à onglets simplifiée qui permet aux utilisateurs de parcourir rapidement et de comprendre l’état de qualité d’appel et les tendances globales.
  
Les quatre onglets sont les suivantes :
  
- **Appelez la qualité** - fournit des informations sur l’ensemble des flux, ce qui constitue un regroupement de flux de données Client-serveur et flux de données Client-Client, ainsi que Client-serveur distinct et flux Client-Client, sous la forme d’évolution mensuelle et journalière.
    
- **Serveur - Client** - fournit des détails supplémentaires sur le flux de données entre les points de terminaison de serveur et le Client.
    
- **Client - Client** - fournit des détails supplémentaires sur le flux de données entre deux points de terminaison de Client.
    
- **SLA de qualité vocale** - fournit des informations sur les appels qui sont inclus dans le Skype pour entreprise qualité vocale en ligne contrat SLA.
    
### <a name="overall-call-quality-tab"></a>Onglet d’appeler la qualité globale

Utilisez les données de cet onglet pour évaluer l’état de qualité d’appel et des tendances en examinant le nombre de flux et les pourcentages faibles. La légende dans le coin supérieur droit affiche les couleurs et les éléments visuels représentent ces mesures.
  
![Clé de données de CQD](../images/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Flux de données est classés dans trois groupes : une bonne et une mauvaise non classifié. Il sont également calculées faible valeurs *%* qui permettent de vous le rapport des flux de données classées comme * médiocre * le nombre total de flux classifiés. Dans la mesure où *médiocre % = médiocres flux / (mauvaise flux + bon flux) * 100* , cela rend la *mauvaise %* pas affecté par la présence plusieurs flux *Unclassified* . Pour ce qui est utilisé pour la classification d’un flux de données en tant que de bonne ou de mauvaise, reportez-vous à [Appeler les seuils de qualité](https://aka.ms/cqd_quality_thresholds).
  
Pour mesurer les valeurs de nombre d’appel, utilisez l’échelle sur la gauche.
  
![Nombre CQD de données](../images/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Utiliser l’échelle à droite pour mesurer les valeurs faibles %.
  
![Données CQD pour cent](../images/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Vous pouvez également obtenir les valeurs numériques en pointant la souris sur une barre.
  
> [!NOTE]
> L’exemple suivant provient d’un jeu de données très petit échantillon, et les valeurs ne sont pas réalistes pour un déploiement réel. 
  
![Numérique de données de CQD](../images/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Le volume global de flux de données est un facteur important pour déterminer quelle mesure les pourcentages faibles calculés. Plus le volume du flux global, moins fiable les valeurs de pourcentage de mauvaise signalés sont.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Onglet serveur-Client et les onglets Client-Client

Ces deux onglets fournissent des détails supplémentaires pour les flux qui se déroulent dans les scénarios de point de terminaison au point de terminaison. Les deux onglets ont quatre sections réductibles, représentant les quatre scénarios qui sous lequel afficherait le flux de données.
  
- À l’intérieur de réseau câblé
    
- En dehors de réseau câblé
    
- À l’intérieur de la Wi-Fi
    
- À l’extérieur de la Wi-Fi
    
#### <a name="inside-test"></a>Test à l’intérieur

Au cours du traitement, CQD back-end classifie un flux *à l’intérieur* ou *extérieur* à l’aide des informations de génération, si elle existe. Points de terminaison de chaque flux de données sont associés à une adresse de sous-réseau. Si le sous-réseau est dans la liste des sous-réseaux dans les informations de construction téléchargées, il est considéré à l’intérieur. Si d’informations n’a pas encore été téléchargée, puis à l’intérieur d’un Test va toujours classer les flux comme *à l’extérieur* . Veuillez noter qu’à l’intérieur de Test pour un scénario Client-serveur considère uniquement le point de terminaison client. Les serveurs étant toujours en dehors du point de vue d’un utilisateur, ce n’est pas pris en compte dans le test.
  
#### <a name="wired-vs-wifi"></a>Filaire et le Wi-Fi

Comme l’indiquent les noms, il s’agit d’un critère de classification en fonction du type de connexions client. À nouveau, serveur est toujours câblée et il n’est pas inclus dans le calcul.
  
> [!NOTE]
> Étant donné un flux de données, si un des deux points de terminaison est connecté à un réseau Wi-Fi, puis il est classé comme Wifi dans CQD. 
  
## <a name="selecting-product-data-to-see-in-reports"></a>Sélection des données de produit à afficher dans les rapports
<a name="BKMKFeaturesOfTheCQD"> </a>

Dans le résumé et l’emplacement des rapports améliorés, vous pouvez utiliser la liste déroulante **Filtre de produits** pour afficher toutes les données de produit, uniquement les données de Microsoft Teams, ou uniquement les Skype pour les données d’entreprise en ligne.
  
![Capture d’écran montre le contrôle de filtre de produit avec options pour toutes les Teams de Microsoft et Skype pour les entreprises.](../images/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Dans des rapports détaillés, vous pouvez utiliser la dimension des équipes pour filtrer les données à Microsoft Teams ou Skype pour des données commerciales en ligne dans le cadre de la définition de l’état.
  
## <a name="upload-building-information"></a>Informations de construction de téléchargement
<a name="BKMKFeaturesOfTheCQD"> </a>

Le tableau de bord des rapports de synthèse de CQD inclut une page **De téléchargement de données client** , accédée en sélectionnant le **Téléchargement des données clients** à partir du menu Paramètres, dans le coin supérieur droit. Cette page est utilisée pour les administrateurs de télécharger leurs propres informations, par exemple le mappage d’adresse IP et les informations géographiques, mappage de chaque point d’accès sans fil et l’adresse MAC, etc..
  
![Tableau de bord CQD](../images/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Sur la page **De téléchargement de données clients** , utilisez le menu déroulant pour choisir un type de fichier de données pour le téléchargement. Le type de données de fichier indique le contenu du fichier (par exemple, « Construction » fait référence au mappage d’adresse IP et la création ainsi que d’autres informations géographiques). Actuellement nous sommes uniquement en charge le type de données de « Construction ». Quelques autres types de données seront ajoutés avec les versions ultérieures.
    
2. Après avoir sélectionné le type de données de fichier, cliquez sur **Parcourir** pour choisir un fichier de données.
    
  - Le fichier de données doit être un fichier .tsv (valeurs séparées par des tabulations) ou .csv (valeurs séparées par des virgules). Si vous utilisez un fichier .csv, un champ qui contient une virgule doit contenir de guillemets ou que la virgule supprimée. Par exemple, si votre nom est NY, NY, dans le fichier .csv elle doit être entrée en tant que « NY, NY ».
    
  - Le fichier de données doit être non supérieur à 50 Mo.
    
  - Pour chaque fichier de données, chaque colonne du fichier doit correspondre à un type de données prédéfini, décrit plus loin dans cette rubrique.
    
3. Après avoir sélectionné un fichier de données, spécifiez la **date de début** et, le cas échéant, **Spécifiez une date de fin**.
    
4. Après avoir sélectionné la **date de début**, sélectionnez **Télécharger** pour télécharger le fichier sur le serveur CQD.
    
    Avant que le fichier est téléchargé, il est tout d’abord validé. Une fois validée, elle est stockée dans un blob Azure. Si validation échoue ou que le fichier ne peut pas être stocké dans un blob Azure, un message d’erreur s’affiche et demande une correction dans le fichier. L’image suivante illustre une erreur ne se produise lorsque le nombre de colonnes dans le fichier de données est incorrect.
    
     ![Erreur de validation de chargement de CQD exemple](../images/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Si aucune erreur ne se produit lors de la validation, le téléchargement du fichier réussit. Vous pouvez voir le fichier de données téléchargées dans la table **Mes téléchargements** , qui affiche la liste complète de tous les fichiers téléchargés pour les clients en cours au bas de cette page.
    
    Chaque enregistrement affiche un locataire téléchargé fichier de données, avec le type de fichier, heure de la dernière mise à jour, période, description, suppression et une icône de téléchargement. Pour supprimer un fichier, sélectionnez l’icône de la Corbeille dans le tableau. Pour télécharger un fichier, sélectionnez l’icône de téléchargement dans la colonne de **téléchargement** de la table.
    
     ![Chargement de mes CQD de table](../images/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-building-data-file-structure"></a>Format de fichier de données de clients et de la structure de fichier de données de construction
<a name="BKMKTenantDataFile"> </a>

Le format du fichier de données que vous chargez doit satisfaire comme suit pour passer le contrôle de validation avant de le télécharger.
  
- Le fichier doit être un fichier .tsv, ce qui signifie que, dans chaque ligne, les colonnes sont séparées par une tabulation, ou un fichier .csv avec chaque colonne séparée par une virgule.
    
- En-têtes de tableau n’inclut pas le contenu du fichier de données. Que signifie que la première ligne du fichier de données doit être des données réelles, pas d’en-têtes comme « Réseau », etc..
    
- Pour chaque colonne, le type de données ne peut y Bool, nombre ou chaîne. Si c’est le nombre, la valeur doit être une valeur numérique ; s’il s’agit de Bool, la valeur doit être 0 ou 1.
    
- Pour chaque colonne, si le type de données est la chaîne, les données ne peuvent être vides (mais toujours, doivent être séparés par délimités appropriée (c'est-à-dire, une tabulation ou une virgule). Cela affecte uniquement ce champ une valeur de chaîne vide.
    
- Il doit y avoir de 14 colonnes de chaque ligne et chaque colonne doit avoir les données suivantes type et que les colonnes doivent être dans l’ordre indiqué dans le tableau suivant :
    
|**Nom de la colonne**|**Type de données**|**Exemple**|
|:-----|:-----|:-----|
|Réseau  <br/> |Chaîne  <br/> |192.168.1.0  <br/> |
|Nom_réseau  <br/> |Chaîne  <br/> |États-Unis/Seattle/SEATTLE-SEA-1  <br/> |
|NetworkRange  <br/> |Numéro  <br/> |26  <br/> |
|BuildingName  <br/> |Chaîne  <br/> |SEATTLE-SEA-1  <br/> |
|OwnershipType  <br/> |Chaîne  <br/> |Contoso  <br/> |
|BuildingType  <br/> |Chaîne  <br/> |Arrêt de l’informatique  <br/> |
|BuildingOfficeType  <br/> |Chaîne  <br/> |Ingénierie  <br/> |
|Ville  <br/> |Chaîne  <br/> |Seattle  <br/> |
|Code postal  <br/> |Chaîne  <br/> |98001  <br/> |
|Pays  <br/> |Chaîne  <br/> |NOUS  <br/> |
|État  <br/> |Chaîne  <br/> |WA  <br/> |
|Région  <br/> |Chaîne  <br/> |MSU  <br/> |
|InsideCorp  <br/> |Bool  <br/> |1  <br/> |
|ExpressRoute  <br/> |Bool  <br/> |0  <br/> |
   
> [!IMPORTANT]
> La plage réseau peut servir à représenter une supernet (combinaison de plusieurs sous-réseaux avec un préfixe de routage unique). Tous les nouveaux téléchargements de construction seront vérifiées de chevauchement de plages. Si vous avez déjà chargé un fichier de construction, téléchargez le fichier en cours et téléchargez à nouveau pour identifier les chevauchements et résoudre le problème avant de le télécharger à nouveau. Tout chevauchement dans les fichiers précédemment téléchargés peut entraîner les mappages incorrects de sous-réseaux et bâtiments dans les rapports. Certaines implémentations VPN ne signalent pas correctement les informations de sous-réseau. Il est recommandé que lors de l’ajout d’un sous-réseau VPN à la création du fichier, au lieu d’une entrée pour le sous-réseau, séparez les entrées sont ajoutées pour chaque adresse dans le sous-réseau VPN comme un réseau distinct de 32 bits. Chaque ligne peut comporter les mêmes métadonnées de construction. Par exemple, au lieu d’une seule ligne de 172.16.18.0/24, vous devez disposer de 256 lignes, avec une ligne pour chaque adresse entre 172.16.18.0/32 et 172.16.18.255/32, inclus. 
  
## <a name="selecting-media-type-in-detailed-reports"></a>Sélection de type de média dans des rapports détaillés.
<a name="BKMKFeaturesOfTheCQD"> </a>

Les rapports détaillés prennent en charge le consultant à la fiabilité de qualité et support pour l’audio, la vidéo, le partage d’application et les types de supports de partage d’écran vidéo. Les filtres qui sont spécifiques à un seul type de support, les mesures et les dimensions ont « Audio », « Vidéo », « AppSharing » ou « VBSS » comme préfixe.
  
![Appelez les Dimensions du tableau de bord qualité.](../images/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
Si vous souhaitez afficher les dimensions et les mesures pour un seul type de support, la nouvelle dimension MediaType et le filtre peuvent être requis. Par exemple, pour un rapport qui affiche le total session compte entre les différents types de média, inclure la dimension MediaType.
  
![Appelez le nombre de flux Total du tableau de bord qualité.](../images/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a>Rubriques connexes
[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Permet de résoudre les problèmes d’appel de médiocre qualité Analytique d’appeler](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Différence entre l’appel Analytique et tableau de bord qualité appel ?](difference-between-call-analytics-and-call-quality-dashboard.md)
