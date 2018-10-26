---
title: Suppression de la base de données SQL Server pour un serveur de surveillance
TOCTitle: Suppression de la base de données SQL Server pour un serveur de surveillance
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49891492
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression de la base de données SQL Server pour un serveur de surveillance

 

_**Dernière rubrique modifiée :** 2012-10-04_

Après avoir supprimé un serveur de surveillanceMicrosoft Lync Server 2010, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données de serveur. Utilisez les procédures suivantes pour supprimer les définitions à partir du Générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de bases de données.

## Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie

1.  Sur le serveur frontal Lync Server 2013, ouvrez le Générateur de topologie.

2.  Dans le Générateur de topologie, accédez à **Composants partagés** puis à **Magasins SQL Server** , cliquez avec le bouton droit sur l’instance SQL Server associée au serveur de surveillance ayant été supprimé ou reconfiguré, puis cliquez sur **Supprimer** .

3.  Publiez la topologie, puis vérifiez l’état de la réplication.

## Pour supprimer les fichiers de base de données du serveur SQL Server

1.  Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe sysadmins SQL Server pour le serveur SQL Server sur lequel vous supprimez les fichiers de base de données.

2.  Ouvrez Lync Server Management Shell.

3.  Dans la ligne de commande, tapez ce qui suit :
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Où *\<FQDN\>* est le nom de domaine complet du serveur de bases de données et *\<instance\>* est l’instance de base de données nommée facultative.

4.  Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur la touche **O** (ou appuyez sur Entrée) pour continuer ou sur **N** puis Entrée si vous souhaitez arrêter l’applet de commande (en cas d’erreur).

