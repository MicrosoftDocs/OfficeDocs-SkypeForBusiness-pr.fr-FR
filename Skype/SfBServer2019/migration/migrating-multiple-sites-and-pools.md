---
title: Migration de plusieurs sites et pools
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype pour Business Server 2019 prend en charge les déploiements sur plusieurs sites et multi-pool. Le processus de migration de plusieurs pools à Skype pour Business Server 2019 nécessite les considérations suivantes :'
ms.openlocfilehash: ecd7e795c7cde9265f26c9c7533fcfd6ec87d684
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293547"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="198a0-104">Migration de plusieurs sites et pools</span><span class="sxs-lookup"><span data-stu-id="198a0-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="198a0-105">Skype pour Business Server 2019 prend en charge les déploiements sur plusieurs sites et multi-pool.</span><span class="sxs-lookup"><span data-stu-id="198a0-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="198a0-106">Le processus de migration de plusieurs pools à Skype pour Business Server 2019 nécessite les considérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="198a0-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="198a0-107">Après avoir déployé un Skype pour Business Server 2019 le pool pilote, vous devez définir un sous-ensemble d’utilisateurs qui seront déplacées vers le Skype pour Business Server 2019 pool et une méthode pour valider le fonctionnement des utilisateurs du pilote.</span><span class="sxs-lookup"><span data-stu-id="198a0-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="198a0-108">Par exemple, après le déplacement d’un utilisateur vers le pool pilote, vérifiez que la stratégie de conférence de l’utilisateur a déplacé à Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="198a0-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="198a0-109">Après avoir déployé un serveur de périphérie dans le pool pilote, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="198a0-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="198a0-110">Conversation permanente, la mise en miroir SQL et la fonctionnalité XMPP sont déconseillées dans Skype pour Business Server 2019 et n’est plus disponible en tant que Skype pour les fonctionnalités de Business Server 2019, mais peut être poursuivis dans un environnement de coexistence si elles ont été précédemment déployés dans un environnement hérité.</span><span class="sxs-lookup"><span data-stu-id="198a0-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="198a0-111">Si vous souhaitez continuer à utiliser ces fonctionnalités, vous devez planifier poursuivre un environnement de coexistence où certains utilisateurs restent dans les pools hérités.</span><span class="sxs-lookup"><span data-stu-id="198a0-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="198a0-112">Après la transition des serveurs des itinéraires fédérés de périphérie pour le pilote Skype pour les serveurs de périphérie 2019 Business Server, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="198a0-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="198a0-113">Après avoir déplacé tous les utilisateurs et les objets contact non-utilisateur, vous devez vérifier que le pool hérité est vide.</span><span class="sxs-lookup"><span data-stu-id="198a0-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="198a0-114">Après avoir vérifié que le pool hérité est vide, vous pouvez le désactiver le pool.</span><span class="sxs-lookup"><span data-stu-id="198a0-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="198a0-115">Pour plus d’informations sur la façon de désactiver le pool hérité hérité et les serveurs, voir [Phase 8 : mettre hors service les pools hérités](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="198a0-115">For details about how to deactivate the legacy legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

