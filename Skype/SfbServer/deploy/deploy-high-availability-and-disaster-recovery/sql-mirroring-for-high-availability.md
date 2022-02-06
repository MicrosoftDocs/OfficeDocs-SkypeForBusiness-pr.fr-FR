---
title: Déployer SQL mise en miroir pour la haute disponibilité du serveur principal dans Skype Entreprise Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: "Pour pouvoir déployer la mise en miroir SQL, vos serveurs doivent exécuter au moins SQL Server\_2008\_R2. Cette version doit s’exécuter sur tous les serveurs impliqués\_: principal, miroir et témoin. Pour plus d’informations, voir Package de mise à jour cumulative 9 SQL Server 2008 Service Pack 1."
---

# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Déployer SQL mise en miroir pour la haute disponibilité du serveur principal dans Skype Entreprise server 2015


Pour pouvoir déployer la mise en miroir SQL, vos serveurs doivent exécuter au moins SQL Server 2008 R2. Cette version doit s’exécuter sur tous les serveurs impliqués : principal, miroir et témoin. Pour plus d’informations, voir Package de mise à jour [cumulative 9 SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).

En général, la configuration de la mise en miroir SQL entre deux serveurs principaux avec un témoin exige ce qui suit :

- La version d’SQL Server du serveur principal doit prendre en charge SQL miroir.

- Le principal, le miroir et le témoin (s’il est déployé) doivent disposer de la même version de SQL Server.

- Le principal et le miroir doivent disposer de la même édition de SQL Server. Le témoin peut en avoir une différente.

Pour SQL meilleures pratiques en matière de SQL versions de base de données sont pris en charge pour un rôle témoin, voir Témoin de mise en miroir [de base de données](/sql/database-engine/database-mirroring/database-mirroring-witness).

Vous utilisez le Générateur de topologie pour déployer SQL miroir. Vous sélectionnez une option dans le Générateur de topologie pour mettre en miroir les bases de données, et le Générateur de topologies définit la mise en miroir (y compris la configuration d’un témoin, si vous le souhaitez) lorsque vous publiez la topologie. Notez que vous configurez ou supprimez le témoin en même temps que le miroir. Il n’existe pas de commande distincte pour déployer ou supprimer uniquement un témoin.

Pour configurer la mise en miroir des serveurs, vous devez d’abord configurer les autorisations de base de données SQL correctement. Pour plus d’informations, voir [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).

Avec la mise en miroir SQL, le mode de récupération de la base de données a toujours la valeur **Complète**, ce qui signifie que vous devez surveiller de près la taille du journal des transactions et sauvegarder les journaux des transactions de manière régulière afin d’éviter toute insuffisance d’espace disque sur les serveurs principaux. La fréquence des sauvegardes des journaux des transactions dépend de la vitesse à laquelle leur taille augmente, laquelle dépend à son tour des transactions de base de données induites par les activités des utilisateurs sur le pool frontal. Nous vous recommandons de déterminer la croissance attendue du journal des transactions pour votre charge de travail de déploiement afin de pouvoir planifier en conséquence. Les articles suivants fournissent des informations supplémentaires sur la gestion des journaux et sauvegardes SQL :

- [Modèles de récupération de base de données](/sql/relational-databases/backup-restore/recovery-models-sql-server)

- [Vue d’ensemble de la sauvegarde](/sql/relational-databases/backup-restore/backup-overview-sql-server)

- [Journal des transactions de sauvegarde](/sql/relational-databases/backup-restore/back-up-a-transaction-log-sql-server)

Avec la mise en miroir SQL, vous pouvez configurer la topologie pour la mise en miroir lorsque vous créez les pools ou après les avoir déjà créés.

> [!IMPORTANT]
> L’utilisation du Générateur de topologie ou des cmdlets pour configurer et supprimer la mise en miroir SQL n’est prise en charge que lorsque les serveurs principal, miroir et témoin (si vous le souhaitez) appartiennent tous au même domaine. Si vous voulez configurer la mise en miroir SQL entre des serveurs de différents domaines, voir votre documentation SQL Server.

> [!IMPORTANT]
> Dès lors que vous apportez une modification à une relation de mise en miroir d’une base de données principale, vous devez redémarrer tous les serveurs frontaux du pool. > pour modifier la mise en miroir (par exemple, en modifiant l’emplacement d’un miroir), vous devez utiliser le Générateur de topologie pour effectuer les trois étapes suivantes :

1. Supprimez la mise en miroir de l’ancien serveur miroir.

2. Ajoutez la mise en miroir au nouveau serveur miroir.

3. Publiez la topologie.

> [!NOTE]
> Un partage de fichiers doit être créé pour que les fichiers miroir soient écrits et que le service sous SQL Server et SQL Agent soit en cours d’exécution nécessite un accès en lecture/écriture. Si le service SQL Server est en cours d’exécution dans le contexte du service réseau, \<Domain\>\\ vous pouvez ajouter<SQLSERVERNAME\>$ des serveurs d’SQL principal et miroir aux autorisations de partage. Le $ est important pour identifier qu’il s’agit d’un compte d’ordinateur.

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Pour configurer la mise en SQL lors de la création d’un pool dans le Générateur de topologies

1. Dans la page **Définir le magasin SQL**, cliquez sur **Nouveau** en regard de la zone **Magasin SQL**.

2. Dans la page **Définir un nouveau magasin SQL**, spécifiez le magasin principal, sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (5022 par défaut), puis cliquez sur **OK**.

3. De retour dans la page **Définir le magasin SQL**, sélectionnez **Activer la mise en miroir du magasin SQL**.

4. Dans la page **Définir un nouveau magasin SQL**, spécifiez le magasin SQL à utiliser en tant que miroir. Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port (5022 par défaut), puis cliquez sur **OK**.

5. Si vous voulez un témoin pour ce miroir, procédez comme suit :

    a. Sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**.

    b. Dans la page **Définir le magasin SQL**, sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**, puis spécifiez le magasin SQL à utiliser en tant que témoin.

    c. Spécifiez le numéro de port (7022 par défaut) et cliquez sur **OK**.

6. Une fois que vous avez terminé de définir votre pool frontal et tous les autres rôles de votre topologie, utilisez le Générateur de topologie pour publier la topologie. Lorsque la topologie est publiée, si la mise en miroir du pool frontal qui héberge le magasin central de gestion SQL été activée, une option s’offre à vous pour créer à la fois des bases de données principales et miroirs SQL banque d’données.

    Cliquez sur **Paramètres**, puis tapez le chemin d’accès à utiliser en tant que partage de fichiers pour la sauvegarde de mise en miroir.

    Cliquez sur **OK**, puis sur **Suivant** pour créer les bases de données et publier la topologie. Le miroir et le témoin (s’il est spécifié) sont déployés.

Vous pouvez utiliser le Générateur de topologie pour modifier les propriétés d’un pool déjà existant afin d’activer SQL miroir.

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Pour ajouter SQL mise en miroir à un pool frontal existant dans le Générateur de topologie

1. Dans le Générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez **sur Modifier les propriétés**.

2. Sélectionnez **Activer la mise en miroir du magasin SQL**, puis cliquez sur **Nouveau** en regard de **Magasin SQL de mise en miroir**.

3. Spécifiez le magasin SQL à utiliser en tant que miroir.

4. Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (5022 par défaut), puis cliquez sur **OK**.

5. Si vous voulez configurer un témoin, sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**, puis cliquez sur **Nouveau**.

6. Spécifiez le magasin SQL à utiliser en tant que témoin.

7. Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (7022 par défaut), puis cliquez sur **OK**.

8. Cliquez sur **OK**.

9. Publiez la topologie. Après cela, vous êtes invité à installer la base de données.

    Pendant le processus de publication de la topologie, vous serez invité à définir un chemin d’accès au partage de fichiers. Les SQL qui participent à la mise en miroir doivent avoir un accès en lecture/écriture à ce partage de fichiers pour que le miroir soit établi.

Vous devez alors installer la base de données avant de passer à la procédure suivante.

Gardez les points suivants à l’esprit lorsque vous configurez la mise en miroir SQL :

- S’il existe déjà un point de terminaison de mise en miroir, celui-ci est réutilisé à l’aide des ports définis ; ceux que vous spécifiez dans la topologie sont ignorés.

- Tout port déjà alloué à d’autres applications sur le même serveur, y compris ceux des autres instances SQL, ne doit pas être utilisé pour les instances SQL installées. Cela signifie que si vous avez plusieurs instances SQL installées sur le même serveur, elles ne doivent pas utiliser le même port pour la mise en miroir. Pour plus d’informations, voir les articles suivants :

  - [Spécifier une adresse réseau de serveur (mise en miroir de bases de données)](/sql/database-engine/database-mirroring/specify-a-server-network-address-database-mirroring)

  - [Point de terminaison de mise en miroir de bases de données (SQL Server)](/sql/database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Utilisation Skype Entreprise Server cmdlets 2015 Management Shell pour configurer SQL miroir

Le moyen le plus simple de configurer la mise en miroir consiste à utiliser le Générateur de topologie, mais vous pouvez également le faire à l’aide d’cmdlets.

1. Ouvrez une Skype Entreprise Server 2015 Management Shell et exécutez l’cmdlet suivante :

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    Par exemple :

   ```powershell
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

   - Les comptes exécutant les serveurs SQL sur tous les serveurs SQL principal et miroir ont une autorisation en lecture/\\écriture sur le partage de fichiers E04-OCS\csdatabackup

   - Vérifiez que le fournisseur WMI (Windows Management Instrumentation) est en cours d’exécution sur tous ces serveurs. L’applet de commande utilise ce fournisseur pour rechercher les informations de compte pour les services SQL Server qui s’exécutent sur tous les serveurs principaux, miroir et témoin.

   - Vérifiez que le compte qui exécute cette applet de commande est autorisé à créer les dossiers pour les données et fichiers journaux de tous les serveurs miroir.

   - Notez que le compte d’utilisateur que l’instance SQL utilise pour s’exécuter doit posséder une autorisation de lecture/écriture sur le partage de fichiers. Si ce dernier se trouve sur un autre serveur, et que l’instance SQL exécute un compte système local, vous devez octroyer au partage de fichier des autorisations d’accès au serveur qui héberge l’instance SQL.

3. Tapez A, puis appuyez sur Entrée.

    La mise en miroir est configurée.

    **Install-CsMirrorDatabase** installe le miroir et configure la mise en miroir de toutes les bases de données présentes sur le magasin SQL principal. Si vous souhaitez configurer la mise en miroir pour des bases de données spécifiques uniquement, vous pouvez utiliser l’option -DatabaseType, ou si vous souhaitez configurer la mise en miroir pour toutes les bases de données à l’exception de quelques-unes, vous pouvez utiliser l’option -ExcludeDatabaseList, ainsi qu’une liste séparée par des virgules de noms de base de données à exclure.

    Par exemple, si vous ajoutez l’option suivante à **Install-CsMirrorDatabase**, toutes les bases de données à l’exception de rtcab et rtcxds sont mises en miroir.

    `-ExcludeDatabaseList rtcab,rtcxds`

   Par exemple, si vous ajoutez l’option suivante à **Install-CsMirrorDatabase**, seules les bases de données rtcab, rtcshared et rtcxds sont mises en miroir.

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>Suppression ou modification de la mise en miroir SQL

Pour supprimer la mise en miroir SQL d’un pool dans le Générateur de topologie, vous devez d’abord utiliser une applet de commande pour supprimer le miroir dans SQL Server. Vous pouvez ensuite utiliser le Générateur de topologie pour supprimer le miroir de la topologie. Pour supprimer le miroir dans SQL Server, utilisez l’applet de commande suivante :

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

Par exemple, pour supprimer la mise en miroir et ignorer les bases de données pour les bases de données User, tapez ce qui suit :

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

L’option  `-DropExistingDatabasesOnMirror` entraîne la suppression des bases de données affectées du miroir.

Ensuite, pour supprimer le miroir de la topologie, procédez comme suit :

1. Dans le Générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.

2. Désactivez la case à cocher **Activer la mise en miroir du magasin SQL** et cliquez sur **OK**.

3. Publiez la topologie.

## <a name="removing-a-mirroring-witness"></a>Suppression d’un témoin de mise en miroir

Utilisez cette procédure si vous devez supprimer le témoin d’une configuration de mise en miroir de serveur principal.

1. Dans le Générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.

2. Désactivez la case à cocher **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** et cliquez sur **OK**.

3. Publiez la topologie.

    Après la publication de la topologie, le Générateur de topologies vous verrez un message qui inclut les données suivantes :

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    Toutefois, ne suivez pas cette étape et ne  `Uninstall-CsMirrorDatabase` tapez pas car cela désinstallerait toute la configuration de mise en miroir.

4. Pour supprimer uniquement le témoin de la configuration SQL Server, suivez les instructions de l’étape Supprimer le témoin d’une session de mise en miroir de base de [données (SQL Server).](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server).