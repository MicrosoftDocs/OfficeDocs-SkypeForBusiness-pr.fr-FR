---
title: 'Lync Server 2013 : gestion des capacités et de la disponibilité'
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
ms.openlocfilehash: 169c2e383a1799f5f3ab7ca810de32f86350e51b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="7f937-102">Gestion de la capacité et de la disponibilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f937-102">Capacity and availability management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f937-103">_**Dernière modification de la rubrique :** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="7f937-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="7f937-104">L’objectif de la gestion de la capacité et de la gestion de la disponibilité est de mesurer et de contrôler les performances du système.</span><span class="sxs-lookup"><span data-stu-id="7f937-104">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="7f937-105">Nous vous recommandons de mettre en œuvre des procédures de gestion de la capacité et de gestion de la disponibilité pour pouvoir mesurer et contrôler les performances du système.</span><span class="sxs-lookup"><span data-stu-id="7f937-105">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="7f937-106">Vous devez savoir si le système est disponible et s’il peut gérer les demandes actuelles et projetées en définissant des plannings de référence et en analysant le système pour trouver des tendances.</span><span class="sxs-lookup"><span data-stu-id="7f937-106">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="7f937-107">Gestion de la capacité</span><span class="sxs-lookup"><span data-stu-id="7f937-107">Capacity management</span></span>

<span data-ttu-id="7f937-108">La gestion de la capacité implique la planification, le dimensionnement et la gestion de la capacité de service pour garantir que les niveaux de performance minimum spécifiés dans votre SLA soient dépassés.</span><span class="sxs-lookup"><span data-stu-id="7f937-108">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="7f937-109">La gestion de la capacité est un bon moyen de garantir que vous pouvez fournir des services informatiques à un tarif raisonnable tout en respectant les niveaux de performance définis dans les SLA avec le client.</span><span class="sxs-lookup"><span data-stu-id="7f937-109">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="7f937-110">Ces critères peuvent être les suivants :</span><span class="sxs-lookup"><span data-stu-id="7f937-110">These criteria can include the following:</span></span>

  - <span data-ttu-id="7f937-111">**Temps de réponse système**   il s’agit de la durée mesurée que le système exécute pour effectuer des actions courantes.</span><span class="sxs-lookup"><span data-stu-id="7f937-111">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="7f937-112">Par exemple, le temps nécessaire au rôle du serveur audio/vidéo pour le traitement du trafic audio et vidéo, le temps nécessaire à un client pour la création et la participation à une conférence, ou le temps nécessaire pour la mise à jour de la présence dans tous les clients FileSystemWatcher.</span><span class="sxs-lookup"><span data-stu-id="7f937-112">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="7f937-113">**Capacité de stockage**   il s’agit de la capacité d’un système de stockage, qu’il s’agisse d’une base de données de contenu, d’un périphérique de sauvegarde ou d’un disque local.</span><span class="sxs-lookup"><span data-stu-id="7f937-113">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="7f937-114">Par exemple, vous pouvez inclure le volume maximal d’espace de stockage par site, ainsi que l’heure de stockage des copies de sauvegarde avant leur remplacement.</span><span class="sxs-lookup"><span data-stu-id="7f937-114">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="7f937-115">La modification de la capacité est souvent le cas pour garantir la disponibilité de ressources physiques suffisantes, telles que l’espace disque et la bande passante réseau.</span><span class="sxs-lookup"><span data-stu-id="7f937-115">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="7f937-116">Le tableau suivant répertorie les résolutions typiques des problèmes liés à la capacité.</span><span class="sxs-lookup"><span data-stu-id="7f937-116">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="7f937-117">Résolution standard pour les problèmes liés à la capacité</span><span class="sxs-lookup"><span data-stu-id="7f937-117">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f937-118">Problème</span><span class="sxs-lookup"><span data-stu-id="7f937-118">Issue</span></span></th>
<th><span data-ttu-id="7f937-119">Résolution possible</span><span class="sxs-lookup"><span data-stu-id="7f937-119">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f937-120">Utilisateurs distants ayant des performances audio/vidéo médiocres</span><span class="sxs-lookup"><span data-stu-id="7f937-120">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="7f937-121">Vérifiez si la bande passante appropriée est disponible sur les liaisons WAN et si la QoS est activée et configurée correctement.</span><span class="sxs-lookup"><span data-stu-id="7f937-121">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="7f937-122">Vérifiez les données QoE.</span><span class="sxs-lookup"><span data-stu-id="7f937-122">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f937-123">La réponse globale de l’environnement Lync est lente.</span><span class="sxs-lookup"><span data-stu-id="7f937-123">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="7f937-124">Exécutez des tests pour vérifier que les serveurs frontaux existants peuvent gérer le chargement.</span><span class="sxs-lookup"><span data-stu-id="7f937-124">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="7f937-125">Introduisez un nouveau serveur frontal le cas échéant. Vérifiez les temps de réponse de la base de données SQL et résolvez les causes des retards (par exemple, amélioration du disque e/s).</span><span class="sxs-lookup"><span data-stu-id="7f937-125">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7f937-126">Pour plus d’informations, reportez-vous à la section Guide de mise en réseau de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7f937-126">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="7f937-127">La capacité est affectée par la configuration du système et dépend des ressources physiques telles que la bande passante réseau.</span><span class="sxs-lookup"><span data-stu-id="7f937-127">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="7f937-128">Par exemple, si un environnement Lync est configuré pour effectuer une sauvegarde complète nocturne, il est nécessaire de veiller à ce qu’il soit possible de réduire l’impact sur les performances interactives de l’utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="7f937-128">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="7f937-129">La gestion de la capacité est le processus de conservation de la capacité d’un système dans des niveaux acceptables et répond aux problèmes suivants :</span><span class="sxs-lookup"><span data-stu-id="7f937-129">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="7f937-130">**La réaction aux modifications des exigences de capacité requise**   doit être ajustée pour tenir compte des modifications apportées au système ou à l’organisation.</span><span class="sxs-lookup"><span data-stu-id="7f937-130">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="7f937-131">Par exemple, si votre environnement décide de mettre en place une voix entreprise, le nombre et l’emplacement des passerelles de réseau téléphonique commuté (PSTN) et du réseau public commuté (RTC) seront très importants.</span><span class="sxs-lookup"><span data-stu-id="7f937-131">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="7f937-132">Si vous enverrez le trunking SIP (Session Initiation Protocol) ou le SIP direct, le design global sera considérablement modifié pour offrir les meilleures performances vocales pour l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="7f937-132">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="7f937-133">**Prévoir les exigences**   futures les exigences en matière de capacités évoluent dans le temps.</span><span class="sxs-lookup"><span data-stu-id="7f937-133">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="7f937-134">En effectuant le suivi des tendances, vous pouvez planifier des mises à jour à l’avance.</span><span class="sxs-lookup"><span data-stu-id="7f937-134">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="7f937-135">Par exemple, la bande passante disponible entre divers sites Lync doit être contrôlée pour créer un planning de référence.</span><span class="sxs-lookup"><span data-stu-id="7f937-135">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="7f937-136">Ce planning de référence vous permettra d’augmenter la quantité de bande passante que vous devez ajouter à ces liens, car le nombre d’utilisateurs dans ces sites distants augmente avec le temps.</span><span class="sxs-lookup"><span data-stu-id="7f937-136">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="7f937-137">Gestion de la disponibilité</span><span class="sxs-lookup"><span data-stu-id="7f937-137">Availability management</span></span>

<span data-ttu-id="7f937-138">La gestion de la disponibilité est le processus qui permet de garantir le bon respect de tout service informatique et d’offrir le niveau de service cohérent et fiable requis par le client.</span><span class="sxs-lookup"><span data-stu-id="7f937-138">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="7f937-139">La gestion de la disponibilité implique de limiter la perte de services et de vérifier que l’action appropriée est effectuée en cas de perte de service.</span><span class="sxs-lookup"><span data-stu-id="7f937-139">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="7f937-140">Dans un environnement Lync, vous voudrez peut-être savoir si le service voix entreprise est disponible, si les utilisateurs peuvent participer à des conférences planifiées, etc.</span><span class="sxs-lookup"><span data-stu-id="7f937-140">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="7f937-141">Un SLA définit une fréquence et une durée acceptables d’arrêts et autorise des périodes lorsque le système n’est pas disponible pour la maintenance planifiée.</span><span class="sxs-lookup"><span data-stu-id="7f937-141">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="7f937-142">Si vous devez fournir des rapports à votre gestion concernant la disponibilité des systèmes, ou si vous avez des pénalités financières ou d’autres pénalités associées à des cibles de disponibilité manquantes, vous devez enregistrer les données de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="7f937-142">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="7f937-143">Même si vous n’avez pas cette configuration, il est conseillé de savoir au moins le nombre d’échecs d’un système pendant une période donnée.</span><span class="sxs-lookup"><span data-stu-id="7f937-143">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="7f937-144">Par exemple, la disponibilité du système au cours des 12 derniers mois et le temps nécessaire à la récupération de chaque échec.</span><span class="sxs-lookup"><span data-stu-id="7f937-144">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="7f937-145">Ces informations vous permettront de mesurer et d’améliorer l’efficacité de votre équipe en réponse à une panne système.</span><span class="sxs-lookup"><span data-stu-id="7f937-145">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="7f937-146">Il peut également vous fournir des informations utiles en cas de litige.</span><span class="sxs-lookup"><span data-stu-id="7f937-146">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="7f937-147">Les mesures liées à la disponibilité sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f937-147">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="7f937-148">**Disponibilité**   en règle générale, il s’agit du temps d’accès d’un système ou d’un service par rapport au temps qu’il est fixé.</span><span class="sxs-lookup"><span data-stu-id="7f937-148">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="7f937-149">Elle est généralement exprimée en pourcentage.</span><span class="sxs-lookup"><span data-stu-id="7f937-149">It is typically expressed as a percentage.</span></span> <span data-ttu-id="7f937-150">(Il est possible que vous voyiez des références à « trois neuf » ou « cinq neuf ».</span><span class="sxs-lookup"><span data-stu-id="7f937-150">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="7f937-151">Celles-ci se réfèrent à la disponibilité de 99,9% ou 99,999%.)</span><span class="sxs-lookup"><span data-stu-id="7f937-151">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="7f937-152">**Fiabilité**   il s’agit d’une mesure du temps entre les échecs d’un système et est parfois exprimée en temps moyenne (ou moyenne) entre les échecs (MTBF).</span><span class="sxs-lookup"><span data-stu-id="7f937-152">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="7f937-153">**Temps de réparation**   il s’agit du temps nécessaire pour récupérer un service après une période d’indisponibilité et est souvent exprimé par le temps moyen de réparation (MTTR).</span><span class="sxs-lookup"><span data-stu-id="7f937-153">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="7f937-154">La disponibilité, la fiabilité et le temps de réparation sont liés comme suit :</span><span class="sxs-lookup"><span data-stu-id="7f937-154">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="7f937-155">**Disponibilité = (MTBF-MTTR)/MTBF**   (par exemple, si un serveur tombe sur une période de six mois et n’est pas disponible pendant une moyenne de 20 minutes, le temps de MTBF est d’au moins trois mois ou 90, et le MTTR est de 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="7f937-155">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="7f937-156">Par conséquent, la disponibilité = (90 jours – 20 minutes)/90 jours = 99,985%.</span><span class="sxs-lookup"><span data-stu-id="7f937-156">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="7f937-157">La gestion de la disponibilité est le processus de vérification de l’agrandissement et de la disponibilité de la disponibilité dans les paramètres définis dans les SLA.</span><span class="sxs-lookup"><span data-stu-id="7f937-157">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="7f937-158">La gestion de la disponibilité comprend les processus suivants :</span><span class="sxs-lookup"><span data-stu-id="7f937-158">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="7f937-159">**Surveillance**     de l’analyse du temps et des services indisponibles.</span><span class="sxs-lookup"><span data-stu-id="7f937-159">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="7f937-160">**La création de rapports**   de disponibilité doit être fournie régulièrement aux équipes gestion, utilisateurs et opérations.</span><span class="sxs-lookup"><span data-stu-id="7f937-160">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="7f937-161">Ce rapport doit mettre en évidence des tendances et identifier les domaines qui nécessitent une attention particulière.</span><span class="sxs-lookup"><span data-stu-id="7f937-161">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="7f937-162">Le rapport doit résumer la conformité aux cibles définies dans les SLA.</span><span class="sxs-lookup"><span data-stu-id="7f937-162">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="7f937-163">**Si la**disponibilité ne correspond pas aux cibles définies dans les SLA ou lorsque la tendance est une disponibilité réduite, le processus de gestion de la disponibilité doit planifier les étapes de remédiation.   </span><span class="sxs-lookup"><span data-stu-id="7f937-163">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="7f937-164">Cela devrait inclure le fait de travailler avec d’autres équipes responsables pour mettre en évidence les raisons des pannes et de planifier des actions de remédiation pour éviter toute réapparition des pannes.</span><span class="sxs-lookup"><span data-stu-id="7f937-164">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="7f937-165">Les mesures de capacité et de disponibilité sont des tâches répétées qui conviennent idéalement aux outils et scripts automatisés tels que Microsoft System Center Operations Manager (anciennement Microsoft Operations Manager), qui est abordé plus loin dans ce document.</span><span class="sxs-lookup"><span data-stu-id="7f937-165">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f937-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f937-166">See Also</span></span>


[<span data-ttu-id="7f937-167">Surveiller Lync Server 2013 avec System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="7f937-167">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

