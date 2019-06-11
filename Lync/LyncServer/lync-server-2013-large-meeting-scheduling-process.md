---
title: 'Lync Server 2013: processus de planification de grande réunion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af97cdbd07603c420780a92fbbe0a03c8a4d0520
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="8f2d7-102">Processus de planification de grande réunion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f2d7-102">Large-meeting scheduling process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f2d7-103">_**Dernière modification de la rubrique:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8f2d7-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8f2d7-104">Étant donné qu’une seule grande réunion à la fois est prise en charge sur le pool de réunions important, nous vous recommandons d’implémenter un processus de planification de réunion volumineux pour éviter les conflits de réunion importants.</span><span class="sxs-lookup"><span data-stu-id="8f2d7-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="8f2d7-105">L’objectif du processus de planification consiste à faciliter la configuration des réunions de grande envergure.</span><span class="sxs-lookup"><span data-stu-id="8f2d7-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="8f2d7-106">Cette fonctionnalité n’est pas fournie directement par les clients Lync Server ou Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8f2d7-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="8f2d7-107">Le recours au le système de tickets du support de votre organisation, le cas échéant, est l’une des méthodes disponibles pour mettre en œuvre cette procédure.</span><span class="sxs-lookup"><span data-stu-id="8f2d7-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="8f2d7-108">Pour les organisateurs de réunion de grande taille, la planification d’une réunion importante implique les étapes suivantes:</span><span class="sxs-lookup"><span data-stu-id="8f2d7-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="8f2d7-p102">Outre la liste de présentateurs, l’organisateur de réunion ou le délégué détermine l’heure, la durée et la taille d’une prochaine réunion. Si la taille de réunion prévue dépasse 250 utilisateurs ou pour garantir la meilleure expérience pour une réunion de moins de 250 utilisateurs, l’organisateur ou le délégué envoie une demande pour une grande réunion.</span><span class="sxs-lookup"><span data-stu-id="8f2d7-p102">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="8f2d7-p103">Le personnel chargé de la planification vérifie si la date et l’heure demandées sont disponibles. Comme nous ne prenons en charge qu’une seule grande réunion à la fois sur le pool dédié, le personnel de planification doit vérifier le calendrier des grandes réunions pour déterminer si une autre réunion est planifiée à la date et à l’heure demandées. Si l’heure demandée est disponible, le personnel approuve la demande de réunion.</span><span class="sxs-lookup"><span data-stu-id="8f2d7-p103">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="8f2d7-114">S’il s’agit d’une demande approuvée, le personnel de planification (à l’aide des informations d’identification de la réserve dédiée) utilise le complément réunion en ligne pour Lync 2013 avec Outlook pour configurer une réunion sur le pool de réunion volumineux dédié.</span><span class="sxs-lookup"><span data-stu-id="8f2d7-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="8f2d7-115">L’URL à utiliser pour participer à la réunion est fournie par le demandeur dans le cadre de l’avis d’approbation.</span><span class="sxs-lookup"><span data-stu-id="8f2d7-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="8f2d7-p105">L’organisateur de réunion ou le délégué utilise Outlook pour planifier la réunion suivante en ajoutant l’URL de l’invitation à participer à la réunion. L’organisateur de réunion ou le délégué spécifie alors les utilisateurs à inviter et envoie les invitations à la réunion.</span><span class="sxs-lookup"><span data-stu-id="8f2d7-p105">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation. The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="8f2d7-118">La figure suivante illustre un flux de travail de demande et d’approbation standard pour planifier des réunions de grande taille.</span><span class="sxs-lookup"><span data-stu-id="8f2d7-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="8f2d7-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d] (images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="8f2d7-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

