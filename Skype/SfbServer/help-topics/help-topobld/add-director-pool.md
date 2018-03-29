---
title: Ajouter un Pool de directeur
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Pour définir le nom de domaine complet du pool directeur, sélectionnez soit un plusieurs ordinateur pool qui sera composé de deux ou plusieurs directeurs dans un pool d’équilibrage de charge, ou un seul ordinateur. Vous devez également taper le nom de domaine complet (FQDN) qui sera utilisé pour se connecter au pool de directeur ou de nom de domaine complet du directeur unique. Pour un pool d’ordinateurs du directeur, il s’agit de l’entrée de nom de domaine (DNS) pour l’adresse IP virtuelle d’un équilibreur de charge matériel ou l’entrée DNS partagée pour l’équilibrage de la charge DNS.
ms.openlocfilehash: d71219f6e9c51d69bee8d2457cc30c19f4fa6c89
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-director-pool"></a><span data-ttu-id="29b1b-105">Ajouter un Pool de directeur</span><span class="sxs-lookup"><span data-stu-id="29b1b-105">Add Director Pool</span></span>
 
<span data-ttu-id="29b1b-106">Pour **définir le nom de domaine complet du pool Director**, sélectionnez un **pool de plusieurs ordinateur** qui sera composé de deux ou plusieurs directeurs dans un pool d’équilibrage de charge ou un **pool d’un seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="29b1b-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="29b1b-107">Vous devez également taper le nom de domaine complet (FQDN) qui sera utilisé pour se connecter au pool de directeur ou de nom de domaine complet du directeur unique.</span><span class="sxs-lookup"><span data-stu-id="29b1b-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="29b1b-108">Pour un pool d’ordinateurs du directeur, il s’agit de l’entrée de nom de domaine (DNS) pour l’adresse IP virtuelle d’un équilibreur de charge matériel ou l’entrée DNS partagée pour l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="29b1b-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="29b1b-109">Si vous envisagez d’implémenter un pool de directeur à l’avenir, sélectionnez **plusieurs pool d’ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="29b1b-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="29b1b-110">Même si un pool est défini en tant que deux ordinateurs ou plus qui sont à équilibrage de charge, vous pouvez créer un pool d’ordinateur unique et créer un nom de domaine complet du pool pour le seul ordinateur.</span><span class="sxs-lookup"><span data-stu-id="29b1b-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="29b1b-111">Lorsque vous êtes prêt à ajouter des ordinateurs au pool ultérieurement, vous devez exécuter le Générateur de topologies pour définir le nouveau membre du pool, publiez la nouvelle topologie, puis configurer le nouveau membre du pool directeur via le Skype pour l’Assistant de déploiement de serveur Business.</span><span class="sxs-lookup"><span data-stu-id="29b1b-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="29b1b-112">Vous devez également ajouter le nouveau membre du pool pour les équilibreurs de charge approprié pour le pool, système de nom de domaine (DNS)-équilibrage de la charge, ou pour le matériel des équilibreurs de charge.</span><span class="sxs-lookup"><span data-stu-id="29b1b-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="29b1b-113">Dans de nombreux cas, vous avez les deux systèmes d’équilibrage de la charge.</span><span class="sxs-lookup"><span data-stu-id="29b1b-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="29b1b-114">Assurez-vous que vous ajoutez le nouveau serveur membre pour les deux.</span><span class="sxs-lookup"><span data-stu-id="29b1b-114">Be sure that you are adding the new member server to both.</span></span> 
  

