---
title: Distribution de la charge de conférence Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b37c61be4d715751b18581c643babfddae06ea5e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a><span data-ttu-id="6137e-102">Distribution de la charge de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6137e-102">Conferencing load distribution in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6137e-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6137e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6137e-104">Contrairement à d’autres solutions de conférence dédiées, l’architecture Lync Server est un modèle de matériel partagé.</span><span class="sxs-lookup"><span data-stu-id="6137e-104">Unlike some other dedicated conferencing solutions, Lync Server architecture is a shared-hardware model.</span></span> <span data-ttu-id="6137e-105">Cela signifie que le même matériel est partagé par de nombreux composants logiciels, chacun d’entre eux prenant en charge différentes communications en temps réel.</span><span class="sxs-lookup"><span data-stu-id="6137e-105">This means that the same hardware is shared by many software components, each of which supports different real-time communications.</span></span> <span data-ttu-id="6137e-106">Chaque type de communication en temps réel place des charges spécifiques sur les serveurs.</span><span class="sxs-lookup"><span data-stu-id="6137e-106">Each type of real-time communications places specific loads on the servers.</span></span> <span data-ttu-id="6137e-107">Par exemple, le serveur frontal peut exécuter les composants de routage SIP (Session Initiation Protocol), les applications Web (telles que la recherche de carnet d’adresses), le service de conférence Web, le service de conférence A/V, les applications voix entreprise (par exemple, l’application de surveillance de conférence et l’application Response Group) et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="6137e-107">For example, the Front End Server can run the Session Initiation Protocol (SIP) routing components, web applications (such as Address Book search), Web Conferencing service, A/V Conferencing service, Enterprise Voice applications (for example, Conferencing Attendant application and Response Group application), and Mediation Server.</span></span> <span data-ttu-id="6137e-108">Un ensemble de bases de données sur le serveur frontal assure également le stockage et le traitement des données d’utilisateur, de contact, de présence, de conférence et de routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="6137e-108">A set of databases on the Front End Server also provide storage and processing for user, contact, presence, conferencing, and voice routing data.</span></span> <span data-ttu-id="6137e-109">Avec ce partage matériel, les composants, les services et les processus rivalisant pour les ressources du processeur et de la mémoire, les charges de travail non relatives aux conférences ont un impact direct sur la mise à l’échelle du serveur.</span><span class="sxs-lookup"><span data-stu-id="6137e-109">With this hardware sharing, components, services, and processes compete for CPU and memory resources, so non-conferencing workloads have a direct impact on server scaling.</span></span>

<span data-ttu-id="6137e-110">Par rapport aux autres solutions de conférence basées sur les ports matériels, l’architecture de conférence Lync Server est un modèle sans réservation.</span><span class="sxs-lookup"><span data-stu-id="6137e-110">Compared to other hardware port-based conferencing solutions, Lync Server conferencing architecture is a no-reservation model.</span></span> <span data-ttu-id="6137e-111">Lorsqu’un utilisateur planifie une réunion, Lync Server crée un enregistrement dans la base de données de conférence, qui stocke les données de conférence, mais ne réserve pas de ressources matérielles pour la réunion planifiée à l’avance.</span><span class="sxs-lookup"><span data-stu-id="6137e-111">When a user schedules a meeting, Lync Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="6137e-112">Au lieu de cela, Lync Server dispose d’une logique d’équilibrage de charge intégrée pour allouer dynamiquement les ressources de conférence sur les serveurs frontaux d’une manière qui distribue équitablement les charges sur tous les serveurs frontaux du pool.</span><span class="sxs-lookup"><span data-stu-id="6137e-112">Instead, Lync Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="6137e-113">Cela permet d’approvisionner et d’utiliser les ressources matérielles mais rend difficile la prise en charge des réunions de très grande taille (surtout sans planification appropriée).</span><span class="sxs-lookup"><span data-stu-id="6137e-113">This effectively provisions and utilizes hardware resources, but makes it challenging to support very large meetings (especially without appropriate planning).</span></span> <span data-ttu-id="6137e-114">Par exemple, lorsqu’un pool Lync Server 2013 est exécuté près de sa capacité maximale, chaque serveur frontal peut héberger environ 125 réunions de taille moyenne.</span><span class="sxs-lookup"><span data-stu-id="6137e-114">For example, when a Lync Server 2013 pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="6137e-115">L’ajout d’une autre petite réunion ne serait pas un problème, mais l’ajout d’une réunion pour 1000 utilisateurs serait un problème, car les serveurs frontaux ne seraient probablement pas en mesure de prendre en charge une réunion de grande taille en même temps que les autres réunions 125.</span><span class="sxs-lookup"><span data-stu-id="6137e-115">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

