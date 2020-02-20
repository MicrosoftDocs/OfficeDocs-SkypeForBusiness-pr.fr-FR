---
title: 'Lync Server 2013 : rapports sur l’utilisation du système'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System usage reports
ms:assetid: 187d316d-2456-417e-b636-05527a18ef06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558618(v=OCS.15)
ms:contentKeyID: 48183529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b020217863dd4adf04a8e91041dcae8fa078ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-usage-reports-in-lync-server-2013"></a><span data-ttu-id="cf367-102">Rapports sur l’utilisation du système dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf367-102">System usage reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf367-103">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="cf367-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="cf367-104">Les rapports d’utilisation du système fournissent des informations relatives à l’utilisation du système en fonction des données d’enregistrement des détails des appels collectées par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf367-104">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Lync Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cf367-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="cf367-105">In This Section</span></span>

  - [<span data-ttu-id="cf367-106">Rapport d’enregistrement de l’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf367-106">User Registration Report in Lync Server 2013</span></span>](lync-server-2013-user-registration-report.md)
    
    <span data-ttu-id="cf367-107">Fournit un résumé de la connectivité utilisateur au déploiement Lync Server 2013 en fonction des événements d’inscription, tels que les ouvertures de session utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cf367-107">Provides a summary of user connectivity to the Lync Server 2013 deployment based on registration events such as user logons.</span></span> <span data-ttu-id="cf367-108">Le rapport permet d’afficher les ouvertures de session internes et externes et de comparer le nombre d’utilisateurs qui se sont connectés à Lync Server 2013 avec le nombre d’utilisateurs ayant réellement utilisé le service pendant qu’ils ont ouvert une session.</span><span class="sxs-lookup"><span data-stu-id="cf367-108">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Lync Server 2013 with the number of users who actually used the service while they were logged on.</span></span>

  - [<span data-ttu-id="cf367-109">Rapport de synthèse des activités P2P dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf367-109">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="cf367-p102">Fournit une synthèse des sessions de messagerie instantanée d’égal à égal, audio, vidéo, de transfert de fichiers et de partage d’applications. Les sessions d’égal à égal sont des sessions impliquant seulement deux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cf367-p102">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions. Peer-to-peer sessions are sessions involving just two users.</span></span>

  - [<span data-ttu-id="cf367-112">Rapport de synthèse de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf367-112">Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-conference-summary-report.md)
    
    <span data-ttu-id="cf367-113">Fournit une synthèse de toutes les activités de conférence.</span><span class="sxs-lookup"><span data-stu-id="cf367-113">Provides a summary of all conference activities.</span></span> <span data-ttu-id="cf367-114">Les conférences sont des sessions qui impliquent plus de deux personnes.</span><span class="sxs-lookup"><span data-stu-id="cf367-114">Conferences are sessions involving three or more people.</span></span>

  - [<span data-ttu-id="cf367-115">Rapport de synthèse de conférence RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf367-115">PSTN Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-pstn-conference-summary-report.md)
    
    <span data-ttu-id="cf367-p104">Fournit une synthèse de toutes les conférences PSTN. Il s’agit de conférences où au moins un utilisateur compose un numéro sur le réseau téléphonique commuté (PSTN). Ces conférences sont aussi appelées *conférence rendez-vous*.</span><span class="sxs-lookup"><span data-stu-id="cf367-p104">Provides a summary of all PSTN conferences. These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as *dial-in conferencing*.</span></span>

  - [<span data-ttu-id="cf367-118">Rapport d’utilisation de Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf367-118">Response Group Usage Report in Lync Server 2013</span></span>](lync-server-2013-response-group-usage-report.md)
    
    <span data-ttu-id="cf367-119">Fournit un résumé de l’utilisation de Response Group.</span><span class="sxs-lookup"><span data-stu-id="cf367-119">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="cf367-120">L’application Response Group vous permet d’acheminer automatiquement les appels téléphoniques vers des entités telles qu’un support technique ou un service clientèle.</span><span class="sxs-lookup"><span data-stu-id="cf367-120">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>

  - [<span data-ttu-id="cf367-121">Rapport d’inventaire de téléphonie IP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf367-121">IP Phone Inventory Report in Lync Server 2013</span></span>](lync-server-2013-ip-phone-inventory-report.md)
    
    <span data-ttu-id="cf367-122">Fournit des informations sur les téléphones IP actuellement en cours d’utilisation dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="cf367-122">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="cf367-123">Le rapport est basé sur les inscriptions et les connexions des téléphones.</span><span class="sxs-lookup"><span data-stu-id="cf367-123">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="cf367-124">Il ne doit pas être considéré comme un inventaire complet.</span><span class="sxs-lookup"><span data-stu-id="cf367-124">It should not be considered a complete inventory.</span></span> <span data-ttu-id="cf367-125">Par exemple, vous ne possédez peut-être plus certains téléphones qui sont encore répertoriés dans le rapport (car ils se sont connectés au moins une fois).</span><span class="sxs-lookup"><span data-stu-id="cf367-125">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="cf367-126">De même, vous pouvez également avoir de nouveaux téléphones qui ne s’affichent pas dans le rapport simplement parce que les utilisateurs n’ont pas encore ouvert de session sur Lync Server avec leur nouveau téléphone.</span><span class="sxs-lookup"><span data-stu-id="cf367-126">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Lync Server with their new phones yet.</span></span>

  - [<span data-ttu-id="cf367-127">Rapport de contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf367-127">Call Admission Control Report in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-report.md)
    
    <span data-ttu-id="cf367-p107">Fournit une liste d’activités d’égal à égal et de conférence qui utilisent le contrôle d’admission des appels. Le contrôle d’admission des appels (CAC, Call Admission Control) permet de déterminer si les sessions de communication en temps réel, comme les appels audio et vidéo, doivent ou non être autorisées, en fonction des restrictions de bande passante.</span><span class="sxs-lookup"><span data-stu-id="cf367-p107">Provides a list of peer-to-peer and conference activities that use call admission control. Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

