---
title: Ajouter un Pool directeur
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Pour définir le nom de domaine complet du pool directeur, sélectionnez un pool de plusieurs ordinateurs qui se compose de deux ou plusieurs directeurs dans un pool à charge équilibrée, ou un pool à ordinateur unique. Vous devez également taper le nom de domaine complet (FQDN) qui sera utilisé pour se connecter au pool directeur ou nom de domaine complet du directeur unique. Pour un pool d’ordinateurs directeur, il s’agit de l’entrée de nom de domaine DNS (Domain Name System) pour l’adresse IP virtuelle de l’équilibrage de charge matérielle ou l’entrée DNS partagée pour l’équilibrage de charge DNS.
ms.openlocfilehash: 84f74962465645890e976a6f1ff77b6ef55ca930
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19967179"
---
# <a name="add-director-pool"></a><span data-ttu-id="f5bba-105">Ajouter un Pool directeur</span><span class="sxs-lookup"><span data-stu-id="f5bba-105">Add Director Pool</span></span>
 
<span data-ttu-id="f5bba-106">Pour **définir le nom de domaine complet du pool directeur**, sélectionnez un **pool de plusieurs ordinateurs** qui se compose de deux ou plusieurs directeurs dans un pool à charge équilibrée ou un **seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="f5bba-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="f5bba-107">Vous devez également taper le nom de domaine complet (FQDN) qui sera utilisé pour se connecter au pool directeur ou nom de domaine complet du directeur unique.</span><span class="sxs-lookup"><span data-stu-id="f5bba-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="f5bba-108">Pour un pool d’ordinateurs directeur, il s’agit de l’entrée de nom de domaine DNS (Domain Name System) pour l’adresse IP virtuelle de l’équilibrage de charge matérielle ou l’entrée DNS partagée pour l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="f5bba-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="f5bba-109">Si vous envisagez d’implémenter un pool directeur à l’avenir, sélectionnez **pool de plusieurs ordinateurs**.</span><span class="sxs-lookup"><span data-stu-id="f5bba-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="f5bba-110">Même si un pool est défini en tant que deux ou plusieurs ordinateurs qui sont à charge équilibrée, vous pouvez créer un pool à ordinateur unique et créer un nom de domaine complet du pool pour le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f5bba-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="f5bba-111">Lorsque vous êtes prêt à ajouter des ordinateurs au pool ultérieurement, vous devez exécuter le Générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du pool directeur via le Skype pour l’Assistant Déploiement Business Server.</span><span class="sxs-lookup"><span data-stu-id="f5bba-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="f5bba-112">Vous devez également ajouter le nouveau membre du pool pour les équilibreurs de charge approprié pour le pool, le nom de domaine (DNS)-équilibrage de la charge, ou pour le matériel équilibreurs de charge.</span><span class="sxs-lookup"><span data-stu-id="f5bba-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="f5bba-113">Dans la plupart des cas, vous devez les deux systèmes en place d’équilibrage de charge.</span><span class="sxs-lookup"><span data-stu-id="f5bba-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="f5bba-114">N’oubliez pas que vous ajoutez le nouveau serveur membre pour les deux.</span><span class="sxs-lookup"><span data-stu-id="f5bba-114">Be sure that you are adding the new member server to both.</span></span> 
  

