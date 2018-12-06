---
title: Ajout ou suppression d’un serveur frontal dans Lync Server 2013
TOCTitle: Ajout ou suppression d’un serveur frontal dans Lync Server 2013
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205153(v=OCS.15)
ms:contentKeyID: 49298519
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ajout ou suppression d’un serveur frontal dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-01-21_

Lorsque vous ajoutez un serveur frontal à un pool, ou que vous supprimez un serveur frontal d’un pool, vous devez redémarrer le pool. Pour éviter toute interruption de service pour les utilisateurs, utilisez la procédure suivante en cas d’ajout ou de suppression d’un serveur frontal.

## Pour ajouter ou supprimer des serveurs frontaux

1.  Si vous supprimez des serveurs frontaux, commencez par arrêter les nouvelles connexions à ces serveurs. Pour ce faire, vous pouvez utiliser l’applet de commande suivante :
    
        Stop -CsWindowsServices -Graceful

2.  Lorsque les serveurs supprimés n’ont pas de sessions actives, arrêtez les services Lync Server sur ces serveurs.

3.  Ouvrez le Générateur de topologie, puis ajoutez ou supprimez les serveurs nécessaires.

4.  Publiez la topologie.

5.  Si le pool est passé de deux serveurs frontaux à plus de deux , ou s’il est passé de plus de deux servers à exactement deux serveurs, vous devez taper l’applet de commande suivante :
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Si le pool comprend trois serveurs ou plus, au moins trois de ces serveurs doivent être en cours d’exécution lorsque vous tapez cette applet de commande.

6.  Redémarrez tous les serveurs frontaux du pool, l’un après l’autre.

