---
title: 'Lync Server 2013: cmdlets de réplication'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Replication cmdlets
ms:assetid: e0c49601-d2a3-45a1-b05c-26c7ff820708
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415677(v=OCS.15)
ms:contentKeyID: 48185527
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46652100e421fba8935454f2832e258a9fb2203f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replication-cmdlets-in-lync-server-2013"></a><span data-ttu-id="8dbb6-102">Cmdlets de réplication dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dbb6-102">Replication cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dbb6-103">_**Dernière modification de la rubrique:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="8dbb6-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="8dbb6-104">Les applets de contrôle de réplication vous permettent de surveiller et de gérer la réplication de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8dbb6-104">The replication cmdlets provide a way for you to both monitor and manage Lync Server replication.</span></span> <span data-ttu-id="8dbb6-105">Vous pouvez utiliser ces applets de applet pour configurer les paramètres de réplication. pour surveiller la progression de la réplication; pour forcer manuellement la réplication sur un serveur.</span><span class="sxs-lookup"><span data-stu-id="8dbb6-105">You can use these cmdlets to configure replication settings; to monitor replication progress; and to manually force replication on a server.</span></span>

<div>

## <a name="replication-cmdlets"></a><span data-ttu-id="8dbb6-106">Cmdlets de réplication</span><span class="sxs-lookup"><span data-stu-id="8dbb6-106">Replication Cmdlets</span></span>

<span data-ttu-id="8dbb6-107">Voici une liste des applets de commande qui concernent directement la gestion de la réplication:</span><span class="sxs-lookup"><span data-stu-id="8dbb6-107">The following is a list of cmdlets that relate directly to managing replication:</span></span>

<span data-ttu-id="8dbb6-108">**Duplication**</span><span class="sxs-lookup"><span data-stu-id="8dbb6-108">**Replication**</span></span>

  - <span></span>  
    <span data-ttu-id="8dbb6-109">[Debug-CsInterPoolReplication](https://technet.microsoft.com/en-us/library/JJ619185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8dbb6-109">[Debug-CsInterPoolReplication](https://technet.microsoft.com/en-us/library/JJ619185(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8dbb6-110">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/en-us/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8dbb6-110">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/en-us/library/Gg413060(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8dbb6-111">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/en-us/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8dbb6-111">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/en-us/library/Gg399052(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8dbb6-112">[Enable-CsReplica](https://technet.microsoft.com/en-us/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8dbb6-112">[Enable-CsReplica](https://technet.microsoft.com/en-us/library/Gg425965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8dbb6-113">[Test-CsReplica](https://technet.microsoft.com/en-us/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8dbb6-113">[Test-CsReplica](https://technet.microsoft.com/en-us/library/JJ205289(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8dbb6-114">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8dbb6-114">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398548(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8dbb6-115">[Nouveau-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8dbb6-115">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg399059(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8dbb6-116">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8dbb6-116">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg425738(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8dbb6-117">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8dbb6-117">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398540(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8dbb6-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8dbb6-118">See Also</span></span>


[<span data-ttu-id="8dbb6-119">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="8dbb6-119">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

