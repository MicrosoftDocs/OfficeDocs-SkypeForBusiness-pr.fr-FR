---
title: Suppression de la base de données SQL Server pour un pool frontal
description: Supprimez la base de données SQL Server d’un pool frontal.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c5d47e4c52197c5792fa3b7770da7bbd1b26cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551260"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Suppression de la base de données SQL Server pour un pool frontal

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Après avoir supprimé un pool frontal Microsoft Lync Server 2010 ou reconfiguré le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Pour supprimer la base de données SQL Server à l’aide du générateur de topologies

1.  À partir du serveur frontal Lync Server 2013, ouvrez le générateur de topologies et téléchargez la topologie existante.

2.  Dans le générateur de topologies, accédez à **composants partagés** , puis **magasins SQL Server**, cliquez avec le bouton droit sur l’instance SQL Server associée au pool frontal supprimé ou reconfiguré, puis cliquez sur **supprimer**.

3.  Publiez la topologie, puis vérifiez l’état de la réplication.

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Pour supprimer les bases de données d’utilisateurs et d’applications depuis le serveur SQL

1.  Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe des administrateurs système SQL Server chargés du serveur sur lequel vous voulez supprimer les fichiers de base de données.

2.  Ouvrir Lync Server Management Shell

3.  Pour supprimer la base de données du magasin d’utilisateurs du pool, tapez :
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Où \<FQDN\> est le nom de domaine complet (FQDN) du serveur de base de données et \<instance\> est l’instance de base de données nommée (si elle a été définie).

4.  Pour supprimer la base de données du magasin d’applications du pool, tapez :
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Où \<FQDN\> représente le nom de domaine complet (FQDN) du serveur de base de données et \<instance\> l’instance de base de données nommée (si elle a été définie).

5.  Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer vos actions, lisez les informations, puis appuyez sur **Y** (ou appuyez sur Entrée) pour poursuivre, ou sur **N**, puis sur Entrée si vous souhaitez arrêter l’applet de commande (en cas d’erreurs).

</div>

</div>

<span> </span>

</div>

</div>

</div>

