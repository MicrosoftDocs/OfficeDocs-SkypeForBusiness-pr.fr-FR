---
title: 'Lync Server 2013 : vue d’inscription'
description: 'Lync Server 2013 : vue d’inscription.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be169cafc324f89cacedda154ca49a8ff1ff39aa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578524"
---
# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="ef6fe-103">Vue d’enregistrement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef6fe-103">Registration view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef6fe-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ef6fe-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ef6fe-105">L’affichage Inscription stocke les informations relatives à l’inscription de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-105">The Registration view stores information about user registration.</span></span> <span data-ttu-id="ef6fe-106">Cet affichage a été introduit dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-106">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef6fe-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="ef6fe-107">Column</span></span></th>
<th><span data-ttu-id="ef6fe-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="ef6fe-108">Data Type</span></span></th>
<th><span data-ttu-id="ef6fe-109">Détails</span><span class="sxs-lookup"><span data-stu-id="ef6fe-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef6fe-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="ef6fe-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-112">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-112">Time of session request.</span></span> <span data-ttu-id="ef6fe-113">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="ef6fe-114">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ef6fe-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef6fe-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-116">int</span><span class="sxs-lookup"><span data-stu-id="ef6fe-116">int</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-117">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-117">ID number to identify the session.</span></span> <span data-ttu-id="ef6fe-118">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="ef6fe-119">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ef6fe-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef6fe-120"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-120"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="ef6fe-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-122">Heure de l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-122">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef6fe-123"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-123"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ef6fe-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-125">URI de l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-125">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef6fe-126"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-126"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef6fe-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-128">Type d’URI de l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-128">Type of URI of the user who registered.</span></span> <span data-ttu-id="ef6fe-129">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ef6fe-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef6fe-130"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-130"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef6fe-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-132">Locataire de l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-132">Tenant of the user who registered.</span></span> <span data-ttu-id="ef6fe-133">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ef6fe-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef6fe-134"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-134"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-135">unique</span><span class="sxs-lookup"><span data-stu-id="ef6fe-135">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-136">Identificateur unique du point de terminaison auprès duquel l’utilisateur est inscrit.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-136">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef6fe-137"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-137"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-138">unique</span><span class="sxs-lookup"><span data-stu-id="ef6fe-138">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-139">Identificateur unique utilisé pour différencier les inscriptions du même utilisateur auprès du même point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-139">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef6fe-140"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-140"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-141">DateHeure</span><span class="sxs-lookup"><span data-stu-id="ef6fe-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-142">Heure à laquelle la désinscription a eu lieu.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-142">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef6fe-143"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-143"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef6fe-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-145">Raison de la désinscription.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-145">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef6fe-146"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-146"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef6fe-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-148">Version du client utilisé par l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-148">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef6fe-149"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-149"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-150">int</span><span class="sxs-lookup"><span data-stu-id="ef6fe-150">int</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-151">Client utilisé par l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-151">Client used by the user who registered.</span></span> <span data-ttu-id="ef6fe-152">Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ef6fe-152">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef6fe-153"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-153"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-154">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ef6fe-154">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-155">Catégorie du client utilisée par l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-155">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef6fe-156"><strong>IP</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-156"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-157">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef6fe-157">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-158">Adresse IP avec laquelle l’utilisateur s’est inscrit.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-158">IP Address the user registered with.</span></span> <span data-ttu-id="ef6fe-159">Il peut s’agit d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-159">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef6fe-160"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-160"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-161">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="ef6fe-161">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-p108">ID de dialogue SIP. Le format est :</span><span class="sxs-lookup"><span data-stu-id="ef6fe-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="ef6fe-164">boîte de dialogue ; balise ; à-tag</span><span class="sxs-lookup"><span data-stu-id="ef6fe-164">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef6fe-165"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-165"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-166">int</span><span class="sxs-lookup"><span data-stu-id="ef6fe-166">int</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-p109">Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="ef6fe-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef6fe-170"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-170"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-171">int</span><span class="sxs-lookup"><span data-stu-id="ef6fe-171">int</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-172">ID de diagnostic capturé à partir de l’en-tête SIP.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-172">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef6fe-173"><strong>Inscriptions</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-173"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef6fe-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-175">Nom de domaine complet du serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-175">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef6fe-176"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef6fe-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-178">Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-178">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef6fe-179"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-179"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef6fe-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-181">Nom de domaine complet du serveur Edge utilisé par l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-181">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef6fe-182"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-182"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-183">légèrement</span><span class="sxs-lookup"><span data-stu-id="ef6fe-183">bit</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-184">Indique si l’utilisateur s’est connecté à partir du réseau interne ou non.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-184">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef6fe-185"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-185"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-186">légèrement</span><span class="sxs-lookup"><span data-stu-id="ef6fe-186">bit</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-187">Indique si UserService était disponible au moment de l’inscription.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-187">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef6fe-188"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-188"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-189">légèrement</span><span class="sxs-lookup"><span data-stu-id="ef6fe-189">bit</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-190">Indique si l’inscription a eu lieu auprès du serveur d’inscriptions principal.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-190">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef6fe-191"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-191"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-192">comportant</span><span class="sxs-lookup"><span data-stu-id="ef6fe-192">bigint</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-193">Adresse MAC de l’appareil inscrit.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-193">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef6fe-194"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-194"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef6fe-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-196">Fabricant de l’appareil inscrit.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-196">Manufacturer of the device registered.</span></span> <span data-ttu-id="ef6fe-197">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-manufacturers-table.md">table constructeurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ef6fe-197">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef6fe-198"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ef6fe-198"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ef6fe-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef6fe-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef6fe-200">Version matérielle de l’appareil inscrit.</span><span class="sxs-lookup"><span data-stu-id="ef6fe-200">Hardware version of the device registered.</span></span> <span data-ttu-id="ef6fe-201">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-hardwareversions-table.md">table table hardwareversions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ef6fe-201">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

