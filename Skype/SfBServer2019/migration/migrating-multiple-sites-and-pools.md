---
title: Migration de plusieurs sites et pools
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype Entreprise Server 2019 prend en charge les déploiements sur plusieurs sites et plusieurs pool. Le processus de migration de plusieurs pools vers Skype Entreprise Server 2019 nécessite les considérations suivantes :'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752656"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="19810-104">Migration de plusieurs sites et pools</span><span class="sxs-lookup"><span data-stu-id="19810-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="19810-105">Skype Entreprise Server 2019 prend en charge les déploiements sur plusieurs sites et plusieurs pool.</span><span class="sxs-lookup"><span data-stu-id="19810-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="19810-106">Le processus de migration de plusieurs pools vers Skype Entreprise Server 2019 nécessite les considérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="19810-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="19810-107">Après avoir déployé un pool pilote Skype Entreprise Server 2019, vous devez définir un sous-ensemble d’utilisateurs pilotes qui seront déplacés vers le pool Skype Entreprise Server 2019 et une méthodologie pour valider les fonctionnalités des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="19810-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="19810-108">Par exemple, après avoir déplacé un utilisateur vers le pool pilote, vérifiez que la stratégie de conférence de l’utilisateur a été déplacée vers Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="19810-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="19810-109">Après avoir déployé un serveur Edge dans le pool pilote, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="19810-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="19810-110">Les fonctionnalités de conversation permanente, de mise en miroir SQL et XMPP sont désormais disponibles dans Skype Entreprise Server 2019 et ne sont plus disponibles en tant que fonctionnalités Skype Entreprise Server 2019, mais elles peuvent être poursuivies dans un environnement de coexistence si elles ont été précédemment déployées dans un environnement hérité.</span><span class="sxs-lookup"><span data-stu-id="19810-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="19810-111">Si vous souhaitez continuer à utiliser ces fonctionnalités, vous devez planifier de continuer avec un environnement de coexistence dans lequel certains utilisateurs resteront dans des pools hérités.</span><span class="sxs-lookup"><span data-stu-id="19810-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="19810-112">Après la transition des serveurs Edge des itinéraires fédérés vers les serveurs Edge Skype Entreprise Server 2019 pilotes, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="19810-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="19810-113">Après le déplacement de tous les utilisateurs et des objets contact non-utilisateur, vous devez vérifier que le pool hérité est vide.</span><span class="sxs-lookup"><span data-stu-id="19810-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="19810-114">Après avoir vérifié que le pool hérité est vide, vous pouvez le désactiver.</span><span class="sxs-lookup"><span data-stu-id="19810-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="19810-115">Pour plus d’informations sur la désactivation du pool et des serveurs hérités, voir Phase 8 : Désaffecter les [pools hérités.](phase-8-decommission-legacy-pools.md)</span><span class="sxs-lookup"><span data-stu-id="19810-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

