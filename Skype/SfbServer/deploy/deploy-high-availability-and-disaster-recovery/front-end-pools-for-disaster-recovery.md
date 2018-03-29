---
title: Déployer des pools frontaux couplés pour la récupération d’urgence dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Vous pouvez décider d'utiliser des pools frontaux couplés pour assurer une protection en cas de récupération d’urgence, bien que ceci ne soit pas nécessaire.
ms.openlocfilehash: e13694c364908cfef70edafc1e7eb0484c5fe1bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server-2015"></a><span data-ttu-id="8ff5b-103">Déployer des pools frontaux couplés pour la récupération d’urgence dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="8ff5b-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8ff5b-104">Vous pouvez décider d'utiliser des pools frontaux couplés pour assurer une protection en cas de récupération d’urgence, bien que ceci ne soit pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="8ff5b-105">Vous pouvez facilement déployer la topologie de reprise après sinistre de paires pools Front-End à l’aide du Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="8ff5b-106">Pour déployer une paire de pools de serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="8ff5b-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="8ff5b-107">Si les pools sont nouvelles et non encore définie, utilisez le Générateur de topologies pour créer les pools.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="8ff5b-108">Dans le Générateur de topologies, cliquez droit sur un de ces deux groupes et puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="8ff5b-109">Cliquez sur **Résistance** dans le volet gauche, puis sélectionnez **Pool de stockage associé** dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="8ff5b-p101">Dans la zone située en dessous de **Pool de stockage associé**, sélectionnez le pool que vous voulez jumeler à celui-ci. Seuls les pools existants qui ne sont pas déjà jumelés avec un autre pool peuvent être choisis.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="8ff5b-112">Sélectionnez **Basculement et restauration automatiques pour Voice**, puis cliquez sur **OK **.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="8ff5b-113">Quand vous affichez les détails de ce pool, le pool associé s’affiche dans le volet droit sous **Résistance**. </span><span class="sxs-lookup"><span data-stu-id="8ff5b-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="8ff5b-114">Utilisez le Générateur de topologies pour publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="8ff5b-p102">Si les deux pools n’étaient pas déjà déployés, déployez-les maintenant pour terminer la configuration. Vous pouvez ignorer les deux dernières étapes de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="8ff5b-117">Cependant, si les pools étaient déjà déployés avant de définir la relation de paire, vous devez procéder aux deux dernières étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>
    
8. <span data-ttu-id="8ff5b-118">Sur chaque serveur frontal des deux pools, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8ff5b-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="8ff5b-119">Cela permet de configurer les autres services requis pour un fonctionnement correct du jumelage de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="8ff5b-120">À partir d’un Skype pour Business Server Management Shell invite de commandes, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8ff5b-120">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

10. <span data-ttu-id="8ff5b-121">Forcez la synchronisation des données d’utilisateur et de conférence entre les deux pools, à l’aide des applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="8ff5b-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
   ```
   Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
   ```

   ```
   Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
   ```

   <span data-ttu-id="8ff5b-p103">La synchronisation des données peut durer un certain temps. Vous pouvez utiliser les applets de commande suivantes pour vérifier l’état. Assurez-vous que l’état de synchronisation dans les deux sens est stable.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-p103">Synchronizing the data may take some time. You can use the following cmdlets to check the status. Make sure that the status in both directions is in steady state.</span></span>
    
   ```
   Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
   ```

   ```
   Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
   ```

> [!NOTE]
> <span data-ttu-id="8ff5b-125">L’option de **basculement automatique sur incident et retour arrière pour la voix** et les intervalles de temps associée dans le Générateur de topologie s’appliquent uniquement aux fonctionnalités de résilience vocale qui ont été introduites dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-125">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="8ff5b-126">La sélection de cette option ne signifie pas que le basculement du pool mentionné dans ce document est automatique.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="8ff5b-127">Le basculement et la restauration du pool requiert l’intervention manuelle d’un administrateur pour appeler respectivement les applets de commande de basculement et de restauration.</span><span class="sxs-lookup"><span data-stu-id="8ff5b-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8ff5b-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8ff5b-128">See also</span></span>

#### 

[<span data-ttu-id="8ff5b-129">Avant la reprise de pool fin dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8ff5b-129">Front End pool disaster recovery in Skype for Business Server 2015</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)

