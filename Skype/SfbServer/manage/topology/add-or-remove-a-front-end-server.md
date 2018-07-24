---
title: Ajouter ou supprimer un serveur frontal dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé : Découvrez comment ajouter ou supprimer des serveurs frontaux dans Skype pour Business Server.'
ms.openlocfilehash: 07f23f3dfb913a353a72ac855915d4001ed02f24
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21018782"
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server"></a><span data-ttu-id="c46df-103">Ajouter ou supprimer un serveur frontal dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="c46df-103">Add or remove a Front End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="c46df-104">**Résumé :** Découvrez comment ajouter ou supprimer des serveurs frontaux dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="c46df-104">**Summary:** Learn how to add or remove Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="c46df-105">Lorsque vous ajoutez un serveur frontal à un pool, ou supprimez un serveur frontal d’un pool, vous devez redémarrer le pool.</span><span class="sxs-lookup"><span data-stu-id="c46df-105">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c46df-p101">Lorsque vous ajoutez ou que vous supprimez un serveur d’un pool dans votre topologie, puis publiez la topologie mise à jour, cela entraîne le redémarrage de tous les serveurs du pool au même moment. Pendant que les serveurs redémarrent, le pool est hors-ligne, ce qui interrompt le service pour les utilisateurs connectés à ce pool. Pour éviter toute interruption de service, prévoyez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures de bureau.</span><span class="sxs-lookup"><span data-stu-id="c46df-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="c46df-109">Vous pouvez utiliser la procédure suivante lors de l’ajout ou suppression d’un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c46df-109">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c46df-110">Si vous ajoutez des serveurs au pool, mettez à jour vos nouveaux serveurs du pool pour qu’ils se trouvent au même niveau de mise à jour cumulée que les serveurs existants du pool.</span><span class="sxs-lookup"><span data-stu-id="c46df-110">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="c46df-111">Pour ajouter ou supprimer des serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="c46df-111">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="c46df-112">Si vous supprimez les serveurs frontaux, arrêtez tout d’abord nouvelles connexions à ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="c46df-112">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="c46df-113">Pour ce faire, vous pouvez utiliser l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c46df-113">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="c46df-114">Ouvrez le Générateur de topologie et comment ajouter ou supprimer les serveurs nécessaires.</span><span class="sxs-lookup"><span data-stu-id="c46df-114">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="c46df-115">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="c46df-115">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c46df-p103">Lorsque vous ajoutez ou que vous supprimez un serveur d’un pool dans votre topologie, puis publiez la topologie mise à jour, cela entraîne le redémarrage de tous les serveurs du pool au même moment. Pendant que les serveurs redémarrent, le pool est hors-ligne, ce qui interrompt le service pour les utilisateurs connectés à ce pool. Pour éviter toute interruption de service, prévoyez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures de bureau.</span><span class="sxs-lookup"><span data-stu-id="c46df-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
4. <span data-ttu-id="c46df-119">Si vous avez modifié le nombre de serveurs dans votre pool frontal dans une des manières suivantes, puis réinitialisez le pool avec en tapant l’applet de commande suivante : Reset-cspoolregistrarstate ne - ResetType FullReset - PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="c46df-119">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="c46df-120">2 à quelconque</span><span class="sxs-lookup"><span data-stu-id="c46df-120">2 to any</span></span>
    
     - <span data-ttu-id="c46df-121">Quelconque à 2</span><span class="sxs-lookup"><span data-stu-id="c46df-121">Any to 2</span></span>
    
     - <span data-ttu-id="c46df-122">3 à quelconque</span><span class="sxs-lookup"><span data-stu-id="c46df-122">3 to any</span></span>
    
     - <span data-ttu-id="c46df-123">Quelconque à 3</span><span class="sxs-lookup"><span data-stu-id="c46df-123">Any to 3</span></span>
    
5. <span data-ttu-id="c46df-124">Redémarrez le pool en tapant l’applet de commande suivante</span><span class="sxs-lookup"><span data-stu-id="c46df-124">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```