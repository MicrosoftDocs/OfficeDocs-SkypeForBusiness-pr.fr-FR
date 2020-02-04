---
title: Suppression de la base de données SQL Server pour un pool frontal
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 853b52c6f6a06d05f106114ab6b59ebc52129fc3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="74cd3-102">Suppression de la base de données SQL Server pour un pool frontal</span><span class="sxs-lookup"><span data-stu-id="74cd3-102">Remove the SQL Server database for a Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74cd3-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="74cd3-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="74cd3-104">Après avoir supprimé une réserve Microsoft Lync Server 2010 frontale ou reconfigurer le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server qui ont hébergé les données du pool.</span><span class="sxs-lookup"><span data-stu-id="74cd3-104">After you remove a Microsoft Lync Server 2010 Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="74cd3-105">Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="74cd3-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="74cd3-106">Pour supprimer la base de données SQL Server à l’aide du générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="74cd3-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="74cd3-107">À partir du serveur frontal Lync Server 2013, ouvrez le générateur de topologie et téléchargez la topologie existante.</span><span class="sxs-lookup"><span data-stu-id="74cd3-107">From the Lync Server 2013 Front End Server, open Topology Builder and download the existing topology.</span></span>

2.  <span data-ttu-id="74cd3-108">Dans le générateur de topologie, accédez à **composants partagés** , puis aux **magasins SQL Server**, cliquez avec le bouton droit sur l’instance SQL Server associée au pool frontal supprimé ou reconfiguré, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="74cd3-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>

3.  <span data-ttu-id="74cd3-109">Publiez la topologie, puis vérifiez l’état de la réplication.</span><span class="sxs-lookup"><span data-stu-id="74cd3-109">Publish the topology, and then check the replication status.</span></span>

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="74cd3-110">Pour supprimer des bases de données d’application et d’application du serveur SQL Server</span><span class="sxs-lookup"><span data-stu-id="74cd3-110">To remove user and application databases from the SQL Server</span></span>

1.  <span data-ttu-id="74cd3-111">Pour supprimer les bases de données du serveur SQL Server, vous devez être membre du groupe sysadmin SQL Server pour le serveur SQL sur lequel vous supprimez les fichiers de la base de données.</span><span class="sxs-lookup"><span data-stu-id="74cd3-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="74cd3-112">Ouvrez Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="74cd3-112">Open Lync Server Management Shell</span></span>

3.  <span data-ttu-id="74cd3-113">Pour supprimer la base de données du magasin utilisateur de la liste, tapez :</span><span class="sxs-lookup"><span data-stu-id="74cd3-113">To remove the database for the pool user store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="74cd3-114">Où \<FQDN\> est le nom de domaine complet (FQDN) du serveur de base de données \<et\> l’instance est l’instance de base de données nommée (autrement dit, le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="74cd3-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="74cd3-115">Pour supprimer la base de données du magasin d’applications de réserve, tapez :</span><span class="sxs-lookup"><span data-stu-id="74cd3-115">To remove the database for the pool application store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="74cd3-116">Où \<FQDN\> est le nom de domaine complet du serveur de \<base\> de données et l’instance est l’instance de base de données nommée (autrement dit, le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="74cd3-116">Where \<FQDN\> is the FQDN of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

5.  <span data-ttu-id="74cd3-117">Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur **Y** (ou appuyez sur entrée) pour continuer ou sur **N** , puis sur entrée si vous souhaitez arrêter l’applet de commande (autrement dit, en cas d’erreurs).</span><span class="sxs-lookup"><span data-stu-id="74cd3-117">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

