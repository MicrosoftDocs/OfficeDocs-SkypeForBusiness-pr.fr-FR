---
title: Basculement ou restauration d’un pool
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: d5409441336ef2af8bbe9c6a39530584a167ec05
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818205"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="6f9f0-103">Échec et reprise d’un regroupement dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6f9f0-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="6f9f0-104">Appliquez les procédures suivantes si un pool frontal unique a échoué et qu’il doit être en échec, ou si le pool ayant rencontré le désastre est en ligne et que vous devez rétablir le fonctionnement normal de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="6f9f0-105">Apprenez-en plus sur le basculement et le basculement du pool Edge utilisé pour la Fédération Skype entreprise ou XMPP, ou changez le pool de périphériques associés à un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="6f9f0-106">Basculer sur un pool frontal</span><span class="sxs-lookup"><span data-stu-id="6f9f0-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="6f9f0-107">Restauration d’un pool</span><span class="sxs-lookup"><span data-stu-id="6f9f0-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="6f9f0-108">Basculer vers le pool Edge utilisé pour la Fédération de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6f9f0-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="6f9f0-109">Basculer vers le pool Edge utilisé pour la Fédération XMPP dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6f9f0-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="6f9f0-110">Restauration de la liste détourée utilisée pour Skype entreprise Server Federation ou XMPP Federation</span><span class="sxs-lookup"><span data-stu-id="6f9f0-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="6f9f0-111">Changer le pool de frontière associé à un pool frontal</span><span class="sxs-lookup"><span data-stu-id="6f9f0-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="6f9f0-112">Basculer sur un pool frontal</span><span class="sxs-lookup"><span data-stu-id="6f9f0-112">Fail over a Front End pool</span></span>

<span data-ttu-id="6f9f0-113">Dans cette procédure, Datacenter1 contient Pool1 et Pool1 a échoué.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="6f9f0-114">Vous basculez vers Pool2 situé dans Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="6f9f0-115">La majeure partie du fonctionnement du basculement de pool implique un échec du magasin de gestion central, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="6f9f0-116">C’est important, car le magasin de gestion centralisée doit être opérationnel lorsque les utilisateurs du pool ont échoué.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="6f9f0-117">De plus, si un pool frontal tombe en panne mais que le pool Edge sur ce site est toujours en cours d’exécution, vous devez savoir si le pool d’applications de périmètre utilise le pool en échec en tant que pool de prochains tronçons.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="6f9f0-118">Si tel est le cas, vous devez modifier le pool Edge pour utiliser un autre pool frontal avant de basculer sur le pool frontal défectueux.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="6f9f0-119">La façon dont vous modifiez le paramètre de saut suivant dépend de la façon dont le bord utilise un pool sur le même site que le pool de périphérie ou un site différent.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="6f9f0-120">**Pour définir un pool de bords pour utiliser un pool de sauts suivant sur le même site**</span><span class="sxs-lookup"><span data-stu-id="6f9f0-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="6f9f0-121">Ouvrez le générateur de topologie, cliquez avec le bouton droit sur le pool de bords qui doit être modifié, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="6f9f0-122">Cliquez sur **tronçon suivant**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-122">Click **Next Hop**.</span></span> <span data-ttu-id="6f9f0-123">À partir de la liste **pool de prochains tronçons :** , sélectionnez le pool qui fera désormais Office de réserve de prochains tronçon.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="6f9f0-124">Cliquez sur **OK**, puis publiez les modifications.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="6f9f0-125">**Pour définir un pool de bords pour utiliser un pool de sauts suivant sur un autre site**</span><span class="sxs-lookup"><span data-stu-id="6f9f0-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="6f9f0-126">Ouvrez une fenêtre Skype entreprise Server Management Shell et tapez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="6f9f0-127">**Pour basculer sur un pool en cas de sinistre**</span><span class="sxs-lookup"><span data-stu-id="6f9f0-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="6f9f0-128">Recherchez quel pool est l’hôte du serveur de gestion central en tapant l’applet de commande suivante sur un serveur frontal dans Pool2 :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="6f9f0-129">Les résultats de cette applet de requête indiquent le pool qui héberge actuellement le serveur de gestion central.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="6f9f0-130">Dans le reste de cette procédure, ce pool est appelé pool CMS\_.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="6f9f0-131">Utilisez le générateur de topologie pour rechercher la version de Skype entreprise Server en cours d’exécution\_sur le pool CMS.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="6f9f0-132">S’il s’agit de Skype entreprise Server, utilisez l’applet de commande suivante pour trouver le pool de sauvegarde du pool 1.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="6f9f0-133">Laissez le\_pool de sauvegarde être le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="6f9f0-134">Vérifiez l’état du magasin central de gestion avec l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="6f9f0-135">Cette applet de cmdlet doit indiquer que ActiveMasterFQDN et ActiveFileTransferAgents sont dirigés vers le nom\_de domaine complet du pool CMS.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="6f9f0-136">S’il est vide, le serveur de gestion central n’est pas disponible et vous devez le basculer.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="6f9f0-137">Si le magasin de gestion central n’est pas disponible ou si la Banque de gestion centrale s’exécutait sur Pool1 (autrement dit, le pool ayant échoué), vous devez faire basculer le serveur de gestion central avant de basculer sur le pool.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="6f9f0-138">Si vous avez besoin de basculer sur le serveur de gestion central hébergé sur un pool exécutant Skype entreprise Server, utilisez l’applet de demande à l’étape 5 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="6f9f0-139">Si vous n’avez pas besoin de basculer sur le serveur de gestion central, passez à l’étape 7 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="6f9f0-140">Pour faire basculer le magasin de gestion central sur un pool exécutant Skype entreprise Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="6f9f0-141">Tout d’abord, vérifiez quel serveur principal du\_pool de sauvegarde exécute l’instance principale du magasin central de gestion en entrant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="6f9f0-142">Si le serveur principal principal du pool de\_sauvegarde est le principal, tapez :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="6f9f0-143">Si le serveur principal miroir du pool de\_sauvegarde est le principal, tapez :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="6f9f0-144">Vérifiez que le basculement du serveur central de gestion est terminé.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="6f9f0-145">Tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="6f9f0-146">Vérifiez que les ActiveMasterFQDN et ActiveFileTransferAgents pointent sur le nom de domaine\_complet (FQDN) du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="6f9f0-147">Enfin, vérifiez l’état de réplica de tous les serveurs front-end en entrant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="6f9f0-148">Vérifiez que tous les réplicas ont la valeur true.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="6f9f0-149">Passez à l’étape 7 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="6f9f0-150">Installez le centre de gestion central sur le serveur principal du pool\_de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="6f9f0-151">Tout d’abord, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="6f9f0-152">Exécutez la commande suivante sur l’un des serveurs front-end du\_pool de sauvegarde pour forcer le déplacement du magasin de gestion central :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="6f9f0-153">Valider le déplacement est terminé :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="6f9f0-154">Vérifiez que les ActiveMasterFQDN et ActiveFileTransferAgents pointent sur le nom de domaine\_complet (FQDN) du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="6f9f0-155">Vérifiez l’état du réplica pour tous les serveurs frontaux en entrant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="6f9f0-156">Vérifiez que tous les réplicas ont la valeur true.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="6f9f0-157">Installez le service central de gestion sur le reste des serveurs frontaux dans le pool\_de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="6f9f0-158">Pour cela, exécutez la commande suivante sur tous les serveurs frontaux, à l’exception de celle que vous avez utilisée lorsque vous forcez le déplacement du magasin de gestion central plus haut dans cette procédure :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="6f9f0-159">Basculez les utilisateurs de Pool1 à Pool2 en exécutant l’applet de commande suivante dans une fenêtre Skype entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="6f9f0-160">Dans la mesure où les étapes décrites dans les parties précédentes de cette procédure permettent de vérifier que l’état du magasin de gestion central n’est pas universel, il est possible que cette applet de connexion échoue, car le magasin central de gestion n’a pas encore été complètement en échec.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="6f9f0-161">Dans ce cas, vous devez résoudre le magasin de gestion central en fonction des messages d’erreur qui s’affichent, puis réexécuter cette cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="6f9f0-162">Si vous voyez le message d’erreur suivant, vous devez modifier le pool de périphérie sur ce site pour utiliser un autre pool comme tronçon suivant avant d’avoir basculé sur le pool.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="6f9f0-163">Pour plus d’informations, reportez-vous aux procédures au début de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="6f9f0-164">Restauration d’un pool</span><span class="sxs-lookup"><span data-stu-id="6f9f0-164">Fail back a pool</span></span>

<span data-ttu-id="6f9f0-165">Une fois que le regroupement qui a expérimenté le désastre est en ligne (à savoir Pool1 dans cet exemple), procédez comme suit pour restaurer le statut de travail normal de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="6f9f0-166">Notez que le processus de restauration automatique prend quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="6f9f0-167">À titre de référence, il devrait prendre jusqu’à 60 minutes pour un pool de 20 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="6f9f0-168">Restaurez les utilisateurs qui ont été initialement hébergés dans Pool1 et qui ont échoué sur Pool2 en tapant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="6f9f0-169">Aucune autre étape n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-169">No other steps are necessary.</span></span> <span data-ttu-id="6f9f0-170">Si vous avez échoué sur le serveur de gestion central, vous pouvez le laisser dans Pool2.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="6f9f0-171">Basculer vers le pool Edge utilisé pour la Fédération de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6f9f0-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="6f9f0-172">Si le pool de périphériques sur lequel vous avez configuré la Fédération de Skype entreprise Server s’affiche, vous devez modifier la Fédération de manière à utiliser un pool de périphérie différent pour que la Fédération fonctionne.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="6f9f0-173">Sur un serveur frontal, ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="6f9f0-174">Développez **pools de bords**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="6f9f0-175">Sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="6f9f0-176">Dans **modifier les propriétés** sous **général**, décochez **la case Activer la Fédération pour ce pool de périphériques (port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="6f9f0-177">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-177">Click **OK**.</span></span>

3.  <span data-ttu-id="6f9f0-178">Développez **pools de bords**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge que vous voulez utiliser pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="6f9f0-179">Sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="6f9f0-180">Dans **modifier les propriétés** sous **général**, sélectionnez **activer la Fédération pour ce pool Edge (port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="6f9f0-181">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-181">Click **OK**.</span></span>

5.  <span data-ttu-id="6f9f0-182">Cliquez sur **action**, sélectionnez **topologie**, puis **publier**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="6f9f0-183">Lorsque le système vous **le**demande, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="6f9f0-184">Lorsque la publication est terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="6f9f0-185">Sur le serveur Edge, ouvrez l’Assistant Déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="6f9f0-186">Cliquez sur **installer ou mettre à jour le système Skype entreprise Server**, puis cliquez sur **configurer ou supprimer les composants Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="6f9f0-187">Cliquez de **nouveau sur exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="6f9f0-188">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-188">Click **Next**.</span></span> <span data-ttu-id="6f9f0-189">L’écran de synthèse indique les actions à mesure qu’elles sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="6f9f0-190">Lorsque le déploiement est effectué, cliquez sur **afficher le journal** pour afficher les fichiers journaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="6f9f0-191">Cliquez sur **Terminer** pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="6f9f0-192">Si le site contenant le pool de périphériques en échec contient des serveurs frontaux qui sont toujours en cours d’exécution, vous devez mettre à jour les services de conférence Web et de conférence A/V sur ces pools frontal pour qu’ils utilisent un pool de bords sur un site distant qui est toujours en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="6f9f0-193">Basculer vers le pool Edge utilisé pour la Fédération XMPP dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6f9f0-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="6f9f0-194">Dans votre organisation, il existe un pool Edge désigné comme pool à utiliser pour la Fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="6f9f0-195">Si ce pool est vers le bas, vous devez le faire basculer sur la Fédération XMPP pour utiliser un pool Edge différent avant que la Fédération XMPP puisse fonctionner de nouveau.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="6f9f0-196">Lorsque vous installez les pools de périphérie et activez la Fédération XMPP, vous pouvez simplifier le processus de reprise après sinistre en configurant des enregistrements SRV DNS externes pour tous vos pools de périphérie pour la Fédération XMPP, au lieu d’une seule.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="6f9f0-197">Chacun de ces enregistrements SRV doit avoir un ensemble de priorités différent.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="6f9f0-198">Tout le trafic de Fédération XMPP traverse le pool avec l’enregistrement SRV dont la priorité est la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="6f9f0-199">Dans la procédure ci-dessous, EdgePool1 est le pool qui a hébergé la Fédération XMPP et EdgePool2 est le pool qui héberge désormais la Fédération de XMPP.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="6f9f0-200">Pour faire basculer le pool Edge utilisé pour la Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="6f9f0-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="6f9f0-201">Si vous n’avez pas encore déployé un pool Edge (en plus de celui qui est actuellement disponible), vous devez déployer ce pool.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="6f9f0-202">Sur chaque serveur Edge du nouveau pool de périphériques Edge qui hébergera maintenant la Fédération de XMPP (EdgePool2), exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="6f9f0-203">Exécutez l’applet de commande suivante pour rediriger l’itinéraire de Fédération XMPP vers EdgePool2 :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="6f9f0-204">Dans cet exemple, site2 est le site contenant le pool de bords qui héberge désormais l’itinéraire de Fédération XMPP et EdgeServer2.contoso.com est le nom de domaine complet d’un serveur Edge dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="6f9f0-205">Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la Fédération XMPP de sorte qu’il pointe sur EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="6f9f0-206">Si vous ne disposez pas encore d’un enregistrement DNS SRV pour la Fédération XMPP qui se résout au pool de périphérie qui hébergera maintenant la Fédération de XMPP, vous devez l’ajouter, comme dans l’exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="6f9f0-207">Cet enregistrement SRV doit avoir une valeur de port de 5269.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="6f9f0-208">Assurez-vous que le pool de bords qui hébergera désormais la Fédération XMPP dispose d’une ouverture externe du port 5269.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="6f9f0-209">Démarrez les services sur tous les serveurs Edge du pool Edge qui hébergeront désormais la Fédération XMPP :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="6f9f0-210">Restauration de la liste détourée utilisée pour Skype entreprise Server Federation ou XMPP Federation</span><span class="sxs-lookup"><span data-stu-id="6f9f0-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="6f9f0-211">Après le rétablissement d’un pool de périphériques inactif utilisé pour la Fédération d’hébergement en ligne, procédez comme suit pour restaurer le routage de la Fédération Skype entreprise Server et/ou l’itinéraire de Fédération XMPP pour qu’il utilise de nouveau ce pool de périphériques restaurés.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="6f9f0-212">Sur le pool Edge qui est désormais disponible, démarrez les services Edge.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="6f9f0-213">Si vous souhaitez remettre en échec l’itinéraire de la Fédération Skype entreprise Server afin qu’il utilise le serveur Edge restauré, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="6f9f0-214">Sur un serveur frontal, ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="6f9f0-215">Développez **pools de bords**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="6f9f0-216">Sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="6f9f0-217">Dans **modifier les propriétés** sous **général**, décochez **la case Activer la Fédération pour ce pool de périphériques (port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="6f9f0-218">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="6f9f0-219">Développez **pools de bords**, puis cliquez avec le bouton droit sur le serveur Edge d’origine ou sur le pool de serveurs Edge que vous souhaitez utiliser pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="6f9f0-220">Sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="6f9f0-221">Dans **modifier les propriétés** sous **général**, sélectionnez **activer la Fédération pour ce pool Edge (port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="6f9f0-222">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="6f9f0-223">Cliquez sur **action**, sélectionnez **topologie**, puis **publier**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="6f9f0-224">Lorsque le système vous **le**demande, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="6f9f0-225">Lorsque la publication est terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="6f9f0-226">Sur le serveur Edge, ouvrez l’Assistant Déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="6f9f0-227">Cliquez sur **installer ou mettre à jour le système Skype entreprise Server**, puis cliquez sur **configurer ou supprimer les composants Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="6f9f0-228">Cliquez de **nouveau sur exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="6f9f0-229">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-229">Click **Next**.</span></span> <span data-ttu-id="6f9f0-230">L’écran de synthèse indique les actions à mesure qu’elles sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="6f9f0-231">Lorsque le déploiement est effectué, cliquez sur **afficher le journal** pour afficher les fichiers journaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="6f9f0-232">Cliquez sur **Terminer** pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="6f9f0-233">Si vous souhaitez restaurer l’itinéraire de la Fédération XMPP de manière à utiliser le serveur de périphérie de restauration, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="6f9f0-234">Exécutez l’applet de commande suivante pour rediriger l’itinéraire de Fédération XMPP vers le pool Edge qui hébergera maintenant la Fédération de XMPP (dans cet exemple, EdgeServer1) :</span><span class="sxs-lookup"><span data-stu-id="6f9f0-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="6f9f0-235">Dans cet exemple, site1 est le site contenant le pool de bords qui héberge désormais l’itinéraire de Fédération XMPP et EdgeServer1.contoso.com est le nom de domaine complet d’un serveur Edge dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="6f9f0-236">Si vous ne disposez pas encore d’un enregistrement DNS SRV pour la Fédération XMPP qui se résout au pool de périphérie qui hébergera maintenant la Fédération de XMPP, vous devez l’ajouter, comme dans l’exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="6f9f0-237">Cet enregistrement SRV doit avoir une valeur de port de 5269.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="6f9f0-238">Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la Fédération XMPP de sorte qu’il pointe sur EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="6f9f0-239">Assurez-vous que le pool de bords qui hébergera désormais la Fédération XMPP dispose d’une ouverture externe du port 5269.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="6f9f0-240">Si le pool frontal restait en cours d’exécution sur le site contenant le pool de périphériques ayant échoué et a été restauré, vous devez mettre à jour les services de conférence Web et de service de conférence A/V sur ces pools frontal pour pouvoir utiliser les pools de périphérie sur leur site local.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="6f9f0-241">Si le pool frontal sur le même site que le pool d’échecs en panne ne fonctionne pas, vous pouvez désormais utiliser Invoke-CsPoolFailback pour restaurer le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="6f9f0-242">Changer le pool de frontière associé à un pool frontal</span><span class="sxs-lookup"><span data-stu-id="6f9f0-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="6f9f0-243">Si un pool de bords est en panne alors que le pool frontal sur le même site est toujours en cours d’exécution, vous devez définir le pool frontal pour qu’il utilise un pool de bords sur un autre site jusqu’à ce que le pool de frontière en panne soit restauré.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="6f9f0-244">Dans le générateur de topologie, accédez au nom de la réserve frontale que vous devez modifier.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="6f9f0-245">Cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="6f9f0-246">Dans la section **associations** , sous **associer le pool de bords (pour les composants multimédias)**, utilisez la zone de liste déroulante pour sélectionner le pool de bords avec lequel vous voulez associer ce pool frontal.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="6f9f0-247">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f9f0-247">Click **OK**.</span></span>
