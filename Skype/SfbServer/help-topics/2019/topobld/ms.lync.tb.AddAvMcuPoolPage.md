---
title: Ajouter un pool MCU audio/vidéo
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: Tous les serveurs Enterprise Edition frontaux d’un site central qui n’ont pas un colocalisé un service de conférence V peut utiliser le même Stand-Alone A / pool de conférence V. Pour chaque A / pool de conférence V, vous devez spécifier un nom de domaine complet (FQDN) pour le pool et si elle aura uniquement un seul A / V Conferencing Server ou multiples, à charge équilibrée A / V Conferencing Servers.
ms.openlocfilehash: f88476165ce6affe23e9e5cbb33e03a997c04971
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202302"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="0ed99-104">Ajouter un pool MCU audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="0ed99-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="0ed99-105">Tous les serveurs Enterprise Edition frontaux d’un site central qui n’ont pas un colocalisé un service de conférence V peut utiliser le même Stand-Alone A / pool de conférence V.</span><span class="sxs-lookup"><span data-stu-id="0ed99-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="0ed99-106">Pour chaque A / pool de conférence V, vous devez spécifier un nom de domaine complet (FQDN) pour le pool et si elle aura uniquement un seul A / V Conferencing Server ou multiples, à charge équilibrée A / V Conferencing Servers.</span><span class="sxs-lookup"><span data-stu-id="0ed99-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0ed99-107">Impossible de convertir un pool de serveur unique vers un pool de plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="0ed99-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="0ed99-108">Si vous décidez ultérieurement que votre organisation a besoin d’un pool de plusieurs serveurs, vous devez supprimer le pool de serveur unique et puis ajouter le pool de plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="0ed99-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="0ed99-109">Si vous envisagez d’implémenter un / pool de conférence V activez à l’avenir, le **pool de plusieurs ordinateurs**.</span><span class="sxs-lookup"><span data-stu-id="0ed99-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="0ed99-110">Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec équilibrage de la charge, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique.</span><span class="sxs-lookup"><span data-stu-id="0ed99-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="0ed99-111">Lorsque vous êtes prêt à ajouter des ordinateurs au pool ultérieurement, vous devez le Générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer la nouvelle A / V Conferencing pool membre via le Skype pour l’Assistant de déploiement Business Server.</span><span class="sxs-lookup"><span data-stu-id="0ed99-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="0ed99-112">A / pools V Conferencing Server sont uniques dans la mesure où ils ne pas besoin équilibreurs de charge pour créer un pool.</span><span class="sxs-lookup"><span data-stu-id="0ed99-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="0ed99-113">A / pools de conférence V équilibrer la charge en interne et n’avez pas besoin de matériel supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="0ed99-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

