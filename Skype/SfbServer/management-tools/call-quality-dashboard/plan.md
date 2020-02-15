---
title: Planifier le tableau de bord de qualité des appels pour Skype entreprise Server
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
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Résumé : Découvrez les éléments à prendre en compte lorsque vous planifiez le tableau de bord de qualité des appels.'
ms.openlocfilehash: 25342998332a596abce9ecd02e63e153be6e6d94
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029415"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Planifier le tableau de bord de qualité des appels pour Skype entreprise Server 
 
**Résumé :** Découvrez les éléments à prendre en compte lorsque vous planifiez le tableau de bord de qualité des appels.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Vue d’ensemble du tableau de bord de qualité des appels de Skype entreprise Server

Le tableau de bord de la qualité des appels de Skype entreprise Server (CQD) est une couche de création de rapports située au-dessus de la base de données de qualité de l’expérience dans le serveur de surveillance dans Skype entreprise Server. CQD utilise Microsoft SQL Server Analysis Services pour fournir des informations sur l’utilisation agrégée et la qualité des appels, ainsi que pour le filtrage et le glissement sur le jeu de données. Les fonctionnalités CQD sont les suivantes :
  
- **Stockage d’archivage des données QoE via le composant d’archive QoE de CQD.** Le composant d’archive QoE peut stocker des données QoE pendant une durée plus longue que le serveur de surveillance. Cela permet la création de tendances et la création de rapports pour un maximum de sept mois de données à la fois, avec la possibilité de faire glisser la fenêtre de création de rapports aussi loin qu’il y a des données.
- **Création de rapports et analyse à l’aide de la puissance et de la vitesse de Microsoft SQL Server Analysis Services.** CQD utilise Microsoft SQL Analysis Services pour fournir des fonctionnalités de résumé, de filtrage et de pivotement rapides pour alimenter le tableau de bord via un cube d’analyse. La création de rapports sur la vitesse d’exécution et la possibilité d’explorer les données peut réduire considérablement les temps d’analyse.
- **Nouveau schéma de données optimisé pour la création de rapports sur la qualité des appels.** Le cube dispose d’un schéma conçu pour la création de rapports et les enquêtes de qualité vocale. Les utilisateurs de portail peuvent se concentrer sur les tâches de création de rapports au lieu de savoir comment le schéma de base de données de mesures QoE mappe aux vues dont ils ont besoin. La combinaison de l’archive QoE et du cube offre une abstraction qui réduit la complexité de la création de rapports et de l’analyse via CQD. Le schéma de base de données d’archive QoE contient également des tables pouvant être remplies avec des données spécifiques au déploiement afin d’améliorer la valeur globale des données.
- **Le concepteur de rapports intégré et la modification des rapports sur place.** Le composant portail est doté de plusieurs rapports prédéfinis modélisés après la méthodologie de qualité des appels. Les utilisateurs du portail peuvent modifier les rapports et en créer de nouveaux via la fonctionnalité de modification du portail.
- **Accès à l’API Web pour la structure du rapport et les données du cube d’analyse.** L’infrastructure de création de rapports de tableau de bord n’est pas la seule façon d’afficher les données du cube. CQD fournit plusieurs exemples d’utilisation du code HTML et de JavaScript pour récupérer des données des API Web CQD et afficher les données dans un format personnalisé. La combinaison de l’éditeur de rapport et des API Web CQD permet un prototypage rapide des rapports et de la mise en page des rapports personnalisés.

> [!NOTE]
> Un administrateur peut désormais gérer Skype entreprise Server 2019 à l’aide de [CQD version 3](https://cqd.teams.microsoft.com) (se connecter avec les informations d’identification d’administrateur). Cela nécessite une implémentation hybride et l’utilisation du connecteur de données d’appel (CDC). Pour plus d’informations sur l’activation de CDC, voir [plan Call Data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) . Pour obtenir une documentation CQD version 3, voir [activer et utiliser le tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) pour plus d’informations sur CQD version 3.

## <a name="cqd-design-goals"></a>Objectifs de conception CQD

CQD permet aux professionnels de l’informatique d’utiliser des données agrégées pour identifier les domaines ciblés dans leur environnement confrontés à des problèmes de qualité des médias. Elle permet aux professionnels de l’informatique de comparer les statistiques de différents groupes d’utilisateurs et d’identifier des tendances et des modèles. Il n’est pas axé sur la résolution des problèmes liés aux appels individuels, mais sur l’identification des problèmes et des solutions qui s’appliqueront à de nombreux utilisateurs dans un environnement donné. 
  
## <a name="call-quality-dashboard-components"></a>Composants de tableau de bord de qualité des appels

Le tableau de bord de qualité des appels se compose de plusieurs bases de données, de travaux de l’agent Microsoft SQL, de processus et d’applications Web. Les travaux de l’agent Microsoft SQL copient régulièrement les données de la base de données de mesures QoE dans la base de données d’archivage QoE et traite le cube avec les données de la base de données d’archivage QoE. La base de données de référentiel stocke les définitions de rapport qui alimentent le portail. Le portail fournit l’accès du navigateur aux données du cube. 
  
Les composants CQD, y compris les bases de données d’archive, de cube et de référentiel QoE, peuvent être installés sur le serveur de surveillance, installés sur son propre serveur ou installés sur plusieurs serveurs. La méthode d’installation particulière dépend des exigences de performances de CQD et de l’impact sur les autres processus sur les mêmes serveurs. Pour plus d’informations, reportez-vous à la section « composants et topologies de CQD » plus loin dans cet article.
  
### <a name="architectural-overview"></a>Vue d’ensemble de l’architecture

Pour résumer, CQD nécessite les éléments suivants :
  
- Deux bases de données : une base de données d’archivage et une base de données de référentiel.
    
- Un cube SSAS qui regroupe des données agrégées 
    
- Hôtes IIS CQD portail Web
    
![Composants CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
La même architecture CQD prend en charge Lync Server 2013 et Skype entreprise. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD et Skype entreprise vs. Lync 2013

 Dans un environnement Skype entreprise uniquement, les fonctionnalités suivantes sont disponibles :
  
- Signalement de l’intensité de signal Wi-Fi
    
- Création de rapports Wi-Fi sur les pilotes des puces
    
- Évaluer mes données d’appel 
    
## <a name="information-available-through-cqd"></a>Informations disponibles via CQD

CQD peut afficher le nombre de flux de travail de partage d’application, vidéo et audio Skype entreprise Server, ainsi que le nombre d’appels corrects ou incorrects, ainsi que les ratios d’appels incorrects. Les affichages peuvent être découpés en tranches et filtrés selon de nombreuses dimensions différentes. CQD extrait les données de la base de données de mesures QoE dans le serveur de surveillance. Les données sont ensuite fusionnées avec les données fournies par le client, telles que le mappage de sous-réseau à créer pour créer des rapports tels que « qualité des appels par bâtiment » possible. 
  
CQD résume également un grand nombre des particularités de données QoE internes telles que « Caller » et « callee » de sorte que l’utilisateur puisse se concentrer sur la création de vues de rapport sur « Server » et « client ». À la suite de la méthodologie de qualité des appels, CQD est rationalisé afin d’identifier les conditions que les poches de mauvais appels ont en commun, un des principes permettant d’améliorer la qualité des appels.
  
## <a name="viewing-data-in-cqd"></a>Affichage de données dans CQD

Les données CQD peuvent être visualisées via le portail CQD et accessibles via des appels d’API REST.
  
### <a name="cqd-portal"></a>Portail CQD

Le portail est la méthode la plus rapide pour afficher les données dans le cube. Le portail est doté de plusieurs rapports intégrés qui peuvent être utilisés immédiatement. Les rapports intégrés sont liés de manière structurée pour guider l’utilisateur vers des tranches successivement plus petites et plus petites des données d’appel. Les rapports intégrés illustrent également les différentes façons d’afficher les données en illustrant une combinaison de graphiques et de tableaux avec différents tableaux croisés dynamiques, filtres et mesures. Chaque utilisateur qui accède au portail peut disposer de son propre ensemble de rapports qu’il peut modifier et partager. Pour plus d’informations sur l’utilisation du portail Web CQD, voir [Use Call Quality Dashboard for Skype for Business Server](use.md).
  
Systèmes d’exploitation pris en charge pour le portail CQD : Windows 8,1, Windows 8, Windows Server 2012 R2, Windows Server 2012 et Windows Server 2016 (Skype entreprise Server 2019 CQD uniquement).
  
Navigateurs pris en charge pour le portail CQD : Internet Explorer 11, Internet Explorer 10 et Internet Explorer 9.
  
### <a name="rest-apis"></a>API REST

Les données du cube sont également accessibles via les appels d’API REST. Les données récupérées via les appels de l’API REST peuvent être rendues via des pages HTML. Les utilisateurs peuvent tirer parti de la vitesse de requête et du schéma de haut niveau de CQD tout en créant des rapports personnalisés adaptés aux besoins de leur entreprise. Pour plus d’informations sur l’API et les exemples, voir [develop Call Quality Dashboard for Skype for Business Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Définition des exigences de votre organisation pour CQD

CQD fournit un archivage des données QoE, ainsi qu’une analyse rapide et approfondie des données de qualité des appels. Le guide suivant vous aide à déterminer quand et pourquoi déployer CQD.
  
### <a name="when-to-deploy-cqd"></a>Quand déployer CQD

 **CQD peut être déployé pour établir une mesure de la qualité des appels de base, même si une organisation ne présente pas de problèmes de qualité de l’appel.** Il est important d’établir une mesure de la qualité des appels de base, car chaque organisation a une combinaison différente de Wi-Fi par rapport à des employés filaires et distants. Lorsque des problèmes de qualité des appels surviennent, les mesures de qualité des appels les plus récentes peuvent être comparées à des intervalles de temps précédents. Les fonctionnalités de tendance de CQD permettent de détecter facilement les modifications apportées à la qualité des appels au fil du temps.
  
 **CQD peut être déployé pour trouver de façon proactive des problèmes susceptibles d’influer sur la qualité des appels.** Même si la qualité d’appel moyenne d’une organisation peut répondre aux objectifs définis par l’organisation, il peut y avoir des poches de problèmes de qualité d’appel masqués par rapport à la moyenne. CQD permet la répartition de tableau croisé dynamique des mesures de qualité des appels par grand nombre de dimensions dans la base de données QoEMetrics. La détection des éléments aberrants dans les groupes d’homologues permet de localiser de manière rapide les problèmes de qualité des appels.
  
 **CQD doit être déployé s’il existe des problèmes de qualité des appels au sein de l’organisation afin de réduire le temps nécessaire pour résoudre les problèmes.** CQD peut simplifier les enquêtes de qualité des appels existants en offrant des performances de création de rapports rapides et des fonctionnalités d’exploration dynamique. CQD est conçu pour de nombreux types de flux de travail dans les analyses de qualité des appels validation des réparations dans l’environnement.
  
### <a name="why-deploy-cqd"></a>Pourquoi déployer CQD

 **CQD doit être déployé si les rapports QoE doivent se produire pendant plus de 3 mois de données.** La base de données QoEMetrics et les rapports du serveur de surveillance sont conçus pour conserver et signaler un petit ensemble de données. La base de données de mesures QoE est optimisée pour des insertions rapides, et les performances de création de rapports peuvent donc être entravées par un grand nombre d’appels ou un accès concurrentiel à la base de données. La base de données d’archivage QoE d’CQD fournit une deuxième copie des données de mesures QoE avec des capacités de rétention plus longues. Le portail est également optimisé pour afficher jusqu’à 7 mois de données à la fois et peut rendre compte de toutes les données de l’archive QoE, le cas échéant.
  
 **CQD doit être déployé si des rapports QoE personnalisés sont nécessaires.** Le portail dispose d’une fonctionnalité d’éditeur de rapports permettant de créer et de prototyper rapidement et facilement des rapports. Il rend également disponibles les API REST disponibles pour l’accès par programme aux données du cube, ce qui permet une présentation personnalisée à l’aide de HTML/JavaScript ou de nombreuses autres structures. Il n’est plus nécessaire de créer de nouvelles requêtes SQL dans le but de créer des vues de données personnalisées pour la création de rapports.
  
 **CQD doit être déployé si la fonctionnalité de création de rapports QoE existante ne répond pas à la vitesse ou à la profondeur requise par l’organisation.** CQD est fourni avec de nombreux rapports intégrés. Les rapports sont immédiatement utiles et montrent comment l’extraction progressive des données peut offrir des informations supplémentaires à chaque niveau. La hiérarchie de rapports contribue également à la gestion logique des nombreux rapports et favorise la création de nombreux rapports facilement accessibles et compréhensibles. CQD n’offre pas simplement de vitesse et de flexibilité, mais est également optimisé pour les flux de travail développés par la méthodologie de qualité des appels.
  
## <a name="components-and-topologies-for-cqd"></a>Composants et topologies pour CQD

CQD est fourni avec plusieurs composants, et il est utile de comprendre les exigences de chaque composant et leur relation les unes avec les autres pour obtenir le déploiement le plus simple et le plus performant de l’outil. Le tableau suivant décrit le composant dépendant pour chaque composant CQD.
  

|**Nom du composant**|**Composant dépendant**|
|:-----|:-----|
|Archives QoE  <br/> |Microsoft SQL Server  <br/> |
|Carré  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portail  <br/> |Services d’information Microsoft  <br/> |
|Service de référentiel (partie de l’installation du portail)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Pour l’archivage et le cube QoE, certaines options de déploiement requièrent l’aide à la décision ou les éditions entreprise de Microsoft SQL Server. Pour plus d’informations, reportez-vous à la section [Configuration requise pour l’infrastructure pour CQD](plan.md#Infrastructure_Req) ci-dessous.
  
![Composants CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configuration d’un seul serveur

Tous les composants CQD et les composants dépendants peuvent être installés sur un seul ordinateur. La configuration à une seule zone est la configuration la plus simple et permet à CQD d’être autonome. CQD a simplement besoin d’accéder à la base de données de mesures QoE sur le serveur de surveillance. Le serveur CQD peut être un ordinateur autonome, une machine virtuelle, ou même être le serveur de surveillance, en fonction des ressources disponibles de l’ordinateur hôte et des performances requises. 
  
Lors de l’installation, l’utilisateur qui effectue l’installation doit simplement fournir les instances Microsoft SQL Server et Microsoft SQL Server Analysis Services qui ont été configurées précédemment sur l’ordinateur sur lequel le CQD doit être installé. Pour plus d’informations, reportez-vous à la rubrique [déployer le tableau de bord de la qualité des appels pour Skype entreprise Server](deploy-0.md) .
  
### <a name="multiserver-configuration"></a>Configuration MultiServer

Dans une configuration multiserveur, l’archive, le cube et le portail QoE peuvent tous se trouver sur des machines différentes. Il existe deux utilisations principales pour la configuration MultiServer :
  
- Hébergement d’un portail Web CQD et d’un cube CQD sur différents serveurs.
    
- Hébergement d’un portail de « développement » distinct du portail de production. 
    
  **Hébergement d’un portail Web CQD et d’un cube CQD sur des ordinateurs différents.** Les organisations qui peuvent avoir besoin de séparer le portail CQD de l’installation SQL Server ou qui peuvent souhaiter combiner et faire correspondre les éditions SQL Server pour l’instance SQL Server et l’instance SQL Server Analysis Services peuvent choisir d’installer le portail CQD et CQD cube sur différentes machines. Le composant d’archive QoE peut également être le seul composant CQD installé si l’organisation souhaite simplement disposer d’une méthode viable pour archiver les données QoE sans atteindre des limites de performances sur le serveur de surveillance.
  
![Serveur CQD](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hébergement d’un portail de « développement » distinct du portail de production.** Les organisations qui développent leurs propres rapports personnalisés (via les API REST) peuvent préférer déployer des instances de portail supplémentaires (CQD) avec le portail de production, ce qui permet aux utilisateurs réguliers d’accéder aux analyses ou à la surveillance de la qualité des appels. Le portail de développement peut isoler les modifications apportées au portail à partir de l’environnement de production. Les portails Web supplémentaires peuvent être déployés sur différentes machines (voir ci-dessous) ou déployés sur des répertoires Web différents sur le même ordinateur (non illustré). Pour ce faire, le portail Web CQD supplémentaire doit être copié sur l’ordinateur de production manuellement, car le processus de configuration de CQD déploie toujours le portail Web CQD sur le site Web par défaut avec des noms d’applications Web prédéfinies.
  
![Planifier CQD MultiServer](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologies prises en charge

CQD ne fusionne pas les données à partir de plusieurs bases de données QoEMetrics, comme dans le cas où il existe plusieurs topologies de Skype entreprise Server, chacune avec son propre serveur de surveillance. Chaque instance CQD doit pointer vers une base de données QoEMetrics. Toutefois, étant donné que CQD déplace une grande partie de la charge de travail de création de rapports à partir du serveur de surveillance, les grandes organisations qui devaient déployer un serveur de surveillance par topologie Skype entreprise Server devraient envisager d’utiliser un serveur de surveillance pour toutes les topologies.
  
## <a name="infrastructure-requirements-for-cqd"></a>Configuration requise pour l’infrastructure pour CQD
<a name="Infrastructure_Req"> </a>

CQD, y compris tous ses composants et les composants dépendants, peuvent être déployés sur une machine virtuelle, une seule machine ou sur plusieurs machines. La configuration matérielle et logicielle minimale requise est indiquée ci-dessous. La disponibilité des données et les performances des requêtes peuvent varier de quelques minutes à quelques heures, en fonction du nombre d’utilisateurs et de la configuration de Skype entreprise Server actifs, de sorte que certaines mesures de performances sont indiquées ci-dessous.
  
|||
|:-----|:-----|
|Pour CQD 2015 <br/> |  <br/> |
|Systèmes d’exploitation pris en charge   <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|SQL Server pris en charge  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|Pour CQD 2019 <br/> |  <br/> |
|Systèmes d’exploitation pris en charge   <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|SQL Server pris en charge  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
CQD utilise Microsoft SQL Server, Microsoft SQL Server Analysis Services et Microsoft Internet Information Services de sorte que la configuration matérielle et logicielle minimale de CQD est fondamentalement identique à celle de ces composants dépendants. Toutefois, en fonction des besoins de l’Organisation concernant l’actualisation des données (qui dépend en partie du volume de données QoE que l’organisation génère) et des coûts de déploiement, des considérations supplémentaires sur le déploiement doivent être apportées.
  
Le traitement des données dans CQD est séparé en deux étapes principales : 
  
- Processus d’archivage QoE
    
- Traitement de cube CQD
    
  **Traitement des archives QoE.** La tâche de traitement de l’archive QoE copie les données de la base de données de mesures QoE sur le serveur de surveillance vers la base de données d’archivage QoE. Il existe deux situations dans lesquelles le temps de traitement de la tâche aurait fondamentalement différentes caractéristiques de performances. Le premier est après l’installation initiale de CQD. Lorsque la tâche est exécutée pour la première fois après une nouvelle installation, la tâche de traitement de l’archive QoE copie toutes les données de la base de données de mesures QoE dans la base de données d’archivage QoE. Le second est le traitement périodique après cet arrondi initial. La tâche de traitement d’archive QoE est exécutée toutes les 15 minutes et traite les nouveaux enregistrements QoE qui se trouvent dans la base de données de mesures QoE. En règle générale, le temps de traitement initial n’est pas un problème, car il est exécuté uniquement la première fois, lors de l’installation de CQD. Toutefois, si le serveur CQD est gravement sous-configuré, cette tâche peut prendre plusieurs heures. Reportez-vous au tableau ci-dessous pour obtenir des temps de traitement d’archives QoE initiales.
  
  **Traitement de cube CQD.** La tâche de traitement du cube agrège les données de la base de données d’archivage QoE dans le cube. Le temps de traitement initial du cube et le temps de traitement du cube suivant sont déterminés par l’édition SQL Server Analysis Services utilisée pour le cube CQD. Si la version Standard Edition est utilisée, il n’existe aucune différence entre le temps de traitement initial du cube et le temps de traitement du cube suivant, car chaque fois que les données du cube sont actualisées, il s’agit toujours d’un traitement complet de toutes les données disponibles. (Cela signifie que le temps de traitement du cube augmente à mesure que la quantité de données dans la base de données d’archive QoE augmente.) Étant donné que l’édition Business Intelligence et l’édition entreprise de SQL Server prennent en charge les partitions, si l’une des éditions est utilisée, seule la première exécution traitera toutes les données de la base de données d’archivage QoE. Dans les exécutions suivantes, lorsque la tâche est déclenchée toutes les 15 minutes, la tâche traite uniquement les nouveaux enregistrements ajoutés à la base de données d’archivage QoE depuis la dernière exécution de la tâche. Une fois par jour, il y aura également un traitement complet sur la partition qui contient les données du mois en cours.
  
Les caractéristiques de l’ordinateur physique peuvent avoir une incidence sur les performances de CQD, ainsi que sur les fonctionnalités logicielles disponibles à partir des composants SQL Server. Le composant d’archive QoE sera plus gourmand en disques comparé aux autres composants, tandis que le composant de cube sera plus gourmand en ressources processeur et de mémoire. Tous ces facteurs contribuent au temps total de traitement des données d’CQD, ce qui affecte directement l’actualisation et la disponibilité des données. Les organisations doivent prendre des décisions sur le matériel et les logiciels en fonction des besoins individuels de l’organisation. 
  
### <a name="tested-hardware-configurations"></a>Configurations matérielles testées

Cette section suppose qu’il existe une seule base de données QoEMetrics dans l’environnement. 
  
**Profils d’ordinateur**

|**Ordinateur**|**Cœurs de l’UC**|**RAM**|**Archives QoE et cube sur le même disque**|**Archive QoE et base de données temp SQL sur le même disque**|
|:-----|:-----|:-----|:-----|:-----|
|Machine virtuelle  <br/> |4   <br/> |7 GO  <br/> |Oui  <br/> |Oui  <br/> |
|4 cœurs  <br/> |4   <br/> |20 Go  <br/> |Oui  <br/> |Non  <br/> |
|8 cœurs  <br/> |8   <br/> |32 Go   <br/> |Oui  <br/> |Non  <br/> |
|16 cœurs  <br/> |16   <br/> |128 Go  <br/> |Non  <br/> |Non  <br/> |
   
**Résultats des performances**

|**Ordinateur**|**Taille de la base de données des mesures QoE**|**Partitions SQL**|**Type de disque**|**Nombre de flux**|**Processus d’archivage initial**|**Processus de cube initial**|**Processus d’archivage suivant**|**Processus de cube suivant**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Machine virtuelle  <br/> |900 MO  <br/> |Unique  <br/> |VHD (taille variable)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Machine virtuelle  <br/> |9 GO  <br/> |Unique  <br/> |VHD (taille variable)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Machine virtuelle  <br/> |9 GO  <br/> |Unique  <br/> |Disque dur virtuel (de taille fixe)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Machine virtuelle  <br/> |PLUS DE 30 GO  <br/> |Unique  <br/> |Disque dur virtuel (de taille fixe)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 cœurs  <br/> |9 GO  <br/> |Unique  <br/> |Plusieurs disques  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 cœurs  <br/> |9 GO  <br/> |Multiple  <br/> |Plusieurs disques  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 cœurs  <br/> |PLUS DE 30 GO  <br/> |Unique  <br/> |Plusieurs disques  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 cœurs  <br/> |PLUS DE 30 GO  <br/> |Multiple  <br/> |Plusieurs disques  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 cœurs  <br/> |200 Go  <br/> |Unique  <br/> |Plusieurs disques  <br/> |125 M  <br/> |6 + jours  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 cœurs  <br/> |500 Go  <br/> |Multiple  <br/> |Plusieurs piles de disques  <br/> |250 M  <br/> |8 jours  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Il n’est pas prévu de les rencontrer dans des déploiements réels, car la base de données de mesures QoE doit avoir entre 9 et 18 mois de données, mais elles sont fournies ici pour des raisons de finalisation.
  
### <a name="service-account-requirements"></a>Exigences en matière de compte de service

Vous aurez besoin d’un compte (avec un accès en lecture à QoEMetrics) que l’agent SQL sur le serveur CQD peut utiliser pour importer les données dans le QoEArchiveDB.
  
Vous devrez peut-être également configurer un compte distinct pour un travail SSAS afin d’extraire les données de QoEArchiveDB (il s’agit d’un processus facultatif).
  
En règle générale, IIS utilise le service réseau en tant qu’identité du pool d’applications, mais peut être configuré sur un compte de service.
  
### <a name="portal-access-control"></a>Contrôle d’accès au portail

Par défaut, tout utilisateur authentifié a accès. Cela peut être modifié à l’aide de règles d’autorisation IIS pour limiter l’accès à un groupe spécifique.
  
### <a name="pre-install-requirements"></a>Conditions préalables à l’installation

Ces instructions supposent qu’une base de données de mesures QoE a déjà été installée et qu’elle est en cours d’exécution dans la topologie Skype entreprise Server.
  
#### <a name="hardware-requirements"></a>Configuration matérielle requise

CQD utilise Microsoft SQL Server, Microsoft SQL Analysis Server et Microsoft Internet Information Server pour que la configuration matérielle et logicielle minimale de CQD soit fondamentalement identique à celle de ces composants dépendants. Toutefois, en fonction des besoins de l’Organisation concernant l’actualisation des données (qui dépend en partie du volume de données QoE que l’organisation génère) et des coûts de déploiement, des considérations supplémentaires sur le déploiement doivent être apportées.
  
#### <a name="software-requirements"></a>Configuration logicielle requise

Les systèmes d’exploitation suivants sont requis pour CQD :
  
- Windows Server 2008 R2 avec IIS 7,5
    
- Windows Server 2012 avec IIS 8,0
    
- Windows Server 2012 R2 avec IIS 8,5

- Windows Server 2016 avec IIS 10,0 (Skype entreprise Server 2019 CQD uniquement)

- Windows Server 2019 (Skype entreprise Server 2019 CQD uniquement)
    
Les services de rôle IIS requis (dans l’ordre hiérarchique) sont les suivants :
  
- Serveur web
    
  - Fonctionnalités HTTP communes
    
  - Contenu statique
    
  - Document par défaut
    
  - Développement d’applications
    
  - ASP.NET
    
  - Filtres ISAPI
    
  - Diagnostics d’intégrité &amp;
    
  - Journalisation HTTP
    
  - Sécurité
    
  - Autorisation d’URL
    
  - Authentification Windows
    
  - Outils de gestion
    
  - Console de gestion IIS
    
> [!NOTE]
>  Notez les points suivants pour les exigences ci-dessus : les versions > 3,5 et 4,5 de .NET Framework sont disponibles. Les deux sont obligatoires (plus précisément, 3,5 SP1 est requis). > sur certains systèmes, si ASP.NET est configuré avant l’installation d’IIS, ASP.NET peut ne pas être enregistré dans IIS. Le problème est lié à l’absence de pools d’applications pour la version .net correspondante et la version .NET CLR est manquante dans la configuration du pool d’applications. Pour résoudre ce problème sur Windows Server 2008 R2, exécutez `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`. Sur Windows Server 2012 et Windows Server 2012 R2, exécutez `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` suivi en supprimant le module « ServiceModel » du site Web par défaut dans le gestionnaire des services Internet (IIS). > les outils de gestion sont facultatifs, mais recommandés.
  
Pour installer ces exigences à l’aide de PowerShell, exécutez la commande suivante :
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Les versions suivantes de SQL Server sont prises en charge :
  
- SQL Server 2012
    
- SQL Server 2014

- SQL Server 2016

- SQL Server 2017

- SQL Server 2019 (Skype entreprise Server 2019 CQD uniquement)
    
L’aide à la décision ou Enterprise Edition est recommandée pour des raisons de performances. Ces éditions autorisent l’utilisation de plusieurs fichiers de partition pouvant être traités en parallèle, ce qui est bénéfique pour le traitement des données sur plusieurs mois ou plus. 
  
Bien que ce ne soit pas recommandé, Standard Edition est également pris en charge. Le traitement sera limité à une seule partition (qui doit être configurée lors de l’installation). 
  
Dans tous les cas, « services de moteur de base de données » et « Analysis Services » doivent être installés. Il est recommandé, mais pas obligatoire d’installer également la fonctionnalité « outils de gestion-terminé », qui ajoute la prise en charge de SQL Server Management Studio pour Analysis Services. L’écran de sélection de fonctionnalité doit ressembler à la figure.
  
![Configuration requise pour la fonctionnalité SQL Server](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Lors de la configuration de l’installation de SSAS, dans la configuration d’Analysis Services, définissez « mode serveur » sur « mode de Mining multidimensionnel et données ». 
  
Pour plus d’informations sur l’installation et la configuration des fonctionnalités d’aide à la décision SQL Server, voir [install Analysis Services in Multidimensional and Data Mining mode](https://msdn.microsoft.com/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Exigences en matière de compte

Trois comptes de service de domaine sont recommandés sur le principe des privilèges minimum : 
  
- Une instance qui dispose déjà d’un principal de sécurité de connexion pour la base de données de mesures QoE (avec le privilège db_datareader) et d’un principal de sécurité de connexion dans l’instance SQL Server d’archive QoE (nécessaire pour créer un objet serveur lié lors de l’installation). Ce compte sera utilisé pour exécuter l’étape « données d’archivage QoE » du travail de l’agent SQL Server.
    
- Un qui sera utilisé pour exécuter l’étape « traiter le cube » du travail de l’agent SQL Server. Le programme d’installation crée un principal de sécurité de connexion à la base de données d’archivage QoE (avec le privilège lecture et écriture) et crée également un membre dans le rôle QoE (avec le privilège contrôle total) pour le cube.
    
- Un qui sera utilisé pour exécuter le processus de travail IIS pour les portails Web et les API Web. Le programme d’installation crée un principal de sécurité de connexion à la base de données d’archivage QoE (avec le privilège lecture), un principal de sécurité de connexion à la base de données de référentiel (avec les privilèges lecture et écriture) et un membre dans QoERole (avec le privilège contrôle total) pour le cube. 
    
    > [!NOTE]
    > Lorsque la base de données d’archives QoE et la base de données de référentiel sont hébergées dans le même serveur SQL, un seul principal de sécurité de connexion avec deux mappages utilisateur est créé. 
  
Les deux premiers comptes peuvent être considérés logiquement comme des « comptes de service principaux » et le dernier compte est un « compte de service frontal ». Bien que cela ne soit pas recommandé, il est possible d’utiliser un seul compte dans tous les cas.
  
> [!NOTE]
> Le compte d’utilisateur qui lance l’installation doit également disposer d’un accès en lecture à la base de données des mesures QoE (en plus des droits d’administrateur d’ordinateur sur le serveur de base de données d’archivage QoE où l’installation doit avoir lieu). 
  
## <a name="capacity-planning"></a>Planification de la capacité
<a name="Infrastructure_Req"> </a>

CQD est conçu pour un impact minimal sur QoEMetrics : le code a été optimisé pour ne pas verrouiller les données et les travaux d’importation sont ajustables.
  
Le type de matériel à utiliser dépend de votre configuration requise pour l’exécution des synchronisations rapides. La taille du disque est la suivante :
  
- QoEArchive ~ 1,5 x plus grand que QoEMetrics DB initialement
    
- Le cube SSIS compresse les données presque 10% par rapport à la base de données
    
- Les données sont partitionnées tous les mois ; les partitions peuvent être supprimées
    

