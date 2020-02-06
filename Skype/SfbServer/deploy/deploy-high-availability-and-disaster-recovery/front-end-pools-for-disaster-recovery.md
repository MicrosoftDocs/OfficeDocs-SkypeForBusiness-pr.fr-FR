---
title: Déploiement de pools frontaux couplés pour une reprise après sinistre dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Vous pouvez décider d'utiliser des pools frontaux couplés pour assurer une protection en cas de récupération d’urgence, bien que ceci ne soit pas nécessaire.
ms.openlocfilehash: 63b9c55aad2b31e01eec506ce28e54d2145ee636
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790082"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="7661c-103">Déploiement de pools frontaux couplés pour une reprise après sinistre dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7661c-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="7661c-104">Vous pouvez décider d'utiliser des pools frontaux couplés pour assurer une protection en cas de récupération d’urgence, bien que ceci ne soit pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="7661c-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="7661c-105">Vous pouvez facilement déployer la topologie de reprise après sinistre des pools front-end couplés à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="7661c-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="7661c-106">Pour déployer une paire de pools de serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="7661c-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="7661c-107">Si les pools sont nouveaux et ne sont pas encore définis, utilisez le générateur de topologie pour créer les pools.</span><span class="sxs-lookup"><span data-stu-id="7661c-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="7661c-108">Dans le générateur de topologie, cliquez avec le bouton droit sur l’un des deux pools, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7661c-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="7661c-109">Cliquez sur **Résistance** dans le volet gauche, puis sélectionnez **Pool de stockage associé** dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="7661c-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="7661c-p101">Dans la zone située en dessous de **Pool de stockage associé**, sélectionnez le pool que vous voulez jumeler à celui-ci. Seuls les pools existants qui ne sont pas déjà jumelés avec un autre pool peuvent être choisis.</span><span class="sxs-lookup"><span data-stu-id="7661c-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="7661c-112">Sélectionnez **Basculement et restauration automatiques pour Voice**, puis cliquez sur \*\*OK \*\*.</span><span class="sxs-lookup"><span data-stu-id="7661c-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="7661c-113">Quand vous affichez les détails de ce pool, le pool associé s’affiche dans le volet droit sous **Résistance**. </span><span class="sxs-lookup"><span data-stu-id="7661c-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="7661c-114">Utilisez le générateur de topologie pour publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="7661c-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="7661c-115">Si les deux pools n’étaient pas déjà déployés, déployez-les maintenant pour terminer la configuration.</span><span class="sxs-lookup"><span data-stu-id="7661c-115">If the two pools were not yet deployed, deploy them now and the configuration will be complete.</span></span> <span data-ttu-id="7661c-116">Vous pouvez ignorer les étapes finales de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="7661c-116">You can skip the final steps in this procedure.</span></span>
    
    <span data-ttu-id="7661c-117">Toutefois, si les pools ont déjà été déployés avant de définir la relation couplée, vous devez effectuer les étapes finales suivantes.</span><span class="sxs-lookup"><span data-stu-id="7661c-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following final steps.</span></span>
    
8. <span data-ttu-id="7661c-118">Sur chaque serveur frontal des deux pools, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7661c-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="7661c-119">Cela permet de configurer les autres services requis pour un fonctionnement correct du jumelage de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7661c-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="7661c-120">Une fois que le programme d’amorçage a terminé l’installation des composants requis pour le jumelage des copies de sauvegarde sur chaque serveur frontal dans les deux pools, veillez à réappliquer toute mise à jour cumulative déjà appliquée sur ces serveurs frontaux dans les deux pools, puis continuez. à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="7661c-120">Once Bootstrapper finishes installing the required components for backup pairing on every Front end Server in both pools, please be sure to re-apply any existing Cumulative Update that was previously applied on these Front End Servers in both pools and then continue with the next step.</span></span>

10. <span data-ttu-id="7661c-121">À partir d’une invite de commandes de Skype entreprise Server Management Shell, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7661c-121">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. <span data-ttu-id="7661c-122">Forcez la synchronisation de l’utilisateur et des données de conférences de ces deux groupes avec les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="7661c-122">Force the user and conference data of both pools to be synchronized with each other with the following cmdlets:</span></span>
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="7661c-p103">La synchronisation des données peut durer un certain temps. Vous pouvez utiliser les applets de commande suivantes pour vérifier l’état. Assurez-vous que l’état de synchronisation dans les deux sens est stable.</span><span class="sxs-lookup"><span data-stu-id="7661c-p103">Synchronizing the data may take some time. You can use the following cmdlets to check the status. Make sure that the status in both directions is in steady state.</span></span>
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="7661c-126">L’option **reprise automatique et retour automatique pour les appels vocaux** et les intervalles de temps associés dans le générateur de topologie ne s’appliquent qu’aux fonctionnalités de résilience vocale introduites dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7661c-126">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="7661c-127">La sélection de cette option ne signifie pas que le basculement du pool mentionné dans ce document est automatique.</span><span class="sxs-lookup"><span data-stu-id="7661c-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="7661c-128">Le basculement et la restauration du pool requiert l’intervention manuelle d’un administrateur pour appeler respectivement les applets de commande de basculement et de restauration.</span><span class="sxs-lookup"><span data-stu-id="7661c-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7661c-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7661c-129">See also</span></span>

[<span data-ttu-id="7661c-130">Reprise après sinistre de la liste frontale dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7661c-130">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
