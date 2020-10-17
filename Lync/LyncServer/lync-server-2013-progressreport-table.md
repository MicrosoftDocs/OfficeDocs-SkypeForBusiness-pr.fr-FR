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
ms.openlocfilehash: c92adf48a09f83c3c3dec18f91e4aadc3a3cbd39
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513231"
---
# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="006d5-102">Table ProgressReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="006d5-102">ProgressReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="006d5-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="006d5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="006d5-104">Les rapports d’avancement sont basés sur les données téléchargées par le client dans la base de données à l’issue d’un appel ou d’une session.</span><span class="sxs-lookup"><span data-stu-id="006d5-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="006d5-105">Les rapports d’avancement sont créés uniquement pour les appels et les sessions que Lync Server 2013 considère comme utiles à des fins de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="006d5-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="006d5-106">Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs mais aux messages qui indiquent l’état des appels ou des messages.</span><span class="sxs-lookup"><span data-stu-id="006d5-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="006d5-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="006d5-107">Column</span></span></th>
<th><span data-ttu-id="006d5-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="006d5-108">Data Type</span></span></th>
<th><span data-ttu-id="006d5-109">Clé/index</span><span class="sxs-lookup"><span data-stu-id="006d5-109">Key/Index</span></span></th>
<th><span data-ttu-id="006d5-110">Détails</span><span class="sxs-lookup"><span data-stu-id="006d5-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="006d5-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="006d5-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="006d5-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="006d5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="006d5-113">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="006d5-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="006d5-114">Date et heure du rapport d’erreurs d’avancement qui contient ce rapport d’avancement.</span><span class="sxs-lookup"><span data-stu-id="006d5-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="006d5-115">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-errorreport-table.md">table errorreport dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="006d5-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="006d5-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="006d5-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="006d5-117">int</span><span class="sxs-lookup"><span data-stu-id="006d5-117">int</span></span></p></td>
<td><p><span data-ttu-id="006d5-118">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="006d5-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="006d5-119">Numéro d’identification utilisé conjointement avec ErrorTime et ProgressReportSeq pour identifier de manière unique un rapport d’avancement.</span><span class="sxs-lookup"><span data-stu-id="006d5-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="006d5-120">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-errorreport-table.md">table errorreport dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="006d5-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="006d5-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="006d5-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="006d5-122">int</span><span class="sxs-lookup"><span data-stu-id="006d5-122">int</span></span></p></td>
<td><p><span data-ttu-id="006d5-123">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="006d5-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="006d5-124">Numéro d’identification qui identifie le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="006d5-124">ID number that identifies the error report.</span></span> <span data-ttu-id="006d5-125">ErrorReportSeq est utilisé conjointement avec ErrorTime pour identifier de manière unique un rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="006d5-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="006d5-126">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-errorreport-table.md">table errorreport dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="006d5-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="006d5-127">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="006d5-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="006d5-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="006d5-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="006d5-129">int</span><span class="sxs-lookup"><span data-stu-id="006d5-129">int</span></span></p></td>
<td><p><span data-ttu-id="006d5-130">Primaire</span><span class="sxs-lookup"><span data-stu-id="006d5-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="006d5-p105">Numéro d’identification utilisé pour identifier le rapport d’avancement. Utilisé conjointement avec ErrorTime et ErrorReportSeq pour identifier de manière unique un rapport d’avancement.</span><span class="sxs-lookup"><span data-stu-id="006d5-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="006d5-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="006d5-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="006d5-134">int</span><span class="sxs-lookup"><span data-stu-id="006d5-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="006d5-135">ID de diagnostic du rapport d’avancement.</span><span class="sxs-lookup"><span data-stu-id="006d5-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="006d5-136">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="006d5-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="006d5-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="006d5-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="006d5-138">int</span><span class="sxs-lookup"><span data-stu-id="006d5-138">int</span></span></p></td>
<td><p><span data-ttu-id="006d5-139">Etranger</span><span class="sxs-lookup"><span data-stu-id="006d5-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="006d5-140">Serveur qui a envoyé le rapport d’erreurs (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="006d5-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="006d5-141">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> . Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="006d5-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="006d5-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="006d5-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="006d5-143">int</span><span class="sxs-lookup"><span data-stu-id="006d5-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="006d5-p107">Processus Lync Server sur lequel porte le rapport. Pour plus d’informations, voir la Table Application.</span><span class="sxs-lookup"><span data-stu-id="006d5-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="006d5-146"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="006d5-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="006d5-147">image</span><span class="sxs-lookup"><span data-stu-id="006d5-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="006d5-148">Détails du rapport d’avancement, stockés dans un format binaire pour économiser de l’espace. Ces données peuvent être converties au format texte en utilisant la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="006d5-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="006d5-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="006d5-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="006d5-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="006d5-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="006d5-151">Unique</span><span class="sxs-lookup"><span data-stu-id="006d5-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="006d5-152">Identificateur unique qui met en corrélation des informations d’heure d’arrivée pour les différents composants impliqués dans la conférence.</span><span class="sxs-lookup"><span data-stu-id="006d5-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="006d5-153">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="006d5-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="006d5-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="006d5-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="006d5-155">int</span><span class="sxs-lookup"><span data-stu-id="006d5-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="006d5-156">Durée (en millisecondes) nécessaire à un composant spécifique pour se joindre à une conférence.</span><span class="sxs-lookup"><span data-stu-id="006d5-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="006d5-157">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="006d5-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

