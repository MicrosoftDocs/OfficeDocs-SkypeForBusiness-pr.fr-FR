---
title: Activer et utiliser le tableau de bord de qualité des appels
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
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
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Apprenez-en davantage sur l’activation et l’utilisation du tableau de bord de qualité des appels et obtenez des rapports de synthèse sur la qualité des appels.
ms.openlocfilehash: 95c4a777576b2cf574ba76d7f1b19de69f64dc88
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44047388"
---
# <a name="turn-on-and-use-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Activation et utilisation du tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online

Apprenez à configurer votre 365 ou Office 365 pour utiliser le tableau de bord de qualité des appels pour surveiller la qualité des appels.
  
Le tableau de bord de qualité des appels (bord) vous permet d’obtenir des renseignements sur la qualité des appels passés à l’aide de Microsoft teams et des services Skype entreprise online. Cette rubrique décrit la procédure de démarrage de la collecte de données que vous pouvez utiliser pour résoudre les problèmes de qualité d’appel.

Pour l’instant, les fonctionnalités avancées bord et bord sont disponibles pour une utilisation. Advanced bord est disponible à <span>https://cqd.teams.microsoft.com</span>l’adresse. Nouvelle URL sauf si vous êtes connecté à l’aide de vos informations d’identification d’administrateur.

## <a name="assign-roles-for-accessing-cqd"></a>Affecter des rôles pour accéder à bord

Attribuez des [rôles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) pour accéder à bord aux personnes qui ont besoin de les utiliser. 

Le tableau suivant vous montre les différents rôles possibles dans bord :


|  |Afficher les rapports  |Afficher les champs de EUII  |Créer des rapports  |Télécharger les données de bâtiment  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrateur général     |Oui          |Oui          |Oui          |Oui          |
|Administrateur du service Teams     |Oui          |Oui          |Oui          |Oui          |
|Administrateur des communications Teams     |Oui          |Oui          |Oui          |Oui          |
|Ingénieur du support technique pour les communications Teams     |Oui          |Oui          |Oui         |Non         |
|Spécialiste du support des communications teams     |Oui         |Non         |Oui         |Non         |
|Administrateur Skype entreprise     |Oui          |Oui          |Oui          |Oui          |
|Lecteur global Azure AD |Oui          |Oui          |Oui         |Non         |
|Microsoft 365 rapports lecteur<sup>1</sup>     |Oui         |Non         |Oui         |Non         |

<sup>1</sup> en plus de lire des rapports bord, le lecteur de rapports 365 Microsoft peut afficher tous les [rapports d’activité](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) dans le centre d’administration et les rapports du [Pack de contenu adoption de Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Si vous ne voyez pas EUII (informations d’identification de l’utilisateur final) et que vous disposez de l’un des rôles qui vous permettent d’accéder à ces informations, gardez à l’esprit que bord ne conserve EUII pendant 30 jours. Les éléments datant de plus de 30 jours sont supprimés.


## <a name="use-power-bi-to-analyze-cqd-data"></a>Utiliser Power BI pour analyser des données de bord

Nouveauté de janvier 2020 : [Télécharger les modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et enregistrer vos données bord.

Pour en savoir plus, voir [utiliser Power bi pour analyser les données de bord](CQD-Power-BI-query-templates.md) .


## <a name="latest-changes-and-updates"></a>Dernières modifications et mises à jour


La mise à jour bord (à compter du 1er novembre 2019) fournit un tableau de bord bord en temps réel proche. Les données bord sont désormais disponibles en moyenne dans 30 minutes (par rapport au bord précédent qui est en moyenne de 24 heures).  Le bord mis à jour utilise les informations d’identification de l’utilisateur final (EUII), ce qui permet aux administrateurs de descendre et de zoomer sur le niveau utilisateur. Il existe également des rapports d’interactivité permettant de prendre en charge de nouveaux scénarios, tels que :


- Qualité des appels par région :
  - date par région
  - agrégées jusqu’à la plage horaire
  - emplacements spécifiques
  - sous-réseau spécifique
  - utilisateurs concernés ou utilisateurs concernés

- Fiabilité/échec de l’appel par région :
  - date par région
  - agrégées jusqu’à la plage horaire
  - emplacements spécifiques
  - sous-réseau spécifique
  - utilisateurs concernés ou utilisateurs concernés

- Évaluer mon appel (RMC) par région : d’un mois à une autre dans la zone agrégés vers des emplacements spécifiques pour les utilisateurs qui fournissent des évaluations plus basses. BORD v3 inclut également le retour Verbatim.
- Support technique disponible pour un utilisateur particulier sur les appels ou réunions P2P, ou pour tous les participants et les détails de l’appel. Permet d’identifier les problèmes système potentiels en fonction de l’emplacement du réseau, des appareils ou du microprogramme.  
- Versions du client : Affichez la session et les comptes des utilisateurs pour chaque version du client, ou explorez les noms d’utilisateurs pour chaque version du client. Les filtres prédéfinis pour le type produit et client permettent de focaliser les versions sur des clients spécifiques.
- Points de terminaison : affiche les points de terminaison d’ordinateur mappés au PC/Mac. Affiche la qualité agrégée par création/modèle. Le mappage des données est semblable à la génération de données.

La prise en charge du RBAC bord Advanced (v3) est également prise en charge par le biais de l’accès EUII.  

Un administrateur peut gérer Skype entreprise Server 2019 (pas seulement Skype entreprise Online et Microsoft Teams) via bord version 3. Pour cela, vous devez disposer d’une implémentation hybride et de l’utilisation du connecteur de données d’appel. Pour plus d’informations, reportez-vous à la section [plan des données d’appel](/SkypeForBusiness/hybrid/plan-call-data-connector) .

BORD version 2 ajoutée :

- Données de Microsoft teams et de Skype entreprise Online
- Les rapports de synthèse incluent un filtre produit permettant de sélectionner toutes les données, les données de Microsoft teams ou les données de Skype entreprise online.
- Mise à jour de la logique de classification de la qualité des flux vidéo et VBSS. Pour plus d’en plus d’une définition de classifieur [, voir classification en flux dans le tableau de bord qualité des appels](stream-classification-in-call-quality-dashboard.md)

Consultez cet article pour obtenir la liste des [dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Pour afficher des informations sur les mises à jour et les modifications apportées au tableau de bord, cliquez sur le lien dans la **bonne nouvelle.** bannière affichée sur le tableau de bord.

BORD version 1 a fourni les fonctionnalités suivantes aux administrateurs 2015 de Skype entreprise Server :

- Accès aux données de rapport mises en cache pour un accès rapide
- Liens en profondeur vers des pages de rapport pour le partage et la publication d’informations
- Simplification de la modification et de la création de rapports et métadonnées modifiables pour les descriptions de rapport
- API Web permettant d’accéder par programmation aux données du cube en vue de leur utilisation dans des tableaux de bord personnalisés

## <a name="cqd-near-real-time-nrt-data"></a>BORD de données en temps réel (NRT)

Advanced bord (v3, publiée le 2019 novembre) utilise un flux de données en temps réel. Les enregistrements d’appels sont disponibles sur le portail bord en moyenne dans 30 minutes (par rapport au bord précédent qui est en moyenne de 24 heures). Les enregistrements d’appels à partir du pipeline NRT sont uniquement disponibles pendant quelques mois avant d’être supprimés du jeu de données. BORDx, XXXXXXXXX, xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx. Les requêtes sur les portails v2 et v3 pour les données de la période d’archivage produisent les mêmes résultats. Les requêtes de données v2 et v3 pour les données NRT et les périodes d’informations d’identification de NRT sont différentes.

### <a name="piieuii-data"></a>Données personnelles/EUII

Les données d’informations d’identification personnelle ou EUII proviennent uniquement du pipeline v3. En raison de la conformité, les données d’PII/EUII sont conservées pendant 30 jours. Les données NRT qui se trouvent dans la marque de 30 jours, les champs PII/EUII sont effacés, ce qui crée des données NRT gratuites. Les champs PII/EUII sont les suivants :

- Adresse IP complète
- Adresse de contrôle d’accès au média (MAC)
- Identificateur de l’ensemble de services standard (BSSID)
- URI SIP (Session Initiation Protocol) (Skype entreprise uniquement)
- Nom d’utilisateur principal (UPN)
- Nom du point de terminaison de l’ordinateur
- Commentaires textuels de l’utilisateur
- ID d’objet (ID d’objet Active Directory de l’utilisateur du point de terminaison);

### <a name="date-controls"></a>Contrôles de date

BORD v3 ajoute les nouveaux types de tendance de roulement suivants :

- 5 jours
- 7 jours
- 30 jours
- 60-jour
- 90-jour

Le paramètre de date URL peut désormais accepter un champ Day. Rapports d’une journée à l’aide de dates spécifiées au format AAAA-MM-JJ comme dernier jour de la tendance.  Le paramètre de date d’URL « 00 » indique « aujourd’hui ».

|URL| Date de fin de la tendance du jour de roulement|
|:---|:---|
|<span>https://<cqdv3>/SPD/#/Dashboard/<reportid>/2019-02/</span>   |Jour actuel en février 2019|
|<span>https://<cqdv3>/SPD/#/Dashboard/<reportid>/2019-02-15/</span>|15 février 2019|
|<span>https://<cqdv3>/SPD/#/Dashboard/<reportid>/00/</span>        |Jour actuel|
|||

Par défaut, le jour du mois actuel est utilisé comme dernier jour de la tendance du jour de roulement.

### <a name="drill-thru-functionality"></a>Fonctionnalité de perçage via

BORD v3 prend en charge l’utilisation de champs d’exploration ou d’exploration dans les rapports SPD. Si ces champs de dimension sont sélectionnés, le rapport ouvre automatiquement un onglet de rapport différent et filtre sur la valeur sélectionnée. Les champs dotés d’une extraction de filtre peuvent être distingués par une icône de curseur différente (le pointeur) lorsque vous pointez dessus.

Lorsqu’un champ Drill through est sélectionné, le tableau de bord accède automatiquement au nouvel onglet spécifié et applique un filtre avec la valeur sélectionnée. S’il s’agit de ses propres champs de perçage et qu’une option est sélectionnée, les filtres d’extraction de filtres et de nouvelles propagés. Cela vous permet de générer un rapport pour affiner progressivement le jeu de données résultant.

Par exemple, dans un rapport d’analyse de qualité d’appel, un utilisateur peut cliquer sur la date à laquelle il souhaite « extraire », ce qui amène à l’onglet emplacement.

![Capture d’écran : affichage de l’État analyse approfondie](media/CQD-drill-thru-report.png)

Vous pouvez ajouter plusieurs dates à partir de l’onglet emplacement, par exemple, ajouter 2019-09-22 à la date : 2019-09-24 : 

![Capture d’écran : ajouter une date au rapport d’extraction](media/CQD-add-date.png)

> [!NOTE]
> Ne passez pas directement au dernier onglet. Sans filtres sélectionnés à partir d’un affichage d’exploration antérieur les résultats seraient trop volumineux pour être affichés dans un tableau.

## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Activer les rapports de synthèse sur le tableau de bord de qualité d’appel Microsoft (bord)

Pour pouvoir commencer à utiliser bord, vous devez l’activer pour votre application Microsoft 365 ou Office 365 en procédant comme suit :

![Icône montrant le logo](media/teams-logo-30x30.png) de Microsoft teams **à l’aide du centre d’administration Microsoft teams**

1. Pour ouvrir le centre d’administration, connectez-vous à votre compte Microsoft 365 ou Office 365 à l’aide du compte d’administrateur du service Microsoft Teams, puis sélectionnez la vignette **administrateur** .
2. Dans le volet gauche, sous **centres d’administration**, sélectionnez **Microsoft teams** pour ouvrir le centre d’administration Microsoft Teams.
3. Dans le centre d’administration de Microsoft Teams, sélectionnez **tableau de bord de qualité des appels** dans le volet gauche.
4. Dans la page qui s' \(ouvre<span><span/>\), cliquez sur **se connecter** , puis entrez les informations de votre compte d’administrateur général ou d’administrateur du service Microsoft Teams.

    ![Capture d’écran : affiche la demande d’informations d’identification](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Après vous être connecté, une fois activé, le bord commence la collecte et le traitement des données.  
> [!NOTE]
> Le traitement d’une quantité suffisante de données pour afficher des résultats significatifs dans les rapports risque de nécessiter une ou plusieurs heures.

![Icône du logo](media/sfb-logo-30x30.png) Skype entreprise **avec le portail hérité Skype entreprise**

1. Connectez-vous à votre compte Microsoft 365 ou Office 365 à l’aide d’un compte d’administrateur, puis sélectionnez la vignette **administrateur** pour ouvrir le centre d’administration.
2. Dans le volet gauche, sous **centres d’administration**, sélectionnez **Microsoft teams** pour ouvrir le centre d’administration Microsoft Teams.
3. Dans le centre d’administration de Microsoft Teams, sélectionnez **portail hérité** dans le volet gauche, sélectionnez **Outils**, puis cliquez sur **tableau de bord de qualité des appels de Skype entreprise Online**.

     ![Capture d’écran : sélectionner le tableau de bord de qualité des appels](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. Dans la page qui s’affiche, connectez-vous à l’aide de votre compte d’administrateur général, puis indiquez les informations d’identification du compte lorsque vous y êtes invité.

Après vous être connecté, une fois activé, le tableau de bord de qualité des appels commence à collecter et à traiter les données.

## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Fonctionnalités du tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online

<a name="BKMKFeaturesOfTheCQD"> </a>


BORD-XX XXXXXXX XXXXXXX XXXXXXX XXXXXXX xxxxxxxxx XXXXXXXXX. Les différences entre les éditions sont résumées ici :
  
|Fonctionnalité|Rapports de synthèse|Rapports détaillés|
|:--- |:--- |:--- |
|Métrique du partage d’application | Non | Oui |
|Support des informations sur le bâtiment du client | Oui | Oui  |
|Support technique des informations de point de terminaison client | Uniquement dans <span>CQD.Teams.Microsoft.com<span/> | Uniquement dans <span>CQD.Teams.Microsoft.com<span/> |
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

### <a name="out-of-the-box-reports"></a>Rapports prêts à l’emploi

Toutes les éditions de bord fournissent une nouvelle expertise qui vous permet d’appeler des indicateurs de qualité sans avoir à créer de nouveaux rapports. Une fois que les données sont traitées au serveur principal, vous pouvez afficher les données de qualité d’appel dans les rapports.

Nouveauté de janvier 2020 : [Télécharger les modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et enregistrer vos données bord.
  
### <a name="overview-reports"></a>Présentation des rapports

Toutes les éditions du bord fournissent un point d’entrée de haut niveau aux informations générales de qualité des appels, mais la façon dont les informations sont présentées dans les rapports de synthèse est différente des rapports détaillés.  
  
Les rapports de synthèse offrent un affichage simplifié des rapports de pages à onglets pour vous permettre de parcourir et de comprendre rapidement l’État et les tendances de la qualité globale des appels.

Les quatre onglets sont les suivants :
  
- **Qualité d’appel globale** : fournit des informations sur tous les flux, qui est une agrégation qui affiche des tendances mensuelles et journalières pour :
  - Serveur-flux client
  - Flux client-client
  - Séparer les flux client-client et client-client
- **Serveur-client** : fournit des détails sur les flux entre les points de terminaison serveur et client.
- **Client-client** : fournit des détails sur les flux reliant deux points de terminaison client.
- **SLA de qualité vocale** : fournit des informations sur les appels inclus dans le contrat de service de qualité vocale de Skype entreprise online.

> [!NOTE]
> BORD version 3 fonctionne avec Microsoft Teams, Skype entreprise Online et Skype entreprise Server. Pour utiliser bord avec Skype entreprise Server 2019, vous devez [configurer un connecteur de données d’appel](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector). Pour commencer, voir [connecteur des données d’appel](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) .

- Qualité des appels par région :

  - date par région
  - agrégées jusqu’à la plage horaire
  - emplacements spécifiques
  - sous-réseau spécifique
  - utilisateurs concernés ou utilisateurs concernés

- Fiabilité/échec de l’appel par région :
  - date par région
  - agrégées jusqu’à la plage horaire
  - emplacements spécifiques
  - sous-réseau spécifique
  - utilisateurs concernés ou utilisateurs concernés

- Évaluer mon appel (RMC) par région : d’un mois à une autre dans la zone agrégés vers des emplacements spécifiques pour les utilisateurs qui fournissent des évaluations plus basses. BORD v3 inclut également le retour Verbatim.
- Support technique disponible pour un utilisateur particulier sur les appels ou réunions P2P, ou pour tous les participants et les détails de l’appel. Permet d’identifier les problèmes système potentiels en fonction de l’emplacement du réseau, des appareils ou du microprogramme.  
- Versions du client : Affichez la session et les comptes des utilisateurs pour chaque version du client, ou explorez les noms d’utilisateurs pour chaque version du client. Les filtres prédéfinis pour le type produit et client permettent de focaliser les versions sur des clients spécifiques.
- Points de terminaison : affiche les points de terminaison d’ordinateur mappés au PC/Mac. Affiche la qualité agrégée par création/modèle. Le mappage des données est semblable à la génération de données.

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

#### <a name="inside-test"></a>Test interne

Lors du traitement, le serveur principal bord classifie un flux comme *à l’intérieur* ou à l' *extérieur* en utilisant des informations de bâtiment, le cas échéant. Les points de terminaison de chaque flux sont associés à une adresse de sous-réseau. Si le sous-réseau figure dans la liste des sous-réseaux marqués dans l’entreprise dans les informations de bâtiment téléchargées, il est considéré comme *à l’intérieur*. Si les informations de bâtiment n’ont pas encore été chargées, le test interne les classifie toujours en tant qu' *extérieur*.  

> [!NOTE]
> Le test interne d’un scénario serveur-client considère uniquement le point de terminaison client. Étant donné que les serveurs sont toujours extérieurs du point de vue d’un utilisateur, ce n’est pas pris en compte dans le test.
  
#### <a name="wired-vs-wifi"></a>Connexion filaire et WiFi

Étant donné que les noms indiquent, les critères de classification sont basés sur le type de connexions client. Là encore, le serveur est toujours câblé et n’est pas inclus dans le calcul.
  
> [!NOTE]
> À partir d’un flux, si l’un des deux points de terminaison est connecté à un réseau WiFi, il est considéré comme WiFi dans bord.
  
## <a name="selecting-product-data-to-see-in-reports"></a>Sélection des données de produits à afficher dans les rapports

<a name="BKMKProductFilter"></a>

Dans la liste déroulante du filtre produit, vous pouvez utiliser la liste déroulante du **filtre produit** pour afficher toutes les données de produit, uniquement les données de Microsoft Teams, ou uniquement les données de Skype entreprise online.
  
![Capture d’écran : affiche les options de contrôle du filtre de produit](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Dans les rapports détaillés, vous pouvez utiliser la dimension **is teams** pour filtrer les données sur les données de Microsoft teams ou de Skype entreprise online.
  
## <a name="upload-tenant-data-information"></a>Télécharger les informations sur les données de client

<a name="BKMKTenantDataInformationUpload"></a>

Le tableau de bord des rapports de synthèse de bord inclut une page de **téléchargement de données de client** accessible en sélectionnant télécharger les **données client** dans le menu paramètres dans le coin supérieur droit. Cette page permet aux administrateurs de télécharger leurs propres informations, par exemple :

- Carte d’adresse IP et informations géographiques
- Carte de chaque point d’accès sans fil et son adresse MAC
- Carte de point de terminaison à marque/modèle/type de point de terminaison, etc.
  
> [!NOTE]
> Les étiquettes de rapport que vous chargez dans bord seront gérées en tant que *données de support* dans le cadre de votre contrat pour Office 365, y compris les informations qui seraient considérées comme des *données client* ou des *données personnelles*. N’incluez pas de données que vous ne souhaitez pas envoyer à Microsoft en tant que *données de support technique*, ces informations seront visibles par les ingénieurs Microsoft à des fins de support.

![Capture d’écran : affiche les données client du tableau de bord de qualité des appels](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Dans la page **téléchargement de données du client** , utilisez le menu déroulant pour choisir le type de fichier de données à télécharger. Le type de données de fichier indique le contenu du fichier (par exemple, « bâtiment » désigne le mappage de l’adresse IP et de la construction ainsi que d’autres informations géographiques, « point de terminaison » fait référence au mappage du nom du point de terminaison aux informations sur la création/type de point de terminaison. Pour l’instant, bord prend en charge les types de données « bâtiment » et « point de terminaison » pour cqd.teams.microsoft.com (en phase d’aperçu et non officiellement disponible), cqd.lync.com prend uniquement en charge le type de données « bâtiment ».



2. Après avoir sélectionné le type de données du fichier, cliquez sur **Parcourir** pour choisir un fichier de données.

   - Un fichier de données doit être un fichier. TSV (valeurs séparées par des tabulations) ou un fichier. csv (valeurs séparées par des virgules). Dans un fichier. csv, les champs qui contiennent une virgule doivent être entourés de guillemets ou être supprimés. Par exemple, si le nom de votre bâtiment est NY, NY, entrez « NY, NY » dans le fichier. csv.
   - Le fichier de données ne doit pas dépasser 50 Mo.
   - Les fichiers téléchargés sur cqd.teams.microsoft.com ont une limite de lignes développée de 1 million pour garantir une performance rapide des requêtes. Cette limite s’applique également à bord v2 sur<span></span>bord.<span></span>Lync. com.
   - Pour chaque fichier de données, chaque colonne du fichier doit correspondre à un type de données prédéfini, abordé plus loin dans cette rubrique.
3. Ensuite, spécifiez une **Date de début** et, éventuellement, **Spécifiez une date de fin**.
4. Enfin, sélectionnez **Télécharger** pour télécharger le fichier sur le serveur bord.
    Avant de télécharger le fichier, il est d’abord validé. Une fois validée, elle est stockée dans un blob Azure. Si la validation échoue ou que le fichier ne peut pas être stocké dans un objet BLOB Azure, un message d’erreur demande une correction du fichier. L’image suivante montre un exemple d’erreur avec un nombre incorrect de colonnes dans le fichier de données.

     ![Capture d’écran : affiche une erreur de validation de téléchargement](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Si aucune erreur ne se produit lors de la validation, le téléchargement du fichier réussit. Le fichier de données chargé est alors affiché dans la table **Mes téléchargements** . Le bas de cette page affiche également une liste complète de tous les fichiers téléchargés pour le client actuel.
    Chaque enregistrement affiche un fichier de données client téléchargé, avec le type de fichier, l’heure de la dernière mise à jour, la période, la description, une icône de suppression et une icône de téléchargement. Pour supprimer un fichier, sélectionnez l’icône de corbeille dans le tableau. Pour télécharger un fichier, sélectionnez l’icône de téléchargement dans la colonne **Télécharger** du tableau.

     ![Capture d’écran : affiche la table Mes téléchargements](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. Si vous optez pour l’utilisation de plusieurs fichiers de données de construction ou de plusieurs fichiers de données de point de terminaison, certains rapports génèrent une plus plus lente.

### <a name="tenant-data-file-format-and-structure"></a>Format et structure du fichier de données client

<a name="BKMKTenantDataFile"> </a>

### <a name="building-data-file"></a>Création d’un fichier de données

BORD utilise un fichier de données de bâtiment qui vous permet de fournir des informations d’appel utiles. La colonne de sous-réseau repose sur le développement de la colonne Network + plage du réseau, puis sur la colonne de sous-réseau pour le premier sous-réseau de l’enregistrement d’appel ou sur le second sous-réseau. Pour que le format du fichier de données réussisse le contrôle de validation avant le téléchargement, il doit respecter les critères suivants.

Vous pouvez télécharger un exemple de modèle [ici](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)
  
- Il doit s’agir d’un fichier. TSV (les colonnes sont séparées par une tabulation) ou d’un fichier. csv (les colonnes sont séparées par une virgule).
- Le fichier de données n’inclut pas de ligne d’en-tête de tableau. La première ligne du fichier de données est censée être de véritables données, pas d’étiquettes d’en-tête comme « réseau ».
- Les types de données dans le fichier ne peuvent être que des chaînes, des entiers ou des valeurs booléennes. Pour le type de données Integer, la valeur doit être une valeur numérique. Les valeurs booléennes doivent être égales à 0 ou 1.
- Si une colonne utilise le type de données chaîne, un champ de données peut être vide, mais doit toujours être séparé par une tabulation ou une virgule. Un champ de données vide attribue simplement une valeur de chaîne vide.
- Il doit y avoir 14 colonnes pour chaque ligne (ou 15 si vous souhaitez ajouter la colonne facultative), chaque colonne doit avoir le type de données approprié, et les colonnes doivent être dans l’ordre indiqué dans le tableau suivant :

||||||||||||||||
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:---  |:--- |:---|
|**Nom de champ de colonne**|NetworkIP  |Nom réseau              |NetworkRange|BuildingName  |Type de propriété| Type de bâtiment  |BuildingOfficeType|Ville   |ZipCode|Pays|État |Région|InsideCorp&dagger;|ExpressRoute&Dagger;|VPN (facultatif)|
|**Type de données**        | String    | String                  |Numéro      | String       | String      | String        |String            |String |String |String |String|String|Boolean   |Boolean     |Boolean|
|**Exemple de valeur**    |192.168.1.0|États-Unis/Seattle/SEATTLE-SEA-1| 26/08/03         | SEATTLE-SEA-1| Chez     | Arrêt|Ingénieur       |Seattle|98001  |Nous     |WA    |MSUS  | 1        |0,4           | 0,4|
|||||||||||||||||

&dagger;Ce paramètre peut être utilisé pour indiquer si le sous-réseau se trouve ou non dans le réseau d’entreprise. Vous pouvez personnaliser l’utilisation pour d’autres raisons si vous le souhaitez.

&Dagger;Ce paramètre peut être utilisé pour indiquer si le réseau utilise ou non Azure ExpressRoute. Vous pouvez personnaliser l’utilisation pour d’autres raisons si vous le souhaitez.  

**Ligne d’exemple :**

`192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> La plage réseau peut être utilisée pour représenter un super-réseau (combinaison de plusieurs sous-réseaux avec un seul préfixe de routage). Les nouveaux chargements de construction seront examinés pour toutes les plages qui se chevauchent. Si vous avez déjà téléchargé un fichier de construction, vous devez télécharger le fichier actif et le télécharger à nouveau pour identifier les chevauchements et résoudre le problème avant de le télécharger à nouveau. Tout chevauchement dans les fichiers précédemment téléchargés risque de provoquer des mappages incorrects de sous-réseaux sur les bâtiments dans les rapports. Certaines implémentations de réseau privé virtuel n’indiquent pas exactement les informations de sous-réseau. Lorsque vous ajoutez un sous-réseau VPN au fichier de construction au lieu d’une entrée pour le sous-réseau, nous vous conseillons d’ajouter des entrées distinctes pour chaque adresse du sous-réseau VPN en tant que réseau 32 différent. Chaque ligne peut avoir les mêmes métadonnées de bâtiment. Par exemple, au lieu d’une ligne pour 172.16.18.0/24, vous devez disposer de lignes 256, avec une ligne pour chaque adresse entre 172.16.18.0/32 et 172.16.18.255/32, inclusive.
>
> La colonne RPV est facultative et utilise par défaut la valeur 0.  Si la valeur de la colonne VPN est définie sur 1, le sous-réseau représenté par cette ligne sera entièrement étendu pour correspondre à toutes les adresses IP au sein du sous-réseau.  N’hésitez pas à utiliser cette fonction et uniquement pour les sous-réseaux VPN dans la mesure où le développement complet de ces sous-réseaux aura un impact négatif sur les requêtes de création de données.

### <a name="endpoint-data-file"></a>Fichier de données du point de terminaison

BORD utilise un fichier de données de point de terminaison. Les valeurs de colonne sont utilisées dans la première colonne nom du point de terminaison du client ou deuxième nom du point de terminaison du client pour afficher les informations de point de terminaison, de modèle ou de type. Pour que le format du fichier de données réussisse le contrôle de validation avant le téléchargement, il doit respecter les critères suivants.

- Il doit s’agir d’un fichier. TSV (les colonnes sont séparées par une tabulation) ou d’un fichier. csv (les colonnes sont séparées par une virgule).
- Le contenu du fichier de données ne comporte pas d’en-têtes de tableau. La première ligne du fichier de données est censée être une véritable donnée, et non une étiquette d’en-tête telle que « EndpointName ».
- Les sept colonnes utilisent uniquement le type de données chaîne. La longueur maximale autorisée est de 64 caractères.
- Un champ de données peut être vide, mais doit toujours être séparé par une tabulation ou une virgule. Un champ de données vide attribue simplement une valeur de chaîne vide.
- EndpointName doit être unique, sinon le téléchargement échoue. S’il existe une ou deux lignes en double utilisant la même EndpointName, le conflit provoquera une jointure incorrecte.
- EndpointLabel1, EndpointLabel2 et EndpointLabel3 sont des étiquettes personnalisables. Il peut s’agir de chaînes vides ou de valeurs telles que « service informatique de l’ordinateur portable 2018 » ou « indicateur de ressources 5678 ».
- Il doit y avoir sept colonnes pour chaque ligne et les colonnes doivent être dans l’ordre suivant :

  **Ordre des champs :**

EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Ligne d’exemple :**

' 1409W3534, fabricant 123, Fabrikam Model 123, ordinateur portable, ordinateur portable 2018, balise de ressources 5678, achat 2018

## <a name="migrate-reports-from-previous-version-of-cqd"></a>Migrer des rapports à partir d’une version précédente de bord

Si vous avez créé des rapports ou téléchargé des fichiers de données client (mappage) sur bord pour Skype entreprisehttps://cqd.lync.com) (et que vous voulez les migrer vers bordhttps://cqd.teams.microsoft.com)pour Teams (, procédez comme suit :

1.    Accédez à [https://cqd.lync.com/cqd/](https://cqd.lync.com/cqd/) l’ensemble de rapports que vous souhaitez exporter, puis recherchez-le. 
2.    Placez le pointeur de la souris sur le rapport et, sur le « ... » , sélectionnez **exporter l’arborescence du rapport**. Enregistrez le fichier d’exportation.
3.    Accédez à [https://cqd.teams.microsoft.com/cqd/](https://cqd.teams.microsoft.com/cqd/) l’emplacement où vous souhaitez importer les rapports, puis recherchez-le.
4.    Dans les liens de gauche, cliquez sur **Importer** , puis sélectionnez le fichier exporté. 
5.    Après l’importation des rapports, le message suivant s’affiche : «l’importation du rapport a réussi. Le nouveau rapport a été ajouté à la fin de l’ensemble de rapports.» 


## <a name="create-custom-detailed-reports"></a>Créer des rapports détaillés personnalisés

Si vous souhaitez créer un rapport spécifique qui porte sur une dimension des données de telle sorte que les rapports détaillés fournis ne le sont pas, créez un rapport personnalisé.

Dans la liste déroulante des rapports qui se trouvent en haut de l’écran, \(dans **l’écran** \) de connexion, sélectionnez **rapports détaillés** **, puis cliquez** sur modifier dans le menu action d’un rapport pour afficher l’éditeur de requête. Chaque rapport est complété par une requête effectuée dans le cube. Il s’agit de la visualisation des données renvoyées par la requête. L’éditeur de requête vous permet de modifier ces requêtes et les options d’affichage du rapport. Lorsque vous ouvrez l’éditeur de requête pour un nouveau rapport, vous voyez une section semblable à celle-ci :

![Modifier de nouveaux rapports](media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Les dimensions, les mesures et les filtres sont sélectionnés dans le volet gauche. Cliquez sur le bouton « plus » en regard d’un titre pour ouvrir la boîte de dialogue dans laquelle vous pouvez ajouter une dimension, une mesure ou un filtre et cocher la case correspondante. Si vous modifiez un rapport existant, vous pouvez décocher les valeurs existantes pour les supprimer. Pour plus d’informations, consultez [dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md).
2. Les options de personnalisation de graphique figurent en haut.
3. Un aperçu du rapport est disponible dans l’éditeur de requête.
4. Le nom et la description du rapport détaillé peuvent être créés à l’aide de la zone d’édition en bas.

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Pourquoi bord marque-t-on comme bon dans le cas d’un ou plusieurs participants à la réunion ?

Découvrez les règles utilisées par bord pour la [classification des flux](stream-classification-in-call-quality-dashboard.md).
 
Dans le cas des flux audio, l’un des cinq classifieurs, qui est calculé pour la moyenne en fonction de la longueur de l’appel, peut être un paramètre « Good ». Cela ne signifie pas que les utilisateurs n’ont pas eu d’action ayant contribué à une chute ou un problème audio. 

Pour savoir s’il s’agit d’un problème de réseau, observez le delta entre les valeurs moyennes de la session et les valeurs maximales. Les valeurs maximales sont le maximum détecté et signalé lors de la session.
 
Voici un exemple de procédure à suivre pour résoudre ce problème. Imaginons que vous suiviez une trace réseau lors d’un appel et les 20 premières minutes qu’il n’y a pas de paquets perdus, mais que vous avez un espace de 1,5 secondes de paquets et que vous avez l’habitude de le reste de l’appel. La moyenne est <de 10% (0,1) de perte de paquets même dans une analyse RTP de suivi Wireshark. Quelle a été la perte de paquets maximale ? 1,5 secondes sur une période de 5 secondes seraient de 30% (0,3). A-t-il observé au cours de la période de cinq secondes (peut-être, ou peut-être fractionné au cours de la période d’échantillonnage) ?
 
Si les métriques du réseau s’importent correctement dans les valeurs moyenne et maximale, accédez à d’autres données de télémétrie : 
- Vérifiez le ratio d’événement d’UC insuffisant pour vérifier si les ressources de l’UC détectées disponibles étaient insuffisantes et ont une mauvaise qualité. 
- Le périphérique audio est-il en mode half duplex pour éviter les commentaires en raison de micros à proximité des haut-parleurs ? 
- Vérifiez le coefficient d’événement AEC en mode half duplex. Le périphérique est-il en faute d’introduction ou de problème de micro, en raison d’une chute USB ou d’une station d’accueil USB, s’il est connecté à un concentrateur ou une station d’ancrage :  
- Vérifiez les ratios d’événement liés aux problèmes liés aux périphériques et aux problèmes de micro. Est-ce que l’appareil proprement dit fonctionne correctement ?  
- Vérifiez que l’appareil de capture et de rendu ne fonctionne pas.


Pour en savoir plus sur les dimensions et les mesures disponibles dans la télémétrie bord, voir [dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md).

Pour bruit de fond, activez la case à cocher Désactiver le coefficient d’événement pour voir la durée pendant laquelle les participants ont été désactivés.
 
Créez des rapports détaillés dans bord et filtrez sur ID de réunion pour consulter tous les utilisateurs et les flux d’une réunion et ajouter les champs qui vous intéressent. Il est possible qu’un utilisateur signalant ce problème ne soit pas celui qui rencontre le problème. Ils signalent simplement l’utilisateur.
 
La télémétrie ne sera pas nécessairement à l’origine du problème, mais elle peut vous aider à mieux comprendre la façon dont vous pouvez trouver et informer vos décisions. S’agit-il des mises à jour du réseau, du périphérique, du pilote ou du microprogramme, de l’utilisation ou de l’utilisateur ?

### <a name="why-do-i-see-upto-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Pourquoi est-ce que je vois une différence de 0,2% dans les valeurs d’appel et de nombre d’utilisateurs sur les mesures et comment obtenir des volumes plus précis ? 
Pour calculer le nombre d’appels et les mesures de nombre d’utilisateurs, une opération NB.si distincte est effectuée par rapport aux identificateurs d’appel ou d’utilisateur du jeu de données. Dans de grands ensembles de données, il y a une erreur de plus de 0,2% d’inherient avec le opeartion NB.si distinct. Pour obtenir le volume le plus précis, vous devez vous fier aux mesures de nombre de flux, car elles ne dépendent pas de cette opération NB.si distincte. Le filtrage permettant de réduire le volume de données risque de réduire l’erreur, mais il est possible que vous n’elimnate pas cette source d’erreur dans les nombre d’appels et d’utilisateurs distincts. Reportez-vous aux [sections Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md) pour lesquels des mesures sont affectées.

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a>Pourquoi les données du rapport bord v2 sont-elles différentes de celles du rapport bord v3 ? 

Si vous voyez des différences de données entre bord v2 et v3, assurez-vous que la comparaison ou la validation des données est réalisée sur une « pommes-to-pommes » et un niveau étroit, et non sur un niveau agrégé. Par exemple, si vous filtrez les deux rapports pour les données du client de bureau MSIT de la construction de 30 ', le pourcentage de qualité médiocre doit être identique entre la version v2 et la version v3.

Le nombre total de BORDs v2 et bord v3 est différent dans la mesure où bord v3 a de nouveaux scénarios non présents dans bord v2. Le total cumulé ou le nombre d’agrégats cumulés sans aucun filtre ne devrait être différent.  

Si le scénario d’utilisation inclut les appels Skype entreprise Server 2019, les données de bord v3 incluent les appels Skype bot (standard automatique, CVI, l’interface de bureau virtuel), les événements en direct et les appels RTC. BORD v2 n’utilise pas ces données. (Bord V3 nécessite Skype entreprise Server 2019 avec le Cloud Data Connector configuré.)

Par exemple, si vous voyez des flux audio 200 000 avec 5000 échecs dans un rapport de synthèse bord v2, il n’était pas rare de voir les flux audio 300 000 avec les échecs de la fonction 5500 (la différence peut être due à Skype entreprise Server 2019 appels, appels CVI, appels RTC, etc.) dans un rapport de synthèse bord v3.

Pour éliminer toute ambiguïté de différences inattendues, observez plus d’une répartition des données globales. Filtrez les données à l’aide d’un ou de plusieurs des paramètres suivants :

- User Agent Category Pair
- Premier produit
- Deuxième produit

### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a>Autres différences attendues entre bord v2 et bord v3

Il existe de nombreuses améliorations de la qualité et de la fiabilité dans Teams, mais pas dans Skype entreprise Online :

- Reconnexion automatique
- Itinérance rapide
- Gestion des BW améliorée

Lorsque vous comparez des données pour ces deux services :

- Choisissez un scénario avec le focus étroit, tel que les connexions câblées d’entreprise, les ordinateurs de bureau Windows, ou une région ou un bâtiment unique.
- Vérifiez les plages d’adresses IP de RM, TR ou MP. Les plages d’équipes sont plus récentes que Skype entreprise Online et peuvent entraîner des problèmes de connectivité liés à des pare-feu.
- Ne pas comparer les numéros de synthèse ou de niveau supérieur. Ces comparaisons vous aideront à comparer le volume des appels de Skype entreprise Online sur une connexion câblée d’entreprise à un petit volume d’appels d’équipe sur un réseau LTE ou privé.
- Soyez attentif aux différences de décalage d’emplacement et de population : de nombreuses comparaisons sont trop différentes pour être utiles :
  - NOAM : APAC
  - NY : autorités australiennes
  - Filaire : wifi
  - Réseau d’entreprise : réseau domestique
  
### <a name="why-cant-i-see-euii-in-cqd"></a>Pourquoi ne puis-je pas voir EUII dans bord ?

Ces rôles d’administrateur peuvent accéder à bord, mais ils ne peuvent pas afficher EUII (informations d’identification de l’utilisateur final) :
- Lecteur de rapports Microsoft 365
- Spécialiste du support des communications teams

Pour en savoir plus sur les rôles qui peuvent accéder à bord, y compris les [rôles d’attribution de EUII-lecture des rôles pour accéder à bord](#assign-roles-for-accessing-cqd).

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Pourquoi des informations Skype entreprise s’afficheront dans bord lorsque j’ai filtré uniquement pour les équipes ?

Lorsque vous filtrez les équipes uniquement dans les rapports bord (isTeams = 1), vous filtrez tous les appels dans lesquels le *premier point de terminaison* est Teams. Si le *deuxième point de terminaison* est Skype entreprise, ces informations apparaissent dans votre rapport bord.

## <a name="related-topics"></a>Rubriques connexes

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md)

[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Tableau de bord Analyse des appels et Qualité des appels](difference-between-call-analytics-and-call-quality-dashboard.md)
 
