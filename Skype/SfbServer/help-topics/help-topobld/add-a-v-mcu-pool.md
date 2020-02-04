---
title: Ajouter un pool MCU audio/vidéo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Les serveurs frontaux Enterprise Edition d’un site central ne disposant pas d’un service de conférence A/V colocalisé peuvent utiliser le même pool de conférence A/V autonome. Pour chaque pool de conférence A/V, vous devez spécifier un nom de domaine complet (FQDN) pour le pool et savoir s’il n’en a qu’un seul ou plusieurs serveurs de conférence A/V.
ms.openlocfilehash: cf34ca6b82f31b0232748d15f0b0cc6597511249
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685387"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="fdd39-104">Ajouter un pool MCU audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="fdd39-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="fdd39-105">Les serveurs frontaux Enterprise Edition d’un site central ne disposant pas d’un service de conférence A/V colocalisé peuvent utiliser le même pool de conférence A/V autonome.</span><span class="sxs-lookup"><span data-stu-id="fdd39-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="fdd39-106">Pour chaque pool de conférence A/V, vous devez spécifier un nom de domaine complet (FQDN) pour le pool et savoir s’il n’en a qu’un seul ou plusieurs serveurs de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="fdd39-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fdd39-107">Vous ne pouvez pas convertir un pool serveur unique en pool de plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="fdd39-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="fdd39-108">Si vous décidez plus tard que votre organisation a besoin d’un pool de serveurs multiples, vous devez supprimer le pool de serveur unique, puis ajouter le pool de serveurs multiples.</span><span class="sxs-lookup"><span data-stu-id="fdd39-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="fdd39-109">Si vous envisagez d’implémenter un pool de conférence A/V à l’avenir, sélectionnez **plusieurs pools d’ordinateurs**.</span><span class="sxs-lookup"><span data-stu-id="fdd39-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="fdd39-110">Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec équilibrage de la charge, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique.</span><span class="sxs-lookup"><span data-stu-id="fdd39-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="fdd39-111">Lorsque vous êtes prêt à ajouter plus d’ordinateurs au pool par la suite, vous devez de nouveau définir le générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du groupe de conférence A/V par le biais de l’Assistant Déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="fdd39-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="fdd39-112">Les pools de serveurs de conférence A/V sont uniques dans le fait qu’ils n’ont pas besoin des équilibreurs de charge pour créer un pool.</span><span class="sxs-lookup"><span data-stu-id="fdd39-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="fdd39-113">Les pools de conférence A/V sont équilibrés en interne et ne nécessitent pas de matériel supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="fdd39-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

