---
title: Déployer des pools frontux couplés pour la récupération d’urgence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Vous pouvez décider d’utiliser des pools frontux couplés pour fournir une protection contre la récupération d’urgence, mais cela n’est pas obligatoire.
ms.openlocfilehash: 7d066de60bf3ab98d73d8aeee08044803fad983c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830604"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="99a57-103">Déployer des pools frontux couplés pour la récupération d’urgence dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="99a57-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="99a57-104">Vous pouvez décider d’utiliser des pools frontux couplés pour fournir une protection contre la récupération d’urgence, mais cela n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="99a57-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="99a57-105">Vous pouvez facilement déployer la topologie de récupération d’urgence des pools frontux couplés à l’aide du Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="99a57-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="99a57-106">Pour déployer une paire de pools de serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="99a57-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="99a57-107">Si les pools sont nouveaux et pas encore définis, utilisez le Générateur de topologie pour créer les pools.</span><span class="sxs-lookup"><span data-stu-id="99a57-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="99a57-108">Dans le Générateur de topologie, cliquez avec le bouton droit sur l’un des deux pools, puis cliquez **sur Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="99a57-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="99a57-109">Cliquez sur **Résistance** dans le volet gauche, puis sélectionnez **Pool de stockage associé** dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="99a57-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="99a57-p101">Dans la zone située en dessous de **Pool de stockage associé**, sélectionnez le pool que vous voulez jumeler à celui-ci. Seuls les pools existants qui ne sont pas déjà jumelés avec un autre pool peuvent être choisis.</span><span class="sxs-lookup"><span data-stu-id="99a57-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="99a57-112">Sélectionnez **Basculement et restauration automatiques pour Voice**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="99a57-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="99a57-113">Quand vous affichez les détails de ce pool, le pool associé apparaît dans le volet droit sous **Résistance**.</span><span class="sxs-lookup"><span data-stu-id="99a57-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="99a57-114">Utilisez le Générateur de topologie pour publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="99a57-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="99a57-115">Si les deux pools n’étaient pas déjà déployés, déployez-les maintenant pour terminer la configuration.</span><span class="sxs-lookup"><span data-stu-id="99a57-115">If the two pools were not yet deployed, deploy them now and the configuration will be complete.</span></span> <span data-ttu-id="99a57-116">Vous pouvez ignorer les dernières étapes de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="99a57-116">You can skip the final steps in this procedure.</span></span>
    
    <span data-ttu-id="99a57-117">Toutefois, si les pools ont déjà été déployés avant de définir la relation couplée, vous devez effectuer les étapes finales suivantes.</span><span class="sxs-lookup"><span data-stu-id="99a57-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following final steps.</span></span>
    
8. <span data-ttu-id="99a57-118">Sur chaque serveur frontal des deux pools, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="99a57-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="99a57-119">Cela permet de configurer les autres services requis pour un fonctionnement correct du jumelage de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="99a57-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="99a57-120">Une fois que Bootstrapper a terminé l’installation des composants requis pour le jumelage de sauvegarde sur chaque serveur frontal des deux pools, n’oubliez pas de réappl attention à appliquer à nouveau toute mise à jour cumulative existante précédemment appliquée sur ces serveurs frontaux dans les deux pools, puis de poursuivre l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="99a57-120">Once Bootstrapper finishes installing the required components for backup pairing on every Front end Server in both pools, please be sure to re-apply any existing Cumulative Update that was previously applied on these Front End Servers in both pools and then continue with the next step.</span></span>

10. <span data-ttu-id="99a57-121">À partir d’une invite de commandes Skype Entreprise Server Management Shell, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="99a57-121">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. <span data-ttu-id="99a57-122">Forcez la synchronisation des données utilisateur et de conférence des deux pools avec les cmdlets suivantes :</span><span class="sxs-lookup"><span data-stu-id="99a57-122">Force the user and conference data of both pools to be synchronized with each other with the following cmdlets:</span></span>
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="99a57-123">La synchronisation des données peut durer un certain temps.</span><span class="sxs-lookup"><span data-stu-id="99a57-123">Synchronizing the data may take some time.</span></span> <span data-ttu-id="99a57-124">Vous pouvez utiliser les applets de commande suivantes pour vérifier l’état.</span><span class="sxs-lookup"><span data-stu-id="99a57-124">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="99a57-125">Assurez-vous que l’état dans les deux sens est stable.</span><span class="sxs-lookup"><span data-stu-id="99a57-125">Make sure that the status in both directions is in steady state.</span></span>
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="99a57-126">L’option De **failover et de failback** automatique pour Voice et les intervalles de temps associés dans le Générateur de topologie s’appliquent uniquement aux fonctionnalités de résistance vocale introduites dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99a57-126">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="99a57-127">La sélection de cette option ne signifie pas que le basculement du pool mentionné dans ce document est automatique.</span><span class="sxs-lookup"><span data-stu-id="99a57-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="99a57-128">Le basculement et la restauration du pool requiert l’intervention manuelle d’un administrateur pour appeler respectivement les applets de commande de basculement et de restauration.</span><span class="sxs-lookup"><span data-stu-id="99a57-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="99a57-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="99a57-129">See also</span></span>

[<span data-ttu-id="99a57-130">Récupération d’urgence du pool frontal dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="99a57-130">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
