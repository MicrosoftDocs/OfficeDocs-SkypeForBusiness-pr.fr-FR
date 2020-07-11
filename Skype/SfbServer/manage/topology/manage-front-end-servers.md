---
title: Gérer les serveurs frontaux dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé : Découvrez comment ajouter, supprimer, corriger ou mettre à jour des serveurs frontaux dans Skype entreprise Server.'
ms.openlocfilehash: 3d2298711e707ed897b26939fd383dbedcfb3957
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098412"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="cc44b-103">Gérer les serveurs frontaux dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cc44b-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="cc44b-104">Cet article explique comment ajouter ou supprimer des serveurs frontaux et comment appliquer des mises à niveau ou des correctifs sur des serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="cc44b-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="cc44b-105">Skype entreprise Server 2019 ne prend pas en charge les pools frontaux Enterprise Edition avec deux serveurs frontaux et n’autorise pas la publication de la topologie dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="cc44b-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="cc44b-106">Ajouter ou supprimer des serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="cc44b-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="cc44b-107">Lorsque vous ajoutez un serveur frontal à un pool, ou que vous supprimez un serveur frontal d’un pool, vous devez redémarrer le pool.</span><span class="sxs-lookup"><span data-stu-id="cc44b-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="cc44b-108">Lorsque vous ajoutez ou supprimez un serveur dans le pool de votre topologie, puis que vous publiez la topologie mise à jour, tous les serveurs du pool sont redémarrés en même temps.</span><span class="sxs-lookup"><span data-stu-id="cc44b-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="cc44b-109">Pendant que les serveurs redémarrent, le pool est hors connexion, ce qui interrompt le service pour les utilisateurs connectés à ce pool.</span><span class="sxs-lookup"><span data-stu-id="cc44b-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="cc44b-110">Pour empêcher toute interruption de service pour les utilisateurs, envisagez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures d’ouverture.</span><span class="sxs-lookup"><span data-stu-id="cc44b-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="cc44b-111">Vous pouvez utiliser la procédure suivante lors de l’ajout ou de la suppression d’un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="cc44b-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc44b-112">Si vous ajoutez de nouveaux serveurs au pool, mettez à jour vos nouveaux serveurs de pool de sorte qu’ils se trouvent au même niveau de mise à jour cumulative que les serveurs existants dans le pool.</span><span class="sxs-lookup"><span data-stu-id="cc44b-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="cc44b-113">Pour ajouter ou supprimer des serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="cc44b-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="cc44b-114">If you are removing any Front End Servers, first stop new connections to those servers.</span><span class="sxs-lookup"><span data-stu-id="cc44b-114">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="cc44b-115">To do so, you can use the following cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cc44b-115">To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="cc44b-116">Ouvrez le Générateur de topologie, puis ajoutez ou supprimez les serveurs nécessaires.</span><span class="sxs-lookup"><span data-stu-id="cc44b-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="cc44b-117">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="cc44b-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cc44b-118">Lorsque vous ajoutez ou supprimez un serveur dans le pool de votre topologie, puis que vous publiez la topologie mise à jour, tous les serveurs du pool sont redémarrés en même temps.</span><span class="sxs-lookup"><span data-stu-id="cc44b-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="cc44b-119">Pendant que les serveurs redémarrent, le pool est hors connexion, ce qui interrompt le service pour les utilisateurs connectés à ce pool.</span><span class="sxs-lookup"><span data-stu-id="cc44b-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="cc44b-120">Pour empêcher toute interruption de service pour les utilisateurs, envisagez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures d’ouverture.</span><span class="sxs-lookup"><span data-stu-id="cc44b-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="cc44b-121">De plus, lorsque vous ajoutez ou supprimez un serveur dans le pool, vous devez exécuter l’Assistant Déploiement de Skype entreprise Server sur chaque ordinateur ajouté ou supprimé, pour plus d’informations, reportez-vous à la rubrique [installation de Skype entreprise Server sur des serveurs dans la topologie](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) .</span><span class="sxs-lookup"><span data-stu-id="cc44b-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="cc44b-122">Si vous avez modifié le nombre de serveurs dans votre pool frontal de l’une des manières suivantes, réinitialisez le pool en tapant l’applet de commande suivante : Reset-CsPoolRegistrarState-ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="cc44b-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="cc44b-123">2 à n’importe quel</span><span class="sxs-lookup"><span data-stu-id="cc44b-123">2 to any</span></span>
    
     - <span data-ttu-id="cc44b-124">Any à 2</span><span class="sxs-lookup"><span data-stu-id="cc44b-124">Any to 2</span></span>
    
     - <span data-ttu-id="cc44b-125">3 à n’importe quel</span><span class="sxs-lookup"><span data-stu-id="cc44b-125">3 to any</span></span>
    
     - <span data-ttu-id="cc44b-126">Any à 3</span><span class="sxs-lookup"><span data-stu-id="cc44b-126">Any to 3</span></span>
    
5. <span data-ttu-id="cc44b-127">Redémarrez le pool en tapant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="cc44b-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="cc44b-128">Correctif ou mise à jour des serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="cc44b-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="cc44b-129">Lorsque vous appliquez un correctif aux serveurs d’un pool frontal, vous pouvez le faire sur un serveur à la fois.</span><span class="sxs-lookup"><span data-stu-id="cc44b-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="cc44b-130">Pour appliquer une mise à niveau sur les serveurs frontaux dans un pool</span><span class="sxs-lookup"><span data-stu-id="cc44b-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="cc44b-131">Tapez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="cc44b-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="cc44b-132">Si cette applet de commande affiche des réplicas manquants, exécutez l’applet de commande suivante pour récupérer le pool avant d’appliquer les correctifs.</span><span class="sxs-lookup"><span data-stu-id="cc44b-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="cc44b-133">Sur le premier serveur auquel vous souhaitez appliquer un correctif, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="cc44b-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="cc44b-134">Cette applet de commande déplace tous les services vers d’autres serveurs frontaux dans le pool et met ce serveur hors connexion.</span><span class="sxs-lookup"><span data-stu-id="cc44b-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="cc44b-135">Appliquez la mise à niveau ou le correctif à ce serveur.</span><span class="sxs-lookup"><span data-stu-id="cc44b-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="cc44b-136">Sur le serveur mis à niveau, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="cc44b-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="cc44b-137">Le serveur est renvoyé au service.</span><span class="sxs-lookup"><span data-stu-id="cc44b-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="cc44b-138">Répétez les étapes 2-4 pour chaque serveur qui doit être mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="cc44b-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
