---
title: Restauration du serveur principal Enterprise Edition
TOCTitle: Restauration du serveur principal Enterprise Edition
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202163(v=OCS.15)
ms:contentKeyID: 53095361
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauration du serveur principal Enterprise Edition

 

_**Dernière rubrique modifiée :** 2013-02-18_

Utilisez la procédure décrite dans cette rubrique dans les deux cas suivants :

  - La base de données primaire et la base de données miroir d’un serveur principal Enterprise Edition en miroir échouent.

  - Un serveur principal Enterprise Edition qui n’est pas en miroir échoue.

Si vous possédez un serveur principal Enterprise Edition en miroir et que seule la base de données miroir ou primaire échoue, voir [Restauration d’un serveur principal Enterprise Edition en miroir - Base de données primaire](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) pour restaurer la base de données primaire ou [Restauration d’un serveur principal Enterprise Edition en miroir - Miroir](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) pour restaurer la base de données miroir.

Si le magasin central de gestion échoue, voir [Restauration du serveur hébergeant le magasin central de gestion](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si un serveur membre Enterprise Edition qui n’est pas le serveur principal échoue, voir [Restauration d’un serveur membre Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

> [!TIP]  
> Nous vous recommandons de faire une image du système avant de démarrer la restauration. Vous pouvez utiliser cette image en tant que point de restauration au cas où un problème se produise pendant la restauration. Cette image pourra être effectuée après l’installation du système d’exploitation et SQL Server, et la restauration et réinscription des certificats.

## Pour restaurer un serveur principal Enterprise Edition

1.  Démarrez avec un nouveau serveur qui est doté du même nom de domaine complet (FQDN) que l’ordinateur qui a échoué, installez le système d’exploitation, puis restaurez ou réinscrivez les certificats.
    
    > [!NOTE]  
    > Suivez les procédures de déploiement de votre organisation pour effectuer cette étape.

2.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins, ouvrez une session sur le serveur que vous êtes en train de restaurer.

3.  Installez SQL Server 2012 ou SQL Server 2008 R2, en conservant les noms d’instance qui existaient avant l’échec.
    
    > [!NOTE]  
    > Selon votre déploiement, le serveur principal peut comprendre plusieurs bases de données colocalisées ou distinctes. Suivez la même procédure pour installer SQL Server que celle que vous avez utilisée pour déployer le serveur, y compris les autorisations et les connexions SQL Server.

4.  Une fois que vous avez installé SQL Server, effectuez les actions suivantes :
    
    1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.
    
    2.  Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.
    
    3.  Sélectionnez la topologie, puis cliquez sur **Enregistrer**. Cliquez sur **Oui** pour confirmer la sélection.
    
    4.  Cliquez avec le bouton droit sur le nœud **Lync Server 2013**, puis cliquez sur **Publier la topologie**.
    
    5.  Suivez l’Assistant **Publier la topologie**. Dans la page **Créer des bases de données**, sélectionnez les bases de données à recréer.
        
        > [!NOTE]  
        > Seules les bases de données autonomes sont affichées dans la page <strong>Créer des bases de données</strong>.    
    6.  Si vous restaurez un serveur principal en miroir, poursuivez le reste de l’Assistant jusqu’à l’apparition de l’invite **Créer des bases de données miroir**. Sélectionnez la base de données à installer, puis terminez le processus.
    
    7.  Suivez le reste de l’Assistant, puis cliquez sur **Terminer**.
    
    > [!TIP]  
    > Au lieu d’exécuter le Générateur de topologie, vous pouvez utiliser l’applet de commande <strong>Install-CsDatabase</strong>, pour créer chaque base de données, et l’applet de commande <strong>Install-CsMirrorDatabase</strong>, pour configurer la mise en miroir. Pour plus d’informations, voir la documentation Lync Server Management Shell.

5.  Restaurez les données utilisateur comme suit :
    
    1.  Copiez ExportedUserData.zip à partir de $Backup\\ vers un répertoire local.
    
    2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.
    
    3.  Avant de restaurer les données utilisateur, vous devez arrêter les services Lync. Pour ce faire, tapez :
        
            Stop-CsWindowsService
    
    4.  Pour restaurer les données utilisateur, Sur la ligne de commande, tapez ce qui suit :
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Par exemple :
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  Redémarrez les services Lync en tapant :
        
            Start-CsWindowsService

6.  Si vous déployez l’Response Group sur ce pool, restaurez les données de configuration de Response Group. Pour plus d’informations, voir [Restauration des paramètres Response Group](lync-server-2013-restoring-response-group-settings.md).

7.  Si vous restaurez un serveur principal qui incluait des bases de données d’archivage ou de surveillance, restaurez les données d’archivage ou de surveillance à l’aide d’un utilitaire SQL Server, tel que SQL Server Management Studio. Pour plus d’informations, voir [Restauration des données de surveillance ou d’archivage](lync-server-2013-restoring-monitoring-or-archiving-data.md).

