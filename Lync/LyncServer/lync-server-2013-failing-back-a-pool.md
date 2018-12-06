---
title: 'Lync Server 2013 : Basculement vers un pool'
TOCTitle: Basculement vers un pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204945(v=OCS.15)
ms:contentKeyID: 49297398
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Basculement vers un pool dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Une fois que le pool ayant subi une défaillance est à nouveau en ligne (Pool1 dans cet exemple), procédez comme suit pour rétablir votre déploiement à un état de fonctionnement normal.

Notez que le processus de restauration nécessite plusieurs minutes. Pour référence, il peut prendre jusqu’à 60 minutes pour un pool de 20 000 utilisateurs.

1.  Restaurez les utilisateurs qui étaient initialement hébergés dans Pool1 et qui ont été basculés vers Pool2 en tapant l’applet de commande suivante :
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Aucune autre étape n’est nécessaire. Si vous avez effectué le basculement vers le serveur de gestion centralisée, vous pouvez le laisser dans Pool2.

