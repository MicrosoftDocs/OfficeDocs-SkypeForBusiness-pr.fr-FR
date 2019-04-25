---
title: Suppression de la base de données SQL Server pour un serveur de surveillance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Une fois que vous supprimez un serveur de surveillance, vous pouvez supprimer les bases de données SQL Server hébergeant les données du serveur. Utilisez les procédures suivantes pour supprimer les définitions de générateur de topologie, puis supprimer les fichiers journaux et de base de données à partir du serveur de base de données.
ms.openlocfilehash: 7e299eb2de3fc0820cd4497c2956c71ceec79910
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231370"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="07cbc-104">Suppression de la base de données SQL Server pour un serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="07cbc-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="07cbc-105">Une fois que vous supprimez un serveur de surveillance, vous pouvez supprimer les bases de données SQL Server hébergeant les données du serveur.</span><span class="sxs-lookup"><span data-stu-id="07cbc-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="07cbc-106">Utilisez les procédures suivantes pour supprimer les définitions de générateur de topologie, puis supprimer les fichiers journaux et de base de données à partir du serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="07cbc-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="07cbc-107">Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="07cbc-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="07cbc-108">Sur Skype pour Business Server 2019 serveur frontal, ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="07cbc-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="07cbc-109">Dans le Générateur de topologie, accédez à **Composants partagés** puis **Magasins SQL Server**, cliquez sur le serveur SQL Server instance associé supprimé ou reconfiguré le serveur de surveillance, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="07cbc-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="07cbc-110">Publiez la topologie, puis vérifier l’état de réplication.</span><span class="sxs-lookup"><span data-stu-id="07cbc-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="07cbc-111">Pour supprimer les fichiers de base de données de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="07cbc-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="07cbc-112">Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe administrateurs système SQL Server pour le serveur SQL Server où vous supprimez les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="07cbc-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="07cbc-113">Ouvrez le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="07cbc-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="07cbc-114">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="07cbc-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="07cbc-115">Où _ \<nom de domaine complet\> _ est le nom de domaine complet (FQDN) du serveur de base de données, et _ \<instance\> _ l’instance de base de données nommée facultative.</span><span class="sxs-lookup"><span data-stu-id="07cbc-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="07cbc-116">Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou entrez) pour continuer ou appuyez sur N et appuyez sur entrée, si vous souhaitez arrêter l’applet de commande (s’il y a des erreurs).</span><span class="sxs-lookup"><span data-stu-id="07cbc-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

