---
title: "Dépl. du serv. de gest. centralisée Lync Server 2010 vers Lync Server 2013"
TOCtitle: "Dépl. du serv. de gest. centralisée Lync Server 2010 vers Lync Server 2013"
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49891290
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacement du serveur de gestion centralisée Lync Server 2010 vers Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-25_

Après la migration de Lync Server 2010 vers Lync Server 2013, vous devez déplacer le serveur de gestion centraliséeLync Server 2010 vers le serveur frontal ou le pool de serveurs frontaux Lync Server 2013 avant de pouvoir supprimer l’ancien serveur Lync Server 2010.

Le serveur de gestion centralisée est un système de réplicas multi-maître, dans lequel la copie en lecture/écriture de la base de données est abritée par le serveur frontal qui contient le serveur de gestion centralisée. Chaque ordinateur de la topologie, notamment le serveur frontal qui contient le serveur de gestion centralisée, dispose d’une copie en lecture seule des données du magasin central de gestion dans la base de données SQL Server (nommée RTCLOCAL par défaut) installée sur l’ordinateur pendant la configuration et le déploiement. La base de données locale reçoit des mises à jour de réplicas par le biais de l’agent réplicateur Lync Server exécuté en tant que service sur tous les ordinateurs. Le nom de la base de données réelle sur le serveur de gestion centralisée et du réplica local est XDS, constitué des fichiers xds.mdf et xds.ldf. L’emplacement de la base de données maître est référencé par un point de contrôle de service dans les services de domaine Active Directory. Tous les outils qui utilisent le serveur de gestion centralisée pour gérer et configurer Lync Server utilisent le point de contrôle de service pour situer le magasin central de gestion.

Après avoir déplacé le serveur de gestion centralisée, vous devez supprimer les bases de données du serveur de gestion centralisée du serveur frontal d’origine. Pour plus d’informations sur la suppression des bases de données du serveur de gestion centralisée, reportez-vous à [Suppression de la base de données SQL Server pour un pool frontal](remove-the-sql-server-database-for-a-front-end-pool.md).

Vous utilisez l’applet de commande Windows PowerShell**Move-CsManagementServer** dans Lync Server Management Shell pour déplacer la base de données depuis la base de données SQL Server Lync Server 2010 vers la base de données SQL Server Lync Server 2013, puis mettre à jour le point de contrôle de service afin qu’il pointe vers l’emplacement du serveur de gestion centraliséeLync Server 2013.

## Préparation des serveurs frontauxLync Server 2013 avant de déplacer le serveur de gestion centralisée

Utilisez les procédures indiquées dans cette section pour préparer les serveurs frontauxLync Server 2013 avant le déplacement du serveur de gestion centraliséeLync Server 2010.

## Pour préparer un pool de serveurs frontaux Enterprise Edition

1.  Sur le pool de serveurs frontauxLync Server 2013 Enterprise Edition sur lequel vous voulez déplacer le serveur de gestion centralisée : connectez-vous en tant que membre du groupe **RTCUniversalServerAdmins** à l’ordinateur sur lequel Lync Server Management Shell est installé. Vous devez aussi disposer des droits et autorisations d’administrateur système sur la base de données SQL Server sur laquelle vous voulez installer le magasin central de gestion.

2.  Ouvrez Lync Server Management Shell.

3.  Pour créer le nouveau magasin central de gestion dans la base de données SQL Server Lync Server 2013, dans Lync Server Management Shell, tapez :
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  Vérifiez que le statut du service du **Serveur principal Lync Server** est **Démarré** .

## Pour préparer un serveur frontal Standard Edition

1.  Sur le serveur frontalLync Server 2013 Standard Edition sur lequel vous voulez déplacer le serveur de gestion centralisée : connectez-vous en tant que membre du groupe **RTCUniversalServerAdmins** à l’ordinateur sur lequel Lync Server Management Shell est installé.

2.  Ouvrez Assistant Déploiement de Lync Server.

3.  Dans l’Assistant Déploiement de Lync Server, cliquez sur **Préparer d’abord le serveur Standard Edition** .

4.  Dans la page **Exécution de commandes** , SQL Server Express est installé en tant que serveur de gestion centralisée. Les règles de pare-feu nécessaires sont créées. Lorsque l’installation de la base de données et des logiciels prérequis est terminée, cliquez sur **Terminer** .
    
    > [!NOTE]  
    > L’installation initiale peut durer un certain temps sans que les mises à jour ne soient visibles sur l’écran récapitulatif des résultats de la commande. Cela est dû à l’installation de SQL Server Express. Pour surveiller l’installation de la base de données, utilisez le Gestionnaire des tâches.

5.  Pour créer le magasin central de gestion sur le serveur frontalLync Server 2013 Standard Edition, dans Lync Server Management Shell, tapez :
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  Vérifiez que le statut du service du **Serveur principal Lync Server** est **Démarré** .

## Pour déplacer le serveur de gestion centraliséeLync Server 2010 vers Lync Server 2013

1.  Sur le serveur Lync Server 2013 qui sera le serveur de gestion centralisée : connectez-vous en tant que membre du groupe **RTCUniversalServerAdmins** sur l’ordinateur sur lequel Lync Server Management Shell est installé. Vous devez aussi disposer des droits et autorisation d’administrateur système sur la base de données SQL.

2.  Ouvrez le Lync Server Management Shell.

3.  Dans Lync Server Management Shell, tapez :
    
        Enable-CsTopology
    
    > [!WARNING]  
    > Si <code>Enable-CsTopology</code> ne donne pas de résultat satisfaisant, corrigez le problème en empêchant la commande d’aboutir avant de poursuivre. Si <strong>Enable-CsTopology</strong> ne donne pas de résultat satisfaisant, le déplacement échouera et votre topologie ne contiendra pas de magasin central de gestion.

4.  Sur le serveur frontal ou pool de serveurs frontauxLync Server 2013, dans Lync Server Management Shell, tapez :
    
        Move-CsManagementServer

5.  Lync Server Management Shell affiche les serveurs, les magasins de fichiers, les magasins de bases de données et les points de connexion du service de l’État actuel et de l’État proposé. Lisez soigneusement les informations et confirmez qu’il s’agit de la source et de la destination prévues. Tapez **Y** pour continuer, ou **N** pour cesser le déplacement.

6.  Examinez l’ensemble des erreurs et des avertissements générés par la commande **Move-CsManagementServer** et corrigez-les.

7.  Sur le serveur Lync Server 2013, ouvrez l’Assistant Déploiement de Lync Server.

8.  Dans l’Assistant Déploiement de Lync Server, cliquez successivement sur **Installer ou mettre à jour le système Lync Server** , **Étape 2 : Installer ou supprimer des composants Lync Server** , **Suivant** , examinez la synthèse, puis cliquez sur **Terminer** .

9.  Sur le serveur Lync Server 2010, ouvrez l’Assistant Déploiement de Lync Server.

10. Dans l’Assistant Déploiement de Lync Server, cliquez successivement sur **Installer ou mettre à jour le système Lync Server** , **Étape 2 : Installer ou supprimer des composants Lync Server** , **Suivant** , examinez la synthèse, puis cliquez sur **Terminer** .

11. Redémarrez le serveur Lync Server 2013. Ce redémarrage est nécessaire en raison d’un changement d’appartenance à un groupe pour l’accès à la base de données serveur de gestion centralisée.

12. Pour vérifier que la réplication est en cours avec le nouveau magasin central de gestion, dans Lync Server Management Shell, tapez :
    
        Get-CsManagementStoreReplicationStatus
    
    > [!NOTE]  
    > La réplication peut prendre un certain temps pour mettre à jour tous les réplicas.

## Pour supprimer les fichiers du magasin central de gestionLync Server 2010 après un déplacement

1.  Sur le serveur Lync Server 2010 : connectez-vous en tant que membre du groupe **RTCUniversalServerAdmins** sur l’ordinateur sur lequel Lync Server Management Shell est installé. Vous devez aussi disposer des droits et autorisation d’administrateur système sur la base de données SQL.

2.  Ouvrez Lync Server Management Shell.
    
    > [!WARNING]  
    > Ne procédez pas à la suppression des fichiers de base de données précédents avant que la réplication soit terminée et stable. Si vous supprimez les fichiers avant la fin de leur réplication, vous perturberez le processus de réplication et laisserez le serveur de gestion centralisée récemment déplacé dans un état inconnu. Utilisez l’applet de commande <strong>Get-CsManagementStoreReplicationStatus</strong> pour confirmer le statut de réplication.

3.  Pour supprimer les fichiers de base de données du magasin central de gestion du serveur de gestion centraliséeLync Server 2010, tapez :
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    Exemple :
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    Où *\<Nom de domaine complet du serveur SQL\>* peut être le nom de domaine complet du serveur principal Lync Server 2010 dans un déploiement Enterprise Edition ou celui du serveur Standard Edition.

