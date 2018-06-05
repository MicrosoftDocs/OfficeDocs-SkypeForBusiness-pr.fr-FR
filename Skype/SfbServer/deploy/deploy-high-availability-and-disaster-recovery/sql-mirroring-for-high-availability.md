---
title: Déployer la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Pour pouvoir déployer la mise en miroir SQL, vos serveurs doivent exécuter au moins SQL Server 2008 R2. Cette version doit s’exécuter sur tous les serveurs impliqués : principal, miroir et témoin. Pour plus d’informations, voir Cumulative mise à jour de package 9 pour SQL Server 2008 Service Pack 1.'
ms.openlocfilehash: 9edbda5d793fed48d31625c3e0d53ab2f9e6d349
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569137"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Déployer la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Skype Entreprise Server 2015
 

Pour pouvoir déployer la mise en miroir SQL, vos serveurs doivent exécuter au moins SQL Server 2008 R2. Cette version doit s’exécuter sur tous les serveurs impliqués : principal, miroir et témoin. Pour plus d’informations, voir [9 pour SQL Server 2008 Service Pack 1 de package de mises à jour cumulatives ](http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).
  
En général, la configuration de la mise en miroir SQL entre deux serveurs principaux avec un témoin exige ce qui suit :
  
- Version du serveur principal de SQL Server doit prendre en charge la mise en miroir SQL.
    
- Le principal, le miroir et le témoin (s’il est déployé) doivent disposer de la même version de SQL Server. 
    
- Le principal et le miroir doivent disposer de la même édition de SQL Server. Le témoin peut en avoir une différente.
    
Pour les meilleures pratiques en termes de quelles versions SQL sont pris en charge pour un rôle de témoin SQL, voir [Témoin de mise en miroir de base de données](https://go.microsoft.com/fwlink/p/?LinkId=247345).
  
Vous utilisez le Générateur de topologie pour déployer la mise en miroir SQL. Vous sélectionnez une option dans le Générateur de topologie pour mettre en miroir de bases de données et le Générateur de topologie définit la mise en miroir (y compris la configuration d’un témoin, si vous le souhaitez) lorsque vous publiez la topologie. Notez que vous configurez ou supprimez le témoin en même temps que le miroir. Il n’existe pas de commande distincte pour déployer ou supprimer uniquement un témoin.
  
Pour configurer la mise en miroir des serveurs, vous devez d’abord configurer les autorisations de base de données SQL correctement. Pour plus d’informations, voir [Définir des comptes de connexion pour la mise en miroir de base de données ou groupes de disponibilité AlwaysOn (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Avec la mise en miroir SQL, le mode de récupération de la base de données a toujours la valeur **Complète**, ce qui signifie que vous devez surveiller de près la taille du journal des transactions et sauvegarder les journaux des transactions de manière régulière afin d’éviter toute insuffisance d’espace disque sur les serveurs principaux. La fréquence des sauvegardes des journaux des transactions dépend de la vitesse à laquelle leur taille augmente, laquelle dépend à son tour des transactions de base de données induites par les activités des utilisateurs sur le pool frontal. Nous vous recommandons d’estimer l’accroissement des journaux des transactions pour la charge de travail de votre déploiement afin de procéder à une planification en conséquence. Les articles suivants fournissent des informations supplémentaires sur la gestion des journaux et sauvegardes SQL :
  
- [Modèles de récupération de base de données](https://go.microsoft.com/fwlink/p/?LinkId=268446)
    
- [Présentation de la sauvegarde](https://go.microsoft.com/fwlink/p/?LinkId=268449)
    
- [Journaux de transactions](https://go.microsoft.com/fwlink/p/?LinkId=268452)
    
Avec la mise en miroir SQL, vous pouvez configurer la topologie pour la mise en miroir lorsque vous créez les pools ou après les avoir déjà créés.
  
> [!IMPORTANT]
> À l’aide du Générateur de topologie ou des applets de commande pour configurer et supprimer SQL la mise en miroir est prise en charge uniquement lorsque le serveur principal, miroir et le serveur témoin (le cas échéant) appartiennent au même domaine. Si vous voulez configurer la mise en miroir SQL entre des serveurs de différents domaines, reportez-vous à votre documentation SQL Server. 
  
> [!IMPORTANT]
> Dès lors que vous apportez une modification à une relation de mise en miroir d’une base de données principale, vous devez redémarrer tous les serveurs frontaux du pool.  > Pour une modification de la mise en miroir, (telles que la modification de l’emplacement d’un miroir), vous devez utiliser le Générateur de topologie pour effectuer ces trois étapes : 
  
1. Supprimez la mise en miroir de l’ancien serveur miroir.
    
2. Ajoutez la mise en miroir au nouveau serveur miroir.
    
3. Publiez la topologie.
    
> [!NOTE]
> Un partage de fichiers doit être créé pour pouvoir y écrire les fichiers miroir, et le service sous lequel SQL Server et SQL Agent s’exécutent doit disposer d’un accès en lecture/écriture. Si le service SQL Server est en cours d’exécution dans le contexte de Service réseau, vous pouvez ajouter \<domaine\>\\< SQLSERVERNAME\>$ d’à la fois les serveurs Principal et miroir SQL pour les autorisations de partage. Le signe $ est important afin d’identifier qu’il s’agit d’un compte ordinateur. 
  
## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Pour configurer la mise en miroir SQL lors de la création d’un pool dans le Générateur de topologie

1. Dans la page **Définir le magasin SQL**, cliquez sur **Nouveau** en regard de la zone **Magasin SQL**. 
    
2. Dans la page **Définir un nouveau magasin SQL**, spécifiez le magasin principal, sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (5022 par défaut), puis cliquez sur **OK**.
    
3. De retour dans la page **Définir le magasin SQL**, sélectionnez **Activer la mise en miroir du magasin SQL**.  
    
4. Dans la page **Définir un nouveau magasin SQL**, spécifiez le magasin SQL à utiliser en tant que miroir. Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port (5022 par défaut), puis cliquez sur **OK**.
    
5. Si vous voulez un témoin pour ce miroir, procédez comme suit :  
    
    a. Sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**.  
    
    b. Dans la page **Définir le magasin SQL**, sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**, puis spécifiez le magasin SQL à utiliser en tant que témoin.  
    
    c. Spécifiez le numéro de port (7022 par défaut) et cliquez sur **OK**.  
    
6. Une fois que vous avez terminé définition de votre pool frontal et tous les autres rôles dans votre topologie, utilisez le Générateur de topologie pour publier la topologie. Une fois la topologie publiée, si le pool frontal qui héberge le magasin Central de gestion a miroir SQL, vous verrez une option pour créer les deux principal et de mise en miroir de bases de données de magasin SQL.
    
    Cliquez sur **Paramètres**, puis tapez le chemin d’accès à utiliser en tant que partage de fichiers pour la sauvegarde de mise en miroir.
    
    Cliquez sur **OK**, puis sur **Suivant ** pour créer les bases de données et publier la topologie. Le miroir et le témoin (s’il est spécifié) sont déployés.
    
Vous pouvez utiliser le Générateur de topologie pour modifier les propriétés d’un pool déjà existant pour activer la mise en miroir SQL. 
  
## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Pour ajouter la mise en miroir SQL à un pool frontal existant dans le Générateur de topologie

1. Dans le Générateur de topologie avec le bouton droit de la liste, puis cliquez sur **Modifier les propriétés**.
    
2. Sélectionnez **Activer la mise en miroir du magasin SQL**, puis cliquez sur **Nouveau ** en regard de **Magasin SQL de mise en miroir**.  
    
3. Spécifiez le magasin SQL à utiliser en tant que miroir.  
    
4. Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (5022 par défaut), puis cliquez sur **OK**.
    
5. Si vous voulez configurer un témoin, sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**, puis cliquez sur **Nouveau**.  
    
6. Spécifiez le magasin SQL à utiliser en tant que témoin.  
    
7. Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (7022 par défaut), puis cliquez sur **OK**.
    
8. Cliquez sur **OK**.
    
9. Publiez la topologie. Après cela, vous êtes invité à installer la base de données.  
    
    Lors du processus de publication de la topologie, vous serez invité à définir un chemin d’accès au partage de fichiers. Les serveurs SQL Server qui participent à la mise en miroir doivent disposer d’un accès en lecture/écriture à ce partage de fichiers pour que le miroir puisse être établi.
    
Vous devez alors installer la base de données avant de passer à la procédure suivante.
  
Gardez les points suivants à l’esprit lorsque vous configurez la mise en miroir SQL :
  
- S’il existe déjà un point de terminaison de mise en miroir, celui-ci est réutilisé à l’aide des ports définis ; ceux que vous spécifiez dans la topologie sont ignorés.
    
- Tout port déjà alloué à d’autres applications sur le même serveur, dont ceux des autres instances SQL, ne doit pas être utilisé pour les instances SQL installées. Cela signifie que si vous avez plusieurs instances SQL installées sur le même serveur, elles ne doivent pas utiliser le même port pour la mise en miroir. Pour plus d’informations, reportez-vous aux articles suivants :
    
  - [Spécifier une adresse réseau du serveur (mise en miroir de base de données)](https://go.microsoft.com/fwlink/p/?LinkId=247346)
    
  - [La base de données mise en miroir de point de terminaison (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=247347)
    
## <a name="using-skype-for-business-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a>À l’aide de Skype pour les applets de commande Business Server Management Shell pour configurer la mise en miroir SQL

Le moyen le plus simple pour configurer la mise en miroir est à l’aide du Générateur de topologie, mais vous pouvez également effectuer à l’aide des applets de commande.
  
1. Ouvrez un Skype pour fenêtre Business Server Management Shell et exécutez la cmdlet suivante :
    
   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
   ```

    Par exemple :
    
   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
   ```

    Les informations suivantes s’affichent :
    
 <pre>
  Database Name:rtcxds 
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rtcshared 
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rtcab 
        Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
         Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rgsconfig 
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rgsdyn 
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:cpsdyn 
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:xds 
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:lis 
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 
</pre>

2. Vérifiez les éléments suivants :
    
    - Le port 5022 est accessible via le pare-feu si le Pare-feu Windows est activé sur le serveur SQL principal e04-ocs.los_a.lsipt.local\rtc.  
    
    - Le port 5022 est accessible via le pare-feu si le Pare-feu Windows est activé dans le serveur SQL miroir K16-ocs.los_a.lsipt.local\rtc.  
    
    - Le port 7022 est accessible via le pare-feu si le Pare-feu Windows est activé dans le serveur SQL témoin AB14-lct.los_a.lsipt.local\rtc.  
    
   - Les comptes qui exécutent les serveurs miroir SQL Server principal tous les serveurs SQL ont l’autorisation en lecture/écriture pour le partage de fichiers \\OCS\csdatabackup-E04 
    
   - Vérifiez que le fournisseur WMI (Windows Management Instrumentation) est en cours d’exécution sur tous ces serveurs. L’applet de commande utilise ce fournisseur pour rechercher les informations de compte pour les services SQL Server qui s’exécutent sur tous les serveurs principaux, miroir et témoin.  
    
   - Vérifiez que le compte qui exécute cette applet de commande est autorisé à créer les dossiers pour les données et fichiers journaux de tous les serveurs miroir.  
    
   - Notez que le compte d’utilisateur que l’instance SQL utilise pour s’exécuter doit posséder une autorisation de lecture/écriture sur le partage de fichiers. Si ce dernier se trouve sur un autre serveur, et que l’instance SQL exécute un compte système local, vous devez octroyer au partage de fichier des autorisations d’accès au serveur qui héberge l’instance SQL.
    
3. Tapez A, puis appuyez sur Entrée.
    
    La mise en miroir est configurée.
    
    **Install-CsMirrorDatabase** installe le miroir et configure la mise en miroir pour toutes les bases de données qui sont présents sur le magasin SQL principal. Si vous souhaitez configurer la mise en miroir de bases de données spécifiques, vous pouvez utiliser l’option - DatabaseType, ou si vous souhaitez configurer la mise en miroir pour toutes les bases de données à l’exception de quelques, vous pouvez utiliser l’option - ExcludeDatabaseList, ainsi que d’une liste séparée par des virgules de base de données noms à exclure.
  
    Par exemple, si vous ajoutez l’option suivante à **Install-CsMirrorDatabase**, toutes les bases de données à l’exception de rtcab et rtcxds sont mises en miroir.
  
    `-ExcludeDatabaseList rtcab,rtcxds`
  
   Par exemple, si vous ajoutez l’option suivante à **Install-CsMirrorDatabase**, uniquement, des bases de données rtcab, rtcshared et rtcxds sont mises en miroir.
  
    `-DatabaseType User`
  
## <a name="removing-or-changing-sql-mirroring"></a>Suppression ou modification de la mise en miroir SQL

Pour supprimer la mise en miroir SQL d’un pool dans le générateur de topologie, vous devez d’abord utiliser une applet de commande pour supprimer le miroir dans SQL Server. Vous pouvez ensuite utiliser le générateur de topologie pour supprimer le miroir de la topologie. Pour supprimer le miroir dans SQL Server, utilisez l’applet de commande suivante :
  
```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

Par exemple, pour supprimer la mise en miroir et ignorer les bases de données pour les bases de données User, tapez ce qui suit :
  
```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

Le `-DropExistingDatabasesOnMirror` avec l’option, les bases de données affectées à supprimer de la mise en miroir.
  
Ensuite, pour supprimer le miroir de la topologie, procédez comme suit :
  
1. Dans le générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.
    
2. Désactivez la case à cocher **Activer la mise en miroir du magasin SQL ** et cliquez sur **OK**.
    
3. Publiez la topologie.
    
## <a name="removing-a-mirroring-witness"></a>Suppression d’un témoin de mise en miroir

Utilisez cette procédure si vous avez besoin supprimer le témoin d’un serveur principal configuration de la mise en miroir.
  
1. Dans le générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**. 
    
2. Désactivez la case à cocher **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** et cliquez sur **OK**.
    
3. Publiez la topologie.
    
    Après la publication de la topologie, le Générateur de topologie vous verrez un message qui inclut les éléments suivants
    
   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    Toutefois, ne suivez pas cette étape et ne tapez pas `Uninstall-CsMirrorDatabase` car cela désinstallerait toute la configuration de la mise en miroir.
    
4. Pour supprimer uniquement le témoin de la configuration de SQL Server, suivez les instructions de [Supprimer le témoin d’une Session de la mise en miroir de base de données (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).
    

