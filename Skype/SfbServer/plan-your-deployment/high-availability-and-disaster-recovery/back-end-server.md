---
title: Arrière serveur haute disponibilité dans Skype pour Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Découvrez les options de haute disponibilité du serveur principal prises en charge dans Skype pour Business Server, y compris les groupes de disponibilité AlwaysOn, Instances de Cluster de basculement AlwaysOn, la mise en miroir de base de données et le clustering avec basculement SQL.
ms.openlocfilehash: c17d4afb20a0aeef2a1dacc40080a1092fbda357
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789291"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Arrière serveur haute disponibilité dans Skype pour Business Server
 
Découvrez les options de haute disponibilité du serveur principal prises en charge dans Skype pour Business Server, y compris les groupes de disponibilité AlwaysOn, Instances de Cluster de basculement AlwaysOn, la mise en miroir de base de données et le clustering avec basculement SQL.
  
Pour améliorer la haute disponibilité de vos serveurs principaux, vous disposez de quatre options :
  
- Mise en miroir de bases de données
    
- Groupes de disponibilité AlwaysOn
    
- Cluster de basculement AlwaysOn Instances (FCI)
    
- Clustering SQL avec basculement
    
L’utilisation d’une de ces solutions est facultative mais est recommandée pour préserver la continuité des activités de votre organisation. Dans le cas contraire, avoir un serveur de base de données unique Descendre peut entraîner la perte de Skype important pour les données métiers. 
  
Vous pouvez définir la mise en miroir de base de données à l’aide du Générateur de topologie uniquement. Pour les groupes de disponibilité AlwaysOn, Instances de Cluster de basculement AlwaysOn ou le clustering avec basculement SQL, vous utilisez SQL Server pour créer la solution de haute disponibilité, puis vous pouvez utiliser le Générateur de topologie pour associer un pool frontal.
  
Si vous utilisez une haute disponibilité du serveur principal sur un pool frontal qui est associé à un autre pool frontal pour la récupération d’urgence, vous devez utiliser la solution de haute disponibilité principales même dans les deux pools. 
  
## <a name="database-mirroring"></a>Mise en miroir de bases de données

Skype pour Business Server prend en charge la mise en miroir avec le logiciel de base de données suivantes :
  
- SQL Server 2016, Enterprise Edition et Standard Edition

- SQL Server 2014, Enterprise Edition et Standard Edition
    
- SQL Server 2012 SP2 et CU2, Enterprise Edition et Standard Edition
    
- SQL Server 2008 R2 SP2, Enterprise Edition et Standard Edition

> [!NOTE]
> SQL Server 2016 est la seule version prise en charge par Skype pour Business Server 2019.
    
La mise en miroir de base de données asynchrone n’est pas pris en charge pour la haute disponibilité de serveur principal dans Skype pour Business Server. Dans le reste du document, sauf mention explicite, la mise en miroir sous-entend une mise en miroir synchrone. 
  
Lorsque vous déployez la mise en miroir de base de données dans un pool frontal, Skype toutes les bases de données Business Server du pool sont mis en miroir, y compris le magasin Central de gestion, si elle se trouve dans ce pool, ainsi que la base de données application Response Group et la mise en garde d’appels base de données, si ces applications s’exécutent dans le pool. 
  
La mise en miroir de base de données vous permet de ne pas avoir à utiliser de stockage partagé pour les serveurs. Chaque serveur garde sa copie des bases de données en local. 
  
Vous pouvez déployer la mise en miroir de base de données avec ou sans témoin. Cela dit, nous vous recommandons d’en utiliser un, car il permet le basculement automatique du serveur principal. Dans le cas contraire, un administrateur doit appeler le basculement manuellement. Notez que même si un témoin est déployé, un administrateur peut au besoin appeler manuellement le basculement du serveur principal.
  
Si vous utilisez un témoin, celui-ci peut servir pour plusieurs paires de serveurs principaux. Il n’y a aucune correspondance stricte un-à-un entre les témoins et les paires de serveurs principaux. Les déploiements utilisant un seul témoin pour plusieurs paires de serveurs principaux ne sont simplement pas aussi résilients que les topologies faisant appel à un témoin à part pour chaque paire de serveurs principaux. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Directives pour la planification de la mise en miroir du serveur frontal

En général, la configuration de la mise en miroir SQL entre deux serveurs principaux avec un témoin exige ce qui suit :
  
- Version du serveur principal de SQL Server doit prendre en charge la mise en miroir SQL.
    
- Le principal, le miroir et le témoin (s’il est déployé) doivent disposer de la même version de SQL Server. 
    
- Le principal et le miroir doivent disposer de la même édition de SQL Server. Le témoin peut en avoir une différente.
    
Pour les meilleures pratiques en termes de quelles versions SQL sont pris en charge pour un rôle de témoin SQL, voir [« témoin de mise en miroir de base de données »](https://go.microsoft.com/fwlink/p/?LinkId=247345) dans la bibliothèque MSDN.
  
Avant de configurer la mise en miroir des serveurs, vous devez d’abord configurer les autorisations de base de données SQL correctement. Pour plus d’informations, voir [« Configurer les comptes de connexion pour la mise en miroir de base de données ou groupes de disponibilité AlwaysOn (SQL Server) »](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Avec la mise en miroir SQL, le mode de récupération de la base de données a toujours la valeur **Complète**, ce qui signifie que vous devez surveiller de près la taille du journal des transactions et sauvegarder les journaux des transactions de manière régulière afin d’éviter toute insuffisance d’espace disque sur les serveurs principaux. La fréquence des sauvegardes des journaux des transactions dépend de la vitesse à laquelle leur taille augmente, laquelle dépend à son tour des transactions de base de données induites par les activités des utilisateurs sur le pool frontal. Nous vous recommandons d’estimer l’accroissement des journaux des transactions pour la charge de travail de votre déploiement Lync afin de procéder à une planification en conséquence. Les articles suivants fournissent des informations supplémentaires sur la gestion des journaux et sauvegardes SQL :
  
> [!IMPORTANT]
> À l’aide du Générateur de topologie ou des applets de commande pour configurer et supprimer SQL la mise en miroir est prise en charge uniquement lorsque le serveur principal, miroir et le serveur témoin (le cas échéant) appartiennent au même domaine. Si vous voulez configurer la mise en miroir SQL entre des serveurs de différents domaines, reportez-vous à votre documentation SQL Server. 

> [!NOTE]
> La mise en miroir SQL est disponible dans Skype pour Business Server 2015 mais n’est plus pris en charge dans Skype pour Business Server 2019. Les méthodes de clustering avec basculement SQL, les Instances de Cluster de basculement AlwaysOn (FCI) et les groupes de disponibilité AlwaysOn sont préférés avec Skype pour Business Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Temps de récupération pour le basculement automatique de serveur principal avec la mise en miroir de base de données

Pour le basculement automatique de serveur principal avec la mise en miroir de base de données, la cible d’ingénierie pour la durée maximale d’interruption admissible (RTO, Recovery Time Objective) est de 5 minutes. Par l’usage de la mise en miroir de base de données synchrone, nous ne prévoyons pas de perte de données en cas de panne du serveur principal sauf dans de rares cas où les serveurs frontaux et le serveur principal s’arrêtent de fonctionner en même temps pendant un transfert de données entre les serveurs. La cible d’ingénierie pour la perte de données maximale admissible (RPO, Recovery Point Objective) est de 5 minutes.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Expérience utilisateur en cas de panne du serveur principal avec la mise en miroir de base de données

L’expérience utilisateur en cas de panne dépend de la nature de la panne et de votre topologie.
  
Si vous utilisez la mise en miroir de base de données et avez configuré un témoin et qu’une panne se produit au niveau du serveur principal, le basculement du serveur principal se fait automatiquement et rapidement. Les utilisateurs actifs ne devraient pas remarquer d’interruption particulière de leurs sessions actives.
  
Si aucun témoin n’est configuré, l’administrateur peut perdre du temps à appeler manuellement le basculement. Pendant ce temps, les utilisateurs actifs peuvent s’en trouver affectés. Leurs sessions se poursuivent normalement pendant environ 30 minutes. Si le serveur principal n’est pas toujours restauré ou un administrateur n’a pas basculé vers la sauvegarde, puis les utilisateurs passent en mode résilience, ce qui signifie qu’ils ne peuvent pas effectuer des tâches qui nécessitent une modification permanente sur Lync Server (telles que l’ajout d’un contact).
  
Si le serveur principal et les serveurs principaux en miroir tombent en panne, ou si l’un de ces derniers serveurs et le témoin tombent en panne, le serveur principal n’est alors plus disponible (même s’il fonctionne toujours). Dans ce cas, le mode de résistance s’active pour les utilisateurs actifs après une certaine durée.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Groupes de disponibilité AlwaysOn et instances de cluster de basculement AlwaysOn

Groupes de disponibilité AlwaysOn et des Instances de Cluster de basculement AlwaysOn sont pris en charge uniquement sur SQL Server 2014 Enterprise Edition et SQL Server 2012 Enterprise Edition. Skype pour Business Server prend en charge les groupes de disponibilité AlwaysOn uniquement en tant que clusters actif/passif, actif/actif. 
  
Pour utiliser des groupes de disponibilité AlwaysOn ou des Instances de Cluster de basculement AlwaysOn, vous d’abord utilisez SQL Server pour installer et configurer la solution de haute disponibilité. Vous pouvez ensuite utiliser le Générateur de topologie pour associer un pool frontal.
  
> [!IMPORTANT]
> Noms d’instance pour plusieurs instances du groupe de disponibilité AlwaysOn doivent être identiques. 
  
Pour connaître les étapes pour le déploiement de groupes de disponibilité AlwaysOn, voir [déploiement d’un groupe de disponibilité AlwaysOn sur un serveur principal Skype pour Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>Clustering de basculement de SQL Server

Skype pour Business Server prend en charge les clusters SQL Server avec le logiciel de base de données suivantes :
  
- SQL Server 2016, Enterprise Edition et Standard Edition

- SQL Server 2014, Enterprise Edition et Standard Edition
    
- SQL Server 2012 SP2 et CU2, Enterprise Edition et Standard Edition
    
- SQL Server 2008 R2 SP2, Enterprise Edition et Standard Edition

> [!NOTE]
> SQL Server 2016 est la seule version prise en charge par Skype pour Business Server 2019.
    
Pour utiliser le clustering avec basculement SQL, vous devez tout d’abord installer et configurer le cluster SQL Server avant de déployer votre pool frontal. Pour meilleures pratiques et des instructions d’installation pour le cluster de basculement dans SQL Server 2014 et 2016, voir [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx). Clustering de basculement de SQL Server 2008, voir [https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
Lorsque vous installez SQL Server, vous devez installer SQL Server Management Studio pour gérer les emplacements des bases de données et des fichiers journaux. SQL Server Management Studio est installé en tant que composant facultatif lorsque vous installez SQL Server.
  

