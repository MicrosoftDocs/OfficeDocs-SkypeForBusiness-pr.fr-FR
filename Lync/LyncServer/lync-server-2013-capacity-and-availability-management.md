---
title: 'Lync Server 2013 : gestion de la capacité et de la disponibilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efef66bcac833bb67c67dc453c25f3e0f6d51ba1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512851"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="55929-102">Gestion de la capacité et de la disponibilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55929-102">Capacity and availability management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55929-103">_**Dernière modification de la rubrique :** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="55929-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="55929-104">L’objectif de la gestion de la capacité et de la gestion de la disponibilité est de mesurer et de contrôler les performances du système.</span><span class="sxs-lookup"><span data-stu-id="55929-104">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="55929-105">Nous vous recommandons de mettre en œuvre les procédures de gestion de la capacité et de gestion de la capacité afin de pouvoir mesurer et contrôler les performances du système.</span><span class="sxs-lookup"><span data-stu-id="55929-105">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="55929-106">Vous devez savoir si le système est disponible et s’il peut gérer les demandes actuelles et prévues en définissant des configurations de référence et en surveillant le système pour rechercher des tendances.</span><span class="sxs-lookup"><span data-stu-id="55929-106">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="55929-107">Gestion de la capacité</span><span class="sxs-lookup"><span data-stu-id="55929-107">Capacity management</span></span>

<span data-ttu-id="55929-108">La gestion de la capacité implique la planification, le dimensionnement et le contrôle de la capacité de service afin de garantir que les niveaux de performances minimaux spécifiés dans votre contrat SLA sont dépassés.</span><span class="sxs-lookup"><span data-stu-id="55929-108">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="55929-109">La gestion de la capacité permet de garantir que vous pouvez fournir des services informatiques à un coût raisonnable tout en respectant les niveaux de performances définis dans vos accords SLA avec le client.</span><span class="sxs-lookup"><span data-stu-id="55929-109">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="55929-110">Ces critères peuvent être les suivants :</span><span class="sxs-lookup"><span data-stu-id="55929-110">These criteria can include the following:</span></span>

  - <span data-ttu-id="55929-111">Temps de réponse du **système**     Il s’agit du temps mesuré que le système effectue pour effectuer des actions classiques.</span><span class="sxs-lookup"><span data-stu-id="55929-111">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="55929-112">Les exemples incluent le temps nécessaire au rôle de serveur audio/vidéo pour traiter le trafic audio/vidéo, le temps nécessaire pour qu’un client crée et participe à une conférence, ou le temps nécessaire pour que la présence soit mise à jour dans tous les clients observateurs.</span><span class="sxs-lookup"><span data-stu-id="55929-112">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="55929-113">**Capacité**     de stockage Il s’agit de la capacité d’un système de stockage, qu’il s’agisse d’une base de données de contenu, d’une unité de sauvegarde ou d’un lecteur local.</span><span class="sxs-lookup"><span data-stu-id="55929-113">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="55929-114">Par exemple, l’espace de stockage maximal doit être fourni par site et le temps de stockage des sauvegardes avant leur remplacement.</span><span class="sxs-lookup"><span data-stu-id="55929-114">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="55929-115">L’ajustement de la capacité est souvent un cas de s’assurer que suffisamment de ressources physiques sont disponibles, telles que l’espace disque et la bande passante réseau.</span><span class="sxs-lookup"><span data-stu-id="55929-115">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="55929-116">Le tableau suivant répertorie les résolutions typiques des problèmes liés à la capacité.</span><span class="sxs-lookup"><span data-stu-id="55929-116">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="55929-117">Résolutions typiques des problèmes liés à la capacité</span><span class="sxs-lookup"><span data-stu-id="55929-117">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55929-118">Problème</span><span class="sxs-lookup"><span data-stu-id="55929-118">Issue</span></span></th>
<th><span data-ttu-id="55929-119">Résolution possible</span><span class="sxs-lookup"><span data-stu-id="55929-119">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55929-120">Utilisateurs distants présentant des performances audio/vidéo médiocres</span><span class="sxs-lookup"><span data-stu-id="55929-120">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="55929-121">Vérifiez si la bande passante appropriée est disponible sur les liaisons WAN et si la qualité de service (QoS) est activée et configurée correctement.</span><span class="sxs-lookup"><span data-stu-id="55929-121">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="55929-122">Vérifier les données QoE.</span><span class="sxs-lookup"><span data-stu-id="55929-122">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55929-123">La réponse globale de l’environnement Lync est lente.</span><span class="sxs-lookup"><span data-stu-id="55929-123">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="55929-124">Exécutez des tests pour vérifier que les serveurs frontaux existants peuvent traiter la charge.</span><span class="sxs-lookup"><span data-stu-id="55929-124">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="55929-125">Introduisez un nouveau serveur frontal si nécessaire. Vérifiez les temps de réponse de la base de données SQL et corrigez les causes de ces retards (par exemple, amélioration des e/s disque).</span><span class="sxs-lookup"><span data-stu-id="55929-125">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="55929-126">Le dépannage est plus détaillé dans le Guide de mise en réseau Lync Server.</span><span class="sxs-lookup"><span data-stu-id="55929-126">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="55929-127">La capacité est affectée par la configuration du système et dépend des ressources physiques telles que la bande passante réseau.</span><span class="sxs-lookup"><span data-stu-id="55929-127">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="55929-128">Par exemple, si un environnement Lync est configuré pour effectuer une sauvegarde complète nocturne, il convient de s’assurer que l’impact sur les performances interactives prises en charge par les utilisateurs finaux est minimisé.</span><span class="sxs-lookup"><span data-stu-id="55929-128">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="55929-129">La gestion de la capacité est le processus qui consiste à maintenir la capacité d’un système dans des limites acceptables et à résoudre les problèmes suivants :</span><span class="sxs-lookup"><span data-stu-id="55929-129">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="55929-130">**Réaction aux modifications des exigences**     Les besoins en capacité doivent être ajustés pour tenir compte des modifications apportées au sein du système ou de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="55929-130">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="55929-131">Par exemple, si votre environnement décide d’implémenter voix entreprise, le nombre et l’emplacement des serveurs de médiation et des passerelles PSTN (réseau téléphonique commuté) sont très importants.</span><span class="sxs-lookup"><span data-stu-id="55929-131">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="55929-132">Si vous effectuez une jonction SIP (Session Initiation Protocol) ou SIP direct, la conception globale sera considérablement modifiée afin de fournir les meilleures performances vocales de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="55929-132">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="55929-133">**Prévision des besoins futurs**     Certaines exigences en matière de capacité changent de manière prévisible au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="55929-133">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="55929-134">Le suivi des tendances vous permet de planifier les mises à niveau à l’avance.</span><span class="sxs-lookup"><span data-stu-id="55929-134">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="55929-135">Par exemple, la bande passante disponible entre les différents sites Lync doit être surveillée pour créer une configuration de référence.</span><span class="sxs-lookup"><span data-stu-id="55929-135">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="55929-136">Cette configuration de référence vous permettra de prévoir le moment où vous devez ajouter davantage de bande passante à ces liens, car le nombre d’utilisateurs dans ces sites distants augmente avec le temps.</span><span class="sxs-lookup"><span data-stu-id="55929-136">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="55929-137">Gestion de la disponibilité</span><span class="sxs-lookup"><span data-stu-id="55929-137">Availability management</span></span>

<span data-ttu-id="55929-138">La gestion de la disponibilité est le processus qui consiste à garantir que tout service informatique se comporte de façon cohérente et rentable le niveau de service cohérent et fiable requis par le client.</span><span class="sxs-lookup"><span data-stu-id="55929-138">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="55929-139">La gestion de la disponibilité s’occupe de minimiser la perte de service et de s’assurer que l’action appropriée est effectuée en cas de perte du service.</span><span class="sxs-lookup"><span data-stu-id="55929-139">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="55929-140">Dans un environnement Lync, vous pouvez vous préoccuper de savoir si le service voix entreprise est disponible, si les utilisateurs peuvent participer à des conférences planifiées, etc.</span><span class="sxs-lookup"><span data-stu-id="55929-140">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="55929-141">Un accord SLA définit une fréquence et une durée de panne acceptables et autorise certaines périodes lorsque le système n’est pas disponible pour une maintenance planifiée.</span><span class="sxs-lookup"><span data-stu-id="55929-141">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="55929-142">Si vous devez fournir des rapports à votre gestion sur la disponibilité des systèmes, ou si vous avez des pénalités financières ou d’autres pénalités associées à des objectifs de disponibilité manquants, vous devez enregistrer les données de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="55929-142">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="55929-143">Même si vous n’avez pas ces exigences formelles, il est judicieux de connaître au moins la fréquence à laquelle un système est tombé en panne pendant une période donnée.</span><span class="sxs-lookup"><span data-stu-id="55929-143">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="55929-144">Par exemple, la disponibilité du système au cours des 12 derniers mois et la durée de la récupération à partir de chaque défaillance.</span><span class="sxs-lookup"><span data-stu-id="55929-144">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="55929-145">Ces informations vous aideront à mesurer et à améliorer l’efficacité de votre équipe dans la réponse à une défaillance du système.</span><span class="sxs-lookup"><span data-stu-id="55929-145">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="55929-146">Elle peut également vous fournir des informations utiles en cas de litige.</span><span class="sxs-lookup"><span data-stu-id="55929-146">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="55929-147">Les mesures liées à la disponibilité sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="55929-147">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="55929-148">**Disponibilité**     En règle générale, il s’agit du moment où un système ou un service est accessible par rapport à l’heure à laquelle il est inactif.</span><span class="sxs-lookup"><span data-stu-id="55929-148">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="55929-149">Elle est généralement exprimée sous la forme d’un pourcentage.</span><span class="sxs-lookup"><span data-stu-id="55929-149">It is typically expressed as a percentage.</span></span> <span data-ttu-id="55929-150">(Vous pouvez voir les références à « trois neufs » ou à « cinq neuf ».</span><span class="sxs-lookup"><span data-stu-id="55929-150">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="55929-151">Ces éléments font référence à 99,9% ou 99,999% de disponibilité.)</span><span class="sxs-lookup"><span data-stu-id="55929-151">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="55929-152">**Fiabilité**     Il s’agit d’une mesure du temps entre les défaillances d’un système et est parfois exprimée en temps moyen (ou en moyenne) entre les défaillances (MTBF).</span><span class="sxs-lookup"><span data-stu-id="55929-152">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="55929-153">**Temps de réparation**     Il s’agit du temps nécessaire pour récupérer un service après une panne et est souvent exprimé en temps moyen de réparation (MTTR).</span><span class="sxs-lookup"><span data-stu-id="55929-153">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="55929-154">La disponibilité, la fiabilité et le temps de réparation sont liés comme suit :</span><span class="sxs-lookup"><span data-stu-id="55929-154">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="55929-155">**Disponibilité = (MTBF – MTTR)/MTBF**     Par exemple, si un serveur tombe en panne deux fois pendant une période de six mois et n’est pas disponible pendant une moyenne de 20 minutes, le MTBF est de trois mois ou de 90 jours et le MTTR est de 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="55929-155">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="55929-156">Par conséquent, la disponibilité = (90 jours – 20 minutes)/90 jours = 99,985%.</span><span class="sxs-lookup"><span data-stu-id="55929-156">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="55929-157">La gestion de la disponibilité est le processus qui consiste à s’assurer que la disponibilité est optimisée et conservée dans les paramètres définis dans SLA.</span><span class="sxs-lookup"><span data-stu-id="55929-157">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="55929-158">La gestion de la disponibilité inclut les processus suivants :</span><span class="sxs-lookup"><span data-stu-id="55929-158">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="55929-159">**Surveillance**     Examen du délai et de la durée pendant laquelle les services ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="55929-159">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="55929-160">**Création de rapports**     Les chiffres de disponibilité doivent être régulièrement fournis aux équipes de gestion, des utilisateurs et des opérations.</span><span class="sxs-lookup"><span data-stu-id="55929-160">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="55929-161">Ces rapports doivent mettre en évidence des tendances et identifier les domaines qui nécessitent une attention particulière.</span><span class="sxs-lookup"><span data-stu-id="55929-161">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="55929-162">Le rapport doit résumer la conformité aux objectifs définis dans les SLA.</span><span class="sxs-lookup"><span data-stu-id="55929-162">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="55929-163">**Amélioration**     Si la disponibilité ne répond pas aux objectifs définis dans les SLA ou lorsque la tendance est à réduire la disponibilité, le processus de gestion de la disponibilité doit planifier les étapes de réparation.</span><span class="sxs-lookup"><span data-stu-id="55929-163">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="55929-164">Cela doit inclure la collaboration avec d’autres équipes responsables pour mettre en évidence les raisons des pannes et planifier des actions correctives afin d’éviter une réapparition des pannes.</span><span class="sxs-lookup"><span data-stu-id="55929-164">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="55929-165">Les mesures de capacité et de disponibilité sont des tâches répétitives qui conviennent parfaitement aux outils et scripts automatisés, tels que Microsoft System Center Operations Manager (anciennement Microsoft Operations Manager), qui est abordé plus loin dans ce document.</span><span class="sxs-lookup"><span data-stu-id="55929-165">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55929-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="55929-166">See Also</span></span>


[<span data-ttu-id="55929-167">Surveillance de Lync Server 2013 avec System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="55929-167">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

