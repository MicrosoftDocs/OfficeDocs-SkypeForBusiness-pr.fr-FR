---
title: Mise à niveau ou mise à jour des serveurs frontaux dans Lync Server 2013
TOCTitle: Mise à niveau ou mise à jour des serveurs frontaux dans Lync Server 2013
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204736(v=OCS.15)
ms:contentKeyID: 49296473
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mise à niveau ou mise à jour des serveurs frontaux dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-06-28_

Les serveurs frontaux d’un pool Enterprise Edition sont organisés en *domaines de mise à niveau*. Il s’agit de sous-ensembles des serveurs frontaux dans le pool. Les domaines de mise à niveau sont créés automatiquement par le Générateur de topologie.

Quand vous effectuez la mise à niveau des serveurs, vous devez procéder un domaine de mise à niveau à la fois. Arrêtez chaque serveur dans un domaine de mise à niveau, effectuez sa mise à niveau, puis redémarrez-le avant de passer au domaine de mise à niveau suivant. Veillez à assurer un suivi des serveurs et domaines de mise à niveau déjà mis à niveau. Utilisez le diagramme de flux suivant dans la cadre de la mise à niveau de chaque serveur.

![Diagramme de mise à niveau de serveur](images/JJ204736.42ed59a4-1c26-49f7-ade4-a5a788457ab9(OCS.15).jpg "Diagramme de mise à niveau de serveur")

## Application d’une mise à niveau aux serveurs frontaux dans un pool

1.  Sur le serveur frontal du pool, exécutez l’applet de commande suivant :
    
    **Get-CsPoolUpgradeReadinessState**
    
    Si *PoolUpgradeState* a la valeur **Busy**, patientez 10 minutes, puis réessayez **Get-CsPoolUpgradeReadinessState**. Si la valeur **Busy** s’affiche au moins à trois reprises consécutives, après une attente de 10 minutes entre chaque tentative, ou si un résultat de type **InsufficientActiveFrontEnds** s’affiche pour **PoolUpgradeState**, il s’agit d’un problème dans le pool. Si ce pool est couplé avec un autre pool frontal dans une topologie de récupération d’urgence, basculez ce pool vers le pool de sauvegarde, puis mettez à jour les serveurs de ce pool. Pour plus d’informations, voir [Basculement vers un pool dans Lync Server 2013](lync-server-2013-failing-over-a-pool.md).
    
    Si la valeur de *PoolUpgradeState* est **Ready**, passez à l’étape 2.

2.  L’applet de commande **Get-CsPoolUpgradeReadinessState** renvoie également des informations sur chaque domaine de mise à niveau dans le pool, et indique quels serveurs frontaux se trouvent dans chaque domaine de mise à niveau. Si **ReadyforUpgrade** a la valeur **True** pour le domaine de mise à niveau contenant le ou les serveurs que vous voulez mettre à niveau, vous pouvez à présent effectuer la mise à niveau de ces serveurs en toute sécurité. Pour ce faire, procédez comme suit :
    
    1.  Utilisez l’applet de commande `Stop-CsWindowsService -Graceful -Verbose` pour interrompre les nouvelles connexions aux serveurs frontaux que vous allez mettre à niveau.
        
        > [!NOTE]  
        > Si vous effectuez ces opérations pendant un temps d’arrêt programmé des serveurs, vous pouvez exécuter cette applet de commande sans le paramètre « -<strong>Graceful</strong> », comme suit : <strong>Stop-CsWindowsService</strong>. Ceci permet d’arrêter immédiatement les services, sans attendre l’exécution de toutes les demandes de service existantes.    
    2.  Mettez à niveau les serveurs associés à ce domaine de mise à niveau.
    
    3.  Redémarrez les serveurs, puis assurez-vous qu’ils acceptent de nouvelles connexions.

3.  Répétez les étapes 1 et 2 pour les autres domaines de mise à niveau individuels dans le pool, jusqu’à ce que l’ensemble des serveurs frontaux aient été mis à niveau.

