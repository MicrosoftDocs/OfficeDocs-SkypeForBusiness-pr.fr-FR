---
title: 'Lync Server 2013 : vue ProgressReport'
description: 'Lync Server 2013 : vue ProgressReport.'
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
ms.openlocfilehash: b95086012f254499644e778e43cafdf70ffc8f9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579790"
---
# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="9bf13-103">Vue ProgressReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9bf13-103">ProgressReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bf13-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9bf13-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9bf13-105">L’affichage ProgressReport stocke les informations relatives aux sessions terminées.</span><span class="sxs-lookup"><span data-stu-id="9bf13-105">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="9bf13-106">Les rapports d’avancement sont créés uniquement pour les appels et les sessions que Lync Server 2013 considère comme utiles à des fins de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="9bf13-106">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="9bf13-107">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9bf13-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9bf13-108">Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs mais aux messages qui indiquent l’état des appels ou des messages.</span><span class="sxs-lookup"><span data-stu-id="9bf13-108">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9bf13-109">Colonne</span><span class="sxs-lookup"><span data-stu-id="9bf13-109">Column</span></span></th>
<th><span data-ttu-id="9bf13-110">Type de données</span><span class="sxs-lookup"><span data-stu-id="9bf13-110">Data Type</span></span></th>
<th><span data-ttu-id="9bf13-111">Détails</span><span class="sxs-lookup"><span data-stu-id="9bf13-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9bf13-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="9bf13-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9bf13-113">DateHeure</span><span class="sxs-lookup"><span data-stu-id="9bf13-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="9bf13-p102">Heure à laquelle l’erreur s’est produite. Utilisé conjointement à ErrorReportSeq pour identifier une erreur de manière unique.</span><span class="sxs-lookup"><span data-stu-id="9bf13-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf13-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9bf13-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9bf13-117">int</span><span class="sxs-lookup"><span data-stu-id="9bf13-117">int</span></span></p></td>
<td><p><span data-ttu-id="9bf13-p103">Numéro d’identification de l’erreur. Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.</span><span class="sxs-lookup"><span data-stu-id="9bf13-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf13-120"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9bf13-120"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9bf13-121">int</span><span class="sxs-lookup"><span data-stu-id="9bf13-121">int</span></span></p></td>
<td><p><span data-ttu-id="9bf13-122">ID utilisé pour identifier le rapport d’avancement.</span><span class="sxs-lookup"><span data-stu-id="9bf13-122">ID to identify the progress report.</span></span> <span data-ttu-id="9bf13-123">Utilisé pour distinguer des rapports d’avancement du même rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="9bf13-123">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf13-124"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="9bf13-124"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="9bf13-125">int</span><span class="sxs-lookup"><span data-stu-id="9bf13-125">int</span></span></p></td>
<td><p><span data-ttu-id="9bf13-126">ID de diagnostic pour le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="9bf13-126">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf13-127"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="9bf13-127"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="9bf13-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9bf13-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9bf13-129">Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="9bf13-129">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf13-130"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="9bf13-130"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="9bf13-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9bf13-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9bf13-132">Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="9bf13-132">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf13-133"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="9bf13-133"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="9bf13-134">unique</span><span class="sxs-lookup"><span data-stu-id="9bf13-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9bf13-135">Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="9bf13-135">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf13-136"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="9bf13-136"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9bf13-137">int</span><span class="sxs-lookup"><span data-stu-id="9bf13-137">int</span></span></p></td>
<td><p><span data-ttu-id="9bf13-138">Durée (en millisecondes) requise pour qu’un composant spécifique rejoigne une conférence.</span><span class="sxs-lookup"><span data-stu-id="9bf13-138">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf13-139"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="9bf13-139"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="9bf13-140">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="9bf13-140">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="9bf13-141">Informations supplémentaires sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="9bf13-141">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

