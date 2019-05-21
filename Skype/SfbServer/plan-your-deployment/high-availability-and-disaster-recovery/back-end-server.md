---
title: Haute disponibilité du serveur principal dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: En savoir plus sur les options de haute disponibilité du serveur principal prises en charge dans Skype entreprise Server, y compris les groupes de disponibilité AlwaysOn, les instances de cluster de basculement, la mise en miroir de base de données et la mise en cluster de basculement SQL.
ms.openlocfilehash: db732d106546e5139725713da28bcb9c8b82bb93
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297483"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Haute disponibilité du serveur principal dans Skype entreprise Server
 
En savoir plus sur les options de haute disponibilité du serveur principal prises en charge dans Skype entreprise Server, y compris les groupes de disponibilité AlwaysOn, les instances de cluster de basculement, la mise en miroir de base de données et la mise en cluster de basculement SQL.
  
Pour améliorer la haute disponibilité de vos serveurs principaux, vous disposez de quatre options :
  
- Mise en miroir de bases de données
    
- Groupes de disponibilité AlwaysOn
    
- Instances AlwaysOn du cluster de basculement (ICF)
    
- Clustering SQL avec basculement
    
L’utilisation d’une de ces solutions est facultative mais est recommandée pour préserver la continuité des activités de votre organisation. Dans le cas contraire, le fait de disposer d’un serveur de base de données unique peut entraîner la perte de données significatives de Skype entreprise Server. 
  
Vous pouvez configurer la mise en miroir de la base de données à l’aide du seul générateur de topologie. Pour les groupes de disponibilité AlwaysOn, les instances de clusters de basculement AlwaysOn ou le cluster de basculement SQL, vous devez utiliser SQL Server pour créer la solution de haute disponibilité, vous pouvez utiliser le générateur de topologie pour l’associer à un pool frontal.
  
Si vous utilisez la haute disponibilité du serveur principal sur un pool frontal couplé à un autre pool frontal de reprise après sinistre, vous devez utiliser la même solution de haute disponibilité back-end dans les deux pools. 
  
## <a name="database-mirroring"></a>Mise en miroir de bases de données

Skype entreprise Server prend en charge la mise en miroir avec le logiciel de base de données suivant:
  
- SQL Server 2017, éditions Enterprise et Edition standard

- SQL Server 2016, éditions Enterprise et Edition standard

- SQL Server 2014, éditions Enterprise et Edition standard
    
- SQL Server 2012 SP2 et CU2, éditions Enterprise et Edition standard
    

> [!NOTE]
> La mise en miroir SQL est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de clusters de basculement AlwaysOn (ICF) et les méthodes de regroupement de relais SQL sont préférés dans Skype entreprise Server 2019.
    
La mise en miroir de base de données asynchrone n’est pas prise en charge pour la haute disponibilité du serveur principal dans Skype entreprise Server. Dans le reste du document, sauf mention explicite, la mise en miroir sous-entend une mise en miroir synchrone. 
  
Lorsque vous déployez la mise en miroir de base de données dans une liste frontale, toutes les bases de données Skype entreprise Server du pool sont mises en miroir, y compris la Banque centrale de gestion, si elles se trouvent dans ce pool, ainsi que la base de données d’application et le parc d’appels. base de données d’application, si ces applications sont exécutées dans le pool. 
  
La mise en miroir de base de données vous permet de ne pas avoir à utiliser de stockage partagé pour les serveurs. Chaque serveur garde sa copie des bases de données en local. 
  
Vous pouvez déployer la mise en miroir de base de données avec ou sans témoin. Cela dit, nous vous recommandons d’en utiliser un, car il permet le basculement automatique du serveur principal. Dans le cas contraire, un administrateur doit appeler le basculement manuellement. Notez que même si un témoin est déployé, un administrateur peut au besoin appeler manuellement le basculement du serveur principal.
  
Si vous utilisez un témoin, celui-ci peut servir pour plusieurs paires de serveurs principaux. Il n’y a aucune correspondance stricte un-à-un entre les témoins et les paires de serveurs principaux. Les déploiements utilisant un seul témoin pour plusieurs paires de serveurs principaux ne sont simplement pas aussi résilients que les topologies faisant appel à un témoin à part pour chaque paire de serveurs principaux. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Directives pour la planification de la mise en miroir du serveur frontal

En général, la configuration de la mise en miroir SQL entre deux serveurs principaux avec un témoin exige ce qui suit :
  
- La version du serveur principal de SQL Server doit prendre en charge la mise en miroir SQL.
    
- Le principal, le miroir et le témoin (s’il est déployé) doivent disposer de la même version de SQL Server. 
    
- Le principal et le miroir doivent disposer de la même édition de SQL Server. Le témoin peut en avoir une différente.
    
Pour les meilleures pratiques SQL en ce qui concerne les versions SQL prises en charge pour un rôle de témoin, voir [«témoin de mise en miroir de base de données»](https://go.microsoft.com/fwlink/p/?LinkId=247345) dans MSDN Library.
  
Avant de configurer la mise en miroir des serveurs, vous devez d’abord configurer les autorisations de base de données SQL correctement. Pour plus d’informations, consultez [la section «configurer des comptes de connexion pour la mise en miroir de base de données ou les groupes AlwaysOn de disponibilité (SQL Server)»](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Avec la mise en miroir SQL, le mode de récupération de la base de données a toujours la valeur **Complète**, ce qui signifie que vous devez surveiller de près la taille du journal des transactions et sauvegarder les journaux des transactions de manière régulière afin d’éviter toute insuffisance d’espace disque sur les serveurs principaux. La fréquence des sauvegardes des journaux des transactions dépend de la vitesse à laquelle leur taille augmente, laquelle dépend à son tour des transactions de base de données induites par les activités des utilisateurs sur le pool frontal. Nous vous recommandons d’estimer l’accroissement des journaux des transactions pour la charge de travail de votre déploiement Lync afin de procéder à une planification en conséquence. Les articles suivants fournissent des informations supplémentaires sur la gestion des journaux et sauvegardes SQL :
  
> [!IMPORTANT]
> Le recours au générateur de topologie ou aux cmdlets pour configurer et supprimer la mise en miroir SQL est uniquement pris en charge lorsque les serveurs principal, miroir et témoin (le cas échéant) appartiennent tous au même domaine. Si vous voulez configurer la mise en miroir SQL entre des serveurs de différents domaines, reportez-vous à votre documentation SQL Server. 

> [!NOTE]
> La mise en miroir SQL est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de clusters de basculement AlwaysOn (ICF) et les méthodes de regroupement de relais SQL sont préférés dans Skype entreprise Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Temps de récupération pour le basculement automatique de serveur principal avec la mise en miroir de base de données

Pour le basculement automatique de serveur principal avec la mise en miroir de base de données, la cible d’ingénierie pour la durée maximale d’interruption admissible (RTO, Recovery Time Objective) est de 5 minutes. Par l’usage de la mise en miroir de base de données synchrone, nous ne prévoyons pas de perte de données en cas de panne du serveur principal sauf dans de rares cas où les serveurs frontaux et le serveur principal s’arrêtent de fonctionner en même temps pendant un transfert de données entre les serveurs. La cible d’ingénierie pour la perte de données maximale admissible (RPO, Recovery Point Objective) est de 5 minutes.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Expérience utilisateur en cas de panne du serveur principal avec la mise en miroir de base de données

L’expérience utilisateur en cas de panne dépend de la nature de la panne et de votre topologie.
  
Si vous utilisez la mise en miroir de base de données et avez configuré un témoin et qu’une panne se produit au niveau du serveur principal, le basculement du serveur principal se fait automatiquement et rapidement. Les utilisateurs actifs ne devraient pas remarquer d’interruption particulière de leurs sessions actives.
  
Si aucun témoin n’est configuré, l’administrateur peut perdre du temps à appeler manuellement le basculement. Pendant ce temps, les utilisateurs actifs peuvent s’en trouver affectés. Leurs sessions se poursuivent normalement pendant environ 30 minutes. Si le serveur principal n’est toujours pas restauré ou s’il n’a pas pu basculer vers la sauvegarde, les utilisateurs sont basculés vers le mode de résilience, ce qui signifie qu’ils ne sont pas en mesure d’effectuer des tâches nécessitant un changement permanent sur le serveur Lync (par exemple, ajouter un contact).
  
Si le serveur principal et les serveurs principaux en miroir tombent en panne, ou si l’un de ces derniers serveurs et le témoin tombent en panne, le serveur principal n’est alors plus disponible (même s’il fonctionne toujours). Dans ce cas, le mode de résistance s’active pour les utilisateurs actifs après une certaine durée.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Groupes de disponibilité AlwaysOn et instances de cluster de basculement AlwaysOn

Skype entreprise Server prend en charge les groupes de disponibilité alwaysable uniquement en tant que actif/passif, pas actif/actif. 
  
Pour utiliser les groupes de disponibilité AlwaysOn ou les instances de cluster de basculement AlwaysOn, vous devez commencer par utiliser SQL Server pour configurer et configurer la solution de haute disponibilité. Vous pouvez ensuite utiliser le générateur de topologie pour l’associer à un pool frontal.

Skype entreprise Server prend en charge AlwaysOn avec le logiciel de base de données suivant:

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition avec des limitations, voir la remarque ci-dessous

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition avec des limitations, voir la remarque ci-dessous

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 et CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2017 et SQL Server 2016 sont les seules versions prises en charge par Skype entreprise Server 2019.

> [!NOTE]
> Toujours sur les groupes de disponibilité n’est **pas** pris en charge dans les éditions SQL 2016 et 2017 standard, mais vous pouvez les utiliser toujours sur les instances de cluster de basculement. Pour en savoir plus [, voir Éditions et fonctionnalités prises en charge de SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) .
  
> [!IMPORTANT]
> Les noms d’instances pour plusieurs instances de groupe de disponibilité AlwaysOn doivent être identiques. 
  
Pour connaître la procédure de déploiement des groupes de disponibilité AlwaysOn, voir [déployer un groupe de disponibilité Alwaysn sur un serveur principal dans Skype entreprise Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>Clustering de basculement de SQL Server

Skype entreprise Server prend en charge le regroupement SQL Server Failover avec le logiciel de base de données suivant:
  
- SQL Server 2017, éditions Enterprise et Edition standard

- SQL Server 2016, éditions Enterprise et Edition standard

- SQL Server 2014, éditions Enterprise et Edition standard
    
- SQL Server 2012 SP2 et CU2, éditions Enterprise et Edition standard

Pour utiliser le regroupement SQL Failover, vous devez d’abord configurer et configurer le cluster SQL Server avant de déployer votre pool frontal. Pour obtenir des recommandations et des instructions de configuration pour la mise en cluster de basculement dans SQL Server 2012, voir [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx).

> [!NOTE]
> SQL Server 2017 et SQL Server 2016 sont les seules versions prises en charge par Skype entreprise Server 2019.
    
Pour utiliser le regroupement SQL Failover, vous devez d’abord configurer et configurer le cluster SQL Server avant de déployer votre pool frontal. Pour obtenir des recommandations et des instructions de configuration pour la mise en cluster de basculement dans [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx)SQL Server 2014 et 2016, voir. Pour la mise en cluster de basculement dans SQL [https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx)Server 2008, voir.
  
Lorsque vous installez SQL Server, vous devez installer SQL Server Management Studio pour gérer les emplacements des bases de données et des fichiers journaux. SQL Server Management Studio est installé en tant que composant facultatif lorsque vous installez SQL Server.
  

