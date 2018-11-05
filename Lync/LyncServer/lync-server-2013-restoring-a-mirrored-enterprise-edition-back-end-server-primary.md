---
title: "Rest. d’un serv. Princ. Enterprise Edition en miroir - Base de données prim."
TOCtitle: "Rest. d’un serv. Princ. Enterprise Edition en miroir - Base de données prim."
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945648(v=OCS.15)
ms:contentKeyID: 53095513
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauration d’un serveur principal Enterprise Edition en miroir - Base de données primaire

 

_**Dernière rubrique modifiée :** 2013-02-17_

Si vous avez un serveur principal Enterprise Edition dans une configuration en miroir et que seule la base de données primaire subit une défaillance, appliquez les procédures de cette section. Si la défaillance affecte à la fois la base de données primaire et la base de données miroir, voir [Restauration du serveur principal Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Si seule la base de données miroir subit une défaillance, voir [Restauration d’un serveur principal Enterprise Edition en miroir - Miroir](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md). Si la base de données hébergeant le magasin central de gestion subit une défaillance, voir [Restauration du serveur hébergeant le magasin central de gestion](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si un serveur membre Enterprise Edition différent du serveur principal subit une défaillance, voir [Restauration d’un serveur membre Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Nous vous recommandons de faire une image du système avant de démarrer la restauration. Vous pourrez utiliser cette copie comme point de restauration au cas où un problème surviendrait lors de la restauration. Il peut être préférable de créer cette copie instantanée après avoir installé le système d’exploitation et SQL Server et après avoir restauré ou réinscrit les certificats.

Dans cette rubrique, le nom de domaine complet de l’exemple de base de données primaire est BE1.contoso.com et le nom de domaine complet de la base de données miroir est BE2.contoso.com.

## Pour restaurer une base de données primaire de serveur principal Enterprise Edition

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un serveur frontal.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Forcez le basculement de toutes les bases de données configurées vers le miroir. Pour chaque type de base de données configuré sur ce serveur, tapez l’applet de commande suivante :
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    Par exemple :
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    > [!WARNING]  
    > Si vous avez configuré votre base de données de serveur principal afin d’utiliser une mise en miroir synchronisée avec un témoin, le basculement est automatique.

4.  À l’issue du basculement, procédez comme suit :
    
      - Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.
    
      - Désactivez la mise en miroir sur le serveur principal : cliquez avec le bouton droit sur le pool sous **Pools frontaux Enterprise Edition** et sélectionnez **Modifier les propriétés**. Sous l’onglet **Général**, sous **Associations**, désactivez la case à cocher **Activer la mise en miroir du magasin SQL Server**. Procédez ainsi pour l’archivage et la surveillance si nécessaire. Ensuite, cliquez sur **OK**.
    
      - Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **Topologie**, puis sur **Publier**.
    
      - Sélectionnez le serveur principal encore opérationnel (BE2.contoso.com) comme nouveau magasin SQL store. Pour cela, cliquez avec le bouton droit sur le pool sous **Pools frontaux Enterprise Edition** et sélectionnez **Modifier les propriétés**. Sous l’onglet **Général**, sous **Associations**, tapez le nom de domaine complet du serveur principal opérationnel dans le champ **Magasin SQL Server** (dans notre exemple, BE2.contoso.com).
    
      - Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **Topologie**, puis sur **Publier**.
    
      - Redémarrez les services de sorte que chaque serveur puisse lire la nouvelle topologie. Dans Lync Server Management Shell, exécutez les applets de commande suivantes sur chaque serveur frontal appartenant à ce pool :
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  Désinstallez la mise en miroir. Dans Lync Server Management Shell, exécutez l’applet de commande suivante :
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Par exemple :
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    Procédez ainsi pour tous les types de bases de données sur ce serveur.

6.  Créez un serveur ayant le même nom de domaine complet (dans notre exemple, DB1.contoso.com) que l’ordinateur ayant subi une défaillance, installez le système d’exploitation, puis restaurez ou réinscrivez les certificats. Ce serveur fonctionnera comme nouveau miroir.

7.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, ouvrez une session sur le nouveau serveur.

8.  Installez SQL Server 2012 ou SQL Server 2008 R2, en conservant les mêmes noms d’instances qu’avant la défaillance.

9.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un serveur frontal.

10. Utilisez le Générateur de topologie pour installer la base de données miroir. Effectuez les étapes suivantes :
    
      - Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.
    
      - Activez la mise en miroir sur le serveur principal. Pour cela, cliquez avec le bouton droit sur le pool sous **Pools frontaux Enterprise Edition** et sélectionnez **Modifier les propriétés**. Sous l’onglet **Général**, sous **Associations**, activez la case à cocher **Activer la mise en miroir du magasin SQL Server**. Procédez également ainsi pour l’archivage et la surveillance si nécessaire.
        
        Ensuite, dans le champ **Magasin SQL Server de mise en miroir**, tapez le nom de domaine complet du nouveau serveur (dans notre exemple, BE1.contoso.com). Ensuite, cliquez sur **OK**.
    
      - Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **Topologie**, puis sur **Installer une base de données**.
    
      - Suivez les instructions de l’Assistant **Installer une base de données**. Dans la page **Créer des bases de données**, sélectionnez les bases de données à recréer.
    
      - Suivez les instructions de l’Assistant jusqu’à atteindre l’invite **Créer des bases de données miroir**. Sélectionnez la base de données à installer, puis terminez ce processus.

