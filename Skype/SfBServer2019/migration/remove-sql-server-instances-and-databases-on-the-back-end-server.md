---
title: Supprimer des instances de SQL Server et les bases de données sur le serveur principal
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Pour supprimer les bases de données Microsoft SQL Server, instances après avoir supprimé les serveurs exécutant qui dépendent les, ou une fois que vous reconfigurez les serveurs pour utiliser une autre base de données. Vous devez effectuer la procédure dans cette rubrique lorsque vous retirer le serveur SQL Server en cours ou reconfigurez le serveur actuel de telle sorte qu’il s’affiche les bases de données obsolètes ou non disponible.
ms.openlocfilehash: 648c808ee293c4fa33352d0f68ba337e4a489d27
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027878"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="5b98b-104">Supprimer des instances de SQL Server et les bases de données sur le serveur principal</span><span class="sxs-lookup"><span data-stu-id="5b98b-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="5b98b-105">Pour supprimer les bases de données Microsoft SQL Server, instances après avoir supprimé les serveurs exécutant qui dépendent les, ou une fois que vous reconfigurez les serveurs pour utiliser une autre base de données.</span><span class="sxs-lookup"><span data-stu-id="5b98b-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="5b98b-106">Vous devez effectuer la procédure dans cette rubrique lorsque vous retirer le serveur SQL Server en cours ou reconfigurez le serveur actuel de telle sorte qu’il s’affiche les bases de données obsolètes ou non disponible.</span><span class="sxs-lookup"><span data-stu-id="5b98b-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="5b98b-107">Pour supprimer les bases de données ou les instances de serveur d’archivage ou un serveur de surveillance, vous devez d’abord supprimer le rôle de serveur.</span><span class="sxs-lookup"><span data-stu-id="5b98b-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="5b98b-108">De même, pour supprimer les instances de bases de données pour un pool frontal, vous devez tout d’abord supprimer ou reconfigurer le rôle de serveur qui en dépendent.</span><span class="sxs-lookup"><span data-stu-id="5b98b-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="5b98b-109">Ces procédures font pas de distinction entre les bases de données COLOCALISÉES ou instances distinctes pour les serveurs.</span><span class="sxs-lookup"><span data-stu-id="5b98b-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="5b98b-110">Les procédures ne sont pas affectés par la colocalisation des bases de données.</span><span class="sxs-lookup"><span data-stu-id="5b98b-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="5b98b-111">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="5b98b-111">In this section</span></span>

- [<span data-ttu-id="5b98b-112">Supprimer la base de données SQL Server pour un pool frontal</span><span class="sxs-lookup"><span data-stu-id="5b98b-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="5b98b-113">Supprimer la base de données SQL Server pour un serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="5b98b-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="5b98b-114">Supprimer la base de données SQL Server pour un serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="5b98b-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

