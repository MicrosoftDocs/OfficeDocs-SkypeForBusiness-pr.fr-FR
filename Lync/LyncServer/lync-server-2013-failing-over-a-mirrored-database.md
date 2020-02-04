---
title: 'Lync Server 2013 : Basculement vers une base de données en miroir'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 822a7a2fa13ce444bbaf590ee0d8ba2144debcc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="78c50-102">Basculement vers une base de données en miroir dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78c50-102">Failing over a mirrored database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78c50-103">_**Dernière modification de la rubrique :** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="78c50-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="78c50-104">Si vous avez configuré votre base de données principale pour utiliser la mise en miroir synchronisée avec un témoin, le basculement est automatique.</span><span class="sxs-lookup"><span data-stu-id="78c50-104">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span> <span data-ttu-id="78c50-105">Si vous avez configuré la mise en miroir synchronisée sans témoin, vous pouvez utiliser les procédures suivantes pour basculer et restaurer votre base de données.</span><span class="sxs-lookup"><span data-stu-id="78c50-105">If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database.</span></span> <span data-ttu-id="78c50-106">Vous pouvez également utiliser ces procédures pour basculer manuellement et restaurer des bases de données, même si vous avez configuré un témoin.</span><span class="sxs-lookup"><span data-stu-id="78c50-106">You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="78c50-107">Pour basculer votre base de données principale</span><span class="sxs-lookup"><span data-stu-id="78c50-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="78c50-108">Avant de basculer, déterminez quelle est la base de données principale qui est le principal et qui est le miroir en tapant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="78c50-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="78c50-109">Si le magasin central de gestion est hébergé dans ce pool, tapez l’applet de commande suivante pour identifier le principal et le miroir du magasin central de gestion :</span><span class="sxs-lookup"><span data-stu-id="78c50-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="78c50-110">Effectuez le basculement de la base de données utilisateur :</span><span class="sxs-lookup"><span data-stu-id="78c50-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="78c50-111">Si le problème principal est en échec et que vous ne parvient pas à mettre en miroir, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="78c50-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="78c50-112">Si le miroir a échoué et que vous basculez sur le disque principal, tapez :</span><span class="sxs-lookup"><span data-stu-id="78c50-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="78c50-113">Si ce n’est pas le cas, effectuez le basculement du magasin de gestion central.</span><span class="sxs-lookup"><span data-stu-id="78c50-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="78c50-114">Si le problème principal est en échec et que vous ne parvient pas à mettre en miroir, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="78c50-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="78c50-115">Si le miroir a échoué et que vous basculez sur le disque principal, tapez :</span><span class="sxs-lookup"><span data-stu-id="78c50-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

