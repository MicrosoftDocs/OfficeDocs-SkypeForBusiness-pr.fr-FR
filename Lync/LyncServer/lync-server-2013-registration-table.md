---
title: 'Lync Server 2013 : table d’enregistrement'
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
ms.openlocfilehash: 0679915e73061e550e01c0809fd5c5b20b566ff6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="530c5-102">Table Registration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="530c5-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="530c5-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="530c5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="530c5-104">Chaque enregistrement représente un événement relatif à l’inscription d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="530c5-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="530c5-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="530c5-105">Column</span></span></th>
<th><span data-ttu-id="530c5-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="530c5-106">Data Type</span></span></th>
<th><span data-ttu-id="530c5-107">Clé/index</span><span class="sxs-lookup"><span data-stu-id="530c5-107">Key/Index</span></span></th>
<th><span data-ttu-id="530c5-108">Détails</span><span class="sxs-lookup"><span data-stu-id="530c5-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="530c5-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="530c5-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="530c5-111">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="530c5-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="530c5-112">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="530c5-112">Time of session request.</span></span> <span data-ttu-id="530c5-113">Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="530c5-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="530c5-114">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="530c5-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="530c5-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-116">int</span><span class="sxs-lookup"><span data-stu-id="530c5-116">int</span></span></p></td>
<td><p><span data-ttu-id="530c5-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="530c5-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="530c5-118">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="530c5-118">ID number to identify the session.</span></span> <span data-ttu-id="530c5-119">Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="530c5-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="530c5-120">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="530c5-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="530c5-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-122">int</span><span class="sxs-lookup"><span data-stu-id="530c5-122">int</span></span></p></td>
<td><p><span data-ttu-id="530c5-123">Etranger</span><span class="sxs-lookup"><span data-stu-id="530c5-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="530c5-124">ID de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="530c5-124">The user ID.</span></span> <span data-ttu-id="530c5-125">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="530c5-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="530c5-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-127">unique</span><span class="sxs-lookup"><span data-stu-id="530c5-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="530c5-p104">GUID pour identifier un système d’extrémité d’inscription. Généralement, l’événement d’inscription d’un même ordinateur et d’un même utilisateur aura le même ID de système d’extrémité. Des ordinateurs différents ont un ID de système d’extrémité différent.</span><span class="sxs-lookup"><span data-stu-id="530c5-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="530c5-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-132">Unique</span><span class="sxs-lookup"><span data-stu-id="530c5-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="530c5-133">ID utilisé pour différencier des inscriptions qui impliquent le même utilisateur et le même point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="530c5-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="530c5-134">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="530c5-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="530c5-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-136">int</span><span class="sxs-lookup"><span data-stu-id="530c5-136">int</span></span></p></td>
<td><p><span data-ttu-id="530c5-137">Etranger</span><span class="sxs-lookup"><span data-stu-id="530c5-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="530c5-138">Version du client de l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="530c5-138">Client version of current user.</span></span> <span data-ttu-id="530c5-139">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="530c5-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="530c5-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-141">int</span><span class="sxs-lookup"><span data-stu-id="530c5-141">int</span></span></p></td>
<td><p><span data-ttu-id="530c5-142">Etranger</span><span class="sxs-lookup"><span data-stu-id="530c5-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="530c5-143">ID du serveur d’inscriptions utilisé pour l’inscription.</span><span class="sxs-lookup"><span data-stu-id="530c5-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="530c5-144">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="530c5-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="530c5-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-146">int</span><span class="sxs-lookup"><span data-stu-id="530c5-146">int</span></span></p></td>
<td><p><span data-ttu-id="530c5-147">Etranger</span><span class="sxs-lookup"><span data-stu-id="530c5-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="530c5-148">ID du pool dans lequel la session a été capturée.</span><span class="sxs-lookup"><span data-stu-id="530c5-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="530c5-149">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-pools-table.md">tableau pools dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="530c5-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="530c5-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-151">int</span><span class="sxs-lookup"><span data-stu-id="530c5-151">int</span></span></p></td>
<td><p><span data-ttu-id="530c5-152">Etranger</span><span class="sxs-lookup"><span data-stu-id="530c5-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="530c5-153">Serveur Edge sur lequel l’inscription a lieu.</span><span class="sxs-lookup"><span data-stu-id="530c5-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="530c5-154">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">table table edgeservers dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="530c5-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="530c5-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-156">Légèrement</span><span class="sxs-lookup"><span data-stu-id="530c5-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="530c5-157">Si l’utilisateur est connecté en interne ou non.</span><span class="sxs-lookup"><span data-stu-id="530c5-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="530c5-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-159">légèrement</span><span class="sxs-lookup"><span data-stu-id="530c5-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="530c5-160">Si UserService est disponible ou non.</span><span class="sxs-lookup"><span data-stu-id="530c5-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="530c5-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-162">légèrement</span><span class="sxs-lookup"><span data-stu-id="530c5-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="530c5-163">Si l’inscription est effectuée sur le serveur d’inscriptions principal ou non.</span><span class="sxs-lookup"><span data-stu-id="530c5-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="530c5-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-165">légèrement</span><span class="sxs-lookup"><span data-stu-id="530c5-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="530c5-166">Indique si l’utilisateur est inscrit ou non avec un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="530c5-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="530c5-167">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="530c5-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="530c5-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-169">DateHeure</span><span class="sxs-lookup"><span data-stu-id="530c5-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="530c5-170">Heure d’inscription.</span><span class="sxs-lookup"><span data-stu-id="530c5-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="530c5-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-172">DateHeure</span><span class="sxs-lookup"><span data-stu-id="530c5-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="530c5-173">Heure de désinscription.</span><span class="sxs-lookup"><span data-stu-id="530c5-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="530c5-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-175">int</span><span class="sxs-lookup"><span data-stu-id="530c5-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="530c5-176">Code de réponse de la demande d’inscription.</span><span class="sxs-lookup"><span data-stu-id="530c5-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="530c5-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-178">int</span><span class="sxs-lookup"><span data-stu-id="530c5-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="530c5-p109">ID de diagnostic de la demande d’inscription. Indique les informations du type de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="530c5-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="530c5-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-182">int</span><span class="sxs-lookup"><span data-stu-id="530c5-182">int</span></span></p></td>
<td><p><span data-ttu-id="530c5-183">Etranger</span><span class="sxs-lookup"><span data-stu-id="530c5-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="530c5-184">L’appareil à partir duquel est émise la demande d’inscription.</span><span class="sxs-lookup"><span data-stu-id="530c5-184">The device that the register request is coming from.</span></span> <span data-ttu-id="530c5-185">Pour plus d’informations, reportez-vous au <a href="lync-server-2013-devices-table.md">tableau périphériques dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="530c5-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="530c5-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-187">entier très petit</span><span class="sxs-lookup"><span data-stu-id="530c5-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="530c5-188">Etranger</span><span class="sxs-lookup"><span data-stu-id="530c5-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="530c5-189">La raison de l’annulation de l’inscription, par exemple « initié par l’utilisateur », « expiration de l’inscription », « échec du client », et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="530c5-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="530c5-190">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-deregistertype-table.md">table DeRegisterType dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="530c5-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="530c5-191"><strong>IP</strong></span><span class="sxs-lookup"><span data-stu-id="530c5-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="530c5-192">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="530c5-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="530c5-193">Adresse IP du point de terminaison avec laquelle l’utilisateur s’est inscrit.</span><span class="sxs-lookup"><span data-stu-id="530c5-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="530c5-194">Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="530c5-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="530c5-195">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="530c5-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

