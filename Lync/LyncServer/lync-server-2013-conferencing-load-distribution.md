---
title: Distribution de chargement de conférences de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd78b6dcedc66f5a2235b45066be7faf70d4379b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a><span data-ttu-id="ba2fd-102">Distribution de chargement de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba2fd-102">Conferencing load distribution in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba2fd-103">_**Dernière modification de la rubrique:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ba2fd-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ba2fd-104">Contrairement à d’autres solutions de conférence dédiées, Lync Server architecture est un modèle de matériel partagé.</span><span class="sxs-lookup"><span data-stu-id="ba2fd-104">Unlike some other dedicated conferencing solutions, Lync Server architecture is a shared-hardware model.</span></span> <span data-ttu-id="ba2fd-105">Cela signifie que le même matériel est partagé par de nombreux composants logiciels, chacun d’entre eux prenant en charge des communications en temps réel différentes.</span><span class="sxs-lookup"><span data-stu-id="ba2fd-105">This means that the same hardware is shared by many software components, each of which supports different real-time communications.</span></span> <span data-ttu-id="ba2fd-106">Chaque type de communication en temps réel place des charges spécifiques sur les serveurs.</span><span class="sxs-lookup"><span data-stu-id="ba2fd-106">Each type of real-time communications places specific loads on the servers.</span></span> <span data-ttu-id="ba2fd-107">Par exemple, le serveur frontal peut exécuter les composants de routage SIP (Session Initiation Protocol), les applications Web (telles que la recherche dans le carnet d’adresses), le service de conférence Web, le service de conférence A/V, les applications vocales d’entreprise (par exemple, les conférences Application attendant et application de groupe de réponse) et serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="ba2fd-107">For example, the Front End Server can run the Session Initiation Protocol (SIP) routing components, web applications (such as Address Book search), Web Conferencing service, A/V Conferencing service, Enterprise Voice applications (for example, Conferencing Attendant application and Response Group application), and Mediation Server.</span></span> <span data-ttu-id="ba2fd-108">Un ensemble de bases de données du serveur frontal permet également de stocker et de traiter les données utilisateur, de contact, de présence, de conférence et de routage vocal.</span><span class="sxs-lookup"><span data-stu-id="ba2fd-108">A set of databases on the Front End Server also provide storage and processing for user, contact, presence, conferencing, and voice routing data.</span></span> <span data-ttu-id="ba2fd-109">Avec ce partage matériel, ses composants, ses services et ses processus en concurrence pour les ressources de mémoire et d’UC, les charges de travail non associées peuvent avoir un impact direct sur la mise à l’échelle du serveur.</span><span class="sxs-lookup"><span data-stu-id="ba2fd-109">With this hardware sharing, components, services, and processes compete for CPU and memory resources, so non-conferencing workloads have a direct impact on server scaling.</span></span>

<span data-ttu-id="ba2fd-110">Comparée aux autres solutions de conférence basées sur les ports, l’architecture de conférence serveur Lync est un modèle sans réservation.</span><span class="sxs-lookup"><span data-stu-id="ba2fd-110">Compared to other hardware port-based conferencing solutions, Lync Server conferencing architecture is a no-reservation model.</span></span> <span data-ttu-id="ba2fd-111">Lorsqu’un utilisateur planifie une réunion, Lync Server crée un enregistrement dans la base de données de conférence qui stocke les données de conférence, mais ne réserve aucune ressource matérielle pour la réunion planifiée à l’avance.</span><span class="sxs-lookup"><span data-stu-id="ba2fd-111">When a user schedules a meeting, Lync Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="ba2fd-112">Au lieu de cela, Lync Server dispose d’une logique d’équilibrage de charge intégrée permettant d’allouer dynamiquement les ressources de conférence sur les serveurs frontaux de telle sorte que les données de répartition soient uniformément chargées sur tous les serveurs frontaux de la liste.</span><span class="sxs-lookup"><span data-stu-id="ba2fd-112">Instead, Lync Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="ba2fd-113">Cela met en application et utilise efficacement les ressources matérielles, mais contribue à la prise en charge des réunions de très grande taille (en particulier, sans planification appropriée).</span><span class="sxs-lookup"><span data-stu-id="ba2fd-113">This effectively provisions and utilizes hardware resources, but makes it challenging to support very large meetings (especially without appropriate planning).</span></span> <span data-ttu-id="ba2fd-114">Par exemple, lorsqu’un pool Lync Server 2013 est en cours d’exécution en plus grande capacité, chaque serveur frontal peut héberger approximativement 125 réunions de taille moyenne.</span><span class="sxs-lookup"><span data-stu-id="ba2fd-114">For example, when a Lync Server 2013 pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="ba2fd-115">L’ajout d’une autre réunion de petite taille ne serait pas un obstacle à la différence d’une réunion de 1 000 utilisateurs, car les serveurs frontaux ne pourraient probablement pas prendre en charge une grande réunion en même temps que les 125 autres réunions.</span><span class="sxs-lookup"><span data-stu-id="ba2fd-115">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

