---
title: Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b167ea64f42510febe0f405d15e2eafab7efc2bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="446d6-102">Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="446d6-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="446d6-103">_**Dernière modification de la rubrique:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="446d6-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="446d6-104">Dans le générateur de topologie, effectuez les étapes suivantes pour configurer une haute disponibilité et une reprise après sinistre pour le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="446d6-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="446d6-105">Ajoutez les bases de données miroir et les magasins de données secondaires SQL Server.</span><span class="sxs-lookup"><span data-stu-id="446d6-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="446d6-106">Modifiez les propriétés du service de chat permanent serveur pour:</span><span class="sxs-lookup"><span data-stu-id="446d6-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="446d6-107">activer la mise en miroir pour la base de données primaire ;</span><span class="sxs-lookup"><span data-stu-id="446d6-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="446d6-108">Ajoutez le magasin SQL Server en miroir principal.</span><span class="sxs-lookup"><span data-stu-id="446d6-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="446d6-109">Activez la base de données d’envoi de journaux de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="446d6-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="446d6-110">Ajoutez la banque SQL Server secondaire pour l’envoi du journal SQL Server.</span><span class="sxs-lookup"><span data-stu-id="446d6-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="446d6-111">Ajoutez le miroir SQL Server Store pour la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="446d6-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="446d6-112">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="446d6-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

