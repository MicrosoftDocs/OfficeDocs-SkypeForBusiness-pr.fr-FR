---
title: 'Lync Server 2013 : Table Registration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfee81d83fb58b2fbeccff68a672da47e6770bd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="0baaf-102">Table Registration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0baaf-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0baaf-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="0baaf-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0baaf-104">Chaque enregistrement représente un événement d’inscription utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0baaf-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0baaf-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="0baaf-105">Column</span></span></th>
<th><span data-ttu-id="0baaf-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="0baaf-106">Data Type</span></span></th>
<th><span data-ttu-id="0baaf-107">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="0baaf-107">Key/Index</span></span></th>
<th><span data-ttu-id="0baaf-108">Détails</span><span class="sxs-lookup"><span data-stu-id="0baaf-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0baaf-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="0baaf-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="0baaf-111">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="0baaf-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0baaf-112">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="0baaf-112">Time of session request.</span></span> <span data-ttu-id="0baaf-113">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="0baaf-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0baaf-114">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0baaf-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baaf-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-116">int</span><span class="sxs-lookup"><span data-stu-id="0baaf-116">int</span></span></p></td>
<td><p><span data-ttu-id="0baaf-117">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="0baaf-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0baaf-118">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="0baaf-118">ID number to identify the session.</span></span> <span data-ttu-id="0baaf-119">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="0baaf-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0baaf-120">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0baaf-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baaf-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-122">int</span><span class="sxs-lookup"><span data-stu-id="0baaf-122">int</span></span></p></td>
<td><p><span data-ttu-id="0baaf-123">Externes</span><span class="sxs-lookup"><span data-stu-id="0baaf-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0baaf-124">IDENTIFIant de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0baaf-124">The user ID.</span></span> <span data-ttu-id="0baaf-125">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0baaf-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baaf-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-127">identificateur</span><span class="sxs-lookup"><span data-stu-id="0baaf-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0baaf-128">GUID permettant d’identifier un point de terminaison d’inscription.</span><span class="sxs-lookup"><span data-stu-id="0baaf-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="0baaf-129">En règle générale, l’événement Register sur le même ordinateur que le même utilisateur aura le même ID de point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="0baaf-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="0baaf-130">Différents ordinateurs ont un ID de point de terminaison différent.</span><span class="sxs-lookup"><span data-stu-id="0baaf-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baaf-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-132">Identificateur</span><span class="sxs-lookup"><span data-stu-id="0baaf-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0baaf-133">ID utilisé pour différencier les inscriptions qui impliquent le même utilisateur et le même point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="0baaf-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="0baaf-134">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0baaf-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baaf-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-136">int</span><span class="sxs-lookup"><span data-stu-id="0baaf-136">int</span></span></p></td>
<td><p><span data-ttu-id="0baaf-137">Externes</span><span class="sxs-lookup"><span data-stu-id="0baaf-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0baaf-138">Version du client de l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="0baaf-138">Client version of current user.</span></span> <span data-ttu-id="0baaf-139">Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0baaf-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baaf-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-141">int</span><span class="sxs-lookup"><span data-stu-id="0baaf-141">int</span></span></p></td>
<td><p><span data-ttu-id="0baaf-142">Externes</span><span class="sxs-lookup"><span data-stu-id="0baaf-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0baaf-143">ID du serveur d’inscriptions utilisé pour l’inscription.</span><span class="sxs-lookup"><span data-stu-id="0baaf-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="0baaf-144">Pour plus d’informations, voir le <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0baaf-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baaf-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-146">int</span><span class="sxs-lookup"><span data-stu-id="0baaf-146">int</span></span></p></td>
<td><p><span data-ttu-id="0baaf-147">Externes</span><span class="sxs-lookup"><span data-stu-id="0baaf-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0baaf-148">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="0baaf-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="0baaf-149">Pour plus d’informations, voir la <a href="lync-server-2013-pools-table.md">table pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0baaf-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baaf-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-151">int</span><span class="sxs-lookup"><span data-stu-id="0baaf-151">int</span></span></p></td>
<td><p><span data-ttu-id="0baaf-152">Externes</span><span class="sxs-lookup"><span data-stu-id="0baaf-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0baaf-153">Serveur Edge le passage à l’inscription.</span><span class="sxs-lookup"><span data-stu-id="0baaf-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="0baaf-154">Pour plus d’informations, voir la <a href="lync-server-2013-edgeservers-table.md">table EdgeServers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0baaf-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baaf-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-156">Résolution</span><span class="sxs-lookup"><span data-stu-id="0baaf-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0baaf-157">Si l’utilisateur est connecté à partir d’une connexion interne ou non.</span><span class="sxs-lookup"><span data-stu-id="0baaf-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baaf-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-159">bit</span><span class="sxs-lookup"><span data-stu-id="0baaf-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0baaf-160">Si le UserService est disponible ou non.</span><span class="sxs-lookup"><span data-stu-id="0baaf-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baaf-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-162">bit</span><span class="sxs-lookup"><span data-stu-id="0baaf-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0baaf-163">S’il est inscrit au bureau d’enregistrement principal ou non.</span><span class="sxs-lookup"><span data-stu-id="0baaf-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baaf-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-165">bit</span><span class="sxs-lookup"><span data-stu-id="0baaf-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0baaf-166">Indique si l’utilisateur est inscrit auprès d’une unité de branchement survivant.</span><span class="sxs-lookup"><span data-stu-id="0baaf-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="0baaf-167">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0baaf-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baaf-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-169">DateHeure</span><span class="sxs-lookup"><span data-stu-id="0baaf-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0baaf-170">Durée de l’inscription.</span><span class="sxs-lookup"><span data-stu-id="0baaf-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baaf-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-172">DateHeure</span><span class="sxs-lookup"><span data-stu-id="0baaf-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0baaf-173">Durée de l’inscription.</span><span class="sxs-lookup"><span data-stu-id="0baaf-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baaf-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-175">int</span><span class="sxs-lookup"><span data-stu-id="0baaf-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0baaf-176">Code de réponse de la demande Register.</span><span class="sxs-lookup"><span data-stu-id="0baaf-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baaf-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-178">int</span><span class="sxs-lookup"><span data-stu-id="0baaf-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0baaf-179">ID de diagnostic de la demande d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="0baaf-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="0baaf-180">Ce type d’informations indique ce type d’informations de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="0baaf-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baaf-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-182">int</span><span class="sxs-lookup"><span data-stu-id="0baaf-182">int</span></span></p></td>
<td><p><span data-ttu-id="0baaf-183">Externes</span><span class="sxs-lookup"><span data-stu-id="0baaf-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0baaf-184">L’appareil à partir duquel la requête d’enregistrement provient.</span><span class="sxs-lookup"><span data-stu-id="0baaf-184">The device that the register request is coming from.</span></span> <span data-ttu-id="0baaf-185">Pour plus d’informations, voir le <a href="lync-server-2013-devices-table.md">tableau des appareils dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0baaf-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baaf-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="0baaf-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0baaf-188">Externes</span><span class="sxs-lookup"><span data-stu-id="0baaf-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0baaf-189">La raison de l’annulation de l’inscription, par exemple «initié par l’utilisateur», «inscription expirée», «échec du client», etc.</span><span class="sxs-lookup"><span data-stu-id="0baaf-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="0baaf-190">Pour plus d’informations, voir la <a href="lync-server-2013-deregistertype-table.md">table DeRegisterType dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0baaf-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baaf-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="0baaf-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="0baaf-192">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0baaf-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0baaf-193">Adresse IP du point de terminaison avec lequel l’utilisateur a été enregistré.</span><span class="sxs-lookup"><span data-stu-id="0baaf-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="0baaf-194">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="0baaf-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="0baaf-195">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0baaf-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

