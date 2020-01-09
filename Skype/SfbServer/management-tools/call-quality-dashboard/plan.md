---
title: Planifier le tableau de bord de qualité des appels pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Résumé : Découvrez les éléments à prendre en compte lorsque vous planifiez le tableau de bord de qualité des appels.'
ms.openlocfilehash: 3a0982f565495740887b6da07dd802de1205dcf8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991409"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Planifier le tableau de bord de qualité des appels pour Skype entreprise Server 
 
**Résumé :** Découvrez les points à prendre en considération lorsque vous planifiez le tableau de bord de qualité des appels.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Vue d’ensemble du tableau de bord de qualité des appels de Skype entreprise Server

Le tableau de bord de qualité des appels de Skype entreprise Server (bord) est une couche de rapport sur la qualité de la base de données du serveur de surveillance dans Skype entreprise Server. BORD utilise Microsoft SQL Server Analysis Services pour fournir des informations sur l’utilisation agrégée et la qualité des appels, ainsi que pour le filtrage et le glissement du jeu de données. Les fonctionnalités de bord sont les suivantes :
  
- **Stockage d’archivage des données QoE via le composant d’archive QoE de bord.** Le composant d’archive QoE peut stocker des données QoE pour une durée bien plus longue que celle du serveur de surveillance. Cela permet de passer des tendances et de signaler jusqu’à sept mois de données à la fois, grâce auquel vous pouvez faire glisser la fenêtre de création de rapports dans le temps.
- **Rapports et analyse grâce à la puissance et à la vitesse de Microsoft SQL Server Analysis Services.** BORD utilise Microsoft SQL Analysis Services pour fournir des fonctionnalités de synthèse, de filtrage et de tableau croisé dynamique rapides pour alimenter le tableau de bord via un cube d’analyse. Le signalement de la vitesse d’exécution et la possibilité de descendre dans les données peuvent réduire considérablement les temps d’analyse.
- **Nouveau schéma de données optimisé pour la création de rapports sur la qualité des appels.** Le cube possède un schéma conçu pour le rapport qualité de la voix et les investigations. Les utilisateurs du portail peuvent se consacrer aux tâches de création de rapports au lieu de déterminer comment le schéma de base de données de la fonction QoE est mappé sur les vues dont ils ont besoin. La combinaison de l’archive QoE et du cube fournit une abstraction qui réduit la complexité des rapports et analyses via bord. Le schéma de base de données d’archive QoE contient également des tables qui peuvent être renseignées à l’aide de données spécifiques de déploiement pour améliorer la valeur globale des données.
- **Concepteur de rapports intégré et modification de rapport inaltérable.** Le composant portail est fourni avec plusieurs rapports prédéfinis modélisés selon la méthode de qualité d’appel. Les utilisateurs du portail peuvent modifier les rapports et créer des rapports à l’aide de la fonctionnalité d’édition du portail.
- **API Web : accès à la structure du rapport et aux données du cube d’analyse.** L’infrastructure de création de tableaux de bord n’est pas la seule façon d’afficher les données du cube. BORD fournit plusieurs exemples d’utilisation de HTML et JavaScript pour récupérer les données des API Web bord et afficher les données dans un format personnalisé. La combinaison de l’éditeur de rapport et des API Web bord permet un prototypage rapide des rapports et de la disposition de rapport personnalisée.

> [!NOTE]
> Un administrateur peut désormais gérer Skype entreprise Server 2019 à l’aide de [bord version 3](https://cqd.teams.microsoft.com) (se connecter avec les informations d’identification d’administrateur). Pour cela, vous devez disposer d’une implémentation hybride et de l’utilisation du connecteur de données d’appel (CDC). Pour plus d’informations sur l’activation de CDC, voir [connecteur des données d’appel](/SkypeForBusiness/hybrid/plan-call-data-connector) de la planification. Pour plus d’informations sur la version 3 d’bord, voir [activer et utiliser le tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) pour plus d’informations sur bord version 3.

## <a name="cqd-design-goals"></a>Objectifs de conception de bord

Le Tableau de bord de la qualité des appels permet aux professionnels de l’informatique d’utiliser des données agrégées pour identifier des secteurs cibles dans leur environnement rencontrant des problèmes de qualité multimédia. Il permet à un professionnel de l’informatique de comparer des statistiques de différents groupes d’utilisateurs et d’identifier des tendances et modèles. Le tableau n’est pas utilisé pour résoudre des problèmes d’appel spécifiques, mais pour identifier les problèmes et les solutions qui concernent de nombreux utilisateurs dans un environnement donné. 
  
## <a name="call-quality-dashboard-components"></a>Composants du tableau de bord de qualité des appels

Le tableau de bord de qualité des appels se compose de plusieurs bases de données, de tâches d’agent Microsoft SQL, de processus et d’applications Web. Les tâches de l’agent Microsoft SQL copient périodiquement les données de la base de données de valeurs QoE dans la base de données d’archive QoE et traite le cube avec les données dans la base de données d’archive QoE. La base de données du référentiel stocke les définitions de rapport qui alimentent le portail. Le portail fournit l’accès du navigateur aux données du cube. 
  
Les composants bord, notamment les bases de données d’archive QoE, de cube et de référentiel, peuvent être installés sur le serveur de surveillance, installés sur leur propre serveur ou installés sur plusieurs serveurs. La méthode d’installation particulière dépend des besoins en matière de performances de bord ainsi que de l’impact sur d’autres processus sur les mêmes serveurs. Pour plus d’informations, reportez-vous à la section « composants et topologies pour bord », plus loin dans cet article.
  
### <a name="architectural-overview"></a>Présentation architecturale

Pour résumer, bord nécessite les éléments suivants :
  
- Deux bases de données : une base de données d’archive et une base de données de référentiel.
    
- Un cube SSA qui Visualisez les données agrégées 
    
- Portail Web bord d’hébergement de services Internet
    
![Composants CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
La même architecture bord prend en charge Lync Server 2013 et Skype entreprise. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>BORD et Skype entreprise par rapport à Lync 2013

 Dans un environnement Skype entreprise uniquement, les fonctionnalités suivantes sont disponibles :
  
- Signalisation Wi-Fi de la force du signal
    
- Rapports Wi-Fi des pilotes de chipset
    
- Évaluer les données de mon appel 
    
## <a name="information-available-through-cqd"></a>Informations disponibles par le biais de bord

BORD est en mesure d’afficher le nombre de flux de partage d’application et audio de Skype entreprise Server, et le nombre de flux de partage d’application et de rapports d’appels incorrects. Les vues peuvent être coupées en tranches et filtrées selon de nombreuses dimensions différentes. BORD dessine les données de la base de données de métriques QoE dans le serveur de surveillance. Les données sont ensuite fusionnées avec les données fournies par le client, telles que le mappage de sous-réseau à bâtiment pour créer des rapports tels que « qualité d’appel par bâtiment » possible. 
  
BORD soustrait également de nombreuses spécificités de l’utilisation des données de QoE (par exemple, « appelant » et « appelé »), de telle sorte que l’utilisateur puisse se concentrer sur la création de vues de rapport concernant « serveur » et « client ». Après la méthodologie de qualité d’appel, bord est rationalisé pour faciliter l’identification des poches d’appels médiocres en commun, l’un des principes d’amélioration de la qualité des appels.
  
## <a name="viewing-data-in-cqd"></a>Affichage de données dans bord

Les données bord peuvent être affichées via le portail bord et accessibles via les appels d’API REST.
  
### <a name="cqd-portal"></a>Portail bord

Le portail est le moyen le plus rapide d’afficher les données dans le cube. Le portail est fourni avec plusieurs rapports prédéfinis utilisables immédiatement. Les rapports intégrés sont liés de manière structurée afin de guider l’utilisateur vers des secteurs plus petits et plus petits des données d’appel. Les rapports intégrés présentent également les différentes méthodes d’affichage des données en montrant une combinaison de graphiques et de tableaux avec différents tableaux croisés dynamiques, filtres et mesures. Chaque utilisateur qui accède au portail peut avoir son propre jeu de rapports qu’il peut modifier et partager. Pour plus d’informations sur l’utilisation du portail Web bord, voir [utiliser le tableau de bord de qualité des appels pour Skype entreprise Server](use.md).
  
Systèmes d’exploitation pris en charge pour le portail bord : Windows 8,1, Windows 8, Windows Server 2012 R2, Windows Server 2012 et Windows Server 2016 (Skype entreprise Server 2019 bord uniquement).
  
Navigateurs pris en charge pour le portail bord : Internet Explorer 11, Internet Explorer 10 et Internet Explorer 9.
  
### <a name="rest-apis"></a>API REST

Vous pouvez également accéder aux données du cube via les appels d’API REST. Les données récupérées par le biais des appels d’API REST peuvent être affichées dans des pages HTML. Les utilisateurs peuvent tirer parti de la vitesse de requête et du schéma de haut niveau de bord tout en créant des rapports personnalisés adaptés aux besoins de leurs entreprises. Pour plus d’informations sur l’API et les exemples, voir [développer le tableau de bord de qualité des appels pour Skype entreprise Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Définition des exigences de votre organisation pour bord

BORD fournit un archivage de données QoE et une analyse rapide et complète des données de qualité d’appel. Le guide suivant vous aide à déterminer quand et pourquoi vous devez déployer bord.
  
### <a name="when-to-deploy-cqd"></a>Moment du déploiement de bord

 **BORD peut être déployé pour établir une mesure de qualité des appels de base, même si une organisation n’a pas de problème de qualité des appels.** Il est important de définir une mesure de qualité des appels de base, car chaque organisation a une combinaison de réseaux Wi-Fi et de personnes distantes et distantes. En cas de problème de qualité d’appel, les mesures de qualité d’appel les plus récentes peuvent être comparées à des intervalles de temps précédents. Les fonctionnalités de courbe de bord vous permettent de détecter facilement les changements de qualité d’appel au fil du temps.
  
 **BORD peut être déployé pour détecter de manière proactive des zones de problèmes qui peuvent avoir un impact sur la qualité des appels.** Même si la qualité d’appel moyenne d’une entreprise est susceptible de correspondre aux cibles définies par l’organisation, il est possible qu’il y ait des poches de problèmes de qualité d’appel qui sont masqués par des métriques moyennes. BORD autorise la répartition de type tableau croisé dynamique des métriques de qualité d’appel selon de nombreux axes de la base de données QoEMetrics. Le fait de détecter les éléments non-errants dans les groupes d’homologues permet de rechercher rapidement les problèmes de qualité d’appel.
  
 **BORD doit être déployé s’il rencontre des problèmes de qualité d’appel au sein de l’organisation afin de réduire le temps nécessaire à la résolution des problèmes.** BORD peut simplifier les enquêtes sur la qualité des appels, en offrant des performances de rapport rapide et des fonctionnalités d’exploration dynamique. BORD est conçu pour de nombreux types de flux de travail dans les enquêtes de qualité d’appel pour la validation des réparations dans l’environnement.
  
### <a name="why-deploy-cqd"></a>Pourquoi déployer bord

 **BORD doit être déployé si le rapport QoE doit se produire pendant plus de 3 mois de données.** Les rapports sur le serveur de base de données et de surveillance de QoEMetrics permettent de conserver et de signaler un ensemble réduit de données. La base de données des métriques QoE est optimisée pour les insertions rapides, et par conséquent, la création de rapports sur la base de données peut être entravée par un grand nombre d’appels ou le signalement d’un rapport compétitif. La base de données d’archive QoE d’bord fournit une seconde copie des données de mesure QoE avec des capacités de rétention bien plus longues. Le portail est également optimisé pour afficher jusqu’à 7 mois de données à la fois et peut signaler toutes les données de l’archive QoE selon les besoins.
  
 **BORD doit être déployé si des rapports QoE personnalisés sont nécessaires.** Le portail est doté d’une fonctionnalité d’éditeur de rapports permettant de créer et de créer des rapports rapidement et facilement. Il rend également disponibles les API REST disponibles pour l’accès par programmation aux données du cube, permettant ainsi une présentation personnalisée en HTML/JavaScript ou bien d’autres infrastructures. Il n’est plus nécessaire de créer de nouvelles requêtes SQL dans le but de créer des vues de données personnalisées pour la création de rapports.
  
 **BORD doit être déployé si la fonctionnalité de création de rapports QoE existante ne correspond pas à la vitesse ou à la profondeur requise par l’organisation.** BORD est fourni avec de nombreux rapports intégrés. Les rapports sont immédiatement utiles et montrent la manière dont les données de perçage progressivement dans les données peuvent vous permettre d’accéder à des informations supplémentaires à chaque niveau. La hiérarchie de rapports facilite également la gestion des nombreux rapports d’une manière logique et favorise la création de nombreux rapports facilement accessibles et compréhensibles. BORD ne propose pas uniquement de vitesse et de flexibilité, mais il est également optimisé pour les flux de travail développés par la méthodologie de qualité des appels.
  
## <a name="components-and-topologies-for-cqd"></a>Composants et topologies pour bord

BORD est fourni avec plusieurs composants, et il permet de comprendre les exigences de chaque composant et leur relation pour obtenir le déploiement le plus simple et le plus simple de l’outil. Le tableau suivant décrit le composant dépendant de chaque composant bord.
  

|**Nom du composant**|**Composant dépendant**|
|:-----|:-----|
|Archive QoE  <br/> |Microsoft SQL Server  <br/> |
|OLAP  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portail  <br/> |Services d’information Microsoft  <br/> |
|Service du référentiel (partie de l’installation du portail)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Dans le cas d’une archive et d’un cube QoE, certaines options de déploiement nécessitent des éditions d’aide à la décision ou des éditions Enterprise de Microsoft SQL Server. Pour plus d’informations, reportez-vous à la section [exigences d’infrastructure pour bord](plan.md#Infrastructure_Req) ci-dessous.
  
![Composants CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configuration d’un serveur unique

Tous les composants bord et composants dépendants peuvent être installés sur un ordinateur. La configuration à une seule boîte est la configuration la plus simple et permet à bord d’être autonome. BORD n’aura besoin d’accéder à la base de données de valeurs QoE sur le serveur de surveillance. Le serveur bord peut être un ordinateur autonome, une machine virtuelle ou peut même être le serveur de surveillance, en fonction des ressources disponibles de l’ordinateur hôte et des besoins en termes de performances. 
  
Lors de l’installation, l’utilisateur qui effectue l’installation doit simplement fournir les instances Microsoft SQL Server et Microsoft SQL Server Analysis Services qui ont été précédemment configurées sur l’ordinateur sur lequel bord doit être installé. Pour plus d’informations, reportez-vous à la rubrique [déploiement du tableau de bord de qualité des appels pour Skype entreprise Server](deploy-0.md) .
  
### <a name="multiserver-configuration"></a>Configuration multiserveur

Dans une configuration multiserveur, l’archive, le cube et le portail QoE peuvent tous être sur des ordinateurs différents. Il existe deux utilisations principales de la configuration multiserveur :
  
- Hébergement d’un portail Web bord et d’un cube bord sur différents serveurs.
    
- Hébergement d’un portail de « développement » distinct du portail « de production ». 
    
  **Hébergement d’un portail Web bord et d’un cube bord sur différentes machines.** Les organisations susceptibles de disposer de la configuration requise pour séparer le portail bord de l’installation de SQL Server, ou celles susceptibles de mélanger et de faire correspondre les éditions SQL Server pour l’instance SQL Server et l’instance SQL Server Analysis Services peuvent choisir d’installer le portail bord et BORD cube sur différentes machines. Le composant d’archive QoE peut également être le seul composant bord installé si l’organisation veut simplement disposer d’une méthode viable pour archiver les données QoE sans atteindre de limites de performance sur le serveur de surveillance.
  
![CQD mono-serveur](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hébergement d’un portail de « développement » distinct du portail « de production ».** Les organisations qui développent leurs propres rapports personnalisés (via les API REST) peuvent être amenés à déployer des instances de portail supplémentaires (bord) en plus du portail de production, qui permet aux utilisateurs d’accéder à des enquêtes ou à la qualité des appels. Le portail de développement peut isoler les modifications apportées au portail de l’environnement de production. Vous pouvez déployer des portails Web supplémentaires sur différentes machines (comme illustré ci-dessous) ou les déployer sur différents répertoires Web sur le même ordinateur (non affiché). Pour ce faire, le portail Web bord supplémentaire doit être copié sur l’ordinateur de production manuellement, car le processus de configuration d’bord déploie toujours le portail Web bord vers le site Web par défaut avec les noms des applications Web prédéfinies.
  
![Planification de multi-serveur CQD](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologies prises en charge

BORD ne fusionne pas les données de plusieurs bases de données QoEMetrics, comme dans le cas où il existe plusieurs topologies serveur Skype entreprise, chacune avec son propre serveur de surveillance. Chaque instance bord doit pointer vers une base de données QoEMetrics. Toutefois, étant donné que bord démontera considérablement la charge de travail de création de rapports du serveur de surveillance, il est préférable d’utiliser un serveur de surveillance pour toutes les topologies pour le déploiement d’un serveur de surveillance par topologie Skype entreprise Server.
  
## <a name="infrastructure-requirements-for-cqd"></a>Exigences d’infrastructure pour bord
<a name="Infrastructure_Req"> </a>

BORD, y compris tous ses composants et composants dépendants, peuvent être déployés sur une machine virtuelle, sur un seul ordinateur ou sur plusieurs machines. La configuration minimale requise pour les logiciels et les logiciels est indiquée ci-dessous. La disponibilité des données et des performances de requête peut varier d’un nombre de minutes à une heure, en fonction du nombre d’utilisateurs et de configurations du serveur Skype entreprise actifs, de sorte que certaines mesures de performance sont fournies ci-dessous.
  
|||
|:-----|:-----|
|Pour bord 2015 <br/> |  <br/> |
|Systèmes d’exploitation pris en charge  <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|SQL Server pris en charge  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|Pour bord 2019 <br/> |  <br/> |
|Systèmes d’exploitation pris en charge  <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|SQL Server pris en charge  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
BORD utilise Microsoft SQL Server, Microsoft SQL Server Analysis Services et Microsoft Internet Information Services, de sorte que les configurations matérielles et logicielles minimales d’bord sont les mêmes que celles de ces composants dépendants. Toutefois, en fonction des besoins de l’organisation en matière de fraîcheur des données (qui dépendront en partie du volume de données QoE générées par l’entreprise) et du coût de déploiement, des considérations en matière de déploiement supplémentaires doivent être prises en compte.
  
Le traitement des données dans bord est divisée en deux étapes principales : 
  
- Processus d’archive QoE
    
- Traitement de cube bord
    
  **Traitement d’archive QoE.** La tâche de traitement d’archive QoE copie les données de la base de données QoE Metrics du serveur de surveillance dans la base de données d’archive QoE. Il existe deux situations dans lesquelles le temps de traitement de la tâche a fondamentalement différentes caractéristiques de performances. Le premier est après l’installation initiale de bord. Lorsque la tâche est exécutée pour la première fois après une nouvelle installation, la tâche de traitement d’archive QoE copie toutes les données de la base de données QoE Metrics dans la base de données d’archive QoE. Le deuxième est le traitement périodique après cet arrondi initial. La tâche de traitement d’archive QoE sera exécutée toutes les 15 minutes et traitera les nouveaux enregistrements QoE qui se trouvent dans la base de données des métriques QoE. En règle générale, le délai de traitement initial n’est pas un problème, car il n’est pas exécuté pour la première fois, lorsque bord est installé. Toutefois, si le serveur bord est sérieusement en service, cette tâche peut prendre plusieurs heures. Consultez le tableau ci-dessous pour obtenir un exemple du temps de traitement initial d’archive QoE.
  
  **Traitement de cube bord.** La tâche de traitement du cube agrège les données de la base de données d’archive QoE dans le cube. Le temps de traitement initial du cube et le temps de traitement du cube ultérieur sont déterminés par l’édition SQL Server Analysis Services utilisée pour le cube bord. Si l’édition standard est utilisée, il n’y a pas de différence entre le temps de traitement initial du cube et la durée de traitement du cube suivante, car chaque fois que les données sont actualisées, il sera toujours entièrement traité de toutes les données disponibles. (Cela signifie que le temps de traitement du cube augmente à mesure que le volume de données dans la base de données d’archive QoE augmente.) Dans la mesure où l’édition entreprise et l’édition Enterprise de SQL Server disposent d’une prise en charge de partitions, si l’une des éditions est utilisée, seule la première exécution traitera toutes les données de la base de données d’archive QoE. Dans les exécutions suivantes, lorsque la tâche est déclenchée toutes les 15 minutes, la tâche traite uniquement les nouveaux enregistrements ajoutés à la base de données d’archive QoE depuis la dernière exécution de la tâche. Une fois par jour, il y aura également un traitement complet sur la partition qui contient les données du mois actuel.
  
Les caractéristiques de l’ordinateur physique peuvent affecter les performances de bord ainsi que les fonctionnalités logicielles disponibles dans les composants SQL Server. Le composant d’archive QoE sera plus gourmand en ressources sur le disque par rapport aux autres composants, alors que le composant cube sera plus gourmand en ressources du processeur et de la mémoire. Chacun de ces facteurs contribue au temps total de traitement des données de bord, qui affecte directement la disponibilité et la disponibilité des données. Les organisations doivent prendre des décisions sur le matériel et les logiciels en fonction des besoins spécifiques de l’organisation. 
  
### <a name="tested-hardware-configurations"></a>Configurations matérielles testées

Cette section suppose qu’il existe une seule QoEMetrics DB dans l’environnement. 
  
**Profils d’ordinateur**

|**Postes**|**Cœurs d’UC**|**RAM**|**Archive QoE et cube sur le même disque**|**Archive QoE et BD SQL Temp sur le même disque**|
|:-----|:-----|:-----|:-----|:-----|
|Machine virtuelle  <br/> |4  <br/> |7 GO  <br/> |Oui  <br/> |Oui  <br/> |
|4 cœurs  <br/> |4  <br/> |20 GO  <br/> |Oui  <br/> |Non  <br/> |
|8 cœurs  <br/> |version8  <br/> |32 GO  <br/> |Oui  <br/> |Non  <br/> |
|16 cœurs  <br/> |Seiz  <br/> |128 GO  <br/> |Non  <br/> |Non  <br/> |
   
**Résultats de performance**

|**Postes**|**Taille de la BDD métrique de QoE**|**Partitions SQL**|**Type de disque**|**Nombre de flux**|**Processus d’archivage initial**|**Processus de cube initial**|**Processus d’archivage ultérieur**|**Processus de cube ultérieur**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Machine virtuelle  <br/> |900 MO  <br/> |Donné  <br/> |VHD (taille variable)  <br/> |0,5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Machine virtuelle  <br/> |9 GO  <br/> |Donné  <br/> |VHD (taille variable)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Machine virtuelle  <br/> |9 GO  <br/> |Donné  <br/> |VHD (taille fixe)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Machine virtuelle  <br/> |30 + GO  <br/> |Donné  <br/> |VHD (taille fixe)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 cœurs  <br/> |9 GO  <br/> |Donné  <br/> |Plusieurs disques  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 cœurs  <br/> |9 GO  <br/> |Multiples  <br/> |Plusieurs disques  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 cœurs  <br/> |30 + GO  <br/> |Donné  <br/> |Plusieurs disques  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 cœurs  <br/> |30 + GO  <br/> |Multiples  <br/> |Plusieurs disques  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 cœurs  <br/> |200 GO  <br/> |Donné  <br/> |Plusieurs disques  <br/> |125 M  <br/> |6 + jours  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 cœurs  <br/> |500 GO  <br/> |Multiples  <br/> |Plusieurs piles  <br/> |250 M  <br/> |8 jours  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Celles-ci ne sont pas censées être rencontrées dans de véritables déploiements, car la base de données de mesures de QoE doit avoir 9 et 18 mois de données, mais elles sont fournies ici pour l’exhaustivité.
  
### <a name="service-account-requirements"></a>Exigences relatives au compte de service

Vous aurez besoin d’un compte (avec accès en lecture à QoEMetrics) que l’agent SQL sur le serveur bord peut utiliser pour importer des données dans le QoEArchiveDB.
  
Vous devrez peut-être également configurer un compte distinct pour qu’une tâche SSAS récupère des données à partir de QoEArchiveDB (il s’agit d’un processus facultatif).
  
IIS utilise le plus souvent le service réseau en tant qu’identité du pool d’applications, mais peut être configuré sur un compte de service.
  
### <a name="portal-access-control"></a>Contrôle d’accès au portail

Par défaut, un utilisateur authentifié a accès. Ce problème peut être modifié à l’aide de règles d’autorisation IIS pour restreindre un groupe spécifique.
  
### <a name="pre-install-requirements"></a>Conditions préalables à l’installation

Ces instructions partent du principe qu’une base de données de métriques QoE a déjà été installée et qu’elle s’exécute dans la topologie de Skype entreprise Server.
  
#### <a name="hardware-requirements"></a>Configuration matérielle requise

BORD utilise Microsoft SQL Server, Microsoft SQL Analysis Server et Microsoft Internet Information Server de telle sorte que les exigences matérielles et logicielles de bord sont les mêmes que celles de ces composants dépendants. Toutefois, en fonction des besoins de l’organisation en matière de fraîcheur des données (qui dépendront en partie du volume de données QoE générées par l’entreprise) et du coût de déploiement, des considérations en matière de déploiement supplémentaires doivent être prises en compte.
  
#### <a name="software-requirements"></a>Configuration logicielle requise

Les systèmes d’exploitation suivants sont requis pour bord :
  
- Windows Server 2008 R2 avec IIS 7,5
    
- Windows Server 2012 avec IIS 8,0
    
- Windows Server 2012 R2 avec IIS 8,5

- Windows Server 2016 avec IIS 10,0 (Skype entreprise Server 2019 bord uniquement)

- Windows Server 2019 (Skype entreprise Server 2019 bord uniquement)
    
Vous trouverez ci-après les services de rôles IIS requis (dans l’ordre hiérarchique) :
  
- Serveur Web
    
  - Fonctionnalités HTTP communes
    
  - Contenu statique
    
  - Document par défaut
    
  - Développement d’applications
    
  - ASP.NET
    
  - Filtres ISAPI
    
  - Diagnostics d’intégrité &amp;
    
  - Journalisation HTTP
    
  - Sécurité
    
  - Autorisation d’URL
    
  - Authentification Windows
    
  - Outils de gestion
    
  - Console de gestion des services Internet (IIS)
    
> [!NOTE]
>  Remarque > : pour les exigences ci-dessus, les versions 3,5 et 4,5 du .NET Framework sont disponibles. Les deux sont obligatoires (plus précisément, 3,5 SP1 est requis). > dans certains systèmes, si ASP.NET est configuré avant l’installation d’IIS, ASP.NET risque de ne pas être enregistré dans IIS. Le problème se manifeste par l’absence de pools d’applications pour la version .net correspondante et de la version CLR .NET dans la configuration du pool d’applications. Pour résoudre ce problème sur Windows Server 2008 R2, exécutez `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`. Sur Windows Server 2012 et Windows Server 2012 R2, exécutez `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` suivi en supprimant le module « ServiceModel » du site Web par défaut dans le gestionnaire des services Internet (IIS). > outils de gestion est facultatif, mais il est recommandé.
  
Pour installer ces exigences via PowerShell, exécutez la commande suivante :
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Les versions suivantes de SQL Server sont prises en charge :
  
- SQL Server 2012
    
- SQL Server 2014

- SQL Server 2016

- SQL Server 2017

- SQL Server 2019 (Skype entreprise Server 2019 bord uniquement)
    
Business Intelligence ou Enterprise Edition est recommandé pour des raisons de performances. Ces éditions autorisent l’utilisation de plusieurs fichiers de partitions qui peuvent être traités en parallèle, ce qui est utile pour le traitement des données qui s’étalent sur plusieurs mois ou plus. 
  
Il n’est pas recommandé d’être pris en charge par Standard Edition. Le traitement sera limité à une seule partition (qui doit être configurée lors de l’installation). 
  
Dans tous les cas, « services du moteur de base de données » et « Analysis Services » doivent être installés. Nous vous conseillons de ne pas avoir besoin de l’installation de la fonctionnalité « outils de gestion-complète », qui ajoute la prise en charge de SQL Server Management Studio pour Analysis Services. L’écran de sélection de fonctionnalité doit ressembler à l’illustration.
  
![Configuration requise pour les fonctionnalités SQL Server](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Lorsque vous configurez le programme d’installation de SSAS dans le cadre de la configuration d’Analysis Services, définissez « mode serveur » sur « multidimensionnel et mode d’exploration de données ». 
  
Pour obtenir de l’aide supplémentaire sur l’installation et la configuration des fonctionnalités d’aide à la décision SQL Server, voir [installer Analysis Services en mode multidimensionnel et Data Mining](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Configuration requise pour le compte

Trois comptes de service de domaine sont recommandés selon le principe des privilèges minimum : 
  
- L’un d’eux comporte déjà un principal de sécurité de la connexion à la base de données de la base de données de niveau de service (avec les privilèges de db_datareader) et un principal de sécurité de connexion dans l’instance d’archive SQL Server QoE (nécessaire pour créer un objet de serveur lié lors de l’installation). Ce compte sera utilisé pour exécuter l’étape « données d’archive QoE » du travail de l’agent SQL Server.
    
- Il s’agit d’un outil qui sera utilisé pour exécuter l’étape « traiter le cube » du travail de l’agent SQL Server. Le programme d’installation crée un principal de sécurité de connexion dans la base de données d’archive QoE (avec privilèges de lecture et d’écriture) et crée également un membre du rôle QoE (avec le privilège contrôle total) pour le cube.
    
- L’un qui sera utilisé pour exécuter le processus de travail IIS pour les portails Web et les API Web. Le programme d’installation crée un principal de sécurité de connexion dans la base de données d’archive QoE (avec le privilège lecture), un principal de sécurité de connexion à la base de données du référentiel (avec les privilèges de lecture et d’écriture) et un membre de QoERole (avec le privilège contrôle total) pour le cube. 
    
    > [!NOTE]
    > Lorsque la base de données d’archive QoE et la base de données du référentiel sont hébergées sur le même serveur SQL Server, un seul principal de sécurité de connexion avec deux mappages utilisateur est créé. 
  
Les deux premiers comptes peuvent être considérés comme un « compte de service principal » et le dernier compte « compte de service frontal ». Bien qu’il soit déconseillé, il est possible d’utiliser un seul compte dans tous les cas.
  
> [!NOTE]
> Le compte d’utilisateur à l’origine de l’installation doit disposer d’un accès en lecture à la base de connaissance des métriques QoE également (en plus des droits d’administrateur d’ordinateur sur le serveur de base d’archive QoE sur lequel l’installation doit avoir lieu). 
  
## <a name="capacity-planning"></a>Planification de la capacité
<a name="Infrastructure_Req"> </a>

BORD est conçu pour un impact minimal sur QoEMetrics : le code a été optimisé pour ne pas verrouiller les données et les tâches d’importation sont ajustables.
  
Le type de matériel à utiliser dépend de vos exigences relatives à la manière dont les synchronisations rapides doivent s’exécuter. Le dimensionnement du disque est le suivant :
  
- QoEArchive est ~ 1,5 x plus grand que QoEMetrics DB au départ
    
- Le cube SSIS compresse les données en presque 10x par rapport à la base de données
    
- Les données sont partitionnées par mois ; les partitions peuvent être supprimées
    

