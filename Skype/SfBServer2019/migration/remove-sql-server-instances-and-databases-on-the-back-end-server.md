---
title: Suppression des instances et des bases de données SQL Server sur le serveur principal
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
description: Vous supprimez les bases de données et les instances Microsoft SQL Server après avoir supprimé les serveurs en cours d’exécution qui en dépendent, ou après avoir reconfiguré les serveurs pour qu’ils utilisent une autre base de données. Vous devez effectuer la procédure décrite dans cette rubrique lorsque vous désactivez le serveur SQL Server actuel ou reconfigurez le serveur actuel de telle sorte qu’il rende les bases de données obsolètes ou indisponibles.
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752156"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="c4531-104">Suppression des instances et des bases de données SQL Server sur le serveur principal</span><span class="sxs-lookup"><span data-stu-id="c4531-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="c4531-105">Vous supprimez les bases de données et les instances Microsoft SQL Server après avoir supprimé les serveurs en cours d’exécution qui en dépendent, ou après avoir reconfiguré les serveurs pour qu’ils utilisent une autre base de données.</span><span class="sxs-lookup"><span data-stu-id="c4531-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="c4531-106">Vous devez effectuer la procédure décrite dans cette rubrique lorsque vous désactivez le serveur SQL Server actuel ou reconfigurez le serveur actuel de telle sorte qu’il rende les bases de données obsolètes ou indisponibles.</span><span class="sxs-lookup"><span data-stu-id="c4531-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="c4531-107">Pour supprimer les bases de données ou les instances du serveur d’archivage ou du serveur de surveillance, vous devez d’abord supprimer le rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="c4531-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="c4531-108">De même, pour supprimer les instances ou les bases de données du pool frontal, vous devez d’abord supprimer ou reconfigurer le rôle de serveur dépendant.</span><span class="sxs-lookup"><span data-stu-id="c4531-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="c4531-109">Ces procédures ne font pas de distinction entre les bases de données colocalisées et les instances séparées des serveurs.</span><span class="sxs-lookup"><span data-stu-id="c4531-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="c4531-110">Elles ne sont pas affectées par la colocalisation des bases de données.</span><span class="sxs-lookup"><span data-stu-id="c4531-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="c4531-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c4531-111">In this section</span></span>

- [<span data-ttu-id="c4531-112">Suppression de la base de données SQL Server pour un pool frontal</span><span class="sxs-lookup"><span data-stu-id="c4531-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="c4531-113">Suppression de la base de données SQL Server pour un serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="c4531-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="c4531-114">Suppression de la base de données SQL Server pour un serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="c4531-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

