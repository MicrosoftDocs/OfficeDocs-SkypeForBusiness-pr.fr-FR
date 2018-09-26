---
title: Déplacer le serveur d’administration centrale
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après avoir migré vers Skype pour Business Server 2019, vous devez déplacer le serveur d’administration centrale à le Skype pour Business Server 2019 serveur frontal ou un pool, avant de pouvoir supprimer le serveur hérité.
ms.openlocfilehash: 805b5c506fdda11bdc24144a0622e674e8ef281b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030524"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Atteindre le serveur de gestion centralisée hérité Skype pour Business Server 2019

Après avoir migré vers Skype pour Business Server 2019, et avant de pouvoir supprimer le serveur hérité, vous devez déplacer le serveur de gestion centralisée vers le Skype pour Business Server 2019 serveur frontal ou le pool. 
  
Le serveur de gestion centrale est un système maître/plusieurs réplicas, où la copie en lecture/écriture de la base de données est détenue par le serveur frontal qui contient le serveur d’administration centrale. Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur de gestion centralisée, dispose d’une copie en lecture seule des données du magasin Central de gestion de la base de SQL Server (appelée RTCLOCAL par défaut) installée sur l’ordinateur pendant l’installation et déploiement. La base de données local reçoit des mises à jour de réplica par l’entremise du Skype pour Business Server Agent réplica du réplicateur d’utilisateurs qui s’exécute en tant que service sur tous les ordinateurs. Le nom de la base de données sur le serveur de gestion centrale et du réplica local est XDS, qui est composée des fichiers xds.mdf et xds.ldf. L’emplacement de la base de données master est référencé par un point de contrôle de service (SCP) dans les Services de domaine Active Directory. Tous les outils qui utilisent le serveur d’administration centrale pour gérer et configurer Skype pour Business Server utilisent le SCP pour localiser le magasin Central de gestion.
  
Une fois que vous avez déplacé le serveur d’administration centrale, vous devez supprimer les bases de données du serveur de gestion centralisée depuis le serveur frontal d’origine. Pour plus d’informations sur la suppression des bases de données serveur de gestion centralisée, voir [Supprimer la base de données SQL Server pour un pool frontal](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Vous utilisez l’applet de commande Windows PowerShell **Move-CsManagementServer** dans la Skype pour Business Server Management Shell pour déplacer la base de données à partir de la base de données de SQL Server hérité d’installer le Skype pour la base de données Business Server 2019 SQL Server, puis mettre à jour le SCP pour pointer vers le Skype pour l’emplacement du serveur de gestion centralisée Business Server 2019. 
  
Utilisez les procédures de cette section pour préparer le Skype Business Server 2019 serveurs frontaux avant de déplacer le serveur d’administration centrale.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Pour préparer un pool frontal Enterprise Edition

1. Sur Skype pour Business Server 2019 Enterprise Edition un pool frontal où vous voulez déplacer le serveur d’administration centrale, ouvrez une session sur l’ordinateur où le Skype pour Business Server Management Shell est installé en tant que membre de la **RTCUniversalServerAdmins **groupe. Vous devez également droits sysadmin de base de données SQL Server et les autorisations sur la base de données où vous souhaitez installer le magasin Central de gestion. 
    
2. Ouvrez le Skype pour Business Server Management Shell.
    
3. Pour créer un nouveau magasin Central de gestion dans le Skype pour la base de données Business Server 2019 SQL Server, dans la Skype pour Business Server Management Shell, tapez :
    
  ```
  Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
  ```

4. Vérifiez que l’état du service **Skype pour Business Server frontal** est **démarré**.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Pour préparer un serveur Standard Edition serveur frontal

1. Sur Skype pour Business Server 2019 Standard Edition serveur frontal où vous voulez déplacer le serveur d’administration centrale, ouvrez une session sur l’ordinateur où le Skype pour Business Server Management Shell est installé en tant que membre de la **RTCUniversalServerAdmins **groupe. 
    
2. Ouvrez le Skype pour l’Assistant de déploiement Business Server.
    
3. Dans Skype pour l’Assistant de déploiement Business Server, cliquez sur **préparer premier serveur Standard Edition server**.
    
4. Dans la page **Exécution de commandes** , SQL Server Express est installé en tant que le serveur d’administration centrale. Règles de pare-feu nécessaires sont créés. Une fois l’installation de la base de données et les logiciels prérequis terminée, cliquez sur **Terminer**.
    
    > [!NOTE]
    > L’installation initiale peut prendre un certain temps avec aucune mise à jour visible à l’écran de résumé de sortie de commande. Il s’agit en raison de l’installation de SQL Server Express. Si vous avez besoin contrôler l’installation de la base de données, utilisez le Gestionnaire des tâches pour surveiller le programme d’installation. 
  
5. Pour créer le nouveau magasin Central de gestion sur le Skype pour Business Server 2019 Standard Edition serveur frontal, le Skype pour Business Server Management Shell, tapez : 
    
  ```
  Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
  ```

6. Vérifiez que l’état du service **Skype pour Business Server frontal** est **démarré**.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Pour déplacer que hérité installe le serveur de gestion centralisée pour Skype pour Business Server 2019

1. Sur Skype pour serveur Business Server 2019 qui sera le serveur de gestion centrale, ouvrez une session l’ordinateur où le Skype pour Business Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez également les droits administrateur de base de données SQL Server et les autorisations. 
    
2. Ouvrez Skype pour Business Server Management Shell.
    
3. Dans Skype pour Business Server Management Shell, tapez : 
    
  ```
  Enable-CsTopology
  ```

    > [!CAUTION]
    > Si `Enable-CsTopology` n’a pas réussi, résoudre le problème qui empêchent la commande avant de poursuivre. Si **Enable-CsTopology** ne réussit pas, le déplacement échoue et il peut laisser votre topologie dans un état où il n’y a aucun magasin Central de gestion. 
  
4. Sur la Skype pour un pool frontal ou Business Server 2019 serveur frontal, dans le Skype pour Business Server Management Shell, tapez : 
    
  ```
  Move-CsManagementServer
  ```

5. Skype pour Business Server Management Shell affiche les serveurs, magasins de fichiers, les magasins de base de données et les points de connexion de service de l’état actuel et l’état proposé. Lisez attentivement les informations et confirmez qu’il s’agit de la destination source et destination. Tapez **Y** pour continuer ou **N** pour arrêter le déplacement. 
    
6. Passez en revue les avertissements ou erreurs générées par la commande **Move-CsManagementServer** et résolvez-les. 
    
7. Sur Skype pour Business Server 2019 server, ouvrez le Skype pour l’Assistant de déploiement Business Server. 
    
8. Dans Skype pour l’Assistant de déploiement Business Server, cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**, cliquez sur **étape 2 : installer ou supprimer des Skype pour les composants du serveur Business**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer **. 
    
9. Sur hérité installer server, ouvrez l’Assistant déploiement. 
    
10. Dans Skype pour l’Assistant de déploiement Business Server, cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**, cliquez sur **étape 2 : installer ou supprimer des Skype pour les composants du serveur Business**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer **. 
    
11. Redémarrez le Skype pour serveur Business Server 2019. Cela est nécessaire en raison d’une modification de l’appartenance de groupe pour la base de données du serveur de gestion centralisée.
    
12. Pour confirmer que la réplication avec la gestion centralisée nouveau magasin est en cours, dans le Skype pour Business Server Management Shell, tapez : 
    
  ```
  Get-CsManagementStoreReplicationStatus
  ```

    > [!NOTE]
    > La réplication peut prendre un certain temps pour mettre à jour tous les réplicas. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Pour supprimer hérité pour installer les fichiers du magasin Central de gestion après un déplacement

1. Sur hérité installation du serveur, ouvrez une session sur l’ordinateur où le Skype pour Business Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez également les droits administrateur de base de données SQL Server et les autorisations. 
    
2. Ouvrez Skype pour Business Server Management Shell
    
    > [!CAUTION]
    > Ne poursuivez pas la suppression des fichiers de base de données précédente jusqu'à ce que la réplication est terminée et est stable. Si vous supprimez les fichiers avant la fin de la réplication, vous interrompre le processus de réplication et laisser le serveur de gestion centralisée déplacé dans un état inconnu. Utilisez l’applet de commande **Get-CsManagementStoreReplicationStatus** pour vérifier l’état de réplication. 
  
3. Pour supprimer les fichiers de base de données du magasin Central de gestion de l’installation héritée de serveur de gestion centralisée, tapez :
    
  ```
  Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
  ```

    Par exemple :
    
  ```
  Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
  ```

    Où les _ \<nom de domaine complet de SQL Server\> _ est hérité soit installer un serveur principal dans un déploiement Enterprise Edition ou le nom de domaine complet du serveur Standard Edition. 
    

