---
title: Suppression de la base de données SQL Server pour un serveur d’archivage
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après avoir supprimé un serveur d’archivage, vous pouvez supprimer les bases de données SQL Server qui ont hébergé les données du pool. Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.
ms.openlocfilehash: 5997e54b2ac7a83d2bdd904a6f01cc89d7a17920
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812812"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="cd2c3-104">Suppression de la base de données SQL Server pour un serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="cd2c3-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="cd2c3-105">Après avoir supprimé un serveur d’archivage, vous pouvez supprimer les bases de données SQL Server qui ont hébergé les données du pool.</span><span class="sxs-lookup"><span data-stu-id="cd2c3-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="cd2c3-106">Utilisez les procédures suivantes pour supprimer les définitions du générateur de topologie, puis supprimez la base de données et les fichiers journaux du serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="cd2c3-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="cd2c3-107">Pour supprimer la base de données SQL Server à l’aide du générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="cd2c3-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="cd2c3-108">Sur le serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="cd2c3-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="cd2c3-109">Dans le générateur de topologie, accédez à **composants partagés** puis aux **magasins SQL Server**, cliquez avec le bouton droit sur l’instance SQL Server associée au serveur d’archivage supprimé ou reconfiguré, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="cd2c3-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="cd2c3-110">Publiez la topologie, puis vérifiez l’état de la réplication.</span><span class="sxs-lookup"><span data-stu-id="cd2c3-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="cd2c3-111">Pour supprimer les fichiers de base de données du serveur SQL Server</span><span class="sxs-lookup"><span data-stu-id="cd2c3-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="cd2c3-112">Pour supprimer les bases de données du serveur SQL Server, vous devez être membre du groupe sysadmin SQL Server pour le serveur SQL sur lequel vous supprimez les fichiers de la base de données.</span><span class="sxs-lookup"><span data-stu-id="cd2c3-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="cd2c3-113">Ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cd2c3-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="cd2c3-114">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="cd2c3-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="cd2c3-115">Où _ \<FQDN\> _ est le nom de domaine complet (FQDN) du serveur de base de données _ \<et\> l’instance_ est l’instance de base de données nommée (autrement dit, le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="cd2c3-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="cd2c3-116">Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou entrée) pour continuer, ou appuyez sur N, puis sur entrée si vous voulez arrêter l’applet de commande (en cas d’erreur).</span><span class="sxs-lookup"><span data-stu-id="cd2c3-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

