---
title: Déplacer le serveur de gestion centralisée
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après avoir effectué une migration vers Skype entreprise Server 2019, vous devez déplacer le serveur de gestion centralisée vers le serveur frontal ou le pool Skype entreprise Server 2019 avant de pouvoir supprimer le serveur hérité.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752466"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Déplacer le serveur de gestion centralisée hérité vers Skype entreprise Server 2019

Après avoir effectué la migration vers Skype entreprise Server 2019 et avant de pouvoir supprimer le serveur hérité, vous devez déplacer le serveur de gestion centralisée vers le serveur ou le pool de Skype entreprise Server 2019. 
  
Le serveur de gestion centralisée est un système de réplication maître/multiple unique, dans lequel la copie en lecture/écriture de la base de données est conservée par le serveur frontal qui contient le serveur de gestion centralisée. Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur de gestion centralisée, dispose d’une copie en lecture seule des données du magasin central de gestion dans la base de données SQL Server (nommée RTCLOCAL par défaut) installée sur l’ordinateur lors de l’installation et du déploiement. La base de données locale reçoit les mises à jour de réplica par le biais de l’agent réplicateur de réplicas de Skype entreprise qui s’exécute en tant que service sur tous les ordinateurs. Le nom de la base de données réelle sur le serveur de gestion centralisée et le réplica local est XDS, composé des fichiers XDS. mdf et XDS. ldf. L’emplacement de la base de données maître est référencé par un point de contrôle de service (SCP) dans les services de domaine Active Directory. Tous les outils qui utilisent le serveur de gestion centralisée pour gérer et configurer Skype entreprise Server utilisent le SCP pour localiser le magasin central de gestion.
  
Une fois que vous avez réussi à déplacer le serveur de gestion centralisée, vous devez supprimer les bases de données du serveur de gestion centralisée à partir du serveur frontal d’origine. Pour plus d’informations sur la suppression des bases de données du serveur de gestion centralisée, consultez [la rubrique Remove the SQL Server Database for a front end pool](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Vous utilisez l’applet de commande Windows PowerShell **Move-CsManagementServer** dans Skype for Business Server Management Shell pour déplacer la base de données de la base de données SQL Server héritée vers la base de données sql Server 2019 de Skype entreprise Server, puis mettre à jour le point de gestion de la mise à niveau vers l’emplacement du serveur de gestion centralisée de Skype entreprise Server 2019. 
  
Utilisez les procédures de cette section pour préparer les serveurs frontaux Skype entreprise Server 2019 avant de déplacer le serveur de gestion centralisée.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Pour préparer un pool frontal Enterprise Edition

1. Dans le pool frontal Skype entreprise Server 2019 Enterprise Edition où vous voulez déplacer le serveur de gestion centralisée, ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez également disposer des droits et des autorisations d’utilisateur sysadmin de la base de données SQL Server sur la base de données où vous souhaitez installer le magasin central de gestion. 
    
2. Ouvrez Skype entreprise Server Management Shell.
    
3. Pour créer le nouveau magasin central de gestion dans la base de données de Skype entreprise Server 2019 de la base de données SQL Server, dans Skype entreprise Server Management Shell, tapez :
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Vérifiez que l’état du service **frontal Skype entreprise Server** est **démarré**.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Pour préparer un serveur frontal Standard Edition

1. Sur le serveur frontal Skype entreprise Server 2019 Standard Edition où vous voulez déplacer le serveur de gestion centralisée, ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** . 
    
2. Ouvrez l’Assistant Déploiement de Skype entreprise Server.
    
3. Dans l’Assistant Déploiement de Skype entreprise Server, cliquez sur **préparer d’abord le serveur Standard Edition**.
    
4. Sur la page **exécution de commandes** , SQL Server Express est installé en tant que serveur de gestion centralisée. Les règles de pare-feu nécessaires sont créées. Lorsque l’installation de la base de données et des logiciels prérequis est terminée, cliquez sur **Terminer**.
    
    > [!NOTE]
    > L’installation initiale peut durer un certain temps sans que les mises à jour ne soient visibles sur l’écran récapitulatif des résultats de la commande. Ceci est dû à l’installation de SQL Server Express. Pour surveiller l’installation de la base de données, utilisez le Gestionnaire des tâches. 
  
5. Pour créer le nouveau magasin central de gestion sur le serveur frontal Skype entreprise Server 2019 Standard Edition, dans Skype entreprise Server Management Shell, tapez : 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Vérifiez que l’état du service **frontal Skype entreprise Server** est **démarré**.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Pour déplacer le serveur de gestion centralisée des installations héritées vers Skype entreprise Server 2019

1. Sur le serveur Skype entreprise Server 2019 qui sera le serveur de gestion centralisée, connectez-vous à l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez aussi disposer des droits et autorisation d’administrateur système sur la base de données SQL. 
    
2. Ouvrez Skype entreprise Server Management Shell (exécuter en tant qu’administrateur).
    
3. Dans Skype entreprise Server Management Shell, tapez : 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Si ce `Enable-CsTopology` n’est pas le cas, résolvez le problème en empêchant la commande de se terminer avant de continuer. Si **Enable-CsTopology** ne réussit pas, le déplacement échoue et il peut laisser votre topologie dans un État où il n’existe pas de magasin central de gestion. 
  
4. Sur le serveur frontal ou le pool frontal Skype entreprise Server 2019, dans Skype entreprise Server Management Shell, tapez : 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype entreprise Server Management Shell affiche les serveurs, les magasins de fichiers, les magasins de bases de données et les points de connexion au service de l’état actuel et de l’État proposé. Lisez soigneusement les informations et confirmez qu’il s’agit de la source et de la destination prévues. Tapez **Y** pour continuer, ou **N** pour cesser le déplacement. 
    
6. Examinez l’ensemble des erreurs et des avertissements générés par la commande **Move-CsManagementServer** et corrigez-les. 
    
7. Sur le serveur Skype entreprise Server 2019, ouvrez l’Assistant Déploiement de Skype entreprise Server. 
    
8. Dans l’Assistant Déploiement de Skype entreprise Server, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**, cliquez sur **étape 2 : installer ou supprimer des composants Skype entreprise Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**. 
    
9. Sur le serveur d’installation hérité, ouvrez l’Assistant déploiement. 
    
10. Dans l’Assistant Déploiement de Skype entreprise Server, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**, cliquez sur **étape 2 : installer ou supprimer des composants Skype entreprise Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**. 
    
11. Redémarrez le serveur Skype entreprise Server 2019. Ceci est nécessaire en raison d’une modification de l’appartenance au groupe vers la base de données du serveur de gestion centralisée.
    
12. Pour confirmer que la réplication avec le nouveau magasin central de gestion est en cours, dans Skype entreprise Server Management Shell, tapez : 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > La réplication peut prendre un certain temps pour mettre à jour tous les réplicas. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Pour supprimer les fichiers du magasin central de gestion d’installation héritée après un déplacement

1. Sur le serveur d’installation hérité, ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez aussi disposer des droits et autorisation d’administrateur système sur la base de données SQL. 
    
2. Ouvrir Skype entreprise Server Management Shell
    
    > [!CAUTION]
    > Ne procédez pas à la suppression des fichiers de base de données précédents avant que la réplication ne soit terminée et stable. Si vous supprimez les fichiers avant de terminer la réplication, vous interrompez le processus de réplication et laissez le nouveau serveur de gestion centrale déplacé dans un état inconnu. Utilisez l’applet de commande **Get-CsManagementStoreReplicationStatus** pour confirmer le statut de réplication. 
  
3. Pour supprimer les fichiers de base de données du magasin central de gestion du serveur de gestion centralisée d’installation héritée, tapez :
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Par exemple :
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Où _\<FQDN of SQL Server\>_ est le serveur principal install hérité dans un déploiement Enterprise Edition ou le nom de domaine complet (FQDN) du serveur Standard Edition Server. 
    

