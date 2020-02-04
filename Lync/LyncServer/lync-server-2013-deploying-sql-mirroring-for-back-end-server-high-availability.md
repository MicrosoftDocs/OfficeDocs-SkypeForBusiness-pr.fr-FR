---
title: Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a37c554faf81795363522378160abf5081084f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a>Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-01-08_

Pour pouvoir déployer la mise en miroir SQL, vos serveurs doivent exécuter au moins SQL Server 2008 R2. Cette version doit s’exécuter sur tous les serveurs impliqués : principal, miroir et témoin. Pour plus d’informations [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921), reportez-vous à.

En général, la configuration de la mise en miroir SQL entre deux serveurs principaux avec un témoin exige ce qui suit :

  - La version de SQL Server du serveur principal doit prendre en charge la mise en miroir SQL.

  - Le principal, le miroir et le témoin (s’il est déployé) doivent disposer de la même version de SQL Server.

  - Le principal et le miroir doivent disposer de la même édition de SQL Server. Le témoin peut en avoir une différente.

Pour connaître les meilleures pratiques en matière de SQL en ce qui concerne les versions SQL prises en charge pour un rôle de témoin, voir « témoin de [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345)mise en miroir de base de données » dans MSDN Library à l’adresse.

Vous utilisez le générateur de topologie pour déployer la mise en miroir SQL. Vous pouvez sélectionner une option dans le générateur de topologie pour mettre en miroir les bases de données, et le générateur de topologie configure la mise en miroir (y compris la configuration d’un témoin, si vous le souhaitez) lors de la publication de la topologie. Notez que vous configurez ou supprimez le témoin en même temps que le miroir. Il n’existe pas de commande distincte pour déployer ou supprimer uniquement un témoin.

Pour configurer la mise en miroir des serveurs, vous devez d’abord configurer les autorisations de base de données SQL correctement. Pour plus d’informations, consultez la section « configurer les comptes de connexion pour la mise en miroir de la base de [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454)données ou les groupes AlwaysOn de disponibilité (SQL Server) ».

Avec la mise en miroir SQL, le mode de récupération de la base de données a toujours la valeur **Complète**, ce qui signifie que vous devez surveiller de près la taille du journal des transactions et sauvegarder les journaux des transactions de manière régulière afin d’éviter toute insuffisance d’espace disque sur les serveurs principaux. La fréquence des sauvegardes des journaux des transactions dépend de la vitesse à laquelle leur taille augmente, laquelle dépend à son tour des transactions de base de données induites par les activités des utilisateurs sur le pool frontal. Nous vous recommandons d’estimer l’accroissement des journaux des transactions pour la charge de travail de votre déploiement Lync afin de procéder à une planification en conséquence. Les articles suivants fournissent des informations supplémentaires sur la gestion des journaux et sauvegardes SQL :

  - Modèles de récupération de base de données : « modèles de récupération (SQL Server) » sur[http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)

  - Présentation de la sauvegarde : « présentation de la sauvegarde (SQL Server) » à[http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)

  - Journal de transactions de sauvegarde : « sauvegarder un journal des transactions (SQL Server) » à[http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)

Avec la mise en miroir SQL, vous pouvez configurer la topologie pour la mise en miroir lorsque vous créez les pools ou après les avoir déjà créés.



> [!IMPORTANT]
> Le recours au générateur de topologie ou aux cmdlets pour configurer et supprimer la mise en miroir SQL est uniquement pris en charge lorsque les serveurs principal, miroir et témoin (le cas échéant) appartiennent tous au même domaine. Si vous voulez configurer la mise en miroir SQL entre des serveurs de différents domaines, reportez-vous à votre documentation SQL Server.





> [!IMPORTANT]
> Dès lors que vous apportez une modification à une relation de mise en miroir d’une base de données principale, vous devez redémarrer tous les serveurs frontaux du pool. <BR>Pour un changement de mise en miroir (par exemple, la modification de l’emplacement d’un miroir), vous devez utiliser le générateur de topologie pour effectuer les trois étapes suivantes : 
> <OL>
> <LI>
> <P>Supprimez la mise en miroir de l’ancien serveur miroir.</P>
> <LI>
> <P>Ajoutez la mise en miroir au nouveau serveur miroir.</P>
> <LI>
> <P>Publiez la topologie.</P></LI></OL>




> [!NOTE]
> Un partage de fichiers doit être créé pour pouvoir y écrire les fichiers miroir, et le service sous lequel SQL Server et SQL Agent s’exécutent doit disposer d’un accès en lecture/écriture. Si le service SQL Server s’exécute dans le contexte de service réseau, vous pouvez ajouter &lt;un&gt; domaine &lt;&#92;&gt;SqlServerName $ de l’entité et du serveur miroir SQL aux autorisations de partage. Le signe $ est important afin d’identifier qu’il s’agit d’un compte ordinateur.


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Pour configurer la mise en miroir SQL lors de la création d’un pool dans le générateur de topologie

1.  Dans la page **Définir le magasin SQL**, cliquez sur **Nouveau** en regard de la zone **Magasin SQL**. 

2.  Dans la page **Définir un nouveau magasin SQL**, spécifiez le magasin principal, sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (5022 par défaut), puis cliquez sur **OK**.

3.  De retour dans la page **Définir le magasin SQL**, sélectionnez **Activer la mise en miroir du magasin SQL**. 

4.  Dans la page **Définir un nouveau magasin SQL**, spécifiez le magasin SQL à utiliser en tant que miroir. Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port (5022 par défaut), puis cliquez sur **OK**.

5.  Si vous voulez un témoin pour ce miroir, procédez comme suit : 
    
    1.  Sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**. 
    
    2.  Dans la page **Définir le magasin SQL**, sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**, puis spécifiez le magasin SQL à utiliser en tant que témoin. 
    
    3.  Spécifiez le numéro de port (7022 par défaut) et cliquez sur **OK**. 

6.  Lorsque vous avez terminé de définir votre pool frontal et tous les autres rôles dans votre topologie, utilisez le générateur de topologie pour publier la topologie. Lors de la publication de la topologie, si la mise en miroir SQL est activée pour le pool frontal, une option de création de bases de données de magasin SQL principales et de miroirs est affichée.
    
    Cliquez sur **Paramètres**, puis tapez le chemin d’accès à utiliser en tant que partage de fichiers pour la sauvegarde de mise en miroir.
    
    Cliquez sur **OK**, puis sur **Suivant ** pour créer les bases de données et publier la topologie. Le miroir et le témoin (s’il est spécifié) sont déployés.

Vous pouvez utiliser le générateur de topologie pour modifier les propriétés d’un pool déjà existant et activer la mise en miroir SQL.

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Pour ajouter la mise en miroir SQL à un pool frontal existant dans le générateur de topologie

1.  Dans le générateur de topologie, cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.

2.  Sélectionnez **Activer la mise en miroir du magasin SQL**, puis cliquez sur **Nouveau ** en regard de **Magasin SQL de mise en miroir**. 

3.  Spécifiez le magasin SQL à utiliser en tant que miroir. 

4.  Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (5022 par défaut), puis cliquez sur **OK**.

5.  Si vous voulez configurer un témoin, sélectionnez **Utiliser le témoin de mise en miroir SQL pour activer le basculement automatique**, puis cliquez sur **Nouveau**. 

6.  Spécifiez le magasin SQL à utiliser en tant que témoin. 

7.  Sélectionnez **Cette instance SQL fait partie d’une relation de mise en miroir**, spécifiez le numéro de port de mise en miroir SQL (7022 par défaut), puis cliquez sur **OK**.

8.  Cliquez sur **OK**.

9.  Publiez la topologie. Après cela, vous êtes invité à installer la base de données. 
    
    Lors du processus de publication de la topologie, vous serez invité à définir un chemin d’accès au partage de fichiers. Les serveurs SQL Server qui participent à la mise en miroir doivent disposer d’un accès en lecture/écriture à ce partage de fichiers pour que le miroir puisse être établi.

Vous devez alors installer la base de données avant de passer à la procédure suivante.

Gardez les points suivants à l’esprit lorsque vous configurez la mise en miroir SQL :

  - S’il existe déjà un point de terminaison de mise en miroir, celui-ci est réutilisé à l’aide des ports définis ; ceux que vous spécifiez dans la topologie sont ignorés.

  - Tout port déjà alloué à d’autres applications sur le même serveur, dont ceux des autres instances SQL, ne doit pas être utilisé pour les instances SQL installées. Cela signifie que si vous avez plusieurs instances SQL installées sur le même serveur, elles ne doivent pas utiliser le même port pour la mise en miroir. Pour plus d’informations, reportez-vous aux articles suivants :
    
      - "Spécifiez une adresse réseau du serveur (mise en miroir de la base de données)" dans MSDN Library sur[http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)
    
      - « Point de terminaison de mise en miroir de la base de données (SQL Server) » à[http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Utiliser les applets de applet Lync Server Management Shell pour configurer la mise en miroir SQL

Le moyen le plus simple de définir la mise en miroir consiste à utiliser le générateur de topologies, mais vous pouvez également le faire à l’aide de cmdlets.

1.  Ouvrez une fenêtre Lync Server Management Shell et exécutez l’applet de commande suivante :
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    Par exemple :
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    Les informations suivantes s’affichent :
    
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

2.  Vérifiez les éléments suivants :
    
      - Le port 5022 est accessible via le pare-feu si le pare-feu Windows est activé dans le\_serveur principal SQL Server E04-OCS\\. Los a. LSIPT. local RTC.
    
      - Le port 5022 est accessible via le pare-feu si le pare-feu Windows est activé dans la\_version\\miroir SQL Server K16-OCS. Los a. LSIPT
    
      - Le port 7022 est accessible via le pare-feu si le pare-feu Windows est activé dans le\_témoin SQL Server AB14-LCT.\\Los a. LSIPT
    
      - Les comptes exécutant SQL Server sur tous les serveurs SQL principaux et en miroir disposent d’une autorisation en lecture/ \\ \\écriture sur le\\partage de fichiers E04-OCS csdatabackup
    
      - Vérifiez que le fournisseur WMI (Windows Management Instrumentation) est en cours d’exécution sur tous ces serveurs. L’applet de commande utilise ce fournisseur pour rechercher les informations de compte pour les services SQL Server qui s’exécutent sur tous les serveurs principaux, miroir et témoin. 
    
      - Vérifiez que le compte qui exécute cette applet de commande est autorisé à créer les dossiers pour les données et fichiers journaux de tous les serveurs miroir. 
    
      - Notez que le compte d’utilisateur que l’instance SQL utilise pour s’exécuter doit posséder une autorisation de lecture/écriture sur le partage de fichiers. Si ce dernier se trouve sur un autre serveur, et que l’instance SQL exécute un compte système local, vous devez octroyer au partage de fichier des autorisations d’accès au serveur qui héberge l’instance SQL.

3.  Tapez A, puis appuyez sur Entrée.
    
    La mise en miroir est configurée.

**Install-CsMirrorDatabase** installe le miroir et configure la mise en miroir de toutes les bases de données présentes sur le magasin SQL principal. Pour configurer la mise en miroir pour des bases de données spécifiques uniquement, vous pouvez utiliser l’option –DatabaseType, ou pour configurer la mise en miroir de toutes les bases de données à l’exception de quelques-unes, vous pouvez utiliser l’option -ExcludeDatabaseList, avec la liste séparée par des virgules des noms des bases de données à exclure.

Par exemple, si vous ajoutez l’option suivante à **Install-CsMirrorDatabase**, toutes les bases de données à l’exception de rtcab et rtcxds sont mises en miroir.

`-ExcludeDatabaseList rtcab,rtcxds`

Par exemple, si vous ajoutez l’option suivante à **Install-CsMirrorDatabase**, seules les bases de données rtcab, rtcshared et rtcxds sont mises en miroir.

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a>Suppression ou modification de la mise en miroir SQL

Pour supprimer la mise en miroir SQL d’un pool dans le générateur de topologie, vous devez d’abord utiliser une applet de commande pour supprimer le miroir dans SQL Server. Vous pouvez ensuite utiliser le générateur de topologie pour supprimer le miroir de la topologie. Pour supprimer le miroir dans SQL Server, utilisez l’applet de commande suivante :

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Par exemple, pour supprimer la mise en miroir et ignorer les bases de données pour les bases de données User, tapez ce qui suit :

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

L' `-DropExistingDatabasesOnMirror` option permet de supprimer les bases de données affectées du miroir.

Ensuite, pour supprimer le miroir de la topologie, procédez comme suit :

1.  Dans le générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.

2.  Désactivez la case à cocher **Activer la mise en miroir du magasin SQL ** et cliquez sur **OK**.

3.  Publiez la topologie.

</div>

<div>

## <a name="removing-a-mirroring-witness"></a>Suppression d’un témoin de mise en miroir

Utilisez cette procédure si vous devez supprimer le témoin d’une configuration de mise en miroir du serveur principal.

1.  Dans le générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.

2.  Désactivez la case à cocher **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** et cliquez sur **OK**.

3.  Publiez la topologie.
    
    Après avoir publié la topologie, le générateur de topologie vous verrez un message qui inclut les éléments suivants :
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    Toutefois, ne suivez pas cette étape et ne tapez aucun type `Uninstall-CsMirrorDatabase` pour désinstaller l’ensemble de la configuration de mise en miroir.

4.  Pour supprimer uniquement le témoin de la configuration SQL Server, suivez les instructions de la section « supprimer le témoin d’une session de mise en miroir de base de [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456)données (SQL Server) ».

</div>

</div>

<span> </span>

</div>

</div>

</div>

