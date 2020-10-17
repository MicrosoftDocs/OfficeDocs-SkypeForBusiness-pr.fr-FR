---
title: Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21e240e8fd597f1fe8a2669df45d674be7a7bef1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508651"
---
# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="b74c3-102">Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b74c3-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b74c3-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="b74c3-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="b74c3-104">Dans le générateur de topologie, effectuez les étapes suivantes pour configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b74c3-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="b74c3-105">Ajoutez les bases de données miroir et les magasins SQL Server de base de données secondaire pour l’envoi de journaux.</span><span class="sxs-lookup"><span data-stu-id="b74c3-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="b74c3-106">Modifiez les propriétés du service serveur de conversation permanente comme suit :</span><span class="sxs-lookup"><span data-stu-id="b74c3-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="b74c3-107">activer la mise en miroir pour la base de données primaire ;</span><span class="sxs-lookup"><span data-stu-id="b74c3-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="b74c3-108">Ajoutez le magasin SQL Server miroir principal.</span><span class="sxs-lookup"><span data-stu-id="b74c3-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="b74c3-109">Activez la base de données de copie des journaux SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b74c3-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="b74c3-110">Ajoutez le magasin SQL Server secondaire de copie des journaux de transaction SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b74c3-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="b74c3-111">Ajoutez le miroir du magasin SQL Server pour la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="b74c3-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="b74c3-112">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="b74c3-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

