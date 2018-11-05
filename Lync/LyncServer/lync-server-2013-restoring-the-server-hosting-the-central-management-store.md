---
title: Restauration du serveur hébergeant le magasin central de gestion
TOCTitle: Restauration du serveur hébergeant le magasin central de gestion
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202172(v=OCS.15)
ms:contentKeyID: 53095398
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauration du serveur hébergeant le magasin central de gestion

 

_**Dernière rubrique modifiée :** 2013-02-21_

Un déploiement Lync Server possède un seul magasin central de gestion, une copie duquel étant répliquée sur chaque serveur exécutant un rôle de serveur Lync Server. Cette rubrique décrit comment restaurer un serveur principal ou un serveur Standard Edition qui héberge le magasin central de gestion.

Pour trouver le pool où se trouve le serveur de gestion centralisée, ouvrez le Générateur de topologie, cliquez sur **Lync Server** et regardez dans le volet droit sous **Serveur de gestion centralisée**.

Si le serveur principal qui héberge le magasin central de gestion se trouve dans une configuration en miroir et que la base de données miroir est toujours fonctionnelle, nous vous recommandons d’effectuer une sauvegarde de ce miroir toujours opérationnel, puis d’effectuer une restauration complète sur la base de données primaire et la base de données miroir, à l’aide de cette sauvegarde, en suivant la procédure de restauration ci-après. Cela est nécessaire, car la restauration du serveur principal nécessite la modification et la publication de la topologie, opérations qui ne peuvent être effectuées que si la base de données primaire qui héberge le magasin central de gestion est opérationnelle. En outre, notez que les rôles de base de données primaire et miroir ne peuvent être permutés que si la topologie peut être publiée.

> [!NOTE]  
> Si un serveur principal ou le serveur Standard Edition qui n’héberge pas le magasin central de gestion échoue, consultez <a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restauration du serveur principal Enterprise Edition</a> ou <a href="lync-server-2013-restoring-a-standard-edition-server.md">Restauration d’un serveur Standard Edition</a>. Si un serveur principal qui héberge le magasin central de gestion se trouve dans une configuration en miroir et que seul le miroir échoue, consultez <a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restauration d’un serveur principal Enterprise Edition en miroir - Miroir</a>. Si n’importe quel autre serveur échoue, consultez <a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restauration d’un serveur membre Enterprise Edition</a>.

> [!TIP]  
> Nous vous recommandons de faire une image du système avant de démarrer la restauration. Vous pouvez utiliser cette image en tant que point de restauration au cas où un problème se produise pendant la restauration. Cette image pourra être effectuée après l’installation du système d’exploitation et SQL Server, et la restauration et réinscription des certificats.

## Pour restaurer le magasin central de gestion

1.  Démarrez avec un serveur nouveau ou propre qui a le même nom de domaine complet (FQDN) que l’ordinateur qui a échoué, installez le système d’exploitation, puis restaurez ou réinscrivez les certificats.
    
    > [!NOTE]  
    > Suivez les procédures de déploiement serveur de votre organisation pour effectuer cette étape.

2.  Depuis un compte utilisateur qui est membre du groupe RTCUniversalServerAdmins et du groupe Administrateurs local, connectez-vous au serveur que vous êtes en train de restaurer.

3.  Si vous restaurez un serveur Standard Edition, restaurez le magasin de fichiers en copiant le magasin de fichiers approprié depuis $Backup à l’emplacement du magasin de fichiers sur le serveur, puis partagez le dossier.
    
    > [!IMPORTANT]  
    > Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être exactement les mêmes que ceux du magasin de fichiers sauvegardé pour que les composants qui utilisent les fichiers puissent continuer à y accéder.

4.  Effectuez l’une des opérations suivantes :
    
      - Si vous installez un serveur Standard Edition, naviguez jusqu’au dossier ou support d’installation de Lync Server, puis démarrez l’Assistant Déploiement de Lync Server qui se trouve ici : \\setup\\amd64\\Setup.exe. Dans l’Assistant Déploiement, cliquez sur **Préparer d’abord le serveur Standard Edition Server**, et suivez l’Assistant pour installer le magasin central de gestion.
    
      - Si vous installez un serveur principal d’entreprise, installez SQL Server 2012 ou SQL Server 2008 R2, en conservant les mêmes noms d’instances qu’avant la défaillance.
        
        > [!NOTE]  
        > Suivant le serveur que vous restaurez et votre déploiement, le serveur peut inclure plusieurs bases de données colocalisées ou séparées. Suivez la même procédure pour installer SQL Server que celle que vous avez utilisée à l’origine pour déployer le serveur, avec les autorisations et les comptes de connexion SQL Server.

5.  À partir d’un serveur frontal, procédez comme suit. Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

6.  Recréez le magasin central de gestion. Sur la ligne de commande, tapez :
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Par exemple :
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  Définissez le point de contrôle des services de domaine Active Directory pour le magasin central de gestion. Sur la ligne de commande, tapez :
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Par exemple :
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    > [!NOTE]  
    > Si vous perdez le point de connexion, vous pouvez réexécuter cette applet de commande.

8.  Importez les données du magasin central de gestion depuis $Backup. Sur la ligne de commande, tapez :
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    Par exemple :
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  Activez les modifications que vous venez de faire. Sur la ligne de commande, tapez :
    
        Enable-CsTopology
    
    > [!NOTE]  
    > Lorsque vous avez activé la topologie, vous pouvez trouver le document de topologie dans la base de données.

10. Si vous restaurez un serveur principalEnterprise Edition qui hébergeait également le magasin central de gestion ou que vous devez recréer un miroir du magasin central de gestion, suivez cette étape. Sinon, passez à l’étape 11.
    
    Installez les bases de données autonomes en procédant comme suit :
    
    1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.
    
    2.  Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis sur **OK**.
    
    3.  Sélectionnez la topologie, puis cliquez sur **Enregistrer**. Cliquez sur **Oui** pour confirmer votre sélection.
    
    4.  Cliquez avec le bouton droit sur le nœud **Lync Server 2013**, puis cliquez sur **Installer une base de données**.
    
    5.  Suivez l’Assistant **Installer une base de données**. Si vous restaurez une autre base de données que le magasin central de gestion sur ce serveur, dans la page **Créer des bases de données**, sélectionnez les bases de données que vous voulez recréer.
        
        > [!NOTE]  
        > Seules les bases de données autonomes sont affichées dans la page <strong>Créer des bases de données</strong>. Les bases de données colocalisées sont créées lorsque vous exécutez l’Assistant Déploiement de Lync Server.    
    6.  Si vous restaurez un serveur principal en miroir, poursuivez le reste de l’Assistant jusqu’à l’apparition d’une invite Créer des bases de données miroir. Sélectionnez la base de données à installer, puis terminez le processus.
    
    7.  Suivez les dernières instructions de l’Assistant, puis cliquez sur **Terminer**.
    
    > [!TIP]  
    > Au lieu d’exécuter le Générateur de topologie, vous pouvez utiliser l’applet de commande <strong>Install-CsDatabase</strong> pour créer chaque base de données et l’applet de commande <strong>Install-CsMirrorDatabase</strong> pour configurer la mise en miroir. Pour plus d’informations, voir <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</a> et <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</a>.

11. Si vous restaurez un serveur Standard Edition, naviguez jusqu’au dossier ou au support d’installation de Lync Server, puis démarrez l’Assistant Déploiement de Lync Server qui se trouve ici : \\setup\\amd64\\Setup.exe. Utilisez l’Assistant Déploiement de Lync Server pour faire ce que suit :
    
    1.  Exécutez **Étape 1: Installer le magasin de configurations local** pour installer les fichiers de configuration locaux.
    
    2.  Exécutez **Étape 2: Installer ou supprimer des composants Lync Server** pour installer les rôles de serveur Lync Server.
    
    3.  Exécutez **Étape 3 : Demander, installer ou assigner des certificats** pour assigner les certificats.
    
    4.  Exécutez **Étape 4 : Démarrer les services** pour démarrer les services sur le serveur.
    
    Pour des détails sur l’exécution de l’Assistant Déploiement, consultez la documentation du déploiement pour le rôle serveur que vous restaurez.

12. Restaurez les données utilisateur en procédant comme suit :
    
    1.  Copiez ExportedUserData.zip depuis $Backup\\ dans un répertoire local.
    
    2.  Avant de restaurer les données utilisateur, vous devez arrêter les services Lync. Pour ce faire, tapez :
        
            Stop-CsWindowsService
    
    3.  Pour restaurer les données utilisateur, sur la ligne de commande, tapez :
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Par exemple :
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Redémarrez les services Lync en tapant :
        
            Start-CsWindowsService

13. Restaurez les données d’informations d’emplacement sur le magasin central de gestion. Sur la ligne de commande, tapez :
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    Par exemple :
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. Si vous avez déployé Response Group sur ce pool ou serveur Standard Edition, restaurez les données de configuration Response Group. Pour des informations détaillées, consultez [Restauration des paramètres Response Group](lync-server-2013-restoring-response-group-settings.md).

15. Si vous restaurez un serveur principal sur lequel se trouvent des bases de données d’archivage ou de surveillance, restaurez les données d’archivage ou de surveillance à l’aide d’un outil de gestion SQL Server, comme SQL Server Management Studio. Pour des informations détaillées, consultez [Restauration des données de surveillance ou d’archivage](lync-server-2013-restoring-monitoring-or-archiving-data.md).

