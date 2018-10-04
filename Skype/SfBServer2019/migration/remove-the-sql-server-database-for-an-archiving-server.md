---
title: Supprimer la base de données SQL Server pour un serveur d’archivage
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après la suppression d’un serveur d’archivage, vous pouvez supprimer les bases de données SQL Server hébergeant les données du pool. Utilisez les procédures suivantes pour supprimer les définitions de générateur de topologie, puis supprimer les fichiers journaux et de base de données à partir du serveur de base de données.
ms.openlocfilehash: b7c1fe6591564a690ea1da55fb65eb1071661d63
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370800"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="c7860-104">Supprimer la base de données SQL Server pour un serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="c7860-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="c7860-105">Après la suppression d’un serveur d’archivage, vous pouvez supprimer les bases de données SQL Server hébergeant les données du pool.</span><span class="sxs-lookup"><span data-stu-id="c7860-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="c7860-106">Utilisez les procédures suivantes pour supprimer les définitions de générateur de topologie, puis supprimer les fichiers journaux et de base de données à partir du serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="c7860-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="c7860-107">Pour supprimer la base de données SQL Server à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="c7860-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="c7860-108">Sur Skype pour Business Server 2019 serveur frontal, ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="c7860-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="c7860-109">Dans le Générateur de topologie, accédez à **Composants partagés** puis **Magasins SQL Server**, cliquez sur le serveur SQL Server instance associé supprimé ou reconfiguré serveur d’archivage, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="c7860-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="c7860-110">Publiez la topologie, puis vérifier l’état de réplication.</span><span class="sxs-lookup"><span data-stu-id="c7860-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="c7860-111">Pour supprimer les fichiers de base de données de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c7860-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="c7860-112">Pour supprimer les bases de données sur le serveur SQL Server, vous devez être membre du groupe administrateurs système SQL Server pour lequel vous voulez supprimer les fichiers de base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c7860-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="c7860-113">Ouvrez le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c7860-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="c7860-114">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c7860-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="c7860-115">Où _ \<nom de domaine complet\> _ est le nom de domaine complet (FQDN) du serveur de base de données, et _ \<instance\> _ est l’instance de base de données nommée (autrement dit, si elle a été définie).</span><span class="sxs-lookup"><span data-stu-id="c7860-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="c7860-116">Lorsque l’applet de commande **Uninstall-CsDataBase** vous invite à confirmer les actions, lisez les informations, puis appuyez sur Y (ou entrez) pour continuer ou appuyez sur N et appuyez sur entrée, si vous souhaitez arrêter l’applet de commande (s’il y a des erreurs).</span><span class="sxs-lookup"><span data-stu-id="c7860-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

