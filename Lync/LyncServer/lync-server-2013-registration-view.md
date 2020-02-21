---
title: 'Lync Server 2013 : vue d’inscription'
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
ms.openlocfilehash: d3683965562d01c5aff33000450182c83e4d4c7b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="a564e-102">Vue d’enregistrement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a564e-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a564e-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a564e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a564e-104">L’affichage Inscription stocke les informations relatives à l’inscription de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a564e-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="a564e-105">Cet affichage a été introduit dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a564e-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a564e-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="a564e-106">Column</span></span></th>
<th><span data-ttu-id="a564e-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="a564e-107">Data Type</span></span></th>
<th><span data-ttu-id="a564e-108">Détails</span><span class="sxs-lookup"><span data-stu-id="a564e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a564e-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="a564e-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a564e-111">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="a564e-111">Time of session request.</span></span> <span data-ttu-id="a564e-112">Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="a564e-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="a564e-113">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a564e-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a564e-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-115">int</span><span class="sxs-lookup"><span data-stu-id="a564e-115">int</span></span></p></td>
<td><p><span data-ttu-id="a564e-116">Numéro d’identification de la session.</span><span class="sxs-lookup"><span data-stu-id="a564e-116">ID number to identify the session.</span></span> <span data-ttu-id="a564e-117">Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="a564e-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="a564e-118">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a564e-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a564e-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-120">DateHeure</span><span class="sxs-lookup"><span data-stu-id="a564e-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="a564e-121">Heure de l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="a564e-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a564e-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a564e-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a564e-124">URI de l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="a564e-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a564e-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a564e-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a564e-127">Type d’URI de l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="a564e-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="a564e-128">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a564e-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a564e-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a564e-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a564e-131">Locataire de l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="a564e-131">Tenant of the user who registered.</span></span> <span data-ttu-id="a564e-132">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a564e-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a564e-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-134">unique</span><span class="sxs-lookup"><span data-stu-id="a564e-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a564e-135">Identificateur unique du point de terminaison auprès duquel l’utilisateur est inscrit.</span><span class="sxs-lookup"><span data-stu-id="a564e-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a564e-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-137">unique</span><span class="sxs-lookup"><span data-stu-id="a564e-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a564e-138">Identificateur unique utilisé pour différencier les inscriptions du même utilisateur auprès du même point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="a564e-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a564e-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-140">DateHeure</span><span class="sxs-lookup"><span data-stu-id="a564e-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="a564e-141">Heure à laquelle la désinscription a eu lieu.</span><span class="sxs-lookup"><span data-stu-id="a564e-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a564e-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a564e-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a564e-144">Raison de la désinscription.</span><span class="sxs-lookup"><span data-stu-id="a564e-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a564e-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a564e-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a564e-147">Version du client utilisé par l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="a564e-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a564e-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-149">int</span><span class="sxs-lookup"><span data-stu-id="a564e-149">int</span></span></p></td>
<td><p><span data-ttu-id="a564e-150">Client utilisé par l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="a564e-150">Client used by the user who registered.</span></span> <span data-ttu-id="a564e-151">Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a564e-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a564e-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a564e-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a564e-154">Catégorie du client utilisée par l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="a564e-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a564e-155"><strong>IP</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-156">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a564e-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a564e-157">Adresse IP avec laquelle l’utilisateur s’est inscrit.</span><span class="sxs-lookup"><span data-stu-id="a564e-157">IP Address the user registered with.</span></span> <span data-ttu-id="a564e-158">Il peut s’agit d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="a564e-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a564e-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-160">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="a564e-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="a564e-p108">ID de dialogue SIP. Le format est :</span><span class="sxs-lookup"><span data-stu-id="a564e-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="a564e-163">boîte de dialogue ; balise ; à-tag</span><span class="sxs-lookup"><span data-stu-id="a564e-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a564e-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-165">int</span><span class="sxs-lookup"><span data-stu-id="a564e-165">int</span></span></p></td>
<td><p><span data-ttu-id="a564e-p109">Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="a564e-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a564e-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-170">int</span><span class="sxs-lookup"><span data-stu-id="a564e-170">int</span></span></p></td>
<td><p><span data-ttu-id="a564e-171">ID de diagnostic capturé à partir de l’en-tête SIP.</span><span class="sxs-lookup"><span data-stu-id="a564e-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a564e-172"><strong>Inscriptions</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a564e-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a564e-174">Nom de domaine complet du serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="a564e-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a564e-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a564e-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a564e-177">Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="a564e-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a564e-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a564e-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a564e-180">Nom de domaine complet du serveur Edge utilisé par l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="a564e-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a564e-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-182">légèrement</span><span class="sxs-lookup"><span data-stu-id="a564e-182">bit</span></span></p></td>
<td><p><span data-ttu-id="a564e-183">Indique si l’utilisateur s’est connecté à partir du réseau interne ou non.</span><span class="sxs-lookup"><span data-stu-id="a564e-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a564e-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-185">légèrement</span><span class="sxs-lookup"><span data-stu-id="a564e-185">bit</span></span></p></td>
<td><p><span data-ttu-id="a564e-186">Indique si UserService était disponible au moment de l’inscription.</span><span class="sxs-lookup"><span data-stu-id="a564e-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a564e-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-188">légèrement</span><span class="sxs-lookup"><span data-stu-id="a564e-188">bit</span></span></p></td>
<td><p><span data-ttu-id="a564e-189">Indique si l’inscription a eu lieu auprès du serveur d’inscriptions principal.</span><span class="sxs-lookup"><span data-stu-id="a564e-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a564e-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-191">comportant</span><span class="sxs-lookup"><span data-stu-id="a564e-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="a564e-192">Adresse MAC de l’appareil inscrit.</span><span class="sxs-lookup"><span data-stu-id="a564e-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a564e-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a564e-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a564e-195">Fabricant de l’appareil inscrit.</span><span class="sxs-lookup"><span data-stu-id="a564e-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="a564e-196">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-manufacturers-table.md">table constructeurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a564e-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a564e-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a564e-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a564e-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a564e-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a564e-199">Version matérielle de l’appareil inscrit.</span><span class="sxs-lookup"><span data-stu-id="a564e-199">Hardware version of the device registered.</span></span> <span data-ttu-id="a564e-200">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-hardwareversions-table.md">table table hardwareversions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a564e-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

