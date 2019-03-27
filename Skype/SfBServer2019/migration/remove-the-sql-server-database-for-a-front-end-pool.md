---
title: Suppression de la base de données SQL Server pour un pool frontal
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Une fois que vous supprimez un pool frontal ou reconfigurez le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server hébergeant les données du pool. Utilisez les procédures suivantes pour supprimer les définitions de générateur de topologie, puis supprimer les fichiers journaux et de base de données à partir du serveur de base de données.
ms.openlocfilehash: 4ba60a905d5f4cda56cf5277e1be2db80d906ca0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893781"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="5a454-104">Suppression de la base de données SQL Server pour un pool frontal</span><span class="sxs-lookup"><span data-stu-id="5a454-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="5a454-105">Une fois que vous supprimez un pool frontal ou reconfigurez le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server hébergeant les données du pool.</span><span class="sxs-lookup"><span data-stu-id="5a454-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="5a454-106">Utilisez les procédures suivantes pour supprimer les définitions de générateur de topologie, puis supprimer les fichiers journaux et de base de données à partir du serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="5a454-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="5a454-107">Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="5a454-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="5a454-108">Depuis Skype pour Business Server 2019 serveur frontal, ouvrez le Générateur de topologie et téléchargez la topologie existante.</span><span class="sxs-lookup"><span data-stu-id="5a454-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="5a454-109">Dans le Générateur de topologie, accédez à **Composants partagés** puis **Magasins SQL Server**, cliquez sur l’instance SQL Server associée au pool frontal supprimé ou reconfiguré, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5a454-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="5a454-110">Publiez la topologie, puis vérifiez l’état de réplication.</span><span class="sxs-lookup"><span data-stu-id="5a454-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="5a454-111">Pour supprimer les bases de données utilisateur et d’application de SQL server.</span><span class="sxs-lookup"><span data-stu-id="5a454-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="5a454-112">Pour supprimer les bases de données sur le serveur SQL server, vous devez être membre du groupe administrateurs système SQL Server pour lequel vous voulez supprimer les fichiers de base de données SQL server.</span><span class="sxs-lookup"><span data-stu-id="5a454-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="5a454-113">Ouvrez Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5a454-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="5a454-114">Pour supprimer la base de données pour le magasin d’utilisateurs pool, tapez :</span><span class="sxs-lookup"><span data-stu-id="5a454-114">To remove the database for the pool user store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="5a454-115">Où _ \<nom de domaine complet\> _ est le nom de domaine complet (FQDN) du serveur de base de données, et _ \<instance\> _ est l’instance de base de données nommée (autrement dit, si elle a été définie).</span><span class="sxs-lookup"><span data-stu-id="5a454-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="5a454-116">Pour supprimer la base de données pour le magasin d’application pool, tapez :</span><span class="sxs-lookup"><span data-stu-id="5a454-116">To remove the database for the pool application store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="5a454-117">Où _ \<nom de domaine complet\> _ est le nom de domaine complet du serveur de base de données, et _ \<instance\> _ est l’instance de base de données nommée (autrement dit, si elle a été définie).</span><span class="sxs-lookup"><span data-stu-id="5a454-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="5a454-118">Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou entrez) pour continuer ou appuyez sur N et appuyez sur entrée, si vous souhaitez arrêter l’applet de commande (s’il y a des erreurs).</span><span class="sxs-lookup"><span data-stu-id="5a454-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

