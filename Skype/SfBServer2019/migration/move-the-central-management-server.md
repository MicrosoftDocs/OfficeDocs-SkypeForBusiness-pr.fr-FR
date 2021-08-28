---
title: Déplacer le serveur central de gestion
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Après avoir migré vers Skype Entreprise Server 2019, vous devez déplacer le serveur de gestion centralisée vers le pool ou le serveur frontal Skype Entreprise Server 2019, avant de pouvoir supprimer le serveur hérité.
ms.openlocfilehash: 5c3d090f762904aa5f076033a68e46139b1e84e4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618280"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Déplacer le serveur de gestion centralisée hérité vers Skype Entreprise Server 2019

Après avoir migré vers Skype Entreprise Server 2019 et avant de pouvoir supprimer le serveur hérité, vous devez déplacer le serveur de gestion centrale vers le pool ou le serveur frontal Skype Entreprise Server 2019. 
  
Le serveur central de gestion est un système de réplicas maître/multiple unique, où la copie en lecture/écriture de la base de données est détenue par le serveur frontal qui contient le serveur central de gestion. Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur central de gestion, dispose d’une copie en lecture seule des données du magasin central de gestion dans la base de données SQL Server (nommée RTCLOCAL par défaut) installée sur l’ordinateur lors de l’installation et du déploiement. La base de données locale reçoit les mises à jour du réplica par le Skype Entreprise Server réplicateur de réplicas qui s’exécute en tant que service sur tous les ordinateurs. Le nom de la base de données réelle sur le serveur central de gestion et du réplica local est XDS, qui est composé des fichiers xds.mdf et xds.ldf. L’emplacement de la base de données maître est référencé par un point de contrôle de service (SCP) dans les services de domaine Active Directory. Tous les outils qui utilisent le serveur central de gestion pour gérer et configurer Skype Entreprise Server utiliser le SCP pour localiser le magasin central de gestion.
  
Une fois que vous avez déplacé le serveur central de gestion, vous devez supprimer les bases de données du serveur central de gestion du serveur frontal d’origine. Pour plus d’informations sur la suppression des bases de données du serveur central de gestion, voir [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Vous utilisez l’Windows PowerShell cmdlet **Move-CsManagementServer** dans l’Skype Entreprise Server Management Shell pour déplacer la base de données de l’installation SQL Server héritée vers la base de données SQL Server Skype Entreprise Server 2019, puis mettez à jour le point de contrôle de pointage vers l’emplacement du serveur central de gestion Skype Entreprise Server 2019. 
  
Utilisez les procédures de cette section pour préparer les serveurs frontaux Skype Entreprise Server 2019 avant de déplacer le serveur central de gestion.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Pour préparer un pool Êdition Entreprise frontal

1. Sur le pool frontal Skype Entreprise Server 2019 Êdition Entreprise où vous souhaitez déplacer le serveur central de gestion, connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins.** Vous devez également avoir SQL Server droits et autorisations utilisateur sysadmin de base de données sur la base de données où vous souhaitez installer le magasin central de gestion. 
    
2. Ouvrez l Skype Entreprise Server Management Shell.
    
3. Pour créer le magasin central de gestion dans la base Skype Entreprise Server de données SQL Server 2019, dans Skype Entreprise Server Management Shell, tapez :
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Confirmez que l’état **du service Skype Entreprise Server frontal** est **démarré.**
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Pour préparer un serveur Édition Standard frontal

1. Sur le serveur frontal Skype Entreprise Server 2019 Édition Standard où vous souhaitez déplacer le serveur central de gestion, connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins.** 
    
2. Ouvrez l Skype Entreprise Server de déploiement.
    
3. Dans l’Assistant Skype Entreprise Server déploiement, cliquez **sur Préparer d’Édition Standard serveur.**
    
4. Dans la page **Exécution de commandes,** SQL Server Express est installé en tant que serveur central de gestion. Les règles de pare-feu nécessaires sont créées. Lorsque l’installation de la base de données et des logiciels prérequis est terminée, cliquez sur **Terminer**.
    
    > [!NOTE]
    > L’installation initiale peut durer un certain temps sans que les mises à jour ne soient visibles sur l’écran récapitulatif des résultats de la commande. Cela est dû à l’installation de SQL Server Express. Pour surveiller l’installation de la base de données, utilisez le Gestionnaire des tâches. 
  
5. Pour créer le magasin central de gestion sur le serveur frontal Skype Entreprise Server 2019 Édition Standard, dans Skype Entreprise Server Management Shell, tapez : 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Confirmez que l’état **du service Skype Entreprise Server frontal** est **démarré.**
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Pour déplacer l’installation héritée de Central Management Server vers Skype Entreprise Server 2019

1. Sur le serveur Skype Entreprise Server 2019 qui sera le serveur central de gestion, connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins.** Vous devez aussi disposer des droits et autorisation d’administrateur système sur la base de données SQL. 
    
2. Ouvrez Skype Entreprise Server Management Shell (exécuter en tant qu’administrateur).
    
3. Dans l’Skype Entreprise Server Management Shell, tapez : 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Si `Enable-CsTopology` l’opération ne réussit pas, résolvez le problème en empêchant la commande de se terminer avant de continuer. En **cas d’échec d’Enable-CsTopology,** le déplacement échouera et votre topologie risque d’être dans un état où il n’y a pas de magasin central de gestion. 
  
4. Sur le Skype Entreprise Server frontal ou le pool frontal 2019, dans Skype Entreprise Server Management Shell, tapez : 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype Entreprise Server Management Shell affiche les serveurs, les magasins de fichiers, les magasins de bases de données et les points de connexion de service de l’état actuel et de l’état proposé. Lisez soigneusement les informations et confirmez qu’il s’agit de la source et de la destination prévues. Tapez **Y** pour continuer, ou **N** pour cesser le déplacement. 
    
6. Examinez l’ensemble des erreurs et des avertissements générés par la commande **Move-CsManagementServer** et corrigez-les. 
    
7. Sur le Skype Entreprise Server 2019, ouvrez l’Assistant Skype Entreprise Server Déploiement. 
    
8. Dans Skype Entreprise Server Assistant Déploiement, cliquez sur Installer ou mettre à jour le système **Skype Entreprise Server,** cliquez sur Étape 2 : Installer ou supprimer des **composants Skype Entreprise Server,** cliquez sur **Suivant,** consultez le résumé, puis cliquez sur **Terminer.** 
    
9. Sur le serveur d’installation hérité, ouvrez l’Assistant Déploiement. 
    
10. Dans Skype Entreprise Server Assistant Déploiement, cliquez sur Installer ou mettre à jour le système **Skype Entreprise Server,** cliquez sur Étape 2 : Installer ou supprimer des **composants Skype Entreprise Server,** cliquez sur **Suivant,** consultez le résumé, puis cliquez sur **Terminer.** 
    
11. Redémarrez le serveur Skype Entreprise Server 2019. Cette modification est requise en raison d’un changement d’appartenance à un groupe pour accéder à la base de données du serveur central de gestion.
    
12. Pour confirmer que la réplication avec le nouveau magasin central de gestion a lieu, dans l’Skype Entreprise Server Management Shell, tapez : 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > La réplication peut prendre un certain temps pour mettre à jour tous les réplicas. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Pour supprimer les fichiers du magasin central de gestion d’installation hérités après un déplacement

1. Sur le serveur d’installation hérité, connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins.** Vous devez aussi disposer des droits et autorisation d’administrateur système sur la base de données SQL. 
    
2. Ouvrir Skype Entreprise Server Management Shell
    
    > [!CAUTION]
    > Ne procédez pas à la suppression des fichiers de base de données précédents avant que la réplication ne soit terminée et stable. Si vous supprimez les fichiers avant la fin de la réplication, vous interrompez le processus de réplication et laissez le serveur central de gestion récemment déplacé dans un état inconnu. Utilisez l’applet de commande **Get-CsManagementStoreReplicationStatus** pour confirmer le statut de réplication. 
  
3. Pour supprimer les fichiers de base de données du magasin central de gestion du serveur de gestion central d’installation hérité, tapez :
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Par exemple :
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Où il s’agit du serveur principal d’installation hérité dans un déploiement Êdition Entreprise ou du nom de Édition Standard _\<FQDN of SQL Server\>_ serveur. 
    

