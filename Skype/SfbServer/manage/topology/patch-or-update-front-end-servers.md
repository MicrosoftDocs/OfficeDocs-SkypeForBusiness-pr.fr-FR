---
title: Correctifs ou mise à jour des serveurs frontaux Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Résumé : Découvrez comment appliquer des mises à jour ou correctifs aux serveurs frontaux Skype pour Business Server.'
ms.openlocfilehash: 29191192b1dab16b79cc594cc0a7b3b68aaa906f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20972771"
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="ca3be-103">Correctifs ou mise à jour des serveurs frontaux Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="ca3be-103">Patch or update Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="ca3be-104">**Résumé :** Apprenez comment appliquer les correctifs et mises à niveau pour les serveurs frontaux Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="ca3be-104">**Summary:** learn how to apply upgrades or patches to Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="ca3be-105">Lorsque vous appliquez le correctif les serveurs dans un pool frontal, procéder à un serveur à la fois.</span><span class="sxs-lookup"><span data-stu-id="ca3be-105">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="ca3be-106">Pour appliquer une mise à niveau aux serveurs frontaux d’un pool</span><span class="sxs-lookup"><span data-stu-id="ca3be-106">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="ca3be-107">Tapez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ca3be-107">Type the following cmdlet:</span></span>
    
  ```
  Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
  ```

     <span data-ttu-id="ca3be-108">si cet applet indique qu’il manque des réplicas, exécutez l’applet de commande suivant pour récupérer le pool avant d’appliquer des correctifs.</span><span class="sxs-lookup"><span data-stu-id="ca3be-108">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
  ```
  Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
  ```

2. <span data-ttu-id="ca3be-109">Sur le premier serveur à « corriger », exécutez l’applet de commande suivant :</span><span class="sxs-lookup"><span data-stu-id="ca3be-109">On the first server you want to patch, run the following cmdlet:</span></span>
    
  ```
  Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
  ```

    <span data-ttu-id="ca3be-110">Cette applet de commande déplace tous les services à d’autres serveurs frontaux du pool et déconnecte ce serveur.</span><span class="sxs-lookup"><span data-stu-id="ca3be-110">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="ca3be-111">Appliquez la mise à niveau ou le correctif à ce serveur.</span><span class="sxs-lookup"><span data-stu-id="ca3be-111">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="ca3be-112">Sur le serveur mis à niveau, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ca3be-112">On the upgraded server, run the following cmdlet:</span></span>
    
  ```
  Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
  ```

    <span data-ttu-id="ca3be-113">Le serveur reprend le service.</span><span class="sxs-lookup"><span data-stu-id="ca3be-113">The server is returned to service.</span></span>
    
5. <span data-ttu-id="ca3be-114">Répétez les étapes 2 à 4 pour chaque serveur à mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="ca3be-114">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    

