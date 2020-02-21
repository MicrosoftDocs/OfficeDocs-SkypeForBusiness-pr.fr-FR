---
title: 'Lync Server 2013 : composants et topologies pour la surveillance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 072dbc882940bc0f28217bcf7c41663bf9ed3708
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="25ff7-102">Composants et topologies pour la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25ff7-102">Components and topologies for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25ff7-103">_**Dernière modification de la rubrique :** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="25ff7-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="25ff7-104">Étant donné que les agents de collecte de données unifiée sont automatiquement installés et activés sur chaque serveur frontal, il n’est pas nécessaire de configurer un serveur comme serveur de surveillance ; chaque serveur frontal fonctionne déjà comme un serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="25ff7-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="25ff7-105">Toutefois, vous devrez installer et configurer une base de données qui servira de magasin de données principal pour vos données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="25ff7-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="25ff7-106">Microsoft Lync Server 2013 peut utiliser les bases de données suivantes en tant que magasin principal pour la surveillance :</span><span class="sxs-lookup"><span data-stu-id="25ff7-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="25ff7-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="25ff7-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="25ff7-108">Microsoft SQL Server 2008 R2 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="25ff7-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="25ff7-109">Microsoft SQL Server 2012 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="25ff7-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="25ff7-110">Microsoft SQL Server 2012 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="25ff7-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="25ff7-111">Notez que vous devez utiliser les éditions 64 bits de ces bases de données ; les versions 32 bits de SQL Server ne peuvent pas être utilisées en tant que magasin principal pour la surveillance.</span><span class="sxs-lookup"><span data-stu-id="25ff7-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="25ff7-112">De même, Lync Server 2013 ne prend pas en charge les éditions Express de SQL Server 2008 ou SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="25ff7-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="25ff7-113">Pour plus d’informations sur les exigences en matière de bases de données pour Lync Server 2013, voir la rubrique relative aux [logiciels de base de données dans Lync server 2013](lync-server-2013-database-software-support.md) dans le Guide de prise en charge de lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25ff7-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="25ff7-114">Gardez à l’esprit que SQL Server doit être installé et configuré avant de déployer et de configurer la surveillance.</span><span class="sxs-lookup"><span data-stu-id="25ff7-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="25ff7-115">Toutefois, vous devez seulement déployer SQL Server lui-même ; vous n’avez pas besoin de configurer les bases de données d’analyse à l’avance.</span><span class="sxs-lookup"><span data-stu-id="25ff7-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="25ff7-116">Au lieu de cela, ces bases de données sont automatiquement créées pour vous lorsque vous publiez votre topologie Lync Server.</span><span class="sxs-lookup"><span data-stu-id="25ff7-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="25ff7-117">Les données de surveillance peuvent partager une instance SQL Server avec d’autres types de données.</span><span class="sxs-lookup"><span data-stu-id="25ff7-117">Monitoring data can share a SQL Server instance with other types of data.</span></span> <span data-ttu-id="25ff7-118">En règle générale, la base de données d’enregistrement des détails des appels (LcsCdr) et la base de données de qualité de l’expérience (QoEMetrics) partagent la même instance SQL ; Il est également courant que les deux bases de données de surveillance se trouvent dans la même instance SQL que la base de données d’archivage (LcsLog).</span><span class="sxs-lookup"><span data-stu-id="25ff7-118">Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog).</span></span> <span data-ttu-id="25ff7-119">La seule exigence réelle concernant les instances SQL Server est que n’importe quelle instance de SQL Server est limitée à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="25ff7-119">About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="25ff7-120">Une instance de la base de données principale Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25ff7-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="25ff7-121">(En règle générale, il n’est pas recommandé que votre base de données de surveillance soit colocalisée dans la même instance SQL, ou même sur le même ordinateur que la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="25ff7-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="25ff7-122">Bien que techniquement possible, vous courez le risque de la base de données de surveillance à l’aide de l’espace disque nécessaire pour la base de données principale.)</span><span class="sxs-lookup"><span data-stu-id="25ff7-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="25ff7-123">Une instance de la base de données d’enregistrement des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="25ff7-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="25ff7-124">Une instance de la base de données de qualité de l’expérience.</span><span class="sxs-lookup"><span data-stu-id="25ff7-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="25ff7-125">Une instance de la base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="25ff7-125">One instance of the archiving database.</span></span>

<span data-ttu-id="25ff7-126">En d’autres termes, vous ne pouvez pas avoir deux instances de la base de données LcsCdr dans la même instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25ff7-126">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="25ff7-127">Si vous avez besoin de plusieurs instances de la base de données LcsCdr, vous devez configurer plusieurs instances de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25ff7-127">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="25ff7-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="25ff7-128">See Also</span></span>


[<span data-ttu-id="25ff7-129">Déploiement de la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25ff7-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

