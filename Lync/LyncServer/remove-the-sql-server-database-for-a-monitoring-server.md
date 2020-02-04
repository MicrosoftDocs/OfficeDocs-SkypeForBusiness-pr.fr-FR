---
title: Suppression de la base de données SQL Server pour un serveur de surveillance
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
ms.openlocfilehash: 0f877f7d8d1ade4d260ed137f52046c21f29cf11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="1ed96-102">Suppression de la base de données SQL Server pour un serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="1ed96-102">Remove the SQL Server database for a Monitoring server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ed96-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="1ed96-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="1ed96-104">Après avoir supprimé un serveur de surveillance Microsoft Lync Server 2010, vous pouvez supprimer les bases de données SQL Server ayant hébergé les données du serveur.</span><span class="sxs-lookup"><span data-stu-id="1ed96-104">After you remove a Microsoft Lync Server 2010 Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="1ed96-105">Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="1ed96-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="1ed96-106">Pour supprimer la base de données SQL Server à l’aide du générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="1ed96-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="1ed96-107">Sur le serveur frontal Lync Server 2013, ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="1ed96-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="1ed96-108">Dans le générateur de topologie, accédez à **composants partagés** puis aux **magasins SQL Server**, cliquez avec le bouton droit sur l’instance SQL Server associée au serveur de surveillance supprimé ou reconfiguré, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1ed96-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="1ed96-109">Publiez la topologie, puis vérifiez l’état de la réplication.</span><span class="sxs-lookup"><span data-stu-id="1ed96-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="1ed96-110">Pour supprimer les fichiers de base de données du serveur SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ed96-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="1ed96-111">Pour supprimer les bases de données du serveur SQL Server, vous devez être membre du groupe sysadmin SQL Server pour le serveur SQL Server sur lequel vous supprimez les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="1ed96-111">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>

2.  <span data-ttu-id="1ed96-112">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1ed96-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="1ed96-113">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="1ed96-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="1ed96-114">Où \<FQDN\> est le nom de domaine complet (FQDN) du serveur de base de données \<et\> l’instance est l’instance de base de données nommée facultative.</span><span class="sxs-lookup"><span data-stu-id="1ed96-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the optional named database instance.</span></span>

4.  <span data-ttu-id="1ed96-115">Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur **Y** (ou appuyez sur entrée) pour continuer ou sur **N** , puis sur entrée si vous souhaitez arrêter l’applet de commande (autrement dit, en cas d’erreurs).</span><span class="sxs-lookup"><span data-stu-id="1ed96-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

