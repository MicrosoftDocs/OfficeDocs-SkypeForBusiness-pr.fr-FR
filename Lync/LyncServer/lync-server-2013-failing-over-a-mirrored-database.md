---
title: 'Lync Server 2013 : Basculement vers une base de données en miroir'
TOCTitle: Basculement vers une base de données en miroir
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204991(v=OCS.15)
ms:contentKeyID: 49297641
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Basculement vers une base de données en miroir dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-03-14_

Si vous avez configuré votre base de données principale afin d’utiliser une mise en miroir synchronisée avec un témoin, le basculement est automatique. Si vous avez configuré la mise en miroir synchronisée sans témoin, vous pouvez utiliser les procédures suivantes pour effectuer un basculement et une restauration de votre base de données. Vous pouvez également utiliser ces procédures pour effectuer manuellement un basculement et une restauration de vos bases de données même si vous avez configuré un témoin.

## Pour effectuer un basculement de votre base de données principale

1.  Avant le basculement, déterminez quelle base de données principale est le principal et laquelle est le miroir en tapant l’applet de commande suivante :
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Si le magasin central de gestion est hébergé dans ce pool, tapez l’applet de commande suivante pour déterminer le principal et le miroir du magasin central de gestion :
    
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

