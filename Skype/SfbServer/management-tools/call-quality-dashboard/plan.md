---
title: Planifier pour le tableau de bord qualité appel Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Résumé : Découvrez les éléments à prendre en compte lorsque vous planifiez le tableau de bord qualité des appels.'
ms.openlocfilehash: ee82d56747ee4f4241f2630a5a6fd3136ff42be4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884420"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Planifier pour le tableau de bord qualité appel Skype pour Business Server 
 
**Résumé :** Découvrez les éléments à prendre en compte lorsque vous planifiez le tableau de bord qualité des appels.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Vue d’ensemble de la Skype pour le tableau de bord qualité Business Server appel

Le Skype pour le module Business Server appeler qualité du tableau de bord (CQD) est une couche de création de rapports sur la qualité de l’expérience de base de données dans le serveur de surveillance dans Skype pour Business Server. CQD utilise Microsoft SQL Server Analysis Services pour fournir l’utilisation d’agrégat et informations sur la qualité ainsi que pour le filtrage et pivotant sur le jeu de données d’appel. Fonctionnalités CQD sont les suivantes :
  
- **Archivage des données de QoE via le composant QoE Archive de CQD.** Le composant QoE Archive peut stocker les données QoE beaucoup plus longtemps que le serveur de surveillance peut. Ainsi, pour l’analyse des tendances et création de rapports pour jusqu'à sept mois de données à la fois, avec la possibilité de la fenêtre de création de rapports autant back que la diapositive donnée.
    
- **Création de rapports et d’analyse à l’aide de la puissance et la vitesse de Microsoft SQL Server Analysis Services.** CQD utilise Microsoft SQL Analysis Services pour fournir résumé rapide, filtrer et glissement des fonctionnalités d’alimenter le tableau de bord par le biais d’un Cube Analysis. Vitesse d’exécution et la possibilité de consulter les données de création de rapports peut réduire les temps d’analyse considérablement.
    
- **Nouveau schéma de données optimisé pour les rapports de qualité des appels.** Le Cube possède un schéma conçu pour les rapports de qualité vocale et d’enquêtes. Les utilisateurs du portail peuvent se concentrer sur les tâches de création de rapports au lieu d’essayer de comprendre comment les mesures QoE de base de données des mappages de schéma pour les affichages dont ils ont besoin. La combinaison de le QoE Archive et le Cube fournit une abstraction qui simplifie la création de rapports et analyses via CQD. Le schéma de base de données QoE Archive contient également des tables qui peuvent être remplis avec des données spécifiques au déploiement pour améliorer la valeur globale des données.
    
- **Concepteur de rapports intégrées et de modification de l’état sur place.** Le composant de portail est livré avec plusieurs rapports intégrés basé sur la méthodologie de qualité des appels. Les utilisateurs du portail peuvent modifier les rapports et créer des rapports par le biais de la fonctionnalité d’édition du portail.
    
- **Accès Web API à la Structure de rapports et analyse les données de Cube.** L’infrastructure de création de rapports de tableau de bord n’est pas le seul moyen pour afficher les données du cube. CQD fournit plusieurs exemples d’utilisation de code HTML et JavaScript pour récupérer des données à partir de l’API Web CQD et afficher les données dans un format personnalisé. La combinaison de l’éditeur de rapport et de l’API Web CQD permet de prototypage de rapports et de mise en page de rapport personnalisé.
    
## <a name="cqd-design-goals"></a>Objectifs de conception CQD

Le Tableau de bord de la qualité des appels permet aux professionnels de l’informatique d’utiliser des données agrégées pour identifier des secteurs cibles dans leur environnement rencontrant des problèmes de qualité multimédia. Il permet à un professionnel de l’informatique de comparer des statistiques de différents groupes d’utilisateurs et d’identifier des tendances et modèles. Le tableau n’est pas utilisé pour résoudre des problèmes d’appel spécifiques, mais pour identifier les problèmes et les solutions qui concernent de nombreux utilisateurs dans un environnement donné. 
  
## <a name="call-quality-dashboard-components"></a>Composants du tableau de bord qualité des appels

Le tableau de bord qualité des appels se compose de plusieurs bases de données, Microsoft SQL Agent travaux, des processus et des applications web. Les travaux de l’Agent Microsoft SQL copier régulièrement des données à partir de la base de données des mesures QoE dans la base de données QoE Archive et les processus du Cube avec les données de la base de données QoE Archive. La base de données de référentiel stocke les définitions de rapport que le portail d’alimentation. Le portail fournit l’accès navigateur pour les données du Cube. 
  
Les composants CQD, y compris les bases de données de référentiel, Cube et QoE archivage peuvent être installés sur le serveur de surveillance, installés sur son propre serveur ou installés sur plusieurs serveurs. Les exigences de performances de CQD ainsi que l’impact à d’autres processus sur les mêmes serveurs dépend de la méthode d’installation particulière. Pour plus d’informations, reportez-vous à la section « Composants et topologies pour CQD » plus loin dans cet article.
  
### <a name="architectural-overview"></a>Présentation de l’architecture

Pour résumer, CQD nécessite les éléments suivants :
  
- Deux bases de données : une base de données d’archivage et d’une base de données de référentiel.
    
- Visualisation d’un Cube SSAS données agrégées 
    
- IIS héberge le portail Web : CQD
    
![Composants CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
La même architecture CQD prend en charge Lync Server 2013 et Skype pour les entreprises. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD et Skype pour professionnels et Lync 2013

 Dans un Skype pour un environnement d’entreprise, les fonctionnalités suivantes sont disponibles :
  
- Création de rapports Wi-Fi de puissance du Signal
    
- Création de rapports Wi-Fi de pilotes
    
- Taux de mes données d’appel 
    
## <a name="information-available-through-cqd"></a>Informations disponibles par le biais de CQD

CQD peut afficher Skype pour Business Server audio, vidéo et le nombre de flux et le nombre de bonne par rapport à des appels incorrectes ainsi que des rapports des appels incorrects pour une bonne de partage d’application. Les affichages peuvent être découpés et filtrés par le nombre de dimensions différente. CQD extrait les données à partir de la base de données mesures QoE Monitoring Server. Les données sont ensuite fusionnées avec toutes les données fournies par le client, telles que le mappage du sous-réseau-création de réseau pour faire des rapports, tels que « Appel qualité par Building ». 
  
CQD nombreux les caractéristiques de données QoE internes tel que « appelant » et « appelé » extrait également afin que l’utilisateur puisse se concentrer sur la création d’affichages de rapport autour de « serveur » et « client ». La suite de la méthodologie de qualité des appels, CQD est simple pour vous aider à identifier les conditions poches d’appels médiocres ont en commun, un des principes pour améliorer la qualité des appels.
  
## <a name="viewing-data-in-cqd"></a>Affichage des données dans CQD

Les données CQD peuvent être visionnées via le portail CQD et accessibles par le biais d’appels de l’API REST.
  
### <a name="cqd-portal"></a>Portail CQD

Le portail est le moyen le plus rapide pour afficher les données dans le Cube. Le portail est livré avec plusieurs rapports intégrés qui sont utilisables immédiatement. Les rapports intégrés sont liées de manière structurée pour guider l’utilisateur à successivement les plus petits segments de données d’appel. Les rapports intégrés également en surbrillance les différentes méthodes que les données peuvent être affichées en montrant une combinaison des graphiques et des tableaux avec différents tableaux croisés dynamiques, des filtres et des mesures. Chaque utilisateur qui accède au portail peut avoir son propre ensemble de rapports qui il peut modifier et partager. Pour plus d’informations sur l’utilisation du portail Web CQD, voir [Utilisation d’appel qualité de tableau de bord pour Skype pour Business Server](use.md).
  
Prise en charge des systèmes d’exploitation pour CQD Portal : Windows 8.1, Windows 8, Windows Server 2012 R2, Windows Server 2012 et Windows Server 2016 (Skype pour Business Server 2019 CQD uniquement).
  
Navigateurs pris en charge pour CQD Portal : Internet Explorer 11, Internet Explorer 10 et Internet Explorer 9.
  
### <a name="rest-apis"></a>API REST

Les données du Cube sont également accessibles via des appels d’API REST. Les données récupérées par le biais de l’API REST peuvent être affichées par le biais des pages HTML. Utilisateurs peuvent tirer parti de la vitesse de requête et le schéma de haut niveau de CQD pendant toujours créer des rapports personnalisés adaptés à leurs besoins. Pour plus d’informations sur les API et les exemples, voir [Développer appeler tableau de bord qualité pour Skype pour Business Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Définition des besoins de votre organisation pour CQD

CQD fournit QoE données d’archivage et rapide et approfondie l’analyse de données de qualité des appels. Le guide suivant vous aide à décider quand et pourquoi vous devez déployer CQD.
  
### <a name="when-to-deploy-cqd"></a>Quand déployer CQD

 **CQD peut être déployé pour établir une mesure de qualité appel planifié, même si une organisation ne rencontrer des problèmes de qualité d’appel.** Établissement d’une mesure de qualité d’appel planifié est important parce que chaque organisation possède une autre combinaison de Wi-Fi et câblé et à distance et employés. En cas de problèmes de qualité des appels, les mesures de qualité d’appel plus récentes peuvent être comparées à des intervalles de temps précédente. Fonctionnalités des tendances de CQD permettent de faciliter la détection des modifications dans la qualité des appels au fil du temps.
  
 **CQD peut être déployé pour identifier de manière proactive les problèmes qui peuvent avoir un impact sur la qualité des appels.** Même si l’appel de la moyenne qualité pour une organisation peut atteindre les objectifs de l’organisation, il pourrait poches des problèmes de qualité d’appel qui sont masqués derrière les mesures moyennes. CQD permet de répartition de sous forme de tableau croisé dynamique des mesures de qualité d’appel par le nombre de dimensions dans la base de données QoEMetrics. SPOTTING valeurs extrêmes dans des groupes de l’homologue est un moyen rapide de localiser proactive des problèmes de qualité d’appel.
  
 **CQD doit être déployé s’il y a appel problèmes de qualité de l’organisation afin de réduire le temps nécessaire pour résoudre les problèmes.** CQD peut simplifier les enquêtes de qualité appel existant en proposant la génération de rapports rapide des performances et exploration dynamique des fonctionnalités. CQD est conçu pour de nombreux types de flux de travail dans l’appel de qualité enquêtes validation des réparations à l’environnement.
  
### <a name="why-deploy-cqd"></a>Raisons pour lesquelles déployer CQD

 **CQD doit être déployé si la création de rapports QoE doit se produire pendant plus de 3 mois de données.** Rapports du serveur de surveillance et de la base de données QoEMetrics sont conçus pour conserver et un petit jeu de données de rapport. La base de données des mesures QoE est optimisé pour les insertions rapides et par conséquent création de rapports de performances peuvent être confrontés à un volume important d’appels ou concurrents l’accès à la base de données création de rapports. Base de données QoE Archive de CQD fournit une deuxième copie des données avec des capacités de rétention beaucoup plues mesures QoE. Le portail est également optimisé pour afficher jusqu'à 7 mois de données à la fois et permettre créer des rapports sur toutes les données dans le QoE Archive selon vos besoins.
  
 **CQD doit être déployé si les rapports QoE personnalisés sont nécessaires.** Le portail a une fonctionnalité d’éditeur de rapport pour les rapports de création et de prototypage rapidement et facilement. En outre, les API REST disponibles pour l’accès par programme aux données du Cube, permettant la présentation personnalisée à l’aide HTML/JavaScript ou nombreuses autres infrastructures. Il n’est plus nécessaire créer des requêtes SQL afin de créer des vues de données personnalisées pour les rapports.
  
 **CQD doit être déployé si QoE existante de rapport proprement dites ne respecte pas la vitesse ou la profondeur requise par l’organisation.** CQD est fourni avec de nombreux rapports intégrés. Les rapports sont utiles immédiatement et montrer comment progressivement l’extraction des données peut offrir des informations supplémentaires à chaque niveau. La hiérarchie des rapports également vous aide à la gestion des nombreux rapports de manière logique et elle favorise la création de nombreux rapports plus facilement accessibles et compréhensibles. CQD n’offre pas seulement la vitesse et la flexibilité, mais également est optimisé pour les flux de travail développé par la méthodologie de qualité des appels.
  
## <a name="components-and-topologies-for-cqd"></a>Composants et topologies pour CQD

CQD est fourni avec plusieurs composants, et il est utile de comprendre les exigences de chaque composant et leurs relations entre eux pour obtenir la plus simple et mieux réaliser le déploiement de l’outil. Le tableau suivant décrit le composant dépendant pour chaque composant CQD.
  

|**Nom du composant**|**Composant dépendant**|
|:-----|:-----|
|QoE Archive  <br/> |Microsoft SQL Server  <br/> |
|Cube  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portail  <br/> |Services Microsoft  <br/> |
|Référentiel Service (partie de l’installation de portail)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> QoE Archive et du Cube, certaines options de déploiement nécessitent des éditions Business Intelligence ou Enterprise de Microsoft SQL Server. Reportez-vous à la section [conditions d’Infrastructure requises pour CQD](plan.md#Infrastructure_Req) ci-dessous pour plus d’informations.
  
![Composants CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configuration de serveur unique

Tous les composants CQD et dépendant peut être installé sur un ordinateur. La configuration d’une zone unique est la configuration la plus simple et CQD à être autonomes. CQD devez uniquement accès à la base de données de mesures QoE sur le serveur de surveillance. Le serveur CQD peut être un ordinateur autonome, un ordinateur virtuel, ou il peut même être le serveur de surveillance, selon les ressources disponibles de l’ordinateur hôte et les exigences de performances. 
  
Pendant l’installation, l’utilisateur effectue que l’installation doit simplement fournir Microsoft SQL Server et les instances de Microsoft SQL Server Analysis Services qui ont été définies sur l’ordinateur où le CQD doit être installé. Pour plus d’informations, reportez-vous à [Déployer appeler tableau de bord qualité pour Skype pour Business Server](deploy-0.md) .
  
### <a name="multiserver-configuration"></a>Configuration multiserveur

Dans une configuration multiserveur, le QoE Archive, Cube et portail peuvent tous être sur des ordinateurs différents. Il existe deux utilisations principales pour la configuration multiserveur :
  
- Hébergement de portail Web : CQD et CQD Cube sur différents serveurs.
    
- Hébergement d’un portail séparé de portail « production » « développement ». 
    
  **Hébergement de portail Web : CQD et CQD Cube sur des ordinateurs différents.** Les organisations qui peuvent avoir des exigences pour séparer le portail de CQD à partir de l’installation de SQL Server ou qui peut à combiner des éditions de SQL Server pour l’instance SQL Server et l’instance de SQL Server Analysis Services peuvent choisir d’installer le portail de CQD et Cube CQD sur des ordinateurs différents. Le composant QoE Archive peut également être le composant CQD unique qui est installé, si l’organisation souhaite simplement d’avoir une méthode durable à archiver sans atteindre les limites de performances sur le serveur de surveillance QoE.
  
![CQD mono-serveur](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hébergement d’un portail séparé de portail « production » « développement ».** Les organisations qui développent leurs propres rapports (par le biais de l’API REST) pourrait être préférable de déployer d’autres instances du portail (CQD) à côté de la production portail auxquels les utilisateurs régulières accès pour la surveillance de qualité appel ou enquêtes. Le portail de développement peut être isolées les modifications apportées au portail à partir de l’environnement de production. Les portails web supplémentaires peuvent être déployés sur des ordinateurs différents (voir ci-dessous) ou déployés sur des répertoires web différente sur le même ordinateur (non illustré). Pour accomplir cette dernière, le portail web : CQD supplémentaire doit être copié sur l’ordinateur de production manuellement, car le processus d’installation CQD déploie toujours le portail Web : CQD au site web par défaut avec des noms d’application web prédéfinis.
  
![Planification de multi-serveur CQD](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologies prises en charge

CQD ne fusionne pas les données à partir de plusieurs bases de données QoEMetrics, comme dans le cas où il existe plusieurs Skype pour les topologies de serveur d’entreprise, chacun avec son propre serveur de surveillance. Chaque instance CQD doit pointer sur une base de données QoEMetrics. Toutefois, car CQD sont déplacés de la charge de travail de création de rapports sur le serveur de surveillance, grandes organisations qui nécessaires pour déployer un serveur de surveillance par Skype pour la topologie du serveur d’entreprise doivent prendre en compte à l’aide d’un serveur de surveillance pour toutes les topologies.
  
## <a name="infrastructure-requirements-for-cqd"></a>Conditions d’infrastructure requises pour CQD
<a name="Infrastructure_Req"> </a>

CQD, y compris tous ses composants et composants dépendants, peut être déployé sur un ordinateur virtuel, un seul ordinateur ou sur plusieurs ordinateurs. La configuration logicielle et matérielle minimale requise est répertoriée ci-dessous. Disponibilité des données et les performances peuvent varier de quelques minutes, heures, selon le nombre de Skype active les utilisateurs Business Server et de matériel et de configuration, de requête sont des mesures de performances sont indiquées ci-dessous.
  
|||
|:-----|:-----|
|Systèmes d’exploitation pris en charge  <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|Prise en charge de SQL Server  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |
   
CQD utilise Microsoft SQL Server, Microsoft SQL Server Analysis Services et Microsoft Internet Information Services afin de CQD configuration matérielle et logicielle requise est les mêmes que ces composants dépendants. Toutefois, en fonction des besoins de l’organisation autour de degré d’actualisation des données (qui dépend en partie du volume de données QoE que génère l’organisation) et les coûts de déploiement, autres aspects du déploiement doivent être effectuées.
  
Traitement des données dans CQD est divisée en deux étapes principales : 
  
- Processus d’archivage QoE
    
- Traitement du Cube CQD
    
  **QoE Archive de traitement.** La tâche de traitement de le QoE Archive copie des données à partir de la base de données de mesures QoE sur le serveur de surveillance dans cette base de données QoE. Il existe deux situations où le temps de traitement de la tâche aurait des caractéristiques de performances fondamentalement différentes. Le premier est après l’installation initiale de CQD. Lorsque la tâche est exécutée pour la première fois après une nouvelle installation, la tâche de traitement de le QoE Archive copie toutes les données qui se trouve dans la base de données de mesures QoE dans la base de données QoE Archive. Le second est le traitement périodique après cette phase initiale. Le QoE Archive tâche de traitement exécute toutes les 15 minutes et traiter les nouveaux enregistrements QoE qui se trouvent dans la base de données des mesures QoE. En règle générale, le temps de traitement initial n’est pas un problème car elle est exécutée uniquement la première fois, lors de l’installation CQD. Toutefois, si le serveur CQD est strictement sous-mis en service, cette tâche peut prendre plusieurs heures. Consultez le tableau ci-dessous par exemple initiale QoE Archive temps de traitement.
  
  **Traitement du Cube CQD.** La tâche de traitement de Cube regroupe les données à partir de la base de données QoE Archive dans le Cube. Les temps de traitement initial et le temps de traitement suivantes sont déterminées par l’édition de SQL Server Analysis Services utilisée pour le Cube CQD. Si la version Standard edition est utilisée, il n’existe aucune différence entre le temps de traitement du cube initial et le temps de traitement, car chaque fois que les données du Cube sont actualisées de cube suivant, sera toujours un traitement complet de toutes les données disponibles. (Cela signifie que le temps de traitement du Cube accroît à mesure que la quantité de données dans le QoE Archive à l’augmentation de la base de données). Car le Business Intelligence Edition et Enterprise Edition de SQL Server partition prend en charge, si l’édition est utilisé, seulement l’exécution initiale va traiter toutes les données dans cette base de données QoE. Dans des exécutions ultérieures, lorsque la tâche est déclenchée toutes les 15 minutes, la tâche traitera uniquement les nouveaux enregistrements ajoutés à la base de données QoE Archive depuis la dernière exécution de la tâche. Une fois par jour, il sera également un traitement complet sur la partition qui contient les données du mois en cours.
  
Les caractéristiques de l’ordinateur physique peuvent affecter les performances de CQD, ainsi que les fonctionnalités logicielles qui sont disponibles dans les composants SQL Server. Le composant QoE Archive seront beaucoup plus de disque par rapport à d’autres composants, tandis que le composant de Cube sera plus du processeur et mémoire. Tous ces facteurs contribuent à temps du CQD traitement des données total, qui affecte directement la disponibilité et le degré d’actualisation des données. Les organisations doivent prendre des décisions sur les matériels et logiciels selon les besoins spécifiques de l’organisation. 
  
### <a name="tested-hardware-configurations"></a>Configurations matérielle testée

Cette section, en partant du principe qu’il existe une seule base de données QoEMetrics dans l’environnement. 
  
**Profils de l’ordinateur**

|**Machine**|**Cœurs de processeur**|**RAM**|**QoE Archive et Cube sur le même disque**|**QoE Archive et la base de données SQL Temp sur le même disque**|
|:-----|:-----|:-----|:-----|:-----|
|Ordinateur virtuel  <br/> |4  <br/> |7 GO  <br/> |Oui   <br/> |Oui  <br/> |
|4 cœurs  <br/> |4  <br/> |20 GO  <br/> |Oui  <br/> |Non  <br/> |
|8 principaux  <br/> |8  <br/> |32 GO  <br/> |Oui  <br/> |Non  <br/> |
|16 cœurs  <br/> |16  <br/> |128 GO  <br/> |Non  <br/> |Non  <br/> |
   
**Résultats des performances**

|**Machine**|**Taille de la base de données les mesures QoE**|**Partitions SQL**|**Type de disque**|**Nombre de flux**|**Processus d’archivage initiales**|**Processus de Cube initial**|**Les processus d’archivage**|**Les processus de Cube**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ordinateur virtuel  <br/> |900 MO  <br/> |Unique  <br/> |Disque dur virtuel (taille de la variable)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Ordinateur virtuel  <br/> |9 GO  <br/> |Unique  <br/> |Disque dur virtuel (taille de la variable)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Ordinateur virtuel  <br/> |9 GO  <br/> |Unique  <br/> |Disque dur virtuel (taille fixe)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Ordinateur virtuel  <br/> |30 GO  <br/> |Unique  <br/> |Disque dur virtuel (taille fixe)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 principaux  <br/> |9 GO  <br/> |Unique  <br/> |Plusieurs disques  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 principaux  <br/> |9 GO  <br/> |Plusieurs  <br/> |Plusieurs disques  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 principaux  <br/> |30 GO  <br/> |Unique  <br/> |Plusieurs disques  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 principaux  <br/> |30 GO  <br/> |Plusieurs  <br/> |Plusieurs disques  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 cœurs  <br/> |200 GO  <br/> |Unique  <br/> |Plusieurs disques  <br/> |125 M  <br/> |6 + jours  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 cœurs  <br/> |500 GO  <br/> |Plusieurs  <br/> |Plusieurs piles de disque  <br/> |250 MO  <br/> |8 jours  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Ils ne devraient pas être rencontrés dans les déploiements réels, car la base de données des mesures QoE aurait besoin 9 et 18 mois de données, respectivement, mais elles sont fournies ici par souci d’intégralité.
  
### <a name="service-account-requirements"></a>Exigences de compte de service

Vous devez un compte que l’Agent SQL sur le serveur CQD peut utiliser pour l’importation de données vers le QoEArchiveDB (avec un accès en lecture à QoEMetrics).
  
Vous devez également configurer un compte distinct pour une tâche SSAS pour extraire des données à partir de QoEArchiveDB (il s’agit d’un processus facultatif).
  
IIS utilise le Service réseau en tant qu’identité du Pool d’application plus fréquemment, mais peut être configuré pour un compte de Service.
  
### <a name="portal-access-control"></a>Contrôle d’accès au portail

Par défaut, tout utilisateur authentifié a accès. Cela peut être modifiée à l’aide de règles d’autorisation d’IIS pour limiter à un groupe spécifique.
  
### <a name="pre-install-requirements"></a>Conditions préalables à l’installation

Ces instructions supposent qu’une base de données des mesures QoE a déjà été installé et est en cours d’exécution dans le Skype pour la topologie du serveur d’entreprise.
  
#### <a name="hardware-requirements"></a>Configuration matérielle requise

CQD utilise Microsoft Internet Information Server, Microsoft SQL Server et Microsoft SQL Server Analysis afin de CQD configuration matérielle et logicielle requise est les mêmes que ces composants dépendants. Toutefois, en fonction des besoins de l’organisation autour de degré d’actualisation des données (qui dépend en partie du volume de données QoE que génère l’organisation) et les coûts de déploiement, autres aspects du déploiement doivent être effectuées.
  
#### <a name="software-requirements"></a>Configuration logicielle requise

Les systèmes d’exploitation suivants sont requis pour CQD :
  
- Windows Server 2008 R2 avec IIS 7.5
    
- Windows Server 2012 avec IIS 8.0
    
- Windows Server 2012 R2 avec IIS 8,5

- Windows Server 2016 avec IIS 10.0 (Skype pour Business Server 2019 CQD uniquement)
    
Voici les services de rôle IIS requis (par ordre hiérarchique) :
  
- Serveur Web
    
  - Fonctionnalités HTTP communes
    
  - Contenu statique
    
  - Document par défaut
    
  - Développement d’applications
    
  - ASP.NET
    
  - Filtres ISAPI
    
  - Intégrité &amp; Diagnostics
    
  - Journalisation HTTP
    
  - Sécurité
    
  - Autorisation d’URL
    
  - Authentification Windows
    
  - Outils de gestion
    
  - Console de gestion des services Internet (IIS)
    
> [!NOTE]
>  Notez ce qui suit pour la configuration requise ci-dessus : > 3.5 et les versions du .net framework 4.5 sont disponibles. Les deux sont requis (plus précisément, 3.5 SP1 est requis) .> dans certains systèmes, si ASP.NET est le programme d’installation avant l’installation d’IIS, ASP.NET ne peut pas être inscrit dans IIS. Le problème se manifeste par le biais de l’absence de pools d’applications pour la version correspondante de .net et pas la version CLR .NET dans la configuration du pool d’applications. Pour corriger ce problème dans Windows Server 2008 R2, vous devez exécuter `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`. Sur Windows Server 2012 et Windows Server 2012 R2, exécutez `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` suivi en supprimant la « ServiceModel « module à partir du Site Web par défaut dans les outils de gestion d’IIS Manager.> est facultatif, mais recommandé.
  
Pour installer ces exigences à l’aide de PowerShell, exécutez la commande suivante :
  
```
import-module servermanager
```

```
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Les versions suivantes de SQL Server sont prises en charge :
  
- SQL Server 2012
    
- SQL Server 2014

- SQL Server 2016

- SQL Server 2017
    
Business Intelligence ou Enterprise edition est recommandée pour des raisons de performances. Ces éditions autorisent l’utilisation de plusieurs fichiers de partition qui peuvent être traités en parallèle, ce qui est utile pour le traitement des données répartis sur plusieurs mois ou plus. 
  
Alors que non recommandé, Standard edition est également pris en charge. Traitement s’être limité à une seule partition (qui doit être configuré lors de l’installation). 
  
Dans tous les cas, « Services du moteur de base de données » et « Analysis Services » doivent être installés. Il est recommandé, mais pas nécessaire d’installer également la fonctionnalité « Outils de gestion - terminer », qui ajoute la prise en charge de SQL Server Management Studio pour Analysis Services. Écran de sélection de fonctionnalité doit ressembler à la figure.
  
![Configuration requise pour les fonctionnalités SQL Server](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Lorsque vous configurez l’installation SSAS, dans la Configuration d’Analysis Services, la valeur « Mode serveur » à « Multidimensionnelle et données exploration Mode ». 
  
Pour plus d’informations d’installation et de configuration des fonctions de SQL Server Business Intelligence, voir [Installer Analysis Services dans multidimensionnel et Mode d’exploration de données](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Configuration requise

Sur le principe des privilèges minimum, trois comptes de service de domaine sont recommandées : 
  
- Une qui dispose déjà d’une entité de sécurité de connexion de base de données des mesures QoE (avec des privilèges db_datareader) et d’une entité de sécurité de connexion dans QoE Archive Instance de SQL Server (nécessaire pour créer un objet de serveur lié lors de l’installation). Ce compte est utilisé pour exécuter l’étape « Archive les données QoE » de la tâche de l’Agent SQL Server.
    
- Une qui sera utilisé pour exécuter l’étape « Traiter le Cube » de la tâche de l’Agent SQL Server. Le programme d’installation créera un compte de connexion à la base de données QoE Archive entité de sécurité (avec lire et écrire des privilèges), ainsi qu’un membre du rôle QoE (avec l’autorisation contrôle total) pour le Cube.
    
- Une qui sera utilisé pour exécuter le processus de travail IIS pour les portails web web API. Le programme d’installation crée un compte de connexion entité de sécurité de base de données QoE Archive (avec des privilèges de lecture), une entité de sécurité de connexion à la base de données de référentiel (avec lire et écrire des privilèges) et un membre dans QoERole (avec l’autorisation contrôle total) pour le Cube. 
    
    > [!NOTE]
    > Lors de la base de données QoE Archive et de base de données de référentiel sont hébergées dans le même serveur SQL Server, qu’une sécurité de connexion principale avec deux mappages utilisateur est créée. 
  
Les deux premiers comptes peuvent être logiquement considérés comme « comptes de service principal » et le dernier compte est un « compte de service frontal ». Alors que non recommandé, il est possible d’utiliser un compte unique dans tous les cas.
  
> [!NOTE]
> Le compte d’utilisateur lançant l’installation doit accéder en lecture à la base de données de mesures QoE ainsi (outre ayant des droits d’administrateur de machine sur le serveur de base de données Archive QoE où l’installation doit avoir lieu). 
  
## <a name="capacity-planning"></a>Planification de la capacité
<a name="Infrastructure_Req"> </a>

CQD est conçu pour un Impact minimal sur QoEMetrics : le code a été optimisé pour ne verrouiller pas les données et les travaux d’importation sont ajustables.
  
Le type de matériel à utiliser dépend de votre configuration requise pour la vitesse des synchronisations doivent s’exécuter. Dimensionnement de disque est la suivante :
  
- QoEArchive est supérieure à la base de données QoEMetrics ~1.5x initialement
    
- Cube SSIS compresse les données presque 10 x par rapport à la base de données
    
- Les données sont partitionnées tous les mois ; les partitions peuvent être supprimées.
    

