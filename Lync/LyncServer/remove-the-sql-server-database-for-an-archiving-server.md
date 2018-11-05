---
title: Suppression de la base de données SQL Server pour un serveur d’archivage
TOCTitle: Suppression de la base de données SQL Server pour un serveur d’archivage
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49891390
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression de la base de données SQL Server pour un serveur d’archivage

 

_**Dernière rubrique modifiée :** 2012-10-04_

Une fois que vous avez supprimé un serveur d’archivageMicrosoft Lync Server 2010, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du Générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.

## Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie

1.  Sur le serveur frontal Lync Server 2013, ouvrez le Générateur de topologie.

2.  Dans Générateur de topologie, accédez à **Composants partagés**, puis à **Magasins SQL Server**. Cliquez avec le bouton droit sur l’instance SQL Server associée au composant serveur d’archivage supprimé ou reconfiguré, puis cliquez sur **Supprimer**.

3.  Publiez la topologie, puis vérifiez l’état de la réplication.

## Pour supprimer les fichiers de base de données du serveur SQL Server

1.  Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe des administrateurs système SQL Server chargés du serveur sur lequel vous voulez supprimer les fichiers de base de données.

2.  Ouvrez Lync Server Management Shell.

3.  Dans la ligne de commande, tapez ce qui suit :
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Où *\<FQDN\>* est le nom de domaine complet du serveur de bases de données, et *\<instance\>* l’instance de base de données nommée (si elle a été définie).

4.  Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur la touche **O** (ou appuyez sur Entrée) pour continuer ou sur **N** puis Entrée si vous souhaitez arrêter l’applet de commande (en cas d’erreur).

