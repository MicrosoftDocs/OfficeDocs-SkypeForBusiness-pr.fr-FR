---
title: Suppression des instances et des bases de données SQL Server sur le serveur principal
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
description: Vous supprimez les bases de données et les instances Microsoft SQL Server après avoir supprimé les serveurs qui en dépendent ou après avoir reconfiguré les serveurs pour utiliser une autre base de données. Vous devez effectuer la procédure décrite dans cette rubrique lorsque vous supprimez le serveur SQL Server actuel ou que vous reconfigurez le serveur actuel de telle sorte qu’il affiche les bases de données obsolètes ou indisponibles.
ms.openlocfilehash: 01552fcd494514802fffb35de7db7643f8cc26fd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812982"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="f0050-104">Suppression des instances et des bases de données SQL Server sur le serveur principal</span><span class="sxs-lookup"><span data-stu-id="f0050-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="f0050-105">Vous supprimez les bases de données et les instances Microsoft SQL Server après avoir supprimé les serveurs qui en dépendent ou après avoir reconfiguré les serveurs pour utiliser une autre base de données.</span><span class="sxs-lookup"><span data-stu-id="f0050-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="f0050-106">Vous devez effectuer la procédure décrite dans cette rubrique lorsque vous supprimez le serveur SQL Server actuel ou que vous reconfigurez le serveur actuel de telle sorte qu’il affiche les bases de données obsolètes ou indisponibles.</span><span class="sxs-lookup"><span data-stu-id="f0050-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="f0050-107">Pour supprimer les bases de données ou les instances du serveur d’archivage ou du serveur de surveillance, vous devez d’abord supprimer le rôle de serveur.</span><span class="sxs-lookup"><span data-stu-id="f0050-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="f0050-108">De même, pour supprimer les instances ou bases de données du pool frontal, vous devez d’abord supprimer ou reconfigurer le rôle de serveur dépendant.</span><span class="sxs-lookup"><span data-stu-id="f0050-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="f0050-109">Ces procédures n’effectuent aucune distinction entre les bases de données colocalisées ou les instances distinctes pour les serveurs.</span><span class="sxs-lookup"><span data-stu-id="f0050-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="f0050-110">Les procédures ne sont pas affectées par la colocalisation des bases de données.</span><span class="sxs-lookup"><span data-stu-id="f0050-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f0050-111">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="f0050-111">In this section</span></span>

- [<span data-ttu-id="f0050-112">Suppression de la base de données SQL Server pour un pool frontal</span><span class="sxs-lookup"><span data-stu-id="f0050-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="f0050-113">Suppression de la base de données SQL Server pour un serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="f0050-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="f0050-114">Suppression de la base de données SQL Server pour un serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="f0050-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

