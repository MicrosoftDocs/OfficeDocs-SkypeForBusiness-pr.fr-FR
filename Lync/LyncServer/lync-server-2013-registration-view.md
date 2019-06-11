---
title: 'Lync Server 2013: affichage d’inscription'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe1b01b748204d3d4365b6f28ae4480d3632b35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="17e60-102">Affichage inscription dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17e60-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17e60-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="17e60-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="17e60-104">Le mode d’enregistrement enregistre des informations sur l’inscription des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="17e60-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="17e60-105">Cet affichage a été présenté dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17e60-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17e60-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="17e60-106">Column</span></span></th>
<th><span data-ttu-id="17e60-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="17e60-107">Data Type</span></span></th>
<th><span data-ttu-id="17e60-108">Détails</span><span class="sxs-lookup"><span data-stu-id="17e60-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17e60-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="17e60-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="17e60-111">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="17e60-111">Time of session request.</span></span> <span data-ttu-id="17e60-112">Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="17e60-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="17e60-113">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17e60-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e60-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-115">int</span><span class="sxs-lookup"><span data-stu-id="17e60-115">int</span></span></p></td>
<td><p><span data-ttu-id="17e60-116">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="17e60-116">ID number to identify the session.</span></span> <span data-ttu-id="17e60-117">Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="17e60-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="17e60-118">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17e60-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17e60-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-120">DateHeure</span><span class="sxs-lookup"><span data-stu-id="17e60-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="17e60-121">Heure à laquelle l’inscription s’est produite.</span><span class="sxs-lookup"><span data-stu-id="17e60-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e60-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="17e60-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="17e60-124">URI de l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="17e60-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17e60-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="17e60-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="17e60-127">Type d’URI de l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="17e60-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="17e60-128">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17e60-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e60-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="17e60-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="17e60-131">Client de l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="17e60-131">Tenant of the user who registered.</span></span> <span data-ttu-id="17e60-132">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17e60-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17e60-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-134">identificateur</span><span class="sxs-lookup"><span data-stu-id="17e60-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="17e60-135">Identificateur unique du point de terminaison de l’utilisateur enregistré avec.</span><span class="sxs-lookup"><span data-stu-id="17e60-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e60-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-137">identificateur</span><span class="sxs-lookup"><span data-stu-id="17e60-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="17e60-138">Identificateur unique utilisé pour différencier les inscriptions qui impliquent le même utilisateur et le même point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="17e60-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17e60-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-140">DateHeure</span><span class="sxs-lookup"><span data-stu-id="17e60-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="17e60-141">Heure à laquelle l’annulation de l’inscription s’est produite.</span><span class="sxs-lookup"><span data-stu-id="17e60-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e60-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="17e60-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="17e60-144">Raison de l’annulation de l’inscription.</span><span class="sxs-lookup"><span data-stu-id="17e60-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17e60-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-146">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="17e60-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="17e60-147">Version du client utilisée par l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="17e60-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e60-148"><strong>TypeClient</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-149">int</span><span class="sxs-lookup"><span data-stu-id="17e60-149">int</span></span></p></td>
<td><p><span data-ttu-id="17e60-150">Client utilisé par l’utilisateur inscrit.</span><span class="sxs-lookup"><span data-stu-id="17e60-150">Client used by the user who registered.</span></span> <span data-ttu-id="17e60-151">Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17e60-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17e60-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="17e60-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="17e60-154">Catégorie du client utilisée par l’utilisateur qui est inscrit.</span><span class="sxs-lookup"><span data-stu-id="17e60-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e60-155"><strong>Grat</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-156">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="17e60-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="17e60-157">Adresse IP de l’utilisateur avec lequel il a été enregistré.</span><span class="sxs-lookup"><span data-stu-id="17e60-157">IP Address the user registered with.</span></span> <span data-ttu-id="17e60-158">Il s’agit éventuellement d’une adresse IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="17e60-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17e60-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-160">varstring (LGA775)</span><span class="sxs-lookup"><span data-stu-id="17e60-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="17e60-161">ID de boîte de dialogue SIP.</span><span class="sxs-lookup"><span data-stu-id="17e60-161">SIP dialog ID.</span></span> <span data-ttu-id="17e60-162">Le format de:</span><span class="sxs-lookup"><span data-stu-id="17e60-162">The format of the is:</span></span></p>
<p><span data-ttu-id="17e60-163">boîte de dialogue; à partir d’une balise</span><span class="sxs-lookup"><span data-stu-id="17e60-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e60-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-165">int</span><span class="sxs-lookup"><span data-stu-id="17e60-165">int</span></span></p></td>
<td><p><span data-ttu-id="17e60-166">Code de réponse SIP à l’invitation de la session.</span><span class="sxs-lookup"><span data-stu-id="17e60-166">SIP response code to the session invitation.</span></span> <span data-ttu-id="17e60-167">Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session.</span><span class="sxs-lookup"><span data-stu-id="17e60-167">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="17e60-168">S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</span><span class="sxs-lookup"><span data-stu-id="17e60-168">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17e60-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-170">int</span><span class="sxs-lookup"><span data-stu-id="17e60-170">int</span></span></p></td>
<td><p><span data-ttu-id="17e60-171">ID de diagnostic capturé à partir de l’en-tête SIP.</span><span class="sxs-lookup"><span data-stu-id="17e60-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e60-172"><strong>serveur d’inscriptions</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="17e60-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="17e60-174">Nom de domaine complet du Bureau d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="17e60-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17e60-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="17e60-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="17e60-177">Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.</span><span class="sxs-lookup"><span data-stu-id="17e60-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e60-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="17e60-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="17e60-180">Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur qui est inscrit.</span><span class="sxs-lookup"><span data-stu-id="17e60-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17e60-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-182">bit</span><span class="sxs-lookup"><span data-stu-id="17e60-182">bit</span></span></p></td>
<td><p><span data-ttu-id="17e60-183">Indique si l’utilisateur s’est connecté à partir du réseau interne.</span><span class="sxs-lookup"><span data-stu-id="17e60-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e60-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-185">bit</span><span class="sxs-lookup"><span data-stu-id="17e60-185">bit</span></span></p></td>
<td><p><span data-ttu-id="17e60-186">Indique si l’UserService a été disponible au moment de l’inscription.</span><span class="sxs-lookup"><span data-stu-id="17e60-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17e60-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-188">bit</span><span class="sxs-lookup"><span data-stu-id="17e60-188">bit</span></span></p></td>
<td><p><span data-ttu-id="17e60-189">Indique si l’inscription a été apportée au bureau d’enregistrement principal.</span><span class="sxs-lookup"><span data-stu-id="17e60-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e60-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-191">bigint</span><span class="sxs-lookup"><span data-stu-id="17e60-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="17e60-192">Adresse MAC de l’appareil inscrit.</span><span class="sxs-lookup"><span data-stu-id="17e60-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17e60-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="17e60-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="17e60-195">Fabricant de l’appareil inscrit.</span><span class="sxs-lookup"><span data-stu-id="17e60-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="17e60-196">Pour plus d’informations, reportez-vous <a href="lync-server-2013-manufacturers-table.md">à la table fabricants dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17e60-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e60-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="17e60-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="17e60-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="17e60-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="17e60-199">Version matérielle de l’appareil inscrit.</span><span class="sxs-lookup"><span data-stu-id="17e60-199">Hardware version of the device registered.</span></span> <span data-ttu-id="17e60-200">Pour plus d’informations, voir la <a href="lync-server-2013-hardwareversions-table.md">table HardwareVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="17e60-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

