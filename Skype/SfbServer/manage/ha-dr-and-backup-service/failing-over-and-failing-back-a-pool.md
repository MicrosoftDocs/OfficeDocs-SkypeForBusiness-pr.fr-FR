---
title: Basculement ou restauration d’un pool
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: 1ebd4e8110b8783c869530d95eda0646a895b88e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826564"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="20365-103">Faire échouer et faire échouer un pool dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="20365-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="20365-104">Utilisez les procédures suivantes si un seul pool frontal a échoué et doit être retenté, ou si le pool qui a connu l’urgence est de nouveau en ligne et que vous devez rétablir l’état de travail normal de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="20365-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="20365-105">Découvrez également comment faire échouer et faire échouer le pool Edge utilisé pour la fédération Skype Entreprise ou XMPP, ou comment modifier le pool edge associé à un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="20365-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="20365-106">Faire échouer un pool frontal</span><span class="sxs-lookup"><span data-stu-id="20365-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="20365-107">Faire échouer un pool</span><span class="sxs-lookup"><span data-stu-id="20365-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="20365-108">Faire échouer le pool edge utilisé pour la fédération Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="20365-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="20365-109">Faire échouer le pool edge utilisé pour la fédération XMPP dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="20365-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="20365-110">Faire échouer le pool edge utilisé pour la fédération Skype Entreprise Server ou XMPP</span><span class="sxs-lookup"><span data-stu-id="20365-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="20365-111">Modifier le pool edge associé à un pool frontal</span><span class="sxs-lookup"><span data-stu-id="20365-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="20365-112">Faire échouer un pool frontal</span><span class="sxs-lookup"><span data-stu-id="20365-112">Fail over a Front End pool</span></span>

<span data-ttu-id="20365-113">Dans cette procédure, Datacenter1 contient Pool1 et Pool1 a échoué.</span><span class="sxs-lookup"><span data-stu-id="20365-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="20365-114">Vous effectuez le basculement vers Pool2 qui se trouve dans Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="20365-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="20365-115">La majeure partie du travail pour le changement de pool implique le fait de faire échouer le magasin central de gestion, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="20365-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="20365-116">Ceci est important, car le magasin central de gestion doit être fonctionnel lorsque les utilisateurs du pool sont retentés.</span><span class="sxs-lookup"><span data-stu-id="20365-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="20365-p104">En outre, si un pool frontal échoue mais que le pool de serveurs Edge sur ce site est toujours en cours d’exécution, vous devez savoir si le pool de serveurs Edge utilise le pool qui a échoué comme pool du tronçon suivant. Si tel est le cas, vous devez modifier le pool de serveurs Edge de manière à utiliser un pool frontal différent avant de faire basculer le pool frontal qui a connu un échec. La manière dont vous pouvez modifier le paramètre du tronçon suivant varie selon que le serveur Edge va utiliser un pool sur le même site comme pool de serveurs Edge ou sur un site différent.</span><span class="sxs-lookup"><span data-stu-id="20365-p104">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="20365-120">**Pour définir un pool edge pour utiliser un pool de saut suivant sur le même site**</span><span class="sxs-lookup"><span data-stu-id="20365-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="20365-121">Ouvrez le Générateur de topologie, cliquez avec le bouton droit sur le pool edge qui doit être modifié, puis cliquez sur **Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="20365-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="20365-p105">Cliquez sur **Tronçon suivant**. Dans la liste **Pool du tronçon suivant :**, sélectionnez le pool qui servira désormais de pool du tronçon suivant.</span><span class="sxs-lookup"><span data-stu-id="20365-p105">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="20365-124">Cliquez sur **OK**, puis publiez les modifications.</span><span class="sxs-lookup"><span data-stu-id="20365-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="20365-125">**Pour définir un pool edge pour utiliser un pool de saut suivant sur un autre site**</span><span class="sxs-lookup"><span data-stu-id="20365-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="20365-126">Ouvrez une fenêtre Skype Entreprise Server Management Shell et tapez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="20365-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="20365-127">**Pour faire échouer un pool en cas d’urgence**</span><span class="sxs-lookup"><span data-stu-id="20365-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="20365-128">Recherchez quel pool est l’hôte du serveur central de gestion en tapant l’cmdlet suivante sur un serveur frontal dans Pool2 :</span><span class="sxs-lookup"><span data-stu-id="20365-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="20365-129">Les résultats de cette cmdlet indiquent quel pool héberge actuellement le serveur central de gestion.</span><span class="sxs-lookup"><span data-stu-id="20365-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="20365-130">Dans le reste de cette procédure, ce pool est appelé pool \_ CMS.</span><span class="sxs-lookup"><span data-stu-id="20365-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="20365-131">Utilisez le Générateur de topologie pour trouver la version de Skype Entreprise Server qui s’exécute sur le \_ pool CMS.</span><span class="sxs-lookup"><span data-stu-id="20365-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="20365-132">S’il exécute Skype Entreprise Server, utilisez l’cmdlet suivante pour trouver le pool de sauvegarde du pool 1.</span><span class="sxs-lookup"><span data-stu-id="20365-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="20365-133">Que le \_ pool de sauvegarde soit le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="20365-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="20365-134">Vérifiez l’état du magasin central de gestion avec l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="20365-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="20365-135">Cette cmdlet doit montrer que activeMasterFQDN et ActiveFileTransferAgents pointent vers le FQDN du \_ pool CMS.</span><span class="sxs-lookup"><span data-stu-id="20365-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="20365-136">S’ils sont vides, le serveur central de gestion n’est pas disponible et vous devez le faire échouer.</span><span class="sxs-lookup"><span data-stu-id="20365-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="20365-137">Si le magasin central de gestion n’est pas disponible ou si le magasin central de gestion était en cours d’exécution sur Pool1 (autrement dit, le pool qui a échoué), vous devez faire échouer le serveur central de gestion avant de faire échouer le pool.</span><span class="sxs-lookup"><span data-stu-id="20365-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="20365-138">Si vous devez faire échouer le serveur central de gestion hébergé sur un pool exécutant Skype Entreprise Server, utilisez la cmdlet à l’étape 5 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="20365-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="20365-139">Si vous n’avez pas besoin de faire échouer le serveur central de gestion, passez à l’étape 7 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="20365-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="20365-140">Pour faire échouer le magasin central de gestion sur un pool exécutant Skype Entreprise Server, exécutez la fonction suivante :</span><span class="sxs-lookup"><span data-stu-id="20365-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="20365-141">Tout d’abord, vérifiez quel serveur principal du pool de sauvegarde exécute l’instance principale du magasin central de gestion \_ en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="20365-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="20365-142">Si le serveur principal principal dans le pool de \_ sauvegarde est le principal, tapez :</span><span class="sxs-lookup"><span data-stu-id="20365-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="20365-143">Si le serveur principal miroir dans le pool de \_ sauvegarde est le principal, tapez :</span><span class="sxs-lookup"><span data-stu-id="20365-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="20365-144">Vérifier que le serveur central de gestion est terminé.</span><span class="sxs-lookup"><span data-stu-id="20365-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="20365-145">Tapez ensuite :</span><span class="sxs-lookup"><span data-stu-id="20365-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="20365-146">Vérifiez que activeMasterFQDN et ActiveFileTransferAgents pointent vers le FQDN du pool de \_ sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="20365-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="20365-147">Enfin, vérifiez l’état du réplica pour tous les serveurs frontux en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="20365-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="20365-148">Assurez-vous que tous les réplicas sont définis sur True.</span><span class="sxs-lookup"><span data-stu-id="20365-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="20365-149">Passez à l’étape 7 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="20365-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="20365-150">Installez le magasin central de gestion sur le serveur principal du pool de \_ sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="20365-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="20365-151">Exécutez d’abord cette commande :</span><span class="sxs-lookup"><span data-stu-id="20365-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="20365-152">Exécutez la commande suivante sur l’un des serveurs frontux du pool de sauvegarde pour forcer le déplacement du \_ magasin central de gestion :</span><span class="sxs-lookup"><span data-stu-id="20365-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="20365-153">Vérifiez que le déplacement est terminé :</span><span class="sxs-lookup"><span data-stu-id="20365-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="20365-154">Vérifiez que activeMasterFQDN et ActiveFileTransferAgents pointent vers le FQDN du pool de \_ sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="20365-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="20365-155">Vérifiez le statut des réplicas de tous les serveurs frontaux en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="20365-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="20365-156">Assurez-vous que tous les réplicas sont définis sur True.</span><span class="sxs-lookup"><span data-stu-id="20365-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="20365-157">Installez le service Serveur central de gestion sur le reste des serveurs frontux du pool de \_ sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="20365-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="20365-158">Pour ce faire, exécutez la commande suivante sur tous les serveurs frontux, à l’exception de celle que vous avez utilisée pour forcer le déplacement du magasin central de gestion précédemment dans cette procédure :</span><span class="sxs-lookup"><span data-stu-id="20365-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="20365-159">Pour faire échouer les utilisateurs de Pool1 à Pool2, exécutez l’cmdlet suivante dans une fenêtre Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="20365-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="20365-160">Étant donné que les étapes des étapes précédentes de cette procédure pour vérifier l’état du magasin central de gestion ne sont pas universelles, il est possible que cette cmdlet échoue, car le magasin central de gestion n’est pas encore entièrement bas de la charge.</span><span class="sxs-lookup"><span data-stu-id="20365-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="20365-161">Dans ce cas, vous devez corriger le magasin central de gestion en fonction des messages d’erreur que vous voyez, puis ré-exécuter cette cmdlet.</span><span class="sxs-lookup"><span data-stu-id="20365-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="20365-p113">Si le message d’erreur suivant apparaît, vous devez modifier le pool de serveurs Edge sur ce site afin d’utiliser un pool différent comme tronçon suivant avant de faire basculer le pool. Pour plus d’informations, voir les procédures indiquées au début de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="20365-p113">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="20365-164">Faire échouer un pool</span><span class="sxs-lookup"><span data-stu-id="20365-164">Fail back a pool</span></span>

<span data-ttu-id="20365-165">Une fois que le pool ayant subi une défaillance est à nouveau en ligne (Pool1 dans cet exemple), procédez comme suit pour rétablir votre déploiement à un état de fonctionnement normal.</span><span class="sxs-lookup"><span data-stu-id="20365-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="20365-166">Notez que le processus de restauration nécessite plusieurs minutes.</span><span class="sxs-lookup"><span data-stu-id="20365-166">Note that the failback process takes several minute to complete.</span></span>  <span data-ttu-id="20365-167">Pour référence, il peut prendre jusqu’à 60 minutes pour un pool de 20 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="20365-167">For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="20365-168">Restaurez les utilisateurs qui étaient initialement hébergés dans Pool1 et qui ont été basculés vers Pool2 en tapant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="20365-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="20365-169">Aucune autre étape n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="20365-169">No other steps are necessary.</span></span> <span data-ttu-id="20365-170">Si vous avez échoué sur le serveur central de gestion, vous pouvez le laisser dans Pool2.</span><span class="sxs-lookup"><span data-stu-id="20365-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="20365-171">Faire échouer le pool edge utilisé pour la fédération Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="20365-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="20365-172">Si le pool Edge sur lequel la fédération Skype Entreprise Server est configurée est en panne, vous devez modifier la fédération pour utiliser un autre pool Edge pour que la fédération fonctionne.</span><span class="sxs-lookup"><span data-stu-id="20365-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="20365-173">Sur le serveur frontal, ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="20365-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="20365-174">Développez les pools de serveurs **Edge,** puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="20365-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="20365-175">Sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="20365-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="20365-176">Dans **Modifier les propriétés**, sous **Général**, désactivez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="20365-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="20365-177">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="20365-177">Click **OK**.</span></span>

3.  <span data-ttu-id="20365-178">Développez les pools de serveurs **Edge,** puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge que vous souhaitez maintenant utiliser pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="20365-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="20365-179">Sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="20365-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="20365-p119">Dans **Modifier les propriétés**, sous **Général**, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**. Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="20365-p119">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="20365-p120">Cliquez sur **Action**, sélectionnez **Topologie**, puis **Publier**. À l’invite dans la page **Publier la topologie**, cliquez sur **Suivant**. Une fois la publication terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="20365-p120">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="20365-185">Sur le serveur Edge, ouvrez l’Assistant Déploiement de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="20365-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="20365-186">Cliquez **sur Installer ou mettre à jour le système Skype Entreprise Server,** puis cliquez sur Installer ou supprimer des **composants Skype Entreprise Server.**</span><span class="sxs-lookup"><span data-stu-id="20365-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="20365-187">Cliquez sur **Réexécuter**.</span><span class="sxs-lookup"><span data-stu-id="20365-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="20365-188">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20365-188">Click **Next**.</span></span> <span data-ttu-id="20365-189">L’écran de résumé affiche les actions au fur et à mesure qu’elles s’exécutent.</span><span class="sxs-lookup"><span data-stu-id="20365-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="20365-190">Une fois le déploiement terminé, cliquez sur **Afficher le journal** pour afficher les fichiers journaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="20365-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="20365-191">Cliquez sur **Terminer** pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="20365-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="20365-192">Si le site contenant le pool de serveurs Edge ayant échoué contient des serveurs frontaux qui sont encore en cours d’exécution, vous devez mettre à jour le service de conférence web et le service de conférence A/V sur ces pools de serveurs frontaux afin d’utiliser un pool de serveurs Edge dans un site distant qui est encore en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="20365-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="20365-193">Faire échouer le pool edge utilisé pour la fédération XMPP dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="20365-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="20365-p123">Dans votre organisation, il existe un pool de serveurs Edge désigné en tant que pool à utiliser pour la fédération XMPP. Si ce pool tombe en panne, vous devez effectuer un basculement de la fédération XMPP et utiliser un autre pool de serveurs Edge pour permettre à la fédération XMPP de fonctionner à nouveau.</span><span class="sxs-lookup"><span data-stu-id="20365-p123">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="20365-196">Quand vous installez des pools de serveurs Edge et que vous activez la fédération XMPP, vous pouvez simplifier le processus de récupération d’urgence en configurant des enregistrements SRV DNS externes pour tous les pools de serveurs Edge (au lieu d’un seul) de la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="20365-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="20365-197">Chacun de ces enregistrements SRV doit avoir une priorité distincte.</span><span class="sxs-lookup"><span data-stu-id="20365-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="20365-198">Tout le trafic de la fédération XMPP passe par le pool dont l’enregistrement SRV a la priorité la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="20365-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="20365-199">Dans la procédure suivante, EdgePool1 est le pool qui a hébergé à l’origine la fédération XMPP. EdgePool2 est le pool qui va désormais héberger la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="20365-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="20365-200">Pour faire échouer le pool edge utilisé pour la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="20365-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="20365-201">Si vous n’avez pas d’autre pool de serveurs Edge déployé (en plus de celui qui est actuellement en panne), déployez ce pool.</span><span class="sxs-lookup"><span data-stu-id="20365-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="20365-202">Sur chaque serveur Edge du nouveau pool de serveurs Edge qui va héberger la fédération XMPP (EdgePool2), exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="20365-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="20365-203">Exécutez l’applet de commande suivante pour faire pointer à nouveau l’itinéraire de fédération XMPP vers EdgePool2 :</span><span class="sxs-lookup"><span data-stu-id="20365-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="20365-204">Dans cet exemple, Site2 est le site contenant le pool de serveurs Edge qui va héberger l’itinéraire de fédération XMPP. EdgeServer2.contoso.com est le nom de domaine complet d’un serveur Edge de ce pool.</span><span class="sxs-lookup"><span data-stu-id="20365-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="20365-205">Sur le serveur DNS externe, modifiez l’enregistrement DNS A afin que la fédération XMPP pointe vers EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="20365-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="20365-p125">Si vous n’avez pas encore d’enregistrement DNS SRV pour la fédération XMPP correspondant au pool de serveurs Edge qui va héberger la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant. La valeur du port de cet enregistrement SRV doit être 5269.</span><span class="sxs-lookup"><span data-stu-id="20365-p125">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="20365-208">Assurez-vous que le port externe 5269 du pool de serveurs Edge qui va héberger la fédération XMPP est ouvert.</span><span class="sxs-lookup"><span data-stu-id="20365-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="20365-209">Démarrez les services de tous les serveurs Edge du pool de serveurs Edge qui va héberger la fédération XMPP :</span><span class="sxs-lookup"><span data-stu-id="20365-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="20365-210">Faire échouer le pool edge utilisé pour la fédération Skype Entreprise Server ou XMPP</span><span class="sxs-lookup"><span data-stu-id="20365-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="20365-211">Après la restauration en ligne d’un pool Edge qui hébergeait la fédération, utilisez cette procédure pour restaurer l’itinéraire de fédération Skype Entreprise Server et/ou l’itinéraire de fédération XMPP pour utiliser à nouveau ce pool Edge restauré.</span><span class="sxs-lookup"><span data-stu-id="20365-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="20365-212">Sur le pool Edge de nouveau disponible, lancez les Services Edge.</span><span class="sxs-lookup"><span data-stu-id="20365-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="20365-213">Si vous souhaitez restaurer l’itinéraire de fédération Skype Entreprise Server pour utiliser le serveur Edge restauré, faites les choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="20365-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="20365-p126">Sur un serveur frontal, ouvrez le Générateur de topologie. Développez **Pool de serveurs Edge**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la fédération. Sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="20365-p126">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="20365-p127">Dans **Modifier les propriétés**, sous **Général**, désactivez l’option **Activer la fédération pour ce pool Edge (Port 5061)**. Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="20365-p127">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="20365-p128">Développez **Pools Edge**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge d’origine que vous voulez réutiliser pour la fédération. Sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="20365-p128">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="20365-p129">Dans **Modifier les propriétés**, sous **Général**, sélectionnez l’option **Activer la fédération pour ce pool Edge (Port 5061)**. Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="20365-p129">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="20365-p130">Cliquez sur **Action**, sélectionnez **Topologie**, puis **Publier**. À l’invite dans la page **Publier la topologie**, cliquez sur **Suivant**. Une fois la publication terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="20365-p130">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="20365-226">Sur le serveur Edge, ouvrez l’Assistant Déploiement de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="20365-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="20365-227">Cliquez sur Installer ou mettre à jour le système Skype Entreprise **Server,** puis cliquez sur Installer ou supprimer **des composants Skype Entreprise Server.**</span><span class="sxs-lookup"><span data-stu-id="20365-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="20365-228">Cliquez sur **Réexécuter**.</span><span class="sxs-lookup"><span data-stu-id="20365-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="20365-229">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20365-229">Click **Next**.</span></span> <span data-ttu-id="20365-230">L’écran de résumé affiche les actions au fur et à mesure qu’elles s’exécutent.</span><span class="sxs-lookup"><span data-stu-id="20365-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="20365-231">Une fois le déploiement terminé, cliquez sur **Afficher le journal** pour afficher les fichiers journaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="20365-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="20365-232">Cliquez sur **Terminer** pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="20365-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="20365-233">Si vous voulez restaurer l’itinéraire de fédération XMPP pour utiliser le serveur Edge restauré, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="20365-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="20365-234">Exécutez la cmdlet suivante pour pointer de nouveau l’itinéraire de fédération XMPP sur le pool Edge qui héberge désormais la fédération XMPP (dans cet exemple, EdgeServer1) :</span><span class="sxs-lookup"><span data-stu-id="20365-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="20365-235">Dans cet exemple, Site1 représente le site qui contient le pool Edge qui hébergera désormais l’itinéraire de fédération XMPP, et EdgeServer1.contoso.com représente le nom de domaine complet (FQDN) d’un serveur Edge de ce pool.</span><span class="sxs-lookup"><span data-stu-id="20365-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="20365-p133">Si vous n’avez pas encore d’enregistrement DNS SRV pour la fédération XMPP qui aboutit au pool Edge qui héberge désormais la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant. Cet enregistrement SRV doit avoir une valeur de port de 5269.</span><span class="sxs-lookup"><span data-stu-id="20365-p133">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="20365-238">Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la fédération XMPP de sorte qu’il pointe sur EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="20365-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="20365-239">Vérifiez que le port 5269 du pool Edge qui héberge désormais la fédération XMPP est ouvert de façon externe.</span><span class="sxs-lookup"><span data-stu-id="20365-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="20365-240">Si les pools frontaux ont continué à s’exécuter sur le site contenant le pool Edge qui a échoué et a été restauré, vous devez mettre à jour les services de conférence web et de conférence A/V sur ces pools frontaux pour réutiliser les pools Edge sur leur site local.</span><span class="sxs-lookup"><span data-stu-id="20365-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="20365-241">Si le pool frontal du site où le pool Edge a échoué échoue également, vous pouvez désormais utiliser Invoke–CsPoolFailback pour restaurer le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="20365-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="20365-242">Modifier le pool edge associé à un pool frontal</span><span class="sxs-lookup"><span data-stu-id="20365-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="20365-243">Si un pool de serveurs Edge est défaillant mais que le pool de serveurs frontaux du même site fonctionne encore, vous devrez définir le pool de serveurs frontaux pour qu’il utilise le pool de serveurs Edge d’un autre site jusqu’à ce que le pool de serveurs Edge défaillant soit restauré.</span><span class="sxs-lookup"><span data-stu-id="20365-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="20365-244">Dans le Générateur de topologie, accédez au nom du pool de serveurs frontaux que vous devez changer.</span><span class="sxs-lookup"><span data-stu-id="20365-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="20365-245">Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="20365-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="20365-246">Dans la section **Associations**, sous **Associer le pool de serveurs Edge (pour les composants multimédias)**, utilisez la zone de liste déroulante pour sélectionner le pool de serveurs Edge que vous voulez associer à ce pool de serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="20365-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="20365-247">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="20365-247">Click **OK**.</span></span>
