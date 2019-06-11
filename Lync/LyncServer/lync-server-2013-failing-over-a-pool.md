---
title: 'Lync Server 2013 : Basculement vers un pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 512d7bc09d40d7b99cc66970cdd2a5584030fea9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="35bfc-102">Basculement vers un pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35bfc-102">Failing over a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35bfc-103">_**Dernière modification de la rubrique:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="35bfc-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="35bfc-104">Si un pool frontal unique a échoué et qu’il doit être basculé, utilisez la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="35bfc-104">If a single Front End pool has failed and needs to be failed over, use the following procedure.</span></span> <span data-ttu-id="35bfc-105">Dans cette procédure, Datacenter1 contient Pool1 et Pool1 a échoué.</span><span class="sxs-lookup"><span data-stu-id="35bfc-105">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="35bfc-106">Vous basculez vers Pool2 situé dans Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="35bfc-106">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="35bfc-107">La majeure partie du fonctionnement du basculement de pool implique un échec du magasin de gestion central, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="35bfc-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="35bfc-108">C’est important, car le magasin de gestion centralisée doit être opérationnel lorsque les utilisateurs du pool ont échoué.</span><span class="sxs-lookup"><span data-stu-id="35bfc-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="35bfc-109">De plus, si un pool frontal tombe en panne mais que le pool Edge sur ce site est toujours en cours d’exécution, vous devez savoir si le pool d’applications de périmètre utilise le pool en échec en tant que pool de prochains tronçons.</span><span class="sxs-lookup"><span data-stu-id="35bfc-109">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="35bfc-110">Si tel est le cas, vous devez modifier le pool Edge pour utiliser un autre pool frontal avant de basculer sur le pool frontal défectueux.</span><span class="sxs-lookup"><span data-stu-id="35bfc-110">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="35bfc-111">La façon dont vous modifiez le paramètre de saut suivant dépend de la façon dont le bord utilise un pool sur le même site que le pool de périphérie ou un site différent.</span><span class="sxs-lookup"><span data-stu-id="35bfc-111">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="35bfc-112">**Pour définir un pool de bords pour utiliser un pool de sauts suivant sur le même site**</span><span class="sxs-lookup"><span data-stu-id="35bfc-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="35bfc-113">Ouvrez le générateur de topologie, cliquez avec le bouton droit sur le pool de bords qui doit être modifié, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="35bfc-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="35bfc-114">Cliquez sur **tronçon suivant**.</span><span class="sxs-lookup"><span data-stu-id="35bfc-114">Click **Next Hop**.</span></span> <span data-ttu-id="35bfc-115">À partir de la liste **pool de prochains tronçons:** , sélectionnez le pool qui fera désormais Office de réserve de prochains tronçon.</span><span class="sxs-lookup"><span data-stu-id="35bfc-115">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="35bfc-116">Cliquez sur **OK**, puis publiez les modifications.</span><span class="sxs-lookup"><span data-stu-id="35bfc-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="35bfc-117">**Pour définir un pool de bords pour utiliser un pool de sauts suivant sur un autre site**</span><span class="sxs-lookup"><span data-stu-id="35bfc-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="35bfc-118">Ouvrez une fenêtre Lync Server Management Shell et tapez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="35bfc-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="35bfc-119">**Pour basculer sur un pool en cas de sinistre**</span><span class="sxs-lookup"><span data-stu-id="35bfc-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="35bfc-120">Recherchez quel pool est l’hôte du serveur de gestion central en tapant l’applet de commande suivante sur un serveur frontal dans Pool2:</span><span class="sxs-lookup"><span data-stu-id="35bfc-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="35bfc-121">Les résultats de cette applet de requête indiquent le pool qui héberge actuellement le serveur de gestion central.</span><span class="sxs-lookup"><span data-stu-id="35bfc-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="35bfc-122">Dans le reste de cette procédure, ce pool est appelé pool CMS\_.</span><span class="sxs-lookup"><span data-stu-id="35bfc-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="35bfc-123">Utilisez le générateur de topologie pour rechercher la version de Lync Server exécutée sur\_le pool CMS.</span><span class="sxs-lookup"><span data-stu-id="35bfc-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="35bfc-124">S’il exécute Lync Server 2013, utilisez l’applet de commande suivante pour trouver le pool de sauvegarde du pool 1.</span><span class="sxs-lookup"><span data-stu-id="35bfc-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="35bfc-125">Laissez le\_pool de sauvegarde être le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="35bfc-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="35bfc-126">Vérifiez l’état du magasin central de gestion avec l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="35bfc-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="35bfc-127">Cette applet de cmdlet doit indiquer que ActiveMasterFQDN et ActiveFileTransferAgents sont dirigés vers le nom\_de domaine complet du pool CMS.</span><span class="sxs-lookup"><span data-stu-id="35bfc-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="35bfc-128">S’il est vide, le serveur de gestion central n’est pas disponible et vous devez le basculer.</span><span class="sxs-lookup"><span data-stu-id="35bfc-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="35bfc-129">Si le magasin de gestion central n’est pas disponible ou si la Banque de gestion centrale s’exécutait sur Pool1 (autrement dit, le pool ayant échoué), vous devez faire basculer le serveur de gestion central avant de basculer sur le pool.</span><span class="sxs-lookup"><span data-stu-id="35bfc-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="35bfc-130">Si vous devez basculer sur le serveur de gestion central hébergé sur un pool exécutant Lync Server 2013, utilisez l’applet de demande à l’étape 5 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="35bfc-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="35bfc-131">Si vous devez basculer sur le serveur de gestion central hébergé sur un pool exécutant Lync Server 2010, utilisez l’applet de contrôle à l’étape 6 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="35bfc-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="35bfc-132">Si vous n’avez pas besoin de basculer sur le serveur de gestion central, passez à l’étape 7 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="35bfc-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="35bfc-133">Pour faire basculer le magasin de gestion central sur un pool exécutant Lync Server 2013, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="35bfc-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="35bfc-134">Tout d’abord, vérifiez quel serveur principal du\_pool de sauvegarde exécute l’instance principale du magasin central de gestion en entrant la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="35bfc-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="35bfc-135">Si le serveur principal principal du pool de\_sauvegarde est le principal, tapez:</span><span class="sxs-lookup"><span data-stu-id="35bfc-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="35bfc-136">Si le serveur principal miroir du pool de\_sauvegarde est le principal, tapez:</span><span class="sxs-lookup"><span data-stu-id="35bfc-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="35bfc-137">Vérifiez que le basculement du serveur central de gestion est terminé.</span><span class="sxs-lookup"><span data-stu-id="35bfc-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="35bfc-138">Tapez les informations suivantes:</span><span class="sxs-lookup"><span data-stu-id="35bfc-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="35bfc-139">Vérifiez que les ActiveMasterFQDN et ActiveFileTransferAgents pointent sur le nom de domaine\_complet (FQDN) du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="35bfc-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="35bfc-140">Enfin, vérifiez l’état de réplica de tous les serveurs front-end en entrant la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="35bfc-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="35bfc-141">Vérifiez que tous les réplicas ont la valeur true.</span><span class="sxs-lookup"><span data-stu-id="35bfc-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="35bfc-142">Passez à l’étape 7 de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="35bfc-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="35bfc-143">Installez le centre de gestion central sur le serveur principal du pool\_de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="35bfc-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="35bfc-144">Tout d’abord, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="35bfc-144">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="35bfc-145">Exécutez la commande suivante sur l’un des serveurs front-end du\_pool de sauvegarde pour forcer le déplacement du magasin de gestion central:</span><span class="sxs-lookup"><span data-stu-id="35bfc-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="35bfc-146">Valider le déplacement est terminé:</span><span class="sxs-lookup"><span data-stu-id="35bfc-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="35bfc-147">Vérifiez que les ActiveMasterFQDN et ActiveFileTransferAgents pointent sur le nom de domaine\_complet (FQDN) du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="35bfc-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="35bfc-148">Vérifiez l’état du réplica pour tous les serveurs frontaux en entrant la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="35bfc-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="35bfc-149">Vérifiez que tous les réplicas ont la valeur true.</span><span class="sxs-lookup"><span data-stu-id="35bfc-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="35bfc-150">Installez le service central de gestion sur le reste des serveurs frontaux dans le pool\_de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="35bfc-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="35bfc-151">Pour cela, exécutez la commande suivante sur tous les serveurs frontaux, à l’exception de celle que vous avez utilisée lorsque vous forcez le déplacement du magasin de gestion central plus haut dans cette procédure:</span><span class="sxs-lookup"><span data-stu-id="35bfc-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="35bfc-152">Basculez les utilisateurs de Pool1 à Pool2 en exécutant l’applet de commande suivante dans une fenêtre Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="35bfc-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="35bfc-153">Dans la mesure où les étapes décrites dans les parties précédentes de cette procédure permettent de vérifier que l’état du magasin de gestion central n’est pas universel, il est possible que cette applet de connexion échoue, car le magasin central de gestion n’a pas encore été complètement en échec.</span><span class="sxs-lookup"><span data-stu-id="35bfc-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="35bfc-154">Dans ce cas, vous devez résoudre le magasin de gestion central en fonction des messages d’erreur qui s’affichent, puis réexécuter cette cmdlet.</span><span class="sxs-lookup"><span data-stu-id="35bfc-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="35bfc-155">Si vous voyez le message d’erreur suivant, vous devez modifier le pool de périphérie sur ce site pour utiliser un autre pool comme tronçon suivant avant d’avoir basculé sur le pool.</span><span class="sxs-lookup"><span data-stu-id="35bfc-155">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="35bfc-156">Pour plus d’informations, reportez-vous aux procédures au début de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="35bfc-156">For details, see the procedures at the beginning of this topic.</span></span>
    
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

