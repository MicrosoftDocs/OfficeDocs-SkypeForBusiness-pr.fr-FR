---
title: 'Lync Server 2013 : Basculement vers une base de données en miroir'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a943705f13cff4f015285b1ef74feb11dc540091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Basculement vers une base de données en miroir dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-03-14_

Si vous avez configuré votre base de données principale pour utiliser la mise en miroir synchronisée avec un témoin, le basculement est automatique. Si vous avez configuré la mise en miroir synchronisée sans témoin, vous pouvez utiliser les procédures suivantes pour basculer et restaurer votre base de données. Vous pouvez également utiliser ces procédures pour basculer manuellement et restaurer des bases de données, même si vous avez configuré un témoin.

<div>

## <a name="to-fail-over-your-back-end-database"></a>Pour basculer votre base de données principale

1.  Avant de basculer, déterminez quelle est la base de données principale qui est le principal et qui est le miroir en tapant l’applet de commande suivante:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Si le magasin central de gestion est hébergé dans ce pool, tapez l’applet de commande suivante pour identifier le principal et le miroir du magasin central de gestion:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  Effectuez le basculement de la base de données utilisateur:
    
      - Si le problème principal est en échec et que vous ne parvient pas à mettre en miroir, tapez ce qui suit:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - Si le miroir a échoué et que vous basculez sur le disque principal, tapez:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  Si ce n’est pas le cas, effectuez le basculement du magasin de gestion central.
    
      - Si le problème principal est en échec et que vous ne parvient pas à mettre en miroir, tapez ce qui suit:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - Si le miroir a échoué et que vous basculez sur le disque principal, tapez:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

