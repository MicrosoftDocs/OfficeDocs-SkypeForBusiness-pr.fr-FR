---
title: 'Lync Server 2013 : Table ProgressReport'
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
ms.openlocfilehash: 2e1cb7c8e764097af96981220ee74d481b379341
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="33eb6-102">Table ProgressReport dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33eb6-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33eb6-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="33eb6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="33eb6-104">Les rapports de progression sont basés sur les données chargées par le client dans la base de données une fois l’appel ou la session terminée.</span><span class="sxs-lookup"><span data-stu-id="33eb6-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="33eb6-105">Les rapports de progression seront écrits uniquement pour les appels et les sessions que Lync Server 2013 détermine peut être utile à des fins de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="33eb6-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="33eb6-106">Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs, mais aux messages indiquant l’état des appels ou des messages.</span><span class="sxs-lookup"><span data-stu-id="33eb6-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33eb6-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="33eb6-107">Column</span></span></th>
<th><span data-ttu-id="33eb6-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="33eb6-108">Data Type</span></span></th>
<th><span data-ttu-id="33eb6-109">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="33eb6-109">Key/Index</span></span></th>
<th><span data-ttu-id="33eb6-110">Détails</span><span class="sxs-lookup"><span data-stu-id="33eb6-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33eb6-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="33eb6-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33eb6-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="33eb6-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="33eb6-113">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="33eb6-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="33eb6-114">Date et heure du rapport d’erreur de progression contenant ce rapport de progression.</span><span class="sxs-lookup"><span data-stu-id="33eb6-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="33eb6-115">Pour plus d’informations, voir la <a href="lync-server-2013-errorreport-table.md">table errorreport dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33eb6-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33eb6-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="33eb6-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="33eb6-117">int</span><span class="sxs-lookup"><span data-stu-id="33eb6-117">int</span></span></p></td>
<td><p><span data-ttu-id="33eb6-118">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="33eb6-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="33eb6-119">Numéro d’identification utilisé conjointement avec ErrorTime, ProgressReportSeq pour identifier de façon unique un rapport de progression.</span><span class="sxs-lookup"><span data-stu-id="33eb6-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="33eb6-120">Pour plus d’informations, voir la <a href="lync-server-2013-errorreport-table.md">table errorreport dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33eb6-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33eb6-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="33eb6-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="33eb6-122">int</span><span class="sxs-lookup"><span data-stu-id="33eb6-122">int</span></span></p></td>
<td><p><span data-ttu-id="33eb6-123">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="33eb6-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="33eb6-124">Numéro identifiant le rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="33eb6-124">ID number that identifies the error report.</span></span> <span data-ttu-id="33eb6-125">ErrorReporSeq est utilisé en conjonction avec ErrorTime pour identifier de manière unique un rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="33eb6-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="33eb6-126">Pour plus d’informations, voir la <a href="lync-server-2013-errorreport-table.md">table errorreport dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="33eb6-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="33eb6-127">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33eb6-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33eb6-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="33eb6-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="33eb6-129">int</span><span class="sxs-lookup"><span data-stu-id="33eb6-129">int</span></span></p></td>
<td><p><span data-ttu-id="33eb6-130">Principal</span><span class="sxs-lookup"><span data-stu-id="33eb6-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="33eb6-131">Numéro d’identification pour identifier le rapport de progression.</span><span class="sxs-lookup"><span data-stu-id="33eb6-131">ID number to identify the progress report.</span></span> <span data-ttu-id="33eb6-132">Utilisé conjointement avec ErrorTime et ErrorReportSeq pour identifier de manière unique un rapport de progression.</span><span class="sxs-lookup"><span data-stu-id="33eb6-132">Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33eb6-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="33eb6-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="33eb6-134">int</span><span class="sxs-lookup"><span data-stu-id="33eb6-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="33eb6-135">ID de diagnostic du rapport de progression.</span><span class="sxs-lookup"><span data-stu-id="33eb6-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="33eb6-136">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33eb6-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33eb6-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="33eb6-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="33eb6-138">int</span><span class="sxs-lookup"><span data-stu-id="33eb6-138">int</span></span></p></td>
<td><p><span data-ttu-id="33eb6-139">Externes</span><span class="sxs-lookup"><span data-stu-id="33eb6-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="33eb6-140">Serveur ayant envoyé le rapport d’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="33eb6-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="33eb6-141">Pour plus d’informations, voir le <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> . Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33eb6-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33eb6-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="33eb6-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="33eb6-143">int</span><span class="sxs-lookup"><span data-stu-id="33eb6-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="33eb6-144">Le processus serveur Lync dont le rapport est sujet.</span><span class="sxs-lookup"><span data-stu-id="33eb6-144">The Lync Server process that the report is about.</span></span> <span data-ttu-id="33eb6-145">Pour plus d’informations, consultez le tableau de l’application.</span><span class="sxs-lookup"><span data-stu-id="33eb6-145">See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33eb6-146"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="33eb6-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="33eb6-147">image</span><span class="sxs-lookup"><span data-stu-id="33eb6-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="33eb6-148">Détails du rapport de progression, enregistrés au format binaire pour économiser de l’espace. Il est possible de convertir les données au format texte à l’aide de la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="33eb6-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="33eb6-149">Cast (de type « detail ») As varchar (max))</span><span class="sxs-lookup"><span data-stu-id="33eb6-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33eb6-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="33eb6-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="33eb6-151">Identificateur</span><span class="sxs-lookup"><span data-stu-id="33eb6-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="33eb6-152">Identificateur unique qui met en corrélation les informations de connexion aux différents composants impliqués dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="33eb6-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="33eb6-153">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33eb6-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33eb6-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="33eb6-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="33eb6-155">int</span><span class="sxs-lookup"><span data-stu-id="33eb6-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="33eb6-156">Durée (en millisecondes) d’un composant spécifique pour participer à une conférence.</span><span class="sxs-lookup"><span data-stu-id="33eb6-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="33eb6-157">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33eb6-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

