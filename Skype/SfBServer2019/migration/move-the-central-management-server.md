---
title: Déplacer le serveur de gestion central
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après la migration vers Skype entreprise Server 2019, vous devez déplacer le serveur de gestion central vers le serveur ou le pool frontal de Skype entreprise Server 2019 avant de pouvoir supprimer le serveur hérité.
ms.openlocfilehash: b6a2dd08949b5b15370f27e1da936009048982f6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990929"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Déplacer le serveur de gestion central hérité vers Skype entreprise Server 2019

Après avoir effectué une migration vers Skype entreprise Server 2019 et que vous ne pouvez pas supprimer le serveur hérité, vous devez déplacer le serveur de gestion central vers le serveur principal ou le pool Skype entreprise Server 2019. 
  
Le serveur de gestion central est un système de réplication maître/multiple unique, où la copie en lecture/écriture de la base de données est stockée par le serveur frontal qui contient le serveur de gestion central. Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur de gestion central, dispose d’une copie en lecture seule de la base de données centrale de gestion de la base de données SQL Server (nommée RTCLOCAL par défaut) installée sur l’ordinateur lors de l’installation et développement. La base de données locale reçoit les mises à jour de réplica par le biais de l’agent de réplicateur de réplicas Skype entreprise Server exécuté en tant que service sur tous les ordinateurs. Le nom de la base de données réelle du serveur de gestion central et du réplica local est XDS, qui est constitué des fichiers XDS. mdf et XDS. ldf. L’emplacement de la base de données maître est référencé par un point de contrôle de service (SCP) dans les services de domaine Active Directory (AD DS). Tous les outils qui utilisent le serveur de gestion central pour gérer et configurer Skype entreprise Server utilisent le SCP pour trouver le magasin de gestion central.
  
Après avoir déplacé le serveur de gestion central, vous devez supprimer les bases de données du serveur principal de gestion du serveur frontal initial. Pour plus d’informations sur la suppression de la base de données de serveur de gestion centrale, voir [Supprimer la base de données SQL Server d’un pool frontal](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Pour déplacer la base de données de la base de données SQL Server héritée dans la base de données SQL Server de Skype entreprise Server 2019, vous devez utiliser l’applet de la cmdlet Windows PowerShell **Move-CsManagementServer** dans la base de données SQL Server de Skype entreprise Server, puis mettre à jour le SCP pour qu’il pointe vers l’emplacement du serveur de gestion central de Skype entreprise Server 2019. 
  
Suivez les procédures décrites dans cette section pour préparer les serveurs front-end Skype entreprise Server 2019 avant de déplacer le serveur de gestion central.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Pour préparer un pool frontal Enterprise Edition

1. Dans le pool frontal de Skype entreprise Server 2019 Enterprise Edition sur lequel vous voulez déplacer le serveur de gestion central, connectez-vous à l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez également disposer des droits d’utilisateur sysadmin et des autorisations de la base de données SQL Server sur la base de données dans laquelle vous voulez installer le centre de gestion central. 
    
2. Ouvrez Skype entreprise Server Management Shell.
    
3. Pour créer la nouvelle Banque centrale de gestion dans la base de données SQL Server 2019 de Skype entreprise Server, dans Skype entreprise Server Management Shell, tapez :
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Vérifiez que l’état du service **frontal Skype entreprise Server** est **démarré**.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Pour préparer un serveur frontal Standard Edition

1. Sur le serveur frontal Skype entreprise Server 2019 Standard Edition sur lequel vous voulez déplacer le serveur de gestion central, connectez-vous à l’ordinateur sur lequel est installé Skype entreprise Server Management Shell en tant que membre du groupe **RTCUniversalServerAdmins** . 
    
2. Ouvrez l’Assistant Déploiement de Skype entreprise Server.
    
3. Dans l’Assistant Déploiement de Skype entreprise Server, cliquez sur **préparer le premier serveur Standard Edition**.
    
4. Sur la page **exécution des commandes** , SQL Server Express est installé en tant que serveur de gestion central. Des règles de pare-feu nécessaires sont créées. Lorsque l’installation de la base de données et du logiciel requis est terminée, cliquez sur **Terminer**.
    
    > [!NOTE]
    > L’installation initiale risque de prendre un certain temps sans qu’aucune mise à jour ne s’affiche à l’écran de synthèse de la sortie de commande. Le problème est dû à l’installation de SQL Server Express. Si vous avez besoin de surveiller l’installation de la base de données, utilisez le gestionnaire des tâches pour contrôler la configuration. 
  
5. Pour créer la nouvelle Banque centrale de gestion sur le serveur frontal Skype entreprise Server 2019 Standard Edition, dans Skype entreprise Server Management Shell, tapez : 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Vérifiez que l’état du service **frontal Skype entreprise Server** est **démarré**.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Pour déplacer le serveur de gestion central des installations héritées vers Skype entreprise Server 2019

1. Sur le serveur Skype entreprise Server 2019 qui sera le serveur de gestion central, connectez-vous à l’ordinateur sur lequel est installé Skype entreprise Server Management Shell en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez également avoir les autorisations et les droits d’utilisateur de l’administrateur de base de données SQL Server. 
    
2. Ouvrez Skype entreprise Server Management Shell (exécuter en tant qu’administrateur).
    
3. Dans Skype entreprise Server Management Shell, tapez : 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Si `Enable-CsTopology` ce n’est pas le cas, résolvez le problème empêchant l’exécution de la commande avant de poursuivre. Si **Enable-CsTopology** ne fonctionne pas, le déplacement échoue et il peut arriver que votre topologie soit dans un État où il n’y a aucune banque centrale de gestion. 
  
4. Dans Skype entreprise Server 2019 front end Server ou pool frontal, dans Skype entreprise Server Management Shell, tapez : 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype entreprise Server Management Shell affiche les serveurs, les magasins de fichiers, les magasins de bases de données et les points de connexion de service de l’état actuel et de l’État proposé. Lisez attentivement les informations et confirmez qu’il s’agit de la source et de la destination attendues. Tapez **Y** pour continuer ou **N** pour arrêter le déplacement. 
    
6. Examinez les avertissements ou erreurs générés par la commande **Move-CsManagementServer** et résolvez-les. 
    
7. Sur le serveur 2019 de Skype entreprise Server, ouvrez l’Assistant Déploiement de Skype entreprise Server. 
    
8. Dans l’Assistant Déploiement de Skype entreprise Server, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**, cliquez sur **étape 2 : configurer ou supprimer des composants Skype entreprise Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**. 
    
9. Sur le serveur d’installation hérité, ouvrez l’Assistant déploiement. 
    
10. Dans l’Assistant Déploiement de Skype entreprise Server, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**, cliquez sur **étape 2 : configurer ou supprimer des composants Skype entreprise Server**, cliquez sur **suivant**, passez en revue le résumé, puis cliquez sur **Terminer**. 
    
11. Redémarrez le serveur Skype entreprise Server 2019. Ceci est requis en raison d’une modification d’appartenance de groupe à une base de données du serveur de gestion centralisée.
    
12. Pour vérifier que la réplication avec le nouveau magasin central de gestion est en cours, dans la base de connaissances Skype entreprise Server Management Shell, tapez : 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > La réplication risque de prendre un certain temps pour mettre à jour tous les réplicas actuels. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Pour supprimer des fichiers du magasin de gestion de la gestion des installations héritées après un déplacement

1. Sur le serveur d’installation hérité, connectez-vous à l’ordinateur sur lequel est installé Skype entreprise Server Management Shell en tant que membre du groupe **RTCUniversalServerAdmins** . Vous devez également avoir les autorisations et les droits d’utilisateur de l’administrateur de base de données SQL Server. 
    
2. Ouverture de Skype entreprise Server Management Shell
    
    > [!CAUTION]
    > Ne continuez pas la suppression des fichiers de base de données précédents tant que la réplication n’est pas terminée et qu’elle est stable. Si vous supprimez les fichiers avant de procéder à la réplication, vous désactiverez le processus de réplication et laissons le serveur de gestion central nouvellement déplacé dans un état inconnu. Utilisez l’applet de connexion **Get-CsManagementStoreReplicationStatus** pour vérifier l’état de la réplication. 
  
3. Pour supprimer les fichiers de base de données de la Banque centrale de gestion de l’installation héritée, tapez :
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Par exemple :
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Où le _ \<FQDN de SQL Server\> _ est le serveur principal de l’installation héritée dans un déploiement Enterprise Edition ou le nom de domaine complet (FQDN) du serveur Standard Edition Server. 
    

