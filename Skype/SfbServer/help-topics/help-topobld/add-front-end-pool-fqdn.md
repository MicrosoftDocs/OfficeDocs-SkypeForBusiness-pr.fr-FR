---
title: Ajouter le nom de domaine complet du pool frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous êtes en train de créer. Vous ne pouvez pas modifier le nom de domaine complet d’un pool après avoir publié la topologie contenant le pool frontal. Si vous devez renommer un pool, vous devez le supprimer puis en ajouter un nouveau avec le nouveau nom de domaine complet.
ms.openlocfilehash: 99bf31760ce908952547ccfb3f150c136966e9f0
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218855"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="d87b3-105">Ajouter le nom de domaine complet du pool frontal</span><span class="sxs-lookup"><span data-stu-id="d87b3-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="d87b3-p102">Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous êtes en train de créer. Vous ne pouvez pas modifier le nom de domaine complet d’un pool après avoir publié la topologie contenant le pool frontal. Si vous devez renommer un pool, vous devez le supprimer puis en ajouter un nouveau avec le nouveau nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="d87b3-p102">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating. You cannot change the FQDN of a pool after you publish the topology containing the Front End pool. If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="d87b3-109">Si vous envisagez d’implémenter un pool frontal par la suite, sélectionnez **Pool de plusieurs ordinateurs**.</span><span class="sxs-lookup"><span data-stu-id="d87b3-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="d87b3-110">Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec charge équilibrée, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique.</span><span class="sxs-lookup"><span data-stu-id="d87b3-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="d87b3-111">Lorsque vous êtes prêt à ajouter d’autres ordinateurs au pool ultérieurement, vous devez réexécuter le générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du pool frontal par le biais de l’Assistant Déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d87b3-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="d87b3-112">Vous devez également ajouter le nouveau membre du pool aux équilibreurs de la charge pour le pool, à l’équilibrage de la charge DNS ou aux équilibreurs de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="d87b3-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="d87b3-113">Dans de nombreux cas, les deux systèmes d’équilibrage de la charge seront en place.</span><span class="sxs-lookup"><span data-stu-id="d87b3-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="d87b3-114">Veillez à ajouter le nouveau membre aux deux systèmes.</span><span class="sxs-lookup"><span data-stu-id="d87b3-114">Be sure that you are adding the new member server to both.</span></span> 
  

