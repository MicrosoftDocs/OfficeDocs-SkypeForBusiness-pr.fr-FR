---
title: Suppression de la base de données SQL Server pour un pool frontal
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6dcbe9bcab20438d02fe489666f9b4c0c0f6d0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Suppression de la base de données SQL Server pour un pool frontal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-04_

Après avoir supprimé une réserve Microsoft Lync Server 2010 frontale ou reconfigurer le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server qui ont hébergé les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Pour supprimer la base de données SQL Server à l’aide du générateur de topologie

1.  À partir du serveur frontal Lync Server 2013, ouvrez le générateur de topologie et téléchargez la topologie existante.

2.  Dans le générateur de topologie, accédez à **composants partagés** , puis aux **magasins SQL Server**, cliquez avec le bouton droit sur l’instance SQL Server associée au pool frontal supprimé ou reconfiguré, puis cliquez sur **supprimer**.

3.  Publiez la topologie, puis vérifiez l’état de la réplication.

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Pour supprimer des bases de données d’application et d’application du serveur SQL Server

1.  Pour supprimer les bases de données du serveur SQL Server, vous devez être membre du groupe sysadmin SQL Server pour le serveur SQL sur lequel vous supprimez les fichiers de la base de données.

2.  Ouvrez Lync Server Management Shell

3.  Pour supprimer la base de données du magasin utilisateur de la liste, tapez:
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Où \<FQDN\> est le nom de domaine complet (FQDN) du serveur de base de données \<et\> l’instance est l’instance de base de données nommée (autrement dit, le cas échéant).

4.  Pour supprimer la base de données du magasin d’applications de réserve, tapez:
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Où \<FQDN\> est le nom de domaine complet du serveur de \<base\> de données et l’instance est l’instance de base de données nommée (autrement dit, le cas échéant).

5.  Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur **Y** (ou appuyez sur entrée) pour continuer ou sur **N** , puis sur entrée si vous souhaitez arrêter l’applet de commande (autrement dit, en cas d’erreurs).

</div>

</div>

<span> </span>

</div>

</div>

</div>

