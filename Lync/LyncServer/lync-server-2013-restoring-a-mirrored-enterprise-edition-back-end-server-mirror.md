---
title: Restauration d’un serveur principal Enterprise Edition en miroir - Miroir
TOCTitle: Restauration d’un serveur principal Enterprise Edition en miroir - Miroir
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945626(v=OCS.15)
ms:contentKeyID: 53095409
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauration d’un serveur principal Enterprise Edition en miroir - Miroir

 

_**Dernière rubrique modifiée :** 2013-02-19_

Si une configuration en miroir comporte un serveur principal Enterprise Edition et que seule la base de données miroir échoue, suivez les procédures indiquées dans cette section. Si la base de données primaire et la base de données miroir échouent toutes les deux, reportez-vous à [Restauration du serveur principal Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Si seule la base de données primaire échoue, reportez-vous à [Restauration d’un serveur principal Enterprise Edition en miroir - Base de données primaire](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Si la base de données hébergeant le magasin central de gestion échoue, reportez-vous à [Restauration du serveur hébergeant le magasin central de gestion](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si un serveur membre Enterprise Edition autre que le serveur principal échoue, reportez-vous à [Restauration d’un serveur membre Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Nous vous recommandons de faire une image du système avant de démarrer la restauration. Vous pouvez utiliser cette image en tant que point de restauration au cas où un problème se produise pendant la restauration. Cette image pourra être effectuée après l’installation du système d’exploitation et SQL Server, et la restauration et réinscription des certificats.

## Pour restaurer une base de données miroir d’un serveur principal Enterprise Edition

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un serveur frontal.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Désinstallez la mise en miroir. Dans un premier temps, tapez l’applet de commande suivante :
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Exemple :
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Effectuez cette opération pour tous les types de base de données sur ce serveur.

4.  Créez un serveur possédant le même nom de domaine complet (FQDN) (DB1.contoso.com) que l’ordinateur ayant échoué, installez le système d’exploitation, puis restaurez ou réinscrivez les certificats. Ce serveur fera office de nouveau miroir.

5.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, ouvrez une session sur le nouveau serveur.

6.  Installez SQL Server 2012 ou SQL Server 2008 R2, en conservant les noms d’instance qui existaient avant l’échec.

7.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un serveur frontal.

8.  Utilisez le Générateur de topologie pour installer la base de données miroir. Procédez comme suit :
    
      - Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.
    
      - Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **Topologie**, puis cliquez sur **Installer une base de données**.
    
      - Suivez l’Assistant **Installer une base de données**. Dans la page **Créer des bases de données**, sélectionnez les bases de données que vous voulez recréer.
    
      - Suivez l’Assistant jusqu’à l’apparition de l’invite **Créer des bases de données miroir**. Sélectionnez la base de données à installer, puis terminez ce processus.
        
        > [!TIP]  
        > Au lieu d’exécuter le Générateur de topologie, vous pouvez utiliser l’applet de commande <strong>Install-CsMirrorDatabase</strong>, pour configurer la mise en miroir. Pour plus d’informations, voir la documentation Lync Server Management Shell.
