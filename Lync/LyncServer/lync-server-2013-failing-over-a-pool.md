---
title: 'Lync Server 2013 : basculement d’un pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5771d21479cf4dd63a3fa1e1e141b566fdbe6899
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="f3280-102">Basculement d’un pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3280-102">Failing over a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3280-103">_**Dernière modification de la rubrique :** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="f3280-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="f3280-p101">Si un seul pool frontal a échoué et doit être basculé, utilisez la procédure ci-après. Dans cette procédure, Datacenter1 contient Pool1 et Pool1 a échoué. Vous effectuez le basculement vers Pool2 qui se trouve dans Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="f3280-p101">If a single Front End pool has failed and needs to be failed over, use the following procedure. In this procedure, Datacenter1 contains Pool1, and Pool1 has failed. You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="f3280-107">La plupart du travail pour le basculement de pool implique le basculement du magasin central de gestion, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f3280-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="f3280-108">Ceci est important, car le magasin central de gestion doit être fonctionnel lorsque les utilisateurs du pool ont basculé.</span><span class="sxs-lookup"><span data-stu-id="f3280-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="f3280-p103">En outre, si un pool frontal échoue mais que le pool de serveurs Edge sur ce site est toujours en cours d’exécution, vous devez savoir si le pool de serveurs Edge utilise le pool qui a échoué comme pool du tronçon suivant. Si tel est le cas, vous devez modifier le pool de serveurs Edge de manière à utiliser un pool frontal différent avant de faire basculer le pool frontal qui a connu un échec. La manière dont vous pouvez modifier le paramètre du tronçon suivant varie selon que le serveur Edge va utiliser un pool sur le même site comme pool de serveurs Edge ou sur un site différent.</span><span class="sxs-lookup"><span data-stu-id="f3280-p103">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="f3280-112">**Pour configurer un pool de serveurs Edge de manière à utiliser un pool du tronçon suivant sur le même site**</span><span class="sxs-lookup"><span data-stu-id="f3280-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="f3280-113">Ouvrez le générateur de topologies, cliquez avec le bouton droit sur le pool de serveurs Edge à modifier, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f3280-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f3280-p104">Cliquez sur **Tronçon suivant**. Dans la liste **Pool du tronçon suivant :**, sélectionnez le pool qui servira désormais de pool du tronçon suivant.</span><span class="sxs-lookup"><span data-stu-id="f3280-p104">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="f3280-116">Cliquez sur **OK**, puis publiez les modifications.</span><span class="sxs-lookup"><span data-stu-id="f3280-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="f3280-117">**Pour configurer un pool de serveurs Edge de manière à utiliser un pool du tronçon suivant sur un site différent**</span><span class="sxs-lookup"><span data-stu-id="f3280-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="f3280-118">Ouvrez une fenêtre Lync Server Management Shell et tapez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f3280-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="f3280-119">**Pour faire basculer un pool en cas d’urgence**</span><span class="sxs-lookup"><span data-stu-id="f3280-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="f3280-120">Recherchez le pool qui héberge le serveur de gestion centralisée en tapant l’applet de commande suivante sur un serveur frontal dans Pool2 :</span><span class="sxs-lookup"><span data-stu-id="f3280-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="f3280-121">Les résultats de cette cmdlet indiquent le pool qui héberge actuellement le serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="f3280-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="f3280-122">Dans le reste de cette procédure, ce pool est appelé pool CMS\_.</span><span class="sxs-lookup"><span data-stu-id="f3280-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="f3280-123">Utilisez le générateur de topologies pour rechercher la version de Lync Server exécutée\_sur le pool CMS.</span><span class="sxs-lookup"><span data-stu-id="f3280-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="f3280-124">S’il exécute Lync Server 2013, utilisez l’applet de commande suivante pour rechercher le pool de sauvegarde du pool 1.</span><span class="sxs-lookup"><span data-stu-id="f3280-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="f3280-125">Laissez le\_pool de sauvegardes être le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f3280-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="f3280-126">Vérifiez l’état du magasin central de gestion à l’aide de l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f3280-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="f3280-127">Cette applet de commande doit indiquer que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de\_domaine complet du pool CMS.</span><span class="sxs-lookup"><span data-stu-id="f3280-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="f3280-128">S’ils sont vides, le serveur de gestion centralisée n’est pas disponible et vous devez le faire basculer.</span><span class="sxs-lookup"><span data-stu-id="f3280-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="f3280-129">Si le magasin central de gestion n’est pas disponible ou si le magasin central de gestion était en cours d’exécution sur Pool1 (autrement dit, sur le pool ayant échoué), vous devez basculer le serveur de gestion centralisée avant de basculer sur le pool.</span><span class="sxs-lookup"><span data-stu-id="f3280-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="f3280-130">Si vous avez besoin de basculer le serveur de gestion centralisée hébergé sur un pool exécutant Lync Server 2013, utilisez l’applet de commande à l’étape 5 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="f3280-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="f3280-131">Si vous avez besoin de basculer le serveur de gestion centralisée hébergé sur un pool exécutant Lync Server 2010, utilisez l’applet de commande à l’étape 6 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="f3280-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="f3280-132">Si vous n’avez pas besoin de basculer le serveur de gestion centralisée, passez à l’étape 7 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="f3280-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="f3280-133">Pour faire basculer le magasin central de gestion sur un pool exécutant Lync Server 2013, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f3280-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="f3280-134">Tout d’abord, vérifiez le serveur principal dans\_le pool de sauvegarde qui exécute l’instance principale du magasin central de gestion en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f3280-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="f3280-135">Si le principal serveur principal dans le pool\_de sauvegarde est le principal, tapez :</span><span class="sxs-lookup"><span data-stu-id="f3280-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="f3280-136">Si le serveur principal miroir dans le pool\_de sauvegarde est le principal, tapez :</span><span class="sxs-lookup"><span data-stu-id="f3280-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="f3280-137">Vérifiez que le basculement du serveur de gestion centralisée est terminé.</span><span class="sxs-lookup"><span data-stu-id="f3280-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="f3280-138">Tapez ensuite :</span><span class="sxs-lookup"><span data-stu-id="f3280-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="f3280-139">Vérifiez que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de domaine complet\_du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f3280-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="f3280-140">Enfin, vérifiez l’état du réplica de tous les serveurs frontaux en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f3280-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="f3280-141">Assurez-vous que tous les réplicas sont définis sur True.</span><span class="sxs-lookup"><span data-stu-id="f3280-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="f3280-142">Passez à l’étape 7 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="f3280-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="f3280-143">Installez le magasin central de gestion sur le serveur principal du pool\_de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f3280-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="f3280-144">Exécutez d’abord cette commande :</span><span class="sxs-lookup"><span data-stu-id="f3280-144">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="f3280-145">Exécutez la commande suivante sur l’un des serveurs frontaux du pool\_de sauvegarde pour forcer le déplacement du magasin central de gestion :</span><span class="sxs-lookup"><span data-stu-id="f3280-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="f3280-146">Vérifiez que le déplacement est terminé :</span><span class="sxs-lookup"><span data-stu-id="f3280-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="f3280-147">Vérifiez que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de domaine complet\_du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f3280-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="f3280-148">Vérifiez le statut des réplicas de tous les serveurs frontaux en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f3280-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="f3280-149">Assurez-vous que tous les réplicas sont définis sur True.</span><span class="sxs-lookup"><span data-stu-id="f3280-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="f3280-150">Installez le service de gestion centralisée sur le reste des serveurs frontaux dans le\_pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f3280-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="f3280-151">Pour ce faire, exécutez la commande suivante sur tous les serveurs frontaux, à l’exception de celle que vous avez utilisée lors de l’activation forcée du déplacement du magasin central de gestion plus haut dans cette procédure :</span><span class="sxs-lookup"><span data-stu-id="f3280-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="f3280-152">Basculez les utilisateurs de Pool1 vers Pool2 en exécutant l’applet de commande suivante dans une fenêtre Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="f3280-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="f3280-153">Étant donné que les étapes décrites dans les parties précédentes de cette procédure pour vérifier que l’état du magasin central de gestion ne sont pas universelles, il est possible que cette cmdlet échoue car le magasin central de gestion n’est pas encore totalement basculé.</span><span class="sxs-lookup"><span data-stu-id="f3280-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="f3280-154">Dans ce cas, vous devez corriger le magasin central de gestion en fonction des messages d’erreur qui s’affichent, puis réexécuter cette applet de commande.</span><span class="sxs-lookup"><span data-stu-id="f3280-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="f3280-p112">Si le message d’erreur suivant apparaît, vous devez modifier le pool de serveurs Edge sur ce site afin d’utiliser un pool différent comme tronçon suivant avant de faire basculer le pool. Pour plus d’informations, voir les procédures indiquées au début de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="f3280-p112">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

