---
title: Suppression de la base de données SQL Server pour un serveur de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdb2888a6c3dc7cc5dd4e3b77b70310a405f607d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Suppression de la base de données SQL Server pour un serveur de surveillance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-04_

Après avoir supprimé un serveur de surveillance Microsoft Lync Server 2010, vous pouvez supprimer les bases de données SQL Server ayant hébergé les données du serveur. Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Pour supprimer la base de données SQL Server à l’aide du générateur de topologie

1.  Sur le serveur frontal Lync Server 2013, ouvrez le générateur de topologie.

2.  Dans le générateur de topologie, accédez à **composants partagés** puis aux **magasins SQL Server**, cliquez avec le bouton droit sur l’instance SQL Server associée au serveur de surveillance supprimé ou reconfiguré, puis cliquez sur **supprimer**.

3.  Publiez la topologie, puis vérifiez l’état de la réplication.

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>Pour supprimer les fichiers de base de données du serveur SQL Server

1.  Pour supprimer les bases de données du serveur SQL Server, vous devez être membre du groupe sysadmin SQL Server pour le serveur SQL Server sur lequel vous supprimez les fichiers de base de données.

2.  Ouvrez Lync Server Management Shell.

3.  Dans la ligne de commande, tapez ce qui suit :
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Où \<FQDN\> est le nom de domaine complet (FQDN) du serveur de base de données \<et\> l’instance est l’instance de base de données nommée facultative.

4.  Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur **Y** (ou appuyez sur entrée) pour continuer ou sur **N** , puis sur entrée si vous souhaitez arrêter l’applet de commande (autrement dit, en cas d’erreurs).

</div>

</div>

<span> </span>

</div>

</div>

</div>

