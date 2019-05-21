---
title: Ajouter un pool directeur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Pour définir le nom de domaine complet (FQDN) du pool de réalisateurs, sélectionnez un pool d’ordinateurs qui sera composé de deux ou plusieurs directeurs dans un pool équilibré ou un seul pool d’ordinateurs. Vous devez également taper le nom de domaine complet (FQDN, Fully Qualified Domain Name) qui sera utilisé pour la connexion au nom de domaine complet (FQDN) du réalisateur ou du réalisateur unique. Dans le cas d’un pool d’ordinateurs Director, il s’agirait de l’entrée DNS (Domain Name System) pour l’adresse IP virtuelle d’un équilibreur de charge matériel ou de l’entrée DNS partagée pour l’équilibrage de charge DNS.
ms.openlocfilehash: 163de8a6091e74238c4a4127ae39f7cd500cdb84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304785"
---
# <a name="add-director-pool"></a><span data-ttu-id="6356d-105">Ajouter un pool directeur</span><span class="sxs-lookup"><span data-stu-id="6356d-105">Add Director Pool</span></span>
 
<span data-ttu-id="6356d-106">Pour **définir le nom de domaine complet (FQDN) du pool**de réalisateurs, sélectionnez un **pool d’ordinateurs** qui sera composé de deux ou plusieurs directeurs dans un pool équilibré ou un **seul pool d’ordinateurs**.</span><span class="sxs-lookup"><span data-stu-id="6356d-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="6356d-107">Vous devez également taper le nom de domaine complet (FQDN, Fully Qualified Domain Name) qui sera utilisé pour la connexion au nom de domaine complet (FQDN) du réalisateur ou du réalisateur unique.</span><span class="sxs-lookup"><span data-stu-id="6356d-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="6356d-108">Dans le cas d’un pool d’ordinateurs Director, il s’agirait de l’entrée DNS (Domain Name System) pour l’adresse IP virtuelle d’un équilibreur de charge matériel ou de l’entrée DNS partagée pour l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="6356d-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="6356d-109">Si vous envisagez d’implémenter un pool de réalisateurs à l’avenir, sélectionnez **pool d’ordinateurs multiples**.</span><span class="sxs-lookup"><span data-stu-id="6356d-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="6356d-110">Même si le regroupement comporte au moins deux ordinateurs dont le chargement est équilibré, vous pouvez créer un pool d’ordinateurs unique et créer un nom de domaine complet de pool pour l’ordinateur unique.</span><span class="sxs-lookup"><span data-stu-id="6356d-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="6356d-111">Lorsque vous êtes prêt à ajouter plus d’ordinateurs au pool par la suite, vous devez exécuter de nouveau le générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du pool de directeurs par le biais de l’Assistant Déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6356d-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="6356d-112">Vous devez également ajouter le nouveau membre de la liste aux équilibreurs de charge appropriés pour le pool, pour l’équilibrage de charge DNS (Domain Name System) ou pour les équilibreurs de charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="6356d-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="6356d-113">Dans de nombreux cas, les deux systèmes d’équilibrage de charge sont en place.</span><span class="sxs-lookup"><span data-stu-id="6356d-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="6356d-114">Assurez-vous d’ajouter le nouveau serveur membre aux deux.</span><span class="sxs-lookup"><span data-stu-id="6356d-114">Be sure that you are adding the new member server to both.</span></span> 
  

