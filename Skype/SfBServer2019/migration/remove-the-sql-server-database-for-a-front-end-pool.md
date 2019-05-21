---
title: Suppression de la base de données SQL Server pour un pool frontal
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après avoir supprimé un pool frontal ou reconfiguré le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server qui ont hébergé les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
ms.openlocfilehash: e89c8cc670256bf56cb3ff93705766191a9e32c8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301089"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="08b26-104">Suppression de la base de données SQL Server pour un pool frontal</span><span class="sxs-lookup"><span data-stu-id="08b26-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="08b26-105">Après avoir supprimé un pool frontal ou reconfiguré le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server qui ont hébergé les données du pool.</span><span class="sxs-lookup"><span data-stu-id="08b26-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="08b26-106">Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="08b26-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="08b26-107">Pour supprimer la base de données SQL Server à l’aide du générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="08b26-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="08b26-108">À partir du serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie et téléchargez la topologie existante.</span><span class="sxs-lookup"><span data-stu-id="08b26-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="08b26-109">Dans le générateur de topologie, accédez à **composants partagés** , puis aux **magasins SQL Server**, cliquez avec le bouton droit sur l’instance SQL Server associée au pool frontal supprimé ou reconfiguré, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="08b26-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="08b26-110">Publiez la topologie, puis vérifiez l’état de la réplication.</span><span class="sxs-lookup"><span data-stu-id="08b26-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="08b26-111">Pour supprimer des bases de données d’application et d’application du serveur SQL Server</span><span class="sxs-lookup"><span data-stu-id="08b26-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="08b26-112">Pour supprimer les bases de données du serveur SQL Server, vous devez être membre du groupe sysadmin SQL Server pour le serveur SQL sur lequel vous supprimez les fichiers de la base de données.</span><span class="sxs-lookup"><span data-stu-id="08b26-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="08b26-113">Ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="08b26-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="08b26-114">Pour supprimer la base de données du magasin utilisateur de la liste, tapez:</span><span class="sxs-lookup"><span data-stu-id="08b26-114">To remove the database for the pool user store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="08b26-115">Où _ \<FQDN\> _ est le nom de domaine complet (FQDN) du serveur de base de données _ \<et\> l’instance_ est l’instance de base de données nommée (autrement dit, le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="08b26-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="08b26-116">Pour supprimer la base de données du magasin d’applications de réserve, tapez:</span><span class="sxs-lookup"><span data-stu-id="08b26-116">To remove the database for the pool application store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="08b26-117">Où _ \<FQDN\> _ est le nom de domaine complet du serveur de base de données et _ \<l’instance\> _ est l’instance de base de données nommée (autrement dit, le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="08b26-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="08b26-118">Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou entrée) pour continuer, ou appuyez sur N, puis sur entrée si vous voulez arrêter l’applet de commande (en cas d’erreur).</span><span class="sxs-lookup"><span data-stu-id="08b26-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

