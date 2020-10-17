---
title: Suppression de la base de données SQL Server pour un serveur d’archivage
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fab9cefc3fff51267426fd26263f9e2ec20a85ee
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518101"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="5947b-102">Suppression de la base de données SQL Server pour un serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="5947b-102">Remove the SQL Server database for an Archiving server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5947b-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="5947b-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="5947b-104">Après avoir supprimé un serveur d’archivage Microsoft Lync Server 2010, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du pool.</span><span class="sxs-lookup"><span data-stu-id="5947b-104">After you remove a Microsoft Lync Server 2010 Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="5947b-105">Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="5947b-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="5947b-106">Pour supprimer la base de données SQL Server à l’aide du générateur de topologies</span><span class="sxs-lookup"><span data-stu-id="5947b-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="5947b-107">Sur le serveur frontal Lync Server 2013, ouvrez le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="5947b-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="5947b-108">Dans le générateur de topologies, accédez à **composants partagés** , puis **magasins SQL Server**, cliquez avec le bouton droit sur l’instance SQL Server associée au serveur d’archivage supprimé ou reconfiguré, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5947b-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="5947b-109">Publiez la topologie, puis vérifiez l’état de la réplication.</span><span class="sxs-lookup"><span data-stu-id="5947b-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="5947b-110">Pour supprimer les fichiers de base de données de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5947b-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="5947b-111">Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe des administrateurs système SQL Server chargés du serveur sur lequel vous voulez supprimer les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="5947b-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="5947b-112">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5947b-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="5947b-113">Dans la ligne de commande, tapez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="5947b-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="5947b-114">Où \<FQDN\> est le nom de domaine complet (FQDN) du serveur de base de données et \<instance\> est l’instance de base de données nommée (si elle a été définie).</span><span class="sxs-lookup"><span data-stu-id="5947b-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="5947b-115">Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer vos actions, lisez les informations, puis appuyez sur **Y** (ou appuyez sur Entrée) pour poursuivre, ou sur **N**, puis sur Entrée si vous souhaitez arrêter l’applet de commande (en cas d’erreurs).</span><span class="sxs-lookup"><span data-stu-id="5947b-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

