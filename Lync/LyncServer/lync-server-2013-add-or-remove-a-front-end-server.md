---
title: 'Lync Server 2013: ajout ou suppression d’un serveur frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fe1e81d3983b89d4f68111179c3adc7409bee2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="100fd-102">Add or remove a Front End Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="100fd-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="100fd-103">_**Dernière modification de la rubrique:** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="100fd-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="100fd-104">Lorsque vous ajoutez un serveur frontal à un pool, ou supprimez un serveur frontal d’un pool, vous devez redémarrer le pool.</span><span class="sxs-lookup"><span data-stu-id="100fd-104">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> <span data-ttu-id="100fd-105">Pour éviter toute interruption de service aux utilisateurs, utilisez la procédure suivante lors de l’ajout ou de la suppression d’un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="100fd-105">To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="100fd-106">Si vous ajoutez des serveurs au pool, mettez à jour vos nouveaux serveurs du pool pour qu’ils se trouvent au même niveau de mise à jour cumulée que les serveurs existants du pool.</span><span class="sxs-lookup"><span data-stu-id="100fd-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="100fd-107">Pour ajouter ou supprimer des serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="100fd-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="100fd-108">Si vous supprimez un serveur frontal, vous devez d’abord arrêter de nouvelles connexions sur ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="100fd-108">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="100fd-109">Pour ce faire, vous pouvez utiliser l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="100fd-109">To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="100fd-110">Lorsque les serveurs en cours de suppression ne disposent pas de sessions actives, arrêtez les services Lync Server.</span><span class="sxs-lookup"><span data-stu-id="100fd-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="100fd-111">Ouvrez le générateur de topologie et ajoutez ou supprimez les serveurs nécessaires.</span><span class="sxs-lookup"><span data-stu-id="100fd-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="100fd-112">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="100fd-112">Publish the topology.</span></span>

5.  <span data-ttu-id="100fd-113">Si le nombre d’éléments de la liste est supérieur à deux ou qu’il n’a pas encore plus de deux serveurs, vous devez taper l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="100fd-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="100fd-114">Si le pool comporte au moins trois serveurs, trois de ces serveurs doivent être en cours d’exécution lorsque vous tapez cette cmdlet.</span><span class="sxs-lookup"><span data-stu-id="100fd-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="100fd-115">Redémarrez tous les serveurs frontaux de la liste, un par un.</span><span class="sxs-lookup"><span data-stu-id="100fd-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

