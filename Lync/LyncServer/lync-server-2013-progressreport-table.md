---
title: 'Lync Server 2013 : table ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50697242b7086dbd81b74d098d200b1162ac12a5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="91f16-102">Table ProgressReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91f16-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91f16-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="91f16-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="91f16-104">Les rapports d’avancement sont basés sur les données téléchargées par le client dans la base de données à l’issue d’un appel ou d’une session.</span><span class="sxs-lookup"><span data-stu-id="91f16-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="91f16-105">Les rapports d’avancement sont créés uniquement pour les appels et les sessions que Lync Server 2013 considère comme utiles à des fins de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="91f16-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="91f16-106">Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs mais aux messages qui indiquent l’état des appels ou des messages.</span><span class="sxs-lookup"><span data-stu-id="91f16-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91f16-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="91f16-107">Column</span></span></th>
<th><span data-ttu-id="91f16-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="91f16-108">Data Type</span></span></th>
<th><span data-ttu-id="91f16-109">Clé/index</span><span class="sxs-lookup"><span data-stu-id="91f16-109">Key/Index</span></span></th>
<th><span data-ttu-id="91f16-110">Détails</span><span class="sxs-lookup"><span data-stu-id="91f16-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91f16-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="91f16-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="91f16-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="91f16-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="91f16-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="91f16-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="91f16-114">Date et heure du rapport d’erreurs d’avancement qui contient ce rapport d’avancement.</span><span class="sxs-lookup"><span data-stu-id="91f16-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="91f16-115">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-errorreport-table.md">table errorreport dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91f16-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91f16-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="91f16-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="91f16-117">int</span><span class="sxs-lookup"><span data-stu-id="91f16-117">int</span></span></p></td>
<td><p><span data-ttu-id="91f16-118">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="91f16-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="91f16-119">Numéro d’identification utilisé conjointement avec ErrorTime et ProgressReportSeq pour identifier de manière unique un rapport d’avancement.</span><span class="sxs-lookup"><span data-stu-id="91f16-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="91f16-120">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-errorreport-table.md">table errorreport dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91f16-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91f16-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="91f16-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="91f16-122">int</span><span class="sxs-lookup"><span data-stu-id="91f16-122">int</span></span></p></td>
<td><p><span data-ttu-id="91f16-123">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="91f16-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="91f16-124">Numéro d’identification qui identifie le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="91f16-124">ID number that identifies the error report.</span></span> <span data-ttu-id="91f16-125">ErrorReportSeq est utilisé conjointement avec ErrorTime pour identifier de manière unique un rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="91f16-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="91f16-126">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-errorreport-table.md">table errorreport dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="91f16-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="91f16-127">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91f16-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91f16-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="91f16-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="91f16-129">int</span><span class="sxs-lookup"><span data-stu-id="91f16-129">int</span></span></p></td>
<td><p><span data-ttu-id="91f16-130">Primaire</span><span class="sxs-lookup"><span data-stu-id="91f16-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="91f16-p105">Numéro d’identification utilisé pour identifier le rapport d’avancement. Utilisé conjointement avec ErrorTime et ErrorReportSeq pour identifier de manière unique un rapport d’avancement.</span><span class="sxs-lookup"><span data-stu-id="91f16-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91f16-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="91f16-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="91f16-134">int</span><span class="sxs-lookup"><span data-stu-id="91f16-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="91f16-135">ID de diagnostic du rapport d’avancement.</span><span class="sxs-lookup"><span data-stu-id="91f16-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="91f16-136">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91f16-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91f16-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="91f16-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="91f16-138">int</span><span class="sxs-lookup"><span data-stu-id="91f16-138">int</span></span></p></td>
<td><p><span data-ttu-id="91f16-139">Etranger</span><span class="sxs-lookup"><span data-stu-id="91f16-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="91f16-140">Serveur qui a envoyé le rapport d’erreurs (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="91f16-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="91f16-141">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> . Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91f16-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91f16-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="91f16-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="91f16-143">int</span><span class="sxs-lookup"><span data-stu-id="91f16-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="91f16-p107">Processus Lync Server sur lequel porte le rapport. Pour plus d’informations, voir la Table Application.</span><span class="sxs-lookup"><span data-stu-id="91f16-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91f16-146"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="91f16-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="91f16-147">image</span><span class="sxs-lookup"><span data-stu-id="91f16-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="91f16-148">Détails du rapport d’avancement, stockés dans un format binaire pour économiser de l’espace. Ces données peuvent être converties au format texte en utilisant la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="91f16-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="91f16-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="91f16-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91f16-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="91f16-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="91f16-151">Unique</span><span class="sxs-lookup"><span data-stu-id="91f16-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="91f16-152">Identificateur unique qui met en corrélation des informations d’heure d’arrivée pour les différents composants impliqués dans la conférence.</span><span class="sxs-lookup"><span data-stu-id="91f16-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="91f16-153">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91f16-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91f16-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="91f16-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="91f16-155">int</span><span class="sxs-lookup"><span data-stu-id="91f16-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="91f16-156">Durée (en millisecondes) nécessaire à un composant spécifique pour se joindre à une conférence.</span><span class="sxs-lookup"><span data-stu-id="91f16-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="91f16-157">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91f16-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

