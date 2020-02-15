---
title: 'Lync Server 2013 : vue ProgressReport'
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
ms.openlocfilehash: 916fb459e71460249b47719ab4a4c07f8d082e4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="d06d5-102">Vue ProgressReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d06d5-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d06d5-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d06d5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d06d5-104">L’affichage ProgressReport stocke les informations relatives aux sessions terminées.</span><span class="sxs-lookup"><span data-stu-id="d06d5-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="d06d5-105">Les rapports d’avancement sont créés uniquement pour les appels et les sessions que Lync Server 2013 considère comme utiles à des fins de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="d06d5-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="d06d5-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d06d5-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d06d5-107">Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs mais aux messages qui indiquent l’état des appels ou des messages.</span><span class="sxs-lookup"><span data-stu-id="d06d5-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d06d5-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="d06d5-108">Column</span></span></th>
<th><span data-ttu-id="d06d5-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="d06d5-109">Data Type</span></span></th>
<th><span data-ttu-id="d06d5-110">Détails</span><span class="sxs-lookup"><span data-stu-id="d06d5-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d06d5-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="d06d5-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d06d5-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d06d5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d06d5-p102">Heure à laquelle l’erreur s’est produite. Utilisé conjointement à ErrorReportSeq pour identifier une erreur de manière unique.</span><span class="sxs-lookup"><span data-stu-id="d06d5-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d06d5-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d06d5-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d06d5-116">int</span><span class="sxs-lookup"><span data-stu-id="d06d5-116">int</span></span></p></td>
<td><p><span data-ttu-id="d06d5-p103">Numéro d’identification de l’erreur. Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.</span><span class="sxs-lookup"><span data-stu-id="d06d5-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d06d5-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d06d5-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d06d5-120">int</span><span class="sxs-lookup"><span data-stu-id="d06d5-120">int</span></span></p></td>
<td><p><span data-ttu-id="d06d5-121">ID utilisé pour identifier le rapport d’avancement.</span><span class="sxs-lookup"><span data-stu-id="d06d5-121">ID to identify the progress report.</span></span> <span data-ttu-id="d06d5-122">Utilisé pour distinguer des rapports d’avancement du même rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="d06d5-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d06d5-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="d06d5-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="d06d5-124">int</span><span class="sxs-lookup"><span data-stu-id="d06d5-124">int</span></span></p></td>
<td><p><span data-ttu-id="d06d5-125">ID de diagnostic pour le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="d06d5-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d06d5-126"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="d06d5-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="d06d5-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d06d5-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d06d5-128">Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="d06d5-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d06d5-129"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="d06d5-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="d06d5-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d06d5-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d06d5-131">Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="d06d5-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d06d5-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="d06d5-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="d06d5-133">unique</span><span class="sxs-lookup"><span data-stu-id="d06d5-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d06d5-134">Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="d06d5-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d06d5-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="d06d5-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d06d5-136">int</span><span class="sxs-lookup"><span data-stu-id="d06d5-136">int</span></span></p></td>
<td><p><span data-ttu-id="d06d5-137">Durée (en millisecondes) requise pour qu’un composant spécifique rejoigne une conférence.</span><span class="sxs-lookup"><span data-stu-id="d06d5-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d06d5-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="d06d5-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="d06d5-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="d06d5-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="d06d5-140">Informations supplémentaires sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="d06d5-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

