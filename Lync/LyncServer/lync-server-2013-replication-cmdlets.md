---
title: 'Lync Server 2013 : cmdlets de réplication'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replication cmdlets
ms:assetid: e0c49601-d2a3-45a1-b05c-26c7ff820708
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415677(v=OCS.15)
ms:contentKeyID: 48185527
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25a9de5a754545aa49c4a7d9dda6b8378f448eab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replication-cmdlets-in-lync-server-2013"></a><span data-ttu-id="544a3-102">Cmdlets de réplication dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="544a3-102">Replication cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="544a3-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="544a3-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="544a3-104">Les cmdlets de réplication vous permettent de surveiller et de gérer la réplication Lync Server.</span><span class="sxs-lookup"><span data-stu-id="544a3-104">The replication cmdlets provide a way for you to both monitor and manage Lync Server replication.</span></span> <span data-ttu-id="544a3-105">Vous pouvez utiliser ces applets de commande pour configurer les paramètres de réplication, pour surveiller la progression de la réplication et pour forcer manuellement la réplication sur un serveur.</span><span class="sxs-lookup"><span data-stu-id="544a3-105">You can use these cmdlets to configure replication settings; to monitor replication progress; and to manually force replication on a server.</span></span>

<div>

## <a name="replication-cmdlets"></a><span data-ttu-id="544a3-106">Applets de commande de réplication</span><span class="sxs-lookup"><span data-stu-id="544a3-106">Replication Cmdlets</span></span>

<span data-ttu-id="544a3-107">La liste suivante indique les applets de commande qui sont directement associées à la gestion de la réplication :</span><span class="sxs-lookup"><span data-stu-id="544a3-107">The following is a list of cmdlets that relate directly to managing replication:</span></span>

<span data-ttu-id="544a3-108">**Réplication**</span><span class="sxs-lookup"><span data-stu-id="544a3-108">**Replication**</span></span>

  - <span></span>  
    <span data-ttu-id="544a3-109">[Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="544a3-109">[Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="544a3-110">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="544a3-110">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="544a3-111">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="544a3-111">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="544a3-112">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="544a3-112">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="544a3-113">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="544a3-113">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="544a3-114">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="544a3-114">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="544a3-115">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="544a3-115">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="544a3-116">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="544a3-116">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="544a3-117">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="544a3-117">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="544a3-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="544a3-118">See Also</span></span>


[<span data-ttu-id="544a3-119">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="544a3-119">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

