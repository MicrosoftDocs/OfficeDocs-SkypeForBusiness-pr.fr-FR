---
title: Gérer les serveurs frontaux dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé : Apprenez à ajouter, supprimer, correctif ou mettre à jour des serveurs frontaux Skype pour Business Server.'
ms.openlocfilehash: bfd090ab007523ff05795aff012e4a01da4a0175
ms.sourcegitcommit: 70d3a3b162fdbca1cf2c2713d6bce54c3cbad3bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026180"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="018d0-103">Gérer les serveurs frontaux dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="018d0-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="018d0-104">Cet article explique comment ajouter ou supprimer des serveurs frontaux et comment appliquer les mises à jour ou correctifs aux serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="018d0-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="018d0-105">Ajouter ou supprimer des serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="018d0-105">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="018d0-106">Lorsque vous ajoutez un serveur frontal à un pool, ou supprimez un serveur frontal d’un pool, vous devez redémarrer le pool.</span><span class="sxs-lookup"><span data-stu-id="018d0-106">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="018d0-p101">Lorsque vous ajoutez ou que vous supprimez un serveur d’un pool dans votre topologie, puis publiez la topologie mise à jour, cela entraîne le redémarrage de tous les serveurs du pool au même moment. Pendant que les serveurs redémarrent, le pool est hors-ligne, ce qui interrompt le service pour les utilisateurs connectés à ce pool. Pour éviter toute interruption de service, prévoyez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures de bureau.</span><span class="sxs-lookup"><span data-stu-id="018d0-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="018d0-110">Vous pouvez utiliser la procédure suivante lors de l’ajout ou suppression d’un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="018d0-110">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="018d0-111">Si vous ajoutez des serveurs au pool, mettez à jour vos nouveaux serveurs du pool pour qu’ils se trouvent au même niveau de mise à jour cumulée que les serveurs existants du pool.</span><span class="sxs-lookup"><span data-stu-id="018d0-111">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="018d0-112">Pour ajouter ou supprimer des serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="018d0-112">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="018d0-113">Si vous supprimez les serveurs frontaux, arrêtez tout d’abord nouvelles connexions à ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="018d0-113">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="018d0-114">Pour ce faire, vous pouvez utiliser l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="018d0-114">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="018d0-115">Ouvrez le Générateur de topologie et comment ajouter ou supprimer les serveurs nécessaires.</span><span class="sxs-lookup"><span data-stu-id="018d0-115">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="018d0-116">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="018d0-116">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="018d0-p103">Lorsque vous ajoutez ou que vous supprimez un serveur d’un pool dans votre topologie, puis publiez la topologie mise à jour, cela entraîne le redémarrage de tous les serveurs du pool au même moment. Pendant que les serveurs redémarrent, le pool est hors-ligne, ce qui interrompt le service pour les utilisateurs connectés à ce pool. Pour éviter toute interruption de service, prévoyez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures de bureau.</span><span class="sxs-lookup"><span data-stu-id="018d0-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="018d0-120">En outre, lorsque vous ajoutez ou supprimez un serveur au pool, vous devez exécuter la Skype pour l’Assistant de déploiement Business Server sur chaque ordinateur ajouté ou supprimé, pour plus d’informations, voir [Installation de Skype pour Business Server sur les serveurs de la topologie](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="018d0-120">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="018d0-121">Si vous avez modifié le nombre de serveurs dans votre pool frontal dans une des manières suivantes, puis réinitialisez le pool avec en tapant l’applet de commande suivante : Reset-cspoolregistrarstate ne - ResetType FullReset - PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="018d0-121">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="018d0-122">2 à quelconque</span><span class="sxs-lookup"><span data-stu-id="018d0-122">2 to any</span></span>
    
     - <span data-ttu-id="018d0-123">Quelconque à 2</span><span class="sxs-lookup"><span data-stu-id="018d0-123">Any to 2</span></span>
    
     - <span data-ttu-id="018d0-124">3 à quelconque</span><span class="sxs-lookup"><span data-stu-id="018d0-124">3 to any</span></span>
    
     - <span data-ttu-id="018d0-125">Quelconque à 3</span><span class="sxs-lookup"><span data-stu-id="018d0-125">Any to 3</span></span>
    
5. <span data-ttu-id="018d0-126">Redémarrez le pool en tapant l’applet de commande suivante</span><span class="sxs-lookup"><span data-stu-id="018d0-126">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="018d0-127">Corriger ou mettre à jour des serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="018d0-127">Patch or update Front End Servers</span></span>

<span data-ttu-id="018d0-128">Lorsque vous appliquez le correctif les serveurs dans un pool frontal, procéder à un serveur à la fois.</span><span class="sxs-lookup"><span data-stu-id="018d0-128">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="018d0-129">Pour appliquer une mise à niveau aux serveurs frontaux d’un pool</span><span class="sxs-lookup"><span data-stu-id="018d0-129">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="018d0-130">Tapez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="018d0-130">Type the following cmdlet:</span></span>
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="018d0-131">si cet applet indique qu’il manque des réplicas, exécutez l’applet de commande suivant pour récupérer le pool avant d’appliquer des correctifs.</span><span class="sxs-lookup"><span data-stu-id="018d0-131">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="018d0-132">Sur le premier serveur à « corriger », exécutez l’applet de commande suivant :</span><span class="sxs-lookup"><span data-stu-id="018d0-132">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="018d0-133">Cette applet de commande déplace tous les services à d’autres serveurs frontaux du pool et déconnecte ce serveur.</span><span class="sxs-lookup"><span data-stu-id="018d0-133">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="018d0-134">Appliquez la mise à niveau ou le correctif à ce serveur.</span><span class="sxs-lookup"><span data-stu-id="018d0-134">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="018d0-135">Sur le serveur mis à niveau, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="018d0-135">On the upgraded server, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="018d0-136">Le serveur reprend le service.</span><span class="sxs-lookup"><span data-stu-id="018d0-136">The server is returned to service.</span></span>
    
5. <span data-ttu-id="018d0-137">Répétez les étapes 2 à 4 pour chaque serveur à mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="018d0-137">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
