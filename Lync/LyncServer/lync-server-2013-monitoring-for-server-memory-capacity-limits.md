---
title: 'Lync Server 2013 : surveillance des limites de capacité de mémoire des serveurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 160d90a5a79291d18afdab00c23ff0a6726fa5b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531941"
---
# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="5028c-102">Surveillance des limites de capacité de mémoire des serveurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5028c-102">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5028c-103">_**Dernière modification de la rubrique :** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="5028c-103">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="5028c-104">Les informations de cette rubrique qui font référence à la planification de la capacité ne concernent que les clients mobiles Lync 2010 et le service de mobilité (MCX).</span><span class="sxs-lookup"><span data-stu-id="5028c-104">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="5028c-105">La planification de la capacité pour l’API Web de communications unifiées (UCWA), utilisée par les clients mobiles Lync 2013, est fournie par l’outil de planification Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5028c-105">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="5028c-106">Deux compteurs de performances de mobilité peuvent vous aider à déterminer votre utilisation actuelle et à vous aider à planifier la capacité du service de mobilité Lync Server 2013 (MCX), ainsi qu’à surveiller l’utilisation de la mémoire pour UCWA.</span><span class="sxs-lookup"><span data-stu-id="5028c-106">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="5028c-107">Pour UCWA, la catégorie de compteurs est **ls : Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="5028c-107">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="5028c-108">Pour le service de mobilité (MCX), les compteurs appartiennent à la catégorie **ls : Web-service de communication mobile**.</span><span class="sxs-lookup"><span data-stu-id="5028c-108">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="5028c-109">Les compteurs à surveiller sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="5028c-109">The counters to monitor are:</span></span>

  - <span data-ttu-id="5028c-110">Nombre de **sessions actuellement actives avec abonnements de présence actifs**, c’est-à-dire le nombre actuel de points de terminaison enregistrés via UCWA ou le service de mobilité (MCX) qui ont des abonnements de présence actifs (nombre d’utilisateurs mobiles toujours connectés)</span><span class="sxs-lookup"><span data-stu-id="5028c-110">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="5028c-111">Nombre de **sessions actuellement actives**, qui correspond au nombre actuel de points de terminaison enregistrés via UCWA ou le service de mobilité</span><span class="sxs-lookup"><span data-stu-id="5028c-111">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="5028c-112">Si la différence entre le **nombre de sessions actuellement actives et les abonnements de présence actifs** et le **nombre de sessions actuellement actives** est faible au fil du temps, cela signifie que la plupart des utilisateurs d’appareils mobiles disposent d’un appareil connecté toujours, tel qu’un appareil mobile Android ou Nokia (pour MCX uniquement).</span><span class="sxs-lookup"><span data-stu-id="5028c-112">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="5028c-113">Les appareils UCWA toujours connectés incluent des appareils Apple et Android exécutant des clients mobiles Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="5028c-113">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="5028c-114">Si le **nombre de sessions actives** est largement supérieur **au nombre de sessions actuellement actives avec des abonnements de présence actifs**, cela indique que d’autres utilisateurs utilisent un périphérique de point de terminaison d’arrière-plan, tel qu’un périphérique iOS Apple ou Windows Phone sous MCX.</span><span class="sxs-lookup"><span data-stu-id="5028c-114">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="5028c-115">(Windows Phone est le seul client mobile Lync 2013 qui s’inscrira comme suit).</span><span class="sxs-lookup"><span data-stu-id="5028c-115">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="5028c-116">Vous devez définir une limite sur le **nombre de sessions actuellement actives avec des abonnements de présence actifs** et des compteurs de performance de **nombre de sessions actuellement actives** en fonction de votre utilisation, des résultats de la planification de la capacité et de la surveillance continue du service de mobilité et d’autres compteurs de serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="5028c-116">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="5028c-117">Les limites que vous définissez doivent vous permettre d’évaluer la capacité du serveur et de déclencher des alertes lorsque la capacité est dépassée.</span><span class="sxs-lookup"><span data-stu-id="5028c-117">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="5028c-118">Pour déterminer les limites appropriées, vous devez d’abord déterminer la capacité de mémoire disponible sur le serveur frontal pour le service de mobilité.</span><span class="sxs-lookup"><span data-stu-id="5028c-118">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="5028c-119">Surveillez les compteurs pour déterminer à quel moment vous devez planifier une capacité supplémentaire, en fonction de la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="5028c-119">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="5028c-120">Quantité totale de mémoire utilisée par le service de mobilité MCX (Mo) = 164 + (400 + 134)/1024 \* **nombre de sessions actuellement actives avec abonnements de présence actifs** + 400/1024 (nombre de sessions actuellement actives \* – **nombre de sessions actuellement actives avec abonnements de présence actifs**)**Currently Active Session Count**</span><span class="sxs-lookup"><span data-stu-id="5028c-120">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5028c-121">La calculatrice de capacité Microsoft Lync Server 2010 est une feuille de calcul pré-remplie avec toutes les formules qui permettent à un planificateur de déterminer les conditions requises pour les serveurs, notamment l’UC, la mémoire et le disque dur.</span><span class="sxs-lookup"><span data-stu-id="5028c-121">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="5028c-122">Vous pouvez télécharger la feuille de calcul et un document associé à l’adresse suivante : <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="5028c-122">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="5028c-123">Le serveur frontal doit disposer de suffisamment de mémoire disponible pour prendre en charge le service de mobilité dans les situations de basculement.</span><span class="sxs-lookup"><span data-stu-id="5028c-123">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="5028c-124">Vous pouvez surveiller la mémoire disponible sur le serveur frontal en utilisant le compteur **méga- \\ octets disponibles** de la mémoire, ou en utilisant l’équation mentionnée ci-dessus, pour planifier la quantité de mémoire que le service de mobilité doit utiliser.</span><span class="sxs-lookup"><span data-stu-id="5028c-124">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="5028c-125">Si la quantité de mémoire disponible sur le serveur frontal est inférieure à 1 500 Mo lorsque vous planifiez le nombre d’utilisateurs de mobilité prévu, vous devez ajouter davantage de matériel pour prendre en charge le service de mobilité.</span><span class="sxs-lookup"><span data-stu-id="5028c-125">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="5028c-126">Pour plus d’informations, reportez-vous à la rubrique [Monitoring Mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="5028c-126">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5028c-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5028c-127">See Also</span></span>


[<span data-ttu-id="5028c-128">Surveillance de la mobilité pour les performances dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5028c-128">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

