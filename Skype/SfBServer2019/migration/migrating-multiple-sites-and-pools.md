---
title: Migration de plusieurs sites et pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype entreprise Server 2019 prend en charge les déploiements multisites et multi-pool. Le processus de migration de plusieurs regroupements vers Skype entreprise Server 2019 doit prendre en compte les points suivants :'
ms.openlocfilehash: d1257590c431bc15aad4db03908aa6d95fd5fce3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813442"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="d15cb-104">Migration de plusieurs sites et pools</span><span class="sxs-lookup"><span data-stu-id="d15cb-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="d15cb-105">Skype entreprise Server 2019 prend en charge les déploiements multisites et multi-pool.</span><span class="sxs-lookup"><span data-stu-id="d15cb-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="d15cb-106">Le processus de migration de plusieurs regroupements vers Skype entreprise Server 2019 doit prendre en compte les points suivants :</span><span class="sxs-lookup"><span data-stu-id="d15cb-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="d15cb-107">Après le déploiement d’un pool de pilotes de 2019 Skype entreprise Server, vous devez définir un sous-ensemble d’utilisateurs pilote qui seront déplacés vers le pool Skype entreprise Server 2019 et une méthodologie pour la validation de la fonctionnalité des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d15cb-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="d15cb-108">Par exemple, après le déplacement d’un utilisateur vers le pool de pilotes, vérifiez que la stratégie de conférence de l’utilisateur a été déplacée vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d15cb-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="d15cb-109">Après le déploiement d’un serveur de périphérie dans le pool de pilotes, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d15cb-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="d15cb-110">Les fonctionnalités de conversation permanente, de mise en miroir SQL et de fonction XMPP sont déconseillées dans Skype entreprise Server 2019 et ne sont plus disponibles en tant que fonctionnalités de l’API Skype entreprise Server 2019, mais elles peuvent être maintenues dans un environnement de coexistence le cas échéant. environnement hérité.</span><span class="sxs-lookup"><span data-stu-id="d15cb-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="d15cb-111">Si vous souhaitez continuer à utiliser ces fonctionnalités, vous devez planifier la poursuite d’un environnement de coexistence pour lequel certains utilisateurs resteront dans les pools hérités.</span><span class="sxs-lookup"><span data-stu-id="d15cb-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="d15cb-112">Après avoir basculé les serveurs Edge des itinéraires fédérés vers les serveurs de frontière Skype entreprise Server 2019, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le pool 2019 du serveur Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d15cb-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="d15cb-113">Après avoir déplacé tous les utilisateurs et les objets de contact non-utilisateur, vous devez vérifier que le pool hérité est vide.</span><span class="sxs-lookup"><span data-stu-id="d15cb-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="d15cb-114">Après avoir vérifié que le pool hérité est vide, vous pouvez désactiver le pool.</span><span class="sxs-lookup"><span data-stu-id="d15cb-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="d15cb-115">Pour plus d’informations sur la façon de désactiver le pool hérité et les serveurs, voir [phase 8 : déclasser les pools hérités](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="d15cb-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

