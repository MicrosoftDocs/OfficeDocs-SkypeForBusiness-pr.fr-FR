---
title: 'Lync Server 2013 : basculement vers une base de données mise en miroir'
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
ms.openlocfilehash: a5be1bfa3a2c9cfac24529de65d91d7b58f13842
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="c5899-102">Basculement vers une base de données mise en miroir dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5899-102">Failing over a mirrored database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5899-103">_**Dernière modification de la rubrique :** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="c5899-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="c5899-p101">Si vous avez configuré votre base de données principale afin d’utiliser une mise en miroir synchronisée avec un témoin, le basculement est automatique. Si vous avez configuré la mise en miroir synchronisée sans témoin, vous pouvez utiliser les procédures suivantes pour effectuer un basculement et une restauration de votre base de données. Vous pouvez également utiliser ces procédures pour effectuer manuellement un basculement et une restauration de vos bases de données même si vous avez configuré un témoin.</span><span class="sxs-lookup"><span data-stu-id="c5899-p101">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic. If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database. You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="c5899-107">Pour effectuer un basculement de votre base de données principale</span><span class="sxs-lookup"><span data-stu-id="c5899-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="c5899-108">Avant le basculement, déterminez quelle base de données principale est le principal et laquelle est le miroir en tapant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c5899-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="c5899-109">Si le magasin central de gestion est hébergé dans ce pool, tapez l’applet de commande suivante pour déterminer quel est le principal et qui est le miroir pour le magasin central de gestion :</span><span class="sxs-lookup"><span data-stu-id="c5899-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="c5899-110">Effectuez la restauration de la base de données utilisateur :</span><span class="sxs-lookup"><span data-stu-id="c5899-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="c5899-111">En cas de basculement vers le serveur miroir après l’échec du serveur principal, tapez :</span><span class="sxs-lookup"><span data-stu-id="c5899-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="c5899-112">En cas de basculement vers le serveur principal après l’échec du serveur miroir, tapez :</span><span class="sxs-lookup"><span data-stu-id="c5899-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="c5899-113">Si le pool héberge le serveur de gestion centralisée, effectuez le basculement du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="c5899-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="c5899-114">En cas de basculement vers le serveur miroir après l’échec du serveur principal, tapez :</span><span class="sxs-lookup"><span data-stu-id="c5899-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="c5899-115">En cas de basculement vers le serveur principal après l’échec du serveur miroir, tapez :</span><span class="sxs-lookup"><span data-stu-id="c5899-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

