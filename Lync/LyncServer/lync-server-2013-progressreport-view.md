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
ms.openlocfilehash: ac09e1b22e4807b039daf4b5da4778a54cb91d4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="f1b24-102">Vue ProgressReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1b24-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1b24-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f1b24-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f1b24-104">L’affichage ProgressReport stocke les informations relatives aux sessions terminées.</span><span class="sxs-lookup"><span data-stu-id="f1b24-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="f1b24-105">Les rapports d’avancement sont créés uniquement pour les appels et les sessions que Lync Server 2013 considère comme utiles à des fins de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="f1b24-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="f1b24-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1b24-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1b24-107">Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs mais aux messages qui indiquent l’état des appels ou des messages.</span><span class="sxs-lookup"><span data-stu-id="f1b24-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1b24-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="f1b24-108">Column</span></span></th>
<th><span data-ttu-id="f1b24-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="f1b24-109">Data Type</span></span></th>
<th><span data-ttu-id="f1b24-110">Détails</span><span class="sxs-lookup"><span data-stu-id="f1b24-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1b24-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="f1b24-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f1b24-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f1b24-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f1b24-p102">Heure à laquelle l’erreur s’est produite. Utilisé conjointement à ErrorReportSeq pour identifier une erreur de manière unique.</span><span class="sxs-lookup"><span data-stu-id="f1b24-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1b24-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f1b24-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f1b24-116">int</span><span class="sxs-lookup"><span data-stu-id="f1b24-116">int</span></span></p></td>
<td><p><span data-ttu-id="f1b24-p103">Numéro d’identification de l’erreur. Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.</span><span class="sxs-lookup"><span data-stu-id="f1b24-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1b24-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f1b24-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f1b24-120">int</span><span class="sxs-lookup"><span data-stu-id="f1b24-120">int</span></span></p></td>
<td><p><span data-ttu-id="f1b24-121">ID utilisé pour identifier le rapport d’avancement.</span><span class="sxs-lookup"><span data-stu-id="f1b24-121">ID to identify the progress report.</span></span> <span data-ttu-id="f1b24-122">Utilisé pour distinguer des rapports d’avancement du même rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="f1b24-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1b24-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="f1b24-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="f1b24-124">int</span><span class="sxs-lookup"><span data-stu-id="f1b24-124">int</span></span></p></td>
<td><p><span data-ttu-id="f1b24-125">ID de diagnostic pour le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="f1b24-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1b24-126"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="f1b24-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="f1b24-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f1b24-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f1b24-128">Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="f1b24-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1b24-129"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="f1b24-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="f1b24-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f1b24-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f1b24-131">Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="f1b24-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1b24-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="f1b24-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="f1b24-133">unique</span><span class="sxs-lookup"><span data-stu-id="f1b24-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f1b24-134">Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="f1b24-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1b24-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="f1b24-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f1b24-136">int</span><span class="sxs-lookup"><span data-stu-id="f1b24-136">int</span></span></p></td>
<td><p><span data-ttu-id="f1b24-137">Durée (en millisecondes) requise pour qu’un composant spécifique rejoigne une conférence.</span><span class="sxs-lookup"><span data-stu-id="f1b24-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1b24-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="f1b24-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="f1b24-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="f1b24-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="f1b24-140">Informations supplémentaires sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="f1b24-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

