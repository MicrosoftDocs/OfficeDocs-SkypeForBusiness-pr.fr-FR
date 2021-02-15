---
title: Gérer les serveurs frontux dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé : Découvrez comment ajouter, supprimer, patcher ou mettre à jour des serveurs frontux dans Skype Entreprise Server.'
ms.openlocfilehash: 16af245b3c49b21309edd3ee2843f2585814ce9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826324"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="4b321-103">Gérer les serveurs frontux dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4b321-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="4b321-104">Cet article explique comment ajouter ou supprimer des serveurs frontaux et comment appliquer des mises à niveau ou des correctifs aux serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="4b321-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="4b321-105">Skype Entreprise Server 2019 ne prend pas en charge les pools frontux Enterprise Edition avec deux serveurs frontux et n’autorise pas la publication de la topologie dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="4b321-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="4b321-106">Ajouter ou supprimer des serveurs frontux</span><span class="sxs-lookup"><span data-stu-id="4b321-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="4b321-107">Lorsque vous ajoutez un serveur frontal à un pool, ou que vous supprimez un serveur frontal d’un pool, vous devez redémarrer le pool.</span><span class="sxs-lookup"><span data-stu-id="4b321-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4b321-108">Lorsque vous ajoutez ou supprimez un serveur au pool dans votre topologie, puis publiez la topologie mise à jour, tous les serveurs du pool redémarrent en même temps.</span><span class="sxs-lookup"><span data-stu-id="4b321-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="4b321-109">Pendant que les serveurs redémarrent le pool est hors connexion, ce qui interrompt le service pour vos utilisateurs connectés à ce pool.</span><span class="sxs-lookup"><span data-stu-id="4b321-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="4b321-110">Pour éviter toute interruption de service pour les utilisateurs, prévoyez de publier la topologie avec le nouveau serveur dans le pool en de nouvelles heures d’ouverture.</span><span class="sxs-lookup"><span data-stu-id="4b321-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="4b321-111">Vous pouvez utiliser la procédure suivante lors de l’ajout ou de la suppression d’un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="4b321-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4b321-112">Si vous ajoutez de nouveaux serveurs au pool, mettez à jour vos nouveaux serveurs de pool pour qu’ils soient au même niveau de mise à jour cumulative que les serveurs existants dans le pool.</span><span class="sxs-lookup"><span data-stu-id="4b321-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="4b321-113">Pour ajouter ou supprimer des serveurs frontux</span><span class="sxs-lookup"><span data-stu-id="4b321-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="4b321-p102">Si vous supprimez des serveurs frontaux, commencez par arrêter les nouvelles connexions à ces serveurs. Pour ce faire, vous pouvez utiliser l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4b321-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="4b321-116">Ouvrez le Générateur de topologie, puis ajoutez ou supprimez les serveurs nécessaires.</span><span class="sxs-lookup"><span data-stu-id="4b321-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="4b321-117">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="4b321-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4b321-118">Lorsque vous ajoutez ou supprimez un serveur au pool dans votre topologie, puis publiez la topologie mise à jour, tous les serveurs du pool redémarrent en même temps.</span><span class="sxs-lookup"><span data-stu-id="4b321-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="4b321-119">Pendant que les serveurs redémarrent le pool est hors connexion, ce qui interrompt le service pour vos utilisateurs connectés à ce pool.</span><span class="sxs-lookup"><span data-stu-id="4b321-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="4b321-120">Pour éviter toute interruption de service pour les utilisateurs, prévoyez de publier la topologie avec le nouveau serveur dans le pool en de nouvelles heures d’ouverture.</span><span class="sxs-lookup"><span data-stu-id="4b321-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="4b321-121">En outre, lorsque vous ajoutez ou supprimez un serveur dans le pool, vous devez exécuter l’Assistant Déploiement de Skype Entreprise Server sur chaque ordinateur ajouté ou supprimé. Pour plus d’informations, voir Installer Skype Entreprise Server sur les serveurs de la [topologie.](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="4b321-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="4b321-122">Si vous avez modifié le nombre de serveurs dans votre pool frontal de l’une des manières suivantes, réinitialisez-le en tapant l’applet de la cmdlet suivante : Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="4b321-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="4b321-123">2 à n’importe quel</span><span class="sxs-lookup"><span data-stu-id="4b321-123">2 to any</span></span>
    
     - <span data-ttu-id="4b321-124">De 2 à 2</span><span class="sxs-lookup"><span data-stu-id="4b321-124">Any to 2</span></span>
    
     - <span data-ttu-id="4b321-125">3 à n’importe quel</span><span class="sxs-lookup"><span data-stu-id="4b321-125">3 to any</span></span>
    
     - <span data-ttu-id="4b321-126">De 3 à 3</span><span class="sxs-lookup"><span data-stu-id="4b321-126">Any to 3</span></span>
    
5. <span data-ttu-id="4b321-127">Redémarrez le pool en tapant l’cmdlet suivante</span><span class="sxs-lookup"><span data-stu-id="4b321-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="4b321-128">Patch or update Front End Servers</span><span class="sxs-lookup"><span data-stu-id="4b321-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="4b321-129">Lorsque vous patchez les serveurs d’un pool frontal, vous le faites d’un serveur à la fois.</span><span class="sxs-lookup"><span data-stu-id="4b321-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="4b321-130">Pour appliquer une mise à niveau aux serveurs frontux d’un pool</span><span class="sxs-lookup"><span data-stu-id="4b321-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="4b321-131">Tapez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="4b321-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="4b321-132">Si cette cmdlet affiche des réplicas manquants, exécutez la cmdlet suivante pour récupérer le pool avant d’appliquer des correctifs.</span><span class="sxs-lookup"><span data-stu-id="4b321-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="4b321-133">Sur le premier serveur à mettre à jour, exécutez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="4b321-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="4b321-134">Cette applet de cmdlet déplace tous les services vers d’autres serveurs frontaux du pool et met ce serveur hors connexion.</span><span class="sxs-lookup"><span data-stu-id="4b321-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="4b321-135">Appliquez la mise à niveau ou le correctif à ce serveur.</span><span class="sxs-lookup"><span data-stu-id="4b321-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="4b321-136">Sur le serveur mis à niveau, exécutez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="4b321-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="4b321-137">Le serveur est remis en service.</span><span class="sxs-lookup"><span data-stu-id="4b321-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="4b321-138">Répétez les étapes 2 à 4 pour chaque serveur qui doit être mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="4b321-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
