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
ms.openlocfilehash: 24aa85ea7dfdd76b20af30954ea2480fba2f21f5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Basculement vers une base de données mise en miroir dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-03-14_

Si vous avez configuré votre base de données principale afin d’utiliser une mise en miroir synchronisée avec un témoin, le basculement est automatique. Si vous avez configuré la mise en miroir synchronisée sans témoin, vous pouvez utiliser les procédures suivantes pour effectuer un basculement et une restauration de votre base de données. Vous pouvez également utiliser ces procédures pour effectuer manuellement un basculement et une restauration de vos bases de données même si vous avez configuré un témoin.

<div>

## <a name="to-fail-over-your-back-end-database"></a>Pour effectuer un basculement de votre base de données principale

1.  Avant le basculement, déterminez quelle base de données principale est le principal et laquelle est le miroir en tapant l’applet de commande suivante :
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Si le magasin central de gestion est hébergé dans ce pool, tapez l’applet de commande suivante pour déterminer quel est le principal et qui est le miroir pour le magasin central de gestion :
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  Effectuez la restauration de la base de données utilisateur :
    
      - En cas de basculement vers le serveur miroir après l’échec du serveur principal, tapez :
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - En cas de basculement vers le serveur principal après l’échec du serveur miroir, tapez :
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  Si le pool héberge le serveur de gestion centralisée, effectuez le basculement du magasin central de gestion.
    
      - En cas de basculement vers le serveur miroir après l’échec du serveur principal, tapez :
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - En cas de basculement vers le serveur principal après l’échec du serveur miroir, tapez :
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

