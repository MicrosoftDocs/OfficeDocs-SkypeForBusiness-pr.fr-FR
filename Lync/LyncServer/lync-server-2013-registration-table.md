---
title: 'Lync Server 2013 : Table Registration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bc19c35893b12aae7842be5fc474f7831b7f979
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="43982-102">Table Registration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43982-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43982-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="43982-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="43982-104">Chaque enregistrement représente un événement d’inscription utilisateur.</span><span class="sxs-lookup"><span data-stu-id="43982-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43982-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="43982-105">Column</span></span></th>
<th><span data-ttu-id="43982-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="43982-106">Data Type</span></span></th>
<th><span data-ttu-id="43982-107">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="43982-107">Key/Index</span></span></th>
<th><span data-ttu-id="43982-108">Détails</span><span class="sxs-lookup"><span data-stu-id="43982-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43982-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="43982-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="43982-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="43982-111">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="43982-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="43982-112">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="43982-112">Time of session request.</span></span> <span data-ttu-id="43982-113">Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="43982-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="43982-114">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="43982-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43982-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="43982-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-116">int</span><span class="sxs-lookup"><span data-stu-id="43982-116">int</span></span></p></td>
<td><p><span data-ttu-id="43982-117">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="43982-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="43982-118">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="43982-118">ID number to identify the session.</span></span> <span data-ttu-id="43982-119">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="43982-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="43982-120">Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="43982-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43982-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="43982-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-122">int</span><span class="sxs-lookup"><span data-stu-id="43982-122">int</span></span></p></td>
<td><p><span data-ttu-id="43982-123">Externes</span><span class="sxs-lookup"><span data-stu-id="43982-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="43982-124">IDENTIFIant de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="43982-124">The user ID.</span></span> <span data-ttu-id="43982-125">Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="43982-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43982-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="43982-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-127">identificateur</span><span class="sxs-lookup"><span data-stu-id="43982-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43982-128">GUID permettant d’identifier un point de terminaison d’inscription.</span><span class="sxs-lookup"><span data-stu-id="43982-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="43982-129">En règle générale, l’événement Register sur le même ordinateur que le même utilisateur aura le même ID de point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="43982-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="43982-130">Différents ordinateurs ont un ID de point de terminaison différent.</span><span class="sxs-lookup"><span data-stu-id="43982-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43982-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="43982-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-132">Identificateur</span><span class="sxs-lookup"><span data-stu-id="43982-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43982-133">ID utilisé pour différencier les inscriptions qui impliquent le même utilisateur et le même point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="43982-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="43982-134">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43982-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43982-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="43982-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-136">int</span><span class="sxs-lookup"><span data-stu-id="43982-136">int</span></span></p></td>
<td><p><span data-ttu-id="43982-137">Externes</span><span class="sxs-lookup"><span data-stu-id="43982-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="43982-138">Version du client de l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="43982-138">Client version of current user.</span></span> <span data-ttu-id="43982-139">Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="43982-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43982-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="43982-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-141">int</span><span class="sxs-lookup"><span data-stu-id="43982-141">int</span></span></p></td>
<td><p><span data-ttu-id="43982-142">Externes</span><span class="sxs-lookup"><span data-stu-id="43982-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="43982-143">ID du serveur d’inscriptions utilisé pour l’inscription.</span><span class="sxs-lookup"><span data-stu-id="43982-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="43982-144">Pour plus d’informations, voir le <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="43982-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43982-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="43982-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-146">int</span><span class="sxs-lookup"><span data-stu-id="43982-146">int</span></span></p></td>
<td><p><span data-ttu-id="43982-147">Externes</span><span class="sxs-lookup"><span data-stu-id="43982-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="43982-148">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="43982-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="43982-149">Pour plus d’informations, voir la <a href="lync-server-2013-pools-table.md">table pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="43982-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43982-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="43982-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-151">int</span><span class="sxs-lookup"><span data-stu-id="43982-151">int</span></span></p></td>
<td><p><span data-ttu-id="43982-152">Externes</span><span class="sxs-lookup"><span data-stu-id="43982-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="43982-153">Serveur Edge le passage à l’inscription.</span><span class="sxs-lookup"><span data-stu-id="43982-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="43982-154">Pour plus d’informations, voir la <a href="lync-server-2013-edgeservers-table.md">table EdgeServers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="43982-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43982-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="43982-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-156">Résolution</span><span class="sxs-lookup"><span data-stu-id="43982-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43982-157">Si l’utilisateur est connecté à partir d’une connexion interne ou non.</span><span class="sxs-lookup"><span data-stu-id="43982-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43982-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="43982-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-159">bit</span><span class="sxs-lookup"><span data-stu-id="43982-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43982-160">Si le UserService est disponible ou non.</span><span class="sxs-lookup"><span data-stu-id="43982-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43982-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="43982-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-162">bit</span><span class="sxs-lookup"><span data-stu-id="43982-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43982-163">S’il est inscrit au bureau d’enregistrement principal ou non.</span><span class="sxs-lookup"><span data-stu-id="43982-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43982-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="43982-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-165">bit</span><span class="sxs-lookup"><span data-stu-id="43982-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43982-166">Indique si l’utilisateur est inscrit auprès d’une unité de branchement survivant.</span><span class="sxs-lookup"><span data-stu-id="43982-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="43982-167">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43982-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43982-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="43982-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-169">DateHeure</span><span class="sxs-lookup"><span data-stu-id="43982-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43982-170">Durée de l’inscription.</span><span class="sxs-lookup"><span data-stu-id="43982-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43982-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="43982-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-172">DateHeure</span><span class="sxs-lookup"><span data-stu-id="43982-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43982-173">Durée de l’inscription.</span><span class="sxs-lookup"><span data-stu-id="43982-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43982-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="43982-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-175">int</span><span class="sxs-lookup"><span data-stu-id="43982-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43982-176">Code de réponse de la demande Register.</span><span class="sxs-lookup"><span data-stu-id="43982-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43982-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="43982-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-178">int</span><span class="sxs-lookup"><span data-stu-id="43982-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43982-179">ID de diagnostic de la demande d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="43982-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="43982-180">Ce type d’informations indique ce type d’informations de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="43982-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43982-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="43982-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-182">int</span><span class="sxs-lookup"><span data-stu-id="43982-182">int</span></span></p></td>
<td><p><span data-ttu-id="43982-183">Externes</span><span class="sxs-lookup"><span data-stu-id="43982-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="43982-184">L’appareil à partir duquel la requête d’enregistrement provient.</span><span class="sxs-lookup"><span data-stu-id="43982-184">The device that the register request is coming from.</span></span> <span data-ttu-id="43982-185">Pour plus d’informations, voir le <a href="lync-server-2013-devices-table.md">tableau des appareils dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="43982-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43982-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="43982-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="43982-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="43982-188">Externes</span><span class="sxs-lookup"><span data-stu-id="43982-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="43982-189">La raison de l’annulation de l’inscription, par exemple « initié par l’utilisateur », « inscription expirée », « échec du client », etc.</span><span class="sxs-lookup"><span data-stu-id="43982-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="43982-190">Pour plus d’informations, voir la <a href="lync-server-2013-deregistertype-table.md">table DeRegisterType dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="43982-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43982-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="43982-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="43982-192">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="43982-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43982-193">Adresse IP du point de terminaison avec lequel l’utilisateur a été enregistré.</span><span class="sxs-lookup"><span data-stu-id="43982-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="43982-194">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="43982-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="43982-195">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43982-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

