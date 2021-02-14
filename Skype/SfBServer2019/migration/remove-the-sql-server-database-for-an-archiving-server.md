---
title: Suppression de la base de données SQL Server pour un serveur d’archivage
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
description: Après avoir supprimé un serveur d’archivage, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du Générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753306"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="9549e-104">Suppression de la base de données SQL Server pour un serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="9549e-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="9549e-105">Après avoir supprimé un serveur d’archivage, vous pouvez supprimer les bases de données SQL Server qui hébergeaient les données du pool.</span><span class="sxs-lookup"><span data-stu-id="9549e-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="9549e-106">Utilisez les procédures suivantes pour supprimer les définitions du Générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="9549e-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="9549e-107">Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="9549e-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="9549e-108">Sur le serveur frontal Skype Entreprise Server 2019, ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="9549e-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="9549e-109">Dans le Générateur de topologie, accédez à **Composants partagés,** puis **SQL Server Stores,** cliquez avec le bouton droit sur l’instance SQL Server associée au serveur d’archivage supprimé ou reconfiguré, puis cliquez sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="9549e-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="9549e-110">Publiez la topologie, puis vérifiez l’état de la réplication.</span><span class="sxs-lookup"><span data-stu-id="9549e-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="9549e-111">Pour supprimer les fichiers de base de données de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9549e-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="9549e-112">Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe des administrateurs système SQL Server chargés du serveur sur lequel vous voulez supprimer les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="9549e-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="9549e-113">Ouvrez Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9549e-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="9549e-114">Dans la ligne de commande, tapez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="9549e-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="9549e-115">Où se trouve le nom de domaine complet (FQDN) du serveur de base de données et l’instance de base de données nommée (si elle  _\<FQDN\>_  _\<instance\>_ a été définie).</span><span class="sxs-lookup"><span data-stu-id="9549e-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="9549e-116">Lorsque l’cmdlet **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou Entrée) pour continuer, ou appuyez sur N, puis sur Entrée si vous souhaitez arrêter l’cmdlet (s’il existe des erreurs).</span><span class="sxs-lookup"><span data-stu-id="9549e-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

