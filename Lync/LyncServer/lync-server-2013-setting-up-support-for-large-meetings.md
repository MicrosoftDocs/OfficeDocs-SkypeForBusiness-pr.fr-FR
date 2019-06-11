---
title: 'Lync Server 2013: configuration de la prise en charge des réunions de grande envergure'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03196c705253320e31e2483cc89b2aca386ff1af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="825cf-102">Configuration de la prise en charge des réunions de grande envergure dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="825cf-102">Setting up support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="825cf-103">_**Dernière modification de la rubrique:** 2014-05-12_</span><span class="sxs-lookup"><span data-stu-id="825cf-103">_**Topic Last Modified:** 2014-05-12_</span></span>

<span data-ttu-id="825cf-104">La prise en charge de grandes réunions d’un maximum de 1000 utilisateurs nécessite la création d’une topologie appropriée, la mise en œuvre de matériels et de logiciels requis et la configuration de l’environnement de manière appropriée.</span><span class="sxs-lookup"><span data-stu-id="825cf-104">Supporting large meetings of up to 1000 users requires creating an appropriate topology, meeting hardware and software prerequisites, and configuring the environment appropriately.</span></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="825cf-105">Conditions requises pour la topologie</span><span class="sxs-lookup"><span data-stu-id="825cf-105">Topology Requirements</span></span>

<span data-ttu-id="825cf-106">Une grande réunion nécessite au moins un serveur frontal et un serveur principal.</span><span class="sxs-lookup"><span data-stu-id="825cf-106">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="825cf-107">Toutefois, pour garantir une haute disponibilité, nous vous recommandons de disposer d’un pool de serveurs frontal à deux serveurs dorsaux en miroir.</span><span class="sxs-lookup"><span data-stu-id="825cf-107">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers.</span></span>

<span data-ttu-id="825cf-108">Le compte d’utilisateur de l’utilisateur qui héberge les grandes réunions doit être hébergé dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="825cf-108">The user who hosts the large meetings must have their user account homed in this pool.</span></span> <span data-ttu-id="825cf-109">Cependant, nous ne recommandons d’héberger d’autres comptes d’utilisateur dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="825cf-109">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="825cf-110">Utilisez-le uniquement pour les grandes réunions.</span><span class="sxs-lookup"><span data-stu-id="825cf-110">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="825cf-111">Il est recommandé de créer un compte d’utilisateur spécial dans ce pool, qui ne sera utilisé que pour héberger les grandes réunions.</span><span class="sxs-lookup"><span data-stu-id="825cf-111">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="825cf-112">Étant donné que le paramètre des grandes réunions est optimisé pour les performances, son utilisation en tant qu’utilisateur normal peut entraîner des problèmes, comme une incapacité à promouvoir une session P2P dans une réunion lorsqu’un point de terminaison RTC est impliqué.</span><span class="sxs-lookup"><span data-stu-id="825cf-112">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>

<span data-ttu-id="825cf-113">La gestion d’un pool avec deux serveurs frontaux nécessite une attention particulière.</span><span class="sxs-lookup"><span data-stu-id="825cf-113">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="825cf-114">Pour plus d’informations, reportez-vous à la rubrique [topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="825cf-114">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="825cf-115">De plus, si vous voulez fournir la sauvegarde de récupération d’urgence et le basculement pour le pool utilisé pour les grandes réunions, vous pouvez l’associer à un autre pool dédié configuré de la même façon dans d’autres centres de données.</span><span class="sxs-lookup"><span data-stu-id="825cf-115">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="825cf-116">Pour plus d’informations, reportez-vous à [planification d’une haute disponibilité et reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="825cf-116">For details, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<span data-ttu-id="825cf-117">![Configuration du pool de réunions volumineux] (images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configuration du pool de réunions volumineux")</span><span class="sxs-lookup"><span data-stu-id="825cf-117">![Large Meetings pool configuration](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Large Meetings pool configuration")</span></span>

<span data-ttu-id="825cf-118">Autres éléments pour la topologie :</span><span class="sxs-lookup"><span data-stu-id="825cf-118">Additional notes about the topology include:</span></span>

  - <span data-ttu-id="825cf-119">Un partage de fichiers est nécessaire pour le stockage du contenu de la réunion et, si Archiving Server est déployé et activé, pour le stockage des fichiers d’archive.</span><span class="sxs-lookup"><span data-stu-id="825cf-119">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="825cf-120">Le partage de fichiers peut être dédié au pool ou peut être le même que celui utilisé par un autre pool du site dans lequel le pool est déployé.</span><span class="sxs-lookup"><span data-stu-id="825cf-120">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="825cf-121">Pour plus d’informations sur la configuration du partage de fichiers, voir [configurer le stockage de fichiers pour Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="825cf-121">For details about configuring the file share, see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>

  - <span data-ttu-id="825cf-122">Office Web Apps Server est requis pour l’activation de la fonctionnalité présentation PowerPoint dans les réunions de grande envergure.</span><span class="sxs-lookup"><span data-stu-id="825cf-122">A Office Web Apps Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="825cf-123">Office Web Apps Server peut être dédié au pool de réunions de grande taille ou il peut s’agir du serveur Office Web Apps utilisé par d’autres pools sur le site dans lequel le pool dédié est déployé.</span><span class="sxs-lookup"><span data-stu-id="825cf-123">The Office Web Apps Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server used by other pools at the site in which the dedicated pool is deployed.</span></span>

  - <span data-ttu-id="825cf-124">L’équilibrage de charge des serveurs frontaux nécessite l’équilibrage de charge matérielle pour le trafic HTTP (le téléchargement de contenu de la réunion).</span><span class="sxs-lookup"><span data-stu-id="825cf-124">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="825cf-125">L’équilibrage de charge DNS est recommandé pour le trafic SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="825cf-125">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="825cf-126">Pour plus d’informations, voir [exigences d’équilibrage de charge pour Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="825cf-126">For details see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="825cf-127">Si vous souhaitez utiliser la surveillance du serveur pour le pool de réunions importantes, nous vous recommandons d’utiliser le serveur de surveillance et sa base de données partagés sur tous les pools de serveurs frontaux dans le déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="825cf-127">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Lync Server deployment.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="825cf-128">Configuration matérielle et logicielle requise</span><span class="sxs-lookup"><span data-stu-id="825cf-128">Hardware and Software Requirements</span></span>

<span data-ttu-id="825cf-129">La configuration matérielle requise pour les serveurs d’un pool de réunion volumineux dédié est identique à celle de vos autres serveurs Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="825cf-129">The hardware requirements for servers in a dedicated large-meeting pool are the same as for your other Lync Server 2013 servers.</span></span> <span data-ttu-id="825cf-130">Pour plus d’informations sur la configuration matérielle requise, voir «[plateformes matérielles serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="825cf-130">For details about hardware requirements, see "[Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="825cf-131">Les serveurs d’un pool de réunion dédié volumineux doivent respecter toutes les exigences logicielles de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="825cf-131">Servers in a dedicated large-meeting pool must meet all Lync Server 2013 software requirements.</span></span> <span data-ttu-id="825cf-132">Pour plus d’informations sur la configuration logicielle requise, veuillez consulter la documentation suivante:</span><span class="sxs-lookup"><span data-stu-id="825cf-132">For details about software requirements, please see the following documentation:</span></span>

  - [<span data-ttu-id="825cf-133">Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="825cf-133">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="825cf-134">Prise en charge du logiciel de base de données dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="825cf-134">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="825cf-135">Autre configuration logicielle requise pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="825cf-135">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

<span data-ttu-id="825cf-136">De plus, Lync Server 2013 et tous les clients Lync Server 2013 doivent disposer des dernières mises à jour.</span><span class="sxs-lookup"><span data-stu-id="825cf-136">Additionally, both Lync Server 2013 and all Lync Server 2013 clients must have the latest updates.</span></span>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="825cf-137">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="825cf-137">Configuration Requirements</span></span>

<span data-ttu-id="825cf-138">Nous vous recommandons de créer une nouvelle stratégie de conférence spécifique pour les réunions de grande taille, puis d’affecter la stratégie de conférence aux utilisateurs qui sont hébergés sur le pool de réunion volumineux dédié.</span><span class="sxs-lookup"><span data-stu-id="825cf-138">We recommend creating a new conferencing policy specifically for large meetings, and then assigning the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="825cf-139">Configurez la stratégie de conférence avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="825cf-139">Configure the conferencing policy using the following settings:</span></span>

  - <span data-ttu-id="825cf-140">Définissez l’option **MaxMeetingSize** sur **1000**.</span><span class="sxs-lookup"><span data-stu-id="825cf-140">Set the **MaxMeetingSize** option to **1000**.</span></span> <span data-ttu-id="825cf-141">(La valeur par défaut est **250**.)</span><span class="sxs-lookup"><span data-stu-id="825cf-141">(The default is **250**.)</span></span>

  - <span data-ttu-id="825cf-142">Définissez l’option **AllowLargeMeetings** sur **True**.</span><span class="sxs-lookup"><span data-stu-id="825cf-142">Set the **AllowLargeMeetings** option to **True**.</span></span>

  - <span data-ttu-id="825cf-143">Définissez l’option **EnableAppDesktopSharing** sur **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="825cf-143">Set the **EnableAppDesktopSharing** option to **None**.</span></span>

  - <span data-ttu-id="825cf-144">Définissez l’option **AllowUserToScheduleMeetingsWithAppSharing** sur **False**.</span><span class="sxs-lookup"><span data-stu-id="825cf-144">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>

  - <span data-ttu-id="825cf-145">Définissez l’option **AllowSharedNotes** sur **False**.</span><span class="sxs-lookup"><span data-stu-id="825cf-145">Set the **AllowSharedNotes** option to **False**.</span></span>

  - <span data-ttu-id="825cf-146">Définissez l’option **AllowAnnotations** sur **False**.</span><span class="sxs-lookup"><span data-stu-id="825cf-146">Set the **AllowAnnotations** option to **False**.</span></span>

  - <span data-ttu-id="825cf-147">Définissez l’option **DisablePowerPointAnnotations** sur **True**.</span><span class="sxs-lookup"><span data-stu-id="825cf-147">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>

  - <span data-ttu-id="825cf-148">Définissez l’option **AllowMultiview** sur **False**.</span><span class="sxs-lookup"><span data-stu-id="825cf-148">Set the **AllowMultiview** option to **False**.</span></span>

  - <span data-ttu-id="825cf-149">Définissez l’option **EnableMultiviewJoin** sur **False**.</span><span class="sxs-lookup"><span data-stu-id="825cf-149">Set the **EnableMultiviewJoin** option to **False**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="825cf-150">La prise en charge des réunions 1000 de grande envergure dans Lync Server 2013 nécessite le paramètre <STRONG>AllowLargeMeetings</STRONG> de la stratégie de conférence pour le planificateur de conférences sur true.</span><span class="sxs-lookup"><span data-stu-id="825cf-150">The support for 1000 user large meetings in Lync Server 2013 requires the <STRONG>AllowLargeMeetings</STRONG> setting in the conferencing policy for the meeting scheduler to be set to true.</span></span> <span data-ttu-id="825cf-151">Lorsque ce paramètre est défini sur true, l’expérience Lync sera optimisée pour les réunions de grande envergure lorsque les utilisateurs rejoignent une telle réunion.</span><span class="sxs-lookup"><span data-stu-id="825cf-151">When this setting is set to true, the Lync experience will be optimized for extra large meetings when users joins such meeting.</span></span> <span data-ttu-id="825cf-152">Plus précisément, dans une grande réunion, Lync n’affichera pas la première ou la mise à jour de la liste des participants à la réunion complète, qui est un goulet d’étranglement des performances pour le client et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="825cf-152">Specifically, in a large meeting, Lync will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Lync Server 2013.</span></span> <span data-ttu-id="825cf-153">À la place, Lync affiche uniquement les informations relatives à l’utilisateur et la liste des présentateurs de la réunion.</span><span class="sxs-lookup"><span data-stu-id="825cf-153">Instead, Lync will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="825cf-154">Lync va tout de même afficher le nombre total de participants disponibles lors des réunions de grande envergure.</span><span class="sxs-lookup"><span data-stu-id="825cf-154">Lync will still properly shows total number of participants available in the large meetings.</span></span>



</div>

<span data-ttu-id="825cf-155">À l’exception du paramètre **Taille maximale de la réunion**, tous les autres paramètres de stratégie de conférence spécifiés ici sont nécessaires pour désactiver les fonctions de conférence qui ne sont pas nécessaires pour les grandes réunions.</span><span class="sxs-lookup"><span data-stu-id="825cf-155">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>

<span data-ttu-id="825cf-156">Par ailleurs, vous devez configurer le pool de réunion dédié de grande taille de sorte que chaque utilisateur de Lync Server 2013 hébergé sur le pool et responsable de la gestion de la planification de la réunion dispose des autorisations appropriées.</span><span class="sxs-lookup"><span data-stu-id="825cf-156">Additionally, you need to configure the dedicated large-meeting pool so that each Lync Server 2013 user that is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="825cf-157">À cet effet, procédez ainsi :</span><span class="sxs-lookup"><span data-stu-id="825cf-157">To do this, do the following:</span></span>

  - <span data-ttu-id="825cf-p114">Définissez l’option **Désigné comme présentateur** sur **Aucun**. En général, parmi tous les participants, un ou plusieurs utilisateurs sont des présentateurs. Les participants ne doivent pas être admis automatiquement dans des grandes réunions en tant que présentateurs. Les présentateurs doivent être désignés explicitement lors de la planification de la réunion ou promus explicitement lors de la réunion.</span><span class="sxs-lookup"><span data-stu-id="825cf-p114">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>

  - <span data-ttu-id="825cf-161">Assurez-vous que la case à cocher **Type de conférence affecté par défaut** n’est pas activée.</span><span class="sxs-lookup"><span data-stu-id="825cf-161">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="825cf-162">Ce paramètre détermine si le complément réunion en ligne pour Lync 2013 planifie toujours des conférences à l’aide de la Conférence affectée de l’organisateur, ce qui signifie que les réunions planifiées ont la même URL et les mêmes informations audio.</span><span class="sxs-lookup"><span data-stu-id="825cf-162">This setting controls whether the Online Meeting Add-in for Lync 2013 always schedules conferences using the organizer’s assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="825cf-163">Dans des scénarios de collaboration en petit groupe, l’utilisation de ce type de conférence est pratique, car une conférence individuelle est affectée à chacun, et l’URL pour participer, ainsi que les informations audio constantes, permettant de rejoindre facilement la réunion.</span><span class="sxs-lookup"><span data-stu-id="825cf-163">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="825cf-164">En revanche, dans des scénarios de grande réunion, l’équipe de support planifie les grandes réunions avec un ensemble d’informations d’identification d’utilisateur et fournit les URL et les informations audio aux demandeurs de la réunion.</span><span class="sxs-lookup"><span data-stu-id="825cf-164">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="825cf-165">Dans ce cas, l’utilisation d’une URL différente pour rejoindre chaque réunion est préférable.</span><span class="sxs-lookup"><span data-stu-id="825cf-165">In this case, using a different URL to join each meeting works better.</span></span>

  - <span data-ttu-id="825cf-166">Vérifiez que la case à cocher **Admettre les utilisateurs anonymes par défaut** n’est pas activée, sauf si elle est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="825cf-166">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="825cf-167">Ce paramètre affecte le type d’accès par défaut à la réunion planifié par le complément réunion en ligne pour Lync 2013 quand vous n’utilisez pas de conférence affectée.</span><span class="sxs-lookup"><span data-stu-id="825cf-167">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Lync 2013 when not using an assigned conference.</span></span> <span data-ttu-id="825cf-168">L’option appropriée pour ce paramètre dépend des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="825cf-168">The appropriate option for this setting depends on your organization’s needs.</span></span> <span data-ttu-id="825cf-169">Si les grandes réunions de votre organisation sont des réunions internes, ne sélectionnez pas cette option.</span><span class="sxs-lookup"><span data-stu-id="825cf-169">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="825cf-170">Si la plupart des grandes réunions nécessitent la participation d’utilisateurs externes, sélectionnez cette option.</span><span class="sxs-lookup"><span data-stu-id="825cf-170">If most large meetings require that external users be able to join, select this option.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

