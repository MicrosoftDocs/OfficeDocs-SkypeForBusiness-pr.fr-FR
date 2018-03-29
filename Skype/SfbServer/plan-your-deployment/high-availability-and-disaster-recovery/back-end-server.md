---
title: Haute disponibilité des serveurs principaux dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Obtenir des informations sur les options de haute disponibilité de serveur principal pris en charge dans Skype pour Business Server, y compris les groupes de disponibilité AlwaysOn, Instances de Cluster de basculement AlwaysOn, la mise en miroir de la base de données et clustering avec basculement SQL.
ms.openlocfilehash: f0831ffb757d04e954ece8a1874dffad9e6e74d0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="back-end-server-high-availability-in-skype-for-business-server-2015"></a>Haute disponibilité des serveurs principaux dans Skype Entreprise Server 2015
 
Obtenir des informations sur les options de haute disponibilité de serveur principal pris en charge dans Skype pour Business Server, y compris les groupes de disponibilité AlwaysOn, Instances de Cluster de basculement AlwaysOn, la mise en miroir de la base de données et clustering avec basculement SQL.
  
Pour améliorer la haute disponibilité de vos serveurs principaux, vous disposez de quatre options :
  
- Mise en miroir de bases de données
    
- Groupes de disponibilité AlwaysOn
    
- Les Instances de Cluster de basculement AlwaysOn (FCI)
    
- Clustering SQL avec basculement
    
L’utilisation d’une de ces solutions est facultative mais est recommandée pour préserver la continuité des activités de votre organisation. Dans le cas contraire, l’ayant un serveur de base de données unique à descendre pourrait provoquer la perte de Skype significatif pour les données du serveur de l’entreprise. 
  
Vous pouvez définir la mise en miroir de base de données à l’aide du Générateur de topologies uniquement. Pour les groupes de disponibilité AlwaysOn, Instances de Cluster de basculement AlwaysOn ou clustering avec basculement SQL, SQL Server vous permet de créer la solution de haute disponibilité, puis vous pouvez utiliser le Générateur de topologies pour l’associer à un pool frontal.
  
Si vous utilisez un pool frontal qui est associé à un autre pool de Front-End de reprise après sinistre haute disponibilité du serveur principal, vous devez utiliser la même solution de haute disponibilité de Back-End dans les deux pools. 
  
## <a name="database-mirroring"></a>Mise en miroir de bases de données

Skype pour Business Server prend en charge la mise en miroir avec les logiciels de base de données suivants :
  
- SQL Server 2014, Enterprise Edition et Standard Edition
    
- Le Service Pack 2 de SQL Server 2012 et CU2, Enterprise Edition et Standard Edition
    
- SQL Server 2008 R2 SP2, Édition entreprise et Standard Edition
    
La mise en miroir de base de données asynchrone n’est pas pris en charge pour une haute disponibilité de serveur principal dans Skype pour Business Server. Dans le reste du document, sauf mention explicite, la mise en miroir sous-entend une mise en miroir synchrone. 
  
Lorsque vous déployez la mise en miroir de base de données dans un pool frontal, Skype toutes les bases de données Business Server dans le pool sont mis en miroir, y compris le magasin Central de gestion, si elle se trouve dans ce pool, ainsi que la base de données des applications de groupe de réponse et le parc de l’appel application base de données, si ces applications sont en cours d’exécution dans le pool. 
  
La mise en miroir de base de données vous permet de ne pas avoir à utiliser de stockage partagé pour les serveurs. Chaque serveur garde sa copie des bases de données en local. 
  
Vous pouvez déployer la mise en miroir de base de données avec ou sans témoin. Cela dit, nous vous recommandons d’en utiliser un, car il permet le basculement automatique du serveur principal. Dans le cas contraire, un administrateur doit appeler le basculement manuellement. Notez que même si un témoin est déployé, un administrateur peut au besoin appeler manuellement le basculement du serveur principal.
  
Si vous utilisez un témoin, celui-ci peut servir pour plusieurs paires de serveurs principaux. Il n’y a aucune correspondance stricte un-à-un entre les témoins et les paires de serveurs principaux. Les déploiements utilisant un seul témoin pour plusieurs paires de serveurs principaux ne sont simplement pas aussi résilients que les topologies faisant appel à un témoin à part pour chaque paire de serveurs principaux. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Directives pour la planification de la mise en miroir du serveur frontal

En général, la configuration de la mise en miroir SQL entre deux serveurs principaux avec un témoin exige ce qui suit :
  
- Version du serveur principal de SQL Server doit prendre en charge la mise en miroir de SQL.
    
- Le principal, le miroir et le témoin (s’il est déployé) doivent disposer de la même version de SQL Server. 
    
- Le principal et le miroir doivent disposer de la même édition de SQL Server. Le témoin peut en avoir une différente.
    
Pour SQL recommandées en ce qui concerne les versions SQL sont pris en charge pour un rôle de rappel, consultez [« témoin de la mise en miroir de base de données »](https://go.microsoft.com/fwlink/p/?LinkId=247345) dans MSDN Library.
  
Avant de configurer la mise en miroir des serveurs, vous devez d’abord configurer les autorisations de base de données SQL correctement. Pour plus d’informations, reportez-vous à la section [« Configuration des comptes de connexion pour la mise en miroir de base de données ou groupes de disponibilité AlwaysOn (SQL Server) »](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Avec la mise en miroir SQL, le mode de récupération de la base de données a toujours la valeur **Complète**, ce qui signifie que vous devez surveiller de près la taille du journal des transactions et sauvegarder les journaux des transactions de manière régulière afin d’éviter toute insuffisance d’espace disque sur les serveurs principaux. La fréquence des sauvegardes des journaux des transactions dépend de la vitesse à laquelle leur taille augmente, laquelle dépend à son tour des transactions de base de données induites par les activités des utilisateurs sur le pool frontal. Nous vous recommandons d’estimer l’accroissement des journaux des transactions pour la charge de travail de votre déploiement Lync afin de procéder à une planification en conséquence. Les articles suivants fournissent des informations supplémentaires sur la gestion des journaux et sauvegardes SQL :
  
> [!IMPORTANT]
> À l’aide du Générateur de topologies ou des applets de commande pour installer et supprimer SQL mise en miroir est prise en charge uniquement primaire, miroir et serveurs de rappel (le cas échéant) appartiennent au même domaine. Si vous voulez configurer la mise en miroir SQL entre des serveurs de différents domaines, reportez-vous à votre documentation SQL Server. 
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Temps de récupération pour le basculement automatique de serveur principal avec la mise en miroir de base de données

Pour le basculement automatique de serveur principal avec la mise en miroir de base de données, la cible d’ingénierie pour la durée maximale d’interruption admissible (RTO, Recovery Time Objective) est de 5 minutes. Par l’usage de la mise en miroir de base de données synchrone, nous ne prévoyons pas de perte de données en cas de panne du serveur principal sauf dans de rares cas où les serveurs frontaux et le serveur principal s’arrêtent de fonctionner en même temps pendant un transfert de données entre les serveurs. La cible d’ingénierie pour la perte de données maximale admissible (RPO, Recovery Point Objective) est de 5 minutes.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Expérience utilisateur en cas de panne du serveur principal avec la mise en miroir de base de données

L’expérience utilisateur en cas de panne dépend de la nature de la panne et de votre topologie.
  
Si vous utilisez la mise en miroir de base de données et avez configuré un témoin et qu’une panne se produit au niveau du serveur principal, le basculement du serveur principal se fait automatiquement et rapidement. Les utilisateurs actifs ne devraient pas remarquer d’interruption particulière de leurs sessions actives.
  
Si aucun témoin n’est configuré, l’administrateur peut perdre du temps à appeler manuellement le basculement. Pendant ce temps, les utilisateurs actifs peuvent s’en trouver affectés. Leurs sessions se poursuivent normalement pendant environ 30 minutes. Si le serveur principal n’est pas toujours restauré ou si un administrateur n’a pas basculé vers la sauvegarde, puis les utilisateurs passent en mode de résilience, c'est-à-dire qu’ils ne peuvent pas effectuer de tâches nécessitant une modification permanente sur Lync Server (par exemple, l’ajout d’un contact).
  
Si le serveur principal et les serveurs principaux en miroir tombent en panne, ou si l’un de ces derniers serveurs et le témoin tombent en panne, le serveur principal n’est alors plus disponible (même s’il fonctionne toujours). Dans ce cas, le mode de résistance s’active pour les utilisateurs actifs après une certaine durée.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Groupes de disponibilité AlwaysOn et instances de cluster de basculement AlwaysOn

Groupes de disponibilité AlwaysOn et Instances de Cluster de basculement AlwaysOn sont pris en charge uniquement sur SQL Server 2014 Enterprise Edition et Enterprise Edition de SQL Server 2012. Skype pour Business Server prend en charge les groupes de disponibilité AlwaysOn uniquement en tant qu’actif/passif, actif/actif. 
  
Pour utiliser des groupes de disponibilité AlwaysOn ou Instances de Cluster de basculement AlwaysOn, vous utilisez d’abord SQL Server pour installer et configurer la solution de haute disponibilité. Vous pouvez ensuite utiliser le Générateur de topologies pour l’associer à un pool frontal.
  
> [!IMPORTANT]
> Les noms d’instance pour plusieurs instances du groupe de disponibilité AlwaysOn doivent être identiques. 
  
Pour obtenir la procédure de déploiement des groupes de disponibilité AlwaysOn, voir [déploiement d’un groupe de disponibilité AlwaysOn sur un serveur principal dans Skype pour Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>Clustering de basculement de SQL Server

Skype pour Business Server prend en charge SQL Server clustering avec basculement avec les logiciels de base de données suivants :
  
- SQL Server 2014, Enterprise Edition et Standard Edition
    
- Le Service Pack 2 de SQL Server 2012 et CU2, Enterprise Edition et Standard Edition
    
- SQL Server 2008 R2 SP2, Édition entreprise et Standard Edition
    
Pour utiliser le clustering avec basculement SQL, vous devez tout d’abord paramétrer et configurer le cluster SQL Server avant de déployer votre pool frontal. Pour les meilleures pratiques et des instructions d’installation de cluster de basculement dans SQL Server 2012, voir [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx). Pour un cluster de basculement dans SQL Server 2008, voir [https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
Lorsque vous installez SQL Server, vous devez installer SQL Server Management Studio pour gérer les emplacements des bases de données et des fichiers journaux. SQL Server Management Studio est installé en tant que composant facultatif lorsque vous installez SQL Server.
  

