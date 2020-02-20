---
title: Supprimer la base de données SQL Server pour un serveur de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f4a2767d64ac86fbf95f3c4cfc56a6a4dedd433
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Supprimer la base de données SQL Server pour un serveur de surveillance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Après avoir supprimé un serveur de surveillance Microsoft Lync Server 2010, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du serveur. Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Pour supprimer la base de données SQL Server à l’aide du générateur de topologies

1.  Sur le serveur frontal Lync Server 2013, ouvrez le générateur de topologies.

2.  Dans le générateur de topologies, accédez à **composants partagés** , puis **magasins SQL Server**, cliquez avec le bouton droit sur l’instance SQL Server associée au serveur de surveillance supprimé ou reconfiguré, puis cliquez sur **supprimer**.

3.  Publiez la topologie, puis vérifiez l’état de la réplication.

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>Pour supprimer les fichiers de base de données du serveur SQL Server

1.  Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe sysadmins SQL Server pour le serveur SQL Server sur lequel vous supprimez les fichiers de base de données.

2.  Ouvrez Lync Server Management Shell.

3.  Dans la ligne de commande, tapez le code suivant :
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Où \<FQDN\> est le nom de domaine complet (FQDN) du serveur de base de données \<et\> instance est l’instance de base de données nommée facultative.

4.  Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer vos actions, lisez les informations, puis appuyez sur **Y** (ou appuyez sur Entrée) pour poursuivre, ou sur **N**, puis sur Entrée si vous souhaitez arrêter l’applet de commande (en cas d’erreurs).

</div>

</div>

<span> </span>

</div>

</div>

</div>

