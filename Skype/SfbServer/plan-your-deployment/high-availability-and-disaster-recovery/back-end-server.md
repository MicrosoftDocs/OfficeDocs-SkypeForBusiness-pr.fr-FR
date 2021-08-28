---
title: Haute disponibilité du serveur principal dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Découvrez les options de haute disponibilité du serveur principal pris en charge dans Skype Entreprise Server, notamment les groupes de disponibilité AlwaysOn, les instances de cluster de failover AlwaysOn, la mise en miroir de bases de données et le clustering de SQL de base de données.
ms.openlocfilehash: ce84429d77b8da426913d873d99d2f70badc4d12
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595482"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Haute disponibilité du serveur principal dans Skype Entreprise Server
 
Découvrez les options de haute disponibilité du serveur principal pris en charge dans Skype Entreprise Server, notamment les groupes de disponibilité AlwaysOn, les instances de cluster de failover AlwaysOn, la mise en miroir de bases de données et le clustering de SQL de base de données.
  
Pour améliorer la haute disponibilité de vos serveurs back-end, vous avez quatre options :
  
- Mise en miroir de bases de données
    
- Groupes de disponibilité AlwaysOn
    
- Instances de cluster de failover AlwaysOn (FCI)
    
- SQL clustering deover
    
L’utilisation de l’une de ces solutions est facultative, mais est recommandée pour maintenir la continuité des activités de votre organisation. Dans le cas contraire, la panne d’un seul serveur de base de données peut entraîner la perte d’Skype Entreprise Server données. 
  
Vous pouvez configurer la mise en miroir de bases de données uniquement à l’aide du Générateur de topologies. Pour les groupes de disponibilité AlwaysOn, les instances de cluster de failover AlwaysOn ou le clustering de SQL failover, vous utilisez SQL Server pour créer la solution de haute disponibilité, puis vous pouvez utiliser le Générateur de topologie pour l’associer à un pool frontal.
  
Si vous utilisez la haute disponibilité du serveur principal sur un pool frontal associé à un autre pool frontal pour la récupération d’urgence, vous devez utiliser la même solution de haute disponibilité principale dans les deux pools. 
  
## <a name="database-mirroring"></a>Mise en miroir de bases de données

Skype Entreprise Server prend en charge la mise en miroir avec les logiciels de base de données suivants :
  
- SQL Server 2019, Êdition Entreprise et Édition Standard

- SQL Server 2017, Êdition Entreprise et Édition Standard

- SQL Server 2016, Êdition Entreprise et Édition Standard

- SQL Server 2014, Êdition Entreprise et Édition Standard
    
- SQL Server 2012 SP2 et CU2, à la fois Êdition Entreprise et Édition Standard
    

> [!NOTE]
> SQL La mise en miroir est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de cluster de SQL AlwaysOn et les méthodes de clustering de SQL sont les seules options prise en charge avec Skype Entreprise Server 2019.
    
La mise en miroir asynchrone des bases de données n’est pas prise en charge pour la haute disponibilité du serveur principal dans Skype Entreprise Server. Dans le reste de ce document, la mise en miroir de bases de données signifie la mise en miroir synchrone des bases de données, sauf indication contraire explicite. 
  
Lorsque vous déployez la mise en miroir de bases de données dans un pool frontal, toutes les bases de données Skype Entreprise Server du pool sont en miroir, y compris le magasin central de gestion, si elle se trouve dans ce pool, ainsi que la base de données d’application Response Group et la base de données d’application de parcage d’appel, si ces applications sont en cours d’exécution dans le pool. 
  
Avec la mise en miroir de bases de données, vous n’avez pas besoin d’utiliser le stockage partagé pour les serveurs. Chaque serveur garde sa copie des bases de données en local. 
  
Vous pouvez choisir de déployer la mise en miroir de bases de données avec ou sans témoin. Ceci dit, nous vous recommandons d’en utiliser un, car il permet le basculement automatique du serveur principal. Dans le cas contraire, un administrateur doit appeler le basculement manuellement. Notez que même si un témoin est déployé, un administrateur peut au besoin appeler manuellement le basculement du serveur principal.
  
Si vous utilisez un témoin, celui-ci peut servir pour plusieurs paires de serveurs principaux. Il n’y a aucune correspondance stricte un-à-un entre les témoins et les paires de serveurs principaux. Les déploiements utilisant un seul témoin pour plusieurs paires de serveurs principaux ne sont simplement pas aussi résilients que les topologies faisant appel à un témoin à part pour chaque paire de serveurs principaux. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Recommandations en matière de planification de la mise en miroir de serveur principal

En général, la configuration de la mise en miroir SQL entre deux serveurs principaux avec un témoin exige ce qui suit :
  
- La version d’SQL Server du serveur principal doit prendre en charge SQL miroir.
    
- Le principal, le miroir et le témoin (s’il est déployé) doivent disposer de la même version de SQL Server. 
    
- Le principal et le miroir doivent disposer de la même édition de SQL Server. Le témoin peut en avoir une différente.
    
Pour SQL meilleures pratiques en ce qui concerne les versions SQL sont [](/sql/database-engine/database-mirroring/database-mirroring-witness) pris en charge pour un rôle témoin, voir « Témoin de mise en miroir de bases de données » dans la bibliothèque MSDN.
  
Avant de configurer la mise en miroir de serveur, vous devez d’abord configurer SQL les autorisations de base de données correctement. Pour plus d’informations, voir « Configurer des comptes de connexion pour la mise en miroir de bases de données ou les groupes de disponibilité [AlwaysOn (SQL Server)](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)».
  
Avec la mise en miroir SQL, le mode de récupération de la base de données a toujours la valeur **Complète**, ce qui signifie que vous devez surveiller de près la taille du journal des transactions et sauvegarder les journaux des transactions de manière régulière afin d’éviter toute insuffisance d’espace disque sur les serveurs principaux. La fréquence des sauvegardes des journaux des transactions dépend de la vitesse à laquelle leur taille augmente, laquelle dépend à son tour des transactions de base de données induites par les activités des utilisateurs sur le pool frontal. Nous vous recommandons d’estimer l’accroissement des journaux des transactions pour la charge de travail de votre déploiement Lync afin de procéder à une planification en conséquence. Les articles suivants fournissent des informations supplémentaires sur la gestion des journaux et sauvegardes SQL :
  
> [!IMPORTANT]
> L’utilisation du Générateur de topologie ou des cmdlets pour configurer et supprimer la mise en miroir SQL est prise en charge uniquement lorsque les serveurs principal, miroir et témoin (si vous le souhaitez) appartiennent tous au même domaine. Si vous voulez configurer la mise en miroir SQL entre des serveurs de différents domaines, voir votre documentation SQL Server. 

> [!NOTE]
> SQL La mise en miroir est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de cluster de SQL AlwaysOn et les méthodes de clustering de SQL sont préférés avec Skype Entreprise Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Temps de récupération du serveur principal automatique avec mise en miroir de bases de données

Pour le failover principal automatique avec mise en miroir de bases de données, la cible d’ingénierie pour l’objectif de temps de récupération (RTO) est de 5 minutes. En raison de la mise en miroir synchrone des bases de données, nous n’anticipons pas la perte de données en cas de défaillance du serveur principal, sauf dans de rares cas où les serveurs frontaux et les serveurs frontaux sont en panne simultanément pendant que les données sont déplacées entre les serveurs. La cible d’ingénierie pour la perte de données maximale admissible (RPO, Recovery Point Objective) est de 5 minutes.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Expérience utilisateur en cas de défaillance du serveur principal avec la mise en miroir de bases de données

L’expérience utilisateur en cas de panne dépend de la nature de la panne et de votre topologie.
  
Si vous utilisez la mise en miroir de bases de données et qu’un témoin est configuré et que le principal échoue, le serveur principal échoue automatiquement et rapidement. Les utilisateurs actifs ne devraient pas remarquer d’interruption particulière de leurs sessions actives.
  
Si aucun témoin n’est configuré, l’administrateur peut perdre du temps à appeler manuellement le basculement. Pendant ce temps, les utilisateurs actifs peuvent s’en trouver affectés. Leurs sessions se poursuivent normalement pendant environ 30 minutes. Si le serveur principal n’est toujours pas restauré ou si un administrateur n’a pas basculé vers la sauvegarde, les utilisateurs basculent en mode Résistance, ce qui signifie qu’ils ne peuvent pas effectuer des tâches nécessitant une modification permanente sur Lync Server (par exemple, l’ajout d’un contact).
  
Si le serveur principal et les serveurs principaux en miroir tombent en panne, ou si l’un de ces derniers serveurs et le témoin tombent en panne, le serveur principal n’est alors plus disponible (même s’il fonctionne toujours). Dans ce cas, le mode de résilience s’active pour les utilisateurs actifs après une certaine durée.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Groupes de disponibilité AlwaysOn et instances de cluster de failover AlwaysOn

Skype Entreprise Server prend en charge les groupes de disponibilité AlwaysOn uniquement en tant qu’actifs/passifs, et non actifs/actifs. 
  
Pour utiliser des groupes de disponibilité AlwaysOn ou des instances de cluster de failover AlwaysOn, vous devez d’abord utiliser SQL Server pour configurer et configurer la solution de haute disponibilité. Vous pouvez ensuite utiliser le Générateur de topologie pour l’associer à un pool frontal.

Skype Entreprise Server prend en charge AlwaysOn avec les logiciels de base de données suivants :

- SQL Server 2019 Êdition Entreprise

- SQL Server 2019 Édition Standard limitations, voir la remarque ci-dessous

- SQL Server 2017 Êdition Entreprise

- SQL Server 2017 Édition Standard limitations, voir la remarque ci-dessous

- SQL Server 2016 Êdition Entreprise

- SQL Server 2016 Édition Standard limitations, voir la remarque ci-dessous

- SQL Server 2014 Êdition Entreprise
    
- SQL Server 2012 SP2 et CU2 Êdition Entreprise

> [!NOTE]
> SQL Server 2019, 2017 et 2016 sont les seules versions Skype Entreprise Server 2019.

> [!NOTE]
> Les groupes de  disponibilité Always On ne sont pas pris en charge dans SQL 2016, 2017 et 2019 Standard Editions, mais vous pouvez utiliser les instances de cluster de failover Always On. Pour en savoir plus, consultez les éditions et [les fonctionnalités SQL Server 2016.](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)
  
> [!IMPORTANT]
> Les noms d’instance de plusieurs instances de groupe de disponibilité AlwaysOn doivent être identiques. 
  
Pour obtenir la procédure de déploiement des groupes de disponibilité AlwaysOn, voir Déployer un groupe de disponibilité [AlwaysOn](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)sur un serveur principal dans Skype Entreprise Server .
  
## <a name="sql-server-failover-clustering"></a>SQL Server Clustering deover

Skype Entreprise Server prend en charge SQL Server clustering avec le logiciel de base de données suivant :
  
- SQL Server 2019, Êdition Entreprise et Édition Standard

- SQL Server 2017, Êdition Entreprise et Édition Standard

- SQL Server 2016, Êdition Entreprise et Édition Standard

- SQL Server 2014, Êdition Entreprise et Édition Standard
    
- SQL Server 2012 SP2 et CU2, à la fois Êdition Entreprise et Édition Standard

Pour utiliser SQL clustering deover, vous devez d’abord configurer le cluster SQL Server avant de déployer votre pool frontal. Pour obtenir les meilleures pratiques et les instructions de configuration pour le clustering de SQL Server 2012, voir [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) .

> [!NOTE]
> SQL Server 2019, 2017 et SQL Server 2016 sont les seules versions Skype Entreprise Server 2019.
    
Pour utiliser SQL clustering deover, vous devez d’abord configurer le cluster SQL Server avant de déployer votre pool frontal. Pour obtenir les meilleures pratiques et les instructions de configuration pour le clustering de SQL Server 2014 et 2016, voir [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) . Pour le clustering de SQL Server 2008, voir [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)) .
  
Lorsque vous installez SQL Server, pensez à installer SQL Server Management Studio pour la gestion des emplacements des fichiers de la base de données et des fichiers journaux. SQL Server Management Studio est installé en tant que composant facultatif lors de l’installation de SQL Server.
