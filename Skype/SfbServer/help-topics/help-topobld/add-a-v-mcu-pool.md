---
title: Ajouter un pool MCU audio/vidéo
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Tous les serveurs frontaux Enterprise Edition d’un site central qui ne disposent pas d’un service de conférence A/V colocalisé peuvent utiliser le pool de conférence A/V autonome. Pour chaque pool de conférence A/V, vous devez spécifier un nom de domaine complet (FQDN) pour le pool et déterminer s’il aura un serveur de conférence A/V unique ou plusieurs serveurs de conférence A/V avec charge équilibrée.
ms.openlocfilehash: 689f91bd27e4b3bbb2bd31149f34438bac59db46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810464"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="c0af2-104">Ajouter un pool MCU audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="c0af2-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="c0af2-p102">Tous les serveurs frontaux Enterprise Edition d’un site central qui ne disposent pas d’un service de conférence A/V colocalisé peuvent utiliser le pool de conférence A/V autonome. Pour chaque pool de conférence A/V, vous devez spécifier un nom de domaine complet (FQDN) pour le pool et déterminer s’il aura un serveur de conférence A/V unique ou plusieurs serveurs de conférence A/V avec charge équilibrée.</span><span class="sxs-lookup"><span data-stu-id="c0af2-p102">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool. For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c0af2-p103">Vous ne pouvez pas convertir un pool d’un seul serveur en pool de plusieurs serveurs. Si vous décidez par la suite que votre organisation a besoin d’un pool de plusieurs serveurs, vous devez supprimer le pool d’un seul serveur, puis ajouter le pool de plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="c0af2-p103">You cannot convert a single-server pool to a multiple-server pool. If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="c0af2-109">Si vous envisagez d’implémenter un pool de conférence A/V par la suite, sélectionnez **Pool de plusieurs ordinateurs**.</span><span class="sxs-lookup"><span data-stu-id="c0af2-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="c0af2-110">Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec charge équilibrée, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique.</span><span class="sxs-lookup"><span data-stu-id="c0af2-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="c0af2-111">Lorsque vous êtes prêt à ajouter d’autres ordinateurs au pool ultérieurement, vous devez à nouveau le Générateur de topologies pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du pool de conférence A/V via l’Assistant Déploiement de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c0af2-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="c0af2-112">Les pools du serveur de conférence A/V sont uniques, c’est-à-dire qu’ils ne requièrent pas de programmes d’équilibrage de charge pour créer un pool.</span><span class="sxs-lookup"><span data-stu-id="c0af2-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="c0af2-113">Les pools de conférence A/V équilibrent la charge de manière interne et ne nécessitent pas de matériel supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="c0af2-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

