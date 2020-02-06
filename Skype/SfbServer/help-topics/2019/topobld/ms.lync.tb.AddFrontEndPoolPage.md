---
title: Ajouter le nom de domaine complet du pool frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous êtes en train de créer. Vous ne pouvez pas modifier le nom de domaine complet d’un pool une fois que vous avez publié la topologie contenant le pool frontal. Si vous avez besoin de renommer un pool, vous devez supprimer le pool, puis ajouter un nouveau pool avec le nouveau nom de domaine complet (FQDN).
ms.openlocfilehash: 0c6fdf24ec19fe56ff86d4a5b43af2e48aedb3e2
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798521"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="f676d-105">Ajouter le nom de domaine complet du pool frontal</span><span class="sxs-lookup"><span data-stu-id="f676d-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="f676d-106">Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous êtes en train de créer.</span><span class="sxs-lookup"><span data-stu-id="f676d-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="f676d-107">Vous ne pouvez pas modifier le nom de domaine complet d’un pool une fois que vous avez publié la topologie contenant le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="f676d-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="f676d-108">Si vous avez besoin de renommer un pool, vous devez supprimer le pool, puis ajouter un nouveau pool avec le nouveau nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="f676d-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="f676d-109">Si vous envisagez d’implémenter un pool frontal à l’avenir, sélectionnez **pool d’ordinateurs multiples**.</span><span class="sxs-lookup"><span data-stu-id="f676d-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="f676d-110">Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec équilibrage de la charge, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique.</span><span class="sxs-lookup"><span data-stu-id="f676d-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="f676d-111">Lorsque vous êtes prêt à ajouter plus d’ordinateurs au pool par la suite, vous devez exécuter de nouveau le générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie et configurer le nouveau membre du pool frontal par le biais de l’Assistant Déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f676d-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="f676d-112">Vous devez également ajouter le nouveau membre de la liste aux équilibreurs de charge appropriés pour le pool, l’équilibrage de charge DNS (Domain Name System) ou les équilibreurs de charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="f676d-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="f676d-113">Dans de nombreux cas, les deux systèmes d’équilibrage de charge sont en place.</span><span class="sxs-lookup"><span data-stu-id="f676d-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="f676d-114">Assurez-vous d’ajouter le nouveau serveur membre aux deux.</span><span class="sxs-lookup"><span data-stu-id="f676d-114">Be sure that you are adding the new member server to both.</span></span> 
  

