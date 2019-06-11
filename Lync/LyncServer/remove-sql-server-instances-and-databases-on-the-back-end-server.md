---
title: Suppression des instances et des bases de données SQL Server sur le serveur principal
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f03a318e81b839d5f92dbaa4ddcc70bbbc8e2e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="98f87-102">Suppression des instances et des bases de données SQL Server sur le serveur principal</span><span class="sxs-lookup"><span data-stu-id="98f87-102">Remove SQL Server instances and databases on the Back End Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98f87-103">_**Dernière modification de la rubrique:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="98f87-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="98f87-104">Vous supprimez les bases de données et instances Microsoft SQL Server après la suppression des serveurs exécutant Lync Server 2010 qui en dépendent, ou après la reconfiguration des serveurs exécutant Lync Server 2010 pour utiliser une autre base de données.</span><span class="sxs-lookup"><span data-stu-id="98f87-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="98f87-105">Vous devez effectuer la procédure décrite dans cette rubrique lorsque vous supprimez le serveur SQL Server actuel ou que vous reconfigurez le serveur actuel exécutant Lync Server 2010 de telle sorte qu’il affiche les bases de données obsolètes ou indisponibles.</span><span class="sxs-lookup"><span data-stu-id="98f87-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="98f87-106">Pour supprimer les bases de données ou les instances du serveur d’archivage ou du serveur de surveillance, vous devez d’abord supprimer le rôle de serveur.</span><span class="sxs-lookup"><span data-stu-id="98f87-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="98f87-107">De même, pour supprimer les instances ou bases de données du pool frontal, vous devez d’abord supprimer ou reconfigurer le rôle de serveur dépendant.</span><span class="sxs-lookup"><span data-stu-id="98f87-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="98f87-108">Ces procédures n’effectuent aucune distinction entre les bases de données colocalisées ou les instances distinctes pour les serveurs.</span><span class="sxs-lookup"><span data-stu-id="98f87-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="98f87-109">Les procédures ne sont pas affectées par la colocalisation des bases de données.</span><span class="sxs-lookup"><span data-stu-id="98f87-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="98f87-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="98f87-110">In This Section</span></span>

  - [<span data-ttu-id="98f87-111">Suppression de la base de données SQL Server pour un pool frontal</span><span class="sxs-lookup"><span data-stu-id="98f87-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="98f87-112">Suppression de la base de données SQL Server pour un serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="98f87-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="98f87-113">Suppression de la base de données SQL Server pour un serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="98f87-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

