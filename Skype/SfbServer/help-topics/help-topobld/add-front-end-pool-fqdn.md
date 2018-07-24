---
title: Ajouter un Pool frontal nom de domaine complet
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous créez. Vous ne pouvez pas modifier le nom de domaine complet d’un pool une fois que vous publiez la topologie contenant le pool frontal. Si vous avez besoin renommer un pool, vous devez supprimer le pool et puis ajoutez un nouveau pool avec le nouveau nom de domaine complet.
ms.openlocfilehash: 739a794b1b3fd8e88ae074b5c03f4c0e51fb844f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20981296"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="4cdd6-105">Ajouter un Pool frontal nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="4cdd6-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="4cdd6-106">Spécifiez le nom de domaine complet (FQDN) du pool frontal que vous créez.</span><span class="sxs-lookup"><span data-stu-id="4cdd6-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="4cdd6-107">Vous ne pouvez pas modifier le nom de domaine complet d’un pool une fois que vous publiez la topologie contenant le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="4cdd6-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="4cdd6-108">Si vous avez besoin renommer un pool, vous devez supprimer le pool et puis ajoutez un nouveau pool avec le nouveau nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="4cdd6-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="4cdd6-109">Si vous envisagez d’implémenter un pool frontal à l’avenir, sélectionnez **pool de plusieurs ordinateurs**.</span><span class="sxs-lookup"><span data-stu-id="4cdd6-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="4cdd6-110">Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec équilibrage de la charge, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique.</span><span class="sxs-lookup"><span data-stu-id="4cdd6-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="4cdd6-111">Lorsque vous êtes prêt à ajouter des ordinateurs au pool ultérieurement, vous devez exécuter le Générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre de pool frontal via le Skype pour l’Assistant de déploiement Business Server.</span><span class="sxs-lookup"><span data-stu-id="4cdd6-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="4cdd6-112">Vous devez également ajouter le nouveau membre du pool les programmes d’équilibrage de charge approprié pour le pool, le nom de domaine DNS (Domain Name System) de l’équilibrage de charge ou les équilibreurs de charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="4cdd6-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="4cdd6-113">Dans la plupart des cas, vous auriez les deux systèmes en place d’équilibrage de charge.</span><span class="sxs-lookup"><span data-stu-id="4cdd6-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="4cdd6-114">N’oubliez pas que vous ajoutez le nouveau serveur membre pour les deux.</span><span class="sxs-lookup"><span data-stu-id="4cdd6-114">Be sure that you are adding the new member server to both.</span></span> 
  

