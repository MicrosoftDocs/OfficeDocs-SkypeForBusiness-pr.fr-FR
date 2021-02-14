---
title: Suppression de la base de données SQL Server pour un pool frontal
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après avoir supprimé un pool frontal ou reconfiguré le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du Générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753406"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="2b933-104">Suppression de la base de données SQL Server pour un pool frontal</span><span class="sxs-lookup"><span data-stu-id="2b933-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="2b933-105">Après avoir supprimé un pool frontal ou reconfiguré le pool pour utiliser une autre base de données, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du pool.</span><span class="sxs-lookup"><span data-stu-id="2b933-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="2b933-106">Utilisez les procédures suivantes pour supprimer les définitions du Générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="2b933-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="2b933-107">Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="2b933-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="2b933-108">À partir du serveur frontal Skype Entreprise Server 2019, ouvrez le Générateur de topologie et téléchargez la topologie existante.</span><span class="sxs-lookup"><span data-stu-id="2b933-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="2b933-109">Dans le Générateur de topologie, accédez à **Composants partagés,** puis **SQL Server Stores,** cliquez avec le bouton droit sur l’instance SQL Server associée au pool frontal supprimé ou reconfiguré, puis cliquez sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="2b933-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="2b933-110">Publiez la topologie, puis vérifiez l’état de la réplication.</span><span class="sxs-lookup"><span data-stu-id="2b933-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="2b933-111">Pour supprimer des bases de données utilisateur et d’application du SQL serveur</span><span class="sxs-lookup"><span data-stu-id="2b933-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="2b933-112">Pour supprimer les bases de données sur le serveur SQL, vous devez être membre du groupe SQL Server sysadmins pour le serveur SQL où vous supprimez les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="2b933-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="2b933-113">Ouvrez Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2b933-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="2b933-114">Pour supprimer la base de données du magasin d’utilisateurs du pool, tapez :</span><span class="sxs-lookup"><span data-stu-id="2b933-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="2b933-115">Où se trouve le nom de domaine complet (FQDN) du serveur de base de données et l’instance de base de données nommée (si elle  _\<FQDN\>_  _\<instance\>_ a été définie).</span><span class="sxs-lookup"><span data-stu-id="2b933-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="2b933-116">Pour supprimer la base de données du magasin d’applications du pool, tapez :</span><span class="sxs-lookup"><span data-stu-id="2b933-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="2b933-117">Où  _\<FQDN\>_ se trouve le nom deqdn du serveur de base de données et l’instance de base de données nommée (c’est-à-dire, si une instance a été  _\<instance\>_ définie).</span><span class="sxs-lookup"><span data-stu-id="2b933-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="2b933-118">Lorsque l’cmdlet **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou Entrée) pour continuer, ou appuyez sur N, puis sur Entrée si vous souhaitez arrêter l’cmdlet (s’il existe des erreurs).</span><span class="sxs-lookup"><span data-stu-id="2b933-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

