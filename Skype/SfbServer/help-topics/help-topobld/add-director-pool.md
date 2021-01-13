---
title: Ajouter un pool directeur
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
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Pour Définir le nom de domaine complet du pool directeur, sélectionnez un Pool de plusieurs ordinateurs, qui sera constitué de deux directeurs ou plus dans un pool avec équilibrage de la charge, ou bien un Pool d’un seul ordinateur. Vous devez également taper le nom de domaine complet (FQDN) qui sera utilisé pour se connecter au pool directeur ou au nom de domaine complet du directeur unique. Pour un pool d'ordinateurs directeurs, c'est l'entrée DNS (Domain Name System) de l'IP virtuelle d'un mécanisme d'équilibrage de charge basé sur le matériel ou l'entrée DNS partagée pour l’équilibrage de charge DNS.
ms.openlocfilehash: 611692c9491fa197594e5d16038665997809853e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828904"
---
# <a name="add-director-pool"></a><span data-ttu-id="46a86-105">Ajouter un pool directeur</span><span class="sxs-lookup"><span data-stu-id="46a86-105">Add Director Pool</span></span>
 
<span data-ttu-id="46a86-106">Pour **Définir le nom de domaine complet du pool directeur**, sélectionnez un **Pool de plusieurs ordinateurs**, qui sera constitué de deux directeurs ou plus dans un pool avec équilibrage de la charge, ou bien un **Pool d’un seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="46a86-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="46a86-107">Vous devez également taper le nom de domaine complet (FQDN) qui sera utilisé pour se connecter au pool directeur ou au nom de domaine complet du directeur unique.</span><span class="sxs-lookup"><span data-stu-id="46a86-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="46a86-108">Pour un pool d'ordinateurs directeurs, c'est l'entrée DNS (Domain Name System) de l'IP virtuelle d'un mécanisme d'équilibrage de charge basé sur le matériel ou l'entrée DNS partagée pour l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="46a86-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="46a86-109">Si vous pensez implémenter un pool directeur ultérieurement, sélectionnez **Pool de plusieurs ordinateurs**.</span><span class="sxs-lookup"><span data-stu-id="46a86-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="46a86-110">Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec charge équilibrée, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique.</span><span class="sxs-lookup"><span data-stu-id="46a86-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="46a86-111">Lorsque vous êtes prêt à ajouter d’autres ordinateurs au pool ultérieurement, vous devez exécuter à nouveau le Générateur de topologies pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du pool directeur via l’Assistant Déploiement de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="46a86-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="46a86-112">Vous devez également ajouter le nouveau membre du pool aux équilibreurs de la charge pour le pool, à l’équilibrage de la charge DNS ou aux équilibreurs de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="46a86-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="46a86-113">Dans de nombreux cas, les deux systèmes d’équilibrage de la charge seront en place.</span><span class="sxs-lookup"><span data-stu-id="46a86-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="46a86-114">Veillez à ajouter le nouveau serveur membre aux deux systèmes.</span><span class="sxs-lookup"><span data-stu-id="46a86-114">Be sure that you are adding the new member server to both.</span></span> 
  

