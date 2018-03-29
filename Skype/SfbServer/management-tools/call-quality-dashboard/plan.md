---
title: Planifier pour le tableau de bord qualité appel Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/27/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Résumé : Apprenez à prendre en compte lorsque vous planifiez pour appeler le tableau de bord qualité.'
ms.openlocfilehash: 25438b759e367d70df6ae09b7d4a5cc093dc1e7a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server-2015"></a>Planifier pour le tableau de bord qualité appel Skype pour Business Server 2015
 
**Résumé :** Obtenir des informations sur les éléments à prendre en compte lorsque vous planifiez pour appeler le tableau de bord qualité.
  
## <a name="overview-of-the-skype-for-business-server-2015-call-quality-dashboard"></a>Vue d’ensemble de la Skype pour tableau de bord qualité Business Server 2015 appel

Le Skype pour Business Server 2015 appeler qualité du tableau de bord (CQD) est une couche de création de rapports sur la qualité d’expérience de base de données dans le serveur de surveillance dans Skype pour Business Server 2015 et Lync Server 2013. CQD utilise Microsoft SQL Server Analysis Services pour fournir l’utilisation cumulée et d’appeler des informations de qualité ainsi que pour le filtrage et le glissement dans le groupe de données. Fonctionnalités CQD :
  
- **Solution d’archivage de données QoE via le composant QoE Archive de CQD.** Le composant QoE Archive peut stocker des données de QoE beaucoup plus longtemps que ceux Monitoring Server. Cela permet d’établir des tendances et de reporting pour jusqu'à sept mois de données à la fois, avec la possibilité de déplacer la fenêtre de reporting autant back que de données.
    
- **Reporting et analyse à l’aide de la puissance et la vitesse de Microsoft SQL Server Analysis Services.** CQD utilise Microsoft SQL Analysis Services pour fournir une synthèse rapide, filtre et glissement des fonctionnalités pour alimenter le tableau de bord via un Cube d’analyse. La vitesse d’exécution et la possibilité de consulter les données de création de rapports peut réduire les temps d’analyse considérablement.
    
- **Nouveau schéma de données optimisé pour les rapports de qualité appel.** Le Cube possède un schéma conçu pour le rapport sur la qualité vocale et des enquêtes. Les utilisateurs du portail peuvent se concentrer sur les tâches de création de rapports au lieu d’essayer de comprendre comment les métriques QoE de base de données des mappages de schéma pour les vues dont ils ont besoin. La combinaison de le QoE Archive et le Cube fournit une abstraction qui réduit la complexité de reporting et d’analyse via CQD. Le schéma de base de données Archive de QoE contient également les tables qui peuvent être remplis avec des données spécifiques au déploiement afin d’améliorer la valeur globale des données.
    
- **Concepteur de rapport intégré et la modification de l’état de place.** Le composant de portail est livré avec plusieurs rapports intégrés modélisées d’après la méthode appeler de qualité. Les utilisateurs du portail peuvent modifier les rapports et créer des rapports via la fonctionnalité d’édition du portail.
    
- **API Web l’accès à la Structure de rapports et analyse des données du Cube.** Le cadre du tableau de bord n’est pas la seule manière d’afficher les données du cube. CQD fournit plusieurs exemples d’utilisation de codes HTML et JavaScript pour récupérer des données à partir de l’API Web CQD et restituer les données dans un format personnalisé. La combinaison de l’éditeur de rapport et les API de Web CQD permet de prototypage rapide de rapports et de mise en page de rapport personnalisé.
    
## <a name="cqd-design-goals"></a>Objectifs de Design CQD

Le Tableau de bord de la qualité des appels permet aux professionnels de l’informatique d’utiliser des données agrégées pour identifier des secteurs cibles dans leur environnement rencontrant des problèmes de qualité multimédia. Il permet à un professionnel de l’informatique de comparer des statistiques de différents groupes d’utilisateurs et d’identifier des tendances et modèles. Le tableau n’est pas utilisé pour résoudre des problèmes d’appel spécifiques, mais pour identifier les problèmes et les solutions qui concernent de nombreux utilisateurs dans un environnement donné. 
  
## <a name="call-quality-dashboard-components"></a>Appeler des composants de tableau de bord qualité

Le tableau de bord qualité appeler se compose de plusieurs bases de données, Microsoft SQL Agent les tâches, les processus et les applications web. Les travaux de l’Agent SQL de Microsoft copier périodiquement des données à partir de la base de données QoE métriques dans la base de données Archive de QoE et des processus du Cube avec les données dans la base de données Archive de QoE. La base de données de référentiel stocke les définitions de rapport que le portail d’alimentation. Le portail fournit un accès par navigateur aux données du Cube. 
  
Les composants CQD, y compris les bases de données QoE Archive, de Cube et de référentiel peuvent être installés sur le serveur de surveillance, installés sur son propre serveur ou installés sur plusieurs serveurs. Les exigences de performance de CQD ainsi que d’autres processus sur les mêmes serveurs dépend de la méthode d’installation particulier. Pour plus d’informations, reportez-vous à la section « Composants et les topologies pour CQD » plus loin dans cet article.
  
### <a name="architectural-overview"></a>Présentation de l’architecture

Pour résumer, CQD requiert les éléments suivants :
  
- Deux bases de données : une base de données de l’Archive et d’une base de données de référentiel.
    
- Une visualisation de SSAS Cube de données agrégées 
    
- IIS héberge le portail Web de CQD
    
![Composants CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
La même architecture CQD prend en charge Lync Server 2013 et Skype pour les entreprises. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD et Skype pour entreprise et Lync 2013

 Dans un Skype pour entreprises uniquement, les fonctionnalités suivantes sont disponibles :
  
- Génération d’états d’intensité du Signal Wi-Fi
    
- Génération d’états de pilotes Wi-Fi
    
- Taux de mes données d’appel 
    
## <a name="information-available-through-cqd"></a>Informations disponibles par l’intermédiaire de CQD

CQD pouvez afficher Skype pour Business Server audio, vidéo et nombre de flux de données et le nombre de bonnes par rapport aux appels incorrects ainsi que des rapports des appels incorrects à la bonne de partage d’application. Les vues peuvent être découpés en tranches et filtrés par le nombre de dimensions différente. CQD extrait les données à partir de la base de données serveur de surveillance QoE métriques. Les données sont ensuite fusionnées avec toutes les données fournies par le client, telles que le mappage de sous-réseau-création de réseau pour permettre le rapports tels que « Appel de qualité par construction ». 
  
CQD extrait également nombreuses idiosyncrasies données QoE internes tels que « » et le « appelant » telle que l’utilisateur puisse se concentrer sur la création d’affichages d’état autour de « serveur » et « client ». À la suite de la méthodologie de qualité appeler, CQD est rationalisé pour permettre d’identifier les conditions qui ont des poches d’appels médiocres en commun, un des principes de l’amélioration de la qualité de l’appel.
  
## <a name="viewing-data-in-cqd"></a>Affichage des données de CQD

Les données CQD peuvent être affichées via le portail de CQD et accessible via des appels de l’API REST.
  
### <a name="cqd-portal"></a>Portail CQD

Le portail est le moyen le plus rapide pour afficher les données dans le Cube. Le portail est livré avec plusieurs rapports prédéfinis qui sont utilisables immédiatement. Les rapports intégrés sont liés de manière structurée pour guider l’utilisateur à successivement les plus petits secteurs des données de l’appel. Les rapports intégrés, également en surbrillance les façons différentes, que les données peuvent être affichées en montrant une combinaison de graphiques et des tableaux avec des pivots différents, des filtres et des mesures. Chaque utilisateur qui accède au portail peut avoir son propre ensemble de rapports il peut modifier et les partager. Pour plus d’informations sur l’utilisation du portail Web CQD, reportez-vous à la section [Utilisation appeler tableau de bord qualité pour Skype pour Business Server 2015](use.md).
  
Prise en charge des systèmes d’exploitation pour CQD Portal : Windows 8.1, Windows 8, Windows Server 2012 R2 et Windows Server 2012.
  
Navigateurs pris en charge pour CQD Portal : Internet Explorer 9, Internet Explorer 10 et 11 de Internet Explorer.
  
### <a name="rest-apis"></a>AUTRES API

Les données du Cube sont également accessibles via des appels de l’API REST. Les données récupérées via les appels de l’API REST peuvent être restituées par le biais des pages HTML. Les utilisateurs peuvent tirer parti de la vitesse de requête et le schéma de haut niveau de CQD pendant encore créer des rapports personnalisés adapté à leurs besoins. Pour plus d’informations sur l’API et des exemples, consultez [Développement d’appeler tableau de bord qualité pour Skype pour Business Server 2015](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Définition des exigences de votre organisation pour CQD

CQD fournit une analyse de l’archivage et rapide et approfondie de données de données d’appel de qualité QoE. Le guide suivant vous aide à décider quand et pourquoi vous devez déployer CQD.
  
### <a name="when-to-deploy-cqd"></a>Quand déployer CQD

 **CQD peut être déployé pour établir une mesure de qualité appel de référence, même si une organisation ne rencontrez des problèmes de qualité d’appel.** Établissement d’une mesure de qualité d’appel planifié est important parce que chaque organisation possède une autre combinaison de Wi-Fi et filaire et à distance et des employés de bureau. En cas de problèmes de qualité d’appel, les mesures de qualité d’appel la plus récentes peuvent être comparées à des intervalles de temps précédente. Fonctionnalités de tendances de CQD permettent de faciliter la détection des modifications dans la qualité des appels au fil du temps.
  
 **CQD peut être déployé pour identifier de manière proactive les zones de problèmes qui peuvent avoir un impact sur qualité des appels.** Même si l’appel de la moyenne qualité d’une organisation peut-être répondre aux cibles définies par l’organisation, il peut y avoir des poches de problèmes de qualité d’appel qui sont cachées derrière les mesures de moyennes. CQD permet la répartition de sous forme de tableau croisé dynamique des métriques de qualité d’appel par le nombre de dimensions dans la base de données QoEMetrics. Détection des valeurs aberrantes dans groupes d’homologues est un moyen rapide de localiser proactivement les problèmes de qualité d’appel.
  
 **CQD doit être déployé, s’il y a appel de problèmes de qualité de l’organisation afin de réduire le temps nécessaire pour résoudre les problèmes.** CQD peut simplifier les enquêtes de qualité appel existant en proposant le rapports rapide des performances et des fonctionnalités de zoom dynamique. CQD est conçu pour de nombreux types de flux de travail dans l’appel de qualité enquêtes validation des réparations à l’environnement.
  
### <a name="why-deploy-cqd"></a>Pourquoi déployer CQD

 **CQD doit être déployé si QoE reporting doit se produire plus de 3 mois de données.** La base de données QoEMetrics et l’analyse des rapports de serveur sont conçus pour conserver et signaler un petit ensemble de données. La base de données QoE métrique est optimisé pour les insertions rapides, et par conséquent les performances de rapport peut être entravé par gros volume d’appels concurrent rapport accès ou à la base de données. Base de données de CQD QoE Archive fournit une seconde copie des données QoE métriques avec des capacités de rétention beaucoup plus de temps. Le portail est également optimisé pour afficher jusqu'à 7 mois de données à la fois et peut signaler toutes les données dans le QoE Archive selon vos besoins.
  
 **CQD doit être déployé si les rapports QoE personnalisés sont nécessaires.** Le portail a une fonctionnalité d’éditeur de rapport pour les rapports de prototypage et de créer rapidement et facilement. En outre, les API reste disponible pour la programmation aux données du Cube, permettant une présentation personnalisée à l’aide de HTML/JavaScript ou nombreuses autres infrastructures. Il n’est plus nécessaire créer de nouvelles requêtes SQL afin de créer des vues de données personnalisées pour le reporting.
  
 **CQD doit être déployé si QoE existant, la fonctionnalité de création de rapports ne répond pas à la vitesse ou la profondeur requise par l’organisation.** CQD est livré avec de nombreux rapports prédéfinis. Les rapports sont utiles immédiatement et montrez comment progressivement dans les données de perçage peut offrir des éclaircissements à chaque niveau. Également, la hiérarchie de rapports aide à la gestion de nombreux rapports de manière logique et encourage la création de nombreux rapports plus facilement accessibles et compréhensibles. CQD n’offre pas seulement la vitesse et la flexibilité, mais est en outre optimisé pour les workflows de développé par la méthodologie de qualité appeler.
  
## <a name="components-and-topologies-for-cqd"></a>Les composants et les topologies pour CQD

CQD est fourni avec plusieurs composants, et il est utile de comprendre les besoins de chaque composant et leurs relations entre eux pour obtenir le plus simple et mieux réaliser le déploiement de l’outil. Le tableau suivant décrit le composant dépendant pour chaque composant CQD.
  

|**Nom du composant**|**Composant dépendant**|
|:-----|:-----|
|QoE Archive  <br/> |Microsoft SQL Server  <br/> |
|Cube  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portail  <br/> |Services d’informations de Microsoft  <br/> |
|Services de référentiel (partie de l’installation du portail)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> QoE Archive et du Cube, certaines options de déploiement nécessitent des éditions entreprise ou Business Intelligence de Microsoft SQL Server. Reportez-vous à la section [exigences d’Infrastructure pour CQD](plan.md#Infrastructure_Req) ci-dessous pour plus de détails.
  
![Composants CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configuration de serveur unique

Tous les composants CQD et dépendant peut être installé sur un ordinateur. La configuration de zone unique est la configuration la plus simple et CQD à être autonomes. CQD devez uniquement accès à la base de données QoE métriques sur le serveur d’analyse. Le serveur de CQD peut être un ordinateur autonome, une machine virtuelle, ou il peut même être le serveur de surveillance, selon les ressources disponibles de la machine hôte et des exigences de performances. 
  
Pendant l’installation, l’utilisateur effectuant que l’installation doit simplement fournir le Microsoft SQL Server et les instances de Microsoft SQL Server Analysis Services qui ont été définies sur l’ordinateur où le CQD doit être installé. Pour plus d’informations, reportez-vous à [Déployer appeler tableau de bord qualité pour Skype pour Business Server 2015](deploy-0.md) .
  
### <a name="multiserver-configuration"></a>Configuration multiserveurs

Dans une configuration multiserveur, le QoE, Cube et archivage Portal peuvent tous être sur des ordinateurs différents. Il existe deux utilisations principales de la configuration multiserver :
  
- Hébergement de portail Web de CQD et de CQD Cube sur différents serveurs.
    
- Hébergement d’un portail séparé à partir de la « production » Portal « développement ». 
    
 **Hébergement de portail Web de CQD et de CQD Cube sur des ordinateurs différents.** Les organisations qui peuvent avoir des exigences pour séparer le portail de CQD de l’installation de SQL Server ou que pouvez mélanger et assortir des éditions de SQL Server pour l’instance de SQL Server et une instance de SQL Server Analysis Services peuvent choisir d’installer le portail de CQD et Cube de CQD sur des ordinateurs différents. Le composant QoE Archive peut également être le seul composant CQD qui est installé si l’organisation souhaite simplement disposer d’une méthode durable à archiver sans atteindre les limites de performances sur le serveur de surveillance QoE.
  
![CQD mono-serveur](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hébergement d’un portail séparé à partir de la « production » Portal « développement ».** Les organisations qui développent leurs propres rapports (via les API reste) préfèrent déployer des instances supplémentaires de portail de (CQD) avec la portail qui accèdent à des utilisateurs réguliers d’enquêtes ou d’appel de surveillance de la qualité de la production. Le portail de développement permet d’isoler les modifications sur le portail à partir de l’environnement de production. Les portails web supplémentaires peuvent être déployées sur des ordinateurs différents (voir ci-dessous) ou déployées sur les répertoires web différent sur la même machine (non illustré). Pour faire de ce dernier, le portail web CQD supplémentaire doit être copié sur l’ordinateur de production manuellement, car le processus d’installation CQD déploie toujours le portail Web de CQD pour le site web par défaut avec des noms d’application web prédéfinies.
  
![Planification de multi-serveur CQD](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologies prises en charge

CQD ne fusionne pas les données provenant de plusieurs bases de données QoEMetrics, comme dans le cas où il existe plusieurs Skype pour les topologies de serveur d’entreprise, chacune avec son propre serveur de surveillance. Chaque instance CQD doit pointer vers une base de données QoEMetrics. Toutefois, car CQD se déplace de la charge de travail de création de rapports sur le serveur de surveillance, grandes organisations qui doivent déployer un serveur de surveillance par Skype pour la topologie du serveur de l’entreprise doivent prendre en compte à l’aide d’un serveur d’analyse pour toutes les topologies.
  
## <a name="infrastructure-requirements-for-cqd"></a>Exigences de l’infrastructure pour CQD
<a name="Infrastructure_Req"> </a>

CQD, y compris tous ses composants et composants dépendants, peut être déployé sur une machine virtuelle, un seul ordinateur, ou sur plusieurs ordinateurs. La configuration matérielle et logicielle minimale requise est répertoriée ci-dessous. Disponibilité des données et requête de performances peuvent varier de quelques minutes à quelques heures, en fonction du nombre de Skype active pour les utilisateurs du serveur de l’entreprise et de matériel et de configuration, certaines mesures de performances sont indiquées ci-dessous.
  
|||
|:-----|:-----|
|Systèmes d’exploitation pris en charge  <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|Prise en charge de SQL Server  <br/> |SQL Server 2008 R2, SQL Server 2012, SQL Server 2014  <br/> |
   
CQD utilise Microsoft SQL Server, Microsoft SQL Server Analysis Services et Microsoft Internet Information Services afin de CQD minimale logicielle et matérielle requise est les mêmes que les composants dépendants. Toutefois, selon les besoins de l’organisation autour d’actualisation des données (qui dépend en partie du volume de données QoE que génère de l’organisation) et les coûts de déploiement, les considérations de déploiement supplémentaires convient.
  
Traitement des données dans CQD est divisée en deux étapes principales : 
  
- Processus d’archivage de QoE
    
- Traitement du Cube de CQD
    
 **QoE Archive de traitement.** La tâche de traitement QoE Archive copie les données à partir de la base de données QoE métriques sur le serveur de surveillance de la base de données Archive de QoE. Il existe deux situations où le temps de traitement de la tâche aurait des caractéristiques de performances fondamentalement différentes. La première est après l’installation initiale de CQD. Lorsque la tâche est exécutée pour la première fois après une nouvelle installation, la tâche de traitement QoE Archive copie toutes les données qui se trouve dans la base de données QoE métriques dans la base de données Archive de QoE. Le second est le traitement périodique après cette phase initiale. Le QoE Archive tâche de traitement exécute toutes les 15 minutes et traiter les nouveaux enregistrements QoE qui se trouvent dans la base de données de mesure métrique. En règle générale, le temps de traitement initial n’est pas un problème parce qu’il est exécuté uniquement la première fois, lors de l’installation CQD. Toutefois, si le serveur CQD est sérieusement dans-mis en service, cette tâche peut prendre plusieurs heures. Reportez-vous au tableau ci-dessous par exemple initiale QoE d’Archive du délai de traitement.
  
 **Traitement du Cube de CQD.** La tâche de traitement de Cube regroupe les données à partir de la base de données Archive de mesure dans le Cube. Le temps de traitement initial et un temps de traitement de cube suivantes sont déterminées par l’édition de SQL Server Analysis Services utilisée pour le Cube CQD. Si l’Édition Standard est utilisée, il n’y a aucune différence entre le temps de traitement initial et le cube suivant, le temps de traitement, car chaque fois que les données du Cube sont actualisées, il sera toujours un traitement complet de toutes les données disponibles. (Cela signifie que le temps de traitement de Cube augmente à mesure que de la quantité de données dans le QoE Archive augmente de la base de données). Parce que la Business Intelligence Edition et Enterprise Edition de SQL Server ont partition prend en charge, si l’édition n’est utilisée, seulement l’exécution initiale traite toutes les données de la base de données Archive de QoE. Dans les exécutions suivantes, lorsque la tâche se déclenche toutes les 15 minutes, la tâche traitera uniquement les nouveaux enregistrements ajoutés à la base de données Archive de QoE depuis la dernière exécution de la tâche. Une fois par jour, il y aura également un traitement complet sur la partition qui contient les données du mois en cours.
  
Les caractéristiques de la machine physique peuvent affecter les performances de CQD, ainsi que les fonctionnalités du logiciel qui sont disponibles à partir des composants de SQL Server. Le composant QoE Archive sera beaucoup plus de disques par rapport à d’autres composants, alors que le composant de Cube sera plus de processeur et de mémoire. Tous ces facteurs contribuent à temps de traitement total des données de CQD, qui affecte directement la disponibilité et l’actualisation des données. Les organisations doivent prendre des décisions sur le matériel et les logiciels en se basant sur les besoins de l’organisation. 
  
### <a name="tested-hardware-configurations"></a>Configurations matérielles testées

Cette section part de l’hypothèse qu’il existe une seule base de données QoEMetrics dans l’environnement. 
  
**Profils d’ordinateur**

|**Machine**|**Coeurs de processeur**|**MÉMOIRE VIVE**|**QoE Archive et Cube sur le même disque**|**QoE Archive et base de données SQL Temp sur le même disque**|
|:-----|:-----|:-----|:-----|:-----|
|Mmachine virtuel  <br/> |4  <br/> |7 GO  <br/> |Oui  <br/> |Oui  <br/> |
|Ccore 4  <br/> |4  <br/> |20 GO  <br/> |Oui  <br/> |Non  <br/> |
|base 8  <br/> |8  <br/> |32 GO  <br/> |Oui  <br/> |Non  <br/> |
|base 16  <br/> |16  <br/> |128 GO  <br/> |Non  <br/> |Non  <br/> |
   
**Résultats des performances**

|**Machine**|**Taille de la base de données les mesures QoE**|**Partitions SQL**|**Type de disque**|**Nombre de flux**|**Processus d’archivage initial**|**Processus initial de Cube**|**Les processus d’archivage**|**Les processus de Cube**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Machine virtuelle  <br/> |900 MO  <br/> |Unique  <br/> |Disque dur virtuel (taille variable)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Machine virtuelle  <br/> |9 GO  <br/> |Unique  <br/> |Disque dur virtuel (taille variable)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Machine virtuelle  <br/> |9 GO  <br/> |Unique  <br/> |Disque dur virtuel (chasse fixe)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Machine virtuelle  <br/> |+ DE 30 GO  <br/> |Unique  <br/> |Disque dur virtuel (chasse fixe)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|base 8  <br/> |9 GO  <br/> |Unique  <br/> |Plusieurs disques  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|base 8  <br/> |9 GO  <br/> |Plusieurs  <br/> |Plusieurs disques  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|base 8  <br/> |+ DE 30 GO  <br/> |Unique  <br/> |Plusieurs disques  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|base 8  <br/> |+ DE 30 GO  <br/> |Plusieurs  <br/> |Plusieurs disques  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|base 4  <br/> |200 GO  <br/> |Unique  <br/> |Plusieurs disques  <br/> |125 M  <br/> |+ de 6 jours  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|base 16  <br/> |500 GO  <br/> |Plusieurs  <br/> |Plusieurs piles  <br/> |250 M  <br/> |8 jours  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Elles ne devraient pas être rencontrées dans les déploiements réels, car la base de données QoE mesures aurait besoin de respectivement 9 et 18 mois de données, mais elles sont fournies ici par souci d’exhaustivité.
  
### <a name="service-account-requirements"></a>Exigences de compte de service

Vous aurez besoin d’un compte que l’Agent SQL sur le serveur de CQD pouvez utiliser pour importer des données à la QoEArchiveDB (accès en lecture au QoEMetrics).
  
Vous devez également configurer un compte distinct pour une tâche SSAS pour extraire des données à partir de QoEArchiveDB (c’est un processus facultatif).
  
IIS utilise le Service réseau comme identité du Pool d’application plus fréquemment, mais peut être configuré pour un compte de Service.
  
### <a name="portal-access-control"></a>Contrôle d’accès au portail

Par défaut, tout utilisateur authentifié a accès. Cela peut être modifié à l’aide de règles d’autorisation de IIS pour limiter à un groupe spécifique.
  
### <a name="pre-install-requirements"></a>Conditions préalables à l’installation

Ces instructions supposent qu’une base de données QoE mesures a déjà été installé et est en cours d’exécution quelque part dans le Skype pour la topologie du serveur de l’entreprise.
  
#### <a name="hardware-requirements"></a>Configuration matérielle requise

CQD utilise Microsoft SQL Server, Microsoft SQL Analysis Server et Microsoft Internet Information Server afin de CQD minimale logicielle et matérielle requise est les mêmes que les composants dépendants. Toutefois, selon les besoins de l’organisation autour d’actualisation des données (qui dépend en partie du volume de données QoE que génère de l’organisation) et les coûts de déploiement, les considérations de déploiement supplémentaires convient.
  
#### <a name="software-requirements"></a>Configuration logicielle requise

Les systèmes d’exploitation suivants sont requis pour CQD :
  
- Windows Server 2008 R2 avec IIS 7.5
    
- Windows Server 2012 avec IIS 8.0
    
- Windows Server 2012 R2 avec IIS 8.5
    
Voici les services de rôle IIS requis (dans l’ordre hiérarchique) :
  
- Serveur Web
    
  - Fonctionnalités HTTP communes
    
  - Contenu statique
    
  - Document par défaut
    
  - Développement d’applications
    
  - ASP.NET
    
  - Filtres ISAPI
    
  - Santé &amp; Diagnostics
    
  - Journalisation HTTP
    
  - Sécurité
    
  - L’autorisation d’URL
    
  - Authentification Windows
    
  - Outils de gestion
    
  - Console de gestion des services Internet (IIS)
    
> [!NOTE]
>  Notez les informations suivantes pour les conditions ci-dessus : > 3.5 et les versions du .net framework 4.5 sont disponibles. Les deux sont requis (plus précisément, 3.5 SP1 est requis). > dans certains systèmes, si ASP.NET est configuré avant l’installation, IIS, ASP.NET ne peut pas être enregistré dans IIS. Le problème se manifeste par l’absence de pools d’applications pour la version correspondante de .net et pas la version du CLR .NET dans la configuration du pool d’application. Pour corriger ce problème dans Windows Server 2008 R2, vous devez exécuter `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`. Sur Windows Server 2012 et Windows Server 2012 R2, exécutez `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` suivie de la suppression du module « ServiceModel » à partir du Site Web par défaut dans IIS Manager. > Outils de gestion est facultative, mais recommandée.
  
Pour installer ces spécifications à l’aide de PowerShell, exécutez la commande suivante :
  
```
import-module servermanager
```

```
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Les versions suivantes de SQL Server sont pris en charge :
  
- SQL Server 2008 R2
    
- SQL Server 2012
    
- SQL Server 2014
    
Intelligence d’entreprise ou l’édition entreprise est recommandée pour des raisons de performances. Ces éditions autorisent l’utilisation de plusieurs fichiers de la partition qui peuvent être traitées en parallèle, ce qui est utile pour le traitement des données réparties sur plusieurs mois ou plus. 
  
Bien que non recommandé, Édition Standard est également pris en charge. Traitement va être limité à une seule partition (qui doit être configuré lors de l’installation). 
  
Dans tous les cas, les « Services du moteur de base de données » et « Analysis Services » doivent être installés. Il est recommandé mais pas obligatoire d’installer également la fonctionnalité « Outils de gestion - fin », ce qui ajoute la prise en charge de SQL Server Management Studio pour Analysis Services. Écran de sélection de fonctionnalité doit ressembler à la figure.
  
![Configuration requise pour les fonctionnalités SQL Server](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Lorsque vous configurez l’installation SSAS, dans la Configuration d’Analysis Services, la valeur « Mode serveur », « Multidimensionnelle et données Mining en mode ». 
  
Pour plus d’informations dans l’installation et la configuration des fonctionnalités d’analyse décisionnelle SQL Server, voir [Installation de Analysis Services dans multidimensionnel et Mode d’exploration de données](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Configuration requise du compte

Sur le principe du moindre privilège, trois comptes de service de domaine sont recommandés : 
  
- Une qui dispose déjà d’une entité de sécurité de connexion de base de données QoE métriques (avec les privilèges db_datareader) et une entité de sécurité de connexion dans QoE Archive SQL Server Instance (nécessaire pour créer un objet de serveur lié lors de l’installation). Ce compte sera utilisé pour exécuter l’étape « Archive les données QoE » de la tâche de l’Agent de SQL Server.
    
- Celui qui sera utilisé pour exécuter l’étape « Traiter le Cube » de la tâche de l’Agent de SQL Server. Le programme d’installation crée une connexion d’accès à la base de données Archive de QoE entité de sécurité (avec lecture et d’écriture des privilèges) et également créer un membre du rôle QoE (avec des privilèges de contrôle total) pour le Cube.
    
- Celui qui sera utilisé pour exécuter des processus de travail IIS pour les portails web et web API. Le programme d’installation créera une connexion entité de sécurité de base de données Archive de QoE (avec le privilège de lecture), une entité de sécurité de connexion à la base de données de référentiel (avec lecture et écriture) et un membre de la QoERole (avec des privilèges de contrôle total) pour le Cube. 
    
    > [!NOTE]
    > Lorsque la base de données Archive de QoE et de base de données de référentiel sont hébergés dans le même SQL Server, qu’une sécurité de connexion principale avec deux mappages utilisateur est créée. 
  
Les deux premiers comptes peuvent être logiquement considérés comme « comptes de services back-end », et le dernier compte est un « compte de service de front-end ». Bien que non recommandé, il est possible d’utiliser un seul compte dans tous les cas.
  
> [!NOTE]
> Le compte d’utilisateur lançant l’installation doit accéder en lecture à QoE métriques DB ainsi (en plus des droits d’administrateur de machine sur le serveur de base de données Archive QoE où l’installation doit avoir lieu). 
  
## <a name="capacity-planning"></a>Planification de la capacité
<a name="Infrastructure_Req"> </a>

CQD est conçu pour minimiser l’Impact sur les QoEMetrics : le code a été optimisé pour ne verrouille ne pas les données et les tâches d’importation sont réglables.
  
Le type de matériel à utiliser dépend de vos besoins en matière de rapidité synchronisations doivent s’exécuter. Dimensionnement d’un disque est la suivante :
  
- QoEArchive est plus grande que la base de données QoEMetrics de ~1.5x au départ
    
- Cube de SSIS compresse les données presque 10 x par rapport à la base de données
    
- Partition des données mensuelles ; les partitions peuvent être supprimées.
    

