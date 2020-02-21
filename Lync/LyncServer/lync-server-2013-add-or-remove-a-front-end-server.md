---
title: 'Lync Server 2013 : ajout ou suppression d’un serveur frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e358415b086594b67fabdc5ed74706a510e2f82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="a75a6-102">Ajouter ou supprimer un serveur frontal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a75a6-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a75a6-103">_**Dernière modification de la rubrique :** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="a75a6-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="a75a6-p101">Lorsque vous ajoutez un serveur frontal à un pool, ou que vous supprimez un serveur frontal d’un pool, vous devez redémarrer le pool. Pour éviter toute interruption de service pour les utilisateurs, utilisez la procédure suivante en cas d’ajout ou de suppression d’un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a75a6-p101">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool. To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a75a6-106">Si vous ajoutez de nouveaux serveurs au pool, mettez à jour vos nouveaux serveurs de pool de sorte qu’ils se trouvent au même niveau de mise à jour cumulative que les serveurs existants dans le pool.</span><span class="sxs-lookup"><span data-stu-id="a75a6-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="a75a6-107">Pour ajouter ou supprimer des serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="a75a6-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="a75a6-p102">Si vous supprimez des serveurs frontaux, commencez par arrêter les nouvelles connexions à ces serveurs. Pour ce faire, vous pouvez utiliser l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a75a6-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="a75a6-110">Lorsque les serveurs supprimés n’ont pas de sessions actives, arrêtez les services Lync Server sur ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="a75a6-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="a75a6-111">Ouvrez le Générateur de topologie, puis ajoutez ou supprimez les serveurs nécessaires.</span><span class="sxs-lookup"><span data-stu-id="a75a6-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="a75a6-112">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="a75a6-112">Publish the topology.</span></span>

5.  <span data-ttu-id="a75a6-113">Si le pool est passé de deux serveurs frontaux à plus de deux ou de plus de deux serveurs à exactement deux, vous devez taper l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a75a6-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="a75a6-114">Si le pool comprend trois serveurs ou plus, au moins trois de ces serveurs doivent être en cours d’exécution lorsque vous tapez cette applet de commande.</span><span class="sxs-lookup"><span data-stu-id="a75a6-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="a75a6-115">Redémarrez tous les serveurs frontaux du pool, un par un.</span><span class="sxs-lookup"><span data-stu-id="a75a6-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

