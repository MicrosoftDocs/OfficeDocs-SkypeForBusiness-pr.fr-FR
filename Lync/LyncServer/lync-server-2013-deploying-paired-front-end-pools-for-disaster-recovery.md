---
title: 'Lync Server 2013 : déploiement de pools frontaux couplés pour la récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aec22b4d2b4f3049ed2a74cd413fbce0d2eb167
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="03eb5-102">Déploiement de pools frontaux couplés pour la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03eb5-102">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03eb5-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="03eb5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="03eb5-104">Vous pouvez facilement déployer la topologie de récupération d’urgence des pools frontaux couplés à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="03eb5-104">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span>

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="03eb5-105">Pour déployer une paire de pools de serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="03eb5-105">To deploy a pair of Front End pools</span></span>

1.  <span data-ttu-id="03eb5-106">Si les pools ne sont pas encore définis, utilisez le générateur de topologies pour créer les pools.</span><span class="sxs-lookup"><span data-stu-id="03eb5-106">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>

2.  <span data-ttu-id="03eb5-107">Dans le générateur de topologies, cliquez avec le bouton droit sur l’un des deux pools, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="03eb5-107">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="03eb5-108">Cliquez sur **Résistance** dans le volet gauche, puis sélectionnez **Pool de stockage associé** dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="03eb5-108">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>

4.  <span data-ttu-id="03eb5-p101">Dans la zone située en dessous de **Pool de stockage associé**, sélectionnez le pool que vous voulez jumeler à celui-ci. Seuls les pools existants qui ne sont pas déjà jumelés avec un autre pool peuvent être choisis.</span><span class="sxs-lookup"><span data-stu-id="03eb5-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
    <span data-ttu-id="03eb5-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span><span class="sxs-lookup"><span data-stu-id="03eb5-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span></span>  

5.  <span data-ttu-id="03eb5-112">Sélectionnez **Basculement et restauration automatiques pour Voice**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="03eb5-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="03eb5-113">Quand vous affichez les détails de ce pool, le pool associé apparaît dans le volet droit sous **Résistance**.</span><span class="sxs-lookup"><span data-stu-id="03eb5-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>

6.  <span data-ttu-id="03eb5-114">Utilisez le générateur de topologie pour publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="03eb5-114">Use Topology Builder to publish the topology.</span></span>

7.  <span data-ttu-id="03eb5-p102">Si les deux pools n’étaient pas déjà déployés, déployez-les maintenant pour terminer la configuration. Vous pouvez ignorer les deux dernières étapes de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="03eb5-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="03eb5-117">Toutefois, si les pools étaient déjà déployés avant de définir la relation de paire, vous devez procéder aux deux dernières étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="03eb5-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>

8.  <span data-ttu-id="03eb5-118">Sur chaque serveur frontal des deux pools, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="03eb5-118">On every Front End Server in both pools, run the following:</span></span>
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    <span data-ttu-id="03eb5-119">Cela permet de configurer les autres services requis pour un fonctionnement correct du jumelage de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="03eb5-119">This configures other services required for backup pairing to work correctly.</span></span>

9.  <span data-ttu-id="03eb5-120">À partir d’une invite de commandes Lync Server Management Shell, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="03eb5-120">From a Lync Server Management Shell command prompt, run the following:</span></span>
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. <span data-ttu-id="03eb5-121">Forcez la synchronisation des données d’utilisateur et de conférence entre les deux pools, à l’aide des applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="03eb5-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    <span data-ttu-id="03eb5-122">La synchronisation des données peut durer un certain temps.</span><span class="sxs-lookup"><span data-stu-id="03eb5-122">Synchronizing the data may take some time.</span></span> <span data-ttu-id="03eb5-123">Vous pouvez utiliser les applets de commande suivantes pour vérifier l’état.</span><span class="sxs-lookup"><span data-stu-id="03eb5-123">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="03eb5-124">Assurez-vous que l’État dans les deux directions est stable.</span><span class="sxs-lookup"><span data-stu-id="03eb5-124">Make sure that the status in both directions is in steady state.</span></span>
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> <span data-ttu-id="03eb5-125">L’option <STRONG>de basculement et de restauration automatiques pour Voice</STRONG> et les intervalles de temps associés dans le générateur de topologies s’appliquent uniquement aux fonctionnalités de résistance vocale introduites dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="03eb5-125">The <STRONG>Automatic failover and failback for Voice</STRONG> option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server 2010.</span></span> <span data-ttu-id="03eb5-126">La sélection de cette option ne signifie pas que le basculement du pool mentionné dans ce document est automatique.</span><span class="sxs-lookup"><span data-stu-id="03eb5-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="03eb5-127">Le basculement et la restauration du pool requiert l’intervention manuelle d’un administrateur pour appeler respectivement les applets de commande de basculement et de restauration.</span><span class="sxs-lookup"><span data-stu-id="03eb5-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

