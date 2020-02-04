---
title: 'Affichage Lync Server 2013 : ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa8d73981490503b26b77b79be6f42aab77703e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="37146-102">Affichage ProgressReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37146-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37146-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="37146-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="37146-104">L’affichage ProgressReport stocke les informations sur les sessions terminées.</span><span class="sxs-lookup"><span data-stu-id="37146-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="37146-105">Les rapports de progression seront écrits uniquement pour les appels et les sessions que Lync Server 2013 détermine peut être utile à des fins de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="37146-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="37146-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37146-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37146-107">Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs, mais aux messages indiquant l’état des appels ou des messages.</span><span class="sxs-lookup"><span data-stu-id="37146-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37146-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="37146-108">Column</span></span></th>
<th><span data-ttu-id="37146-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="37146-109">Data Type</span></span></th>
<th><span data-ttu-id="37146-110">Détails</span><span class="sxs-lookup"><span data-stu-id="37146-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37146-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="37146-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="37146-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="37146-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="37146-113">L’heure de l’erreur s’est produite.</span><span class="sxs-lookup"><span data-stu-id="37146-113">Time of error occurred.</span></span> <span data-ttu-id="37146-114">Utilisé conjointement avec ErrorReportSeq pour identifier de manière unique une erreur.</span><span class="sxs-lookup"><span data-stu-id="37146-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37146-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="37146-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="37146-116">int</span><span class="sxs-lookup"><span data-stu-id="37146-116">int</span></span></p></td>
<td><p><span data-ttu-id="37146-117">Numéro d’identification pour identifier l’erreur.</span><span class="sxs-lookup"><span data-stu-id="37146-117">ID number to identify the error.</span></span> <span data-ttu-id="37146-118">Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.</span><span class="sxs-lookup"><span data-stu-id="37146-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37146-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="37146-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="37146-120">int</span><span class="sxs-lookup"><span data-stu-id="37146-120">int</span></span></p></td>
<td><p><span data-ttu-id="37146-121">ID pour identifier le rapport de progression.</span><span class="sxs-lookup"><span data-stu-id="37146-121">ID to identify the progress report.</span></span> <span data-ttu-id="37146-122">Permet de distinguer les rapports de progression d’un même rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="37146-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37146-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="37146-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="37146-124">int</span><span class="sxs-lookup"><span data-stu-id="37146-124">int</span></span></p></td>
<td><p><span data-ttu-id="37146-125">ID de diagnostic du rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="37146-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37146-126"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="37146-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="37146-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="37146-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="37146-128">Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="37146-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37146-129"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="37146-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="37146-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="37146-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="37146-131">Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="37146-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37146-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="37146-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="37146-133">identificateur</span><span class="sxs-lookup"><span data-stu-id="37146-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="37146-134">Identifiant unique permettant de corréler les informations de connexion aux différents composants participant à une conférence.</span><span class="sxs-lookup"><span data-stu-id="37146-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37146-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="37146-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="37146-136">int</span><span class="sxs-lookup"><span data-stu-id="37146-136">int</span></span></p></td>
<td><p><span data-ttu-id="37146-137">Durée (en millisecondes) requise pour un composant spécifique pour participer à une conférence.</span><span class="sxs-lookup"><span data-stu-id="37146-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37146-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="37146-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="37146-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="37146-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="37146-140">Informations supplémentaires sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="37146-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

