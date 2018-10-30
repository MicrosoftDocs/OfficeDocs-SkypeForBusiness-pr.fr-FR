---
title: Suppression de la base de données SQL Server pour un pool frontal
TOCTitle: Suppression de la base de données SQL Server pour un pool frontal
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49891388
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression de la base de données SQL Server pour un pool frontal

 

_**Dernière rubrique modifiée :** 2012-10-04_

Lorsque vous avez supprimé un pool de serveurs frontauxMicrosoft Lync Server 2010 ou reconfiguré le serveur de sorte d’utiliser une base de données différente, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du Générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.

## Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie

1.  Depuis le serveur frontal Lync Server 2013, ouvrez le Générateur de topologie et téléchargez la topologie existante.

2.  Dans Générateur de topologie, accédez à **Composants partagés**, puis à **Magasins SQL Server**. Cliquez avec le bouton droit sur l’instance SQL Server associée au pool de serveurs frontaux supprimé ou reconfiguré, puis cliquez sur **Supprimer**.

3.  Publiez la topologie, puis vérifiez l’état de la réplication.

## Pour supprimer les bases de données d’utilisateurs et d’applications depuis le serveur SQL

1.  Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe des administrateurs système SQL Server chargés du serveur sur lequel vous voulez supprimer les fichiers de base de données.

2.  Ouvrez Lync Server Management Shell.

3.  Pour supprimer la base de données du magasin d’utilisateurs du pool, tapez :
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Où *\<FQDN\>* est le nom de domaine complet du serveur de bases de données, et *\<instance\>* l’instance de base de données nommée (si elle a été définie).

4.  Pour supprimer la base de données du magasin d’applications du pool, tapez :
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Où *\<FQDN\>* est le nom de domaine complet du serveur de bases de données, et *\<instance\>* l’instance de base de données nommée (si une a été définie).

5.  Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur la touche **O** (ou appuyez sur Entrée) pour continuer ou sur **N** puis Entrée si vous souhaitez arrêter l’applet de commande (en cas d’erreur).

