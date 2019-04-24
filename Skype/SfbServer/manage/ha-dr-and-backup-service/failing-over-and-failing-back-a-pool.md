---
title: Basculement ou restauration d’un pool
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 809d0305eaa4c8e2197c5137a647ff9354cbf9bd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197799"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="f383f-103">Échec de plus, sinon back un pool dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="f383f-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="f383f-104">Utilisez les procédures suivantes si un pool frontal unique a échoué et doit être basculé ou le pool ayant subi une défaillance est en ligne et que vous avez besoin de restaurer votre déploiement à l’état de fonctionnement normal.</span><span class="sxs-lookup"><span data-stu-id="f383f-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="f383f-105">Également Découvrez comment réaliser le basculement et la restauration automatique du pool Edge utilisé pour Skype pour la fédération entreprise ou la fédération XMPP ou modifier le pool Edge associé à un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="f383f-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="f383f-106">Faire basculer un pool frontal</span><span class="sxs-lookup"><span data-stu-id="f383f-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="f383f-107">Restauration d’un pool</span><span class="sxs-lookup"><span data-stu-id="f383f-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="f383f-108">Faire basculer le pool Edge utilisé pour Skype pour la fédération Business Server</span><span class="sxs-lookup"><span data-stu-id="f383f-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="f383f-109">Basculement du pool Edge utilisé pour la fédération XMPP dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="f383f-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="f383f-110">Basculer le pool Edge utilisé pour Skype pour la fédération du serveur d’entreprise ou la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="f383f-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="f383f-111">Changer le pool Edge associé à un pool frontal</span><span class="sxs-lookup"><span data-stu-id="f383f-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="f383f-112">Faire basculer un pool frontal</span><span class="sxs-lookup"><span data-stu-id="f383f-112">Fail over a Front End pool</span></span>

<span data-ttu-id="f383f-113">Dans cette procédure, Datacenter1 contient Pool1 et Pool1 a échoué.</span><span class="sxs-lookup"><span data-stu-id="f383f-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="f383f-114">Basculement vers Pool2 situé dans Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="f383f-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="f383f-115">La plupart du travail pour le basculement de pool implique le basculement du magasin Central de gestion, si cela est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f383f-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="f383f-116">Ceci est important parce que le magasin Central de gestion doit être fonctionnel lorsque les utilisateurs du pool sont basculées.</span><span class="sxs-lookup"><span data-stu-id="f383f-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="f383f-117">En outre, si un pool frontal échoue mais que le pool Edge sur le site est en cours d’exécution, vous devez savoir si le pool de serveurs Edge utilise le pool ayant échoué comme un pool du tronçon suivant.</span><span class="sxs-lookup"><span data-stu-id="f383f-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="f383f-118">Si c’est le cas, vous devez modifier le pool Edge pour utiliser un autre pool frontal avant le basculement sur le pool frontal ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="f383f-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="f383f-119">Comment vous modifiez le paramètre du tronçon suivant dépend de si le bord utilise un pool sur le même site que le pool de serveurs Edge ou un autre site.</span><span class="sxs-lookup"><span data-stu-id="f383f-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="f383f-120">**Pour définir un pool de serveurs Edge à utiliser un pool du tronçon suivant sur le même site**</span><span class="sxs-lookup"><span data-stu-id="f383f-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="f383f-121">Ouvrez le Générateur de topologie, avec le bouton droit le pool Edge qui doit être modifié, cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f383f-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f383f-122">Cliquez sur le **tronçon suivant**.</span><span class="sxs-lookup"><span data-stu-id="f383f-122">Click **Next Hop**.</span></span> <span data-ttu-id="f383f-123">À partir de la **pool du tronçon suivant :** , sélectionnez le pool qui servira maintenant le pool du tronçon suivant.</span><span class="sxs-lookup"><span data-stu-id="f383f-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="f383f-124">Cliquez sur **OK**, puis publiez les modifications.</span><span class="sxs-lookup"><span data-stu-id="f383f-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="f383f-125">**Pour définir un pool de serveurs Edge à utiliser un pool du tronçon suivant dans un autre site**</span><span class="sxs-lookup"><span data-stu-id="f383f-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="f383f-126">Ouvrez un Skype pour fenêtre Business Server Management Shell et entrez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f383f-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="f383f-127">**Pour faire basculer un pool en cas d’urgence**</span><span class="sxs-lookup"><span data-stu-id="f383f-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="f383f-128">Recherchez le pool qui sert de l’hôte pour le serveur d’administration centrale en tapant l’applet de commande suivante sur un serveur frontal dans Pool2 :</span><span class="sxs-lookup"><span data-stu-id="f383f-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="f383f-129">Les résultats de cette présentation de l’applet de commande quel pool héberge actuellement le serveur d’administration centrale.</span><span class="sxs-lookup"><span data-stu-id="f383f-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="f383f-130">Dans le reste de cette procédure, ce pool est appelé CMS\_Pool.</span><span class="sxs-lookup"><span data-stu-id="f383f-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="f383f-131">Utilisez le Générateur de topologie pour trouver la version de Skype pour Business Server s’exécutant sur le serveur CMS\_Pool.</span><span class="sxs-lookup"><span data-stu-id="f383f-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="f383f-132">Si elle est en cours d’exécution Skype pour Business Server, utilisez l’applet de commande suivante pour rechercher le pool de sauvegarde du Pool 1.</span><span class="sxs-lookup"><span data-stu-id="f383f-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="f383f-133">Permettre la sauvegarde\_Pool est le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f383f-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="f383f-134">Vérifier l’état du magasin Central de gestion avec l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f383f-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="f383f-135">Cette applet de commande doit s’afficher que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de domaine complet du serveur CMS\_Pool.</span><span class="sxs-lookup"><span data-stu-id="f383f-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="f383f-136">S’ils sont vides, le serveur d’administration centrale n’est pas disponible et vous devez le faire basculer.</span><span class="sxs-lookup"><span data-stu-id="f383f-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="f383f-137">Si le magasin Central de gestion n’est pas disponible ou si le magasin Central de gestion a été exécuté sur Pool1 (autrement dit, le pool qui a échoué), vous devez basculer sur le serveur de gestion centralisée avant le basculement vers le pool.</span><span class="sxs-lookup"><span data-stu-id="f383f-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="f383f-138">Si vous avez besoin faire basculer le serveur de gestion centralisée qui était hébergée sur un pool en cours d’exécution Skype pour Business Server, utilisez l’applet de commande à l’étape 5 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="f383f-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="f383f-139">Si vous n’avez besoin pas basculer sur le serveur d’administration centrale, passez à l’étape 7 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="f383f-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="f383f-140">Pour faire basculer le magasin Central de gestion sur un pool en cours d’exécution Skype pour Business Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f383f-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="f383f-141">Vérifiez d’abord quel serveur principal sauvegarde\_Pool s’exécute l’instance principale du magasin Central de gestion en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f383f-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="f383f-142">Si le serveur principal primaire dans sauvegarde\_Pool est le principal, type :</span><span class="sxs-lookup"><span data-stu-id="f383f-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="f383f-143">Si le serveur principal sauvegarde miroir\_Pool est le principal, type :</span><span class="sxs-lookup"><span data-stu-id="f383f-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="f383f-144">Vérifier que le basculement du serveur de gestion centralisée est terminé.</span><span class="sxs-lookup"><span data-stu-id="f383f-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="f383f-145">Tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f383f-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="f383f-146">Vérifiez que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de domaine complet de sauvegarde\_Pool.</span><span class="sxs-lookup"><span data-stu-id="f383f-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="f383f-147">Enfin, vérifiez le statut des réplicas pour tous les serveurs frontaux en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f383f-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="f383f-148">Vérifiez que tous les réplicas ont la valeur True.</span><span class="sxs-lookup"><span data-stu-id="f383f-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="f383f-149">Passez à l’étape 7 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="f383f-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="f383f-150">Installer le magasin Central de gestion sur le Back End Server de sauvegarde\_Pool.</span><span class="sxs-lookup"><span data-stu-id="f383f-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="f383f-151">Tout d’abord, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f383f-151">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="f383f-152">Exécutez la commande suivante sur un de la Front End serveurs de sauvegarde\_Pool pour forcer le déplacement du magasin Central de gestion :</span><span class="sxs-lookup"><span data-stu-id="f383f-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="f383f-153">Valider le déplacement est terminé :</span><span class="sxs-lookup"><span data-stu-id="f383f-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="f383f-154">Vérifiez que ActiveMasterFQDN et ActiveFileTransferAgents pointent vers le nom de domaine complet de sauvegarde\_Pool.</span><span class="sxs-lookup"><span data-stu-id="f383f-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="f383f-155">Vérifiez le statut des réplicas pour tous les serveurs frontaux en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f383f-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="f383f-156">Vérifiez que tous les réplicas ont la valeur True.</span><span class="sxs-lookup"><span data-stu-id="f383f-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="f383f-157">Installez le service de serveur de gestion centralisée sur le reste des serveurs frontaux dans sauvegarde\_Pool.</span><span class="sxs-lookup"><span data-stu-id="f383f-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="f383f-158">Pour ce faire, exécutez la commande suivante sur tous les serveurs frontaux, sauf celle que vous avez utilisé pour forcer la gestion centralisée magasin déplacer plus haut dans cette procédure :</span><span class="sxs-lookup"><span data-stu-id="f383f-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="f383f-159">Faire basculer les utilisateurs de Pool1 vers Pool2 en exécutant la cmdlet suivante dans un Skype pour fenêtre Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="f383f-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="f383f-160">Les étapes effectuées dans les parties précédentes de cette procédure pour vérifier l’état du magasin Central de gestion n’étant pas universels, il est toujours un risque que cette applet de commande échouera car le magasin Central de gestion pas encore totalement de basculement.</span><span class="sxs-lookup"><span data-stu-id="f383f-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="f383f-161">Dans ce cas, vous devez corriger le magasin Central de gestion basé sur les messages d’erreur que vous voyez et puis réexécuter cette applet de commande.</span><span class="sxs-lookup"><span data-stu-id="f383f-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="f383f-162">Si vous voyez le message d’erreur suivant, vous devez modifier le pool Edge sur ce site à utiliser un autre pool comme son tronçon suivant avant le basculement sur le pool.</span><span class="sxs-lookup"><span data-stu-id="f383f-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="f383f-163">Pour plus d’informations, voir les procédures au début de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="f383f-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="f383f-164">Restauration d’un pool</span><span class="sxs-lookup"><span data-stu-id="f383f-164">Fail back a pool</span></span>

<span data-ttu-id="f383f-165">Une fois que le pool ayant subi une défaillance est en ligne (Pool1 dans cet exemple), procédez comme suit pour restaurer votre déploiement à l’état de fonctionnement normal.</span><span class="sxs-lookup"><span data-stu-id="f383f-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="f383f-166">Notez que le processus de basculement prend plusieurs minutes à effectuer.</span><span class="sxs-lookup"><span data-stu-id="f383f-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="f383f-167">À titre de référence, il devrait prendre jusqu’à 60 minutes pour un pool de 20 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f383f-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="f383f-168">Restaurez les utilisateurs qui étaient initialement hébergés dans Pool1 et ont été basculés vers Pool2 en tapant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f383f-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="f383f-169">Aucun autres étapes ne sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="f383f-169">No other steps are necessary.</span></span> <span data-ttu-id="f383f-170">Si vous n’avez pas sur le serveur d’administration centrale, vous pouvez le laisser dans Pool2.</span><span class="sxs-lookup"><span data-stu-id="f383f-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="f383f-171">Faire basculer le pool Edge utilisé pour Skype pour la fédération Business Server</span><span class="sxs-lookup"><span data-stu-id="f383f-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="f383f-172">Si le pool Edge où vous avez Skype pour la fédération Business Server configurée tombe en panne, vous devez modifier la fédération pour utiliser un autre pool Edge pour la fédération fonctionne.</span><span class="sxs-lookup"><span data-stu-id="f383f-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="f383f-173">Sur un serveur frontal, ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="f383f-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="f383f-174">Développez **pools de serveurs Edge**, puis cliquez sur le serveur Edge ou le pool de serveurs Edge qui est actuellement configuré pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="f383f-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="f383f-175">Sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f383f-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="f383f-176">Dans **Modifier les propriétés** , sous **Général**, désactivez **Activer la fédération pour ce pool Edge (Port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="f383f-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="f383f-177">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f383f-177">Click **OK**.</span></span>

3.  <span data-ttu-id="f383f-178">Développez **pools de serveurs Edge**, puis cliquez sur le serveur Edge ou le pool de serveurs Edge que vous souhaitez utiliser pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="f383f-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="f383f-179">Sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f383f-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="f383f-180">Dans **Modifier les propriétés** , sous **Général**, sélectionnez **Activer la fédération pour ce pool Edge (Port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="f383f-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="f383f-181">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f383f-181">Click **OK**.</span></span>

5.  <span data-ttu-id="f383f-182">Cliquez sur **Action**, sélectionnez **la topologie**, sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="f383f-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="f383f-183">Lorsque vous y êtes invité sur **publier la topologie**, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f383f-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="f383f-184">Lorsque la publication est terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f383f-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="f383f-185">Sur le serveur de périphérie, ouvrez le Skype pour l’Assistant de déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f383f-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="f383f-186">Cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**, puis cliquez sur **installer ou supprimer des Skype pour les composants de serveur d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="f383f-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="f383f-187">Cliquez sur **réexécuter**.</span><span class="sxs-lookup"><span data-stu-id="f383f-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="f383f-188">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f383f-188">Click **Next**.</span></span> <span data-ttu-id="f383f-189">L’écran Résumé affiche les actions quand elles sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="f383f-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="f383f-190">Une fois le déploiement est terminé, cliquez sur **Afficher le journal** pour afficher les fichiers journaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="f383f-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="f383f-191">Cliquez sur **Terminer** pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="f383f-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="f383f-192">Si le site contenant le pool Edge ayant échoué contient les serveurs frontaux qui sont en cours d’exécution, vous devez mettre à jour le Service de conférence Web et A / V de Service de conférence sur ces pools frontaux à utiliser un pool de serveurs Edge dans un à distance de sites qui est toujours en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="f383f-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="f383f-193">Basculement du pool Edge utilisé pour la fédération XMPP dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="f383f-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="f383f-194">Dans votre organisation, il existe un pool de serveurs Edge désigné en tant que le pool à utiliser pour la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="f383f-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="f383f-195">Si ce pool tombe en panne, vous devez basculer vers la fédération XMPP pour utiliser un autre pool Edge avant la fédération XMPP peut fonctionner à nouveau.</span><span class="sxs-lookup"><span data-stu-id="f383f-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="f383f-196">Lors de la première installation de pools de serveurs Edge et activer la fédération XMPP, vous pouvez simplifier le processus de récupération d’urgence en configurant les enregistrements SRV DNS externes pour tous vos pools Edge pour la fédération XMPP, au lieu d’un seul.</span><span class="sxs-lookup"><span data-stu-id="f383f-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="f383f-197">Chacun de ces enregistrements SRV doit avoir une priorité différente défini.</span><span class="sxs-lookup"><span data-stu-id="f383f-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="f383f-198">Tout le trafic de fédération XMPP accède par le biais du pool dont l’enregistrement SRV avec la priorité la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="f383f-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="f383f-199">Dans la procédure suivante, EdgePool1 est le pool qui hébergeait à l’origine de la fédération XMPP et EdgePool2 est le pool qui va héberger la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="f383f-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="f383f-200">Pour faire basculer le pool Edge utilisé pour la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="f383f-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="f383f-201">Si vous ne disposez pas d’un autre pool de serveurs Edge déployé (en plus de celui qui est actuellement vers le bas), déployer ce pool.</span><span class="sxs-lookup"><span data-stu-id="f383f-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="f383f-202">Sur chaque serveur Edge du nouveau pool Edge qui va héberger la fédération XMPP (EdgePool2), exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f383f-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="f383f-203">Exécutez la cmdlet suivante pour faire pointer à nouveau l’itinéraire de fédération XMPP vers EdgePool2 :</span><span class="sxs-lookup"><span data-stu-id="f383f-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="f383f-204">Dans cet exemple, Site2 est le site contenant le pool Edge qui va héberger l’itinéraire de fédération XMPP et EdgeServer2.contoso.com est le nom de domaine complet d’un serveur Edge de ce pool.</span><span class="sxs-lookup"><span data-stu-id="f383f-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="f383f-205">Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la fédération XMPP vers EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f383f-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="f383f-206">Si vous n’avez pas déjà un enregistrement DNS SRV pour la fédération XMPP qui correspond au pool Edge qui va héberger la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="f383f-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="f383f-207">Cet enregistrement SRV doit avoir la valeur port 5269.</span><span class="sxs-lookup"><span data-stu-id="f383f-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="f383f-208">Vérifiez que le pool Edge qui va héberger la fédération XMPP a port 5269 open en externe.</span><span class="sxs-lookup"><span data-stu-id="f383f-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="f383f-209">Démarrer les services sur tous les serveurs Edge du pool Edge qui va héberger la fédération XMPP :</span><span class="sxs-lookup"><span data-stu-id="f383f-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="f383f-210">Basculer le pool Edge utilisé pour Skype pour la fédération du serveur d’entreprise ou la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="f383f-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="f383f-211">Après un échec Edge pool utilisé pour la fédération hôte a été remis en ligne, utilisez cette procédure pour basculer le Skype pour l’itinéraire de fédération Business Server et/ou l’itinéraire de fédération XMPP pour réutiliser ce pool Edge restauré.</span><span class="sxs-lookup"><span data-stu-id="f383f-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="f383f-212">Sur le pool Edge qui est maintenant à nouveau disponible, démarrer les Services de périphérie.</span><span class="sxs-lookup"><span data-stu-id="f383f-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="f383f-213">Si vous voulez restaurer le Skype pour l’itinéraire de fédération Business Server afin d’utiliser le serveur Edge restauré, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f383f-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="f383f-214">Sur un serveur frontal, ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="f383f-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="f383f-215">Développez **pools de serveurs Edge**, puis avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge qui est actuellement configuré pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="f383f-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="f383f-216">Sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f383f-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="f383f-217">Dans **Modifier les propriétés** , sous **Général**, désactivez **Activer la fédération pour ce pool Edge (Port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="f383f-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="f383f-218">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f383f-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="f383f-219">Développez **pools de serveurs Edge**, puis avec le bouton droit sur le serveur de périphérie d’origine ou d’un pool de serveurs Edge que vous souhaitez à nouveau utiliser pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="f383f-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="f383f-220">Sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f383f-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="f383f-221">Dans **Modifier les propriétés** , sous **Général**, sélectionnez **Activer la fédération pour ce pool Edge (Port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="f383f-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="f383f-222">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f383f-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="f383f-223">Cliquez sur **Action**, sélectionnez **la topologie**, sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="f383f-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="f383f-224">Lorsque vous y êtes invité sur **publier la topologie**, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f383f-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="f383f-225">Lorsque la publication est terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f383f-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="f383f-226">Sur le serveur de périphérie, ouvrez le Skype pour l’Assistant de déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f383f-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="f383f-227">Cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**, puis cliquez sur **installer ou supprimer des Skype pour les composants de serveur d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="f383f-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="f383f-228">Cliquez sur **réexécuter**.</span><span class="sxs-lookup"><span data-stu-id="f383f-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="f383f-229">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f383f-229">Click **Next**.</span></span> <span data-ttu-id="f383f-230">L’écran Résumé affiche les actions quand elles sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="f383f-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="f383f-231">Une fois le déploiement est terminé, cliquez sur **Afficher le journal** pour afficher les fichiers journaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="f383f-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="f383f-232">Cliquez sur **Terminer** pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="f383f-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="f383f-233">Si vous voulez restaurer l’itinéraire de fédération XMPP pour utiliser le serveur Edge restauré, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f383f-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="f383f-234">Exécutez la cmdlet suivante pour faire pointer à nouveau l’itinéraire de fédération XMPP vers le pool Edge qui va héberger la fédération XMPP (dans cet exemple, EdgeServer1) :</span><span class="sxs-lookup"><span data-stu-id="f383f-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="f383f-235">Dans cet exemple, Site1 est le site contenant le pool Edge qui va héberger l’itinéraire de fédération XMPP et EdgeServer1.contoso.com est le nom de domaine complet d’un serveur Edge de ce pool.</span><span class="sxs-lookup"><span data-stu-id="f383f-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="f383f-236">Si vous n’avez pas déjà un enregistrement DNS SRV pour la fédération XMPP qui correspond au pool Edge qui va héberger la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="f383f-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="f383f-237">Cet enregistrement SRV doit avoir la valeur port 5269.</span><span class="sxs-lookup"><span data-stu-id="f383f-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="f383f-238">Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la fédération XMPP vers EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f383f-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="f383f-239">Vérifiez que le pool Edge qui va héberger la fédération XMPP a port 5269 open en externe.</span><span class="sxs-lookup"><span data-stu-id="f383f-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="f383f-240">Si les pools frontaux est resté en cours d’exécution dans le site contenant le pool Edge qui a échoué et a été restauré, vous devez mettre à jour le Service de conférence Web et A / V Conferencing Service sur ces Front-End pools à utiliser à nouveau les pools de serveurs Edge sur leur site local.</span><span class="sxs-lookup"><span data-stu-id="f383f-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="f383f-241">Si le pool frontal sur le même site en tant que le pool Edge a échoué échoue également, vous pouvez maintenant utiliser Invoke – CsPoolFailback pour basculer le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="f383f-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="f383f-242">Changer le pool Edge associé à un pool frontal</span><span class="sxs-lookup"><span data-stu-id="f383f-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="f383f-243">Si un pool Edge tombe en panne mais le pool frontal sur le même site est en cours d’exécution, vous devez définir le pool frontal à utiliser un pool de serveurs Edge à un autre site jusqu'à ce que le pool Edge ayant échoué est restauré.</span><span class="sxs-lookup"><span data-stu-id="f383f-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="f383f-244">Dans le Générateur de topologie, accédez au nom du pool frontal que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="f383f-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="f383f-245">Avec le bouton droit de la liste, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f383f-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="f383f-246">Dans la section **Associations** , sous **Associer un Pool Edge (pour les composants médias)**, utilisez la liste déroulante pour sélectionner le pool Edge que vous souhaitez associer ce pool frontal avec.</span><span class="sxs-lookup"><span data-stu-id="f383f-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="f383f-247">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f383f-247">Click **OK**.</span></span>
